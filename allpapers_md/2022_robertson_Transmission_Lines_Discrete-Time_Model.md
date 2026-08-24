## Learn About Transmission Lines Using a Discrete-Time Model

We don't often think about signal t ransmission lines, but we use them every day.  Familiar examples are coaxial cable, Ethernet cable, and Universal Serial Bus (USB).  Like it or not, high-speed clock and signal traces on printed-circuit boards are also transmission lines.

While modeling transmission lines is in general a complex undertaking, it is surprisingly simple to model a lossless, uniform line with resistive terminations by using a discrete-time approach.  A discrete-time model easily computes both time and frequency responses, and serves as a good learning tool.  In this post, I provide discrete-time Matlab functions tline and wave\_movie , and use them to model lossless uniform transmission lines (note these simple models can approximate lossy transmission lines only if they are short). Before delving into transmission line math, let's look at a practical case:  a pulse on a printed-circuit board (PCB) trace.

## Example 1.  Pulse on a microstrip line

A microstrip transmission line consists of a trace on the top layer of a PCB with a ground plane on a lower layer.  Figure 1 shows a cross section of a microstrip line of length L = 10 cm, fed by a digital driver and terminated in a buffer. We will neglect the buffer's input capacitance, and assume a resistive load as shown.  We also assume no discontinuities along the line, such as sharp bends or vias.  Let the line have a propagation velocity of 0.55 times the speed of light and a characteristic impedance Z0 of 75 ohms.  Z0 can be calculated from the line's dimensions and substrate properties [1].  There are also microstrip impedance calculators available on the web [2].

Now suppose the total source resistance RS is 20 ohms and the load resistance RL is 50 k ohms, and let the input signal VS be a pulse with sample time Ts = 38 ps, as defined in the following Matlab code.    The output VL of the line is computed by the function tline (Appendix A).  Figure 2 shows the pulse input VS (top) and the output VL (middle).

```
L= 0.1;        % m length of line (10 cm = 3.94 inch) v_rel= 0.55;   %   approx relative velocity, FR-4 microstrip Z0= 75;        % ohms line characteristic impedance RS= 20;        % ohms source resistance RL= 50000;     % ohms load resistance Ts= 38E-12;    % s sample time of VS VS= [zeros(1,8) ones(1,256) zeros(1,256)];  % pulse VL= tline(VS,L,v_rel,Z0,RS,RL,Ts); n= 0:length(VL)-1; t= n*Ts*1e9;         % ns
```

The ringing of the output is due to reflected waves traveling back and forth on the line.  After the initial rising edge, the output changes each time the reflected pulse edge makes a trip from load to source and

back to load.  (Note a real-world signal would not have such sharp edges, for two reasons:  first, the input signal would have a finite bandwidth; and second, the microstrip line would have frequencydependent loss).  To reduce the reflections, we can adjust the source resistance to approximately Z0. For example, if RS = 80 ohms, we get the output shown in the bottom plot of Figure 2.  The response is improved because the matching source resistance absorbs the wave reflected from the load.  Such an arrangement is called a singly-terminated microstrip line.

We can also view an animation of the waves travelling on the microstrip line using wave\_movie (Appendix B).  Here is the Matlab code for a movie of a transmission line with step input:

```
Z0= 75;              % ohms line characteristic impedance RS= 20; RL= 50000;   % ohms source and load resistance VS= [zeros(1,24) ones(1,180)];   % step input wave_movie(VS,Z0,RS,RL);
```

Figure 1.  Microstrip transmission line example.

<!-- image -->

Figure 2.  Microstrip Transmission line signals using function tline . Top: input VS.   Middle: output VL for RS = 20 ohms.   Bottom:  output VL for RS = 80 ohms.

<!-- image -->

## A Very Brief Summary of the Wave Equation for Transmission Lines

