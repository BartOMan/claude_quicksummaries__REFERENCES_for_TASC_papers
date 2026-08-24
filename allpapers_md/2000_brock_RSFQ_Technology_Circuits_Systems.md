## RSFQ TECHNOLOGY: CIRCUITS AND SYSTEMS

## DARREN K. BROCK

## HYPRES, Inc.

## 175 Clearbrook Road, Elmsford, NY 10523-1101, USA

Rapid  Single-Flux-Quantum  (RSFQ)  logic  is  a  superconductor  IC  technology  that,  with only a modest number of researchers worldwide, has produced some of the world's highest performance  digital  and  mixed-signal  circuits.  This  achievement  is  due,  in  part,  to  a constellation of characteristics that manifest themselves at the circuit level - namely, highspeed digital logic at low-power, ideal interconnects, quantum accuracy, scalability, and simplicity of fabrication. A necessary key to translating these advantages to the systemlevel involves understanding the I/O, synchronization, and packaging issues associated with a cryogenic technology. The objective of this paper is to review the status of current RSFQ circuit-level infrastructure components and their potential impact on system-level applications.

## 1.  Introduction

As the RF and digital domains converge 1 , entirely new strategies are needed to enable the innovative  applications  that  will  drive  tomorrow's  electronics  industry.  The  ability  to deploy  100+  GHz  mixed-signal  systems  will  usher  in  a  telecommunications  and computer revolution. Specific areas to benefit include:

The  wireless  communications  industry -  Given  the  insatiable  'thirst  for bandwidth'  in  digital  telecommunications,  future  data  converters  and  digital  signal processors  will  be  required  to  deliver  greatly  increased  performance  to  meet  the connectivity demands of governments, businesses, and consumers.

The  defense/government  market -  The  never-ending  drive  for  militaries  and governments to do 'more with less' is resulting in a concentrated push to deploy multifunction, dynamically reconfigurable systems. Such systems will rely on flexible, ultrafast, digital technologies, and replace, consolidate, and expand the capability of existing dedicated analog systems for radar, electronic warfare, and other surveillance applications.

The hyper-computer business - Demand for access to intensive computation for weather  prediction,  non-invasive  geo-physical  exploration  of  natural  resources,  global economic  modeling,  intensive  data  mining,  and  other  applications  already  exceeds  the abilities  of  modern  supercomputers  and  networks.  Ever-faster  processing  capabilities, ultra-low latency memories, and ultra-high throughput network switches will be needed.

For traditional three-terminal semiconductor transistor devices, a cutoff frequency f max approaching 1 THz is needed to achieve a throughput on the order of 100 Gb/s for small application specific ICs (ASICs). 2 Such performance requirements are beginning to reach the limits of the physical properties of semiconductors. 3,4

Further, it has been noted that the rate of innovation in semiconductor materials and devices has slowed dramatically, and that virtually no improvement in device speed is anticipated beyond the next five years. 5 Ultraexotic or 'speculative' technologies such as  quantum  computing 6 ,  DNA 7 and  molecular  computing 8 represent  a  paradigm  shift unthinkable  until,  at  the  earliest,  the  middle  of  the  century.  To  sustain  the  historical performance growth in the electronics industry, a radically new IC technology - one that is  scalable  and  addresses  the  problems  of  both  device  speed  and  interconnect  delay  must be identified and nurtured, while keeping cost in mind. RSFQ technology, based on low-temperature superconductors 9 , could be the answer.

Rapid Signal Flux Quantum (RSFQ) logic 10 is an IC technology with the potential to leapfrog the performance of traditional silicon and III-V compound semiconductors. ICs with sub-micron RSFQ static digital frequency dividers have already been fabricated and operated  in  university  laboratories  at  over  750  Gb/s. 11 These  achievements  represent faster demonstrated electronic circuit speeds than any other technology has predicted to date,  even  through  computer  simulations.  Prototype  RSFQ  circuits  made  with  modest research-grade 2-3 µm linewidth niobium (Nb) fabrication processes have demonstrated circuits such as those shown in Table 1.

Table 1: Representative RSFQ circuits demonstrated in 23 µm Nb technologies.

| Circuit Type                                   | Circuit metric(s)         | Circuit                                                         | Type Circuit                  |
|------------------------------------------------|---------------------------|-----------------------------------------------------------------|-------------------------------|
| Toggle flip-flop                               | 144 GHz                   | 2-bit counter                                                   | 120                           |
| 4-bit Shift register                           | 66 GHz                    | 1-kbit shift                                                    | register                      |
| 6-bit Flash analog-to- digital converter (ADC) | 3 ENOB a at 20 GHz        | 6-bit Transient digitizer with 6 · 32 bit on-chip memory buffer | 16 GS/s                       |
| 14-bit High-resolution ADC (2 MHz)             | 14 ENOB & -100 dBc SFDR b | 19-bit Digital-to-analog converter                              | fully functional at low speed |
| 1:8 Demultiplexor (synchronous)                | 20 Gb/s                   | 1:2 Demultiplexor (asynchronous)                                | 95 Gb/s                       |
| 1-bit Half-adder                               | 23 GHz                    | 2-bit Full-adder                                                | 13                            |
| 8 · N bit serial multiplier                    | 16 GHz                    | 14-bit digital comb                                             | filter 20                     |
| 128-bit autocorrelator                         | 16 GHz                    | Time-to-digital                                                 | converter                     |

a ENOB = effective number of bits

b SFDR =  spurious-free dynamic range

The  RSFQ  technology  also  has  a  clear  path  to  extend  performance.  Unlike semiconductor devices, the speed of RSFQ ICs comes from inherent physical

Circuit metric(s)

120 GHz

19 GHz

13 GHz

20 GHz

31 GHz

phenomena, not ultra-small scaling. This means that existing lithography techniques can be  employed,  and  more  importantly,  existing  equipment  can  fabricate  circuitry  that surpasses  conventional  limits  of  performance.  Because  RSFQ  logic  uses  the  lossless ballistic  transmission  of  digital  data  'fluxons'  near  the  speed  of  light,  the  wire-up nightmare that silicon designers face is substantially reduced. This scenario also allows the full speed potential of individual gates to be realized.

Other features of this technology that make it suitable for growth into the traditional market  include  its  compatibility  with  existing  IC  packaging  techniques.  These  include compatibility with optical (fiber) signal input and output, a maturing multi-chip module (MCM)  technology  with  multi-Gb/s  digital  data  transfer  between  chips,  and  simple interface circuits to convert to and from both ECL logic and CMOS logic levels.

RSFQ  integrated  circuits  are  made  with  standard  semiconductor  manufacturing equipment;  however,  there  are  many  fewer  mask  layers  (typically  about  10)  and  the actual processing involves much less complex depositions. 12,13 Because RSFQ logic is an all thin-film technology, there are no doping profiles to calculate, no high-temperature drive-ins, no epitaxial growths or chemical-vapor depositions. These differences translate directly into reduced costs in the large-scale manufacture of RSFQ electronics.

System-on-a-chip (SOC) architectures, containing both front-end analog circuitry, as well  as  digital  processing  blocks,  are  fundamental  to  enabling  tomorrow's  100  GHz applications.  This  configuration  presents  extraordinary  difficulties  for  semiconductors, due to 'crosstalk' - problems of interference between the analog and digital sections of the  same  chip.  Because  of  the  unique  reliance  on  single  quanta  of  magnetic  flux  to convey information, RSFQ are inherently more immune to this sort of crosstalk.

## 1.1 Development of the Rapid Single Flux Quantum IC Technology

The  existence  of  the  magnetic  flux  quantum  in  a  superconductor  circuit  was  first predicted  in  1950  by  Fritz  London. 14 In  1961,  Bascom  Deaver  and  William  Fairbank were able to experimentally prove this theory in their laboratories at Stanford University (Palo Alto, CA). 15 The postulation and subsequent discovery of an active superconductor device-the Josephson junction 16 -in 1962 quickly led to a number of efforts to exploit the speed and power advantages of a circuit made from a resistanceless (superconductive) material; however, virtually all of these ideas sought to copy the voltage-level output of the transistor, and its predecessor, the vacuum tube. 17 Called Josephson 'latching logics', perhaps,  the  most  notable  of  these  development  efforts  was  the  superconducting supercomputer program that ran from 1969-1983 at IBM (Yorktown Heights, NY). 18

Ironically,  about  the  same  time  IBM  terminated  its  Josephson  computer  project, innovative solutions were being found to design problems that had plagued the latching logic approaches. As a result, modern RSFQ logic as a digital superconductor technology differs  from  this  original  latching  junction  work  in  three  fundamental  ways:  junction material,  logic  convention,  and  packaging.  These  advances  were  a  result  of  work  in  a number of laboratories and countries and are summarized in the following sections.

3

## 1.1.1 Use of refractory metals - niobium

Nb RSFQ ICs tolerate thermal and mechanical environments well, unlike previous Pballoy Josephson circuits, which did not endure the environmental stresses of ordinary use.

By the early 1980s, it had become clear that a better material system and more r ugged Josephson IC process was needed. At the Sperry Research Center (Sudbury, MA), Harry Kroger,  Larry  Smith,  and  Don  Jillie  introduced  what  is  now  known  as  the  'trilayer process',  a  method  of  creating  reproducible  superconducting  tunnel  barriers  across  a wafer. 19 Using  this  trilayer  approach,  a  stable  Nb/Al  Josephson  junction  process  was developed at Bell Laboratories (Murray Hill, NJ) by Michael Gurvitch, John Rowell and others. 20 This Sperry/Bell Labs 'Nb/Al trilayer process' is now used universally to make Nb  RSFQ  ICs  and  other  superconductor  devices,  such  as  sensors  that  measure  the magnetic fields from the heart and brain. The next step in the development of the modern RSFQ fab process was made in Japan, where, in a Ministry of International Trade and Industry  (MITI)  funded  project,  researchers  at  Fujitsu,  Hitachi,  NEC,  and  Japan's Electrotechnical Laboratory (ETL) showed how the Nb/Al trilayers, which initially were used  in  the  US  to  make  only  small  numbers  of  junctions,  could  be  developed  into  a complete  fabrication  process  for  complex  Josephson  ICs. 21,22,23 The  junction  count  in such ICs is, in principle, limited only by the available lithography and wafer size. Since the 1980s there has also been progress, particularly at TRW (Redondo Beach, CA), and at ETL  (Japan)  in  replacing  the  Nb/Al  trilayer  process  with  one  that  uses  NbN  as  the superconductor, allowing operation at somewhat higher temperatures (~10 K); 24 however, the majority of R&amp;D in the field worldwide remains based on the Nb/Al process.

## 1.1.2 Magnetic flux quanta as binary data

