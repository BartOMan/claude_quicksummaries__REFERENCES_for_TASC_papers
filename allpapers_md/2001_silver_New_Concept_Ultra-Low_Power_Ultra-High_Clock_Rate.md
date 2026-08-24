## A New Concept for Ultra-Low Power and Ultra-High Clock Rate Circuits

Arnold H. Silver and Quentin P. Herr

Abstracf-Compared  with semiconductors, SFQ logic is very fast  and  dissipates  extremely  low  power. But  it  does  not approach the theoretical power dissipation associated with  an SFQ switching event and single gate speed in  complex circuits. For  large  circuits and  systems,  e.g.,  petaflops  computing,  we must  reduce  on-chip  dissipation,  achieve  faster  clocked  logic operation, and increase gate density.  CMOS logic dissipates the energy  required to  switch  a  transistor pair  and  dissipates  no power  between  switching  events. We  describe  a  new  SFQ circuit concept that  mimics CMOS to achieve ultra-low power dissipation  and ultra-high  clock rates. This  results  in a physically compact, self-clocked, complementary logic (SCCL), in which clock distribution is frequency-independent. The basic element in this logic family is a simple two-junction comparator. Using  TRW's  2kA/cm2 Nb  design  rules,  we  simulated  basic digital components: shift  register,  AND,  OR,  and  NOT  at  20 GHz.  We present the simulated and measured performance.

Index Term-Single flux  quantum  circuits;  Self-clocked; Voltage bias; Shift register; Superconductor  logic.

## I. INTRODUCTION

lementary superconductor digital circuits  are  extremely fast  and  limited  ultimately  by  the  Josephson  plasma frequency. They  have  very low  power  dissipation compared with high-speed semiconductor circuits.  In the 25 years that  Josephson digital circuits have been investigated, there  has  been  an  evolution  from  elementary  junctions  to SQUIDs,  and  from  ac-powered,  voltage-latching  to dcpowered, single flux quantum (SFQ) devices 111. Small SFQ circuits,  such  as  microwave  oscillators  and  asynchronous binary  ripple  counters,  do  approach  the  plasma  frequency [2,3], but larger clocked circuits fall far short of this speed in practice [4]. E

As in voltage-latching circuits, conventional SFQ gates are current  biased by individual  resistors  in series  with  the operating junctions  that  set the  current for each gate. Bias resistors dissipate at least ten times the power that is required to  switch the  gate. Furthermore, the  clock  generation and distribution required  for  complex  SFQ  circuits doubles the circuit complexity and footprint [5].  Tradeoffs exist between designed clock rate and jitter-induced error incidence [6,7,8,9]. An approach to the timing and power dissipation problems appears in  [lo], but  it  requires dual-rail data  and abandons  boolean  logic  altogether. We  present  a  new paradigm  for  high  clock  rate  SFQ  circuits  that  eliminates these  problems. Our  approach replaces current-bias series resistors with voltage-biased series  junctions.  This results in lower  power  dissipation,  more  compact  layout,  and  selfclocking at  higher  clock rates. We  call this  concept  Self-

Manuscript received September 18,2000.

Amold H. Silver was with TRW Space &amp; Technology Group.  He is now a Consultant at Rancho Palos Verdes, CA 90275, USA (telephone 310-5412650. e-mail: amold.silver@EEE.org)

Quentin  P.  Herr is with  TRW  Space &amp; Technology Group,  Redondo Beach, CA 90278, USA (telephone 3 10-814-4203. e-mail: quentin.herr@TRW.com)

Clocked Complementary  Logic, or SCCL.

Our goal is to reduce power and increase density and clock rate for high-end computing and wideband signal processing applications.  Important improvements include the following: 1 .) Eliminate  dissipation  in  the  bias  resistors,  2.)  Increase clock  rate  for  complex circuits  closer  to  the  asynchronous SFQ frequency, 3.) Simplify clock  circuitry,  increase  gate density, 4.) Reduce interaction between gates via the power bus,  improve timing  margins,  5.)  Reduce jitter-induced  bit error rate, and 6.) Reduce supply current to the chip.  SCCL improves all but the last of these areas.