In conventional circuit analysis, we assume signals on a wire or printed-circuit trace are functions solely of time.  But at high frequencies, signals are a function of time and position, and a length of wire or a trace becomes a transmission line.  The lossless transmission line model of Figure 3 represents a small length of line dz by a series inductor and shunt capacitor.  L and C have dimensions of inductance per length and capacitance per length; their values depend on the geometry of the line [3].  Voltage on the line obeys the one-dimensional wave equation [4]:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The solution of Equation 1 is any function of the variable t -z/v:

<!-- formula-not-decoded -->

This equation represents a wave on the transmission line, traveling at velocity v.  For example, suppose a pulse wave travels on a lossless transmission line with v = .8c, where c is the speed of light (3E8 m/s). Then, if we measure voltage versus z, the result might look something like Figure 4, where we show the relative location of V(z) at three different times:  as shown, the pulse wave travels in the positive z direction vs. time.   The full solution of Equation 1 includes a wave traveling in the negative direction:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Where V+ is a wave traveling in the positive direction, and V- is a wave traveling in the negative direction.

where

We can write this as:

Figure 3.  Lossless transmission line model.

<!-- image -->

Figure 4.  Pulse wave amplitude vs. distance and time on a lossless transmission line. top: t = 0    middle: t= 21 ns   bottom: t= 42 ns

<!-- image -->

## Characteristic Impedance and Reflection Coefficient [5]

The ratio of voltage to current for either the positive-travelling or negative-travelling wave is a constant of the transmission line called the characteristic impedance Z 0 .  For a lossless line it is given by:

<!-- formula-not-decoded -->

Although it is called an impedance, Z0 is real-valued.  If the load resistance at the end of the line is not equal to Z0, a reflected wave V- is produced, as shown in Figure 5.  The ratio V-/V+ is called the reflection coefficient, and for pure-resistive load it is given by:

<!-- formula-not-decoded -->

For RL = Z0, there is no reflection, and ρ = 0.  When RL is greater than Z0, ρ is positive.  When RL is less than Z0, ρ is negative, and the sign of V - is the inverse of the sign of V+.  For RL = 0, ρ = -1, and for RL &gt;&gt; Z0, ρ approaches + 1 .  Thus, the possible range of ρ is -1 to +1.

Figure 5.  Reflection on a transmission line with resistive load.

<!-- image -->

## Lossless Transmission Line with Sinusoidal Voltages [6]

Let a sinusoidal voltage be represented by:

<!-- formula-not-decoded -->

If we apply this signal to a lossless transmission line, we obtain a positively travelling wave (see Equation 3):

<!-- formula-not-decoded -->

Allowing for a negatively travelling wave as well, the total voltage is:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where β is called the phase constant:

<!-- formula-not-decoded -->

Phase constant β represents the phase at z relative to the phase at z = 0.  The phase at two values of z is equal when 𝛽 ∗ 𝛥𝑧 = 2𝜋𝑘 .  For k = 1, the value of Δz is called the wavelength λ.  Thus :

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Using Equation 12, we can also write:

<!-- formula-not-decoded -->

The reflection coefficient for a resistive load was given by Equation 7.  For general source or load impedances, the reflection coefficients are:

<!-- formula-not-decoded -->

Note ρ is in general complex and | ρ | &lt;=1.

We can shorten this to:

and

## A Discrete-Time Lossless Transmission Line Model

Now let's create the discrete -time model.  The model will consider only resistive source and load.  Figure 6a shows a transmission line with characteristic impedance Z0 and length L, connected between source RS and load RL.  The reflection coefficients due to the source and load terminations are shown.  A wave travelling in either direction on the line undergoes a delay over the line's length of:

<!-- formula-not-decoded -->

where v is propagation velocity.  We want to replace this delay with a discrete-time delay of M samples. Given sample time Ts, we have:

<!-- formula-not-decoded -->

We need the delay to operate on both the positive and negative travelling waves, which is achieved using the block diagram of Figure 6b.  (Here z -M represents a delay of M samples, not distance on the line!)  The real gains ρ S and ρ L account for the reflections at source and load.  The gain K takes into account the gain of the cascade of source, transmission line, and load.  Note that this block diagram models the signals at the ends of the transmission line, but not along the length of the line. We'll consider the latter case later in this article.