RSFQ  logic  does  not  try  to  mimic  semiconductor  voltage-level  logic,  as  did  the Josephson  latching-logic  schemes  (which  incidentally  suffered  from  the  same  speed restrictions of a few GHz that today's semiconductor digital VLSI logics are encountering).

During the mid-1980s, a group of researchers at Moscow State University (Moscow, Russia), including Konstantin Likharev, Oleg Mukhanov and Vasili Semenov, invented a new  Josephson  junction  logic  family  tailor-made  to  access  the  ultimate  potential  of superconductors. This new superconductor digital logic family became known as Rapid Single  Flux  Quantum  (RSFQ)  logic. 25,26 (see  also  Ref.  10)  This  approach  relies  on another intrinsic property of superconductors (apart from the loss of resistance below a critical temperature Tc ), namely that within a closed section of superconductor material any  magnetic  flux  present  can  exist  only  in  discrete  amounts  that  are  multiples  of  the PDJQHWLFGLYPH&lt;3&gt;IOX[GLYPH&lt;3&gt;TXDQWXPGLYPH&lt;15&gt;GLYPH&lt;3&gt; 0 = h /2 e §GLYPH&lt;3&gt; GLYPH&lt;21&gt;GLYPH&lt;17&gt;GLYPH&lt;19&gt;GLYPH&lt;26&gt;GLYPH&lt;3&gt; · 10 -15 Wb, where h is Planck's constant and e is the electron charge (i.e., it is said to be quantized). 27 When a flux quantum moves in an electrical  circuit,  it  is  manifested  as  a  fast  voltage  pulse  -  an  'SFQ  pulse'  -  with  an integrated amplitude of GLYPH&lt;156&gt;9GLYPH&lt;11&gt; t ) dt GLYPH&lt;3&gt; GLYPH&lt;3&gt; 0 §GLYPH&lt;3&gt;GLYPH&lt;21&gt;GLYPH&lt;17&gt;GLYPH&lt;19&gt;GLYPH&lt;26&gt;GLYPH&lt;3&gt;P9 -ps.

Use and manipulation of single quanta of magnetic flux, in superconducting devices called 'flux shuttles', was first demonstrated in 1971 by Philip Anderson, Robert Dynes, and Ted Fulton of Bell Laboratories (Murray Hill, NJ). 28 Another such logic scheme was proposed in 1978 by John Hurrell and Arnold Silver at the Aerospace Corporation (Los Angeles, CA). 29 At the same time in Japan, a group at Tohoko University was developing what would become known as 'phase-mode logic'. 30,31 Although all are based on SFQ pulses,  none  of  these  approaches  adequately  defined  a  convenient  manner  for  coding binary data onto and extracting it from the magnetic flux quanta in the circuit. A primary contribution  of  the  RSFQ  approach  was  to  define  a  convention  for  the  logical representation  of  single  flux  quantum  '1's  and  '0's.  This  made  RSFQ  a  synchronous (clocked) logic, departing from the traditional combinatorial Boolean logic style. Since the  mid-1980s,  a  number  of  other  logic  families  utilizing  SFQ  pulses  have  been proposed 32,33,34 , including dual-rail or 'delay-insensitive' gates. Nevertheless, the RSFQ convention for performing digital and mixed-signal logic with superconductors has now become the dominant approach among researchers around the world.

## 1.1.3 Availability of closed-cycle refrigeration

RSFQ circuits also no longer have to rely solely on liquid-helium cooling, as did their previous voltage-state counterparts. Modern commercial closed-cycle cryogenic refrigerators ('cryocoolers') make packaging RSFQ chips manageable and comparably inexpensive.  Such  refrigerators  can  cool  the  niobium  superconductor  chips  to  their operating temperature of 4-5 K. Although this cooling is often accomplished with liquid helium (LHe) in research laboratories, cryocoolers are almost always the best packaging choice  for  commercial  or  military  systems.  Over  the  past  decade,  the  reliability  and efficiency of such cryocoolers has improved, while their size and cost has decreased. 35 In fact, it is now possible to purchase a cryocooler that reaches 4-5 K, and fits in the lower half of a standard 19 in. instrument rack, for about US $20,000. 36 Further improvements and cost reduction, particularly of pulse-tube refrigerators 37 , seems likely.

## 1.2 Contents of this review

This article gives a general overview of the RSFQ technology at the circuit and system level. It is intended to serve as a companion paper to 'RSFQ Technology: Physics and Devices' by Paul Bunyk, Konstantin Likharev, and Dmitry Zinoviev (also in this issue), which covers, in detail, the theoretical underpinnings, basic operation, and possible future directions  of  RSFQ  technology.  This  review  is  confined  to  work  in  low-temperature superconductor (LTS) development of RSFQ circuits in Nb/Al trilayer material systems. Recent advances in device/circuit research on RSFQ and digital gates in high-temperature superconductor  (HTS)  materials  can  be  found  in  Ref.  38.  Work  in  NbN/MgO  and NbN/AlN material systems is covered in Refs. 22 and 39 respectively. Reviews of the status  of  the  commercialization  of  superconducting  electronics  in  general  can  also  be found in the literature. 40,41,42

5

After originating at Moscow State University (Moscow, Russia), the majority of LTS RSFQ circuit work was performed, over roughly the last 10 years, at the following US institutions: HYPRES, Inc. (Elmsford, NY); Northrop Grumman (Baltimore, MD); TRW (Redondo Beach, CA); NIST (Boulder, CO); Conductus (Sunnyvale, CA); University of Rochester  (Rochester,  NY);  Stanford  University  (Palo  Alto,  CA);  UC  Berkeley (Berkeley,  CA);  MIT  Lincoln  Laboratory  (Lexington,  MA);  and  SUNY  Stony  Brook (Stony Brook, NY).

More  recently,  a  number  of  major  institutions  in  Japan  have  stepped  up  their involvement  in  the  design  and  development  of  Nb  RSFQ  circuits  and  systems.  These include: NEC Fundamental Research Laboratories (Tsukuba, Ibaraki); Hitachi Advanced Research Laboratory (Kokubunji, Tokyo); Fujitsu Laboratories Ltd. (Atsugi-shi, Kanagawa);  Tohoku  University  (Aoba-ku,  Sendai);  Nagoya  University  (Chikusa-ku, Nagoya); the University of Tokyo (Meguro-ku, Tokyo); Yokahama National University (Hodogaya-ku,  Yokahama);  the  Electrotechnical  Laboratory  (ETL)  (Ts ukuba,  Ibaraki); and the Superconductivity Research Laboratory (SRL) of the International Superconductivity Technology Center (ISTEC) (Koto-ku, Tokyo).

In  Europe,  the  focus  has  continued  to  be  more  on  HTS  materials;  however,  LTS RSFQ work is also ongoing at the Technische Universität Ilmenau, (Ilmenau, Germany), the  Physikalish-Technische  Bundesanstalt  (PTB),  (Braunschweig,  Germany),  Chalmers tekniska högskola (Goteborg, Swedsen) and (on a small level) at Ericsson Components AB (Stockholm, Sweden).

This  article  is  intended  to  outline  the  current  state  of  a  number  basic  circuit-level 'building  blocks'  and  techniques,  developed  by  the  above  groups  and  others,  which could  be  applied  towards  creating  fully-functional  RSFQ-based  systems. 43 Section  2 covers  advances  in  circuits  for  data  conversion  between  analog  and  digital  formats. Section  3  introduces  digital  signal  processing  core  components  such  as  adders  and multipliers and other infrastructure components, such as clocks and data buffers. Section 4 focuses on clock and data input/output techniques, which become especially important due  to  both  the  high-speed  and  cryogenic  nature  of  the  technology.  Finally,  section  5 examines several integrated RSFQ applications and their system-level benefits, and gives a summary of promising development areas.

## 2.  RSFQ Data Converters

The  quantum  accurate  periodic  transfer  function  of  the  Superconducting  Quantum Interference Device (SQUID) makes superconductor circuits an obvious choice for data conversion from a continuous-time to discrete-time format. 44 Likewise, when a quantized SFQ pulse is used to represent digital data, the AC Josephson effect 24 (i.e. frequency-tovoltage  relationship) 45 gives  access  to  a  method  for  directly  transferring  back  into  the analog  domain.  RSFQ  analog-to-digital  converters  (ADCs)  have  been  one  of  the  bestfunded  research  areas  in  the  field,  since  they  offer  both  high-speed  and  high-fidelity performance.  Digital-to-analog  converters  (DACs)  have  also  received  considerable

attention, since the basis for their operation is already commercially employed to define the SI ( Systeme Internationale ) unit of the Volt. 46 Several of the major efforts in these areas are discussed in the following sections.

## 2.1  Analog-to-digital converters

This  interest  in  RSFQ  ADCs  is  partly  because  of  potential  dual-use  applications  in civilian markets, such as software-defined radio, and to defense radar and EW systems. The fact that the performance of semiconductor ADCs has improved at an average rate of only  ~1.5  bits  per  6  years  is  a  further  stimulus.  The  performance  of  traditional semiconductor  ADCs  has  been  summarized  by  Robert  Walden  of  HRL  Laboratories (Malibu, CA) 47 , and is plotted in Fig. 1. The overlaid data points for two fully functional RSFQ  ADCs  on  this  plot  show  demonstrated  performance  that  is  already  comparable with the very best semiconductor devices. A number of different RSFQ ADC approaches have received attention, each design typically focussed on stressing different performance parameters. Among them are the HYPRES 'high-resolution' and 'flash' architectures, as well as Northrop*UXPPDQ¶VGLYPH&lt;3&gt; -GLYPH&lt;3&gt;FRQILJXUDWLRQGLYPH&lt;17&gt;GLYPH&lt;3&gt;

Fig.  1.  Performance  regions  for  RSFQ  ADCs  with  diamonds  indicating  demonstrated  circuits. Filled dot semiconductor data used with permission of Bob Walden and © 1999 HRL Laboratories, LLC. All Rights Reserved.

<!-- image -->

## 2.1.1 Phase-modulation/demodulation ADC

Fig.  2  shows  a  block  diagram  of  a  RSFQ  'high-resolution'  ADC  based  on  a  phasemodulation/demodulation  architecture  (a  result  of  collaboration  between  HYPRES  and SUNY). 48 The circuit consists of two major parts: a differential-code front-end quantizer and  a  digital  decimation  low-pass  filter.  The  front  end  is  composed  of  analog  phase modulator and a digital phase demodulator. The phase modulator consists of a singlejunction  SQUID,  biased  by  a  DC  voltage  from  a  special  voltage  source,  which  is

7

stabilized  by  an  internal  clock  frequency.  The  phase  demodulator  consists  of  a  timeinterleaved bank of race arbiters (SYNC) followed by a thermometer-to-binary encoder (DEC).

Fig 2. (left) Block diagram of a phase modulation/demodulation ADC. (right) Chip photo.

<!-- image -->

The  front-end  phase  quantizer 49 operates  as  follows:  a  DC  voltage  generator continuously pumps magnetic flux into the superconducting inductive loop of the singlejunction SQUID at a stabilized rate of ½ flux quantum per clock period. Inside the loop, this linearly growing flux adds to the signal flux coupled in from the input current. After the  total  magnetic  flux  in  the  superconducting  loop  reaches  a  certain  threshold,  the Josephson  junction  of  the  interferometer  switches  and  releases  a  single  quantum  of magnetic flux from the loop, (i.e., an SFQ pulse). Thus, for a constant input signal, the junction simply generates a periodic SFQ pulse train at half the clock frequency. When the input signal increases, however, the total flux within the loop grows more quickly, making the frequency of the output pulse train increase. Similarly, when the input signal decreases, the flux within the loop grows more slowly, and, hence, the frequency of the output  pulse  train  decreases.  This  mechanism,  in  fact,  produces  a  continuous  linear analog  phase  modulation  of  the  train  with  2 of  phase  corresponding  to  a  single  flux quantum worth of input signal coupled into the phase quantizer. 50

Demodulation of the phase-modulated pulse train is performed using a device called a synchronizer.  This  synchronizer  (sometimes  called  a  'race  arbiter')  is  a  specialized RSFQ shift register in which each cell stores the data pulse directed to it, releasing it only when a clock pulse arrives. Several such cells (or 'channels') are cascaded in order to eliminate  unresolved  racing  conditions;  however,  even  under  racing  conditions,  the synchronizer never drops pulses, so the DC component of the signal never drifts. A single synchronizer channel provides digitization of the phase to a resolution Least Significant Bit (LSB) value of , up to an input signal slew rate of ±1 LSB per clock period. Using a bank of N synchronizer channels, uniformly interleaved in time within one clock period, increases this phase resolution to LSB = / N and limits the input signal slew rate to ± N LSBs per clock period. In order to obtain a binary differential code from the thermometer

code  outputs  of  the  synchronizer  bank,  the  encoder  block  adds  up  these  outputs  and subtracts N /2 each clock period.

<!-- image -->

Fig. 3  (left) This oscilloscope photograph shows the operation of a 10-bit version of the highresolution  ADC.  This  chip  was  operated  up  to  900  MS/s  with  a  64:1  decimation  filter.  (right) Measurement of a 14-bit ADC performance at 175 MS/s (11.2 GHz clock frequency with 1:64 decimation ratio) using an 8K-point FFT spectrum. For 50 MHz input sinewave: ENOB = 8.9 bits, SINAD = 55.3 dB, SFDR = -74.3 dBc (12.3 SFDR bits).

<!-- image -->

The differential code from the output of the front end is passed to a digital decimation low-pass filter (DSP), which uses a standard CIC (cascaded integrator-comb) architecture [Hogenauer 51 ]  with  two  integration  stages  and  one  differentiation  stage.  The  first integration stage simply restores the signal from differential code, while the second one provides the first-order low-pass filtering.

The  dynamic  resolution  or  Effective  Number  of  Bits  (ENOB)  of  this  ADC  is determined by the input signal bandwidth (BW), the internal clock frequency f clk , and the number of synchronizer channels N and is given by

<!-- formula-not-decoded -->

The first term in this formula accounts for the slew rate limit, while the second one comes from  standard  oversampling  gain.  Here,  the  BW  is  assumed  to  be  half  the  output sampling rate (i.e. at the Nyquist limit). Therefore, (1) gives a bandwidth-to-resolution tradeoff ratio of 1.5 bits per octave. Output spectra of this ADC for both single tone and two-tone tests is shown in Figs. 3 and 4. Additional details can be found in Refs. 53, 54, and 55.

This ADC design is especially linear, because the quantization thresholds are set by a ratio  of  fundamental  constants  ( h /2 e )  in  the  SQUID  in  the  front-end.  This  leads  to  an enhanced spurious-free dynamic range (SFDR) in comparison to semiconductor ADCs, whose thresholds are set by the matching of device characteristics.

9

Fig. 4 Measured spectra on (left) ADC output for a 10 MHz tone (unfiltered). Note the input tone harmonics; (right) Two-tone ADC test with 8 MHz and 10 MHz signals (filtered). For this initial test, the ADC does not show significant 3 rd order intermodulation products.

<!-- image -->

## 2.1.2 'Flash' wideband parallel ADC

Fig. 5 shows a circuit diagram and photo of the HYPRES RSFQ flash ADC, which is optimized for high bandwidth and clock rate. The flash ADC uses a periodic comparator architecture  requiring  only N comparators  to  digitize N -bit data (unlike semiconductor flash  schemes  which  require  2 N -1  comparators).  In  the  flash  ADC  approach,  the  input signal  is  delivered  to  the  linear  array  of N comparators  via  an  R/2R  resistive  divider ladder, such that each successive comparator in the array receives half of the remaining input signal. This configuration results in a parallel N -bit Gray-code 56 output at the end of each sample interval.

Fig. 5  (left) Circuit schematic of the RSFQ quantizer of the flash ADC. (right) Flash ADC chip with 2 complete 6-bit flash converters (one in each corner). Each ADC contains 6 pairs of RSFQ quantizers, a start-stop acquisition logic block, and a 6 x 32 bit FIFO memory buffer.

<!-- image -->

The  flash  comparator  works  as  follows:  as  the  input  signal  increases,  more  flux  is coupled into the quantizer loop. The Meissner effect causes a counteracting circulating

current  to  be  induced,  which  adds  to  the  current  bias  flowing  through  the  sampling junction. When interrogated by a clock SFQ pulse, the sampling junction will redirect this  flux  quantum  to  the  output  latch,  corresponding  to  a  sampled  value  of  '1'.  In contrast,  as  the  input  signal  decreases,  less  flux  is  coupled  into  the  quantizer  loop, causing less current to add to the sampling junction bias. If a sampling SFQ pulse arrives from  the  clock  in  this  state,  the  floating  buffer  junction  connected  to  the  sampling junction will release the pulse; therefore, there will be no signal sent to the output latch. This behavior corresponds to a sample value of '0'.

The RSFQ flash comparator design employs a two-spoke SQUID wheel (i.e., a twoleaf phase tree) 57,58 containing two quantizing junctions. When the phase between these MXQFWLRQVGLYPH&lt;3&gt;LVGLYPH&lt;3&gt;DGMXVWHGGLYPH&lt;3&gt;WRGLYPH&lt;3&gt;HTXDOGLYPH&lt;3&gt; GLYPH&lt;3&gt; GLYPH&lt;11&gt;LGLYPH&lt;17&gt;HGLYPH&lt;17&gt;GLYPH&lt;3&gt; GLYPH&lt;242&gt;GLYPH&lt;3&gt; IOX[GLYPH&lt;3&gt; TXDQWXPGLYPH&lt;12&gt; , the combination acts as if it were a single  very  small  junction.  This  reduces  the  effective LI product  of  the  comparator circuit, helping to linearize its dynamic performance. A 1-pH shunt inductor in parallel with the input transformer inductance helps to further reduce the L / R time constant of the circuit. A small feedback resistor can even be used to further linearize the comparator's dynamics at high frequencies. Fig. 6 shows 'beat frequency' signal reconstructions from a 5-bit raw Gray-code RSFQ flash ADC. The onset of dynamic distortion can be seen as the input frequency increases. The bandwidth of this front end has been demonstrated in beat-frequency tests up to 30 GHz.

Fig. 6 A panel of oscillographs showing the performance of the flash ADC plotted in Fig. 1, (from left to right) 5 bits at 4 GHz, 4 bits at 12 GHz and 3 bits at 20 GHz.

<!-- image -->

The 1-cm 2 digitizer chip (shown in Fig. 5) contains two 6-bit transient digitizers. This circuit is a six-bit version of the ADC used in the beat-frequency tests; however, for each bit, an acquisition switch set and a 32-stage acquisition shift register were attached to the comparator's  clock  and  data  output  ports.  Using  this  design,  single-shot  pulses  with risetimes &lt; 100 ps were digitized (see Fig. 7). Here, the sampled data reveals structures that suggest ringing which is not visible on the sampling scope reference. The bandwidth of this ADC test chip has been shown to exceed 10 GHz (the 3 dB point is at ~16 GHz).

When  comparator  threshold  distortions  are  present,  there  is  a  marked  decrease  in ADC resolution. Architectural improvements, including redundant comparators and realtime  digital  error-correction  logic,  can  restore  much  of  this  lost  performance.  By interleaving several identical comparator thresholds, using XOR logic to combine pairs of thresholds,  then XORing  those  thresholds,  new  thresholds  for  additional  bits  of

resolution can be synthesized. 59 In addition, the MSB comparators receive the smallest fraction  of  signal  current,  resulting  in  the  widest  'gray  zone'  near  the  threshold.  By interleaving the thresholds of two comparators per bit, and using real-time RSFQ digital logic, the comparator furthest away from its gray zone can be chosen. The algorithm uses the output from the previous bit to choose the correct comparator, hence the name 'lookback'  logic. 60 Fig.  8(left)  shows  a  prototype  Flash  ADC  chip  with  these  additional features.

Fig. 7 Reconstructed sampled data from an RSFQ Flash ADC digitizer. (left) A periodic analog pulse signal captured on a sampling oscilloscope; (middle) 8 GS/s single-shot data; (right) 16 GS/s single-shot data.

<!-- image -->

Fig. 8 (left) The advanced Flash ADC architecture with interleaving and lookback logic. (right) A 'ping-pong' time-interleaved configuration for a 40 GS/s bunch profiler.

<!-- image -->

Very high frequency semiconductor ADCs often use a 'ping-pong' architecture, in which two separate ADCs work in tandem, sampling the input signal 180° out of phase in order  to  effectively  double  the  sampling  frequency.    This  approach  also  works  with

RSFQ ADCs. Fig. 8(right) shows a set of twin Flash ADCs arranged to form a 40 GS/s 'bunch  profiler'  for  application  in  high-energy  physics  experiments  for  the  US Department  of  Energy.  Although  quite  different  at  the  device  level,  this  design demonstrates the ability of RSFQ circuits to re-use existing architectures from traditional IC design. The flash ADC could also be used as a front-end component for a number of envisioned  applications,  including  transient  digitizers,  channelized  wideband  receivers, and digital beamforming receivers.

## 2.1.3 Sigma-Delta ADC

Semiconductor  ADCs  have  used  an  architecture  known GLYPH&lt;3&gt; DVGLYPH&lt;3&gt; DGLYPH&lt;3&gt; -GLYPH&lt;3&gt; PRGXODWRUGLYPH&lt;3&gt; IRUGLYPH&lt;3&gt; VRPHGLYPH&lt;3&gt; time. 61 Several  groups  are  investigating  whether  or  not  RSFQ  technology  can  also  be XVHGGLYPH&lt;3&gt;WRGLYPH&lt;3&gt;LPSOHPHQWGLYPH&lt;3&gt;WKLVGLYPH&lt;3&gt;W\SHGLYPH&lt;3&gt;RIGLYPH&lt;3&gt;$'&amp;GLYPH&lt;17&gt;GLYPH&lt;3&gt;7KHGLYPH&lt;3&gt;WUDGLWLRQDOGLYPH&lt;3&gt; -GLYPH&lt;3&gt; DSSURDFKGLYPH&lt;3&gt;XVHVGLYPH&lt;3&gt;DQGLYPH&lt;3&gt;RS -amp to add XSGLYPH&lt;3&gt; VXFFHVVLYHGLYPH&lt;3&gt; GLJLWDOGLYPH&lt;3&gt; VDPSOHVGLYPH&lt;3&gt; GLYPH&lt;11&gt;WKHGLYPH&lt;3&gt; GLYPH&lt;3&gt; RSHUDWLRQGLYPH&lt;12&gt;GLYPH&lt;3&gt; DQGGLYPH&lt;3&gt; WKHQGLYPH&lt;3&gt; subtract the generated digital ZRUGGLYPH&lt;3&gt;IURPGLYPH&lt;3&gt;WKHGLYPH&lt;3&gt;WRWDOGLYPH&lt;3&gt;LQSXWGLYPH&lt;3&gt;VLJQDOGLYPH&lt;3&gt;GLYPH&lt;11&gt;WKHGLYPH&lt;3&gt; GLYPH&lt;3&gt;RSHUDWLRQGLYPH&lt;12&gt;GLYPH&lt;17&gt;GLYPH&lt;3&gt;7KHGLYPH&lt;3&gt;PRGXODWHGGLYPH&lt;3&gt;GLJLWDOGLYPH&lt;3&gt;VLJQDOGLYPH&lt;3&gt;LVGLYPH&lt;3&gt;VHQWGLYPH&lt;3&gt;WRGLYPH&lt;3&gt; an integrator (low-pass digital filter) where the Nyquist-rate digital words are generated. Fig.  9  shows  the  circuit  photo  and  schema WLFGLYPH&lt;3&gt; RIGLYPH&lt;3&gt; DGLYPH&lt;3&gt; VLQJOHGLYPH&lt;3&gt; IOX[GLYPH&lt;3&gt; TXDQWXPGLYPH&lt;3&gt; -GLYPH&lt;3&gt; PRGXODWRUGLYPH&lt;3&gt; design from Northrop-Grumman (Baltimore, MD). 62,63,64 The modulator uses a superconductive inductor at the input to integrate the applied signal voltage and then a single junction quantizer to digitize the integrated GLYPH&lt;3&gt; FXUUHQWGLYPH&lt;17&gt;GLYPH&lt;3&gt; 7KHGLYPH&lt;3&gt; -feedback is in the form of SFQ pulses. An advantage of using SFQ pulses as this feedback is that each pulse is identically repeatable and accurate. However, the striking disadvantage is that the bulk of signal processing to make an ADC must take place in conventional electronics.

)LJGLYPH&lt;17&gt;GLYPH&lt;3&gt; GLYPH&lt;28&gt;GLYPH&lt;3&gt; GLYPH&lt;11&gt;OHIWGLYPH&lt;12&gt;GLYPH&lt;3&gt; -GLYPH&lt;3&gt;PRGXODWRUGLYPH&lt;3&gt;FLUFXLWGLYPH&lt;3&gt;SKRWRGLYPH&lt;17&gt;GLYPH&lt;3&gt;GLYPH&lt;11&gt;ULJKWGLYPH&lt;12&gt;GLYPH&lt;3&gt; -GLYPH&lt;3&gt;PRGXODWRUGLYPH&lt;3&gt;FLUFXLWGLYPH&lt;3&gt;GLDJUDPGLYPH&lt;17&gt;GLYPH&lt;3&gt;GLYPH&lt;11&gt;3KRWRGLYPH&lt;3&gt;FRXUWHV\GLYPH&lt;3&gt;-GLYPH&lt;17&gt;GLYPH&lt;3&gt; Przybysz, Northrop-Grumman.)

<!-- image -->

The circuit is clocked by sampling pulses generated by a 1.28 GHz room-temperature source and sharpened by a pulse buffer before being applied to the modulator. Each time WKHGLYPH&lt;3&gt; VXPGLYPH&lt;3&gt; RIGLYPH&lt;3&gt; WKHGLYPH&lt;3&gt; VDPSOLQJGLYPH&lt;3&gt; SXOVHGLYPH&lt;3&gt; FXUUHQWGLYPH&lt;15&gt;GLYPH&lt;3&gt; WKHGLYPH&lt;3&gt; MXQFWLRQGLYPH&lt;3&gt; ELDVGLYPH&lt;15&gt;GLYPH&lt;3&gt; DQGGLYPH&lt;3&gt; -inductor current exceed the critical current of the sampling junction, the quantizer produces an SF 4GLYPH&lt;3&gt; -feedback SXOVHGLYPH&lt;3&gt;DQGGLYPH&lt;3&gt;UHGXFHVGLYPH&lt;3&gt;WKHGLYPH&lt;3&gt;FXUUHQWGLYPH&lt;3&gt;LQGLYPH&lt;3&gt;WKHGLYPH&lt;3&gt;LQGXFWRUGLYPH&lt;3&gt;E\GLYPH&lt;3&gt; 0 / L . The Fourier transform of the output of a second-order modulator after processing shows outputs (Fig. 10) with a reduction in quantization noise at low frequencies near the signal frequency.

Fig. 10 Northrop Grumman secondRUGHUGLYPH&lt;3&gt; -GLYPH&lt;3&gt; PRGXODWRUGLYPH&lt;3&gt; GDWDGLYPH&lt;3&gt; ))7GLYPH&lt;3&gt; VKRZLQJGLYPH&lt;3&gt; VHFRQG -order noise shaping. (Photo courtesy J. Przybysz) 65