In this  paper we  review  the  traditional  approach  to superconductor digital circuits, describe the evolution of the SCCL concept, present results of simulation and experiment, and suggest future implementation.

## IT. TRADITIONAL JOSEPHSON DIGITAL CIRCUITS

Superconductor logic today operates in a  constant-current mode.  Series bias resistors set the operating current for each gate.  The voltage across the resistor, IR, must be sufficiently larger than the maximum voltage across the gate to keep the gate  current  constant  and  to  provide  isolation  from  other gates  during  operation. For  latching  devices,  the  voltage across the junction is the gap voltage.  For SFQ devices, the maximum voltage is the peak of the SFQ pulse.  The average voltage across a clocked SFQ device is  Q0f, where f is the clock frequency. The voltage across R is constant, independent of clock  speed. Consequently,  the  on-chip power  dissipation is  set  by  the  maximum  design  speed  of SFQ circuits, and is at least ten times the power dissipation in the  junction itself.

Clock  and  power  distribution approximately doubles the size and complexity of RSFQ circuits.  Clock distribution is perhaps the primary design task. It  is  the  limiting factor in attainable circuit speed due to timing uncertainty arising from jitter and  fabrication  variations. Clocked  SFQ  circuits operate  an  order  of  magnitude  slower  than  expected  from intrinsic device parameters of individual gates.

## 111.  SCCL CONCEPT

SCCL  changes  circuit operation  from current-bias  to voltage-bias,  thereby  eliminating  series  bias  resistors,  and their  associated power  dissipation. Data are stored as SFQ current  in  the  inductor  of  SQUIDs;  data  are  transmitted between  gates  by current  pulses  resulting  from  the  SFQ transitions of  junctions during logic operations.

The SCCL gate is modeled after the complementary  pair of transistors in  a  CMOS  comparator. Only  one  of  the  two transistors is on at any given time, so no current flows except during switching. The output voltage is either zero or  the supply  voltage,  Vo. Power  is  dissipated  only  during  the switching  transition  to  charge  the  gate  capacitor. SAIL [ 1  1,121  (Series  Array Interferometer  Logic) copied  this feature using  series-connected, voltage-biased, damped HTS SQUIDs. SQUIDs  were  switched  between  the  damped voltage-state (&lt; 0.1 mV)  and zero-voltage  by inductive

1051-8223/01$10.00 0 2001 IEEE

Figure 1.  SCCL comparator  operation

<!-- image -->

coupling.  SAIL  was  slow  compared with  either  MVTL  or SFQ  circuits  because  of  the  large  inductance required  to provide adequate  coupling  between gates.

The behavior of a damped Josephson  junction connected to a  voltage source (as  in  a  partially  resistive  SQUID) is  well known [13]. When a current &gt;&gt; I, is  supplied, the  supply voltage is established across the small resistor and consequently across the junction.  The SQUID inductance L isolates  the  junction from  the shunt  resistance  at high frequencies,  enabling  sharp  SFQ  current  pulses.  Figure  1 contains  two  resistive  SQUIDS,  each  with  two  junctions. Each resistive  SQUIDs consist of  a junction  pair  J1,  J2  in series  with  the  inductance between the voltage rail  and  J1. The  SQUID loop  is  closed  by  the  low  resistance  voltage source not shown explicitly.  The transient response of a twojunction  resistive  SQUID  is  similar  to  that  of  the  single junction resistive SQUID.  Only the junction with the lowest eflective I,  switches and emits the SFQ pulse, while the other junction is largely undisturbed.  The effective I, depends on the circuit design and the relative currents present in J1,2 at the  time  the  switching event  occurs. Extrenal  current  is connected to the midpoint between the two junctions, and the direction  of that current  will determine  which  junction switches.

## Iv. IMPLEMENTATION AND SIMULATIONS

Figure  1  illustrates  the  basic  SCCL comparator. A  complementaty pair  of junctions, (J1  ,out, J2,out), are connected in series from a fixed (small) voltage rail to  ground. A fixed current into a very small  source  resistance  establishes the voltage  rail. The  complementary pair (Jl,in,  J2,in)  accepts  an  SFQ  datum pulse and stores  either a True (Right) or Complement (Left) current in the storage  inductor L. The  inductance L and the critical  current of the junctions are chosen  such  that only one flux quantum can be  stored  in L. True data are  stored  by  the  switching of  (J2,in); complement data are stored by switching (Jl,  in]).  In  RSFQ  parlance, the junction that transmits true data, 52, is the transmission  junction, and the one that  transmits  complement data,  J1,  is the escape  junction.