The z-domain transfer function of the block diagram in Figure 6b is:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The expression for K was developed using a circuit model:  see Appendix C.  We can rewrite Equation 18 using IIR filter coefficients:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where where

The time response of the transmission line is then given by the difference equation:

<!-- formula-not-decoded -->

Where x = VS and y = VL.  This simple result applies for any signal waveform, provided that source and load are resistive.  Equation 20 is implemented by the Matlab function tline (See Appendix A).  We used tline in Example 1.

For the case of general source and load impedance, the reflection coefficients are complex functions of frequency.  This case requires a more sophisticated model than the one presented here.  An expression for H(j ω ) of a lossless transmission line for general source and load impedances is derived in Appendix C (Equation C10).

Figure 6.  a)  Lossless transmission line, showing source and load reflection coefficients. b)  Lossless transmission line discrete-time model.

<!-- image -->

## Example 2.  Frequency Response of a Lossless Transmission Line

In this example, we'll compute the frequency response of the lossless transmission line shown in Figure 6a for several values of RS and RL (we won't use tline.m here).  Let the transmission line have the following properties:

```
Z0 = 75 ohms L = 1 m v_rel = 0.8  (velocity relative to the speed of light c = 3E8 m/s) v= v_rel*c
```

Rather than compute M based on Ts (Equations 16 and 17), w e'll use M = 8 samples for the model's delay and compute the resulting Ts.  Given line delay D = L/v and Ts = D/M, this value of M results in Ts of 521 ps, or fs of 1.92 GHz.  The following Matlab code computes the coefficients of Equation 19, then finds the frequency response using freqz . We'll scale the gain such that the transfer function is H(z) = VL/(VS/2), where VS/2 is the gain when RL = RS = Z0.

```
L= 1;              % m length of line v_rel= 0.8;        %  velocity relative to speed of light c= 3E8;            % m/s speed of light v= v_rel*c;        % m/s propagation velocity D= L/v;            % s delay of line M= 8;              % samples delay of line Ts= D/M;           % s sample time fs= 1/Ts           % Hz sample frequency Z0= 75;            % ohms line characteristic impedance RS= 75; RL= 75;    % ohms source and load resistance Krel= 2* Z0/(RS+ Z0) * 2*RL/(RL+ Z0);  % gain const. relative to VS/2 rho_S= (RS - Z0)/(RS + Z0);      % input reflection coeff rho_L= (RL - Z0)/(RL + Z0);      % output reflection coeff b= [zeros(1,M) 1];                   % feed forward coeffs a= [1 zeros(1,2*M-1) -rho_S*rho_L];  % feedback coeffs [h,f]= freqz(Krel*b,a,256,fs/1e6); H= 20*log10(abs(h));
```

Case I:  RS = RL = Z0 = 75 ohms.  The response is plotted in the top of Figure 7.  For this case, there are no reflections, and the response is flat with gain of 0 dB (The response of a lossy line would roll-off vs. frequency, in this and the following cases).

Case II:  RS = 150 ohms, RL = 37.5 ohms.  The response is plotted in the middle of Figure 7.  Mismatches at both source and load cause ripple of roughly 2 dB in the response.

Case III:  RS = RL = 5 ohms.  The response is plotted in the bottom of Figure 7.  For this case, the product of ρ L and ρ S is 0.766, and we see resonances at 120 MHz and its harmonics. As ρ L ρ S approaches 1, |H(z)|/K approaches the inverse of a comb filter response. We'll examine this case further in Example 3.

Figure 7.  Lossless line frequency response magnitude for Example 2, Z0 = 75 ohms.

<!-- image -->

Top: RS = RL = Z0    Middle: RS = 150 ohms, RL = 37.5 ohms.   Bottom: RS = RL = 5 ohms.

## Example 3.  Standing Waves in a Resonator

In Example 2, we found the frequency response of a 75-ohm transmission line with RS = RL = 5 ohms (See circuit diagram in Figure 8).  The response was resonant at 120 MHz and harmonics.  The longest wavelength resonance occurs when wavelength is twice the length of the line:

<!-- formula-not-decoded -->

Thus, from Equation 14, the lowest resonant frequency f0 is:

<!-- formula-not-decoded -->

In this case, f0 = (0.8*3E8)/2 = 120 MHz.

Our transmission line model of Figure 6b represents the line with M time samples.  This corresponds to a sample spacing in distance of L/M.  By summing the positive and negative traveling waves, we can plot the line voltage vs. distance and time.  The function wave\_movie (Appendix B) plots an animation of the voltage on the line, using M= 16.  Here is Matlab code to call wave\_movie for a sine at 120 MHz. Note that the code must calculate the sine's sample time T s based on L, v, and M.

```
L= 1;                    % m length of line v_rel= 0.8;              % velocity relative to speed of light M= 16;                   % samples delay of t-line v= v_rel*3E8;            % m/s propagation velocity D= L/v;                  % s delay of line Ts= D/M;                 % s sample time % sinewave fc= 120E6;               % Hz  sine freq N= 300;                  %   number of time samples n= 0:N-1;                %   time index VS= sin(2*pi*fc*n*Ts);   %   input signal Z0= 75;                  % ohms line characteristic impedance RS= 5; RL= 5;            % ohms source and load resistances wave_movie(VS,Z0,RS,RL);
```

A cumulative plot of the resulting animation is shown in Figure 9 (top).  Each curve approximates 1/2 cycle of a sinewave at a given instant in time.  Thus, wavelength is 2L, which is consistent with Equation 21.  Although V+ and V- move at velocity v, their sum along the line does not travel, producing a standing wave .  Looking at harmonics of the 120 MHz fundamental frequency:  for fc = 240 MHz, each curve approximates a full cycle of a sinewave (Figure 9, middle), and 320 MHz gives 1.5 cycles (bottom).  The amplitude of VS is 1 V peak, while the maximum amplitude of the standing waves is about 7.5 V.  For frequencies not close to multiples of 120 MHz, the amplitude is much lower, as you would expect from the frequency response of Figure 7 (bottom).  The standing waves are analogous to the waves on the plucked string of a guitar (but at much higher frequencies!)[7].  For a guitar, the fundamental and harmonics are present simultaneously on the string.

Figure 8.  Transmission line acting as a resonator.

<!-- image -->

Figure 9.  Standing waves in a resonator:  cumulative plots from wave\_movie.m Top:  fc = 120 MHz.   Middle:  fc = 240 MHz.   Bottom:  fc = 360 MHz.

<!-- image -->

## Appendix A.  Matlab Function tline.m

This function finds the discrete-time output VL of the lossless uniform transmission line of Figure A1a, given discrete-time input VS.  Terminations are resistive.  VL is computed using the model shown in Figure A1b, which includes two delays of M samples.  M is calculated as follows.  The delay of the line is:

<!-- formula-not-decoded -->

Where v is the propagation velocity.  M is then:

<!-- formula-not-decoded -->

where Ts is sample time. The model's delay is approximate due to the rounding.  The error in delay can be kept small by using a small value for Ts relative to D, resulting in a large value of M (e.g., M &gt; = 8). The z-domain transfer function of the model is:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where

Figure A1  a)  Lossless transmission line, showing source and load reflection coefficients.

<!-- image -->

- b)  Lossless transmission line model.

## Function Listing

```
%  function VL= tline(VS,L,v_rel,Z0,RS,RL,Ts); %  Lossless transmission line model with resistive terminations %  1/6/22 Neil Robertson % %  VS = input signal %  L = line length, meters %  v_rel = propagation velocity relative to speed of light %  Z0 = line characteristic impedance, ohms (real) %  RS = source resistance, ohms %  RL = load resistance, ohms %  Ts = sample time of input signal, s % %  VL = output signal % function VL= tline(VS,L,v_rel,Z0,RS,RL,Ts); c= 3E8;            % m/s speed of light v= v_rel*c;        % m/s propagation velocity D= L/v;            % s delay of line if D/Ts < .75 error('D/Ts < 0.75  Decrease Ts or increase L') end M= round(D/Ts);    % samples delay of line K= Z0/(RS+ Z0) * 2*RL/(RL+ Z0);    % gain constant rho_S= (RS - Z0)/(RS + Z0);        % input reflection coeff rho_L= (RL - Z0)/(RL + Z0);        % output reflection coeff b= [zeros(1,M) 1];          % feed forward coeffs a= [1 zeros(1,2*M-1) -rho_S*rho_L];  % feedback coeffs VL= K*filter(b,a,VS); display(['Number of samples delay M = ',num2str(M)])
```