<!-- image -->

## 2.2  Digital-to-analog converters

A number of different programmable Josephson voltage standards have been proposed. 66,67 All  of  these  designs  are  essentially  digital-to-analog  converters  (DACs) based on the properties of flux quantization. The fact that an SFQ DAC uses the same fundamental physics that define the unit of the Volt has some profound consequences. For  instance,  any  instantaneous  voltage  generated  by  the  DAC  will  be  precise  to  the accuracy of the definition of the Volt. Further, every waveform cycle generated will be exactly the  same,  with  quantum  precision.  The  intrinsically  small  time  constants associated with Josephson junctions may make it possible to extend such performance to many GHz, although very large arrays of JJs may be necessary to achieve useful levels of output voltages.

## 2.2.1 Voltage-multiplier Josephson DAC

Vasili  Semenov  at  SUNY  Stony  Brook  first  suggested  an  RSFQ  DAC  design  based around a voltage multiplier (VM) block. 68 This DAC (seen in Fig. 11) uses each bit of an N -bit  RSFQ  digital  word  to  drive  an  RSFQ  digital-to-frequency  converter  (DFC) (sometimes noted as 'SD'). A DFC is designed to output a stream of SFQ pulses at a frequency that is proportional to its reference clock frequency, only when the bit value at its  input  is  '1'.  By  arranging  a  series  of N DFCs  with  reference  frequencies f N that decrease as 2 -N , one can effectively create a binary-weighted set. By switching different DFCs in and out of the series with the digital input word, any of 2 N combinations can be chosen.  The  VM  is  an  inductively-coupled  SQUID  chain  used  to  transform  the  DFC streams  of  flux  quanta  into  time-averaged  voltages,  then  sum  them,  creating  a corresponding  output  voltage  with N -bit  resolution.  This  arrangement  constitutes  a programmable  Voltage  Standard,  since  the  output  voltage  is  derived  directly  from  the input word and the Josephson frequency-to-voltage relation. By updating the N -bit input word periodically, at a rate slower than the slowest DFC reference frequency, one creates

a DAC. The voltage at the output of the DAC during a single sampling period is given by V out = M 0 f 0, where f 0 is a readout or sampling clock frequency, and M is the total number of SFQ pulses driven through the VM by all the DFCs. The LSB of the output voltage is n GLYPH&lt;215&gt;F 0 GLYPH&lt;215&gt; f 0, where n is the number of stages in the smallest stage of the VM, and f 0 is again the output sample rate. The output dynamic range is 2 N GLYPH&lt;215&gt; LSB, where N is the resolution of the DAC in bits.

Fig. 11. (left) DAC chip. (right) DAC block diagram. (Figures courtesy of V. Semenov, SUNY Stony Brook.)

<!-- image -->

Fig. 11 shows a chip photo and block diagram of the voltage multiplier DAC. Many bits of dynamic range are possible, because the initial reference clock can be very high. For instance, the chip in Fig. 11 is a 22-bit DAC. Experimental results of an 8-bit design are shown in Fig. 12. The differential non-linearity of the DAC is excellent (&lt; 0.1 LSB). With the proper microwave engineering of the VMs, a multi-GHz output rate (effective bandwidth) could be achieved, while maintaining significant dynamic range. The update clock and output clock are synchronized to prevent spikes during code transitions.

<!-- image -->

Digi t al   C ode

Fig.  12    (left)  Deviation  of  measured  quantization  levels  from  the  expected  uniform  positions. (right) Dependence of output voltage of the DAC on applied digital code. (Figures courtesy of V. Semenov, SUNY Stony Brook.)

## 2.2.2 Pulse-driven Josephson DAC

The National Institute of Standards and Technology (NIST), (Boulder, CO) has also been developing  a  Josephson  DAC  which  exploits  single  flux  quantum  pulses  to  create  a programmable or 'AC' voltage standard. 69 It is shown in Fig. 13. To operate, a desired tone (or any other periodic waveform) is first sy QWKHVL]HGGLYPH&lt;17&gt;GLYPH&lt;3&gt; $GLYPH&lt;3&gt; -GLYPH&lt;3&gt;PRGXODWRUGLYPH&lt;3&gt;DOJRULWKPGLYPH&lt;3&gt;LVGLYPH&lt;3&gt; implemented  in  a  computer  program  to  generate  a  set  of  digital  samples  of  this  given periodic waveform S ( t ), which is stored in the memory of a semiconductor digital code generator. This data, S ( i ), is used to generate an output digital pulse code, SD ( t ), in which the  density  of  ones  is  proportional  to  the  magnitude  of  the  original  given  signal. Naturally,  the  sequence  will S ( i )  contain  harmonics  of  the  desired  waveform  (i.e. quantization  noise)  which  is  characteristic  of  the  sampling  process.  By  using  a -modulation  approach,  however,  this  quantization  noise  can  be  substantially  reduced  or 'pushed out-of-band'. If the digital code generator were ideal, S D could simply be lowpass filtered and used as the analog waveform; however, real digital code generators have both amplitude and phase distortion - this is where using flux quantization helps.

It has been shown that the Josephson frequency-to-voltage relation holds for pulsedriven Josephson systems, just as for sinewave-driven systems, as long as the frequency of these pulses is below the junction plasma frequency. 70 In this case, S D is applied to a JJ array  at  a  few  GHz.  The  instantaneous  oscillation  frequency  across  the  array  is  then simply proportional to the time-averaged voltage or density of ones (i.e. density of digital code generator pulses) being driven across it. The JJ array serves to quantize the time LQWHJUDOGLYPH&lt;3&gt; RIGLYPH&lt;3&gt; WKHVHGLYPH&lt;3&gt; YROWDJHGLYPH&lt;3&gt; SXOVHVGLYPH&lt;3&gt; E\GLYPH&lt;3&gt; 0 , which cleans up many of the non-idealities in S D . The resulting output SJ can then be applied to an analog low-pass filter to recover a much higher fidelity output signal S ´( t ). Fig. 13 (right) shows the output spectrum of this DAC generating a 23.4 kHz sinewave. The second harmonic is clearly suppressed to about -75 dBc.  In  the  absence  of  noise  or  jitter,  this  should  increase  to  &lt;-100  dBc.  The  output voltage swing of the generated waveform is proportional to the number of junctions in the array. A 1000-junction array could generate waveforms a few milivolts peak-to-peak, so much larger single-chip arrays would presumably be needed for most applications.

Fig. 13 (left) Block diagram and (right) measurement results of pulse-driven Josephson DAC being developed at NIST for AC voltage standards. (Figures courtesy of S. Benz, NIST) 71

<!-- image -->

## 3.  RSFQ DSP and Infrastructure Blocks

Basic digital processing functions are performed in RSFQ as in any other logic family. For  carrying  out  the  manipulation  of  bits,  adders,  multipliers,  clocks,  registers, interconnects, and data buffers are all needed, with active Josephson transmission lines (JTLs)  to  serve  as  delays  for  time  synchronization 72 .  Other  blocks  include  parallel-toserial converters, clock generators, and phase-locking devices.  The  diversity  of components that have been (or are being) developed has brought RSFQ technology to the point  where  the  design  of  larger  systems  with  more  functionality  can  be  reasonably considered. Several key blocks for general DSP applications are covered in this section. The discussion of the applications themselves is reserved for section 5.1.

## 3.1  Digital clocks and phase-locked loops

The naturally high frequency of RSFQ circuits requires that digital clocks of equally high frequency be generated and distributed throughout the chips themselves. For 'low-speed' circuits (i.e. £ 20 GHz) it is often convenient to use an external synthesized source to create a sinewave clock trigger that can be sent to the chip via high-speed coaxial cable; however,  when  useful  systems  are  considered,  a  more  practical  method  of  clock generation is required. Further, the necessity of having very fast RSFQ circuits operate with the traditional semiconductor-based instrumentation leads to a requirement not only for an on-chip RSFQ clock, but also for it to be imbedded in a full phase-locked loop (PLL)  to  create  a  complete  useful  RSFQ  subsystem.  The  effective  implementation  of RSFQ  clock  controllers  (a  key  component  to  enabling  large-scale  RSFQ  systems)  was pioneered by Lin and Semenov (see Ref. 73).

## 3.1.1 On-chip clock sources

The  characteristics  of  several  SFQ  clock  sources  are  summarized  in  Table  1.  These include single over-biased junctions (which do not have particularly narrow linewidths due to thermal noise), JJ arrays (which require special care in ensure coherent radiation), JTL oscillator rings (which are easy to design, but offer only limited tuneability) 74 , and so-called  'long'  Josephson  junctions  (which  can  be  operated  in  either  flux-flow  or resonant modes).

Table 1. A comparison of different single flux quantum clock sources

Frequency

| Oscillator Type                | Quality Factor       |             |
|--------------------------------|----------------------|-------------|
| Single Junction                | 10 2 - 10 3          | > 100 GHz   |
| Junction array                 | 10 3 - 10 5          | > 100 GHz   |
| Long junction (flux flow mode) | 10 3                 | > 100 GHz   |
| JTL oscillator Long Junction   | ring 10 3 - 5 x 10 3 | 10 - 20 GHz |
| (resonant mode)                | 10 5 - 10 6          | 1 - 100 GHz |

High quality room-temperature clock sources at these high frequencies, which could be used to externally clock the circuits, are extremely expensive, difficult to package, and suffer  strongly  increased  timing  jitter  when  transmitted  over  long  distances.  Increased jitter would prove detrimental to the performance of any digital circuit. For these highspeed  integrated  circuits,  a  low-jitter,  on-chip  clock  technology  is  needed.  An  on-chip clock technology consists of four key building blocks: a stable, low-jitter master clock generator; a clock distribution network; a clock decimator and selector to generate and select  a  sub-harmonic  of  the  master  clock  frequency;  a  phase-locked  loop  (PLL) to synchronize the on-chip master clock with a stable external clock to provide long term phase stability.

Fig. 14 Measurements of a 56.6 GHz LJJ resonator SFQ clock pulse train digitally divided by 2 9 for display in (left) Time-domain showing a period 256(T) = 4.52 ns and (right) Frequency-domain with f /256 = 221 MHz.

<!-- image -->

<!-- image -->

An  example  of  a  high-quality  on-chip  SFQ  clock  is  shown  in  Fig.  14.  The  long Josephson  junction  (LJJ)  oscillator  in  resonant  mode  offers  a  compromise  between tunability and stability. By biasing on the N th zero-field step (ZFS) of an LJJ ( N = 7 in Fig. 14), a train of SFQ clock pulses can be generated at the resonant frequency set by the LJJ's  size,  or  alternatively,  at  any  higher  harmonic  of  this  characteristic  frequency. 75 Digital frequency dividers can also be used to access sub-harmonics of the clock pulse train.

Other approaches have also been employed to generate a SFQ clock on chip, while maintaining synchronization with room temperature electronics. One approach employed an SFQ clock coupled to a resonant length of microstrip transmission line, so that the clock  becomes  'locked'  at  the  resonant  frequencies  of  the  microstrip  line. 76 Another variation  employed  a  frequency  doubling  technique  in  which  two  SFQ  pulses  are produced  for  every  one  that  is  input,  so  that  several  cascaded  doublers  can  bring  the frequency  up  to  the  range  of  interest. 77 The  first  of  these  is  a  narrow-band  approach, suitable  for  specific  frequencies,  when  tuning  is  not  needed.  The  second  is  somewhat limited in range and lacks a feedback mechanism for long-term stabilization.

## 3.1.2 Phase-locked loops

A more traditional approach to synchronization - the PLL - is shown in Fig. 15. 78 The layout on the right is an RSFQ PLL suitable for use with any standard RSFQ circuit. The basic phase-locked loop design is that of a classical digital PLL, 79 in which the phase detector and the frequency divider are digital, but the loop filter and voltage-controlled oscillator are analog. Here, the VCO is an over-biased Josephson junction and the clock output  is  a  train  of  SFQ  pulses.  Although  certainly  not  the  highest Q resonator,  it  is nevertheless a suitable (and simple) method for this proof-of-principle design.

In  this  circuit,  the  fast  output  of  the  VCO  is  phase  locked  to  a  slower  reference generated  at  room  temperature  signal  by  first  passing  through  a  frequency  divider  (a toggle  flip-flop  counter)  and  then  being  compared  against  the  reference  signal  in  the phase detector. The phase detector is a device that compares the phases of the two SFQ pulse  trains  at  its  inputs  and  issues  an  analog  feedback  signal  proportional  to  the difference in phase between the signals. This output signal is the filtered by a loop filter (it may also be amplified or attenuated as necessary) and fed back to the VCO bias in order to minimize the phase difference between the two signals. Fig. 15 (right) shows an on-chip  phase-locked  loop  (PLL)  operating  at  50  GHz  and  locking  to  a  reference frequency  over  a  range  of  1.5  GHz  ( -1.5%).  The  pull-in  and  locking  ranges  were indistinguishable.

Fig.  15.  (left)  Layout  of  an  RSFQ  PLL  (right)  PLL  demonstration  at  50  GHz  VCO  frequency. Traces show phase matching at 12.2 MHz between reference clock and frequency divider output, and phase detector output. The two signals are out of phase by 90 degrees.

<!-- image -->

## 3.2  RAM and FIFO buffers

## 3.2.1 Random access memory

Because it is composed of a ratio of fundamental constants, the magnetic flux quantum GLYPH&lt;11&gt; 0 ), stored as a persistent current in a superconductor, is an excellent choice for a unit of data storage for large memories. The ability of such flux quanta to be both stored and transferred with virtually no power dissipation allows the development of various large-

scale  circuits  with  on-chip  memory,  connecting  them  into  deeply  pipelined  devices. While  RSFQ  logic  designs  successfully  use  these  features,  RAM  designs  have historically not fully exploited this ability.

The  most  successful  superconductor  RAM  implementation  thus  far  is  one  from NEC. 80 The design approach used in the NEC memories combine SFQ memory cells with AC-powered voltage-state Josephson periphery circuits (readout, decoder, etc.). Unfortunately, the requirement of large external AC-power limits the clock cycle to about 1 GHz, making the RAM throughput insufficient to match the much faster, DC-powered, RSFQ logic family. 81 Recently, however, new DC-powered SFQ RAM approaches have been pursued that may help this issue. 82,83

One new DCpowered Cryogenic RAM or 'CRAM' 129 consists of SFQ memory cell arrays,  dc/SFQ  decoders,  current  drivers,  sensing  gates,  and  block  multiplexor  and demultiplexors.  The  general  structure  of  the  RAM  is  shown  in  Fig. 16.  In  order  to increase throughput, a 16-Kbit RAM chip is divided into four 4-Kbit blocks. Each block comprises a row-accessible 128 x 32-bit matrix, where each row of contains one 32-bit word.  A  block  demultiplexor  distributes  input  data  between  blocks,  where  a  decoder converts address and/or data into DC currents on microstrip lines, which propagate near the speed of light, to operate on rows of SFQ memory cells. In a READ operation, a 32-bit RSFQ word appears across the block output and is funneled to the CRAM output by a block multiplexor.

Fig. 16.  (left)  Block  diagram  of  the  CRAM  combining  four  blocks  of  memory  arrays,  a  block decoder, Y-decoders, select line drivers, sense gates, and output block multiplexor; (right) Single block of the CRAM including an address decoder and drivers, a 32 x 128 memory cell array, Xdrivers, and output sense dc-to-SFQ converter.

<!-- image -->

Fig. 16  (right)  shows  a  more  detailed  schematic  of  a  single  4-Kbit  memory  block. Access to individual SFQ memory cells is provided via both magnetically coupled and

direct  microstrip  lines.  The  sign  of  the  currents  depends  on  whether READ or  WRITE operations are selected. Each WRITE1 operation is preceded by an erase or WRITE0 to reset the cell. The SFQ memory cell itself (see Fig. 17) is based on a modified version of the  NEC  vortex  transition  (VT)  memory  cell 84,85 ,  with  non-destructive  readout  and current  control.  If  the  read-out  SQUID  switches  to  the  resistive  state  during  a  READ operation, the Y-column sense read-out cell (dc-SFQ) transforms the DC-signal into an RSFQ bit.

| SFQ RAM Cell Access Table   | SFQ RAM Cell Access Table   | SFQ RAM Cell Access Table   |
|-----------------------------|-----------------------------|-----------------------------|
| O per at i ons              | Sel ect Lines               | Access                      |
| WRITE1                      | +X+Y                        | Bit                         |
| WRITE0                      | -X                          | Word                        |
| READ                        | +X                          | Word                        |

Fig. 17. An SFQ memory cell with DC-powered row-accessible selection.

<!-- image -->

## 3.2.2 FIFO memory buffers