The comparator current varies periodically at 486 MHz/CIV on the  voltage rail  and  is  therefore self-clocked. Since all gates in a circuit are connected to the same superconducting voltage rail,  all  gates  are  biased  at  the  same  voltage  and hence synchronously  self-clocked at  precisely  the  same frequency.  Relative timing of adjacent gates must be defined and controlled; we impose a relative phase delay, rather than time delay, between individual gates at the connection to the voltage rails, achieving frequency-independent  timing. Circuits will function over a wide range of clock frequencies, which  can be  adjusted by  varying the  source current to the voltage  rail. Circuits can be  operated initially at  low clock rates, and then the clock can be  speeded up until  maximum frequency is achieved.

We successfully  simulated a logically complete set of gates conforming to  the  SCCL  convention: shift  register,  NOT, AND,  and  OR. All  rely  on  inherent two-phase clocking. Simulations used  shift register stages at the input and output of  each  gate. While  the  shift  register  only  shuttles  SFQ pulses through the  upper  and  lower junctions  at  the  clock frequency,  logic  gates can  move  pulses between the  upper and lower rails.

## A. Shift Register

The  SCCL  shift register  is  shown in  Fig.  2. Each  stage consists  of one escape  junction [E] in series with a complementary 2-junction transmission SQUID  [TI  and  a storage inductor, Ls. The  SQUID inductor is too  small to store a  flux quantum; LS is  large enough to  store one  flux quantum.  If the input junction  of the  SQUID switches, the output junction  switches rapidly  after  the  intrinsic  delay of the SQUID, and data is stored in the next Ls.  The next stage is clocked n : out-of-phase by  imposing Q0/2 flux bias in the inductance  of the voltage rail.

We use a transmission SQUID, similar to a JTL in RSFQ, instead of a single  junction in order to make the timing of the complementary  pair data-independent.

Figure 2 illustrates another feature of SCCL. We distinguish between the superconducting voltage rail and the superconducting current  bus that  supplies the  voltage rail. This is discussed  below under Power and Layout.

- - -

Figure 2.  Shift register.  The underlined inductors, Ls, are the storage inductors. The shaded regions denote shift register units.

<!-- image -->

Figure 3. NOT gate buffered by input and output shift register stages.  The NOT gate is the unshaded section.

<!-- image -->

## B. NOT, AND, and OR Gates

The NOT gate shown in Fig. 3 is analogous to the RSFQ XOR gate, but with one input tied to the clock.  The single Tjunction at the center emits an SFQ pulse every clock tick at Phase 2. Data from SRU1, clocked at Phase 2, provide the other  input  to  the  inverter,  which  is  clocked  at  Phase  1. Figure 4 shows  correct  operation  of  the  input  and  output junctions based on circuit level simulation.

The  two-phase  AND  gate  is  analogous  to  the  RSFQ coincidence buffer.  This simple three-junction device can be used because coincident timing is ensured by  the input shift registers.  The usual summing  junction feeds the output shift register, which is at the alternate phase relative to the inputs. The two-phase OR gate is analogous to the RSFQ confluence buffer. Again,  such a simple device can  be  used  because timing is determined in the  self-clocked shift registers.  We have  successfully simulated the operation of both the  AND and OR gates.

SCCL logic gates do not have escape junctions that permit flux  to  be  released  from  the  circuit  as  in  RSFQ. Rather, single flux quanta are simply passed up or down between the true and complement  paths.

## C. Power and Layout

The current for  a  chip will  be  supplied from only  a  few external leads and must be distributed to the entire circuit by the voltage rails.  Thus, we introduced a current bus for each voltage  rail, including  the ground  rail. Because  of  its intrinsic  inductance,  we need  to avoid  arbitrary  current flowing in  the  either  of  the  voltage rails  or  in  the  ground. Ideally, this is done with very small resistors r connecting the current bus to the voltage rail at the circuit taps to the rail (see Fig.  2). To  minimize  power  dissipation,  these  resistors should be as small as possible, preferably in the pS2 range.  In Fig.  2,  we  achieve  proper  phasing  by  supplying  alternate nodes from different current buses,  where the  difference in current is just enough to flux bias each section of the voltage rail at a0/2. Phase drop in the inductance of the current bus is  isolated from the  voltage rail,  and  hence  from  the  logic circuits by the network of small resistors that are sized for the current required at that node.

SCCL circuits can be designed and fabricated in available Nb processes.  However, to achieve an optimized netlist, one should use more layers than is common today. This would include two junction layers, five superconducting layers, and four resistor layers.  Such a process would result in improved density, margins, and integration scale.

## V. EXPERIMENTAL RESULTS

A preliminary version of the SCCL shift register has been designed and fabricated in TRW's  2 kA/cm2  Nb process, and successfully tested.  In  order  to  make  measurements at  low

I

Figure 4.  Simulation of  internally timed inverter (NOT)  gate frequencies,  it  was necessary  to use  an  external  clock. generator to  lock the clock frequency to  an external source. The circuit schematic shown in Fig. 5 consists of two parts: an 8-bit shift register proper and a clock generator.  This shift register netlist predates that shown in Fig. 2 and is sensitive to  the  data-dependent  delay  problems  mentioned  above.

<!-- image -->

Figure 5.  Single stage of the 8-stage SCCL shift register tested. A, B, C, and D are the inductances  inherent in the voltage rail.

<!-- image -->

Additional junctions  connected directly between the voltage rail and ground  impose  correct  timing. Eight  storage elements are associated with the Phase 1 clock; an additional eight are  associated with Phase  2. For  low  speed  test,  the circuit  was  biased  at V=O; clock  pulses  were  generated externally using  the  inductively-coupled clock  input. The Phase  1 clock is generated on the rising edge; Phase 2 on the falling edge.  The input and output circuits were taken from TRW's  standard  library of SFQ gates.

The data input and output waveforms are shown in Fig. 6 for a clock frequency of 50 MHz. The input (lower trace) is triggered on the rising edge of the external clock. Since the output (upper trace) is a toggle-type asynchronous SFQ-to-dc converter, output occurs at a rising or falling edge.  Vertical cursors  mark  an  input  pulse  and  the  corresponding output pulse eight clock cycles later.  This simple circuit is adequate to  demonstrate clock synchronization to  an external source, power  distribution using low-value resistors, and two-phase clocking.  The circuit layout is extendable to larger size and to logic gates.

## SUMMARY

We have described a new strategy for the design of SFQ digital  and  other circuits that  is  based  on  a  paradigm shift from current-biased  to voltage-biased  complementary  pairs of series junctions.  Table I summarizes  the inherent advantages in  SCCL compared with existing SFQ circuit  families. The only  power  dissipation  is  that  associated  with  the  actual switching events, VoIc, where IC  is the critical current of the junction.  Assuming IC = 10-4 A,  this will be approximately 2 x 10-10 W/GHz/gate, more  than 5 orders-of-magnitude lower than low power CMOS projections.

We  successfully tested  an  8-stage,  2-phase  shift  register that was externally clocked for ease of testing at low speed. SCCL is  in  its  early  formative stage,  providing substantial opportunities  for future  expansion  and improvements.

I

Figure 6. Experimental input (lower) and output (upper) waveforms for the 8-stage shiR register of Fig. 5.

<!-- image -->

Table I.

## Conventional and SCCL Approaches to SFQ Circuits

| Conventional                                                                       | Conventional   | Conventional                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Each device is current-biased                                                      | -              | Most of power is dissipated in bias resistors                                                                                                                                                                                                                                       |
| Clock generation and distribution                                                  | - - -          | complexity >> 10GHz Clock regenerated at each gate Clock distribution adds gate and layout Difficult to implement at clock frequency                                                                                                                                                |
| SCCL                                                                               | SCCL           | SCCL                                                                                                                                                                                                                                                                                |
| Each device/gate is a series pair of complementary junctions/SQUIDs- similartoCMOS | - -            | Pair powered by global rails at V=O,Vo Only one of the pair switches via SFQpulse each clock cycle Signal is + (True) or - (Complement) SFQ pulse on single data line output between the twojunctions                                                                               |
| Eliminates large series bias resistors                                             | - -            | Eliminates dominant power dissipation Reduces power to lowestpossible value: Q0ff = 0.2nW/GHz                                                                                                                                                                                       |
| Intemal self-bias voltage source                                                   | -              | Very low impedance voltage source achieved by parallelism of all gates in circuit                                                                                                                                                                                                   |
| Intemal clock generation and global distribution                                   | - - -          | Voltage bias automatically establishes global clock at Josephson frequency without extra clock generation or distribution circuitry Multi-phase clock is enabled by adjusting flux in inductance of the voltage rail between gates Relative clock phase is independent of frequency |

## REFERENCES

- K. K.  Likharev and V.  Semenov, 'RSFQ logic/memory family: a new Josephson-junction technology for sub-terahertz-clock-frequency digital systems,' ZEEE Trans.  Appl. Supercon., vol. 1, pp. 3-28, March 1991.
- W. Chen, A.  Rylyakov, V.  Patel, J.  E.  Lukens, and K.  K.  Likharev, 'Rapid  single flux quantum  T-flip-flop  operating  up  to 770 GHz,' IEEE Trans.  Appl. Supercon., vol. 9, pp. 3212-3215, June 1999. [2]
- G.  L.  Kerber,  L.  A.  Abelson,  M.  L.  Leung,  Q. P.  Herr, and  M. W. Johnson,  'A  high  density 4 kA/cm2 Nb integrated  circuit  process,' ZEEE Trans.  Appl. Supercon., this issue. [3]
- V.  Semenov, Y.  Polyakov, and A.  Ryzhikh, 'Decimation filters based on RSFQ logic/memory cells,' f i t .  Abs. ZSEC'97, pp. 344-346. [4]
- Q. P. Herr et al., ''Design and  low  speed testing of a  four-bit RSFQ multiplier-accumulator, ZEEE  Trans.  Appl.  Supercon., vol. 7, pp. 3168-3171, June 1997. [5]
- K. Gaj,  Q.  P. Herr,  M.  J.  Feldman,  'Parameter  variations and synchronization  of  RSFQ  circuits,' in  Proc.  Appl.  Supercond  Inst. Phys. Conj Bristol, U.K., 1995, Series #148, pp. 1733-1736. [6]
- K. Gaj, E. G. Friedman, and M. J. Feldman, 'Two-phase clocking for medium to large RSFQ circuits,' Ext. Abs. ZSEC'97, pp. 302-304. [7]
- A.  M.  Herr,  C.  A.  Mancini,  N.  Vukovic,  M.  F.  Bocko,  and  M.  J. Feldman,  'High-speed  operation  of  a  64-bit  circular  shift  register,' ZEEE Trans.  Appl. Supercon., vol. 8, pp. 120-124, Sept. 1998. [8]
9. Paul  Bunyk and  Peter Litskevitch, 'Case study  in  RSFQ design: fast pipelined  parallel  adder,' IEEE  Trans. Appl.  Supercon., vol. 9, pp. 3714-3720. June 1999. [6]
10. [IO] S. Polonsky, 'Delay insensitive  RSFQ circuits with zero static power dissipation,' IEEE Trans.  Appl. Supercon., vol. 9, pp. 3535-3538, June 1999.
11. [It]  S. M. Schwarzbek,  G. J. Chen, J. A. Luine, N. J.  Schneir, G. R. Fischer, R.  A.  Davidheiser,  'SAIL  high  temperature  superconductor  digital logic improvements and analysis,' ZEEE Trans.  Appl. Supercon., vol. 3, pp. 2710-2713, March 1993.
12. [I21  S.  M. Schwarzbek,  Yokoyama,  K.  E., Durand, D. J., R. A. Davidheiser,  'Operation of  SAIL HTS  digital  circuits near 1 GHz,' ZEEE Trans.  Appl. Supercon., vol. 5, pp. 3176-3178, June 1995.
13. [I31 Arnold H. Silver  and  James  E.  Zimmerman,  'Joesphson weak-link devices', Applied  Superconduclivify Vol.  I,  Chapter 1, pp. 34-36, Academic Press, Inc. 1975