## Appendix B.  Matlab Function wave\_movie.m

The Matlab function wave\_movie plots an animation of the voltage along the transmission line. Figure C1 shows the model implemented by the function, which is slightly modified from the model of Appendix A.  The model has a forward travelling wave register V+ and a reverse register V-.  For a delay of M, the registers have M+1 elements.  The model uses M = 16.  Each register element corresponds to a location on the line.  For a line of length L, the locations are:

<!-- formula-not-decoded -->

The V+ and V- register values are represented by the vectors:

<!-- formula-not-decoded -->

For purposes of illustration, if we let n = M, the subscripts simplify to:

<!-- formula-not-decoded -->

The line voltages are found by flipping the V+ vector and then summing each u(n) and r(n) value.

The gain constant K of equation 18 is broken into two constants as shown.  This is required to make the amplitude along the line consistent with the output amplitude.  The constants are:

<!-- formula-not-decoded -->

K1 is the gain of the voltage divider due to RS and Z0.  K2 is the transmission coefficient at the output of the transmission line.  The gain constant K = K1K2 is derived in Appendix C.

## Example Using wave\_movie

This example models a pulse on the line.

<!-- formula-not-decoded -->

Figure C1.  Transmission Line Model for wave\_movie.m Note: M = 16.

<!-- image -->

## Function Listing

```
%  function VL= wave_movie(VS,Z0,RS,RL); %  Lossless Tline model with wave movie.  Terminations are resistive. %  Line has M = 16 delay elements.  1/6/22 Neil Robertson % %  VS = input signal %  Z0 = line characteristic impedance, ohms (real) %  RS = source resistance, ohms %  RL = load resistance, ohms % %  VL = output signal % function VL= wave_movie(VS,Z0,RS,RL); N= length(VS); if N > 1024 N= 1024; warning('truncating movie to 1024 frames') end K1= Z0/(RS+ Z0);            % input gain constant K2= 2*RL/(RL+ Z0);          % output gain constant rho_S= (RS - Z0)/(RS + Z0);    % input reflection coeff rho_L= (RL - Z0)/(RL + Z0);    % output reflection coeff % H(z) coeffs M= 16;                         % samples delay of line b= K1*[zeros(1,M) 1];          % feed forward coeffs a= [1 zeros(1,2*M-1) -rho_S* rho_L];   % feedback coeffs
```

```
y= filter(b,a,VS);      % output prior to K2 VL= K2*y;               % scale by output gain constant % Compute wave on line u= zeros(1,N); S= zeros(M+1,N); u(1:N-M) = y(M+1:N);    % forward register u(n)= y(n+M) r= rho_L*y;             % reverse register r(n)= rho_L*y(n) % sum of forward and rev waves % matrix S has M+1= 17 rows and N columns for n= M+1:N-M; S(:,n)= fliplr(u(n-M:n))' + r(n-M:n)'; end z= 0:1/M:1;      %  position on line relative to length of line % animated wave plot ymax= ceil(max(S(:))); for n= M+1:N-M; pause(.01) subplot(211),plot([0 1],[0 0],'k','linewidth',5) hold on plot(z,S(:,n),'.-','markersize',9),hold off axis([-.2 1.2 -ymax ymax]),grid on xticklabels({}),ylabel('volts') text(0,-ymax/10,'0'),text(1,-ymax/10,'L') title('Voltage vs distance on T-line') % plot of output VL vs time xmax= N-2*M+1; subplot(212),plot(VL(M:n)),grid on axis([0 xmax -ymax ymax]),xlabel('samples'),ylabel('volts') title('T-line Output vs. Time') end hold off
```