First-In  First-Out  (FIFO)  memory  buffers  (of  the  type  used  in  section  2.1.2)  can  be created using basic shift register cells. The first RSFQ shift register was a simple chain of RS  flip-flops  successively  clocked  by  an  SFQ  pulse  on  a  Josephson  transmission  line (JTL) traveling opposite to the data stream. This simple design later extended, with an additional clock JTL, to build a reversible shift register. 86 The subsequent merging of the clock  JTL  and  data  RS  flip-flop  into  a  single  cell  resulted  in  a  junction-efficient  shift register design with only two junctions per bit, often called a '2-JJ' design shown in Fig. 18. 87 All these designs have a constraint between the delay of the clock pulse t clk and the delay of the data shift t shift to avoid racing conditions. Specifically, the clock delay t clk must be negative (i.e. the clock and data must travel in opposite directions), and must be greater than t shift : (-t clk &gt; t shift ). 88

Fig. 19 shows the measurements of 256 x 1-bit and 4 x 1-bit 2-JJ shift registers at 12.36 Gb/s  and  60  Gb/s,  respectively. 89 In  Fig.  19(left)  the  envelope  of  a  directly  triggered measurement  of  the  shifted  sequence  (1110011)  at  6.18  GHz  is  shown  in  trace  (a). Increasing the dc/SFQ clock trigger offset, the input clock frequency can be doubled. The consequence is seen in (b) where the output envelope is moved to a new position in time (by half the delay of the shift register). Specifically, ½ . (6.18 GHz) -1 . (256 bits) = 20.7 ns, corresponding to an operation at the double frequency 12.36 GHz. Trace (c) corresponds

a leap to the position when the dc/SFQ converter generates the clock pulse train. Similar measurements of a 2-JJ 32-bit shift register yielded proper operation at a 31.8 GHz clock frequency.

Fig. 18 The most common '2-JJ' RSFQ shift register design, which features reversible operation as well as a minimum number of junctions per cell. Clock distribution junctions are on the top of the circuit, while data storage registers lie across the bottom.

<!-- image -->

Fig. 19 Shift register measurements. (left) Triggered clock test of a 256-bit SR with a data pattern of (11100111) at 885 MHz for clock frequencies of: (a) 6.18 GHz  (b) 12.36 GHz and (c) &gt;2.4 mA (clock  pulse  train  generation).  (right)  Non-triggered  clock  test  of  a  4-bit  SR  showing  correct operation  to  ~124  µV  (~60  GHz).  Vertical  scale  9.7  GHz/div.  (frequency  =  &lt;voltage&gt;/( h /2 e )). Horiz. scale 50 m A/div.

<!-- image -->

In an un-triggered high-frequency test, a ~1-200 Hz triangle wave (sweep) current is applied to the input of a dc/SFQ converter (the generator of the clock pulse train), and the time-averaged DC voltages on both the clock JTL and the output of the shift register are measured,  with  the  data  signal  frequency  adjusted  in  order  to  observe  a  few  data envelopes in each sweep period. Fig. 19 (right) shows the high frequency un-triggered measurement  of  a  4-bit  buffered  shift  register  using  this  method.  When  operating correctly,  the  digital  SR  output  voltage  is  the  same  as  the  voltage  on  the  clock  JTL whenever the data value is a '1'. The digital SR output voltage is zero when the data value is '0'. In this measurement, beyond ~124 µV (or ~60 GHz according the Josephson

voltage-to-frequency  relation),  the  output  no  longer  follows  the  clock.  This  sets  the maximum  operational  frequency.  Even  these  speeds  are  still  lower  than  the  simulated maximum  frequency  75  GHz.  This  is  due  to:  the  maximum  frequency  of  the  input dc/SFQ  converter  (~65  GHz);  underbiasing  of  the  shift  register  due  to  the  small parameter margins of some cells; and the resonances in the DC bias lines.

## 3.3  Adders and multipliers

In general, the throughput of a computational process can be increased at the expense of latency  by  using  a  pipelined  architecture.  Such  pipelining  normally  requires  additional registers,  which  in  a  semiconductor  technology  can  more  than  double  the  size  of  the circuit. In RSFQ logic, however, register storage is built into the gate itself. This inherent memory state (i.e., storage of single flux quanta) makes it possible to build a basic set of useful  cells  from  Toggle  and  Reset-Set  (T  and  RS)  flip-flops  and  their  modifications. Such modifications can include adding destructive and non-destructive readouts (DROs and NDROs), as well as fanin buffers (often called 'confluence buffers' or 'mergers'), and fan-out cells (typically called 'splitters'). Using this technique, basic cells have been developed  to  execute  many  common  digital  signal  processing  (DSP)  elementary operations, including Addition, Accumulation, and Multiplication. Details of the design and  experimental  evaluation  of  such  cells  have  been  extensively  described  in  the literature 10 , therefore only a few examples will be given here. An excellent self-contained full 'design example', can also be found in Ref. 90; providing a detailed discussion of the cell timing and clock distribution, simulation and verification, and even yield and bit error-rate estimation for an RSFQ pipelined parallel adder design.

## 3.3.1 Basic DSP gates

Since  all  these  cells  have  an  internal  memory,  they  provide  their  own  registers  to synchronize and effectively pipeline their inputs and/or outputs. For a basic latching data register, an RS flip-flop or destructive read-out (DRO) call as in Fig. 20 can be used. Combining a T flip-flop with a DRO and confluence buffer performs the function of half or full addition (FA-cell). 91 As another example, a D flip-flop with non-destructive readout  (NDRO  or  NR-cell)  and  confluence  buffer  can  be  used  to  realize  the  function  of accumulation as shown in Fig. 21. 92,93

Fig. 20 (left) Circuit and (right) block diagrams for a D flip-flop used as a destructive readout cell.

<!-- image -->

To  take  advantage  of  the  speed  (and  hence  throughput)  of  RSFQ,  serial  math approaches have been explored. For implementation of serial addition, an entire carrysave serial adder (CSSA-cell), as seen in Fig. 22, has even been designed. This cell is an excellent demonstration the capabilities of a 'non-Boolean' design approach to RSFQ. 94

<!-- image -->

Fig. 21 (left) Circuit and (right) logical diagrams for a non-destructive read-out cell.

<!-- image -->

Carry-Save  Seri al   Adder   ( C SSA)

Fig. 22 (right) Circuit and (right) logical diagrams for the CSSA.

The  implementation  of  these  gates  is  detailed  in  section  3.3.3.  Another  set  of  basic RSFQ  cells  has  also  been  successfully  developed  and  reported  on. 95 Furthermore,  a traditional approach of composing DSP elementary functions using RSFQ Boolean cells and flip-flops has been described as well. 96

## 3.3.2. The B-flip flop

Success in the design and demonstration of RSFQ functional blocks, such as those in section 3.3.1, was accompanied by development of a 'universal' RSFQ cell. The idea of the 'bi' flip-flop or B-flip flop (shown in Fig. 23) was to take advantage of the inherent memory capability of RSFQ logic to form a template cell, from which a number of useful functions could be derived simply by connecting different cell inputs and/or outputs, with shorting or opening of different branches. 97 The B flip-flop has 4 inputs and 6 outputs

altogether.  Input  SFQ  pulses  can  change  the  internal  state  ('1'  or  '0')  of  the  cell  by introducing  a  flux  quantum  into  the  center,  shared  interferometer.  This  internal  state, along  with  additional  input  pulses,  can  then  define  logical  outputs  with  reference  to different  points  in  the  cell.  Major  modes  include  RS 2 ,  T 2 and  T·RS  configurations, 98 which utilize an input toggle of the memory state, a persistent set-until-reset state, or a combination of both. Possible logical operations include NDRO-cell, toggle flip-flop with synchronous destructive readout (T1-cell), full-adder, or even an asynchronous (reversible)  up-down  counter.  This  template  also  serves  as  the  basis  for  the  gates described in section 4.1.

Fig 23. An approach to a template RSFQ gate, the bi (B) flip-flop, here configured in RS 2 mode. Logical expressions at the outputs indicate the dependence on the inputs.

<!-- image -->

## 3.3.3 Serial vs. parallel architectures

As previously mentioned, the high speed and naturally pipelined architecture of RSFQ logic  makes  it  possible  to  consider  both  parallel  and  serial  approaches  to  computeintensive functions. Specifically, multi-rate processing, in the form of serial math, is one method to take advantage of the very high clock speeds available, while minimizing the total number of devices needed for a given task.

The most common DSP functional primitive is X = WY + Z .  In order to perform this function, both multipliers and adders are required. Fig. 24 shows single-bit modules for both serial and parallel implementations of multipliers. These modules can be designed using  the  basic  set  of  RSFQ  cells  described  above;  then  interconnected  with  JTLs  to provide SFQ pulse transmission and to set the necessary delays within and among them. For  example,  a  serial  multiplier  module  which  dissipates  only  13  µW  has  been constructed using 48 Josephson junctions (JJs). 99 The parallel multiplier module (PMM), also shown in Fig. 24, employs a total of 67 JJs and dissipates only 19 µW of power experimentally at 15 GHz. 100

Fig. 24  Block diagrams of  (left) an RSFQ serial multiplier and (right) single bit slice of an RSFQ parallel multiplier.

<!-- image -->

The serial-multiplier in Fig. 24 uses three elementary RSFQ DSP cells: destructive readout  registers  (DROs  or  DRs),  NDROs  or  NR  cells,  and  carry  save  serial-adders (CSSAs). After clearing the internal carry bits of the CSSA, N -bit operand B is loaded (either  serially  or  in  parallel)  into  the  top N -bit  DROs  where  it  will  be  held  for  the multiplication cycle. If successive multiplies by the same coefficient value are required, operand B need only be loaded once. An N -bit operand A is then shifted into the DR register from the right, LSB first. After the first clock, the LSB of the result product is available at the sum output of the rightmost CSSA. Operand A is shifted N times and then padded with zeros and shifted N more times to produce a 2 N -bit product shift out to the right  from  the  rightmost  CSSA.  At  the  end  of  each  clock  period,  the  serial-multiplier delivers each consecutive bit of the 2 N -bit product ( A x B ) at the output terminal. The partial single-bit multiplications are performed by the AND cells, while the CSSAs sum up  the  partial  products.  The  whole  multiplication  takes  2 N clock  periods;  however, loading of the next B operand can take place during the last N periods of the previous multiplication  cycle.  This  is  a  highly  efficient  method  of  multiplication  and  forms  the basis of the FFT processor described in section 5.1.7.

Built-in self-test (BIST) circuitry is necessary to perform the GHz rate digital testing necessary for this cell. The placement of FIFO memory buffers at the input and output of the cell under test (CUT) provides a method of loading in a test vector at low-frequency, then  switching  to  a  high-speed  signal,  which  clocks  the  CUT  and  stores  the  output  in another on-chip buffer, where it is again available for low-frequency readout. Such highspeed tests are shown in Fig. 25. 101

Fig. 25.  (left) High-speed operation of an 8-bit serial multiplier with shift register test system at 6.3 GHz and 33 MHz load/off-load clock. Inputs: W ={11111111}, Y ={11000000}; output YW ={1011111101000000};  (right)  Correct  operation  ( WX + Y + Z )  of  a  parallel  multiplier module  with  shift-register  test  system  at  5.3  GHz  (load/off-load  clock  is  2.5  MHz)  for W = X =(0000101), Y =(0110101), and Z =(1010001). The outputs for both are in NRZ format.

<!-- image -->

A consequence of the high speed of RSFQ logic is that additions and multiplications can  be  implemented  as  either  parallel  or  serial  operations,  without  much  reduction  in performance.  If  both  operations  are  bit-wise  pipelined  (i.e.  no  carry  propagation)  then circuit complexity can be directly traded for execution time. For example, as previously mentioned, an N -bit x M -bit multiplication requires N x M addition operations; however, these  can  be  accomplished  as  either M additions  over N clock  cycles,  or  by N x M additions  in  only  one  clock  cycle.  The  parallel  implementation  of  a  16-bit  multiplyaccumulator requires 288 full adders; however, a serial implementation requires only 33 Carry Save Adders (CSA). With an internal clock rate of 32 GHz, it would perform the operations at a throughput of 1 GHz. An intermediate trade-off could also be designed, such as using 64 adders over 4 clock periods. This tradeoff example give a good feel for the design flexibility enabled by the high-speed bit rates possible in RSFQ.

## 4.  RSFQ Chip I/O Approaches

An extra level of complexity exists at the interface between RSFQ circuits and offthe-shelf components. This is due to the high aggregate data rates involved, the cryogenic nature of the technology, and the low-level signals of RSFQ. One method for bringing data  onto  or  taking  data  off  an  RSFQ  chip  is  to  perform  time-division  multiplexing  / demultiplexing.  Su ch  'muxing  /  demuxing'  of  data  can  be  done  synchronously  or asynchronously, depending on whether clock recovery is required between data source and destination. The low-level superconductor digital signals can be somewhat amplified to a point where custom semiconductor digital amplifiers can provide output at standard emitter-coupled logic (ECL) levels. Further, direct high-speed data I/O may be possible using on-chip electro-optic techniques. In many cases, partitioning of an RSFQ system may involve the use of a superconductor multi-chip module, which can allow direct data transmission between chips at tens of Gb/s. Ultimately, it is the cryopackage containing

the RSFQ chip or MCM that actually interfaces with the cooling apparatus and I/O path which sets the final cooling requirement. 102

## 4.1  Multiplexors and demultiplexors

The B flip-flop with joined inputs (or T 2 flip-flop), as described in section 3.3.2, can be used as an RSFQ dual-rail (asynchronous) demultiplexor. The circuit in Fig. 26 (left) has two input lines - one for input zeros 'In 0' and one for input ones 'In 1'.  The ones are applied to the input of one internal T flip-flop and the zeros are applied to the input of the other internal T flip-flop. In this configuration, the direct and inverted outputs of each T flip-flop form the dual-rail (asynchronous) demultiplexed output 'Out A and B'.

<!-- image -->

In '1'

Fig. 26  (left) The schematic of a T 2 -mode B flip-flop configured as a dual-rail 1:2 demultiplexor and; (right) schematic of an asynchronous multiplexor cell of similar design.

<!-- image -->

Fig. 27 (left) Functional test of the T 2 demultiplexor cell showing correct operation. All outputs are NRZ data. (right)  High-speed test results of the T 2  demultiplexor cell. (Horiz. axis units - mA; Vert. axis units - mV.)  One trace is the time-averaged voltage i nput to 'In 0'. The other is a tr ace of twice the time-averaged voltage on 'OutA 0'. Correct operation is seen to the point where the two traces diverge. I nput test pattern is (00011011) which is correctly shuffled between OutA and OutB up to 95 Gb/s.

In  order  to  determine  the  maximum  working  speed  of  this  demultiplexor,  a  timeaveraged DC IV characteristic is measured. Scanning a current on the input 'In 0', the

dc  voltage  response  on  the  'In 0'  and  'OutA 0'  terminals  can  be  monitored.  Fig. 27 (right)  shows  the  I-V  curve  from  this  experiment.  For  convenience,  the  voltage  on 'OutA 0'  terminal  was  multiplied  by  two.  As  seen,  the  traces  coincide  up  to  1.9 mV, which  means  the  maximum  working  frequency  is  95 Gb/s,  according  to  the  Josephson frequency-to-voltage relation. Of course, this is not a complete test for such circuit, but it does give a good estimation of the limit of performance the demultiplexor.

A schematic of an asynchronous dual-rail 2:1 multiplexor is shown in Fig. 26 (right). This cell is also based on the B flip-flop, with output terminals serving as inputs and vice versa.  The  input  inductances  serve  as  buffers  for  incoming  data.  In  the  initial  state, junctions J1 and J8 are not biased, causing data arriving to input B to be stored in the L2 or L4 buffer and to wait for data arrival on input A. Meanwhile, junctions J4 and J12 are biased, which allows data (either '0' or '1') arriving to the input A to pass through the inductor L3 (or L5 ). The multiplexor internal state toggles with a delay provided by shunt resistor R, allowing the data captured in input buffers to be released. The multiplexor alternates  between  the  two  incoming  data  streams,  doubling  the  output  data  rate.  If desired, these multiplexor cells can be connected to a tree comprising a 2 N :1 multiplexor with  no  data  transfer  rate  reduction.  This  scheme  also  enables  parallel-to-serial conversion of dual-rail data at an extremely high frequencies. Simulations predict good operation up to data rates of 60 Gb/s.

Fig. 28 1:8 RSFQ demux operating at 20 Gb/s.

<!-- image -->

For  synchronous  operation,  another  shift-and-dump  (serial-to-parallel  converter) architecture can be use for demultiplexing. Fig. 28 shows a fabricated 1:8 demux circuit of this type. For eight clock cycles, a serial bit is loaded into the demux cell; the ninth clock  dumps  these  bits  onto  eight  separate  output  lines,  clears  the  internal  demux registers,  and  begins  a  repeat  of  the  process.  The  8:1  decimated  clock  is  also  made available at the output in order to synchronize the data flow between cryogenic and room temperature circuits. Fig. 28 (right) shows a BIST test (as described in section 3.3.3) for a serial data stream (bottom trace) that is sent to the demux cell at 20 Gb/s and correctly shuffled between eight parallel output lines (topmost traces), reducing the aggregate data rate to 2.5 Gb/s per channel.

## 4.2  Digital output drivers

For electrical connection outside RSFQ chips, the digital data, in the form of SFQ pulses, must be translated into voltage swings suitable for processing by standard semiconductor circuits. The SFQ/dc converter cell 10 is one way of starting this process; however, this method only provides a ~250 µV NRZ voltage swing for each true bit at the chip pad. Socalled 'high-voltage driver' (HVD) blocks (similar to the type shown in Fig. 30) have therefore been developed to convert RSFQ data/clock signals into ~2.5 mV NRZ voltage swings at the chip pad. 103,104,105

Fig. 29.  (left) Output of 2.5 kA/cm 2 asynchronous voltage driver circuit for 1 Gb/s, 4 Gb/s and 8 Gb/s  input  patterns  and  (right)  output  eye  diagram  of  (a)  1  kA/cm 2 and  (b)  2.5  kA/cm 2 driver circuits for 4 Gb/s PRBS input. (Photos courtesy of Conductus, Inc.)

<!-- image -->

A HVD output driver fabricated with critical current densities of Jc = 2.5 kA/cm 2 can operate well up to 8 Gb/s, with rise and fall times of about 100 ps. The outputs of the high-voltage driver circuit for input pulse patterns at 1 Gb/s, 4 Gb/s and 8 Gb/s are shown in  Fig. 29.  Note  that  the  2.2  mV  output  amplitude  at  8  Gb/s  is  less  than  the  3  mV amplitude measured at 1 Gb/s. A large part of the decreased output amplitude at higher frequencies is due to increasing loss in the measurement probe. The output eye diagrams for  a  4 Gb/s  pseudo-random  binary  sequence  (PRBS)  pattern  input  are  also  shown  in Fig. 29. Here, the performance of the circuit is gauged by the size of the eye opening, which improves with larger SNR, smaller phase noise, and smaller rise and fall times. The  eye  opening  represents  the  region,  in  voltage  and  time,  of  error-free  operation. Clearly, the 2.5 kA/cm 2 circuit has a larger eye opening, primarily due to faster rise and fall times, which are about 50% of those for the 1 kA/cm 2 circuit.

Fig. 30 Mask layout of an RSFQ High voltage Driver (HVD) for amplifying NRZ output voltage swings for measurement off-chip. SFQ pulses are amplified by the input JTL on the right and used to trigger a voltage across the SQUID stack in the center for output across the resistor at the left.

<!-- image -->

## 4.3  Electrical and optical signal conversion

Although RSFQ circuits are capable of internal operation at tens of GHz their application is limited by the output drive capability. For data communication applications that require high-speed outputs such as switches and transmitters, the usable bandwidth of an RSFQ circuit is limited by the output interface. The RSFQ signal must be amplified on chip at low  temperature  to  a  large  enough  level  to  be  sensed  by  a  low-noise,  wideband, semiconductor amplifiers with a low error rate. Once amplified, the signal can be used, for example, to drive a laser diode or optical modulator for fiber-optic communication links. Approaches under investigation are introduced in the following sections.

## 4.3.1 Conversion between RSFQ and Emitter-coupled logic (ECL) signals

In  order  to  be  compatible  with  standard  off-the-shelf  data  acquisition  systems,  most RSFQ output interfaces rely on conversion to ECL representation of ones and zeros. 106,107 Fig. 31 (left) shows SFQ-to-ECL interface boards capable of handing up to 16 channels of superconductor data at rates up to 1 GS/s. (see Fig. 32)

Fig. 31 (left) ECL interface in a VME cage consists of one clock board and four 4-channel data receiver boards; (right) On-site interface of a RSFQ ADC and a semic onductor DRFM in a VME cage.

<!-- image -->

<!-- image -->

The design consists of amplifiers, followed by a discriminator circuit and level shifters (DC restore) to provide standard ECL data waveforms. Whereas previous boards utilized differential outputs, the 1 GS/s modules operate with single-ended clock and data signals

from the chip. Boards have been fabricated / operated in both VME and VXI standards to allow compatibility with various existing high-performance electronics systems such as the DRFM in Fig. 31 (right).

Fig. 32 Output-board amplifier test showing a pseudo-random bit sequence of 3 mV data at 1 Gb/s to simulate the output signals from an RSFQ chip (left) and the eye-diagram of the 1 V amplified digital stream ready for interface to room-temperature electronics (right).

<!-- image -->

## 4.3.2 Conversion between optical signals and RSFQ

Interfacing to low-temperature RSFQ devices presents a number of challenges, because the  traditional  method  of  connecting  to  high-frequency  (multi-GHz)  devices  (co-axial cables) introduces a significant heat load into the system. The large physical size of such cables may also limit the total number that may be fit into a given location. If the co-axial cable is more than a few meters long, substantial attenuation due to skin effect losses at higher frequencies may become a problem as well. In comparison, optical fibers have low thermal conductivity, are immune to electromagnetic interference (EMI), are physically smaller and lighter than standard cable, and are not subject to cross talk through ground loops. For these reasons, several groups have been investigating techniques of adapting optical fiber technology to connect both the input and output signals to/from superconductor and RSFQ circuits. 108,109

Optical-to-Electrical Conversion - The coupling of optical signals (either analog or digital) into electrical stimulus for a RSFQ circuit can be accomplished using either PIN diodes or MSM diodes. MSM diodes are easily fabricated in a standard  Nb superconductor IC fabrication process, since Si substrates are typically used a mechanical supports  for  the  thin-film  Josephson  circuits.  Alternatively,  PIN  diodes  (made  from InGaAs or GaAs) can be used either in bare chip form, or completely packaged with fiber optic connectors. InGaAs photodiodes have been operated at up to 4 GHz at 4.2 K and Si MSM  diodes  have  been  run  up  to  6  GHz  at  these  temperatures.  Beneficially,  the performance of these devices increases as the operating temperature is reduced. In either case, care must be taken in affecting the transition from the optical device to co-planar

waveguide in order to make the electrical connection to the RSFQ circuit. In the case of off-the-shelf photodiodes, their packaging capacitance will limit the overall speed to the system.

Fig. 33 (left) Schematic of a typical optically-coupled RSFQ system. (Photo courtesy Conductus, Inc.)  (right) Low-speed RSFQ shift register (of the type described in section 3.2.2) operating with both fiber optic input and fiber optic output. An integrated MSM diode is used at the input (E/O) and a laser diode is modulated by the circuit's amplified voltage output (O/E).

<!-- image -->

Electrical-to-Optical Conversion - To optically couple the RSFQ output signal from the  cryogenic  environment  to  room  temperature,  several  methods  have  been  studied. These  include:  the  use  of  electro-optic  crystals  (such  as  Lithium  Niobate  or  Lithium Tantalate) 110,111 to phase modulate an incoming light beam, Mach-Zender modulators, or the direct modulation of laser diodes or light emitting diodes. Laser diodes are generally preferred to light emitting diodes on the basis of their electrical-optical slope efficiency; however, off-the-shelf laser diodes often show signs of carrier freeze-out when cooled to temperatures near 5 K.

## 4.3  Multi-chip modules and cryopackages

Whereas  many  semiconductor  chips  are  bonded  into  individual  packages  suitable  for placement on a PCB, RSFQ systems can be thought of as being interconnected with each other on a superconducting multi-chip module that resides in a 'cryopackage'. It is this cryopackage that a system-user mounts on a small refrigerator in order to apply cooling and power, and make all I/O connections.

## 4.3.1  Multi-chip modules

Building on work done in the late 1970's at IBM 112 , the idea of a superconducting multichip module (MCM) was revived in the 1980's in Japan 113,114,115 , and independently at TRW 116,117 in the 1990's. Today, these processes have matured and are being refined to yield  even  smaller  inductances  in  the  contacts. 118,119 In  fact,  the  bandwidth  of  25-mm bump bonds is expected to exceed 100 GHz. Different substrate-conductor combinations have also been explored including Nb-on-Si, Cu-on-Si, and Cu-on-Ceramic, but Nb-on-Si remains most popular because of the ability to fabricate the MCM 'carriers' in the same process  as  the  Nb  chips  themselves.  The  Cu-on-Si  and  Cu-on-Ceramic,  while  offering low resistance at 5 K, are not superconductive.

Due of the data speeds involved, it is impractical to consider transferring bits between RSFQ  chips  via  co-axial  cables  in  different  parts  of  the  same  system.  Instead,  a superconductor  (Nb-on-Si)  MCM  can  be  thought  of  as  a  dual  of  the  PCB  for semiconductor ICs; however, the superconductor MCM maintains the lossless, dispersionless transmission of the data between chips. Further, the Nb-on-Si arrangement offers the ability of creating active circuitry in the MCM itself. This approach allows the distribution of global clocks throughout the system, such as the LJJ oscillator and PLL in section  3.1,  and  enables  the  possibility  of  both  synchronous  and  asynchronous  system operation.

Fig. 34 shows the low-temperature solder-bump technique for attaching RSFQ chips onto MCM carriers. Typical bumps are 100 µm round pads comprising  ~35 nm of Ti and an adhesion/barrier layer, 400 nm of Pd as the solder-contact layer, and 50 nm of Au to prevent oxidation of the Pd. The solder is InSn, which reflows at 118°C. After reflow, the bumps  collapse  to  a  height  of  about  5  µm,  yielding  an  inductance  of  ~10  pH  for  the contact. Fig. 35 shows the appearance of a full MCM (left) with two chips on a large carrier and close-up of arrays of test bumps (right).

Fig. 34. MCM bump-bonding / solder re-flow process of TRW for superconductor ICs.

<!-- image -->

Fig. 35. (left) Flip-chip die attach type superconductor MCM with 2 chips on a carrier.  (Photo courtesy J. Spargo, TRW) (right) InSn solder bumps scanning electron micrograph. (Photo courtesy A. Smith, TRW)

<!-- image -->

Essential for an effective design of chip-to-chip transmitter and receiver circuits is an accurate understanding of the intervening electrical pathway. Propagation of signals onchip  is  well  characterized  up  to  the  off-chip  transition.  Along  the  surface  of  a superconductor  chip,  signals  follow  a  nearly  transverse  electromagnetic  (TEM)  mode along  microstrip  wiring.  Currents  along  the  wiring  structures  are  mirrored  by  return currents  confined  below  the  wiring.  Dispersion  is  low,  even  to  hundreds  of  GHz.  In contrast,  the  transition  off-chip  requires  separate,  widely  separated  connections  for signals  and  ground  returns.  Parasitic  reactances  in  the  transition  greatly  affect  the dispersion of transiting signals.  Effective bandwidths of the transitions typically range up to tens of GHz.  One method of reducing the connection parasitics is to keep the physical distances  of  the  non-microstrip  pathways  to  an  absolute  minimum.  The  flip-chip  die attach geometry excels over wire-bonding and other die attach schemes in this regard.

Although  most  superconductor  MCM  digital  signal  transfer  schemes  involve  the boosting of the RSFQ signal before transmission and then recovering the SFQ pulse at the receiver, experiments have shown the direct transfer of SFQ pulses between chips on a MCM using very low-inductance bumps. 120

## 4.3.2  Cryopackages

Whether using a single-chip or MCM configuration, the RSFQ circuitry must be mounted in a cryopackage before mounting it on the cooling surface. In the last 10 years, much has been learned about this art. 121,122 For reliable operation, RSFQ circuits require ambient magnetic fields of less than ~1 mG at the surface of the chip. Typically, cryopackages employ  doublewalled  'high-µ  metal'  shields  to  provide  this  screening,  along  with  a vacuum-insulated heat radiation shield. This configuration can result in a system that will reject  external  magnetic  fields  up  to  ~10  G  and  provide  good  thermal  isolation  from higher temperatures. Since the operation of RSFQ logic itself depends magnetic fields, it is  possible  that,  as  the  chip  is  cooled  below  the  superconducting  critical  temperature, stray  magnetic  flux  quanta  could  become  trapped  (i.e.  Abrikosov  vortices 24 )  within  a closed superconducting region in the chip ground plane. A package 'defluxing' heater provides a means of getting rid of any trapped flux by raising the temperature of the chip above Tc for a short time. Ideally, a self-check procedure should monitor this effect at cool-down time and deflux the RSFQ circuits as a part of normal diagnostics. 123

Fig.  36  shows  a  demo 124 cryopackage  on  a  cryocooler  produced  during  an  ATP program  on  network  switching  for  the  US  Department  of  Commerce. 125 This  package required a mounting stage at 4-5 K with a maximum power dissipation of 300 mW and a temperature stability of &lt; 100 mK. The minimum surface area was 3.25 in. in diameter. This  package  maintained  an  ambient  magnetic  field  &lt;  0.5  mG,  with  clearance  to accommodate 12 co-axial cables 0.085 OD. The second stage lifted a maximum power of 10-20  W  with  a  minimum  surface  area  of  20  in 2 and  a  temperature  stability  of  1  K. Primary concerns in the design were magnetic and electrical noise.

<!-- image -->

Fig.  36  (left)  ATP  program  HYPRES/Boreas  cryopackage/cryocooler  showing  all  three  CCR stages. The digital network switch system tested up to 4 Gb/s I/O. (right) Schematic of the CCR configuration  showing  the  multiple  temperature  stages  and  shielding.  (Photos  courtesy  of Conductus, Inc.)

<!-- image -->

Fig. 36(left) shows another cryopackage, designed specifically for both electrical and optical connections. This unit has been used with the high-resolution ADC described in section 2.1.1. The full ADC parallel output word was first serialized using a 'shift and dump'  type  multiplexor  on-chip  (i.e.  parallel-to-serial  converter)  and  then  used  to modulate  a  serial  data  stream  onto  an  optical  fiber  for  transfer  to  room  temperature electronics. 126,127 Magnetic  and  thermal  shields  are  shown  also.  Fig.  37(right)  shows  a similar package with 6 high-speed (&gt;10 GHz) SMA connectors for high-speed electrical I/O.  In  either  case,  the  package  would  be  heat  sunk  to  a  cold  finger  on  a  CCR  or alternatively  could  simply  be  immersion-cooled  in  liquid  helium  for  development  and reliability-testing.

Some applications, such as the DAC described in section 2.2.1 can benefit from the use  of  multiple  chips,  but  do  not  necessarily  require  the  full  performance  of  a  MCM process.  The  package  in  Fig.  38  accommodates  up  to  20  0.5  cm 2 RSFQ  chips  with relatively low-speed (500 MHz) interconnects. Triple high-µ metal shielding and flexible ribbon cable connectors make this design both robust and simple.

Fig. 37 (left) A cryopackage fitted for optical output with 3 high-speed lines and 18 low-speed lines and a mounting fixture for an output laser diode. (right) A similar cryopackage with 6 high-speed lines and 18 low-speed lines with dimensions: 5.75 in. x 2.1 in. x 1.1 in.

<!-- image -->

<!-- image -->

Fig.  38  Low-speed  multi-chip  package  being  developed  for  a  Josephson  AC-voltage  standard (DAC).

<!-- image -->

## 5.  Integrated RSFQ Applications

Many  applications  for  LTS  circuits  have  been  introduced  and  studied. 128,129 Some emphasizing the digital aspect of RSFQ have reached quite mature stages of development. 130 Recently, substantial funding has been made available for investigation of PetaFLOPs level computing. This future application has been extensively detailed 131,132 , including in the companion RSFQ paper in this issue, and is therefore not covered here. Other possible applications and their cryocooler requirements are reviewed in the following sections.

## 5.1 Application examples

## 5.1.1 Pseudo-random binary sequence generators

For  spread-spectrum  communications  protocols,  it  is  necessary  for  the  receiver  to synchronize its internal code generator with the incoming signal before receiving data.

37

The  speed  of  RSFQ  can  allow  this  synchronization  to  take  place  in  only  a  few  clock cycles, eliminating the need to send sync signals back and forth between transmitter and receiver by providing pseudo-random binary sequence generators. 133 Northrop Grumman has made good progress on this application. 134,135,136

## 5.1.2 Network switches

The  transmission  capacity  of  a  single  mode  optical  fiber  is  more  than  1  Tb/s  and  the speed of RSFQ is well matched to the bandwidth of optical fiber. Although photons (with their low energy) are a good match for sending signals, they interact only weakly, making it difficulty to perform fully-optical switching. The optical I/O capability of RSFQ (see section 4.3.2) creates the possibility of constructing a full optical network switch. 123 A 2node SFQ crossbar switch has been demonstrated with both data streams over 16 Gb/s at Northrop Grumman, while a 16 x 16 design was demonstrated at 3 Gb/s by TRW. 137 The ATP program discussed in section 4.3.2 is another good example. Unlike purely optical switching fabrics, RSFQ data switches can be rapidly reconfigured. For instance, for the Asynchronous  Transfer  Mode  (ATM)  packet  length  of  53  bytes  (i.e.  424  bits),  it  is necessary for an OC-192 data switch to configure the crosspoints every 42 ns. 138 While optical crosspoints are not fast enough for this, it is well within the capability of today's RSFQ  circuits. 139 In  fact,  one  analysis  has  shown  that  a  128 x 128  channel  self-routing Batcher-Banyan  switching  core  implemented  in  a  0.8-µm  RSFQ  technology  could provide throughput close to 100 Gbit per channel, dissipate about 10 mW of power, and fit on a single 1-cm 2 die. 140

## 5.1.3 Software Defined Radio

Considerable interest has arisen in the idea of enabling software-defined radios (SDR) 141 with RSFQ technology. 142 The SDR concept relies on the digitization of communications waveforms as close to the antenna as possible, with subsequent hardware and software DSP  to  sort  out  the  signals.  For  semiconductor  ADCs,  one  or  two  stages  of  downconversion and filtering are typically needed in order to bandlimit a single channel and move it to the baseband before it can be handled digitally. Using one or a combination of the approaches discussed in section 2.1, however, an entire band or several bands could be  digitized  at  once,  skipping  one  or  all  the  mixing  stages,  while  preserving  signal fidelity. The ability to feed the digitized waveforms directly into an RSFQ digital prefilter  before  handing  off  baseband  signals  to  the  control  hardware  might  also  enable dynamically  programmable  or  software  reconfigureable  systems  in  which  a  single platform  can  simultaneously  satisfy  the  requirements  of  communications,  radar,  and electronic warfare applications.

## 5.1.4 Digital RF Memories

Militaries  are  moving  toward  digital  multi-function  systems  (as  a  replacement  for dedicated  RF  systems)  in  order  to  reduce  cost  and  increase  flexibility.  A  digital  RF Memory (DRFM) is an Electronic Countermeasure (ECM) system designed to digitize wideband  waveforms,  store  them  in  a  cache  memory,  and  apply  time-delays  and

frequency-shifts to the data before uploading them to a direct digital synthesizer (DDS) for retransmission. The purpose of this is to put up false or distorted signals that will be misinterpreted by enemy receivers. Naturally, in order to appear realistic, the linearity of all  DRFM  components  should  be  greater  than  the  accuracy  of  the  targeted  receivers. Further,  there  is  a  requirement  that  all  processing  take  place  in  near-realtime.  RSFQ technology has demonstrated all the necessary components, including ADC, DAC, RAM, DSP, etc. for this application.

Fig 39. Digital RF memory test at KOR Electronics (San Diego, CA) showing how an existing system can be retrofitted with an RSFQ chip without loss of performance.

<!-- image -->