## Appendix C.  Lossless Transmission Line Circuit Model

The continuous-frequency transfer function H(j ω ) for a transmission line can be found using ABCD parameters.  First, we'll review ABCD parameters, then we'll find H(j ω ) for a lossless uniform transmission line.

## Review of ABCD parameters

Figure C1.  Two-port network.

<!-- image -->

For the 2-port network of Figure C1, the ABCD parameters are defined by the following two equations:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The equations can be written in matrix form as:

<!-- formula-not-decoded -->

The circuit elements we need to analyze a transmission line and their ABCD matrices are shown in Table C1.  For ABCD matrices, the matrix of the overall system is just the product of the individual ABCD matrices.  Thus, if a system consists of a cascade of a series impedance, transmission line, and shunt admittance, the overall matrix equation is:

<!-- formula-not-decoded -->

where [Z], [T], and [Y] are ABCD matrices from Table C1.

Table C1.  ABCD Matrices for Circuit Elements [8]

<!-- image -->

| Circuit   | ABCD Matrix                                            |
|-----------|--------------------------------------------------------|
| Z         | [𝑍] = [ 1 𝑍 0 1 ]                                      |
| Y         | [𝑌] = [ 1 0 𝑌 1 ]                                      |
| L Z 0 , β | [𝑇] = [ cos (𝛽𝐿) 𝑗𝑍 0 sin (𝛽𝐿) 𝑗𝑠𝑖𝑛(𝛽𝐿)/𝑍 0 cos (𝛽𝐿) ] |

## Lossless Transmission Line H(j ω )

The transmission line to be analyzed is shown in Figure C2.  As discussed, the ABCD Matrix equation is given by Equation C3.  We'll now evaluate the equation one matrix multiplication at a time. Multiplying [Z] times [T], we have:

<!-- formula-not-decoded -->

where A, B, C, and D are the parameters of the transmission line.  Multiplying the above product by [Y], we obtain the overall ABCD matrix:

<!-- formula-not-decoded -->

For this matrix, the 1,1 term is equal to VS/VL, and therefore:

<!-- formula-not-decoded -->

Now substituting for A, B, C, and D from Table C1, and noting that ZL = 1/YL:

<!-- formula-not-decoded -->

Use Euler's sine and cosine identities and some rearranging to get:

<!-- formula-not-decoded -->

A fair amount of algebra then yields:

<!-- formula-not-decoded -->

From Equation 15, we recognize the two quotients multiplying e -j2 β L as reflection coefficients ρ S and ρ L :

<!-- formula-not-decoded -->

This result allows computing H(j ω ) for general source and load impedances, with complex ρ S and ρ L .  For real source and load,

<!-- formula-not-decoded -->

and ρ S and ρ L are real.  The exponential terms in H(j ω ) can be interpreted as follows.  From equations 12 and 16,

<!-- formula-not-decoded -->

where D is the delay of the transmission line.  Thus,

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Represents a delay of 2D.

Figure C2.  Transmission Line with source impedance ZS and load admittance YL.

<!-- image -->

## References

1.  Ludwig, Reinhold and Bogdanov, Gene, RF Circuit Design, 2 nd Ed., Pearson, 2009, section 2.8. 2. Campbell, David, Microstrip Calculator, https://www.microwaves101.com/calculators/1201-microstrip-calculator 3.  Ludwig, sections 2.2 - 2.6. 4.  Ramo, Simon; Whinnery, John; and Van Duzer, Theodore, Fields and Waves in Communication Electronics, Wiley, 1965, section 1.14. 5.  Ramo, sections 1.15 -1.16. 6.  Ramo, section 1.18. 7.  Peterson, Mark R., 'Musical Analysis and Synthesis in Matlab', College Mathematics Journal, Vol. 35, No. 5, Nov. 2004, https://amath.colorado.edu/pub/matlab/music/Petersen04CMJ.pdf 8.  Ludwig, sections 4.1 -4.2.

January, 2022

Neil Robertson