As a first step toward the realization of an all-RSFQ DRFM, HYPRES (Elmsford, NY) has worked with Kor Electronics (San Diego, CA) to take a traditional DRFM and replace only the ADC portion with the RSFQ ADC described in section 2.1.1. Fig. 39 shows the measurement setup for such tests. As input, a 500 ps wide pulse was applied to the ADC at a rate of 29 MHz. The digitized waveform was then passed directly from the superconductor  ADC  to  a  fast  semiconductor  memory  and  immediately  uploaded  to  a GaAs DAC. Power spectra before ADC digitization and after conversion back to analog are shown. Performance was limited by the DAC fidelity. Although rigorous measurements are not yet complete, this demonstration proves the validity of replacing a single system section with an RSFQ component.

## 5.1.5  Time-to-digital converters

Another area where RSFQ circuits are particularly well suited is for the instrumentation of high-energy physics (HEP) experiments. 143 In such applications, LHe is typically used to  cool  superconducting  magnets,  creating  a  natural  place  for  cooling  the  circuits. Because  RSFQ  circuits  are  inherently  radiation-hard 144,145 ,  they  perform  well  in  highradiation  HEP  environments.  Further,  such  circuits  offer  better  sensitivity  for  the measurement of weak detector signals and can reduce SNR degradation by performing

the digitization and multiplexing of many detector signals before the transition to room temperature. A Time-to-Digital Converter (TDC) is one such detector that can be made using RSFQ technology. A TDC is essentially an electronic stopwatch, able to determine the absolute and relative time difference between events (or 'hits') and report them as digital numbers.

Fig. 40. (left) 8-channel TDC chip and (right) block diagram of a single channel.

<!-- image -->

Fig. 40  shows  the  layout  of  an  8-channel  TDC  chip  (left)  and  block  diagram  of  a single-channel (right). Each TDC channel consists of a 14-bit RSFQ counter based on T flip-flops  with  destructive  readouts,  a  9-hit  (i.e.  9-word)  shift  register-based  FIFO memory, and a parallel-to-serial converter with output driver. To facilitate both external user  control  and  data  output  from  the  TDC,  a  complete  VXI-bus  user  interface  with LabView  control  software  has  also  been  constructed.  A  detailed  design  of  the  RSFQ multi-hit TDC circuit is described in Refs. 146 and 147. Interestingly, the binary counter is the only component required to operate at the maximum GHz rate. The FIFO buffer is used to store multiple time stamps associated with different input hits and the parallel-toserial converter provides a serial mode of data readout. An extra 'valid bit' register has even  been  added  to  provide  tagging  capabilities  in  order  to  distinguish  between  valid information and time references, blank time stamps, etc. As shown on the measurement in Fig. 41(left), the applied distance between the first and the second hits is 0.2000 µs and the clock frequency is 33 GHz. The 13-bit binary data output is (1100110111111), which is 6591 in decimal representation. Thus, 6591 x (1/33 GHz) = 0.1997 µs = 0.2 µs ±2.5 ps, as dictated by the design. Further applications are discussed in Ref. 148. Fig. 41(right) shows a prototype control station for the TDC instrument currently under development by HYPRES (Elmsford, NY) for the US Department of Energy's Fermilab (Batavia, IL).

Fig. 41 (left) High-speed testing of the digital (coarse) part of the TDC showing 2.5 ps resolution and (right) TDC user interface showing a VXI crate with interface cards and controlling PC with LabVIEW acquisition, control, and display software.

<!-- image -->

## 5.1.6 Digital signal autocorrelators

Signal autocorrelators perform a correlation function on a spectrum to detect the presence of  periodic  signals,  even  when  the  signal  strength  is  very  weak.  This  is  based  on  the principle  that  random  noise  (non-periodic)  averages  down  and  signals  (periodic)  are brought  out.  Unfortunately,  typical  semiconductor-based  systems  can  take  msec  to seconds to reveal the presence of some covert communications waveforms or to receive spread-spectrum communications signals in areas with significant clutter. RSFQ autocorrelators  offer  two  important  advantages  over  other  technologies.  First,  the hardware  complexity  of  a  broadband  digital  correlator  decreases  rapidly  with  clock speed. From this consideration, RSFQ digital correlators running at 20 GHz clock speeds definitely outperform the existing analog correlators when the level of ~100 stages (or 'lags') is reached. With ~1000 lags they will beat the digital as well as the (very complex and  costly)  analog-digital  systems.  Another  advantage  of  an  RSFQ  correlator  arises  in space-borne  applications  where  reduction  in  power  dissipation  could  be  of  crucial importance. Power dissipated by an RSFQ correlator can be reduced to below 1 µW (at 4.2  K)  per  channel  for  clock  speeds  up  to  20  GHz.  Even  with  a  very  inefficient cryocooler (say 0.1%) this translates into only 1 mW per channel at room temperature and is two orders of magnitude better than semiconductor correlators.

The  basic  correlation  process  consists  of  a  standard  sum  of  products  calculation. Given two data vectors, the corresponding elements from each vector are multiplied and then all the products are summed to a single result. One of the vectors is then shifted by a single element and the multiply and sum process is repeated to produce the next result data point. This process is illustrated in Fig. 42(right).  A 16-channel, 4 GHz bandwidth, double  oversampling  (16  GHz  clock),  RSFQ  autocorrelator  of  this  type  has  been demonstrated. 144,149 The active area of the correlator IC is shown in Fig. 42(left).

Fig. 42 (left) Mask layout for autocorrelator. (right) Block diagram of autocorrelator.

<!-- image -->

## 5.1.7 Fast Fourier Transform Engines

For many digital signal processing applications, especially in SIGINT (signal intercept) and Comms (communications), a transform into the frequency domain allows the use of significantly  faster  algorithms  for  discriminating,  selecting,  and  identifying  waveforms. Unfortunately,  the  calculation  of  the  Fourier  transform  of  a  signal  (even  with  the  Fast Fourier Transform [FFT] method) is very compute-intensive, and grows more so as finer frequency  resolution  is  desired.  Fig.  43  shows  an  RSFQ  Decimation-in-Time  (DIT) Radix-2 Butterfly integrated circuit which is the basic cell needed to implement the 32point  Fast  Fourier  Transform  (FFT)  in  a  parallel  data  flow  architecture. 97 The  radix-2 butterfly  circuit  uses  serial  RSFQ  math  and  consists  of  four  single  bit-wide  serial multipliers and eight carry-save serial adders of the type outlined in section 3.3.3. The circuit with 16-bit word-length employs only 3400 JJs, occupies an area of 3.8 mm x 2.0 mm, and dissipates less than 1.1 mW power.

Fig. 43. (left) 2 Radix-2 16-bit multipliers on a 0.5 cm 2  chip. (right) Full operation of a radix-2 butterfly with 5-bit word length. Outputs are RTZ  with LSBs first. Inputs are W Im = (11111), Y Im = (01110), W Re = (11011), Y Re = (10101), X Re = -X Im = (1011000000), X Im = -X Re = (0101000000). Note, no subtractors are used in the circuit.

<!-- image -->

A DIT radix-2 butterfly operation requires one complex ( ´ e &amp; ` m) multiply and two complex additions. A purely real implementation requires four real multipliers and six real adders to compute:

<!-- formula-not-decoded -->

Fig. 43(right) shows a demonstration of full functional operation of the radix-2 butterfly chip  with  a  5-bit  word  length.  To  multiply, N x 1-bit  serial  multipliers  are  used.  To add/subtract, 1-bit carry-save serial adders (CSSA) are used.

## 5.2  Cryogenic refrigerator requirements

RSFQ circuitry must be cooled for operation. The temperature of operation is normally selected to be ~½ of the material's superconducting transition 'critical temperature' ( Tc ). For  operating  temperatures  below  ½ Tc ,  superconducting  parameters  are  not  strongly sensitive  to  small  variations  in  temperature.  Above  ½ Tc ,  Josephson  junction  device operation  becomes  very  sensitive  to  thermal  fluctuations,  resulting  in  greatly  reduced parameter operating margins. 150 For Nb ( Tc = 9.23 K), operating at the boiling point of LHe at one atmosphere (4.2 K), meets this requirement. A closed-cycle refrigerator with a 5 K final stage temperature is also a suitable platform. 151 At these temperatures, RSFQ circuits require ~10 to 100 mK stability.

Cooling of commercial RSFQ superconducting electronics requires low cost, closed cycle refrigeration. Logistics inhibit the widespread use of LHe, except in a laboratory setting. Space-based (satellite) applications of RSFQ require cryocoolers of the highest reliability,  lowest  input  power,  and  small  weight  and  size;  while  marginal  capital  cost relative  to  that  of  the  electronics  subsystem,  are  the  paramount  concern  for  other applications.  A  cost-reliability  goal  for  commercial  cryocoolers  has  been  suggested  at $1K to 10K for a unit with a 2-10 year lifetime. 152

Refrigeration power required for a RSFQ system will likely be a few watts at most and  the  dominant  heat  load  will  be  heat  leaks  by  radiation  and  conduction  from  the surrounding interface electronics, rather than the RSFQ chips themselves. Consequently, the refrigeration power to go from 300 to 77 K is not much less (~30%) than to go from room temperature to 5 K. However, input power requirements are about 600-2000 W for the LTS RSFQ temperature range, for 0.5 W of refrigeration power, due to the Carnot and actual thermal cycle efficiencies.

Ultimately, it is the thermal conductivity of the I/O and the active device dissipation that determines the requirements of the cryocooler. For a typical RSFQ ADC system, a refrigerator might be needed that can cool a minimum of 250 mW at 5 K; ideally 350 mW. This cooling budget consists of: 100 mW for the RSFQ chip, 70 mW for the I/O heat load from a 40 K stage to the 5 K stage. With a 50% to 100% design margin, this results in 250 mW to 340 mW total power lift.

## 5.2.1 Product platforms

Most refrigerator systems have two separate mechanical components: a cold head and a compressor. The cold head is where the RSFQ circuits are mounted. It can be compact and dissipates only a small amount of power. The compressor contains a motor driven compressor stage and (in some cases) oil particle traps, and dissipates almost all of the required power. It is important to note that the power required by the compressor is for operating a motor, and thus can be primary unregulated power. The fundamentals of CCR operation can be found in Ref.153.

Since extending the lifetime of existing cryocoolers directly impacts cost, and since moving parts limit long-term reliability or lifetime, the most dramatic small cryocooler improvements are in the form of pulse tube refrigerators with only one moving part. 154 The pulse tube is second only to Stirling refrigerators in efficiency. Stirling coolers have gained widespread acceptance for use in infrared sensor cooling. First in reliability and second in current production today are Gifford-McMahon (GM) refrigerators, which are used as cryopumps on high vacuum systems. While these GM production units typically reach 12-15 K, high heat-capacity materials, such as Er 3Ni can be used instead of Pb in a regenerative heat exchanger to yield 4-5 K operation, without resorting to the previously required  separate  Joule-Thomson  (JT)  final  stage. 155 Such  units  are  expandable  to  lift several watts at the 5 K level by using a higher-power compressor. 156

With regard to CCR reliability, MTBFs of 80,000 hours are achievable with GM and JT cryocoolers, although some periodic maintenance may be required (i.e. oil adsorber replacement) perhaps every 18-24 months. Theoretical lifetimes for free-piston Stirling cryocoolers using gas bearings and/or flexture bearings or pulse-tube coolers are also of this magnitude, but do not yet have operating histories to support such numbers. 119 Fig. 44 illustrates the myriad of platforms which can accommodate a CCR-packaged RSFQ system. Although not likely to be found on a handheld devices any time soon, solutions do  exist  for  the  majority  of  fixed-site  and  mobile  platforms,  with  the  possibility  of dismounted (portable) systems in the future.

The practicality of RSFQ-based applications is linked to the ability to package and power such systems. Various options exist for active (closed-cycle refrigerator or CCR) cryocooling to the necessary 45 Kelvin temperatures. Today's cooling options can be loosely grouped into two classes: 'Commercial' and 'Developing'. Examples are given in the following sections.

Fig. 44 Platforms capable of fielding cryogenic electronics.

<!-- image -->

## 5.2.2 Commercial Coolers

Near-term RSFQ systems can make use of commercially available cryocoolers. (i.e., no cooler development work is needed). Instead, work would focus on system integration issues, input/output, and robustness.

The  Leybold  'CoolPower  4.2LAB':  Fig.45(left)  shows  this  compact  (19  in.  rackmountable) cooler which provides a full 0.75 W at 5 K, drawing 2 kW at 220 V (singlephase)  input  power.  It  is  air-cooled  and  requires  one  standard  maintenance  every  24 months.  This  2-stage  Gifford-McMahon  (GM)  cycle  CCR  is  used  for  the  HYPRES primary voltage standard product and is currently deployed, in the field, as a platform for superconductor ICs. The &lt; 100 kg. unit has not been optimized for size and might be reduced in overall profile without undue impact on performance.

Fig. 45 (left) A 19 in. rackmountable Leybold '4.2LAB' 2-stage Gifford-McMahon cryocooler delivering ¼ W of lift at 4 K for 2 kW input power. (right) A CTI single stage Gifford-McMahon cryocooler delivering 60 W lift at 60 K with a no-load temperature of 45 K.

<!-- image -->

45

The  CTI  'Cryodyne'  Refrigerator:  Fig.45(right)  shows  a  single  stage  GM  cooler based on the CTI M350 and 8F Cryopumps which delivers 6 W of lift at 60 K using 600 W  from  the  wall. 119 A  second  stage  might  be  added  to  the  cold-head  to  achieve  the required specifications, perhaps even with the same compressor. Many of these units are currently deployed in the field as a platform for Conductus superconductor HTS filters and have demonstrated excellent reliability statistics. At only 60 lbs., this cooler easily mounts into a standard half-ATR rack and is gaining acceptance within the wireless basestation community as a communications platform. Other 4-5 K commercial cryocoolers are available from many different manufacturers including APD Cryogenics, Sumitomo, Toshiba, Mitsubishi, etc. Improved high-capacity versions (suitable for ground base or large shipboard installations) have recently entered the market as well.

## 5.2.3. Developing Coolers

The reduction in form-factor necessary to realize a single-person-portable or 'backpack'sized  system  stems  from  currently  demonstrated  (but  not  yet  commercial)  technology. There are several promising candidates for 4-5 K RSFQ cooling, although none has yet been demonstrated with the necessary specifications.

The TRW 3503 Pulse-tube cooler: 157 Fig.46(left) shows this ultra-rugged unit which contains no moving parts at the cold-head and has been space-qualified. (Two units are currently deployed in satellites). The unit provides 0.3 W of lift at 35 K for 82 W into the compressor with a 300 K sink temperature: weight = 12.1 kg, size = 341 mm x 200 mm x 498 mm. Additional study into the use of rare-earth regenerators and or a JT expansion stage in the design is the focus of work needed to explore the possibility of 5 K operation. The clever use of reciprocating flexture bearings in the Stirling compressor allows for very little net vibration in the unit, a good match for the requirements of satellite systems.

Fig. 46 (left) Space-qualified TRW 3503 Pulse-tube cryocooler with Sterling compressor r eaches 35 K today. (right) Example of a fullcustom 'MMS 50-80K' class split-sterling cooler for space applications reaches which reaches 4.5 K.

<!-- image -->

<!-- image -->

The Matra Marconi Space 'MMS 50-80K' class of split-Stirling cryocoolers: 158 Fig. 46(right)  shows  another  custom  unit  designed  for  ultra-long  life  applications  for  the European Space Agency (ESA). The 18 kg unit shown can be pushed down to provide 0.11 W of lift at 4.5 K from a compressor power budget of 145 W. Further optimization

has been suggested to increase the lift capacity; however, the cost-to-produce may remain very high, even in large quantities.

The recent introduction of off-the-shelf 5 K CCRs, such as the Leybold unit in section 5.2.2,  has  already  resulted  in  Nb  superconductor  IC-based  products  being  brought  to market.  The  HYPRES  Primary  Josephson  Voltage  Standard  (see  Fig.  47),  previously available only in a LHe-dewar format, is now being sold as a fully self-contained unit based on this CCR. Besides the long-term savings in cryogens for the user, the upgraded unit now requires less maintenance. Further reductions in the size-weight-power profile of CCRs will undoubtedly open up further markets as outlined in section 5.1. The lack of application pull has slowed this development more than the technical challenges. Simply put, if there is a market for cryogenic refrigeration, it could soon be available with the same reliability and cost/performance as household refrigerators.

Fig.  47  Availability  of  off-the-shelf  cryogenic  refrigerators  has  made  superconductor  IC-based products much more user-friendly. This fully self-contained commercial Primary Voltage Standard system from HYPRES uses an Nb trilayer superconductor IC with an array of over 20,000 JJs to reproduce the Systeme Internationale (SI) unit of the Volt for metrology applications in any lab.

<!-- image -->

<!-- image -->

## 6.  Conclusion

As  we  move  closer  to  the  centennial  celebration  of  the  1911  discovery  of  the phenomenon  of  superconductivity,  the  prospect  of  practical  and  useful  applications  of superconductor microelectronics is at its most promising. Fifty years of superconductor research  into  first  analog  and  then  digital  circuits  has  developed  in  the  shadow  of  a semiconductorfueled  'information  revolution'  which  has  invigorated  economies  and shaped  cultures.  Exploiting  the  massive  investment  in  semiconductor  integrated  circuit

processing  equipment,  design  techniques,  and  application  niches,  the  very  demand  for '100 GHz-level' performance created by semiconductors may, in fact, only be fulfilled by superconductors . RSFQ technology could be the key. 159

RSFQ data converters are the fastest and most sensitive ever demonstrated. With a full cadre of clocking, logic, and memory approaches under development, this versatile technology  could  conceivably  merge  the  Digital  and  RF  domains,  once  and  for  all. Moreover,  as  quantum  computation,  optical  and  biological  systems,  or  other  new technologies  mature,  RSFQ  may  be  the  only  approach  with  the  speed  and  integration scale to bridge the gap between traditional electronic data and future formats.

The  key  hurdle  to  achieving  these  technical  goals  is  one  of  investment  -  in  both people  and  facilities.  The  US  DoD  'University  Research  Initiative'  in  LTS  Digital Electronics  that  ran  from  1992  -  1997  produced  a  number  of  new  academic  design centers  for  RSFQ.  If  this  technology  is  to  continue  to  mature,  these  centers  must  be allowed to thrive. Moreover, the inclusion the cooling and interface components requires that cryogenics experts become a standard part of the RSFQ system design team. System form  factor,  refrigeration  power,  and  operating  temperature  variations  need  to  be  well defined; heat leaks and magnetic shielding are key constraints for system packaging. But these are quite solvable issues. Indeed, with proper investment, prototype RSFQ systems for  wireless  base-station  receivers  and  network  switches  could  be  available  within  2-3 years.  In  the  end,  the  cryogenic  nature  of  RSFQ  systems  will  not  be  as  much  a technological issue, as a psychological issue for the prospective user - it represents a true paradigm  shift  in  the  definition  of  an  electronic  system.  The  desire  for  100  GHz performance, however, if great enough, can surmount even this barrier.

## Acknowledgements

Special  thanks  to  all  who  contributed  data,  text,  figures,  and/or  assisted  with proofreading,  including:  John  Rowell,  Deepnaryan  Gupta,  Oleg  Mukhanov,  Alex Kirichenko  and  Alan  Kadin  of  HYPRES;  Konstatin  Likharev,  Paul  Bunyk,  Dmitry Zinoviev, and Vasili Semenov of SUNY Stony Brook; Dale Durand, Andy Smith, and John Spargo of TRW; John Przybysz and Don Miller of Northrop Grumman; Sam Benz of NIST; and Yongming Zhang of Conductus.

## References

1. J. Richey, 'The future of high-speed electronics: RF and Digital electronics will converge to the same domain,' plenary address at Commercialization of Cryoelectronics Technologies in Microelectronics , San Francisco, CA - Feb. 19, 1999.
2. The best research-grade bipolar transistor amplifier and/or digital frequency divider designs reach  an  operational  frequency  ~4 x below  the  unity  power-gain  bandwidth  point, f max . Historically, performance of commercial parts has been closer to 7 x below f max . See also: E. Sano, Y. Matsuoka, and T. Ishibashi, 'Device figure-of-merits for high-speed digital ICs and baseband amplifiers,' IEICE Trans. Electron. E78-C (1995) 1182-1188.
3. M. Schultz, 'The end of the road for silicon?' Natur . 399 (1999) 729-730.

4. P. Packman, 'Pushing the limits,' Sci. 285 (1999) 2079-2081.
5. Semiconductor Industry Association, '1999 International Technology Semiconductors,' [Online] http:// www.itrs.net/ 1999\_SIA\_Roadmap/Home.htm.
6. C. Bennett, 'Quantum information and computation,' Phys. Today 48 (1995) 24-30.
7. L. Adleman, 'Computing with DNA,' Sci. Amer. 279 (1998) 54-61.
8. M. Reed, 'Molecular-scale electronics,' Proc. IEEE 87 (1999) 652-658.
9. For a concise review of superconductivity see: J. Schrieffer and 'Superconductivity,' Rev. Mod. Phys. 71 (1999) S313-S317.

M.

for

Tinkham,

10. General reviews of RSFQ fundamentals are found in: K. Likharev and V. Semenov, 'RSFQ logic/memory family: A new Josephson-junction digital technology for sub-Terahertz-clockfrequency  digital  systems,' IEEE  Trans.  Appl.  Supercond. 1 (1991)  3-28;  K.  Likharev, 'Rapid  single  flux  quantum  logic'  in  H.  Weinstock  and  R.  Ralston  (eds.),  The  New Superconducting Electronics , Kluwer, Dordrecht (1993) 423-452; K. Likharev, 'Superconductor  devices  for  ultrafast  computing,'  in  H.  Weinstock  (ed.)  Applications  of Superconductivity , Kluwer, Dordrecht, (2000) 247-294; and P. Bunyk, K. Likharev, and D. Zinoviev, 'RSFQ Technology: Physics and Devices,' this issue .
11. W.  Chen,  A.  Rylyakov,  V.  Patel,  J.  Lukens,  and  K.  Likharev,  'Superconductor  digital frequency divider operating up to 750 GHz,' Appl. Phys. Lett. 73 (1998) 2817-2819; and W. Chen, A. Rylakov, V. Patel, J. Lukens, and K. Likharev, 'Rapid single flux quantum T-flip flop operating up to 770 GHz,' IEEE Trans. Appl. Supercond. 9 (1999) 3212-3215.
12. HYPRES, Inc., 'HYPRES Nb Design Rules rev. 017', [Online] http:// www.hy res.com/.
13.    L. Ya, C. Berry, R. Drake, et al., 'An all-niobium eight level process for small and medium scale applications,' IEEE Trans. Mag. 23 (1987) 1476-1497.
14. F. London, Superfluids Vol. 1 Macroscopic Theory of Superconductivity , Dover, New York (1950).
15. B. Deaver and W. Fairbank, 'Experimental evidence for quantized flux in superconducting cylinders,' Phys. Rev. Lett. 7 (1961) 43-46.
16. B. Josephson, 'Possible new effects in superconductive tunneling,' Phys. Lett. 1 (1962) 251253.
8. 17 See various articles on latching logics the special issues of IEEE Trans. Elect. Dev. 27 (Oct. 1980) and Proc. IEEE 77 (Aug. 1989).
18. 'Josephson computer technology: An IBM research project,' in Special Issue of IBM J. Res. Dev. 24 (Mar. 1980). A MITI program also ran in Japan from 1981-1990 (see also Ref. 23).
19.    H. Kroger, L. Smith, and D. Jille, 'Selective anodization process for fabricating Josephson tunnel junctions,' Appl. Phys. Lett. 39 (1981) 2180-2182.
20. M.  Gurvitch,  M.  A.  Washington,  and  H.  A.  Huggins,  'High  quality  refractory  Josephson tunnel junctions utilizing thin aluminum layers,' Appl. Phys. Lett. 42 (1983) 472-475.
21. S. Hasuo, T. Imamura and N. Fujimaki 'Recent advances in Josephson junctions devices,' Fujitsu Tech. J. 24 (1988) 284-292.
22. Y. Tarytani, M. Hirado, and U. Kawabe, 'Niobium-based integrated circuit technologies,' Proc. IEEE 77 (1989) 1164-1176.
23. S.  Hasuo,  S.  Kotani,  A.  Inoue,  and  N.  Fujimaki,  'High  speed  Josephson  processor technology', IEEE Trans. Mag. 27 (1991) 2602-2609.
24.     G. Kerber, L. Abelson, R. Elmadjian, et al., 'An improved NbN integrated circuit process featuring thick NbN ground plane and lower parasitic circuit inductance,' IEEE Trans. Appl. Supercond. 7 (1997) 2638-2641.

Roadmap

25. K.K. Likharev, O.A. Mukhanov, and V.K. Semenov, 'Resistive single flux quantum logic for the Josephson-junction technology, in H. Hahlbomand and H. Lübbig (eds.) SQUID'85 , W. deGruyter, Berlin, (1985) 1103-1108.
26. K. Likharev, O. Mukhanov, V. Semenov, 'Ultimate performance of RSFQ logic circuits,' IEEE Trans. Mag. 23 (1987) 759-762.
27. Good textbooks covering the basics of superconductor circuits include: T. Orlando, and K. Delin, Foundations of Applied Superconductivity , Addison-Wesley, Reading MA. (1991); M. Tinkham, Introduction to Superconductivity, 2 nd ed. McGraw-Hill, New York, (1996); T. Van Duzer and C. Turner, Principles of Superconductive Devices 2 nd ed. (1999); and A.M. Kadin, Introduction to Superconducting Circuits , Wiley Interscience, New York (1999).
28.    First introduced in P. Anderson, R. Dynes, and T. Fulton, 'Josephson flux quantum shuttles,' Bull. Am Phys. Soc 16 (1971) 399; and then expounded upon in T. Fulton, R. Dynes, and P. Anderson,  'The  flux  shuttle  -  A  Josephson  shift  register  employing  single  flux  quanta,' Proc. IEEE 61 (1973) 28-35.
29. J. P. Hurrell and A. H. Silver, 'SQUID digital electronics', in: B.S. Deaver Jr. et al. (eds . ) , Future Trends in Superconductive Electronics , AIP, New York, (1978) 437-447.
30. K. Nakajima, Y. Onodera, and Y. Ogawa, 'Logic design of Josephson network,' J. Appl. Phys. 47 (1976) 1620-1627.
31. K. Nakajima and Y. Onodera, 'Logic design of Josephson network - II,' J. Appl. Phys. 49 (1978) 2958-2963.
32. J. Deng, S. Whiteley, and T. VanDuzer, 'Data-driven self-timing of RSFQ digital integrated circuits and systems,' IEEE Trans. Appl. Supercond. 7 (1997) 3634-3637.
33. N.  Yoshikawa,  H.  Tago,  and  K.  Yoneyama,  'Design  considerations  for  data-driven  selftimed RSFQ adder circuits,' IEICE Trans. on Electron. E81-C (1998) 16-18-1626.
34. K. Nakajima, Y. Mizugaki, T. Onomi, and T. Yamashita, 'Fluxiod-type logic circuits,' in H. Ohta and C. Ishii (eds.), Physics and Application of Mesoscopic Josephson Junctions , Phys. Soc. Jap., Toyko (1999) 267-288.
35. 'Present status, future prospects and market potential for 4-5 K cryocoolers' in Proceedings of the HYPRES 5 K Cryocooler Workshop July 24-25, (1995), available from HYPRES Inc.
36. See e.g. Leybold Lab4.2 2-stage GM unit.
37. R.  Radebaugh,  'Development  of  the  pulse  tube  refrigerator  as  an  efficient  and  reliable cryocooler,' Proc. Inst. Referig. (1999) 1-16.
38.    J.  Yoshida,  'Recent  progress  of  high-temperature  superc onductor  Josephson  junction technology for digital circuit applications,' IEICE Trans. Electron. E83-C (2000) 49-59.
39. H.  Terai  and  Z.  Wang,  'All-NbN  single  flux  quantum  circuits  based  on  NbN/AlN/NbN tunnel junctions,' IEICE Trans. Electron. E83-C (2000) 69-74.
40. A.  Braginski,  'Superconducting  Electronics  Coming  to  Market,' IEEE  Trans.  Appl. Supercond. 9 (1999) 2825-2836.
41.    J.  Rowell,  'Recommended  Directions  of  Research  and  Development  in  Superconducting Electronics,' IEEE Trans. Appl. Supercond. 9 (1999) 2837-2848.
42. C.  Rosner,  'Emerging  21st  century  markets  and  outlook  for  applied  superconducting products,' in P. Kittel (ed.), Advances in Cryogenic Engineering 43A (1998) 1-23.
43. K. Gaj, Q. Herr, V. Adler, D. Brock, E. Friedman, and M. Feldman 'Towards a systematic design  methodology  for  large  multi-gigahertz  rapid  single  flux  quantum  circuits,' IEEE Trans. Appl. Supercond. 9 (1999) 4591-4606.
44. G. Lee and D. Petersen, 'Superconductive A/D converters,' Proc. IEEE 77 (1989) 12641273.

45. :KHQGLYPH&lt;3&gt;XVLQJGLYPH&lt;3&gt;IOX[RQVGLYPH&lt;15&gt;GLYPH&lt;3&gt; 0, as data bits, a time-averaged voltage measurement serves as a direct measurement of the bit-rate according to the relation ‹ V › GLYPH&lt;3&gt;  GLYPH&lt;3&gt; 0/sec, where the measurement accuracy is determined by the uncertainty limit on the voltage measurement apparatus.
46. C. Hamilton, C. Burroughs, and S. Benz, 'Josephson voltage standard - A review,' IEEE Trans. Appl. Supercond. 7 (1997) 3756-3761.
47. R. Walden, 'Analog-to-digital converter survey and analysis,' IEEE J. Selec. Areas Comm. 17 (1999) 539-550.
48. S.  Rylov,  D.  Brock,  D.  Gaidarenko,  A.  Kirichenko,  J.  Vogt,  and  V.  Semenov,  'High resolution  ADC  using  phase  modulation-demodulation  architecture,' IEEE  Trans.  Appl. Supercond. 9 (1999) 3016-3019.
49. S. Rylov, 'Novel architecture for flux quantizing ADCs,' Extend. Abs of 4 th Intl. Supercond. Electr. Conf. Boulder, CO (1993) 112-113.
50. S.  Rylov,  'Analysis  of  high-performance  counter-type  A/D  converters  using  RSFQ logic/memory elements,' IEEE Trans. Mag . 27 (1991) 2431-2434.
51. E.  Hogenauer,  'An  economical  class  of  digital  filters  for  decimation  and  interpolation,' IEEE. Trans. Acoust., Speech, and Sig. Proc. 29 (1981) 155-162.
52. S. Rylov and R. Robertazzi, 'Superc onducting high-resolution A/D converter based on phase modulation and multi-channel timing arbitration,' IEEE Trans. Appl. Supercond. 5 (1995) 2260-2263.
53. S.  Rylov,  L.  Bunz,  D.  Gaidarenko,  M.  Fisher,  R.  Robertazzi,  and  O.  Mukhanov,  "High resolution ADC system," IEEE Trans. Appl. Supercond . 7 (1997) 2649-2652.
54. O.  Mukhanov,  D.  Brock,  A.  Kirichenko,  et  al.,  'Progress  in  the  Development  of  a Superconductive High-Resolution ADC,' Extend. Abs of 7th Intl. Supercond. Electr. Conf. Berkeley, CA, 13-16.
55. D. Brock, O. Mukhanov, W. Li, et al.,'A Dynamically programmable ADC for multifunction digital receivers,' Gov. Microcir. App. Conf. Dig. Pap 25 (2000) 217-220.
56. P. Bradley, 'A 6-bit Josephson flash A/D converter with GHz input bandwidth,' IEEE Trans. Appl. Supercond. 3 (1993) 2550-2557.
57. S.  Rylov,  V.  Semenov,  and  K.  Likharev,  'Josephson  junction  A/D  converters  using differential coding,' IEEE Trans. Mag. 23 (1987) 735-378.
58. G. Lee and H. Ko, 'Phase tree: a periodic, fractional flux quantum vernier for high-speed interpolation of A/D converters,' IEEE Trans. Appl. Supercond. 3 (1993) 3001-3004.
59. S. B. Kaplan, S. V. Rylov and P.D. Bradley, 'Real-time digital error correction for flash analog-to-digital converter,' IEEE Trans. Appl. Supercond. 7 (1997) 2822-2825.
60.    C.  Anderson,  'Josephson  look-back  analog  to  digital  converter,' IEEE  Trans.  Appl. Supercond, 3 (1993) 2769-2773.
61. J.  Candy  and  G.  Temes,  (ed.),  Oversampling  Delta-Sigma  Data  Converters ,  IEEE  Pre s, Piscataway, NJ (1992).
62. J. Przybysz, D. Miller, E. Naviasky, and J. Kang, Josephson sigma-delta modulator for high dynamic range A/D conversion,' IEEE Trans. Appl. Supercond. 3 (1993) 2732-2735.
63. J. Przybysz, D. Miller, and E. Naviasky, 'Two-loop modulator for sigma-delta analog-todigital converter,' IEEE Trans. Appl. Supercond . 5 (1995) 2248-2251.
64. D.  Miller,  J.  Przybysz,  H.  Worsham,  and  E.  Dean  'Flux  quantum  sigma-delta  analog-todigital converters for rf signals,' IEEE Trans. Appl. Supercond. 9 (1999) 4026-4029.
65. D. Miller, J. Przybysz, H. Worsham, and A. Miklich, 'Superconducting sigma-delta analogto-digital converters,' Extend. Abstr. of 6 th Intl. Supercond. Elec. Conf. , Berlin, Germany (1997) 38-40.

66. S. Benz, C. Hamilton, and C. Burroughs 'Operating margins for a superconducting voltage waveform  synthesizer,' Extend.  Abs  of  7th  Inter.  Supercond.  Electr.  Conf. Berkeley,  CA (1999) 115-117.
67.    H.  Sasaki,  S.  Kiryu,  F.  Hirayama,  et  al.,  'RSFQ-based  D/A  converter  for  AC  voltage standard,' IEEE Trans. Appl. Supercond. 9 (1999) 3561-3564.
68. V.K. Semenov, 'Digital to analog conversion based on processing of the SFQ pulses,' IEEE Trans. Appl. Supercond. 3 (1993) 2637-2640.
69. C.A. Hamilton, 'Josephson voltage standard based on single-flux-quantum multipliers,' IEEE Trans. Appl. Supercond. 2 (1992) 139-142;  and  S.P. Benz, Appl. Phys. Lett . 67 (1995) 2714.

voltage

70. S.P. Benz and C.A. Hamilton,  'A pulse-driven programmable Josephson voltage standard,' Appl. Phys. Lett . 68 (1996) 3171-3173.
71. A.  Benz,  C.  Hamilton,  C.  Bouroughs,  et  al.,  'Pulse-driven  Josephson  digital/analog converter,' IEEE Trans. Appl. Supercond . 8 (1998) 42-47.
72.    K. Gaj, E. Friedman, and M. Feldman, 'Timing of multi-Gigahertz RSFQ digital circuits,' J. VLSI Sig. Proc. Sys . 16 (1997) 2826-2831.
73. J.L in and  V.  Semenov,  'Timing  circuits  for  RSFQ  digital  systems,' IEEE  Trans.  Appl. Supercond . 5 (1995) 3472-3477.
74. C.  Mancini  and  M.  Bocko,  'Short-term  stability  of  RSFQ  ring  oscillators,' IEEE  Trans. Appl. Supercond . 9 (1999) 3545-3548.
75. D. Gupta and Y. Zhang, 'On-Chip Clock Technology for Ultrafast Digital Superconducting Electronics,' Appl. Phys. Lett ., 76 (2000) 3819-3821.
76. Y.M.  Zhang,  V.  Borzenets,  V.K.  Kaplunenko,  and  N.B.  Dubash,  'Underdamped  long Josephson junction coupled to overdamped single-flux-quantum circuits,' Appl. Phys. Lett. , 71 (1997) 1-3.
77. Y. Zhang and D. Gupta, 'Low-jitter on-chip clock for RSFQ circuit applications', Exten. Abs.of 7 th Intl. Supercond. Elec. Conf. Berkeley, CA (1999) 88-90.
78.    D. Brock and M. Pambianchi, 'A 50 GHz monolithic RSFQ digital phase-locked loop,' 2000 Intl. Microwave Symp. Dig. Vol. 1 (2000) TU4D-3.
79. See  for  instance:  R.E.  Best,  Phase-Locked  loops:  Design,  Simulation,  and  Applications , McGraw-Hill, New York (1997) 91.
80. S. Nagasawa, Y. Hashimoto, H Numata, and S. Tahara, 'High-frequency clock operation of Josephson 256-word x 16-bit RAMs,' IEEE Trans. Appl. Supercond. 9 (1999) 3708-3713.
81. S.  Nagasewa,  H.  Hasegawa,  T  Hasimoto,  et  al.  'Design  of  a  16  K-bit  superconducting latching/SFQ hybrid RAM,' Extend. Abs of 7th Intl. Supercond. Electr. Conf. Berkeley, CA (1999) 365-367.
82. Q. Herr and L. Eaton 'Towards a 16 kilobit, sub-nanosecond Josephson RAM', Extend. Abs of 7th Inter.Supercond. Electr. Conf. Berkeley, CA (1999) 362-364.
83. A.  Kirichenko,  O.  Mukhanov,  and  D.  Brock  'A  single  flux  quantum  cryogenic  random access memory' Extend. Abs of 7 th Inter.Supercond. Electr. Conf. Berkeley, CA (1999) 124127.
84. S. Nagasawa, Y. Hashimoto, H Numata, and S. Tahara, 'A 380ps 9.5mW Josephson 4-Kbit RAM operating at a high bit yield,' IEEE Trans. Appl. Supercond , 5 (1995) 2447.
85. S. Tahara, I. Ishida, Y. Ajisawa, and Y. Wada, 'Experimental vortex nondestructive read-out Josephson memory cell,' J. Appl. Phys . 65 (1989) 851-856.
86. O.A. Mukhanov, 'Rapid Single Flux Quantum (RSFQ) shift register family,' IEEE Trans. Appl. Supercond . 3 (1993) 2578-2581.

transition

87. O. Mukhanov, S. Polonsky, V. Semenov, 'New Elements of the RSFQ logic family,' IEEE Trans. Mag. 27 (1991) 2435-2438.
88.    P.-F. Yuh, 'Testing a 4-b shift register at 11 GHz,' IEEE Trans. Appl. Supercond. 2 (1992), 101-105.
89. O.A. Mukhanov, 'RSFQ 1024-bit shift register for acquisition memory,' IEEE Trans. Appl. Supercond. 3 (1993) 3102-3113.
90. P. Bunyk, and P. Litskevitch, 'Case study in RSFQ design: Fast pipelined parallel adder,' IEEE Trans. Appl. Supercond . 9 (1999) 3714-3720.
91. O. Mukhanov, 'Design and test of RSFQ full adders,' Exten. Abs of 4 th Intl. Supercond. Electr. Conf ., Boulder, CO (1993) 19-20.
92. O. Mukhanov, S. Rylov, V. Semenov, and S. Vyshenskii, 'RSFQ logic arithmetic,' IEEE Trans. Mag . 25 (1989) 857-860.
93. S.  Kaplan  and  O.  Mukhanov,  'Operation  of  a  superconductive  demultiplexer  using  rapid single flux quantum (RSFQ) technology,' IEEE Trans.Appl. Supercond . 5 (1995) 2853-2856.
94. A.  Kirichenko  and  O.  Mukhanov,  'Implementation  of  novel  'push-forward'  RSFQ  carrysave serial adders,' IEEE Trans. Appl Supercond. 5 (1995) 3010-3013.
95. S. Polonsky, J. Lin, and A. Rylyakov, 'RSFQ arithmetic for DSP applications,' IEEE Trans. Appl. Supercond . 5 (1995) 2823-2826.
96. S. Martinet, D. Brock, M. Feldman, and M. Bocko, 'Functional Testing of RSFQ Circuits,' IEEE Trans Appl. Supercond . 5 (1995) 3006-3010.
97. S.  Polonsky,  V.  Semenov,  and  A.  Kirichenko,  'RSFQ  Bi-flip-flop  and  its  possible applications,' Exten. Abs.4 th Intl. Supercond. Electr. Conf. Boulder, CO (1993) 106-107.
98. S.  Polonsky,  V.  Semenov,  and  A.  Kirichenko,  'Single  flux,  quantum  B  flip-flip  and  its possible applications,' IEEE Trans. Appl. Supercond. 4 (1994) 9-18.
99.    O. A. Mukhanov and A. F. Kirichenko, 'Implementation of a FFT radix 2 butterfly using serial RSFQ multiplier-adders,' IEEE Trans. Appl. Supercond . 5 , (1995) 2461-2464.
100.   A. Kirichenko and O. Mukhanov, and A. Ryzhikh, 'Advanced on-chip test technology for RSFQ circuits,' IEEE Trans. Appl. Supercond. 7 (1997) 3438-3441.
101.   A. Pance, J.S. Martens, A. Barfknecht, J.E. Fleischman, K.E. Kihlstrom, and S.R. Whiteley, 'High  performance  RSFQ  shift  register  for  the  10  GHz  hybrid  superconducting  digital system,' Exten. Abs.4 th Intl. Supercond. Electr. Conf. , Boulder, (1993) 104-105.
102.   T. Hendricks, M. Bruns, and E. Hershberg, 'Thermal transport and electrical dissipation in ultra-low thermal load, multi-Gigahertz I/O cables for superconducting microelectronics,' in P.  Kittel  (ed.),  Advances  in  Cryogenic  Engineering  Vol.  41A ,  Plenum  Press,  New  York (1996) 1761.
103.   O.A. Mukhanov, S.V. Rylov, V.K. Semenov, and S.V. Vyshenskii, 'R ecent development of Rapid Single Flux Quantum (RSFQ) logic digital devices,' Exten. Abs.of 2 nd Intl. Supercond. Electr. Conf. Tokyo,  (1989) 557-560.
104.  S.  Rylov,  'DC-powered  high-voltage  driver  for  RSFQ  logic  family,' Exten. Abs.4 th   Intl. Supercond. Electr. Conf. , Boulder, CO (1993) 110-111.
105.   J. Przybysz, D. Miller, S. Martinet, et al., 'Interf ace circuits for chip-to-chip data transfer at GHz rates,' IEEE Trans. Appl. Supercond. 7 (1997) 2657-2660.
106.   R. Koch, P. Ostertag, E. Crocoll, et al., 'A NRZ-Output amplifier for RSFQ Circuits' IEEE Trans. Appl. Supercond . 9 (1999) 3549-3552.
107.   D.F.  Schneider,  J.C.  Lin,  S.V.  Polonsky,  and  V.K.  Semenov,  'Broadband  interfacing  of superconducting  digital  systems  to  room  temperature  electronics,' IEEE  Trans.  Appl. Supercond. 5 (1995) 3152-3155.

108. B. Van Seghbroeck, 'Optical data communications between Josephson junction circuits and room-temperature electronics.' IEEE Trans. Appl. Supercond. 3 (1993) 2881-2884.
109.   L.  Bunz,  E.  Track,  S.  Rylov,  et  al.,  'Fiber-optic  input  and  output  for  superconducting circuits,' Proc. SPIE 2160 (1994) 229-235.
110.   M. Currie, R. Sobolewski, and T. Hsiang, 'Subpicosecond measurements of the response of Josephson transmission lines to large current pulses,' IEEE Trans. Appl. Supercond. 9 (1999) 3531-3534.
111.   M.  Currie,  R.  Sobolewski,  and  T.  Hsiang,  'High-frequency  crosstalk  in  superconducting microstrip waveguide interconnects,' IEEE Trans. Appl. Supercond. 9 (1999) 3602-3605.
112.   H. Jones and D. Herrell 'The characteristics of chip-to-chip signal propagation in a package suitable for superconducting circuits,' IBM J. Res. Dev. 24 (1980) 172-177.
113.   T.  Ogashiwa,  H.  Nakagawa,  H.  Akimoto,  et  al.  'New  flip-chip  bonding  technology  for superconducting IC,' Jap. J. Appl. Phys. 31 (1992) L36-L38.
114.   S. Tanahasi, T. Kubo, K. Kawabata, et al. 'Superconducting wring in multi-chip module for Josephson LSI circuits,' Jap. J. Appl. Phys . 32 (1993) L898-L900.
115.   T. Ogashiwa, H. Nakagawa, H. Akimoto, et al. 'Flip-chip bonding using superconducting solder bump,' Jap. J. Appl. Phys . 34 (1995) 4043-4046.
116.   R. Sandell, G. Akerling, and A. Smith 'Multi-chip packaging for high-speed superconductive circuits,' IEEE Trans. Appl. Supercond. 5 (1995) 3160-3163.
117.   L.  Abelson,  R.  Elmadjian,  G.  Kerber,  and  A.  Smith  'Superconductive  multi-chip  module process for high speed digital applications,' IEEE Trans. Appl. Supercond. 7 (1997) 26272629.
118.   M. Aoyagi, H. Nakagawa H. Sato, et al. 'Superconducting flip-chip bonding method with a µm-scale gap,' Extend. Abs of 7th Inter.Supercond. Electr. Conf. Berkeley, CA (1999) 323325.
119.  M. M aezawa, H. Yamamori, and A. Shoji 'A novel approach to chip-to-chip communication using a single flux quantum pulse,' IEEE Trans. Appl. Supercond. 9 (1999) 4049-4052
120.   M. M aezawa, H. Yamamori, and A. Shoji, 'Chip-to-chip communication using a single flux quantum pulse,' IEEE Trans. Appl. Supercond. 10 (2000) 1603-1605.
121.   G. Lehmann, J. Ramsden, J. Sochor, and G. Beek, 'Cryopackaging for real world products,' in P. Kittel (ed.), Advances in Cryogenic Engineering Vol. 43A , Plenum Press, New York (1998) 865-24.
122.   T.  Clynne,  'Packaging  and  integration  issues  for  cryoelectronic  and  superconductor materials,' in P. Kittel (ed.), Advances in Cryogenic Engineering Vol. 43A , Plenum Press, New York (1998) 871-880.
123.   D. Gaidarenko and R. Robert azzi 'High performance packaging system for superc onducting electronics,' IEEE Trans. Appl. Supercond . 9 (1999) 3668-3671.
124.  E. Hershberg, T. Hendricks, and D. Patelzick, 'A fully functional closed cycle cryosystem, that uses less than one watt of refrigeration at 4.5 K, for a 2.5 GHz per channel, 128x128 channel superconducting switch,' in P. Kittel (ed.), Advances in Cryogenic Engineering Vol. 43, Plenum Press, New York (1998) 881-888.
125.   N. Dubash, V. Borzenets, Y. Zhang, et al., 'System Demonstration of a multigigabit network switch,' IEEE Trans. Micro. Theor. Techni. 48 (2000) 1209-1215.
126.   D. Gupta, D. V. Gaidarenko, and S. V. Rylov, 'A 16-bit Serial Analog-to-Digital Converter Module with Optical Output,' IEEE Trans. Appl. Supercond . 9 (1999) 3030-3033.

127. Gupta, S. V. Rylov, and D. V. Gaidarenko, 'High-resolution superconductive serial analogto-digital converter for on-focal plane data conversion,' in B. Pain (ed.), Infrared Readout Electronics IV , SPIE, Bellingham, WA, 3360 (1998) 28-39.
128.   T. Van Duzer, 'Superconductor Electronics, 1986-1996,' IEEE Trans. Appl. Supercond. 7 (1997) 98-111.
129.   A. Silver, 'Superconductivity in Electronics,' IEEE Trans. Appl. Supercond. 7 (1997) 69-79.
130.   M. Feldman, 'Digital applications of Josephson junctions,' in H. Ohta and C. Ishii (eds.), Physics and Application of Mesoscopic Josephson Junctions , Phys. Soc. Jap., Tokyo (1999) 289-304.
131.   M.  Dorojevets,  P.  Bunyk,  D.  Zinoviev  and  K.  Likharev  'COOL-0:  Design  of  an  RSFQ subsystem for petaflops computing,' IEEE Trans. Appl. Supercond. 9 (1999) 3606-3614.
132.   L. Wittie, D. Zinoviev, G. S azaklis, and K. Likharev 'CNET: Design of an RSFQ switching network for petaflops-scale computing,' IEEE Trans. Appl. Supercond. 9 (1999) 4034-4039.
133.   A.  Kidiyarova-Shevchenko  and  D.  Zinoviev,  'RSFQ  pseudo  random  generator  and  its possible applications,' IEEE Trans. Appl. Supercond. 5 (1995) 2820-2822.
134.   J. Kang, H. Worsham, and J. Przybysz, '4.6 GHz shift register and SFQ pseudorandom bit sequence generator,' IEEE Trans. Appl. Supercond. 5 (1995) 2827-2830.
135.   J. Kang, J.Przybysz, S. Martinet, et al., '3.69 GHz single flux quantum pseudorandom bit sequence generator fabricated with Nb/AlO x /Nb,' IEEE Trans. Appl. Supercond. 7 (1997) 2673-2676.
136.   P.  Dresselhaus,  E.  Dean,  H.  Worsham,  et  al,  'Modulation  and  demonulation  of  2  GHz pseudo random binary sequence using SFQ digital circuits,' IEEE Trans. Appl. Supercond. 9 (1999) 3585-3589.
137.   R. Sandell, J. Spargo, and M. Leung, 'High data rate switch with amplifier chip,' IEEE Trans. Appl. Supercond. 9 (1999) 2985-2988.
138.   J. Przybysz, Sr., 'Applications of Josephson electronics in digital systems,' in H. Weinstock (ed.),  Applications  of  Superconductivity ,  Kluwer  Academic  Publishers,  Dordrecht  (2000) 229-246.
139.   H. Worsham, A. Miklich, D. Miller, J. Kang, and J. Przybysz, 'Single flux quantum circuits for 2.5 Gbps data switching,' IEEE Trans. Appl. Supercond. 7 (1997) 2476-2479.
140.   D.  Zinoviev  and  K.  Likharev,  'Feasibility  study  of  RSFQ  based self-routing nonblocking digital switches,' IEEE Trans. Appl. Supercond. 7 (1997) 3155-3163.
141.   For a good overview, see the special issues on Software Defined Radio of: IEEE J. Selec. Areas  in  Comm. 17 (April  1999); IEEE  Comm.  Mag. 33 (May  1995)  and IEICE  Trans. Comm . E83-B (June 2000).
142.   E. Wikborg, V. Semenov, and K. Likharev, 'RSFQ front-end for a software radio r eceiver' IEEE Trans. Appl. Supercond . 9 (1999) 3615-3618.
143.   S.  Pagano,  V.  Palmieri,  A.  Esposite,  O.  Mukhanov,  and  S.  Rylov,  'First  realization  of  a tracking detector for high energy physics experiments based on Josephson digital readout circuitry,' IEEE Trans. Appl. Supercond. 9 (1999) 3628-3631.
144.   S. Pagano, R. Cristano, L. Frunzio, V. Palmieri, et al. 'Effect of intense proton radiation on properties of Josephson junctions,' IEEE Trans Appl. Supercond . 7 (1997) 2917-2920.
145.   S. Pagano, L. Frunzio, R. Cristano, O. Mukahanov, et al., 'Radiation hardness of Josephson junctions and superconductive digital devices,' Extnd. Abs. Of 6 th Intl. Superoncd. Electr. Conf. Berlin, Germany (1997) 269-271.
146.   O. Mukhanov and S. Rylov, 'Time-to-digital converters based on RSFQ digital counters,' IEEE Trans. Appl. Supercond. 7 (1997) 2669-2672.

147.   O. Mukhanov, A. Kirichenko, and J. Vogt, and M. Pambianchi, 'A superconductive multi-hit time digitizer,' IEEE Trans. Appl. Supercond. 9 (1999) 3619-3622.
148.   D.  Brock  and  O.  Mukhanov  and  A.  Rylyakov,  'Advanced  r eceive  com ponents: A 50-ps resolution  multi-hit  time-to-digital  converter  and  4  GHz  digital  correlator/autocorrelator,' Gov. Microcir. App. Conf. Dig. Pap 24 (1999) 416-419.
149.   A.  Rylyakov,  D.  Schneider,  and  Yu.  Polyakov,  'A  fully  integrated  16-channel  RSFQ autocorrelator operating at 11 GHz,' IEEE Trans. Appl. Supercond . 9 (1999) 3623-3627.
150.   A. Rylyakov and K. Likharev, 'Pulse jitter and timing errors in RSFQ circuits,' IEEE Trans. Appl. Supercond. 9 (1999) 3539-3544.
151.   H.J.M. ter Brake, 'Cryogenic systems for superconducting devices,' in H. Weinstock (ed.), Applications of Superconductivity , Kluwer Academic Publishers, Dordrecht (2000).
152. Conference  Proceedings  of Superconducting  Digital  Circuits  and  Systems  Vol.  1  &amp;  2 , Institute for Technology and Strategic Research, George Washington University (1991).
153.   G. Walker, Cryocoolers Part 1: Fundamentals , Plenum Press, New York (1983).
154.   W. Burt and C. Chan, 'New mid-size high efficiency pulse tube coolers,' in R. Ross Jr. (ed.), Cryocoolers 9 , Plenum Press, New York (1997) 173-182.
155.   H.Yoshimura, et al.,'Helium liquefaction by a Gifford-McMahon cycle refrigerator,' Rev. Sci. Instrum . 60 (1989) 3533-3536.

cryogenic

156.   I. Takashi, N. Masashi, N. Kouki, and Y. Hideto, 'Development of a 2W class 4 K GiffordMcMahon cycle cryocooler,' in R. Ross Jr. (ed.), Cryocoolers 9 , Plenum Press, New York (1997) 617-626.
157.   E. Tward, C. Chan, J. Raab, and R. Orsini, 'Miniature long-life sp ace qua ied pulse tube cryocooler,' SAE Technical Paper #941622, SAE International, Warrendale, PA. (1994)
158.   B. Jones, S. Scull, and C. Jewell, 'The batch manufacture of Stirling-cycle coolers for sp ace applications  including  test,  qualification,  and  integration  issues,'  in  R.  Ross  Jr.  (ed.), Cryocoolers 9 , Plenum Press, New York (1997) 59-68.
159.  D. Brock, E. Track, and J. Rowell, 'Superconductor ICs: The 100 GHz second generation,' IEEE Spectrum 37 (Dec. 2000) 41-46.