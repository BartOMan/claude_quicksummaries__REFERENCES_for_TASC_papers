Serial Biasing Technique for Rapid Single Flux Quantum Circuits

Ashish Shukla

Submitted in partial fulfillment of the requirements for the degree of Doctor of Philosophy under the Executive Committee of the Graduate School of Arts and Sciences

COLUMBIA UNIVERSITY

2023

© 2023 Ashish Shukla All Rights Reserved

## Abstract

## Serial Biasing Technique for Rapid Single Flux Quantum Circuits Ashish Shukla

Superconductor  electronics  based  on  the  Single  Flux  Quantum  (SFQ)  technology  are considered a strong contender for the 'beyond CMOS' future of digital circuits because of the high speed and low power dissipation associated with them. In fact, digital operations beyond tens of GHz have been routinely demonstrated in the SFQ technology. These circuits have widespread applications such as high-speed analog-to-digital conversion, digital signal processing, high-speed computing,  and  in  emerging  topics  such  as  control  circuitry  for  superconducting  quantum computing.

Rapid Single Flux Quantum (RSFQ) circuits have emerged as a promising candidate within the SFQ technology, with information encoded in picosecond wide, milli-volt voltage pulses. As is  the  case  with  any  integrated  circuit  technology,  scalability  of  RSFQ  circuits  is  essential  to realizing their applications. These circuits, based on the Josephson junction, require a DC bias current  for  the  correct  operation.  The  DC  bias  current  requirement  increases  with  circuit complexity,  and  this  has  multiple  implications  on  circuit  operation.  Large  currents  produce magnetic fields that can interfere with logic operation. Furthermore, the heat load delivered to the superconducting  chip  also  increases  with  current  which  could  result  in  the  circuit  becoming 'normal' and not superconducting. These problems make reduction of the bias current necessary.

Serial Biasing (SB) is a bias current reduction technique, that has been proposed in the past. In this technique, a digital circuit is partitioned into multiple identical islands and bias current is provided to each island in a serial manner. While this scheme is promising, there are multiple challenges such as design of the driver-receiver pair circuit resulting in robust and wide operating bias margins, current management on the floating islands, etc.

This  thesis  investigates  SB  in  a  systematic  manner,  focusing  on  the  design  and measurement of the fundamental components of this technique with an emphasis on reliability and scalability.  It  presents  works  on  circuit  techniques  achieving  high  speed  serially  biased  RSFQ circuits  with  robust  operating  margins  and  the  experimental  evidence  to  support  the  ideas.  It develops a framework for serial biasing that could be used by electronic design tools to automate design and synthesis of complex RSFQ circuits. It also investigates Passive Transmission Lines (PTLs) for use as passive interconnects between library cells in a complex design, reducing the DC bias current required by the active circuitry.

## Table of Contents

| List of Figures........................................................................................................................... vi   | List of Figures........................................................................................................................... vi   | List of Figures........................................................................................................................... vi   |
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| List of Tables......................................................................................................................... xvii    | List of Tables......................................................................................................................... xvii    | List of Tables......................................................................................................................... xvii    |
| Acknowledgments....................................................................................................................xix          | Acknowledgments....................................................................................................................xix          | Acknowledgments....................................................................................................................xix          |
| Chapter 1: Introduction ...............................................................................................................1        | Chapter 1: Introduction ...............................................................................................................1        | Chapter 1: Introduction ...............................................................................................................1        |
| 1.1                                                                                                                                             | Overview.....................................................................................................................1                  | Overview.....................................................................................................................1                  |
| 1.2                                                                                                                                             | Fundamentals of Superconductivity .............................................................................2                                | Fundamentals of Superconductivity .............................................................................2                                |
| 1.3                                                                                                                                             | Josephson Junctions.....................................................................................................4                       | Josephson Junctions.....................................................................................................4                       |
|                                                                                                                                                 | 1.3.1                                                                                                                                           | Basic Operation of a Josephson Junction..............................................................4                                          |
|                                                                                                                                                 | 1.3.2                                                                                                                                           | Circuit Model and Dynamics of Josephson Junctions ...........................................5                                                  |
|                                                                                                                                                 | 1.3.3                                                                                                                                           | Superconducting Quantum Interference Device (SQUID) ....................................8                                                       |
| 1.4                                                                                                                                             | Rapid Single Flux Quantum Circuits............................................................................9                                 | Rapid Single Flux Quantum Circuits............................................................................9                                 |
|                                                                                                                                                 | 1.4.1                                                                                                                                           | Single Flux Quantum (SFQ) Pulses......................................................................9                                         |
|                                                                                                                                                 | 1.4.2                                                                                                                                           | Josephson Transmission Line (JTL) ...................................................................10                                         |
|                                                                                                                                                 | 1.4.3                                                                                                                                           | D Flip Flop ........................................................................................................13                          |
| 1.5                                                                                                                                             | Applications and Challenges of RSFQ circuits...........................................................14                                       | Applications and Challenges of RSFQ circuits...........................................................14                                       |
| 1.6                                                                                                                                             | Prior Work on Serial Biasing .....................................................................................16                            | Prior Work on Serial Biasing .....................................................................................16                            |
| 1.7                                                                                                                                             | Contributions of this Thesis .......................................................................................18                          | Contributions of this Thesis .......................................................................................18                          |
|                                                                                                                                                 | 1.7.1                                                                                                                                           | Current Management Techniques for Serially Biased RSFQ circuits ..................18                                                            |
|                                                                                                                                                 | 1.7.2                                                                                                                                           | Driver-Receiver Pair (DRP) Circuit for Serial Biasing........................................18                                                 |
|                                                                                                                                                 | 1.7.3                                                                                                                                           | Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits ..19                                                                 |
|                                                                                                                                                 | 1.7.4                                                                                                                                           | Passive Transmission Lines for Serially Biased RSFQ Circuits ..........................20                                                       |

| 1.8                                                                                                                                              | Organization of the thesis ..........................................................................................21                          | Organization of the thesis ..........................................................................................21                          |                                                                                        |
|--------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Chapter 2: Pulse Interfaces and Current Management Techniques for Serially Biased RSFQ                                                           | Chapter 2: Pulse Interfaces and Current Management Techniques for Serially Biased RSFQ                                                           | Chapter 2: Pulse Interfaces and Current Management Techniques for Serially Biased RSFQ                                                           | Chapter 2: Pulse Interfaces and Current Management Techniques for Serially Biased RSFQ |
| Circuits .....................................................................................................................................23 | Circuits .....................................................................................................................................23 | Circuits .....................................................................................................................................23 |                                                                                        |
| 2.1                                                                                                                                              | Introduction...............................................................................................................23                    | Introduction...............................................................................................................23                    |                                                                                        |
| 2.2                                                                                                                                              | Grapevine Approach..................................................................................................26                           | Grapevine Approach..................................................................................................26                           |                                                                                        |
|                                                                                                                                                  | 2.2.1 General Grapevine Biasing Design.....................................................................26                                    | 2.2.1 General Grapevine Biasing Design.....................................................................26                                    |                                                                                        |
|                                                                                                                                                  | 2.2.2 Going Through a Hole in the Ground Plane........................................................28                                         | 2.2.2 Going Through a Hole in the Ground Plane........................................................28                                         |                                                                                        |
|                                                                                                                                                  | 2.2.3 Example Circuits and DRP Design.....................................................................29                                     | 2.2.3 Example Circuits and DRP Design.....................................................................29                                     |                                                                                        |
| 2.3                                                                                                                                              | Testing of the DDF Circuit ........................................................................................30                            | Testing of the DDF Circuit ........................................................................................30                            |                                                                                        |
|                                                                                                                                                  | 2.3.1 Test Structure Design.........................................................................................30                           | 2.3.1 Test Structure Design.........................................................................................30                           |                                                                                        |
|                                                                                                                                                  | 2.3.2 DDF Test Results...............................................................................................32                          | 2.3.2 DDF Test Results...............................................................................................32                          |                                                                                        |
| 2.4                                                                                                                                              | Testing of 3x3 Matrix of 3-to-2 Counters...................................................................34                                    | Testing of 3x3 Matrix of 3-to-2 Counters...................................................................34                                    |                                                                                        |
|                                                                                                                                                  | 2.4.1 Test Structure Design.........................................................................................34                           | 2.4.1 Test Structure Design.........................................................................................34                           |                                                                                        |
|                                                                                                                                                  | 2.4.2 Test Results .......................................................................................................35                     | 2.4.2 Test Results .......................................................................................................35                     |                                                                                        |
| 2.5                                                                                                                                              | Discussion .................................................................................................................40                   | Discussion .................................................................................................................40                   |                                                                                        |
| 2.6                                                                                                                                              | Conclusions ...............................................................................................................41                    | Conclusions ...............................................................................................................41                    |                                                                                        |
| Chapter 3: 60-GHz Single Flux Quantum Pulse Transfer Circuit for Serial Biasing...................43                                             | Chapter 3: 60-GHz Single Flux Quantum Pulse Transfer Circuit for Serial Biasing...................43                                             | Chapter 3: 60-GHz Single Flux Quantum Pulse Transfer Circuit for Serial Biasing...................43                                             |                                                                                        |
| 3.1                                                                                                                                              | Introduction...............................................................................................................43                    | Introduction...............................................................................................................43                    |                                                                                        |
| 3.2                                                                                                                                              | Driver-Receiver Pair..................................................................................................46                         | Driver-Receiver Pair..................................................................................................46                         |                                                                                        |
|                                                                                                                                                  | 3.2.1                                                                                                                                            | Schematic, Layout, and Cross-Section................................................................46                                           |                                                                                        |
|                                                                                                                                                  | 3.2.2                                                                                                                                            | Simulation Results .............................................................................................48                               |                                                                                        |

|                                                                                                  | 3.2.2                                                                                                                          | DRP Test Structures...........................................................................................50               |                                                                                                |
|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| 3.3                                                                                              | Test Results ...............................................................................................................51 | Test Results ...............................................................................................................51 |                                                                                                |
| 3.4                                                                                              | EM Simulations.........................................................................................................57      | EM Simulations.........................................................................................................57      |                                                                                                |
|                                                                                                  | 3.4.1                                                                                                                          | Simulating the DRP Test Structure.....................................................................57                       |                                                                                                |
|                                                                                                  | 3.4.2                                                                                                                          | Current Distribution in the Source and Drain Vias..............................................61                              |                                                                                                |
|                                                                                                  | 3.4.3                                                                                                                          | Simulating Position of Drain vias in the GVBiasing Case..................................65                                    |                                                                                                |
|                                                                                                  | 3.4.4                                                                                                                          | Simulating M6 Extension over M4-to-M5 Vias..................................................68                                 |                                                                                                |
| 3.5                                                                                              | Discussion .................................................................................................................71 | Discussion .................................................................................................................71 |                                                                                                |
|                                                                                                  | 3.5.1                                                                                                                          | Model-to-Hardware Correlation .........................................................................71                      |                                                                                                |
|                                                                                                  | 3.5.2                                                                                                                          | 80-Island Experiment and Future Steps ..............................................................76                         |                                                                                                |
| 3.6                                                                                              | Conclusion.................................................................................................................78  | Conclusion.................................................................................................................78  |                                                                                                |
| Chapter 4: Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits ........79 | Chapter 4: Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits ........79                               | Chapter 4: Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits ........79                               |                                                                                                |
| 4.1                                                                                              | Introduction...............................................................................................................79  | Introduction...............................................................................................................79  |                                                                                                |
| 4.2                                                                                              | Design Primitives Required for Serial Biasing ...........................................................81                    | Design Primitives Required for Serial Biasing ...........................................................81                    |                                                                                                |
|                                                                                                  | 4.2.1                                                                                                                          | Grapevine Biasing for the MIT-LL SFQ5ee Fabrication Node ...........................82                                         |                                                                                                |
|                                                                                                  | 4.2.2                                                                                                                          | DRP's Core Design............................................................................................83                |                                                                                                |
|                                                                                                  | 4.2.3                                                                                                                          | Horizontal and Vertical Bias JTLs......................................................................85                      |                                                                                                |
|                                                                                                  | 4.2.4                                                                                                                          | Horizontal and Vertical Composite DRPs...........................................................87                            |                                                                                                |
| 4.3                                                                                              | Assembling a Serially Biased Circuit .........................................................................90               | Assembling a Serially Biased Circuit .........................................................................90               |                                                                                                |
|                                                                                                  | 4.3.1                                                                                                                          | Blocks Required.................................................................................................90             |                                                                                                |
|                                                                                                  | 4.3.2                                                                                                                          | Test Circuit Design                                                                                                            | ............................................................................................92 |

| 4.4                                                                                                       | Measurement Results.................................................................................................94        | Measurement Results.................................................................................................94        |
|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                           | 4.4.1                                                                                                                         | Horizontal and Vertical CDRPs..........................................................................94                     |
|                                                                                                           | 4.4.2                                                                                                                         | Comparing Independently Tested Experiments...................................................96                               |
|                                                                                                           | 4.4.3                                                                                                                         | Crosstalk Experiments .......................................................................................99               |
|                                                                                                           | 4.4.4                                                                                                                         | Different Wafer Locations................................................................................102                  |
| 4.5                                                                                                       | Electromagnetic Simulations....................................................................................104            | Electromagnetic Simulations....................................................................................104            |
|                                                                                                           | 4.5.1                                                                                                                         | 2-island CDRP Simulation ...............................................................................104                   |
|                                                                                                           | 4.5.2                                                                                                                         | Simulating Vertical M0 Extension over M4-to-M1 Vias...................................109                                     |
|                                                                                                           | 4.5.3                                                                                                                         | Simulating Horizontal M0 and M1 Extensions over M1-to-M0 vias.................111                                             |
|                                                                                                           | 4.5.4                                                                                                                         | Double Current Injection..................................................................................113                 |
| 4.6                                                                                                       | Discussion ...............................................................................................................115 | Discussion ...............................................................................................................115 |
| 4.7                                                                                                       | Conclusion...............................................................................................................118  | Conclusion...............................................................................................................118  |
| Chapter 5: Passive Transmission Lines for Serially Biased RSFQ Circuits ..............................119 | Chapter 5: Passive Transmission Lines for Serially Biased RSFQ Circuits ..............................119                     | Chapter 5: Passive Transmission Lines for Serially Biased RSFQ Circuits ..............................119                     |
| 5.1                                                                                                       | Introduction.............................................................................................................120  | Introduction.............................................................................................................120  |
| 5.2                                                                                                       | PTL Characterization...............................................................................................122        | PTL Characterization...............................................................................................122        |
|                                                                                                           | 5.2.1                                                                                                                         | Electromagnetic simulations to establish PTL width.........................................122                                |
|                                                                                                           | 5.2.2                                                                                                                         | PTL Receiver Bias Margins as a function of Impedance...................................124                                    |
|                                                                                                           | 5.2.3                                                                                                                         | Receiver Bias Margins for the 2 PTL architectures...........................................125                               |
| 5.3                                                                                                       | PTL Circuit Simulations ..........................................................................................126         | PTL Circuit Simulations ..........................................................................................126         |
|                                                                                                           | 5.3.1                                                                                                                         | Adoption of Multi-Layer Transmission Line Model for PTLs ..........................126                                        |
|                                                                                                           | 5.3.2                                                                                                                         | Model to Hardware Correlation........................................................................129                      |
| 5.4                                                                                                       | Conclusion...............................................................................................................131  | Conclusion...............................................................................................................131  |

Conclusion  ..............................................................................................................................  132

## References ..............................................................................................................................  135

## List of Figures

| 1.1   | Resistance drops to zero below the critical temperature (T c ) in superconductors (a). The                                                                                                                                                                                       |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.2   | Josephson junction (JJ) geometry (cross-section) shown in (a). The typical JJ symbol is shown in (b).....................................................................................................................5                                                       |
|       | RCSJ circuit model of the Josephson                                                                                                                                                                                                                                              |
| 1.3   | junction..................................................................6                                                                                                                                                                                                      |
| 1.4   | The hysteretic I-V characteristic for the underdamped JJ which has  c >>1. A non-                                                                                                                                                                                               |
| 1.5   | DC SQUID comprising superconducting loop interrupted by JJs J1 and J2. .....................8                                                                                                                                                                                    |
| 1.6   | Josephson Transmission Line comprising 4 junctions with  c ~ 1 and inductors for                                                                                                                                                                                                |
| 1.7   | interconnections. Upon receiving an SFQ voltage pulse as an input, the JJs switch in the order JA1-JA2-JA3-JA4, and then the pulse exits the JTL circuit...................................11 (a) RSFQ D Flip-Flop (DFF) block diagram showing the input output connections. (b) |
|       | Presence of a pulse in a clock window is interpreted as logic '1', the absence is a '0'. Note the clock-to-data out delay between the SFQ pulses. The circuit schematic of the DFF is                                                                                            |
| 2.1   | (a) Parallel Bias (PB) versus (b) Serial Bias (SB)...........................................................25                                                                                                                                                                  |
| 2.2   | Straightforward (a) versus Grapevine Approach (b) for MIT-LL SFQ5ee metal stack (c).                                                                                                                                                                                             |
|       | Black and white arrows are used to depict bias current and return current respectively...26                                                                                                                                                                                      |

| 2.3   | Straightforward (a) versus Grapevine Approach (b) for going through a hole in the ground plane for MIT-LL metal layers stack (c). Not all layers are shown in (d) and (e) to simplify                                                                                                   |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 2.4   | Chip layout consisting of the PB, SB1, and SB4 test structures (see text for details). The chip was fabricated at MIT-LL using SFQ5ee 10 kA/2  fab node.................................31                                                                                             |
| 2.5   | Test structure consisting of 4 serially biased DDF slices on 4 islands (SB4)...................32                                                                                                                                                                                       |
|       | Block diagram of the serially biased 3x3 matrix of 3-to-2 counters. The MSB output of the                                                                                                                                                                                               |
| 2.7   | 1st 3-to-2 circuit is split in two and provided to two of the unweighted inputs of the subsequent 3-to-2 circuit. Similar MSB splitting is observed for the 3rd in a row 3-to-2                                                                                                         |
| 2.8   | LF Serial Bias Margins for 7 input patterns, for all rows tested one at a time. The input (for e.g., '001') is addressed as 'Top (T)' 'Middle (M)' 'Bottom (B)' in reference to the physical                                                                                            |
|       | layout location of the inputs on the 3-to-2 circuit (compare with Figure 2.7)..................36 BER versus serial bias current for the '100' input pattern. Frequency is swept from 1 GHz to 50 GHz. Operational margins do not depend strongly on the clock frequency. ...........37 |
| 2.9   |                                                                                                                                                                                                                                                                                         |
| 2.10  | BER versus serial bias current for the '101' input pattern. Frequency is swept from 1 GHz to 50                                                                                                                                                                                         |
|       | GHz......................................................................................................................38                                                                                                                                                             |
| 2.11  | BER versus serial bias current for the '111' input pattern. Frequency is swept from 1 GHz                                                                                                                                                                                               |

|   2.12 | BER versus serial bias current for the '111' input pattern for simultaneous operation mode                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   2.13 | BER versus serial bias current for the '001' input pattern for simultaneous operation mode at 50 GHz......................................................................................................................39                                                                                                                                                                                                                                                                                                                                                                                              |
|   3.1  | (a) The grapevine (GV) biasing technique is implemented on two serially biased islands using (d) the MIT-LL SFQ5ee metal layers' stack. Any bias-line-in has a dedicated ground- line-out to localize the magnetic fields in between the two metal layers and control the return current distribution. The dedicated pair of metal paths for current transfer through                                                                                                                                                                                                                                                     |
|   3.2  | (a) The DRP schematic (a) comprises the driver's junctions on ground Aand the receiver's junctions on ground B: JA1=250  A, JA2=350  A, JA3=488  A, JA4=158  A, JB1=94  A, JB2=131  A, IA1=175  A, IA2=245  A, IA3=344  A, IB1=71  A, IB2=100  A, LA1=2pH, LA2=2.7pH, LA3=2.1pH, LB1=2.7pH, LP=LS=5.8pH, and k=0.53. The DRP layout (b) is shown for MIT-LL SFQ5ee fab node. The shown layout occupies the area of 40  m x 65  m. All inductances, including the transformer with M4 and M7 holes, were calculated using InductEx software. The simplified cross-section (c) is made along the line JA2-JA3- |
|   3.3  | (a) Simulated margins for the normalized SB current as a function of the input frequency for different configurations of DRP parameters. The 'D' margins correspond to the default set of parameters. To calculate the 'M' margins, the mutual inductances in all DRPs were                                                                                                                                                                                                                                                                                                                                               |

|     | all DRPs. The 'L' and 'R' margins are calculated for counterclockwise and clockwise flux trapped in a transformer in a single DRP. The 'B' margins correspond to two fluxes of both polarities trapped in 2 DRPs. .........................................................................................49             |
|-----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3.4 | (a) Two 5-island test structures biased according to SF (a) and GV (b) bias schemes. Both                                                                                                                                                                                                                                 |
| 3.5 | LF bias margins for the SF (red) and GV (blue) test structures across different chip locations. .......................................................................................................................52                                                                                                 |
| 3.6 | Experimental setup and block diagram of the FPGA-based Bit Error Rate Tester (BERT). The computer allows the user to start a BER measurement and visualize the BER during the experiment...............................................................................................................53                 |
| 3.7 | BER curves versus serial bias current at 10.16 GHz for the 2 biasing schemes. The GV (blue) margins are wider compared to the SF (red) case and reach the BER level of 10 - 12 . ......................................................................................................................................55 |
| 3.8 | BER curves for the GV test structure after 4 deflux procedures......................................55                                                                                                                                                                                                                    |
| 3.9 | Normalized serial bias current versus clock frequency for the GV test structure. Data are obtained by running the output waveform stability test to maintain the BER level better                                                                                                                                         |
| 3.1 | The simplified layout of (a) the 2-island SF DRPtest structure and (b) the calculated current distribution in the M4 ground plane. The bias current is injected into the first island,                                                                                                                                    |

|   3.11 | The simplified layout of (a) the 2-island GV DRP test structure and (b) the calculated current distribution in the M4 ground plane. Any metal layer used to carry the incoming current has a corresponding dedicated metal layer to carry the outgoing current as marked                                                                                                           |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   3.12 | Layouts of the serially biased island with the GV(a) and SF (b) biasing. In both cases, bias current enters and exits the island from the top and bottom (white arrows). The load circuit consists of 5 identical resistors connected to M4 ground. In contrast to the dedicated pairs of layers in theGV case (a), the metal layers for current flowing in and out do not overlap |
|   3.13 | The current density distribution in the M4 ground layer is shown for GV (a) and SF (b) biasing cases. The regions shown correspond to the dashed rectangles marked in Figure 3.12(a) and Figure 3.12(b). ............................................................................................63                                                                            |
|   3.14 | Layouts of serially biased islands with GV biasing. In (a), the drain vias are located at the edge of the hole, and in (b), they are located away from the hole at 8  m distance. ........66                                                                                                                                                                                      |
|   3.15 | The current density distribution in the M4 ground plane is shown for different locations of the drain vias in the GV biasing case. The M4-to-M0 drain vias (I-P) are moved from the hole to the edge of the M4ground (a) or placed 8  maway from the hole edge. The regions shown correspond to the dashed rectangles marked in Figures 3.14(a) and 3.14(b). .......67            |
|   3.16 | The M6 strip changes its width from 16  m to 4  m after passing the group of pickup vias with a 4  m extension (a) and 8  m extension combined with 2 chamfers (b) to let the                                                                                                                                                                                                  |

| 3.17   | The current distribution for two implementations of the GV biasing approach depicted in Figure 3.15. The return current is unequally (a) and equally (b) distributed between individual pickup vias (S-Z). The regions shown correspond to the dashed rectangles                                            |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3.18   | The SQUID-based test structures (a) and (c) are used to measure the LP and LS for the                                                                                                                                                                                                                       |
| 3.19   | DRP cross-section (a) shown with all forms of coupling between metal layers. The sign convention for counterclockwise (CCW) and clockwise (CW) flux trapping is shown in (b) and (c) respectively........................................................................................................74 |
| 3.20   | Simplified layout to calculate coupling between M4 ground hole inductor and LP, LS signal inductors of the DRP. InductEx reports a value of L M4 ~10 pH, a value in                                                                                                                                         |
|        | close agreement with a washer inductance of similar geometry reported in [73]......................74                                                                                                                                                                                                       |
|        | The divided output is seen at 1.56 GHz. This corresponds to an input frequency of 49.92                                                                                                                                                                                                                     |
| 3.22   | GHz. Increasing or decreasing the serial bias current results in an unstable waveform. ..77                                                                                                                                                                                                                 |
| 4.1    | The grapevine biasing technique implemented on 2 serially biased islands (a) for the MIT-                                                                                                                                                                                                                   |

| 4.2   | The DRP core (a) comprises driver junctions JA1-JA4 and receiver junctions JB1-JB2                                                      |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------|
|       | placed on separated grounds Aand B. JA1 = 250 µA, JA2 = 350 µA, JA3=488 µA, JA4 =                                                       |
|       | 158 µA, JB1 = 94 µA, JB2 = 131 µA, IA1 = 175 µA, IA2 = 245 µA, IA3 = 344 µA, IB1 =                                                      |
|       | 71 µA, IB2 = 100 µA, LA1 = 2 pH, LA2 = 2.7 pH, LA3 = 2.1 pH, LB1 = 2.7 pH, LP = LS                                                      |
|       | = 5.8 pH, and K = 0.53. The DRP layout (b) is shown for the MIT-LL SFQ5ee fab node.                                                     |
|       | All junctions, bias taps, input-output locations, and the M4-M7 ground moats are labeled.                                               |
|       | The cross-section along the JA2-JA3-JA4 line is shown in (c). ......................................84                                  |
| 4.3   | Layout rules for locations of input and output terminals, as well as bias taps are shown in                                             |
|       | (a). In (b), two horizontal M0 bias buses are added. Note that abutting multiple cells                                                  |
|       | horizontally would form a contiguous M0 bias line. In the horizontal bias JTL of (c), the                                               |
|       | vertical M0 bus linewidth cannot be increased beyond 5 µm due to proximity to the bias                                                  |
|       | taps. In the vertical bias JTL of (d), an M2 layer is also placed over the horizontal M1 bias                                           |
|       | line. ...............................................................................................................................86 |
| 4.4   | The horizontal CDRP layout (b) is shown for SFQ pulse flow from left to right and right                                                 |
|       | to left in the top and bottom channels respectively. The block diagram (b) shows the center                                             |
|       | region (60  m width  40  m height) where the library rules are violated. In addition to                                              |
|       | the 3 bais taps on the driver side of the DRP core, 2 more taps are required for the bias JTL                                           |
|       | and PTL Rx/Tx. Similarly, along with the 2 bias taps on the receiver side of each DRP                                                   |
|       | core, the bias JTL and PTL Tx/Rx require 2 additional taps. The connection of bias taps to                                              |
|       | the horizontal M0 bias lines is not shown.......................................................................88                      |
| 4.5   | The vertical CDRP layout is shown in (a) for SFQ pulse flow from bottom to top and top                                                  |
|       | to bottom in the left and right channels respectively. The block diagram (b) shows the                                                  |

|      | 40  m  60  m center region of the DRP with library rules violation. Vertical M0 bias                         |
|------|-----------------------------------------------------------------------------------------------------------------|
| 4.6  | Block diagram of the assembly of two serially biased DUTs. Blocks D1/D3 and D2/D4                               |
|      | comprise horizontal and vertical CDRPs respectively. Blocks B1-B6 are used to form a                            |
|      | biasing network. All blocks placed around the DUT form moats in M4 and M7. Note that                            |
|      | all blocks are placed slightly separated in the figure for easier recognition.....................91            |
| 4.7  | The test chip includes 4 serially biased DUTs with CDRPs for signal propagation. Each                           |
|      | DUT comprises JTLs and splitters from the standard cell library [6], with a total junction                      |
|      | count of 281 (including the overhead of CDRPs)...........................................................92     |
| 4.8  | Block diagram of the test circuit with the black and blue paths highlighting the SFQ pulse                      |
|      | propagation along the horizontal and vertical CDRPs. Note that the GV biasing scheme is                         |
|      | not shown here. Each LF monitor is preceded by 4 Toggle Flip-Flops (not shown)........93                        |
| 4.9  | BER versus SB current for different frequencies up to 50 GHz plotted for the horizontal                         |
|      | test structures with 5 DRPs (a), 15 DRPs (b), and 5 CDRPs connected on the island by                            |
|      | PTLs (c). The vertical test structure with 16 DRPs is depicted in (d)..............................95           |
| 4.10 | The BER curves as a function of frequency for the 5 and 15hDRPs + JTLs are compared                             |
|      | from chip location E5. Bias margins at 30 GHz and 50 GHz are compared. ...................97                    |
| 4.11 | The BER curves for the 5hDRPs with JTL and PTL interconnections are compared. Note                              |
|      | that in case of the PTL interconnections, the composite DRP is used. ............................97             |
| 4.12 | The BER curves for the '5hDRPs + JTLs' and '5hDRPs + 16vDRPs + JTLs'. At 50 GHz,                                |
|      | a 1.6% reduction in bias margins is observed.................................................................98 |

| 4.13   | The BER curves for the '5hDRPs + JTLs' with and without turning PRBS-B on. A 0.8% reduction in bias margins is observed at 50 GHz. Note no degradation in margins at lower                                                                                                                           |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 4.14   | The BER curves for the '15hDRPs + JTLs' with and without turning on PRBS-B. There is a shrinkage of 1.6% in bias margins at 50 GHz............................................................100                                                                                                    |
| 4.15   | The BER curves for the '5hCDRPs + PTLs' with and without turning on PRBS-B. There is a 1.5% bias margin shrinkage at 50 GHz..................................................................100                                                                                                     |
| 4.16   | The BER curves for the '5hDRPs + 16vDRPs + JTLs' with and without turning on PRBS-                                                                                                                                                                                                                   |
| 4.17   | The BER curves for the '5hDRPs + 16vDRPs + JTLs' and that of 'All Structures' are identical. A ±5.1% bias margin is observed in both cases, at 50 GHz...........................101                                                                                                                  |
| 4.18   | Comparing BER curves across frequency for the '5hDRPs + JTLs' experiment across 3 wafer locations: E3, E5, and E6. Note that in the E6 location, the margins shrink rapidly beyond 20                                                                                                                |
| 4.19   | GHz............................................................................................................103 Comparing BER curves for the '15hDRPs + JTLs' experiment across 3 wafer locations:                                                                                                |
| 4.20   | E3, E5, and E6. The E6 location has reduced margins across frequencies, in contrast to the similar plot for '5hDRPs + JTLs'.................................................................................103 Comparing BERcurves for the '5hDRPs + PTLs' experiment across 3 wafer locations: E3, |
| 4.21   | Comparing BER curves for the '5hDRPs + 16vDRPs + PTLs' experiment across 3 wafer                                                                                                                                                                                                                     |
|        | The single island layout (a) shows the ground moat, bias lines and taps with resistors                                                                                                                                                                                                               |
| 4.22   |                                                                                                                                                                                                                                                                                                      |

|      | seen. Components of GVbiasing, such as the M4-to-M1 and M1-to-M0 groups of vias are marked. Bias taps are labeled from A to N in (b)..........................................................105                                                                                                                                                                                                     |
|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 4.23 | Zoomed view of M4 current density around the bias taps in case of the 2-island CDRP                                                                                                                                                                                                                                                                                                                   |
| 4.24 | Zoomed view of the M4 current density around bias taps in case of the extra M1 ground plane added. Compare with Figure 4.23(a) and Figure 4.23(b).....................................107                                                                                                                                                                                                             |
|      | ....................................................................................................................................110 Layout (a) shows a 5 µm long horizontal M0/M1 extension on both sides of M1-to-M0 vias. Unequal current distribution between M1-to-M0 vias is shown in (b). The 10 µm                                                                                         |
| 4.26 | extension with chamfers (c) helps to equalize the current distribution between all vias (d).                                                                                                                                                                                                                                                                                                          |
| 4.27 | ....................................................................................................................................112 The layout (a) of the horizontal bias bus with 2 injection points (A, B) and the M1-to-M0                                                                                                                                                                     |
| 5.1  | via (D). Current distributions in layers M0 (b), M1 (c), M2 (d) and M4 (e) are shown (see text for details). ...........................................................................................................114 Metal stack of the MIT-LL SFQ5ee process showing layers for PTLs with symmetric (a) and asymmetric (b) dual ground planes. The former is used to route signals outside of |

|   5.2 | Return loss in (dB) (S11) shown in (a) for a 2-port Sonnet EM simulation for an M2-M3- M4 (symmetric) PTL with 12.5 Ω characteristic impedance. In the 3D model of the PTL                                                                                                                |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   5.3 | Receiver bias margins as a function of impedance for the M2-M3-M4 PTL. Lower impedance PTLs have higher bias margins. This result identifies the 8Ω PTL as a strong candidate for the cell library implementation. ..............................................................124      |
|   5.4 | Receiver bias margins of the M2-M3-M4 and M1-M3-M4 PTLs for 8 Ω and 10Ω impedances satisfy the margin criterion. 10 ΩPTLs have slightly reduced margins but may still be used in certain scenarios...................................................................................125  |
|   5.5 | Example of the RLGC data file generated for an 80 µm long, 8 Ω M2-M3-M4 PTL from an EMsimulation. All values are reported per meter. This file can be used to simulate much                                                                                                               |
|   5.6 | longer lengths in SPICE simulators..............................................................................128 Model to hardware correlation for the high-frequency operation of (a) M2-M3-M4 PTL and (b) M2-M3-M4 PTLs. The resonant frequencies at 35 GHz and 40 GHz for these two |

## List of Tables

| 2.1   | Ratio of Measured Total Current to Nominal for PB, SB1, and SB4 ..............................34                                         |
|-------|------------------------------------------------------------------------------------------------------------------------------------------|
| 2.2   | Serial Bias Margins for Individual Rows across 5 Input Patterns at 20 GHz...................40                                           |
| 3.1   | Current Density Distribution in SF a and GV b biasing cases............................................60                                |
| 3.2   | Current Density Distribution in Source and Drain Vias for GV a and SF b without M7 Sky                                                   |
|       | Plane .............................................................................................................................64    |
| 3.3   | Current Density Distribution in Source and Drain Vias forGV a and SF b with M7SkyPlane                                                   |
|       | ......................................................................................................................................64 |
| 3.4   | Current Density Distribution in Source and Drain Vias for Different Positions of Drain                                                   |
|       | Vias in GV Biasing case ................................................................................................68               |
| 3.5   | M4-to-M5 (Pickup Vias) Current Density......................................................................71                           |
| 3.6   | DRP Transformer Inductances (Measured versus Simulated).........................................73                                       |
| 3.7   | Mutual Inductances for weak coupling between ground holes (M4 and M7) and signal                                                         |
|       | inductors (LP and LS)....................................................................................................75              |
| 4.1   | M4 Current Density around the Bias Taps for Different Ground Plane Configurations.108                                                    |
| 4.2   | M4-to-M1 Via Current Density....................................................................................111                      |
| 4.3   | M1-to-M0 Via Current Density....................................................................................112                      |
| 5.1   | Impedance-width of PTLs for different signal and ground conductor configurations....123                                                  |
| 5.2   | The simulation time and memory requirement increases with PTL length....................127                                              |
| 5.3   | Comparison of SFQ pulse propagation time for different PTL models .........................129                                           |

- 5.4 Low-frequency model to hardware correlation between measured and simulated margins for the 8 Ω M2-M3-M4 PTL, with symmetric ground planes and the 8 Ω M1-M3-M4 PTL with asymmetric ground planes.  ...................................................................................  129

## Acknowledgments

My experience during this PhD program has been one of a steep learning curve and rigor. The body of work in this thesis is the outcome of close collaboration with and guidance of several brilliant  researchers  in  both  academia  and  industry.  This  thesis  would  have  not  been  possible without their extensive technical insight and direction. First and foremost, I would like to thank my advisor, Prof. Mingoo Seok for his continual help and support. His passion for pursuing bold research projects led me to work on the topic of this thesis. He encouraged me to explore research topics  outside  of  my  thesis  too,  which  gave  me  a  well-rounded  exposure  in  the  field.  His professionalism and research approach are qualities I hope to imbibe in my career.

I am thankful to Prof. Yannis Tsividis, Prof. Keren Bergman, Prof. Matthias Preindl, and Dr. Timur Filippov for agreeing to be part of the thesis committee. Their inputs and feedback will be invaluable for this thesis.

Much of my thesis work was done in collaboration with Dr. Timur Filippov at HYPRES. I am deeply grateful to him for providing structure and direction to my research. He guided me through multiple challenges I faced during this journey such as design errors, chips failing to work, and  understanding  complex  dynamic  phenomena  in  simulations  and  measurement,  all  while exhibiting tremendous patience. Dr. Filippov provided me with unwavering support, especially when the light at the end of the tunnel appeared bleak.

I  am also very grateful to Dr. Dmitri Kirichenko at HYPRES for helping me overcome multiple hurdles in chip design and test. I have learnt extensively from him and some of his ideas have become the backbone of this thesis. Other colleagues at HYPRES such as Anubhav Sahu, M. Eren  Çelik,  Sukanya  Meher,  Andrei  Talalaevksii,  Benjamin  Chonigman,  and  Mustapha  Habib provided me with useful technical insight and helpful advice.

Thanks are due to the Office of Naval Research (under Contract N68335-18-C-0654) and the  Intelligence  Advanced  Research  Project  Activity  (under  Contract  W911NF-17-9-0001)  for supporting my research. I thank Dr. Deborah Van Vechten of ONR, in particular, for her support and encouragement. I am also grateful to MIT Lincoln Laboratory (MIT-LL) for fabricating the chips in this thesis and to Dr. Sergey Tolpygo at MIT-LL, for productive discussions.

I would be remiss if I do not thank Dr. Deepnarayan Gupta, who inspired me to pursue a PhD. The breadth and depth of his technical expertise in the field of superconductor electronics are attributes I aspire to achieve. I thank Amol Inamdar for his guidance and helpful discussions. Beyond technical work, Amol has taught me perseverance and composure, qualities I will always cherish. I would also like to thank Erik Lehmann for his generous technical help and interactions. His skills and approach in solving complex problems are truly inspiring. Thanks are also due to Prof. Alan Kadin for stimulating discussions and help with editorial efforts.

I  am glad to have friends in Pavan Kumar Chundi, Joao Cerqueira, Bo Zhang, Zhewei Jiang, Sung Kim, Dongkwun Kim, Dewei Wang, Daniel Jang, Paul Huang, and Jeongwook Lee, my colleagues from the VLSI Design Laboratory. I am grateful for the learning and interactions I have had with them.

My parents and my elder sister have been a pillar of strength and support for me. I am indebted to them for their love and unconditional support. Lastly and most importantly, I must thank my wife, Ananya, who has been my bedrock. She has made these PhD years enjoyable with her  love,  friendship,  and  sense  of  humor. I  look forward  to  the  next  adventure  in  our  journey together.

## 1.1 Overview

In  this  Chapter,  digital  superconductor  electronics  (SCE)  is  briefly  introduced.  The fundamental properties of superconductors exploited to design electronic circuits are presented. These include zero resistance, the Meissner effect, and magnetic flux quantization. The active device in SCE, the Josephson Junction (JJ) is described next. Rapid Single Flux Quantum (RSFQ) circuits are discussed next, their operation explained by means of a Josephson Transmission Line (JTL) and a D Flip Flop. Applications of RSFQ circuits with their benefits are then elaborated upon. The  advantages  of  RSFQ  circuits  in  terms  of  dynamic  power  dissipation  and  speed  are discussed.

This Chapter also presents the challenges facing RSFQ circuits in terms of scalability and widespread adoption. It identifies major obstacles in process variations, flux trapping, and static power dissipation. This thesis investigates the DC bias current limitation problem of these circuits. The Serial Biasing (SB) circuit technique is introduced as a promising candidate to alleviate the problem of large on-chip DC bias currents. Prior work on serial biasing is discussed in detail.

Finally,  this  Chapter  discusses  the  main  contributions  of  this  thesis  in  terms  of  the development of serial biasing as a mature and scalable design technique for RSFQ circuits: Bias current management for serially biased RSFQ circuits, pulse interfaces for serially biased RSFQ circuits,  and  electronic  design  automation  techniques  for  serially  biased  RSFQ  circuits.  Using Passive  Transmission  Lines  (PTLs)  instead  of  the  Josephson  Transmission  Lines  (JTLs)  for routing  digital  circuitry,  can  significantly  reduce  bias  currents  associated  with  interconnects.

## Chapter 1: Introduction

Hence,  this  thesis  also  investigates  Passive  Transmission  Lines  (PTLs)  focusing  on  design, simulations and measurements.

## 1.2 Fundamentals of Superconductivity

Superconductivity was first discovered in 1911 [1] when it was noticed that the resistance of certain materials would drop to zero below a certain critical temperature ( Tc ) (see Figure 1.1(a)). For example, a commonly used superconductor in SCE circuits is Niobium (Nb), with a critical temperature  of  9.2 K.  The  BCS  theory  [2]  is  one  of  the  well-accepted  explanations  of  this phenomenon.  Superconductivity  is  a  macroscopic  quantum  mechanical  phenomenon  in  which electrons when cooled below the Tc , form Cooper pairs, which are 2 electrons with opposite spins. Typically, quantum states are microscopic, except in superconductors, where all the Cooper pairs in a bulk superconductor condense into the same quantum state ψ , with a common quantum phase φ .  This  remarkable property allows these paired electrons to move through the superconductor without  any  resistance.  The  resistance-less  property  of  superconductors  makes  them  very appealing in the design of lossless circuits.

The next important property, known as the Meissner effect [3], [4] is the expulsion of the magnetic field from any bulk superconductor, below the Tc , as seen in Figure 1.1(b). This property can be derived directly from the famous London equations [5] and results in the magnetic field (H) within a superconductor decreasing exponentially with depth. The superconductor does this by creating screening currents on its surface that expel any flux in its interior. These are persistent by nature due  to  the  resistance-less  property.  Superconductors  have  a  characteristic  magnetic  field penetration depth, called the London penetration depth (  L), over which the field decays by 1/e value to that at its surface.

There is a critical  H  field  ( Hc ),  above  which,  the  material  stops  superconducting  and  becomes normal.  A  critical  current  ( Ic )  corresponding  to  the Hc exists  for  a  superconductor,  a  direct consequence of the Meissner effect.

1 Figure 1.1: Resistance drops to zero below the critical temperature (Tc) in superconductors (a). The Meissner effect is illustrated in (b) where the magnetic field, below Tc is expelled from the interior of the superconductor. (c) A magnetic flux inside a superconducting loop must be quantized in modulo  0 .

<!-- image -->

The third and perhaps the most important property of superconductors for SCE applications is magnetic flux quantization ([3], [6]). The phase difference ( φ ) across a superconducting loop must be single-valued and modulo 2π due to the superconductor possessing a single quantum state ψ . In the presence of magnetic flux (  ) in a loop, applying Stoke's theorem to the magnetic flux through a loop yields Equation 1.1.

1  HYPRES presentation on Superconductor Microelectronics, 2004. https://www.wirelessinnovation.org/assets/Proceedings/2004/2004-sdr04-4-6-3ppt-rosa-presentation.pdf

<!-- formula-not-decoded -->

As seen from Equation 1.1, this property states that magnetic flux in a superconducting loop must be  quantized  in  modulo  'magnetic  flux  quantum',  0  (2.07 × 10 - 15 Wb,  see  Figure 1.1(c)). Furthermore, it also states that a phase difference of 2π across the loop corresponds to a  0 of magnetic flux threading the loop. As will be seen later, this property allows storing information in terms of  0 and thus can be used to design digital circuits.

## 1.3 Josephson Junctions

## 1.3.1 Basic Operation of a Josephson Junction

In SCE circuits, the Josephson junction (JJ), comprising a weak link contact between two superconducting electrodes, as seen in Figure 1.2(a), is the active device. The two electrodes have different quantum mechanical wave functions and phases, φ, being the phase difference between the two . In the DC Josephson effect ([3], [7]), a supercurrent comprising Cooper pairs, is observed to flow through the junction, without an applied voltage. Equation 1.2 shows the dependence of this current on the phase difference φ , across the JJ:

<!-- formula-not-decoded -->

where Ic is critical or the maximum zero voltage current in the junction. When the voltage V &gt; 0, it is related to φ , by the relationship of Equation 1.3:

<!-- formula-not-decoded -->

Upon integrating φ with respect to time and plugging this in Equation 1.1, it gives an alternating current that oscillates at the Josephson frequency ( f J ) shown in Equation 1.4. This is called the AC Josephson effect ([3], [7]). The JJ behaves like an ideal voltage-controlled oscillator for V &gt; 0.

1.4

Figure 1.2: Josephson junction (JJ) geometry (cross-section) shown in (a). The typical JJ symbol is shown in (b).

<!-- image -->

## 1.3.2 Circuit Model and Dynamics of Josephson Junctions

Along with the superconducting current, there also exist other parallel channels of current flow in the JJ. There exists a normal or resistive current flowing through the JJ, due to single electron  tunneling.  Furthermore,  the  capacitance  between  the  superconducting  electrodes  also results in a finite displacement current. The 3 sources of currents are modeled in circuit simulations as  seen  in  Figure 1.3  and  this  JJ  model  is  known  as  the  Resistively  and  Capacitively  shunted Junction (RCSJ) model. Here, Ic represents the critical current of the JJ, R is the normal resistance (or equivalently, the conductance G ) and C is the parallel plate capacitance. Assuming a current source driving current I into this circuit, I can be expressed as a sum of the 3 contributions, as

Figure 1.3: RCSJ circuit model of the Josephson junction.

<!-- image -->

expressed  by  Equation 1.5,  which  can  be  further converted  into  Equation 1.6, by  using Equation 1.3.

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Equation 1.5 is a second-order nonlinear differential equation. While analyzing this is non-trivial, we can get some insight into the dynamics by observing that under a small φ approximation , and noting that the JJ has a nonlinear inductance [6], this expression simplifies to that of a parallel RLC resonator, with a certain resonant frequency (also known as plasma frequency of the JJ) and quality factor, Q. This analysis holds in the I &lt; Ic regime, and there are mechanical analogs such as the damped pendulum and tilted washboard that help in understanding JJ behavior better.

For  digital  circuit  operation,  the  focus  of  this  thesis, I  &gt;  I c ,  and  the  Q  factor  plays  an important role in characterizing the JJ. Its dynamic behavior strongly depends upon the StewartMcCumber parameter (  c ) ([3], [6], [8]) defined as:

<!-- formula-not-decoded -->

Central to realizing digital operation in a circuit, is a switch (1-&gt;0 and 0-&gt;1), with a non-hysteretic I-V behavior. In a JJ, the  c parameter determines this, as seen in Figure 1.4, showing the I-V curves for 2 cases of  c .

2 Figure 1.4: (a) The hysteretic I-V characteristic for the underdamped JJ which has  c &gt;&gt;1. (b) A non-hysteretic I-V behavior is observed for the overdamped JJ, with a much smaller  c (less than or equal to 1).

<!-- image -->

In Figure 1.4(a), let us assume 0 V is binary '0' and Vg (superconducting gap voltage, 2.6 mV in case of Nb) is a binary '1'. A transition from 0 to 1 is very fast (few picoseconds), but the 1 to 0 transition requires reducing the current all the way to 0 (due to hysteresis), which is inconvenient and also slow. SCE digital circuits based on this were developed back in the 1970s ([3], [6]), but the effort was later abandoned as it was not fast enough to justify the cooling when compared to the rapid development in semiconductor technologies.

The overdamped JJ with a much smaller  c , on the other hand, seen in Figure 1.4(b), has

2 Based on the hysteretic and non-hysteretic JJ I-V curves in textbooks on superconducting circuits such as [3], [6]

a non-hysteretic behavior. As will be seen in the later sections, this can be exploited for creating fast JJ switching. The JJs used to design the circuits in Chapters 2,3,4, and 5 are fabricated using the MIT-LL SFQ5ee 10 kA/2Ω fabrication process [9]. These are the Superconductor-InsulatorSuperconductor (SIS) Nb/AlOx/Nb tunnel junctions. These are underdamped (  c&gt;&gt;1) due to the larger capacitance contribution of the SIS junctions. To remove the hysteresis and thus increase damping,  a  shunt  resistor  is  added  that  reduces  R,  making  the  c  1.  The  overshunted (overdamped) JJ is core to the digital switching operation of RSFQ circuits.

## 1.3.3 Superconducting Quantum Interference Device (SQUID)

A digital circuit requires 2 important considerations: a switching mechanism and a means to store information. While the JJ serves as a switching device, the Superconducting Quantum Interference Device (SQUID) [3] is used for information storage. The SQUID is a superconducting loop interrupted by JJs. In the DC-biased SQUID, shown in Figure 1.5, a current source Ib , biases 2 junctions J1 and J2 in parallel.

Figure 1.5: DC SQUID comprising superconducting loop interrupted by JJs J1 and J2.

<!-- image -->

When  ex is introduced, it induces a screening current Iex in the loop which adds or subtracts from the DC bias of either of the 2 JJs. If we assume J1 and J2 have phases differences φ1 and φ2 , flux quantization requires:

<!-- formula-not-decoded -->

This results in a co-sinusoidal dependence of the SQUID critical current on the external magnetic flux, with a period of  0 . Implicitly, the SQUID voltage also has similar periodic dependence and thus SQUIDs can be used for very accurate detection of magnetic flux of values smaller than  0.

Under the right conditions of  ex and the correct choice of the loop inductances L1, and L2, if the total current of either JJs exceeds their Ic , J1 or J2 could 'switch' and generate a  0 in the loop. The circular current resulting from this  0 would flow in the loop without any dissipation, thus creating persistent memory. For digital SCE circuits, the presence of a  0 in such a SQUID loop is interpreted as a '1' and its absence is a '0'.

Like the DC SQUID, a 1 JJ SQUID (also known as the RF SQUID) is also used widely in flux detection applications. It comprises a loop interrupted by a single junction. We mention it here to highlight the relationship between the JJ phase and external flux, given by Equation 1.9

<!-- formula-not-decoded -->

It is clear from the relation above that a change of phase of 2π across a JJ corresponds to a  0 present in the loop. We bear this in mind as we describe RSFQ circuits in the next section.

## 1.4 Rapid Single Flux Quantum Circuits

## 1.4.1 Single Flux Quantum (SFQ) Pulses

Around the mid-1980s, a remarkable discovery on the dynamics of overdamped JJs was  made  [10]-[12].  The  overdamped  junction  could  be  driven  momentarily  out  of  the

superconducting and into the resistive state when driven with a short current pulse Iin (t) , such that Iin(t) + Ibias &gt; Ic , where Ibias and Ic are the bias and critical currents of the JJ respectively. Due to the non-hysteretic nature of the overdamped JJ, it would return to its original superconducting state soon  after,  but  not  before  inducing  a  Josephson  phase  difference:  = 2  across  it.  From  the fundamental JJ phase-voltage relationship of Equation 1.3, a 2π change in the phase results in a Single Flux Quantum (SFQ) voltage pulse. The SFQ pulse voltage integrated over time is equal to the magnetic flux quantum,  0:

<!-- formula-not-decoded -->

These SFQ pulses can have a range of amplitudes, typically around 1mV, and pulse widths of around 1-2ps. Binary information encoded in form of these SFQ pulses could thus be processed at very high speeds and low power. While different families of logic circuits based on SFQ pulses are currently being investigated, the Rapid Single Flux Quantum (RSFQ) logic has been the most promising and developed. RFSQ circuits are peerless amongst SFQ logic families when it comes to speed (nominal operation is ~40GHz) making them a promising candidate for high-speed digital applications. Let us now briefly discuss how RSFQ circuits operate by means of two example circuits that are widely used in almost every RSFQ design: the Josephson Transmission Line (JTL) and a D Flip Flop.

## 1.4.2 Josephson Transmission Line (JTL)

If the Ib of a JJ is close to its Ic , the 2π change in phase and the consequent SFQ pulse could be triggered by another SFQ pulse. Thus, an array of such JJs could be used to transfer the SFQ pulses  on  an  SCE  chip.  This  idea  leads  us  to  one  of  the  most  ubiquitous  RSFQ  circuits,  the Josephson Transmission Line (JTL). In the JTL circuit of Figure 1.6, the 4 identical JJs, JA1 to

JA4 are biased close to their critical currents Ic (at  0.7 times Ic ). The LA1 and LA2 inductance value is chosen such that the no flux quantum (  0) is stored in the loops (for e.g., JA1-LA2-JA2) of this circuit and that  0 is simply transported from one JJ to the next.

When an SFQ pulse reaches JA1, the total current flowing in JA1 exceeds its Ic , driving JA1 momentarily into the voltage state and undergoing a phase change of 2π. This corresponds to JA1  'switching'  and  emitting  an  SFQ  pulse.  In  magnetic  terms,  a  flux  of  0  crosses  JA1 transversely. This process repeats across all the subsequent JJs and the pulse is thus transported to the output.

3 Figure 1.6: Josephson Transmission Line comprising 4 junctions with  c ~ 1 and inductors for interconnections. Upon receiving an SFQ voltage pulse as an input, the JJs switch in the order JA1-JA2-JA3-JA4, and then the pulse exits the JTL circuit.

<!-- image -->

3 Based on the Josephson Transmission Line described in [12].

4 Figure 1.7: (a) RSFQ D Flip-Flop (DFF) block diagram showing the input output connections. (b) Presence of a pulse in a clock window is interpreted as logic '1', the absence is a '0'. Note the clock -to-data out delay between the SFQ pulses. The circuit schematic of the DFF is shown in (c).

<!-- image -->

4 Based on the D Flip Flop described in [12]. More information on RSFQ circuit designs is found at the SUNY/Stony Brook RSFQ Laboratory: http://www.physics.sunysb.edu/Physics/RSFQ/index.html

Note the resistors used for providing the bias currents to the JJs. All RSFQ circuits require resistors for providing a DC bias, thus contributing to static power dissipation. As described later, this is one of the major obstacles to scaling these circuits.

## 1.4.3 D Flip Flop

While JTLs transfer SFQ pulses, SFQ Flip-Flops store them using DC SQUID loops, as described  in  the  previous  section.  Before  we  describe  the  Flip-Flop  circuit  behavior,  the representation of bits in RSFQ logic is stated. The arrival of an SFQ pulse in a timing window (between two clock pulses) is considered a logic '1' and its absence is a logic '0'. As information is encoded in SFQ pulses, a timing window is always required, necessitating a clock. This is better understood  from  the  block  diagram  in  Figure 1.7(a)  and  the  timing  graph  in  Figure 1.7(b). Generally speaking, most RSFQ circuits which store the flux quantum, require an additional clock for correct operation.

For the D Flip Flop in Figure 1.7(c), the storage element is the DC SQUID comprising the J1-LD2-J2 loop. As described earlier, for an appropriate value of the loop inductance LD2, this could store persistent current, or in magnetic terms, a flux quantum. The presence of  0 in the loop sets the state of the Flip Flop to '1' and absence is a '0'.

In the state '0', an incoming data SFQ pulse enters the circuit, adding to the current flowing in J1. The total current exceeds the Ic of J1 causing it to undergo a 2  phase change or a 'switch'. A DC current now flows in the loop clockwise, under-biasing J1 and biasing J2 close to its Ic . The loop stores a  0 and thus state 1 is achieved. If a clock input is provided, the total current flowing in J2 exceeds its Ic and it switches releasing the  0 to the subsequent circuitry (not shown). The state is reset to '0'. If there is an SFQ pulse input when the state is '1', J0 switches preserving the

state. Similarly, if there is an SFQ pulse clock when the state is '0', J3 switches preserving the state.

Based on these underlying principles, other logic circuits such as NOT, XOR, AND, OR, Toggle Flip Flops, and DRO/NDRO (Destructive Readout/Non-Destructive Readout) Registers are designed.

## 1.5 Applications and Challenges of RSFQ circuits

The width of the SFQ pulse is 1~2 ps and this makes high-speed digital operation a very attractive  application  for  this  technology.  In  fact,  an  RSFQ  Toggle  Flip-Flop  [13]  has  been demonstrated to operate up to 770 GHz, making it the fastest digital circuit to date.  The speed advantage  of  these  circuits  has  led  to  applications  in  high  bandwidth  circuitry  for  digital communications. Analog-to-Digital converter architectures such as the Delta ([14], [15]) and the Flash ([16], [17]) have been successfully designed.

Digital signal processing circuit blocks are the other high throughput application of RSFQ  logic.  Filters,  encoders  [18],  mixers  [19],  Look-up  tables  [20],  Pseudo  Random  Bit Sequence (PRBS) generators ([21], [22]), adders [23], and counters [24] have been demonstrated at  high  speeds,  using  this  technology.  High-speed  general-purpose  computing  could  also  be  a potential use case for these circuits. In fact, in [25], the operation of a 20 GHz RSFQ Arithmetic Logic Unit (ALU) has been successfully demonstrated.

The dynamic power dissipation per JJ switching activity is typically given by:

W =

<!-- formula-not-decoded -->

This value is around 10 -19 J, a number significantly lower compared to conventional computing hardware. Furthermore, SFQ pulses can be transmitted on superconducting passive transmission

lines (PTLs) ([26]-[28]) at speeds approximately 1/3 the speed of light and without much loss. These attributes  make RSFQ and other SFQ logic families such as the  energy-efficient RSFQ (ERSFQ) ([29],  [30]),  Adiabatic  Quantum  Flux Parametron  logic  ([31], [32]),  and  Reciprocal Quantum  Logic  (RQL)  [33]  as  strong  candidates  for  low  power,  high  complexity  computing applications.

One of the challenges in implementing RSFQ circuits for commercial purposes (and other SFQ-based circuits) is the cryogenics required. These circuits operate at ~ 4.2 K and thus require liquid helium for operation. Developments in closed-cycle refrigeration [34] have helped reduce the dependence on expensive Helium and made testing these circuits faster.

Magnetic flux trapping is an undesirable outcome of the Meissner effect, where circulating currents are trapped on the chip, during the cooling process. These currents could couple to active circuitry, resulting in reduced operating margins or, in some cases, no operation. This is a major challenge  to  achieving  large-scale  RSFQ  circuits  with  wide  operating  margins  and  hence significant  research  has  gone  into  understanding  flux  trapping  mechanisms  ([35]-[38])  and modeling them in simulation ([39], [40]).

While the low dynamic power dissipation of RSFQ circuits is an advantage, RSFQ circuits are  biased  using  resistors  that  consume  static  power  dissipation.  Multiple  circuit  techniques  to reduce static power dissipation have been developed, with the ERSFQ family of circuits, a strong contender due to the zero static power dissipation and compatibility with RSFQ logic.

SCE circuits have historically encountered fabrication challenges such as low yield and poor  model-to-hardware  correlation.  This  has  often  resulted  in  circuits  working  with  poor operating  margins.  In  recent  years,  the  fabrication  has  matured  significantly.  This,  along  with better  design  optimization  of  circuits  for  wide  margins,  has  helped  alleviate  this  problem.  For

large-scale  circuits,  however,  sophisticated  electronic  design  automation  (EDA)  tools  must  be developed  for  synthesis  and  place-route  activities.  This  remains  a  big  challenge,  and  multiple efforts ([41]-[45]), such as the IARPA-led SuperTools [46] program, are currently underway to address them.

Lastly, note that RSFQ/ERSFQ circuits require DC bias currents, which can easily exceed several amperes for medium complexity circuits (~1000 JJs) [14]. Such large currents not only are limited in their capacity due to fabrication limitations but also increase the heat load delivered to the  chip.  Magnetic  fields  produced  by  such  currents  can  destroy  circuit  operation  or  reduce operating margins significantly. Reducing the on-chip DC bias currents is an absolute must for successfully scaling this technology. We try to address this problem here.

## 1.6 Prior Work on Serial Biasing

In  serial  biasing  (SB),  the  circuitry  is  divided  into  smaller  identical  circuits,  placed  on isolated ground plane islands. A fraction of the total DC bias current is provided to the circuitry on  the  1 st island  and  serially  transferred  to  the  circuitry  on  the  neighboring  islands.  This  was initially  investigated  and  demonstrated  in  ([47],  [48]).  Serially  biased  SFQ  transmission  using either capacitive or inductive coupling was shown in [49] up to bit-rates of 30 Gbps. Both schemes of coupling resulted in a similar Bit-Error Rate (BER). However, in case of capacitive coupling, this would require a large capacitor size resulting in increased area penalty which is undesirable. Serially biased components of a digital-RF receiver system were designed and tested in [49]. The driver-receiver pair (DRP) circuits, which constitute of inductive coupling were designed such that SFQ pulses would have to pass through 80 DRPs in series. A ±7% bias margin was observed for

this 80-DRP experiment. Core parts of the receiver, such as the digital filter and output drivers were then serially biased and successfully demonstrated.

In [50], a 16-bank, 7-stage ripple counter based on T Flip-Flop (TFF) was serially biased, resulting in operation of up to 50 Gbps. A bias margin of approximately ±4% was observed for the circuit at low frequency. A divided output (by a factor of 128) was used to confirm the 50 Gbps operation. From these works, it is clear that low operating margins, especially at high frequencies, are a challenge that must be overcome to make SB more widely adopted. With this in mind, the DRP was studied in more detail in [51], especially the design of the transformer with respect to the  ground  moat  locations.  Recommendations  were  made  on  the  optimal  DRP  design,  and  a successful correct demonstration of the optimal DRP operation up to 42 GHz was performed. An approximate 5% margin was observed at high frequencies.

In a relatively complex design, a time-to-digital converter (TDC) was serially biased, and the correct operation was observed with a time resolution of 100 ps [52]. This is a promising result as  it  was  the  first  demonstration  of  ~100 mA  serial  biasing.  The  operation,  however,  was determined only at a single point in the bias space, a repeated challenge facing SB.

More recently, [53] designed and demonstrated serially biased circuits for the MIT-LL SFQ5ee fab node. Design recommendations on the DRP were made, and a 16 stack of 16-bit counterflow  RSFQ  shift  registers  was  successfully  serially  biased  with  ~6%  bias  margins observed.  Along  with  physical  circuit  design,  there  have  also  been  efforts  lately  in  designing partitioning  algorithms  for  serial  biasing  of  complex  designs  ([54],  [55]).  In  [54],  for  e.g.,  a partitioning algorithm on different benchmark circuits is performed, and the metrics such as area, number of interconnections, etc., are analyzed.

## 1.7 Contributions of this Thesis

## 1.7.1 Current Management Techniques for Serially Biased RSFQ circuits

In  serial  biasing,  bias  currents  need  to  be  injected  into  the  circuitry  on  the  1 st island, distributed, and then the return current must be extracted from the ground plane. Once extracted, it is transferred to the circuitry on the neighboring island. This constitutes current management and is often ignored when the bias current is small. However, for larger currents, the return currents flowing on the isolated islands could couple into the circuitry, causing it to misbehave. This could reduce the bias margins or even render the circuit non-operational.

In  this  thesis,  a  new  current  management  technique,  the  'Grapevine  Biasing  (GV)' technique, is introduced for managing bias currents for serially biased circuits for the MIT-LL SFQ5ee fabrication node. Detailed circuit implementation of the GV biasing is discussed.  The technique  is  verified  by  designing  serially  biased  versions  of  example  circuits:  the  digital decimation filter (DDF)  [18] and the 3-to-2 parallel counters  [24]. It is shown that the 4-slice serially  biased  DDF  has  similar  margins  to  the  parallel  biased  4-slice  DDF.  A  test  circuit comprising 9 serially biased 3-to-2 parallel counters is observed to work up to 20 GHz with open bias margins. This work was presented at the EUCAS '21 conference and was published in the IEEE Transactions on Applied Superconductivity [56].

## 1.7.2 Driver-Receiver Pair (DRP) Circuit for Serial Biasing

Central to  the  serial  biasing  technique,  are  the  SFQ  pulse  transfer  or  DRP  circuits  that enable inductive coupling between circuits on neighboring ground planes. A single weak DRP can drastically reduce the operating margins of a serially biased circuit. Thus, it is important to design it carefully and exhaustively characterize it across frequency, for different input patterns.

In this thesis, we present a DRP circuit working with open margins, up to 60 GHz. While the DRP has been designed and tested in other works, it is important to test it with random data. To this effect, a testbed with a Pseudo Random Bit Sequence (PRBS) generator is presented. A straightforward and the grapevine biasing are compared and contrasted by means of measurement and  electromagnetic  (EM)  simulations.  BER  Results  from  FPGA-based  acquisitions  are  also reported.  We  present  circuit  margins  across  frequencies  up  to  60 GHz.  Model-to-Hardware correlation is also performed to explain the shrinkage of margins. Furthermore, EM simulations are  used  to  recommend the best  design  practices to  implement  GV biasing. This work will be presented  at  the ASC  '22 conference  and  submitted  to  the IEEE  Transactions  on  Applied Superconductivity.

## 1.7.3 Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits

Scaling RSFQ circuits require the capability of EDA tools to perform operations such as functional  simulation,  synthesis,  timing  verification,  back  annotation,  and  place-and-route. Recently, there has been an active research effort on all these fronts because of the IARPA-led SuperTools Program. With scaling, serial biasing must be addressed by EDA tools as well. While algorithms for partitioning have been developed in other works, circuit-level implementation must be addressed to make physically realizable serially biased circuits.

In this thesis, we have developed all the components needed for performing serial biasing for the SuperTools cell library [57]. New features that make the DRP circuits compatible with the library cells are introduced. The GV biasing scheme is also implemented. Assembly strategies for islands are discussed in detail, with an example test circuit designed, fabricated, and tested. The test  circuit  verifies  the  operation  of  all  the  components  successfully  up  to  50 GHz.  Detailed

experiments  such  as  crosstalk  are  also  performed.  EM  simulations  depicting  the  bias  current density distribution are presented. Layout rules have been developed using EM simulations such that a circuit designer could use them as a reference when performing serial biasing. This work will be presented at the ASC '22 conference and has been accepted for publication in the IEEE Transactions on Applied Superconductivity.

## 1.7.4 Passive Transmission Lines for Serially Biased RSFQ Circuits

Digital cells in RSFQ circuits are typically routed using either Josephson Transmission Lines (JTLs) or Passive Transmission Lines (PTLs). The former is an active circuit and needs DC bias currents. Thus,  it is expected  that  to achieve  the  reduction  of  bias  currents  on  a superconducting chip or, in the context of this thesis, serially biased islands, PTLs must be used extensively instead of JTLs. High-speed operation and wide bias margins of the PTLs are needed to  replace  JTLs reliably.  To  do  this,  PTLs  compatible  with  library  cells  must  be  designed  and extensively validated in simulation and tests.

In this thesis, we have designed two types of PTLs compatible with the SuperTools cell library. The PTLs with symmetric dual ground planes are to be used for communication between distant  circuits,  whereas  the  PTLs  with  the  asymmetric  dual  ground  planes  are  designed  for transferring SFQ pulses under active circuitry. Impedance characterization and bias margins for the PTLs have been reported. Model-to-hardware correlation between simulations and measurements has also been presented. This work was published in the IEEE Transactions on Applied Superconductivity .

## 1.8 Organization of the thesis

Chapter 1 introduces superconductivity and aspects of it that apply to electronic circuits. It briefly describes the Josephson junction as the active element in superconductor electronics and introduces  RSFQ  circuits for  transmitting  binary  information.  The  applications  and  challenges facing RSFQ technology are discussed, and serial biasing is presented as a promising solution for the large DC bias current problem facing these circuits. Prior research works on serial biasing are also presented.

Chapter 2 presents the novel 'Grapevine Biasing' scheme for DC bias current management in serially biased RSFQ circuits. The scheme is validated by designing and testing serially biased example circuits. Bias margins at both low and high frequencies of the circuits confirm that the grapevine technique is indeed promising.

Chapter 3  presents  an  in-depth  study  of  the  Driver-Receiver  pair  circuit,  the  main component  of  the  signal  transfer  scheme  in  serial  biasing.  Design  details,  circuit  and  EM simulations, and design recommendations are presented. Measurement results demonstrating highfrequency operations are presented and attempts to correlate test and simulation data are also made.

Chapter 4  reports  on  all  the  components  required  for  performing  serial  biasing  on  the SuperTools cell library. The techniques developed could be used in conjunction with a synthesis tool  performing  place-and-route.  Measurement  results  on  an  example  test  circuit  confirm  the operation of all the components at high frequencies. EM simulations and layout recommendations are provided that could lead to successful operations in scaled designs using the cell library.

Chapter 5 describes the PTLs with symmetric and asymmetric dual ground planes. The choice of signal and ground metal layers for the MIT-LL SFQ5ee fabrication node is described in detail. The characteristic impedance of the PTLs is simulated and measured as a function of the

signal  widths.  The  PTL  receiver  bias  margins  are  also  reported.  Measurements  confirm  the impedance and margins observed in the simulation. Similar confirmation between measured and simulated bias margins is also observed at low and high frequencies.

Lastly,  we  summarize  the  conclusions  that  can  be  made  from  all  the  research  topics discussed in this thesis.

## Chapter 2: Pulse Interfaces and Current Management Techniques for Serially Biased RSFQ Circuits

As digital superconductor circuits based on Rapid Single Flux Quantum (RSFQ) logic scale up in complexity, so does the total current required to provide DC bias. Serial Biasing (SB) is a promising solution that can be used to reduce the current by placing identical digital blocks on islands with isolated grounds and biasing them sequentially. There are typically two implementations that are essential for the SB approach: the design of a driver-receiver pair (DRP) circuit for inter-island pulse transport and the current management technique to handle bias current flowing into and out of an island. While a DRP with good fidelity is essential for any serially biased circuits,  the  current  management  becomes critical  for  designs  with  relatively  large  bias currents. In this Chapter, we address the latter. First, we propose a grapevine biasing scheme for serial bias current management. Second, we implement the technique using two example circuits: the parallel counter and the digital decimation filter. We report the low and high-speed test results up to 50 GHz for both circuits fabricated at MIT-LL in the SFQ5ee 10kA/2  fab node.

## 2.1 Introduction

Conventional Rapid Single Flux Quantum (RSFQ) [12] circuit design entails supplying each Josephson Junction (JJ) in the circuit with DC bias current. This bias current requirement of complex superconductor circuits can easily exceed several amperes [14] (2 A for 10 4 JJs with an averaged bias current of 200  A per JJ) or tens of amperes (50 A for 10 6 JJs with an averaged bias current  of  50  A),  and  this  can  have  multiple  implications.  Large  DC  bias  currents  produce

magnetic fields that can disrupt the logical operation of a circuit and reduce margins ([58], [59]). Supplying  such  currents  to  the  chip  also  becomes  challenging  because  of  the  limited  current carrying capacity of Nb wires on the chip ([9], [60], [61]) and heat load, increasing with the total bias current, and delivered to the chip through bias current leads [62]. These constraints make reducing bias current for RSFQ circuits highly desirable and unavoidable.

The concept of Serial Biasing (SB)  has been researched in the past [47], with different works demonstrating  the  techniques  ([48]-[51],  [63]-[65]),  including  the  most  recent  experimental results ([52], [53]). SB is a promising, but not quite mature, current reduction technique where a complex digital circuit is partitioned into several identical islands, and the bias current to the first island is 'recycled' across the others. In the parallel bias (PB) case, as shown in Figure 2.1(a), the current is applied to the circuits on the same global ground plane. In comparison, in Figure 2.1(b), the global ground plane is divided into 3 islands, and circuitry is equally partitioned between them. The serial bias current is provided to the 1 st circuit alone, and the 'used' current is picked up to bias the 2 nd circuit  and  so  on.  In this  particular case, the bias current requirement of the entire circuit reduces by a factor of 3. In the case of PB, circuit blocks are galvanically connected for data and clock pulse propagation. In the SB case, the clock and data are transferred inductively between islands while the circuit blocks are galvanically isolated.

Figure 2.1: (a) Parallel Bias (PB) versus (b) Serial Bias (SB).

<!-- image -->

Two key design considerations for SB are the driver-receiver pair (DRP) design and the serial bias current management. A robust DRP is essential for high-fidelity signal transfer across multiple islands. In recent works, the multiple metal layers provided by the fabrication process [60] have been utilized to improve the flux immunity of the DRP transformer [51] and to shield the ground moat in the proximity of the DRP [53] for the fab node [9]. However, as the bias current requirement per island increases, questions of how to inject the bias current in and extract it out of an island become critically important. To the best of our knowledge, current management has not been discussed in detail in the prior work on SB. For example, in [52], a large serially biased FIFO buffer is demonstrated, but a discussion on current management is only briefly touched upon.

In this Chapter, we focus on the current management techniques for serially biased circuits designed for the MIT-LL SFQ5ee 10kA/2  fab node [9]. In section 2.2, a current management scheme is proposed that mitigates magnetic disturbances and image currents circulating on floating islands.  The  digital  decimation  filter  (DDF)  and  the  3-to-2  parallel  counter  are  proposed  as example circuits to evaluate the techniques. Sections 2.3 and 2.4 present the detailed measurement results for the DDF and the 3-to-2 parallel counter. Section 2.5 discusses the challenges in testing and interpreting the test results. Finally, we conclude the study in section 2.6.

## 2.2 Grapevine Approach

## 2.2.1 General Grapevine Biasing Design

Figure 2.2: Straightforward (a) versus Grapevine Approach (b) for MIT-LL SFQ5ee metal stack (c). Black and white arrows depict bias current and return current, respectively.

<!-- image -->

In the SFQ5ee process [9], RSFQ digital circuits are usually designed between the ground plane in the M4 layer and the sky plane in M7, while the underground metal layers M0, M1, M2, and M3 are used for biasing, passive pulse transmitting and extra ground [28].

A  straightforward  approach  to  biasing  a  circuit  on  a  floating  island  is  shown  in Figure 2.2(a). An underground bias bus in M0 is used to deliver the current to an island over a moat, and it reaches the circuitry through holes in the ground plane M4. The 'used' bias current is picked up from the ground plane and delivered to the next island to 'reuse' or 'recycle'. The return current  is  forced  to  flow  around  the  islands.  In  such  an  implementation,  complicated  circular currents  are  created  on  the  floating  ground  planes.  Upon  simulating  this  layout  using  an electromagnetic (EM) simulator such as Sonnet [66], high current density is observed along the edges (moats) of the floating ground planes. This is undesirable as it can disrupt the pulse transfer operation on the DRPs located on the ground moats. The approach in Figure 2.2(b) is proposed to address this shortcoming. The same underground bias bus in M0 is used to deliver current to the island. However, the return current flows along an additional metal layer in M2 connected to the global ground but not touching the floating grounds. As a result of providing a path for the return current to flow, the intensity of the circular currents on the island is minimized. We confirm this by  observing  the  absence  of  high  current  density  along  the  ground  plane  edges  in  Sonnet simulations. The ratio of current densities on edges for straightforward and grapevine approaches is 0.1 or smaller. Note that in addition to M0, another layer, M1, is also used to create a dedicated pair of metal layers to carry bias current in and out in absence of M2 SB ground.

## 2.2.2 Going Through a Hole in the Ground Plane

There are two popular schemes for biasing RSFQ circuits designed for the MIT-LL SFQ5ee fab node [9]. One approach is to design a power grid in the M0 layer and reach each bias resistor through individual holes in M4. Another approach is to deliver the entire current through a single hole in M4 to a power grid formed in the M5 layer with further connections of individual bias resistors.

Figure 2.3: Straightforward (a) versus Grapevine Approach (b) for going through a hole in the ground plane for MIT-LL metal layers stack (c). Not all layers are shown in (d) and (e) to simplify visualization. Note that any metal layer to carry 'current -in' has a dedicated metal layer to carry 'current -out'. Cross -sections (a) and (b) correspond to dashed lines in (d) and (e) respectively.

<!-- image -->

In the latter case, the underground bias in M0 must transmit to M5 through a hole in the M4 ground plane, and such a transition should carry and handle the current to bias the whole island.

The 'used'  current  must  flow 'down'  to  the  underground  layer  M0  for  recycling.  Let  us  first examine the straightforward approach of how the bias current would traverse through a hole. In Figure 2.3(a), a cross-section is shown where the current enters the island in M0 and flows to the circuitry in the upper metal layers. From the junction ground, it flows down to M0 and then to the next island. Thus, there are two stacks of metal layers for the current injection/extraction, and they are arbitrarily placed with respect to each other but in proximity of each other. Figure 2.3(d) is a top view of this implementation. Upon performing an EM simulation on this layout, high current density  around  the  hole  in  the  ground  plane  is  observed.  We  try  to  minimize  this  magnetic disturbance using the grapevine biasing scheme. In Figure 2.3(b), the bias current is observed to enter in M1, which then flows to the circuitry along the metal stack. The ground current from M4 is picked up and flows along another metal stack placed very close to the first stack. Thus, the metal  layer  stack  has  a  well-specified  position  to  pick  up  the  used  bias  current.  The  current injection and extraction via appear to have a double waterfall structure. In proximity of the M4 hole, the current flows in M0 while maintaining an overlap with the M1 metal layer used to enter. This can also be seen in the top view of Figure 2.3(e). In the grapevine biasing approach, the magnetic field is localized between the two superconductors; hence, the image current distribution on  the  island  is  well-behaved.  This  is  again  confirmed  by  Sonnet  simulations  which  show minimum current density around the ground plane hole. The current density for the grapevine approach is at least ten times smaller compared to the straightforward approach.

## 2.2.3 Example Circuits and DRP Design

A Digital Decimation Filter (DDF) [18] and a 3x3 matrix of 3-to-2 parallel counters ([24], [67]) are chosen as the example circuits for studying the grapevine biasing scheme. Both circuits are

designed for the 10 kA/2  SFQ5ee fabrication node at MIT-LL [9] and characterized in the case of  parallel  biasing.  The  4-slice  DDF  and  the  3x3  matrix  of  counters  are  relatively  complex structures (about 10 3 JJs) with non-trivial internal functions implemented, inherent racing between data and clock pulses, and multiple DRPs per island.

Along with the example circuits and the grapevine biasing technique, DRPs are required for pulse transfer. We have designed them similar to what has been reported in [64]. Important parts of the design include the transformer and the 'tongue' spread over the ground moat. The DRP design  is  further  improved  by  borrowing  ideas  from  [53]  that  help  to  reduce  flux  trapping. Extensive details on the DRP design and test are reported in Chapter 3.

## 2.3 Testing of the DDF Circuit

## 2.3.1 Test Structure Design

A slice of a DDF circuit consists of modules for a master clock, toggle flip flops with both destructive/non-destructive readout, and Nyquist clock [18]. Many such identical slices form a DDF circuit. Four slices consist of 856 (4 x 214) JJs. The parallel biased 4-slice DDF is designed as a reference structure and is labeled 'PB' in Figure 2.4. It was placed on the chip to compare the results of serial bias and parallel bias cases. A second test structure consists of 4 slices of the DDF, serially  biased  on  a  single  island  (denoted  'SB1'  in  Figure 2.4).  Finally,  another  test  structure called 'SB4' consists of 4 slices on 4 islands.

Figure 2.4: Chip layout consisting of the PB, SB1, and SB4 test structures (see text for details). The chip was fabricated at MIT-LL using SFQ5ee 10 kA/2  fab node.

<!-- image -->

A detailed block diagram of the SB4 test structure is shown in Figure 2.5. Each 1-bit slice has 6 inputs and 7 outputs. The left, top, right, and bottom interfaces are low-frequency (LF) DCto-SFQ converters and SFQ-to-DC monitors [12] for providing input and observing the output, respectively. The grapevine biasing can be seen at the bottom, entering the first island and exiting the last before being connected to the global ground. The red, black, and blue signals are the Master clock (MC), data, and the Nyquist clock (MC) traversing through the islands.

Figure 2.5: Test structure consisting of 4 serially biased DDF slices on 4 islands (SB4).

<!-- image -->

## 2.3.2 DDF Test Results

The chip consisting of the 3 test structures was designed, fabricated, and tested using the Octopux test system [68] and immersion probe in liquid He. The measured data is compared with the simulation for functional correctness, with different input patterns [64]. This functional testing is typically performed at a sub kHz frequency.

Figure 2.6: LF bias margins for PB, SB1, and SB4 test structures for locations B1, A3, and C3.

<!-- image -->

Figure 2.6 shows the normalized serial bias current for the test structures across 3 wafer locations. We observe that all 3 test structures show similar bias margins exceeding  10% in most cases. Another observation is that the SB4 test structure does not show degradation in margins when compared to SB1 while switching from 1 isolated ground to 4 isolated islands. It means that margins are dominated by the properties of the DDF circuit itself but not by DRPs.

The measured ratio ISB1/IPB was greater than 1 because of the overhead of the DRPs in the SB1 case (see Table 2.1). The measured ratio ISB1/ISB4 was equal to 3.4 and not 4, as the number of DRPs does not grow proportionally to the number of islands between SB1 and SB4. For an ideal case of a scalable circuit, this ratio should be equal to 4. It can be observed from Table 2.1 that the ratio of the measured total current to the nominal total current is larger for serially biased circuits, and this increases with the number of islands for reasons not entirely known for now.

Table 2.1: Ratio of Measured Total Current to Nominal for PB, SB1, and SB4

| Bias Type   | Name   |   Number of Slices |   Number of Islands |   Nom. Bias Current mA |   Nom. Overhead Current mA |   Nom. Total Current mA |   Measured Total Current mA |   Measured Total Current/Nom. Total Current |
|-------------|--------|--------------------|---------------------|------------------------|----------------------------|-------------------------|-----------------------------|---------------------------------------------|
| Parallel    | PB     |                  4 |                   0 |                  109.2 |                        5   |                   114.2 |                         120 |                                        1.05 |
| Serial      | SB1    |                  4 |                   1 |                  109.2 |                       16.3 |                   125.5 |                         136 |                                        1.08 |
| Serial      | SB4    |                  4 |                   4 |                   27.3 |                        7.2 |                    34.5 |                          40 |                                        1.16 |

## 2.4 Testing of 3x3 Matrix of 3-to-2 Counters

## 2.4.1 Test Structure Design

We chose a 3x3 matrix of the 3-to-2 counters to organize nine serially biased islands, as shown in Figure 2.7. The entire matrix consists of 2250 JJs. Each 3-to-2 circuit converts a 3-bit unweighted input to a 2-bit binary output ([24], [67]). The HF test pattern generator allows us to derive input patterns from a continuous clock stream using DC switches as described in ([25], [69]). We can activate one or all of the three rows at a time and select what input pattern to apply. Each binary output is converted into true and complementary forms [69] that allow us to perform Bit Error Rate (BER) testing (see [25] for details). The grapevine serial bias is observed to enter the 1 st island and exits the 9 th island before terminating at the global ground.

Figure 2.7: Block diagram of the serially biased 3x3 matrix of 3-to-2 counters. The MSB output of the 1st 3-to-2 circuit is split in two and provided to two of the unweighted inputs of the subsequent 3-to-2 circuit. Similar MSB splitting is observed for the 3rd in a row 3-to-2 circuit as well.

<!-- image -->

## 2.4.2 Test Results

The circuitry shown in Figure 2.7 was designed and fabricated at MIT-LL. The LF tests were performed using an immersion probe in liquid-He at the clock frequency of 800 kHz. A stable true and complementary outputs and a divided clock were observed on an oscilloscope to confirm the correct operation of the circuit at LF. The results are presented in Figure 2.8. The normalized serial bias current is plotted against the input patterns for the 3 rows separately, tested one by one. We observed correct operation for all 7 input patterns. ROW1 is seen to have the narrowest bias margins of  5%, whereas ROW2 and ROW3 have similar bias margins of  10%.

Figure 2.8: LF Serial Bias Margins for 7 input patterns, for all rows tested one at a time. The input (for e.g., '001') is addressed as 'Top (T)' 'Middle (M)' 'Bottom (B)' in reference to the physical layout location of the inputs on the 3-to-2 circuit (compare with Figure 2.7).

<!-- image -->

For BER testing at high frequency (HF), the outputs need to be observed for a finite time while errors are counted. The BER measurements are time-consuming and were performed in the Integrated Cryogenic Testbed (ICE-T) as it allows for continuous testing over multiple days [34]. Observation windows of 2 and 1 minute were chosen for frequencies up to 20 GHz and greater, respectively.

Figure 2.9: BER versus seria l bias current for the '100' input pattern. Frequency is swept from 1 GHz to 50 GHz. Operational margins do not depend strongly on the clock frequency.

<!-- image -->

ROW3 was observed to have the widest margins. Figure 2.9 shows the BER curves versus the serial bias current across frequencies from 1 GHz to 50 GHz for the '100' input pattern. One can see  that  this  input  combination  works  with  5%  margin  up  to  50 GHz  with  a  BER  of  10 -12 . Figure 2.10 presents similar BER curves but for the '101' input pattern. The margins at 50 GHz are  4.4%. The '111' pattern most complex and is shown in Figure 2.11.

Figure 2.10 : BER versus serial bias current for the '101' input pattern. Frequency is swept from 1 GHz to 50 GHz.

<!-- image -->

Figure 2.11 : BER versus serial bias current for the '1 1 1' input pattern. Frequency is swept from 1 GHz to 50 GHz.

<!-- image -->

Figure 2.12 : BER versus serial bias current for the '111' input pattern for simultaneous operation mode at 20 GHz.

<!-- image -->

Figure 2.13 : BER versus serial bias current for the '001' input pattern for simultaneous operation mode at 50 GHz.

<!-- image -->

We tested 5 of 7 input patterns skipping trivial pattern '000' and repeating patterns '001',  and '010'. Results for all individually tested at 20 GHz rows are summarized in Table 2.2.

Table 2.2: Serial Bias Margins for Individual Rows across 5 Input Patterns at 20 GHz

|      | 111     | 110    | 100    | 101    | 011    |
|------|---------|--------|--------|--------|--------|
| ROW1 |  1.08% |  3.8% |  3.4% |  4%   |  2.7% |
| ROW2 |  1.60% |  2.8% |  5.5% |  3.5% |  5.9% |
| ROW3 |  3.3%  |  3.2% |  5%   |  4.9% |  3.9% |

In addition to testing individual rows, we demonstrated operation when all the rows were simultaneously  activated.  The  circuit  was  observed  to  operate  in  this  mode  up  to  20 GHz. Figure 2.12 shows the corresponding BER curve versus serial bias current at 20 GHz for the '111' input pattern. The margin is observed to be  1.08% with a BER of 10 -12 . While the '111' input only worked up to 20 GHz, some of the other inputs did work at 50 GHz as well for all 3 rows simultaneously. Figure 2.13 shows, for e.g., the BER curve versus serial bias current at 50 GHz for the '001' input pattern. A bias margin of  1.9% was measured. Observed errors varied for different  rows  at  BER  level  of  10 -12 ,  so  we  could  not  identify  a  particular  source  of  errors. However, in all 3-row measurements, ROW1 was observed to limit the margins.

## 2.5 Discussion

Serially  biased  circuits,  like  ERSFQ  circuits  [29],  do  not  have  the  design  flexibility  of having multiple biases. As a result, a parallel biased RSFQ circuit with multiple biases needs to be optimized for a single bias before it can be serially biased. The relatively narrow margins observed for the 3x3 matrix of the 3-to-2 counters cannot be attributed explicitly to the serial bias scheme because we do not have reliable test data for the 3-to-2 counters with combined biases. So, as a

future step, it is planned to place on the same chip SB and PB versions of the 3x3 matrix to compare the biasing schemes directly.

The SB and PB versions of the 4-slice  DDF  had  similar  wide  margins.  However,  this encouraging observation needs to be verified at HF. We need to develop a true and complementary testbed to perform HF testing of the DDF.

Our test results show that a simple input pattern could provide too optimistic results, e.g., compare margins for patterns '100' and '111' for the 3x3 matrix. It proves that a circuitry selected for SB characterization needs to support multiple non-trivial input data streams. We also believe that reporting BER numbers in addition to margins achieved at a particular  frequency helps to eliminate any ambiguity while comparing different test results.

## 2.6 Conclusions

We have proposed, designed, and tested the grapevine current management technique for serially biased RSFQ circuits. Key features include a dedicated pair of bias-line-in and bias-lineout at all locations and the addition of a ground plane along with the existing ground and sky planes.  The  grapevine biasing  scheme was tested on example circuits consisting of the 4-slice digital decimation filter (DDF) and 3x3 matrix of 3-to-2 parallel counters. The serially biased 4slice DDF circuit with a complexity of around 10 3 JJs was tested at LF. The parallelly and serially biased DDFs exhibit similar margins of  10%. A 3x3 matrix of 3-to-2 counters with a complexity of around 2250 JJs was tested at both LF and HF. The LF margins for any individual row were observed to vary from  4% to  12% depending on the row and input pattern selection. Correct operation of the entire matrix was observed up to 20 GHz with a BER better than 10 -12 . Individual

row margins at 20 GHz were limited to a maximum of  5.9%. Correct operation of individual channels up to 50 GHz was also confirmed.

## Chapter 3: 60-GHz Single Flux Quantum Pulse Transfer Circuit for Serial Biasing

In this Chapter, we focus on the design of a driver-receiver pair (DRP) circuit to transfer pulses between islands that are galvanically isolated for pulse streams. We discuss both the DRP itself and the structure for its testing, which comprises several DRPs connected in series, an onchip  pseudo-random  binary  sequence  (PRBS)  generator  for  circuit  stimulation,  and  a  highfrequency (HF) output interface. The layout of the DRPs' chain is used as an example to illustrate the advantage of the grapevine (GV) biasing approach introduced in Chapter 2, to manage the bias current flowing into and out of an island. The GV current management technique is analyzed by both electromagnetic simulations and measurement, compared, and contrasted with the so-called 'straightforward' (SF) approach. The maximum operational frequency for the SF test structure was 10 GHz with zero margins for the serial bias (SB) current. Measurements of the GV structure at 10 GHz demonstrated a Bit Error Rate (BER) of 10 -12 with  5.8% margins for the SB current. We observed  the  correct  operation  of  the  5-island  DRP  chain  up  to  60 GHz  using  the  grapevine approach for SB current management. All chips were fabricated at MIT Lincoln Laboratory using the SFQ5ee fab node.

## 3.1 Introduction

As  mentioned  in  the  previous  Chapter,  the  growing  complexity  of  RSFQ  circuits  [12] requires reduction of the DC bias currents as the total bias current can become prohibitively large in  the  case  of  complex  designs,  reaching  a  level  of  several  amperes  per  chip  [14].  Large  bias currents are responsible for an excessive heat load through current leads [62], as well as for high

on-chip magnetic fields ([58], [59]). In addition, large bias currents are not easy to handle on chip because of some fabricated-related limitations ([9], [60], [61]). All these constraints renewed the interest in Serial Biasing (SB) as a promising current reduction technique ([47]-[49]).

In SB, the total DC bias current of a complex RSFQ circuit is reduced by partitioning a design  into  multiple  islands  with  equal  bias  currents  but  isolated  grounds.  The  bias  current  is applied to the 1 st island, then the 'used' bias current is picked up from the ground to bias the 2 nd island, and so on in a sequential manner. While SB has been demonstrated for circuits of different complexities ([50]-[53], [63], [64]) and fab processes ([51], [53], [64]), a more detailed analysis is required to make it reliable and applicable to complex circuits.

Figure 3.1: (a) The grapevine (GV) biasing technique is implemented on two serially biased islands using (d) the MITLL SFQ5ee metal layers' stack. Any bias -line-in has a dedicated ground-line-out to localize the magnetic fields in between the two metal layers and control the return current distribution. The dedicated pair of metal paths for current transfer through the M4 hole is formed by means of the double waterfall structure (b). The cross-section in (b) is made along the dashed line in (c). Not all layers are shown in (c) to avoid blocking the view of the M0 and M1 metal layers.

<!-- image -->

The design steps to implement serial biasing include circuit partitioning ([54], [55]); design and placement of pulse transfer circuits for inter-island communication ([51], [53]); and addressing bias current management issues [56].

The  grapevine  (GV)  biasing  approach  for  bias  current  management  was  introduced  in Chapter 2  and  described  in  detail  in  [56]  for  the  MIT-LL  SFQ5ee  fab  node  [9].  Figure 3.1 illustrates the GV approach through the example of 2 islands. The bias bus in M0 is used to provide a bias current to the 1 st island, where it is delivered through a single hole in M4 to a power grid formed in the M5 layer. The return current is picked up from M4 and transferred to M0 to be delivered to the 2 nd island. The key feature of the GV approach is that the return current always flows along a dedicated metal layer. It is either M2 for M0/M1 along vertical branches, M0 for M1 for the horizontal branches as shown in Figure 3.1(a). The M2 layer is connected to the global ground outside of the islands but does not touch the ground on the islands. The transfer through the M4 hole is organized in a similar way by means of a double waterfall structure that forms the dedicated pair of metal paths, as shown in Figure 3.1(b). As a result, the magnetic field is always localized  between  these  two  superconducting  paths,  and  the  image  current  distribution  on  the island is well-controlled.

Alternately,  if  biasing  is  done  in  a  'straightforward'  (SF)  manner  without  forming dedicated pairs of layers, the return current flows all over an island including its edges. In this case, operation of RSFQ circuitry can be disturbed by a local return current of high density. In particular, the drive-receiver pairs (DRPs), used for inter-island communication, are placed on the island's edges, and therefore can be affected by the image current distribution. The GV technique, on the other hand, was employed for serially biased circuits such as the 4-slice digital decimation filter and the 3x3 matrix of 3-to-2 parallel counters, in Chapter 2. Both circuits were successfully tested

at low and high frequencies. The 3x3 matrix demonstrated the correct operation up to 20 GHz with a  Bit  Error  Rate  (BER)  better  than  10 -12 .  In  this  Chapter,  we  focus  on  the  design  and characterization of the driver-receiver pair circuit employed in Chapter 2. In addition, we use the DRP testbed to compare the SF and GV biasing schemes.

As discussed in the previous Chapter, there are two different schemes for biasing RSFQ circuits  designed  for  the  MIT-LL  SFQ5ee  fab  node  [9].  One  approach  is  to  deliver  the  entire current through a single hole in M4 to a power grid formed in the M5 layer with further connections of individual bias resistors. Another approach is to design a power grid in the M0 layer and reach each bias resistor through individual holes in M4. In this Chapter, we analyze the former case i.e., a power grid formed in the M5 layer with a single hole in M4. Another case of multiple M4 holes to bias each Josephson Junction (JJ) individually is discussed in Chapter 4.

In section 3.2, the DRP's schematic and layout, as well as its testbeds are discussed. In section 3.3, we report on the SF and GV biasing test results. In section 3.4, electromagnetic (EM) simulations for the SF and GV testbeds are presented. We discuss the results in section 3.5 and conclude in section 3.6

## 3.2 Driver-Receiver Pair

## 3.2.1 Schematic, Layout, and Cross-Section

The schematic of the DRP is shown in Figure 3.2(a). An incoming SFQ pulse switches the driver's junctions JA1-JA3 and couples inductively to the receiver. On the receiver's side, both junctions JB1 and JB2 switch to let the pulse exit the DRP. The junction JA4 is an overshunted JJ to terminate pulses on the driver's side.

Figure 3.2: (a) The DRP schematic (a) comprises the driver's junctions on ground A and the receiver's junctions on ground B: JA1=250  A, JA2=350  A, JA3=488  A, JA4=158  A, JB1=94  A, JB2=131  A, IA1=175  A, IA2=245  A, IA3=344  A, IB1=71  A, IB2=100  A, LA1=2pH, LA2=2.7pH, LA3=2.1pH, LB1=2.7pH, LP=LS=5.8pH, and k=0.53. The DRP layout (b) is shown for MIT-LL SFQ5ee fab node. The shown layout occupies the area of 40  m x 65  m. All inductances, including the transformer with M4 and M7 holes, were calculated using InductEx software. The simplified cross section (c) is made along the line JA2-JA3-JA4 in (b).

<!-- image -->

The driver and receiver belong to different islands separated by moats in M4 and M7 layers as  seen  in  Figure 3.2(b).  The  layout  cross-section  in  Figure 3.2(c)  shows  that  the  M4  and  M7 ground moats are not only staggered but covered by metal layers M3 and M6 to minimize flux trapping [53]. Josephson junctions JA3 and JA4 are physically located above ground B but they are electrically connected to ground A using a 'tongue' that spreads over the M4 moat [49].

When using SF biasing, the current from ground A is transferred to the bias bus on island B at an arbitrary location. As seen in Figure 3.2(b), the serial bias current injection point 'SB IN' is  well  separated from the extraction point 'SF OUT' for the straightforward biasing approach. However, when using the GV biasing, the metal layer carrying the bias-current-in has a dedicated metal layer to carry the ground-current-out. The arrow symbols, labeled 'SB IN' and 'GV OUT', are placed above each other and point in the opposite directions. Note that the DRP's layout shown in Figure 3.2(b) allows us to implement both SF and GV biasing schemes by wiring islands in two different ways.

## 3.2.2 Simulation Results

The DRP testbench, comprised of 11 serially biased driver-receiver pairs separated by 2JJ JTLs, was simulated using PSCAN [70] and Spectre [41] software. Long non-trivial test patterns were applied to optimize the DRP circuit parameters and calculate the serial bias margins. The margins for the serial bias current are shown in Figure 3.3 at different frequencies for different sets of DRP parameters.

Let us start with the 'D' margins, which correspond to the set of default parameters, and note wide better than  25% bias margins at 10 GHz. These margins shrink only slightly (by 5%) at  40  GHz.  Beyond  40  GHz,  the lower  end  of  the  'D'  margins  starts  shrinking  quite  rapidly,

resulting in almost no operation at 60 GHz. An important observation here is that the center of the margin shifts upwards with frequency. At 60 GHz, the circuit does not work at the nominal bias current.

To plot the 'M' margins, we reduced the mutual inductances of all DRPs by 20% following the recent test results reported by MIT-LL. It was stated in [71] that vertically spaced inductors over an M4 ground plane hole may experience variations in their inter-layer dielectric thickness,

Figure 3.3: (a) Simulated margins for the normalized SB current as a function of the input frequency for different configurations of DRP parameters. The 'D' margins correspond to the default set of parameters. To calculate the 'M' margins, the mutual inductances in all DRPs were reduced by 20%. The 'C' margins are calculated considering parasitic capacitors placed in all DRPs. The 'L' and 'R' margins are calculated for counterclockwise and clockwise flux trapped in a transformer in a single DRP. The 'B' margins corresp ond to two fluxes of both polarities trapped in 2 DRPs.

<!-- image -->

possibly causing a reduction in the mutual inductance between them. The 20%-reduction in the mutual inductance manifests itself in abrupt shrinkage of the lower end of the 'M' margins at all frequencies. In the case of a weaker coupling, the DRP circuit starts malfunctioning in an underbiased regime.

The 'C'  margins  simulate  an  addition  of  parasitic  capacitors  Csga and  Csgb between  the signal  inductor  LA3  and  the  ground  plane  A  as  well  as  the  sky  plane  B.  The  island-to-island parasitic  capacitor  Cgg  in  the  area  where  grounds  overlap  between  moats  is  also  added  (see Figure 3.2 for details). We did not observe any change in margins compared to the default 'D' case.

We also tried to mimic a flux trapping in the DRPs transformer by placing a flux in the M4 and M7 holes and estimating the bias current disbalance caused by it. The 'L' margins reflect such an  effect  for  the  'trapped  flux'  current  flowing  through  LS  towards  the  left  junction  JB1  in Figure 3.2(a).  The  margins  shrink  at  the  upper  end.  This  happens  because  the  junction  JB1  is overbiased now. The 'R' margins are calculated for the 'trapped flux' current flowing towards the right  junction  JB2  in  Figure 3.2(a)  with  the  corresponding  shrinkage  of  the  lower  end  of  the margins. The margin changes are defined by junctions JB1 and JB2 because their critical currents are much smaller compared to JA3. All hole and mutual inductances were calculated for the layout in Figure 3.2(b) using InductEx software [72].

## 3.2.2 DRP Test Structures

Our test structures comprise of 5 serially biased islands populated by DRPs and JTLs as seen in Figure 3.4. Pseudo Random Bit Sequence (PRBS) generators [21] are used to supply test

Figure 3.4: (a) Two 5-island test structures biased according to SF (a) and GV (b) bias schemes. Both test structures are identical except for how the SB bias current injection and extraction are organized.

<!-- image -->

Patterns with 127-bit periodicity to the test structures. The outputs are controlled by either LF monitors [12] or HF output drivers based on stacks of SQUIDs, like drivers reported in [14]. Each island comprises circuitry to distribute both clock and data pulses. The total junction count per island is 20 with a nominal serial bias current of 3.2 mA.

Two test  structures  were  designed  to  compare  the  SF  and  GV  biasing  approaches.  As mentioned before, the DRP design shown in Figure 3.2 allowed us to implement both bias schemes by varying the inter-island wiring.

## 3.3 Test Results

The test structures were fabricated at MIT-LL using the SFQ5ee fabrication node [9] and tested  using  an  HYPRES  Integrated  Cryogenic  Electronic  Testbed  (ICE-T)  [34].  The  LF  test results,  obtained  at  254 kHz,  are  summarized  in  Figure 3.5.  We  tested  chips  from  different

locations across the fabricated wafer. In all cases, the GV test structures outperformed their SF counterparts. The smallest bias margins (  8%) in the GV case (location E4) are at least twice larger than the largest margins (  4%) observed in the SF case (location F4).

The digital output of the on-chip HF drivers was used to capture the PRBS data patterns for all high-frequency measurements. Bit error rate analysis was conducted to assess how well the test structure performed for a given set of bias conditions.

Two test  configurations  were  used  to  perform  high-frequency  measurements.  First,  an FPGA-based bit Error Rate Tester (BERT) measured the performance of both test structures at a fixed  clock  frequency  of  10.16 GHz  while  bias  conditions  were  modified.  A  Tektronix Oscilloscope (DSA72004B) was used to collect the BER estimates up to 60 GHz clock frequency.

Figure 3.5: LF bias margins for the SF (red) and GV (blue) test structures across different chip locations.

<!-- image -->

The FPGA-based BER analyzer, depicted in Figure 3.6, was implemented on a Xilinx VCU108 Evaluation Board which features an FPGA chip from the Xilinx UltraScale family. The Xilinx device includes several high-speed transceivers, called GTY, as input and output interfaces. These capable transceivers support line rates up to 30.5 Gbps. An amplifier preceded the FPGA input to increase the signal amplitude from the HF driver, located on the test structure chip, and to ensure compatibility with the semiconductor current mode logic (CML) standard that is used by the Xilinx transceivers.

The GTY transceiver captures the amplified and converted signal trace and provides the captured digital bit stream to the succeeding logic implementation that performs the Bit Error Rate analysis. The received data stream is expected to be a PRBS-7 sequence and is verified following the procedure described in [21]. All identified errors, as well as the total number of checked bits, are  accumulated  over  the  test  period  and  both  values  are  readout  from  a  control  computer  to calculate

Figure 3.6: Experimental setup and block diagram of the FPGA-based Bit Error Rate Tester (BERT). The computer allows the user to start a BER measurement and visualize the BER during the experiment.

<!-- image -->

the  observed  Bit  Error  Rate.  The  computer  and  FPGA  board  communicate  over  an  Ethernet connection. Both accumulators, the one for the total number of bits and the one for the total number of errors, can be reset by the user conducting the experiment through the control software, in order to start a new measurement.

We  observed  5.8%  margins  with  BER  better  than  10 -12 in  the  GV  case  as  seen  in Figure 3.7. The SF-biased structure demonstrated zero margins at this level of BER. Note that the right BER curves almost coincide in Figure 3.7 in contrast to the left curves.

We  also  tested  the  GV  structure  at  10.16 GHz  multiple  times,  performing  a  deflux procedure  before  each  test.  This  entails  warming  the  superconductor  chip  above  the  critical temperature and cooling it back down. The test results are presented in Figure 3.8. The GV test structure performed repeatedly well, not showing much variation between defluxes.

Besides this, we examined the GV test structure by running an output waveform stability test using an oscilloscope at frequencies up to 60 GHz. Any HF driver, depicted in Figure 3.4, is preceded by a T-Flip-Flop [12] which makes a driver very sensitive to a variation in input pattern.

Any missed or added pulse manifests itself by 'flipping' the oscilloscope trace. This can be used to determine margins and estimate the BER. The margins as a function of frequency are shown in Figure 3.9 for a BER better than 10 -12 .  The BER was estimated by monitoring stable output on the oscilloscope for a specific time interval at a particular frequency. For example, at 40 GHz, a stable output was observed on the oscilloscope for 1 minute,  which implied a BER better than 10 -12 . The correct operation of the test structure was recorded up to 60 GHz with some margin degradation above 40 GHz. Note that at 10 GHz, the waveform stability test gives  6% margins. These are very close to the results obtained from the FPGA-based measurements.

Figure 3.7: BER curves versus serial bias current at 10.16 GHz for the 2 biasing schemes. The GV (blue) margins are wider compared to the SF (red) case and reach the BER level of 10 - 12 .

<!-- image -->

Figure 3.8: BER curves for the GV test structure after 4 deflux procedures.

<!-- image -->

Figure 3.9: Normalized serial bias current versus clock frequency for the GV test structure. Data are obtained by running the output waveform stability test to maintain the BER level better than 10 -12  (see text for details).

<!-- image -->

These findings validate the use of the output waveform stability test as a method to determine a BER with less specialized equipment needed.

The maximum operational frequency for the SF-biased test structure was 10 GHz with zero margins for the SB current. It should be compared with 60 GHz of maximum frequency and nonzero margins in the GV case. The GV test structure outperformed its SF counterpart at HF as well as at LF.

## 3.4 EM Simulations

## 3.4.1 Simulating the DRP Test Structure

The  ground  current  density  distribution  over  an  island  is  an  important  design  metric. Regions of high density can couple to the signal inductors, magnetically bias JJs and reduce circuit margins, or even render the circuit nonfunctional.

To investigate the distribution, we used Sonnet Software [66] to simulate 2-island versions of the test structures depicted in Figure 3.4. To keep the layout complexity manageable, all JJs and inessential metal objects were removed, while retaining the M4 ground plane, power grid, and bias network with resistors connected to the M4 ground.

Figure 3.10(a) shows the simplified 2-island layout in the SF case. Each island is formed by a rectangular moat. The positions of the receivers are easy to identify by transformers' holes in M4. Two rows of DRPs are seen in Figure 3.10(a), they are for data and clock streams according to the block diagram in Figure 3.4. Biasing inside of DRPs and JTLs is provided in the M5 layer (red),  while  the  bias  current  to  the  first  island  and  from  the  second  island  over  the  moats  is delivered by means of the M6 layer (blue). The points where the bias current enters, transfers between,  and  exits  islands  are  marked  by  arrows  in  Figure 3.10(a).  The  bias  current  flow  is organized in a 'straightforward' manner, resulting in the above-mentioned current transfer points being well separated from one another. Please note that there is only one island-to-island transfer

Figure 3.10: The simplified layout of (a) the 2-island SF DRP test structure and (b) the calculated current distribution in M4 ground plane. The bias current is injected to the first island, transferred to, and extracted from the second island as marked by arrows in (a). The red straight segments in (b) correspond to the elements of the power grid where the bias current was expected to accumulate.

<!-- image -->

Figure 3.11: The simplified layout of (a) the 2-island GV DRP test structure and (b) the calculated current distribution in the M4 ground plane. Any metal layer used to carry the incoming current has a corresponding dedicated metal layer to carry the outgoing current as marked by the arrows in (a). For comparison, the labeled locations in (b) are identical to those selected in the SF case (Figure 3.10(b)).

<!-- image -->

point (the horizontal arrow in Figure 3.10(a)) that makes the current distribution in the top and bottom DRPs unequal.

The current density distribution in M4 for the SF case is presented in Figure 3.10(b). Note that the current distribution over the island is non-uniform. Signal inductors, transformers, and JJs are particularly sensitive to these variations in the current density distribution. Several of these locations of interest are labeled in Figure 3.10(b), with their corresponding current density values in Table 3.1. The ground current density in the GV case is quite uniformly distributed all over the island, as seen in Figure 3.11(b). As a result, the ratio of SF to GV current densities varies from 6 to 95. So, an implementation of the grapevine current management technique allows us to reduce the current density by a factor of 100 in some locations.

Please note that for all the simulation results presented in this Chapter, the current map scale  is  fixed  from  0  (blue)  to  1500  (red)  A/m  as  shown  in  the  insets  of  Figure 3.10(b)  and Figure 3.11(b). Please also note that all layout elements for the GV simulations in this Chapter were  borrowed  from  the  design  of  the  3 x 3  matrix  of  3-to-2  parallel  counters  discussed  in Chapter 2. The GV power grid in Chapter 2 was designed to support 160 mA of maximum bias current.

Table 3.1: Current Density Distribution in SF a  and GV b  biasing cases

| Location   |   SF Density (A/m) |   GV Density (A/m) |   SF to GV Density Ratio |
|------------|--------------------|--------------------|--------------------------|
| A          |                620 |                 40 |                     15.5 |
| B          |                600 |                 40 |                     15   |
| C          |               1600 |                 40 |                     40   |
| D          |                260 |                 40 |                      6.5 |
| E          |               3300 |                 35 |                     94.3 |
| F          |               2400 |                 35 |                     68.6 |
| G          |                120 |                 20 |                      6   |
| H          |                510 |                 20 |                     25.5 |

According to the MIT-LL design rules for the SFQ5ee fab node [9], the maximum current carrying capacity for metal layers is 40 mA per 1  m of width, which translates into a 4  m minimum width of any metal layer to support 160 mA. Any transition between metal layers involves a layer-tolayer via or a set of vias. The MIT-LL design rules guarantee the maximum current of 20 mA per 2  m x 2  m via with 1  m x 1  m opening in the insulator between metal layers. As a result, a group of 8 parallel vias with a total width of 16  m needs to be assembled to maintain 160 mA of total bias current flowing perpendicularly.

## 3.4.2 Current Distribution in the Source and Drain Vias

As discussed in section 3.1 and depicted in Figure 3.1(b), the current transfer through an M4 hole, to deliver the bias current from under to above the M4 ground, is organized as a double waterfall structure that forms the dedicated pair of paths in the GV biasing case.

In Figure 3.12(a) the source group of 8 parallel vias for the bias current flowing up (M1to-M6) and the drain group of vias for the return current flowing down (M5-to-M0) reside in the same M4 hole. There is also a pickup group of vias (M4-to-M5) to collect the return current on the M4 ground for further delivery through the M5 layer to the drain vias in the M4 hole.

We simulated the  layout  in  Figure 3.12(a)  using  the  Sonnet  software  [66].  The  current density distribution in the M4 layer is presented in Figure 3.13(a). The current densities in all eight source (A-H), drain (I-P), as well as the pickup (S-Z) vias are reported in Table 3.2. One can see that the current is uniformly distributed through all the individual vias. In addition, there is no current flowing around the M4 hole (locations Q and R in Figure 3.13(a)). Such a uniform current distribution between all individual vias, as well as almost no current in the locations Q and R, is achieved in the GV case by employing the dedicated pair of layers placed above each other.

Figure 3.12: Layouts of serially biased island with the GV(a) and SF (b) biasing. In both cases, bias current enters and exits the island from top and bottom (white arrows). The load circuit consists of 5 identical resistors connected to M4 ground. In contrast to the dedicated pairs of layers in the GV case (a), the metal layers for current flowing in and out do not overlap for the SF biasing (b).

<!-- image -->

Let us compare it with the SF layout depicted in Figure 3.12(b), where the metal layers to carry current in and out do not overlap. The simulation results are shown in Figure 3.13(b)

Figure 3.13: The current density distribution in the M4 ground layer is shown for GV (a) and SF (b) biasing cases. The regions shown correspond to the dashed rectangles marked in Figure 3.12(a) and Figure 3.12(b).

<!-- image -->

and  compared  in  Table 3.2.  As  expected,  the  bias  current  is  spread  unequally  between  the individual source vias in the M4 hole. As a result, the bias current through vias A and H can exceed the maximum current value and cause overheating of all the vias in the group. In addition, the large

Table 3.2: Current Density Distribution in Source and Drain Vias for GV a  and SF b without M7 Sky Plane

| GV-Source-Hole   | GV-Source-Hole   | GV-Drain-Pickup   | GV-Drain-Pickup   | SF-Source   | SF-Source     | SF-Drain-Pickup   | SF-Drain-Pickup   | SF-Source/GV- Source   | SF-Source/GV- Source   |
|------------------|------------------|-------------------|-------------------|-------------|---------------|-------------------|-------------------|------------------------|------------------------|
| Location         | Density (A/m)    | Location          | Density (A/m)     | Location    | Density (A/m) | Location          | Density (A/m)     | Location               | Density (A/m)          |
| A                | 1396             | S                 | 1350              | A           | 3300          | S                 | 1400              | A                      | 2.4                    |
| B                | 1362             | T                 | 1339              | B           | 1035          | T                 | 1360              | B                      | 0.8                    |
| C                | 1330             | U                 | 1345              | C           | 620           | U                 | 1350              | C                      | 0.5                    |
| D                | 1330             | V                 | 1351              | D           | 540           | V                 | 1350              | D                      | 0.4                    |
| E                | 1330             | W                 | 1350              | E           | 540           | W                 | 1380              | E                      | 0.4                    |
| F                | 1360             | X                 | 1351              | F           | 680           | X                 | 1350              | F                      | 0.5                    |
| G                | 1365             | Y                 | 1347              | G           | 1057          | Y                 | 1370              | G                      | 0.8                    |
| H                | 1390             | Z                 | 1364              | H           | 3300          | Z                 | 1420              | H                      | 2.4                    |
| Q                | 3                |                   |                   | Q           | 4800          |                   |                   | Q                      | 1600                   |
| R                | 3                |                   |                   | R           | 4800          |                   |                   | R                      | 1600                   |

Table 3.3: Current Density Distribution in Source and Drain Vias for GV a  and SF b with M7 Sky Plane

| GV-Source-Hole   | GV-Source-Hole   | GV-Drain-Pickup   | GV-Drain-Pickup   | SF-Source   | SF-Source     | SF-Drain-Pickup   | SF-Drain-Pickup   | SF-Source/GV- Source   | SF-Source/GV- Source   |
|------------------|------------------|-------------------|-------------------|-------------|---------------|-------------------|-------------------|------------------------|------------------------|
| Location         | Density (A/m)    | Location          | Density (A/m)     | Location    | Density (A/m) | Location          | Density (A/m)     | Location               | Density (A/m)          |
| A                | 1396             | S                 | 1350              | A           | 2100          | S                 | 1480              | A                      | 1.5                    |
| B                | 1362             | T                 | 1339              | B           | 1243          | T                 | 1407              | B                      | 0.9                    |
| C                | 1330             | U                 | 1345              | C           | 1141          | U                 | 1325              | C                      | 0.9                    |
| D                | 1330             | V                 | 1351              | D           | 1111          | V                 | 1340              | D                      | 0.8                    |
| E                | 1330             | W                 | 1350              | E           | 1091          | W                 | 1340              | E                      | 0.8                    |
| F                | 1360             | X                 | 1351              | F           | 1137          | X                 | 1360              | F                      | 0.8                    |
| G                | 1365             | Y                 | 1347              | G           | 1203          | Y                 | 1386              | G                      | 0.9                    |
| H                | 1390             | Z                 | 1364              | H           | 2100          | Z                 | 1480              | H                      | 1.5                    |
| Q                | 3                |                   |                   | Q           | 1400          |                   |                   | Q                      | 466.7                  |
| R                | 3                |                   |                   | R           | 1300          |                   |                   | R                      | 466.3                  |

current densities were observed in the locations Q and R because the absence of a dedicated return path in the M4 hole forces the return current to flow around the hole.

The situation can be improved by adding an M7 sky plane spanned all over the island, including the M4 hole, and connected to the M4 ground plane at multiple locations. The simulation results are presented in Table 3.3. In this case, the bias current is spread more equally between individual vias (A-H) and the current densities around the M4 hole are lower. However, the current distribution in individual vias and around the M4 hole is still worse compared to the GV biasing technique.

## 3.4.3 Simulating the Position of Drain vias in the GV Biasing Case

Placing the drain vias inside the M4 hole in the GV case requires another metal layer, usually M5, to connect it to the pickup vias (see Figure 3.1(b) for the cross-section). The design can be simplified by moving the drain vias out of the M4 hole and combining it with the drain vias while maintaining the double waterfall structure. In Figure 3.14, the drain vias are moved from the hole to the edge of the M4 ground (a) or even 8  m away from the edge (b).

The  simulation  results  are  presented  in  Figure 3.15  and  summarized  in  Table 3.4.  The results should be compared with the layout depicted in Figure 3.12(a). There is not much variation in current densities either for source or drain vias in all 3 cases. Note that the current distribution becomes slightly worse for vias moved 8  m away, probably because of increasing the separation in the dedicated pair of paths. So, the placement of the drain vias in the M4 hole is not required. However, it helps a designer to stick to the GV rules.

Figure 3.14: Layouts of serially biased islands with GV biasing. In (a), the drain vias are located at the edge of the hole, and in (b), they are located away from the hole at an 8  m distance.

<!-- image -->

Figure 3.15: The current densities distribution in the M4 ground plane is shown for different locations of the drain vias in the GV biasing case. The M4-to-M0 drain vias (I-P) are moved from the hole to the edge of the M4 ground (a) or placed 8  m away from the hole edge. The regions shown correspond to the dashed rectangles marked in Figures 3.14(a) and 3.14(b).

<!-- image -->

Table 3.4: Current Density Distribution in Source and Drain Vias for Different Positions of Drain Vias in GV Biasing case

| Source Via Locations   |   GV-hole Density (A/m) |   GV-edge Density (A/m) |   GV-8 µm Density (A/m) | Drain Via Locations   | GV-hole Density (A/m)   | GV-edge Density (A/m)   | GV-8 µm Density (A/m)   |
|------------------------|-------------------------|-------------------------|-------------------------|-----------------------|-------------------------|-------------------------|-------------------------|
| A                      |                    1396 |                    1390 |                    1394 | I                     | 1370                    | 1350                    | 1343                    |
| B                      |                    1362 |                    1325 |                    1325 | J                     | 1335                    | 1332                    | 1335                    |
| C                      |                    1330 |                    1326 |                    1315 | K                     | 1333                    | 1344                    | 1335                    |
| D                      |                    1330 |                    1320 |                    1315 | L                     | 1350                    | 1338                    | 1340                    |
| E                      |                    1330 |                    1322 |                    1320 | M                     | 1350                    | 1328                    | 1350                    |
| F                      |                    1360 |                    1325 |                    1315 | N                     | 1350                    | 1342                    | 1335                    |
| G                      |                    1365 |                    1330 |                    1334 | O                     | 1340                    | 1338                    | 1330                    |
| H                      |                    1390 |                    1395 |                    1385 | P                     | 1375                    | 1350                    | 1350                    |
| Q                      |                       3 |                      10 |                      50 |                       |                         |                         |                         |
| R                      |                       3 |                      10 |                      50 |                       |                         |                         |                         |

## 3.4.4 Simulating M6 Extension over M4-to-M5 Vias

As mentioned before, in this Chapter, we discuss simulation results for the layout elements used in in Chapter 2, to support 160 mA of bias current. According to the MIT-LL design rules for the SFQ5ee fab node [9], the 160 mA bias current requires at least a 4  m-wide metal layer and a 16  m-wide group of 8 parallel vias to change a layer. So, we need to discuss how to organize such a 16  m-to-4  m transition in the proximity of a group of vias to minimize the area occupied by a power grid.

The typical situation is depicted in Figure 3.16(a). The bias current flows from the top to the right through the M4 hole and using the double waterfall structure. The width of the M6 layer changes from 16  m to 4  m after passing the pickup vias with 4  m extension to allow the bias current  to  redistribute.  Simulations  indicate  that  such  a  change  in  width  of  M6  results  in  the unequal current distribution in the parallel group of pickup vias (S-Z) as shown in Figure 3.17(a). The current distribution is summarized in Table 3.5 and should be compared with the simulation results for the layout implementation without narrowing as shown in Figure 3.13(a). An extension

Figure 3.16: The M6 strip changes its width from 16  m to 4  m after passing the group of pickup vias with 4  m extension (a) and 8  m extension combined with 2 chamfers (b) to let the return current redistribute equally between the individual pickup vias.

<!-- image -->

of 8  m (half the width) helps to improve the equality, but the better result is achieved by using the 8  m extension together with 2 chamfers to avoid 90-degree turns as illustrated in

Figure 3.17: The current distribution for two implementations of the GV biasing approach depicted in Figure 3.16. The return current is unequally (a) and equally (b) distributed between individual pickup vias (S-Z). The regions shown correspond to the dashed rectangles marked in Figures 3.16(a) and 3.16(b).

<!-- image -->

Figure 3.16(b) and Figure 3.17(b). According to Table 3.5, the variation in current is negligible in this case.

Table 3.5: M4-to-M5 (Pickup Vias) Current Density

| Via Location   |   Current Density a (A/m) for 4  m long M6 extension |   Current Density b (A/m) for 8  m long M6 extension |   Current Density c (A/m) for 8  m long M6 extension with chamfers |
|----------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------|
| S              |                                                  1110 |                                                  1280 |                                                                1310 |
| T              |                                                  1295 |                                                  1344 |                                                                1335 |
| U              |                                                  1510 |                                                  1424 |                                                                1368 |
| V              |                                                  1692 |                                                  1470 |                                                                1378 |
| W              |                                                  1657 |                                                  1460 |                                                                1380 |
| X              |                                                  1446 |                                                  1390 |                                                                1367 |
| Y              |                                                  1320 |                                                  1320 |                                                                1341 |
| Z              |                                                  1114 |                                                  1250 |                                                                1305 |

## 3.5 Discussion

## 3.5.1 Model-to-Hardware Correlation

The GV version of the 5-island experiment outperformed its SF counterpart at LF and HF frequencies.  However,  the  measured  bias  margins  are  much  smaller  than  expected  from simulations, say  6% in experiment (Figure 3.8) versus  20% in simulations (the 'D' margins in Figure 3.3) at 40 GHz.

There are several factors that can reduce the experimental margins. Some of them are listed in section 3.2 and the related simulated margins are depicted in Figure 3.3.

The first factor is reduction of the mutual inductance in the DRP transformer caused by variation in the dielectric thickness [71]. According to [71], the reduction could potentially reach 20%.  To  investigate  this  further,  we  designed,  got  fabricated  and  measured  SQUID  based structures  comprising  the  primary  and  secondary inductors  of  the  DRP  transformer,  as  seen  in Figure 3.18(a) and Figure 3.18(c). The layouts in Figure 3.17(b) and Figure 3.17(d) are used to

extract the inductances from InductEx and compare the measurement data with the simulation. Our measurement of the test structures placed on different wafers are summarized in Table 3.6.

<!-- image -->

SQUID Test structure to measure LP and M (a)

<!-- image -->

SQUID Test structure to measure LS and M (c)

Layout used for Inductance Extraction (b)

<!-- image -->

Layout used for Inductance Extraction (d)

<!-- image -->

Figure 3.18: The SQUID-based test structures (a) and (c) are used to measure the LP and LS for the DRP transformer (seen in the yellow box) respectively. The mutual inductance (M) is obtained from both structures. These were designed, fabricated, and tested in the MITLL SFQ5ee 10kA/2  fab node. The layouts of (b) and (d) were used to extract the LP, LS respectively, and M, in simulation.

The mutual inductance reduction did not exceed 5% compared to the mutual inductance calculated using InductEx [72]. While the circuit parameters obtained in this measurement help  establish correlation with measurement, the DRP transformer inductances in a real serially biased circuit

would be different due to the layout differences. This is evident from the LP values in Table 3.6, obtained from the SQUID measurement and simulation when compared to the LP values used in

Table 3.6: DRP Transformer Inductances (Measured versus Simulated)

| Chip Location   | Inductance   |   Measured (pH) |   Simulated (pH) | Difference in measured with respect to simulated   |
|-----------------|--------------|-----------------|------------------|----------------------------------------------------|
| D5              | LP           |            4.98 |             4.97 | +0.2%                                              |
| G6              | LP           |            4.94 |             4.97 | -0.6%                                              |
| D5              | LS           |            5.9  |             5.86 | +0.7%                                              |
| G6              | LS           |            5.9  |             5.86 | +0.7%                                              |
| D5              | M a          |            3.23 |             3.34 | -3.3%                                              |
| G6              | M a          |            3.18 |             3.34 | -4.8%                                              |
| D5              | M b          |            3.18 |             3.31 | -3.9%                                              |
| G6              | M b          |            3.18 |             3.31 | -3.9%                                              |

the DRP (see Figure 3.2). The latter is higher due to separate ground planes used for inductance extraction. In summary, a reduction in mutual inductance of the fabricated transformer is quite possible, but 20% could be an overestimate.

Another potential mechanism is the flux trapping in the transformer hole. The current from the trapped flux could couple to LP and/or LS. This is better understood from the transformer cross-section shown in Figure 3.19. In Figure 3.19(a), the strongest coupling exists between the LP and LS inductors, as is expected of a transformer. However, weak coupling could also exist between the M4 and M7 ground holes and the nearest signal inductors, and hence this should be modeled in the circuit simulation, to model the effect of flux trapping.

The CCW and CW fluxes in the ground holes would induce currents in LP and LS in the opposite  direction,  as  seen  in  Figure 3.19(b)  and  Figure 3.19(c).  The  simplified  layout  of Figure 3.20 is used to simulate the weak coupling factors between the M4 ground plane hole and

q

q

the LP, LS inductors, in InductEx. Similarly, coupling factors between the M7 ground plane hole and the LP, LS inductors are also calculated. Flux coupling diagram and sign convention

Figure 3.19: DRP cross-section (a) shown with all forms of coupling between metal layers. The sign convention for counterclockwise (CCW) and clockwise (CW) flux trapping is shown in (b) and (c) respectively. Flux trapped in M4 hole, coupling to LP and LS : Corrected Analysis Strongest coupling exists between the LP and LS of the transformer. Next, is the coupling between M4,M7 ground holes and nearest transformer inductors. Weak coupling exists between M4,M7 grounds and faraway transformer

<!-- image -->

inductors. (a)

Counterclockwise ground flux induces current in clockwise direction in the transformer inductors and vice-versa

(b), (c).

rietary (Not to be Shared)

q

<!-- image -->

* (1/LP) = 7.1uA

q

I

= (phi0/LM4)*MM4-LS

* (1/LS) = 40.5uA

Figure 3.20: Simplified layout to calculate coupling between M4 ground hole inductor and LP, LS signal inductors of the DRP. InductEx reports a value of LM4 ~10 pH, a value in close agreement with a washer inductance of similar geometry reported in [73]. M4-LS q I M4-LS /I C,JB1 =  0.43 and I M4-LS /I C,JB2 = 0.31 (I C,JB1 = 93.75uA, IC,JB2 = 131.25uA) q These are large ratios, hence will impact margins when modelled as extra biases for JB1 and JB2. M4-LP q I M4-LP /I C,JA3 =  0.015 (I C,JA3 = 487.5uA) q This is a small ratio and hence ignored.

I

PRES Proprietary (Not to be Shared)

= (phi0/LM4)*MM4-LP

Inductances simulated from the layout in Figure 3.20 would yield LM4 , MM4-LP and MM4-LS . (shown in Table 3.7). The additional current circulating in the SQUID loops consisting of LP and LS could then be calculated approximately as:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Table 3.7: Mutual Inductances for weak coupling between ground holes (M4 and M7) and signal inductors (LP and LS)

| Mutual Inductance   |   LP (pH) |   LS (pH) |
|---------------------|-----------|-----------|
| L M4_hole           |      0.13 |      1.45 |
| L M7_hole           |      1.7  |      0.49 |

These currents can now be modeled in the simulation as overbiasing or under biasing the receiver junctions JB1 and JB2, ensuring consistency with the sign convention adopted (Figure 3.19(b) and Figure 3.19(c)).

Based on this analysis, the 'L' margins in Figure 3.3 are calculated for the CCW current in the M4 and M7 holes, while the 'R' margins correspond to the CW current. To calculate 'L' or 'R' margins, only one DRP in the middle of the DRPs' chain in Figure 3.4(b) was modified.

Please note that the serial bias margins are affected quite differently by factors discussed above, and both ends of margins are reduced. Several factors, being combined, can cause a major reduction in the margins. For example, 2 fluxes trapped in 2 different DRPs but with different current polarities cause shrinkage on both ends, as depicted in the 'B' case in Figure 3.3.

According to Figure 3.7, the 5-island structure behaved similarly after different defluxes. It can be an indication that staggering of the ground moats and shielding them by extra metal layers

[53] protect the DRP quite effectively. However, it can be also explained by constant flux trapping of both polarities in the transformer holes.

The nominal bias current for our 5-island experiment is 3.2 mA. The measured bias current was larger, 3.45 mA, according to Figure 3.7, which can be explained by a fab variation in the current density. However, all our serially biased circuits (discussed in Chapters 2 and 4) for other GV-biased structures also required larger than nominal bias currents for reasons not entirely known for now. Please note that the 'B' margins in Figure 3.3 are shifted up, towards larger bias currents, because of flux trapping.

## 3.5.2 80-Island Experiment and Future Steps

The experiments in this Chapter have been limited to 5 island DRP chains, however, it is essential to examine the effect of a small serial bias current, but a large accumulated voltage drop across the DRP chain. We designed, got fabricated, and tested an 80-island DRP chain experiment (see [64] for a similar experiment, but a different fab node), shown in Figure 3.21, in the MIT-LL SFQ5ee 10kA/2Ω fab node. The 80 islands were biased using  the  SF  biasing  scheme,  as  this experiment was performed prior to the development of the GV biasing scheme.

At LF, across multiple chip locations, a ±10% serial bias margin was obtained using the Octopux [68] measurement setup. At high frequencies, however, the bias margins degrade very fast.  The  circuit  was  operational  at frequencies  as  high  as  50  GHz,  but  with  no  open  margins. Figure 3.22  shows  the  divided  output  corresponding  to  the  50  GHz  input,  on  a  high-speed oscilloscope.  Note  that  this  experiment  is  limited  because  only  a  periodic  input  pattern  can  be provided  at  HF.  However,  as  discussed  earlier  in  this  Chapter,  a  (pseudo)  random  pattern  is required for accurate data-link testing.

Figure 3.21: 16 island (4 rows) example of the serially biased JTL circuit. The experimental circuit has a total of 80 islands (20 rows). The divide-by-32 circuit used preceding the pre and post-island outputs allows for HF characterization. SF biasing is not shown in the diagram.

<!-- image -->

Figure 3.22: The divided output is seen at 1.56 GHz. This corresponds to an input frequency of 49.92 GHz. Increasing or decreasing the serial bias current results in an unstable waveform.

<!-- image -->

The improved performance (especially at HF) of the 5-island GV-biased test structures (compared to its SF-biased counterpart), discussed earlier in the Chapter, is quite encouraging. However, it is important to expand this experiment into the 'GV-biased' 80-island test structure to observe  the  effectiveness  of  the  GV  technique  across  multiple  islands.  This  future  activity  is required to make the GV-biased technique mature enough for wide usage in RSFQ circuits.

We also need to address the problem of flux trapping in the M4 hole by perhaps designing more sophisticated transformers (see, e.g., [51]). Finally, we need to apply the GV serial biasing approach to energy-efficient RSFQ (ERSFQ) circuits [29] to reduce power consumption.

## 3.6 Conclusion

We designed a driver-receiver pair (DRP) for serially biased RSFQ circuits and tested it up to  60  GHz  with  a  BER  of  10 -12 .  It  was  proven  that  the  grapevine  (GV)  biasing  approach outperformed its counterpart without dedicated return current paths. We demonstrated that the GV technique must be used for bias current values as low as 1 mA. We extensively simulated our test structure using Sonnet software and confirmed a uniform current density distribution in a ground plane of an isolated island. We also provided recommendations for all layout primitives required to implement the grapevine biasing in RSFQ circuits.

## Chapter 4: Serial Biasing Technique for Electronic Design Automation in RSFQ Circuits

There has been renewed interest and efforts in increasing the complexity of superconductor circuits using electronic design automation (EDA). Serial Biasing (SB) is a technique that reduces the total DC bias current required by large Rapid Single Flux Quantum (RSFQ) circuits, including its energy-efficient variant, ERSFQ. We believe SB needs to be incorporated in any EDA flow for large circuits. In SB, equally biased circuit blocks are placed on galvanically isolated islands and biased in series. SFQ pulses are transferred across the islands using driver-receiver pairs (DRPs). The special current management technique called the grapevine (GV) approach and introduced in Chapter 2, is used to handle the bias current flowing in and out of an island. In this Chapter, we present all required layout primitives needed to implement SB for the IARPA-led SuperTools (ST) cell library that targets the SFQ5ee fab node at MIT Lincoln Laboratory. We discuss the horizontal and  vertical  composite  driver-receiver  pairs  (CDRPs)  that  comprise  not  only  DRPs  but  also transmitters and receivers for passive transmission lines (PTLs). We present the basic blocks to implement the GV bias current managing technique for current injection and extraction. As a proof of concept, we designed a 4-island test circuit that comprises all discussed layout primitives and employs an on-chip pseudo-random binary sequence (PRBS) generator circuit as a test pattern source. The test circuit worked up to 50 GHz at the BER level of 10 -12 . Future steps to improve the serial biasing technique for EDA tool-based design flow are also discussed.

## 4.1 Introduction

The IARPA-led SuperTools (ST) program [46] aims to increase the complexity of RSFQ [12]  and  ERSFQ  [29]  circuits  by  developing  EDA  tools  for  cell  library-based  synthesis  and automatic  place  and  route  (P&amp;R)  ([42],  [74]).  As  part  of  this  effort,  the  dual  RSFQ/ERSFQ

standard cell library has been developed [57]. While automation potentially reduces the design effort, large circuits cannot be synthesized without taking their DC bias current requirements into consideration  as  well.  An  RSFQ  circuit  that  comprises  10 6 Josephson  Junctions  (JJs)  with  an average bias current of 100 µA per JJ will require a total bias current of 100A. See [14] for an example of a practical, meaningful circuit with 10 4 JJs and about 1A of the total bias current. Large bias currents need many current leads for the current delivery, which increases the associated heat load  [62].  Large  currents,  successfully  delivered  to  a  chip,  are  difficult  to  handle  because  of fabrication limitations (e.g., the limited current capacity of Nb wires and layer-to-layer vias ([9], [60], [61]) as well as magnetic fields produced in the proximity of RSFQ/ERSFQ circuits that can limit or even destroy their operation [12]. Hence any EDA tool must address bias current reduction during synthesis.

Serial Biasing (SB) is an effective bias current reduction technique where a large RSFQ circuit is divided into smaller circuit blocks with equal bias currents. Each circuit block is placed on its own island with isolated ground ([47]-[49]). Bias current is provided to the islands in a serial manner: the current used to bias the n th island is picked up from the ground of the n th island and 'reused' to bias the (n+1) th island. As a result, the total current reduction is roughly equal to the number of circuit blocks or isolated islands.

Serially  biased  circuits  of  various  complexity  have  been  demonstrated  for  different fabrication processes ([50]-[53], [56], [64]), and, more recently, algorithms to partition circuits into islands have also been introduced ([54], [55]). However, the design primitives required to integrate  it  into  a  cell  library-based  synthesis  and  automatic  P&amp;R  flow,  and  the  associated assembly rules have not been discussed before. In this Chapter, we focus on developing building

blocks (design primitives) needed to apply SB to the ST standard cell library, which is specific for the 100 µA/ µm 2  MIT-LL SFQ5ee fab node [9].

There are at least two key design issues to be addressed for a successful SB implementation. The first is the design of a reliable Driver-Receiver Pair (DRP) to transfer clock and data pulses between islands. Usually, SFQ pulses are transferred from the driver on one island to the receiver on another island by means of inductive coupling. Several DRPs were designed and experimentally verified ([51]-[53], [64]). In Chapter 3, we report a DRP, working at frequencies up to 60 GHz with a bit-error rate (BER) better than 10 -12 .

The second issue is managing bias and return currents on an island. Current management addresses bias current injection into an island, extracted from the ground plane, and transfer to the neighboring  island.  The  grapevine  (GV)  biasing  approach  introduced  in  Chapter 2,  has  been verified by testing relatively complex circuits at low (LF) and high (HF) frequencies. Those test results include LF operation of a serially biased 4-slice digital decimation filter (DDF) circuit and a 3 × 3 matrix of serially biased 3-to-2 counters with a BER better than 10 -12 at 20 GHz.

The goal of this Chapter is to adapt the results reported in the previous 2 Chapters to the RSFQ/ERSFQ  standard  cell  library  [57].  In  section 4.2,  the  design  primitives  required  to implement SB are described. In section 4.3, we focus on the design strategy to assemble a serially biased circuit. A test circuit is presented, and its measurement results are discussed. In section 4.4, we report on the electromagnetic (EM) simulations of the SB components. Finally, in section 4.5, some drawbacks are listed, and possible solutions are discussed. We conclude in section 4.6.

## 4.2 Design Primitives Required for Serial Biasing

## 4.2.1 Grapevine Biasing for the MIT-LL SFQ5ee Fabrication Node

The grapevine (GV) biasing approach is presented in Figure 4.1 for the MIT-LL SFQ5ee fabrication node [9], where Josephson Junctions are formed between the metal layers M5 and M6, and digital circuits are usually designed in between the ground (M4) and sky (M7) planes. The underground metal layers (below M4) are employed for biasing (M0), extra grounding (M1), and passive transmission lines (M2, M3) [57].

As seen in Figure 4.1 for the 2-island example of SB, the bias current (black arrows) is injected into the 1 st island through a horizontal M0 (yellow) bus and is distributed to the design under test (DUT) through a vertical M0 segment. Current from the isolated M4 (orange) ground is picked up and transferred into the M0 bus using M1-to-M0 vias and then exits the 1 st island. The 2 nd island is biased in a similar manner.

The key component of the grapevine biasing is the introduction of an extra M2 ground (shown in green) [56] that is connected to the global ground outside of the islands (through

Figure 4.1: The grapevine biasing technique implemented on 2 serially biased islands (a) for the MIT-LL SFQ5ee layers stack (b) (see text for details).

<!-- image -->

M2-to-M4 vias) but does not touch the grounds on the islands. As a result, return currents (white arrows) flow along the M2 ground, serving as a dedicated path, leaving the isolated M4 ground almost free from image currents. In absence of the extra M2 ground, the vertical segments of M0 and M1 buses form another dedicated pair of metal layers to handle current-in (black arrows) and current-out (purple arrows), keeping the isolated M4 ground minimally disturbed.

Return currents are considered a major problem for the serial biasing technique because they can create areas of high current density and, as a result, disturb the normal operation of digital circuits  and  especially  DRPs  placed  on  islands'  edges.  The  introduction  of  a  dedicated  pair  of layers at every stage of current distribution mitigates this problem and is confirmed in simulations and experimentally [56].

## 4.2.2 DRP's Core Design

The core of the DRP comprises 4 Josephson Junctions (JJs) on the driver side and 2 JJs on the receiver side, as seen in Figure 4.2(a). An SFQ pulse switches junctions JA1, JA2, and JA3 in succession  and  couples  inductively  to  the  receiver  junctions  JB1  and  JB2  to  transfer  between islands. JA4 is an overshunted junction used for termination on the driver side. Note that the driver needs 3 bias resistors corresponding to 3 bias taps, discussed in the next section. The receiver needs 2 bias resistors and bias taps.

The DRP has wide margins based on PSCAN [70] and Spectre [41] simulations, as reported in Chapter 3. Serial biasing is achieved by connecting ground A to bias B.

Figures 4.2(b) and  4.2(c) show the layout of the DRP core with all JJs labeled and its crosssection along the JA2-JA3-JA4 line. The left and right islands are separated by moats in the M4 ground and M7 sky planes. The moats do not overlap each other (staggered) and are

Figure 4.2: The DRP core (a) comprises driver junctions JA1-JA4 and receiver junctions JB1-JB2 placed on separated grounds A and B. JA1 = 250 µA, JA2 = 350 µA, JA3=488 µA, JA4 = 158 µA, JB1 = 94 µA, JB2 = 131 µA, IA1 = 175 µA, IA2 = 245 µA, IA3 = 344 µA, IB1 = 71 µA, IB2 = 100 µA, LA1 = 2 pH, LA2 = 2.7 pH, LA3 = 2.1 pH, LB1 = 2.7 pH, LP = LS = 5.8 pH, and K = 0.53. The DRP layout (b) is shown for the MIT-LL SFQ5ee fab node. All junctions, bias taps, input-output locations, and the M4-M7 ground moats are labeled. The cross-section along the JA2-JA3-JA4 line is shown in (c).

<!-- image -->

covered by metal layers (M3 and M2 for M4, M6 for M7) to reduce flux trapping [53].

Josephson junctions JA3 and JA4 are physically placed above ground B but are electrically  connected  to  ground  A  using  an  M5 'tongue'  spreading  over  the  M4  moat [49]. It allows us to place a transformer (Figure 4.2(b)) in between JJs JA3, JA4, JB1, and JB2, and make holes in the layers M4 and M7 to increase coupling.

All  the  layout  features  mentioned  above  (staggered  and  covered  moats,  M5 'tongue', transformer with M4 and M7 holes) make the structure of metal layers in the proximity of moats quite complicated. We reserve 30 µm on each side of the M4 moat for areas where layers are used differently from the rules specified for the cell library [57].

## 4.2.3 Horizontal and Vertical Bias JTLs

The vertical segment of the M0 bias bus, seen in Figure 4.1(a), delivers current to the DUT. The further distribution of the bias current inside of the DUT is defined by the library rules that are illustrated in Figure 4.3.

Figure 4.3(a) shows the layout area of minimum size. All library cells have a fixed height of  40 µm and width being modulo 20 µm. There are up to 6 dedicated locations for input and output  terminals  depicted  as  black  triangles  in  Figure 4.3(a).  There  are  also  a  maximum  of  2 dedicated locations for bias taps (black rectangles) where bias resistors in RSFQ circuits (or bias JJs along with a large inductor in the case of ERSFQ) can be connected to the M0 bias network using a stack of M0-to-M6 vias that goes through a hole in M4. Note that not all input and output terminals, as well as bias taps, must be used for a circuit placed on the area of the minimum size.

All cells comprise two 2 µm wide horizontal M0 bias lines, depicted in Figure 4.3(b), that

Figure 4.3: Layout rules for locations of input and output terminals, as well as bias taps are shown in (a). In (b), two horizontal M0 bias buses are added. Note that abutting multiple cells horizontally would form a contiguous M0 bias line. In the horizontal bias JTL of (c), the vertical M0 bus linewidth cannot be increased beyond 5 µm due to proximity to the bias taps. In the vertical bias JTL of (d), an M2 layer is also placed over the horizontal M1 bias line.

<!-- image -->

are  connected  to  bias  taps.  Adjacent  cells  form  continuous  horizontal  bias  buses.  The  vertical segment of the M0 bias bus in Figure 4.1(a) locks all horizontal M0 buses together, as illustrated in Figure 4.3(c).

The cell  in  Figure 4.3(c)  includes  2  horizontal  JTLs  shown  schematically  to  let  pulses propagate horizontally over the M0 vertical bias. Such a cell is called the 'horizontal bias JTL'. Similarly,  the  'vertical  bias  JTL'  in  Figure 4.3(d)  is  used  to  distribute  pulses  in  the  vertical direction over the horizontal M1 bias bus covered by M2 (see Figure 4.1). Note that only one bias tap is used in Figure 4.3(d), and an optional 2 µm wide horizontal M0 bias line is added to lock the 2 µm wide horizontal M0 bias lines above and below the M1 and M2 pair. Both horizontal and vertical bias JTLs are used to distribute pulses between a circuit residing in the central part of an island and the DRP cores placed on island edges.

The  maximum  width  of  the  vertical  M0  bus  in  Figure 4.3(c)  is  5  m  to  preserve  the minimum layout area of 20  m (width) by 40  m (height). The vertical M0 bus can be made wider only by doubling the width of the horizontal bias JTL. According to the MIT-LL design rules for the SFQ5ee fab node [9], the maximum current capacity for metal layers, including M0, is 40 mA per  1  m  of  width.  This  translates  into  200 mA  of  bias  current  flowing  through  the  vertical segment.  Any  transition  between  metal  layers,  say  from  M1  to  M0,  as  seen  in  Figure 4.1(a), involves a layer-to-layer via or a set of vias. The MIT-LL design rules guarantee the maximum current of 20 mA per 2  m  2  m via with 1  m  1  m opening in the insulator between the metal layers. As a result, a group of 10 parallel vias with a total width of 20  m needs to be assembled to maintain 200 mA of total bias current flowing perpendicularly.

## 4.2.4 Horizontal and Vertical Composite DRPs

In the cell library design flow [57], Passive Transmission Lines (PTLs) ([27], [28]) are used for pulse propagation between the cells inside the DUT. This requires the inclusion of a PTL transmitter  (Tx)  and  a  receiver  (Rx),  in  addition  to  the  DRP  core  and  bias  JTLs,  to  form  the Composite Driver Receiver Pair (CDRP). The horizontal and vertical CDRPs ensure signal flow in all 4 directions of the 2D plane.

One of the layout variants of the horizontal CDRP is shown in Figure 4.4(a). SFQ pulses propagate along 2 channels in two different directions. Two of the DRP cores are combined in Figure 4.4  to  ensure  the  required  fixed  height  of  40  m.  The  horizontal  bias  JTLs,  PTL transmitters, and receivers are added on either side of the DRP cores. The 5  m wide vertical M0 bias bus, seen in Figure 4.4(b), is part of the bias JTL on the right side. Each channel (top and

bottom) of the CDRP requires 5 bias taps on the driver side and 4 bias taps on the receiver side, as seen in

Figure 4.4: The horizontal CDRP layout (b) is shown for SFQ pulse flow from left to right and right to left in the top and bottom channels respectively. The block diagram (b) shows the center region (60  m width  40  m height) where the library rules are violated. In addition to the 3 bais taps on the driver side of the DRP core, 2 more taps are required for the bias JTL and PTL Rx/Tx. Similarly, along with the 2 bias taps on the receiver side of each DRP core, the bias JTL and PTL Tx/Rx require 2 additional taps. The connection of bias taps to the horizontal M0 bias lines is not shown.

<!-- image -->

Figure 4.4(b).  The  required  number  of  taps  equals  the  number  of  bias  resistors  for  the  RSFQ version  or  bias  JJs  in  the  ERSFQ  case.  The  total  width  of  the  horizontal  CDRP  is  220  m (8  20  m + 2  30  m).

The vertical CDRP, shown in Figure 4.5(a), is used for SFQ pulse transfer from top to bottom and bottom to top. In the block diagram of Figure 4.5(b), two DRP cores are placed next to each other in a vertical orientation to form 2 channels. The vertical bias JTLs and the PTL Tx/Rx can be seen placed above and below the DRP cores. As with the horizontal CDRP, in each channel of the vertical CDRP, the driver and receiver sides require 5 and 4 bias taps, respectively. Each of the vertical bias JTLs and PTL Tx/Rx have fixed heights of 40  m each, resulting in a combined height of 300  m (6  40  m + 2  30  m).

The DUT block can have input and output terminals on every side with a pitch of 20  m. However, not all of them are required to be used. It is thus necessary to have trivial versions of

Figure 4.5: The vertical CDRP layout is shown in (a) for SFQ pulse flow from bottom to top and top to bottom in the left and right channels respectively. The block diagram (b) shows the 40  m  60  m center region of the DRP with library rules violation. Vertical M0 bias lines, 2  m in width, are used in the vertical bias JTL to supply bias to the DRP cores.

<!-- image -->

the horizontal and vertical CDRPs that do not support pulse propagation. They are used only to form the M4 and M7 moats and compose bias buses.

## 4.3 Assembling a Serially Biased Circuit

## 4.3.1 Blocks Required

Figure 4.6 illustrates the assembly of a 2-island serially biased DUT. The D1 block consists of  multiple  rows  of  horizontal  CDRPs.  From this,  it  is  clear  how  the  horizontal  bias  JTLs  are involved in forming the wide vertical M0 bus and biasing the DUT using narrower horizontal lines. The D2 block consists of multiple columns of vertical CDRPs. The vertical bias JTLs are used to form the horizontal M1 bias bus, accompanied with M2 layers, to transfer the bias current from one island to another. The blocks D3 and D4 comprise horizontal and vertical CDRPs without bias buses.

There  are  6  biasing  blocks  (B1-B6)  required  to  complete  the  assembly.  In  Figure 4.6, blocks B1, B2, and B3 are selected to implement the grapevine biasing scheme. The B2 block is

Figure 4.6: Block diagram of the assembly of two serially biased DUTs. Blocks D1/D3 and D2/D4 comprise horizontal and vertical CDRPs respectively. Blocks B1-B6 are used to form a biasing network. All blocks placed around the DUT form moats in M4 and M7. Note that all blocks are placed slightly separated in the figure for easier recognition.

<!-- image -->

the most representative one as it has both the M4-to-M1 drain vias, to pick up the bias current from the ground, and the M1-to-M0 vias to transfer bias current from the M1 layer to the M0 layer.

With these blocks ready, assembling the SB layout is relatively straightforward. First, the horizontal and vertical CDRPs are placed around the DUTs. Second, B1-B6 blocks are placed to complete the layout. As a result, the islands' formation is completed by creating moats all the way around, and the GV-biased structure is properly implemented.

## 4.3.2 Test Circuit Design

Based  on  this  assembling  strategy,  as  proof  of  concept,  we  designed  a  test  circuit comprising 4 serially biased DUTs, as shown in Figure 4.7. The D1-D4 blocks consisting of the

Figure 4.7: The test chip includes 4 serially biased DUTs with CDRPs for signal propagation. Each DUT comprises JTLs and splitters from the standard cell library [6], with a total junction count of 281 (including the overhead of CDRPs).

<!-- image -->

Figure 4.8: Block diagram of the test circuit with the black and blue paths highlighting the SFQ pulse propagation along the horizontal and vertical CDRPs. Note that the GV biasing scheme is not shown here. Each LF monitor is preceded by 4 Toggle FlipFlops (not shown).

<!-- image -->

CDRPs can be identified. B1-B6 are the biasing blocks, with B1-B3 used for GV biasing.

The objective of this test circuit is to verify the operation of the horizontal and vertical CDRPs and their layout variants. In the block diagram of Figure 4.8, independent data streams are generated by two Pseudo-Random Bit Sequence (PRBS) generators [21], PRBS-A and PRBS-B, and they propagate across 4 islands. The 127-bit sequence from PRBS-A flows horizontally (black path),  whereas  that  from  PRBS-B  flows  mostly vertically  (blue  path).  The  DUT,  in  this  case, mainly  comprises  JTLs,  PTLs,  and  confluence  buffers  [12],  and  it  was  assembled  using  the standard library cells [57]. Using PTLs instead of JTLs, as interconnects on the islands, reduces the serial bias current, and hence this is investigated using a 490 µm long PTL with asymmetric dual ground planes (see Chapter 5 for more details). Note, that PTLs cannot be used to cross the islands as the signal grounding is at different potentials and thus must be confined to an island. The  horizontal  and  vertical  paths,  excited  by  PRBS-A  and  PRBS-B,  respectively,  can  be

independently tested and together. The latter lets us quantify the effect of crosstalk between the two data paths.

LF monitors are placed for screening and debugging purposes only. For HF measurement, we used output drivers based on stacks of SQUIDs (similar to [14]). Every driver is preceded by a Toggle Flip-Flop [12], which makes it very sensitive to any missed or added pulse in the PRBS sequence. Each error manifests itself in flipping the PRBS signature trace on the HF oscilloscope. The chip comprising this test circuit was fabricated at MIT-LL using the SFQ5ee fabrication node [9].

## 4.4 Measurement Results

## 4.4.1 Horizontal and Vertical CDRPs

The test results for the horizontal test structure with the 5 DRPs and 15 DRPs are shown in Figures 4.9(a) and 4.9(b). A 3-minute observation window (at all frequencies) was used to measure the Bit Error Rate (BER). Both structures work up to 50 GHz with degradation of margins above 30 GHz from ±10.7% to ±8.2% at a BER level of 10 -12 . We did not observe any difference in the operating margins for the 5 and 15 horizontal DRPs. In the case of the 5 CDRPs connected by PTLs (Figure 4.9(c)), margins are slightly narrower, ±9.8% and ±7.3% at 30 GHz and 50 GHz, respectively.

It is interesting to compare the margins at 50 GHz, and the BER level of 10 -12 for the test structures designed using the custom library of Chapter 3 and the ST standard cell library reported here: ±4% versus ±8%. The difference can be attributed to the different DRP sizes and/or different fabrication runs. The area occupied by DRPs and the bias JTLs for the custom library of Chapter 3, is 40% smaller compared to the one discussed here (65×40 µm 2 vs. 180×20 µm 2 ). In addition, the

test structure in Chapter 3 is quite dense, with DRPs connected directly to each other. In contrast, DRPs of the test circuit of Figure 4.7 are separated by JTLs or PTLs.

Figure 4.9: BER versus SB current for different frequencies up to 50 GHz plotted for the horizontal test structures with 5 DRPs (a), 15 DRPs (b), and 5 CDRPs connected on the island by PTLs (c). The vertical test structure with 16 DRPs is depicted in (d).

<!-- image -->

The  test  structure  with  16  vertical  DRPs,  in  addition  to  the  5  horizontal  DRPs  in Figure 4.9(d), has narrower margins compared to its reference circuit with only 5 horizontal DRPs shown in Figure 4.9(a): ±7.6% versus ±10.7% at 30 GHz, and ±6.6% versus ±8.2% at 50 GHz. The test structure with vertical DRPs was sensitive to the current used to bias circuitry on the global ground. We suspect that the return current on the global ground interacts with the parts of the vertical DRPs placed on the global ground. Such an effect needs to be addressed and eliminated in future designs.

The  horizontal  or  vertical  structures  in  Figure 4.9  were  tested  by  running  either  the generator PRBS-A or the generator PRBS-B as labeled in Figure 4.8. The simultaneous operation of both generators caused margin degradation by 1.5% at 50 GHz. The second running PRBS does not change the position of the left curves in Figure 4.9 but shifts the right curves to the left by 1 - 2 mA. Operation margins of the test circuit were dominated by the operation of the vertical DRPs. More detailed analyses and comparisons on this are presented in the next sections.

## 4.4.2 Comparing Independently Tested Experiments

To simplify the comparisons, we name the experiments 1) 5hDRPs + JTLs, 2) 15hDRPs + JTLs, 3) 5hCDRPs + PTLs, and 4) 5hDRPs + 16vDRPs + JTLs. '5hDRPs', '15hDRPs','5hCDRPs'  and  '16vDRPs'  denote  '5  horizontal  DRPs',  '15  horizontal  DRPs',  '5 horizontal CDRPs', and '16 vertical DRPs' respectively.

The first set of comparisons is made between the '5hDRPs + JTLs' and the '15hDRPs + JTLs', as seen in Figure 4.10. It is clear from the curves that the serial bias margins do not depend on the number of horizontal DRPs, as they are increased from 5 to 15.

DRPs: 5h+JTLs vs 15h+JTLs

## 5hDRPs+JTLs (E5)

@50GHz: 56-66mA, ± 8.2% (PRBS-A)

@30GHz: 54-67mA,

±

10.7% (PRBS-A)

## 15hDRPs+JTLs (E5)

Figure 4.10: The BER curves as a function of frequency for the 5 and 15hDRPs + JTLs are compared from chip location E5. Bias margins at 30 GHz and 50 GHz are compared. 13 No dependence on the number of horizontal DRPs (5h vs 15h) DRPs: 5h+JTLs vs 5h+PTLs

<!-- image -->

## 5hDRPs+JTLs (E5)

## 5hCDRPs+PTLs (E5)

<!-- image -->

71

Figure 4.11: The BER curves for the 5hDRPs with JTL and PTL interconnections are compared. Note that in case of the PTL interconnections, the composite DRP is used. 14 PTLs reduce margins by 0.9% at 50GHz

DRPs: 5h+JTLs vs 5h +16v +JTLs

## 5hDRPs+JTLs (E5)

## 5hDRPs+16vDRPs+JTLs (E5)

Figure 4.12: The BER curves for the '5hDRPs + JTLs' and '5hDRPs + 16vDRPs + JTLs'. At 50 GHz, a 1.6% reduction in bias margins is observed. 15 Vertical DRPs reduce margins by 1.6% at 50GHz

<!-- image -->

The second comparison is between the 5hDRPs with JTL and PTL interconnections. As seen in Figure 4.11, there is a 0.9% reduction in bias margins in the case of PTL interconnections. This could be attributed to the SFQ pulse getting reshaped by JTLs, between islands, resulting in slightly wider margins.

Next, the '5hDRPs + JTLs' (data from PRBS-A) is compared with the '5hDRPs + 16vDRPs + JTLs' (data from PRBS-B) in Figure 4.12. Shrinkage in the bias margins is evident here. An approximately 3% reduction is observed at 30 GHz. As mentioned before, we suspect the interaction between return currents and the vertical DRPs is causing this reduction.

## 4.4.3 Crosstalk Experiments

As a first experiment to measure the impact of turning both PRBS circuits (PRBS-A and PRBS-B)  on,  the  serial  bias  margins  for  the  '5hDRPs + JTLs',  with  and  without  turning  on PRBS- B, are compared in Figure 4.13. There appears to be a marginal impact of a 0.8% reduction in margins, at 50 GHz. PRBS: 5h+JTLs for A vs A&amp;B

## 5hDRPs+JTLs (E5, PRBS-A)

## 5hDRPs+JTLs (E5, PRBS-A&amp;B)

<!-- image -->

@50GHz: 56-66mA, ± 8.2% (PRBS-A)

@50GHz: 56-65mA, ± 7.4% (PRBS-A&amp;B)

Figure 4.13: The BER curves for the '5hDRPs + JTLs' with and without turning PRBS -B on. A 0.8% reduction in bias margins is observed at 50 GHz. Note no degradation in margins at lower frequencies. 16 Turning on the second PRBS-B reduces margins by 0.8% at 50GHz

Next, similar experiment is performed on the '15hDRPs + JTLs'. As seen in Figure 4.14, there is twice as large (1.6%) reduction in the bias margins upon turning on PRBS-B, compared to Figure 4.13.  This  implies  that  as  the  data  propagates  through  more  DRPs,  the  susceptibility  to operational failure due to crosstalk increases, appearing as reduced margins.

For the '5hCDRPs + PTLs' experiment, in Figure 4.15, a 1.5% bias margin reduction is observed at 50 GHz. Upon comparing this result with that in Figure 4.13, it is evident that PTLs

PRBS: 15h+JTLs for A vs A&amp;B

## 15hDRPs+JTLs (E5, PRBS-A)

<!-- image -->

@50GHz: 56-66mA, ± 8.2% (PRBS-A)

## 15hDRPs+JTLs (E5, PRBS-A&amp;B)

<!-- image -->

@50GHz: 56-64mA, ± 6.6% (PRBS-A&amp;B)

Figure 4.14: The BER curves for the '15hDRPs + JTLs' with and without turning on PRBS-B. There is a shrinkage of 1.6% in bias margins at 50 GHz. 17 Turning on the second PRBS-B reduces margins by 1.6% at 50GHz PRBS: 5h+PTLs for A vs A&amp;B

## 5hCDRPs+PTLs (E5, PRBS-A)

<!-- image -->

@50GHz: 57-66mA, ± 7.3% (PRBS-A)

## 5hCDRPs+PTLs (E5, PRBS-A&amp;B)

<!-- image -->

@50GHz: 57-64mA, ± 5.8% (PRBS-A&amp;B)

Figure 4.15 : The BER curves for the '5hCDRPs + PTLs' with and without turning on PRBS-B. There is a 1.5% bias margin shrinkage at 50 GHz. 18 Turning on the second PRBS-B reduces margins by 1.5% at 50GHz

PRBS: 5h+16vDRPs +JTLs for B vs B&amp;A

## 5hDRPs+16vDRPs (E5, PRBS-B)

<!-- image -->

@50GHz: 56-64mA, ± 6.6% (PRBS-B)

## 5hDRPs+16vDRPs (E5, PRBS-B&amp;A)

<!-- image -->

@50GHz: 56-62mA,

± 5.1% (PRBS-B&amp;A)

19

Figure 4.16 : The BER curves for the '5hDRPs + 16vDRPs + JTLs' with and without turning on PRBS-A. The bias margins are impacted above 40 GHz. Turning on the second PRBS-A reduces margins by 1.5% at 50GHz PRBS: 5h+JTLs+16vDRPs vs All Structures for B&amp;A

## 5hDRPs+16vDRPs (E5, PRBS-B&amp;A)

<!-- image -->

@50GHz: 56-62mA, ± 5.1% (PRBS-B&amp;A)

## All Structures (E5, PRBS-B&amp;A)

<!-- image -->

@50GHz: 56-62mA,

± 5.1% (PRBS-B&amp;A)

Figure 4.17 : The BER curves for the '5hDRPs + 16vDRPs + JTLs' and that of 'All Structures' are identical. A ±5.1% bias margin is observed in both cases, at 50 GHz. Margins of the exemplar circuit is defined by vertical DRPs

20

are  more  vulnerable  to  crosstalk  than  JTLs  (1.5%  versus  0.8%  reduction  in  PTL  and  JTL interconnections, respectively).

In  the  case  of  the  '5hDRPs + 16vDRPs + JTLs'  experiment,  the  effect  of  crosstalk  is measured by turning the PRBS-A generator on and off and comparing the bias margins. As seen in Figure 4.16, turning on PRBS-A reduces the bias margins by 1.5% at 50 GHz.

Finally, the outputs of all the structures are simultaneously observed, and the bias margins are noted. This is an important experiment as in a practical serially biased circuit, there is no control over  the  direction  of  SFQ  pulse  propagation  on  the  island.  We  require  robust  SFQ  pulse transmission  along  all  4  directions  of  the  2D  plane.  We  compare  the  BER  plots  of  the '5hDRPs + 16vDRPs + JTLs' with the 'All structures' in Figure 4.17 and observe that the margins of the entire test circuit are defined and limited by the vertical DRPs. Note that in both plots of Figure 4.17, both PRBS-A and PRBS-B generators have been turned on.

## 4.4.4 Different Wafer Locations

The  test  structures  were  tested  across  locations  E3,  E5,  and  E6  on  the  wafer.  The '5hDRPs + JTLs' experiment for the 3 locations is depicted in Figure 4.18. The BER curves for locations E3 and E5 are almost similar except for the left curves. Location E6 reported reduced margins that could be attributed to a fabrication defect.

Similarly,  the  '15hDRPs + JTLs'  experiment  also  reports  reduced  margins  for  wafer location E6, as seen in Figure 4.19. This is expected as any defect in the '5hDRPs + JTLs' signal path will also appear in the '15hDRPs + JTLs' signal path.

For  the  '5hCDRPs + PTLs'  test,  consistent  margins  were  reported  across  the  3  wafer locations. This is shown in the BER curves of Figure 4.20.

Lastly, for the '5hDRPs + 16vDRPs + JTLs' case, location E3 reported the least margins and thus could have a fabrication defect in its signal path. As shown in Figure 4.21, locations E5 and E6 have almost similar BER curves. Location: 5h+JTLs for E3 vs E6 vs E5

## 5hDRPs+JTLs (E3)

1GHz

10GHz

20GHz

30GHz

40GHz

.50GHz

5hDRPs+JTLs (E6)

1GHz

10GHz

20GHz

30GHz

40GHz

·50GHz

## 5hDRPs+JTLs (E5)

<!-- image -->

SerialBias(mA)

Serial Bias(mA)

Figure 4.18: Comparing BER curves across frequency for the '5hDRPs + JTLs' experiment across 3 wafer locations: E3, E5, and E6. Note that in the E6 location, the margins shrink rapidly beyond 20 GHz. 5h+JTLs are defective in location E6

39

## 15hDRPs+JTLs (E5)

<!-- image -->

## 15hDRPs+JTLs (E3)

<!-- image -->

15hDRPs+JTLs (E6)

Figure 4.19 : Comparing BER curves for the '15hDRPs + JTLs' experiment across 3 wafer locations: E3, E5, and E6. The E6 location has reduced margins across frequencies, in contrast to the similar plot for '5hDRPs + JTLs'. 15h+JTLs are defective in location E6

<!-- image -->

40

10-8

10-9

10-10

10-11

ErrorRate

10-12

10-13

49

10-8

10-9

10-10

10-11

ErrorRate

10-12

Location: 15h+JTLs for E3 vs E6 vs E5

51

53

65

67

69

71

Figure 4.20 : Comparing BER curves for the '5hDRPs + PTLs' expe riment across 3 wafer locations: E3, E5, and E6.

<!-- image -->

5h+PTLs are not defective in location E6

5hDRPs+16vDRPs+JTLs (E3)

41 5hDRPs+16vDRPs+JTLs (E5)

5hDRPs+16vDRPs+JTLs (E6)

Figure 4.21 : Comparing BER curves for the '5hDRPs + 16vDRPs + PTLs' experiment across 3 wafer locations: E3, E5, and E6.

<!-- image -->

Vertical DRPs are defective in location E3

## 4.5 Electromagnetic Simulations

## 4.5.1 2-island CDRP Simulation

The GV biasing results in low and uniform current density all over the island of the M4 ground plane, including its edges, as seen in Chapter 3. The ST standard cell library, however, adds several new layout objects that need to be analyzed.

42

Figure 4.22: The single island layout (a) shows the ground moat, bias lines, and taps with resistors connected to the M4 ground. M4 holes used for placing the transformer above, are also seen. Components of GV biasing, such as the M4-to-M1 and M1-to-M0 groups of vias are marked. Bias taps are labeled from A to N in (b).

<!-- image -->

The first object is a set of bias taps placed all over the M4 island. Each bias tap is a stack of vias that are used to deliver current from the M0 layer to the M6 layer through a hole in M4. The  current  through  an  individual  tap  is  relatively  small  (typically  100 µA-200 µA),  and corresponds to a current through an individual bias resistor (RSFQ) or a bias JJ (ERSFQ).

Figure 4.23: Zoomed view of M4 current density around the bias taps in case of the 2island CDRP circuit with M4 ground plane. High current density regions are observed around the bias taps in (a) and (b) (see text for details).

<!-- image -->

However, bias taps can create regions of high current density on the island of the M4 layer. We studied the effect by simulating 2 serially biased islands each comprising DRP cores and JTLs, using Sonnet software [66]. The total bias current per island and its distribution between bias resistors were selected equal to the set of resistors used for similar simulations in Chapter 3.

Figure 4.24: Zoomed view of the M4 current density around bias taps in case of the extra M1 ground plane added. Compare with Figure 4.23(a) and Figure 4.23(b).

<!-- image -->

Table 4.1: M4 Current Density around the Bias Taps for Different Ground Plane Configurations

| Bias Tap   |   Bias Current I through bias tap (µA) |   Current Density D max1 M4 only (A/m) |   Current Density D max2 M4&M7 (A/m) |   Current Density D max3 M1&M4 (A/m) |   Ratio D Max1 /I (10 6 m -1 ) |   Ratio D max2 /I (10 6 m -1 ) |   Ratio D max3 /I (10 6 m -1 ) |
|------------|----------------------------------------|----------------------------------------|--------------------------------------|--------------------------------------|--------------------------------|--------------------------------|--------------------------------|
| A          |                                     71 |                                    440 |                                  389 |                                  256 |                            6.2 |                            5.5 |                            3.6 |
| B          |                                    100 |                                    727 |                                  668 |                                  388 |                            7.3 |                            6.7 |                            3.9 |
| C          |                                    306 |                                   3150 |                                 2352 |                                 1550 |                           10.3 |                            7.7 |                            5.1 |
| D          |                                    351 |                                   2813 |                                 1990 |                                 1415 |                            8   |                            5.7 |                            4   |
| E          |                                    175 |                                   1482 |                                 1025 |                                  747 |                            8.5 |                            5.9 |                            4.3 |
| F          |                                    342 |                                   2414 |                                 1595 |                                 1596 |                            7.1 |                            4.7 |                            4.7 |
| G          |                                    245 |                                   1560 |                                 1150 |                                  972 |                            6.4 |                            4.7 |                            4   |
| H          |                                     71 |                                    435 |                                  305 |                                  276 |                            6.1 |                            4.3 |                            3.9 |
| I          |                                    100 |                                    667 |                                  510 |                                  387 |                            6.7 |                            5.1 |                            3.9 |
| J          |                                    306 |                                   2581 |                                 1825 |                                 1455 |                            8.4 |                            6   |                            4.8 |
| K          |                                    351 |                                   2733 |                                 1823 |                                 1404 |                            7.8 |                            5.2 |                            4   |
| L          |                                    175 |                                   1447 |                                 1020 |                                  752 |                            8.3 |                            5.8 |                            4.3 |
| M          |                                    342 |                                   2413 |                                 1595 |                                 1605 |                            7   |                            4.7 |                            4.7 |
| N          |                                    245 |                                   1518 |                                 1100 |                                  997 |                            6.2 |                            4.5 |                            4.1 |

Figure 4.22(a) shows a single island layout of the 2-island structure, where all Josephson junctions  and  inessential  superconducting  components  were  removed,  retaining  only  the  M4 ground plane, the bias buses, and resistor networks, to simplify analysis. The current density in the M4 layer is shown in Figure 4.22(b) with the color scale from 0 A/m (blue) to 1500 A/m (red). For all simulations presented in this section, we maintain the same scale.

Simulations  confirm that  the  GV  biasing  technique  results  in  low  and  uniform  current density distribution in the proximity of the ground moats and transformer holes. However, high current  densities  were  observed  in  the  M4  layer  above  the  M0  bias  buses  (red  areas  in Figure 4.22(b)), as expected, and in the proximity of the bias taps.

The M4 current densities around bias taps are non-uniform and, in some cases, very high, as seen in Figure 4.23 and summarized in Table 4.1. The highest densities, Dmax1, are observed in the corners of the holes for taps C, D, J, K, F, and M, with the largest bias current ( I ) flowing

through these taps, as expected. However, the ratio Dmax1/I is also high for taps E and L, which can be explained by their proximity to the M0 bias buses. Note that all 8 taps with the highest Dmax1/I ratio (C-F and J-M) reside in proximity of the M0 bias buses.

As a next step, we added the M7 sky plane over each island to cover all bias taps. The M4 ground and M7 sky planes are sewn together in points where the bias resistors are connected to the M4 ground. Adding the M7 sky plane helped to reduce the maximum density Dmax2 by around 25%, as seen in Table 4.1.

As was mentioned before, the ST standard cell library employs the M1 metal layer for extra grounding. It is used to isolate the bias grid in M0 from PTLs, designed in M2 and M3 layers. We added the extra ground plane in M1, shaped as M4, and sewed them together by replacing M6-toM4 vias with M6-to-M1 vias. We also connected the M1 ground to M4-to-M1 drain vias shown in Figure 4.22(a) by a 20 µm wide strip in M1. As expected, the M1 extra ground eliminated areas of high current density in the M4 layer, as seen in Figure 4.24. According to Table 4.1, Dmax3 is 35-50% smaller compared to Dmax1 . Adding the M1 extra ground also reduced the variance of the ratio Dmax3/I ,  which implies a more uniform current distribution on the M4 ground plane. As a result, Josephson junctions can be placed closer to the bias tap holes, at a distance of 2 µm, without interaction.  We  cannot  use  the  M1  layer  for  this  purpose  in  the  vertical  bias  JTLs  (see Figure 4.3(d)) because it is already employed. However, the M1 layer can be replaced by M3 for extra grounding in this case.

## 4.5.2 Simulating Vertical M0 Extension over M4-to-M1 Vias

Another ST cell library-specific object to discuss is the M4-to-M1 group of vias sketched

Figure 4.25: M0 strip (a) carries current into the island and changes its width from 5 µm to 20 µm and back to 5 µm while having the 5 µm long extension behind the drain vias. The individual vias D, E, F, and G vias carry most of the drain current (b). The 10 µm extension together with 2 chamfers, highlighted as triangles in (c), equalizes the drain current distribution (d).

<!-- image -->

in  Figure 4.6  (blocks  B1  and  B2)  and  shown  in  Figure 4.25  in  detail.  As  discussed  before  in subsection 4.2.3, the 5 µm wide M0 and M1 bias buses carry at most 200 mA of current and hence require a group of 10 parallel M4-to-M1 vias [9] to support 200 mA of the return current. The width of such a group of vias is 20 µm, as well as the width of the M1 and M0 wires nearby. As a

result,  the  M0  bias  bus  changes  its  width  from  5 µm  to  20 µm  and  back  to  5 µm,  as  seen  in Figure 4.25.

Table 4.2: M4-to-M1 Via Current Density

| Via Location   |   Current Density (A/m) for 5 µm long M0 extension |   Current Density (A/m) for 10 µm long M0 extension |   Current Density (A/m) for 10 µm long M0 extension with chamfers |
|----------------|----------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------------|
| A              |                                                770 |                                                 986 |                                                              1053 |
| B              |                                                900 |                                                1042 |                                                              1100 |
| C              |                                               1083 |                                                1094 |                                                              1117 |
| D              |                                               1363 |                                                1143 |                                                              1127 |
| E              |                                               1452 |                                                1176 |                                                              1120 |
| F              |                                               1450 |                                                1188 |                                                              1116 |
| G              |                                               1343 |                                                1135 |                                                              1100 |
| H              |                                               1116 |                                                1082 |                                                              1080 |
| I              |                                                917 |                                                1021 |                                                              1045 |
| J              |                                                770 |                                                 960 |                                                              1000 |

Simulations  indicate  that  an  abrupt  transition  from  20 µm  to  5 µm  in  width  of  the  M0 results in unequal current distribution in the parallel group of vias. The M0 wire in Figure 4.25(a) is extended by 5 µm over the drain via to let the bias current redistribute. However, Figure 4.25(b) and Table 4.2 indicate that the individual vias D - G carry unequally large currents. An extension of  10 µm  (half  of  the  width)  helps  to  equalize  the  return  current  distribution  (see  Table 4.2). However, the best result is achieved using 10 µm extensions together with chamfers to avoid 90degree turns, as shown in Figures 4.25(c) and 4.25(d). According to Table 4.2, the variation in current is less than 10% in this case.

## 4.5.3 Simulating Horizontal M0 and M1 Extensions over M1-to-M0 vias

According to Figure 4.6, the horizontal serial bias current needs to be transferred from the M1 layer to the M0 layer, which has a width of 20 µm to support the same 200 mA of bias current.

Figure 4.26: Layout (a) shows a 5 µm long horizontal M0/M1 extension on both sides of M1-to-M0 vias. Unequal current distribution between M1-to-M0 vias is shown in (b). The 10 µm extension with chamfers (c) helps to equalize the current distribution between all vias (d).

<!-- image -->

Table 4.3: M1-to-M0 Via Current Density

| Via Location   |   Current Density (A/m) for 5 µm long M0/M1 extension |   Current Density (A/m) for 10 µm long M0 extension |   Current Density (A/m) for 10 µm long M0 extension with chamfers |
|----------------|-------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------------|
| A              |                                                   670 |                                                 980 |                                                              1036 |
| B              |                                                   830 |                                                1047 |                                                              1065 |
| C              |                                                  1000 |                                                1069 |                                                              1080 |
| D              |                                                  1260 |                                                1107 |                                                              1094 |
| E              |                                                  1480 |                                                1150 |                                                              1156 |
| F              |                                                  1500 |                                                1154 |                                                              1100 |
| G              |                                                  1350 |                                                1169 |                                                              1145 |
| H              |                                                  1013 |                                                1020 |                                                              1074 |
| I              |                                                   850 |                                                1008 |                                                              1040 |
| J              |                                                   612 |                                                 990 |                                                              1017 |

The situation is like the one discussed in the previous subsection, 4.4.2, except that both layers need to be extended away from the group of vias.

A double 5 µm extension is depicted in Figure 4.26(a). Sonnet-based simulations show that not all vias are equally involved in current propagation (see Figure 4.26(b) and Table 4.3). The best solution is to use the double 10 µm extension (half-width extension) together with chamfers, as seen in Figures 4.26(c) and 4.26(d).

Note  also  that  the  width  of  the  M1-to-M0  vias  defines  the  minimum  width  of  the  M2 ground. For the selected 200 mA of maximum bias current, the minimum M2 ground width is 20 µm.

## 4.5.4 Double Current Injection

The maximum bias current of 200 mA is limited by 5 µm of the maximum width of the M0 wire inside the  horizontal  bias  JTL,  that  allows  us  to  keep  the  cell's  size  minimum.  This limitation  seems  easy  to  overcome  by  having  2  parallel  vertical  bias  structures,  as  shown  in Figure 4.27. Let us assume that each of the two vertical M0 segments has a width of 5 µm, which gives the total width of 10 µm and 400 mA for the total bias current. The width of the horizontal M0 and M1 segments, as well as the width of M1-to-M0 vias, should be adjusted properly.

Simulations show that this is not a good solution. The current flowing in the M0 wire splits equally between the two branches, as seen in Figure 4.27(b), being guided by two equal resistors. However, the return current in M1 prefers the right branch, the path B-D is preferable compared to the path A-C-D as clearly seen in Figure 4.27(c). The current in the M2 layer in Figure 4.27(d) looks equally distributed along the horizontal path, while the current density in the M4 layer is unusually  high  in  the  area  A-C-B  (compare  Figure 4.27(e)  with  Figure 4.22(b)).  A  detailed analysis shows that this happens because M0 and M1 wires carry co-flow currents and overlap in

the area C, which induces a circular current in the loop A-C-B involving the M4 layers. As a result, the return current is almost canceled in the left branch and nearly doubled in the right one. The

Figure 4.27: The layout (a) of the horizontal bias bus with 2 injection points (A, B) and the M1-to-M0 via (D). Current distributions in layers M0 (b), M1 (c), M2 (d), and M4 (e) are shown (see text for details).

<!-- image -->

redistributed current can exceed the maximum current in the right drain vias and destroy the proper biasing of the island.

## 4.6 Discussion

The width  of the  horizontal  and  vertical  bias  buses  has  been  chosen  to  be  5 µm.  This imposes a maximum bias current of 200 mA per island that translates into about 1100 junctions per island, assuming each junction on average has a critical current of 250 µA and is biased at 0.7 level of its critical current. As a conservative design practice, we recommend using only the half of the maximum bias current. This translates to 550 junctions on each island.

The maximum number of JJs per island can be increased by reducing the average critical current. For example, switching from 250 µA to 50 µA will allow us to increase the total number of JJs per island by a factor of 5, from 550 to 2750. However, the further reduction is questionable because of noise susceptibility and fabrication related issues.

The noise immunity of RSFQ/ERSFQ cells is a function of the gray-zone parameter ΔIx ([75],  [76]).  The  parameter  ΔIx is  proportional  to  Ic 1/2 ,  where  Ic  is  the  critical  current  of  two junctions forming a decision-making pair. The noise immunity is proportional to ΔIx/Ic and drops as Ic -1/2 [77] for smaller critical currents.

A designer of RSFQ/ERSFQ cells usually uses JJs with critical currents that are in the ±50% range around the average value. The minimum critical current from the MIT-LL SFQ5ee fabrication node is 38 µA. So, a further reduction of the average value of 50 µA is impossible without a fabrication upgrade.

The total number of JJs per island can be doubled by introduction of the second bias grid. Blocks B4-B6 in Figure 4.6 can be used in addition to B1-B3 to form the second bias bus.

However, the implementation of the 2 bias networks should be done carefully to avoid return current redistribution  (see  subsection  4.4.4  for  an  example)  and  problems  with  drain  vias.  The successful implementation of a double bias network was reported in [52].

The total count of 5000-6000 JJs per island seems achievable for the MIT-LL SFQ5ee fab node and circuits of reasonable complexity and functionality, like reported in [14].

Let us calculate the size of an island that comprises 5000 JJs and consumes 200 mA of the total bias. A cell of the minimum 40 µm × 20 µm size can accommodate up to 4 biased JJs (see Figure 4.3(c) and Figure 4.4(a) for the block diagram and layout of the horizontal bias JTL). It gives 200 µm 2 as the effective area for a single JJ. This estimation of the effective area per JJ is also confirmed by the design of the PRBS7 circuit in ([42], [78]) with the total occupied area of 220 µm × 120 µm and 122 JJs used. Note that the PRBS7 circuit in ([42], [78]) was assembled using the ST standard library cells without applying automatic place-and-route tools.

Let us assume that we can keep the effective area per single JJ unchanged after switching the  average  critical  current  from  250 µA  to  50 µA.  To  accommodate  such  a  modification,  all inductors should be increased by a factor of 5. This can be achieved by narrowing inductors and meandering them.

Thus, the DUT of 5000 JJs will occupy an area of 1 mm 2 . However, the total area of the SB island that includes CDRPs and biasing blocks (D and B blocks in Figure 4.6) will be about 1.6 mm 2 for a square-shaped DUT. As a result, 10 such islands can be placed on a 5 mm × 5 mm chip  with  16 mm 2 available  for  the  digital  circuit.  To  accommodate  10 6 JJs,  the  whole  digital circuitry should be partitioned into 200 serially biased islands and placed on 20 chips.

The automatic place-and-route procedure can be expected to roughly double the effective area per JJ, increasing the total number of chips to 40. The size of a multi-chip-module (MCM)

carrier  to  handle  a  5 × 8  matrix  of  40  flip-chips  is  about  32 mm × 50 mm,  assuming  a  1 mm separation between the flip-chips and 0.5 mm reserved on each edge of the MCM carrier for pads. In the very optimistic case, 10 6 JJs will be biased by 200 mA being recycled 200 times.

Serial Biasing does not reduce static power dissipation. The power dissipated in the bias resistors of the RSFQ circuit remains the same. It is the same 104 mW for 40 A in the case of parallel  biasing  with  the  nominal  bias  voltage  of  2.6 mV  and  for  200 mA  in  the  case  of  serial biasing with 520 mV of bias voltage accumulated over 200 islands. The advantage of SB is in the reduction of the number of current leads and associated heat load through them, as well as in the reduction of the total bias current per chip (compare 200 mA vs. 3.2 A for a chip with and without 16 serially biased islands respectively) and the resulting magnetic fields.

Note that in addition to 104 mW of static power dissipation (associated with bias resistors), there is also dynamic power dissipation caused by processes in the Josephson junctions [29]. The dynamic power dissipation is given by the expression

<!-- formula-not-decoded -->

where Ф0 is the magnetic flux quantum, Ib is the bias current, and f clk is the clock frequency. The total dynamic power consumption of 10 6 JJs operating at 40 GHz is 3.2 mW, which is 32.5 times smaller than 104 mW.

The  static  power  dissipation  can  be  eliminated  by  switching  to  the  ERSFQ  mode  of operation by replacing bias resistors used in RSFQ logic with inductors and Josephson junctions [29]. As a result, the total power dissipation will change from 107.2 mW to 6.4 mW, assuming 100% overhead (3.2 mW + 3.2 mW) for dynamic power consumption in the feeding JTL ([29], [79]).

The grapevine approach to serial biasing looks promising but requires further experimental verification. We need to prove experimentally the correct operation of serially biased islands with 5000 JJs and 200 mA of bias current. The next step is to convert them into serially biased ERSFQ islands, with optimal feeding JTL size and external/internal over-pumping implemented in ([79], [80]). The look-up table ([20], [81]) seems to be the ideal candidate for a test circuit because 1) its size can be adjusted by changing the number of bits to meet requirements on JJs' count and the total bias current per island, 2) HF testing can be done relatively easy by using the testbed described in [82], and used in ([25], [56]).

## 4.7 Conclusion

We adopted the grapevine (GV) biasing approach for serially biased (SB) circuits designed using  the  standard  RSFQ/ERSFQ  cell  library  developed  in  [57]  as  a  part  of  the  SuperTools program [46]. All the essential layout primitives, including the composite driver-receiver pairs for inter-island communication, were developed, and successfully verified by designing a test chip. The test structures worked up to 50 GHz at the BER level of 10 -12 . Detailed analyses of different layout structures using electromagnetic simulations were also presented.

## Chapter 5: Passive Transmission Lines for Serially Biased RSFQ Circuits

As  the  complexity  of  superconductor  circuits  grows,  a  dense  network  of  passive transmission lines (PTLs) is envisioned  to be used to interconnect cells in RSFQ circuits.  For serially  biased  circuits,  this  could  significantly  reduce  the  Josephson  junctions  (JJs)  and  bias current utilized simply for data buffering from point to point. A smaller serial bias current is always desirable  as  it  simplifies  current  management,  seen  in  the  previous  Chapters.  This  makes  it necessary  to  investigate  PTLs,  including  their  architectures,  simulation  methodologies,  and measurement  results,  in  detail.  In  the  cell  library  approach,  each  cell  has  dedicated  tracks  as placeholders for routing PTLs. Higher impedance PTLs are desirable since the narrower width of the transmission line may facilitate multiple tracks per unit cell. However, at higher impedances, the margins of the PTL receiver degrade rapidly. Additionally, model-to-hardware correlation for PTLs  is  challenging,  given  the  lack  of  accurate  simulation  tools.  In  this  Chapter,  we  design, simulate, and test PTLs in the MIT-LL SFQ5ee 10kA/2 Ω fabrication node. For the symmetric dual ground planes case, PTLs are in the M1 layer with M0 and M2 ground planes, or in the M3 layer with M2 and M4 ground planes. For the asymmetrical dual ground planes, PTLs are in the M2 or M3 layers with M1 and M4 ground planes. We observed ±30% margins in measurement at low frequency, for these PTLs. We have also adopted a multi-layer multiconductor transmission line model for PTL simulations. Reasonable model-to-hardware correlation is observed for low and high-frequency operations.

## 5.1 Introduction

Scaling  superconducting  digital  circuits  require  an  efficient  and  dense  network  of interconnects. Traditionally active elements such as the Josephson Transmission Lines (JTLs) have been used to transfer Single Flux Quantum (SFQ) pulses between the different logic blocks on the chip ([12], [83]). As circuit complexity increases, the current consumption and the area occupied by JTLs also increase. Passive Transmission Lines (PTLs) are power and area efficient with respect to JTLs. PTLs also have significantly smaller delay per unit length compared to JTLs.

A PTL connected between an SFQ driver and receiver is used ubiquitously in many RSFQ circuits ([84]-[90]). This Chapter focuses on optimizing stripline PTLs for the MIT-LL SFQ5ee process with 8 Nb layers M0 through M7 [9] (see Figure 5.1). Two specific cases are considered: (a)  routing  signals  between  densely  packed  digital  cells,  and  (b)  providing multi-layer  routing between distant blocks. In this Chapter, PTLs have been simulated and designed for performance and reliability. The PTLs with symmetric and asymmetric ground planes, seen in Figure 5.1, have Passive Transmission Line Configurations

Figure 5.1: Metal stack of the MIT-LL SFQ5ee process showing layers for PTLs with symmetric (a) and asymmetric (b) dual ground planes. The former is used to route signals outside of standard cells, whereas the latter is used to route PTLs under active circuitry.

<!-- image -->

| M7      | M7                   | Sky plane   | M7      | M7             | Sky plane   |
|---------|----------------------|-------------|---------|----------------|-------------|
| M5- M6  | JJ, Inductors M5- M6 | M5- M6      | M5- M6  | JJ, Inductors  |             |
| M4      | Ground               | M4          | M4      | Ground         | M4          |
| M3      | PTL M3               | M3          | M3      | PTL            |             |
| M2      | Ground               | M2          | M2      | PTL/Occasional | M2          |
| M1      | PTL                  | M1          | M1      | Ground         | M1          |
| M0      | Ground               | M0          | M0      | Bias           | M0          |
| (a) (b) | (a) (b)              | (a) (b)     | (a) (b) | (a) (b)        | (a) (b)     |

DISTRIBUTION STATEMENT A:

Approved for public release; distribution is unlimited. DCN #: xx-xxxx-xx

been fabricated and experimentally verified [28]. Their operating margins at low frequency (LF) are  reported.  High-frequency  (HF)  measurement characterization  of  these  PTLs  has  also  been performed. To establish model-to-hardware correlation, we have developed a circuit simulation methodology using electromagnetic simulations. The correlation is verified at both LF and HF.

In  the  cell  library  approach,  such  as  the  SuperTools  library  discussed  in  Chapter 4, dedicated metal layers are provided for PTL routing and for biasing of cells [57]. The PTL tracks are used to route signals between densely packed cells without disturbing the circuitry above. At least two metal layers need to be available for routing the bias lines and PTLs in the horizontal and vertical  directions.  To  minimize  crosstalk  between  the  bias  lines  and  PTLs,  routing  them  on different metal layers, preferably with ground plane isolation between them, is desirable. To enable this, the bias lines network is primarily routed in the M0 layer, M1 serves as one of the PTL ground planes as well as serves to minimize crosstalk from the bias lines. The choice of M1 as a ground plane has led to M2 or M3 being the only available metal layer for the PTL signal layer. The ground planes for such a PTL are M1 and M4, which are asymmetrical with respect to the distance to the signal layer. For routing signals between distant blocks with no active circuitry on top, we avoid this asymmetrical configuration and use M3 or M1 as the PTL signal layer with M2-M4 and M0-M2 as dual ground planes. The M2 ground plane between the two PTLs also offers ground plane isolation reducing crosstalk.

In Figure 5.1, the PTLs with symmetric dual ground plane consists of M0-M1-M2 and M2M3-M4 PTLs; where M1 and M3 are the signal layers, and the M0-M2 and M2-M4 are the dual ground layers, respectively. For the PTLs with asymmetric dual ground planes, M1-M2-M4 and M1-M3-M4 PTLs are considered; where the PTL signal layer is M2 or M3, and M1-M4 are the

dual ground planes for both. This choice of metal layers frees M0 to be used for bias lines and allows PTLs to run under active circuits as well.

## 5.2 PTL Characterization

## 5.2.1 Electromagnetic simulations to establish PTL width

We use a Sonnet EM model that takes into account the surface inductance of Nb ([91], [92]). The dielectric constant for SiO2 is assumed to be 4.6. Presently, we have not accounted for the dielectric loss tangent, but it can be incorporated into simulations. Figure 5.2(b) below shows the layout of an M2-M3-M4 PTL. The ground planes M2 and M4 are stitched together every 20 µm so that half-wavelength resonant frequencies are outside the frequencies of interest. Sonnet Simulation to establish PTL width

<!-- image -->

DISTRIBUTION STATEMENT A:

Approved for public release; distribution is unlimited. DCN #: xx-xxxx-xx

Figure 5.2: Return loss in (dB) (S11) shown in (a) for a 2-port Sonnet EM simulation for a M2-M3-M4 (symmetric) PTL with 12.5 Ω characteristic impedance . In the 3D model of the PTL layout in (b), the M2 and M4 ground planes are stitched every 20µm to improve the frequency response. In (c), layout of the TDR test structure of the 2.2 µm M2-M3-M4 PTL is shown.

In the library approach, narrower PTLs make the layout more area efficient but require a higher impedance. For this purpose, we choose a high impedance PTL of 12.5Ω as a starting width, for which a parametric sweep of widths in Sonnet, gives a 2.2 µm width with the least return loss (S11) over a wideband, as seen in Figure 5.2(a). To measure the characteristic impedance, we designed the test circuit shown in Figure 5.2(c), comprising a 40 cm long, 2.2 µm wide M2-M3M4 PTL. The PTL was connected to the pad on one end and terminated to the ground on the other. The impedance was measured using a Time Domain Reflectometry (TDR) measurement using a Tektronix CSA803 communication signal analyzer. The average PTL impedance measured in the TDR was observed to be 12.5Ω. This matches the simulation and is a promising result, lending credibility to the simulation model.

Circuit simulations (discussed in section 5.3) indicate that the 12.5Ω PTL would attenuate the current amplitude of the SFQ pulse resulting in reduced operating margins. A bias margin of ±30%  is  typically  required  of  RSFQ  circuits,  for  robust  operation.  With  this  in  mind,  lower impedance 8 Ω and 10 Ω PTLs  are considered potential candidates for a cell library implementation. Based on EM simulations, the widths needed for the 8 Ω, and 10 Ω PTLs, for the symmetric and asymmetric dual ground plane configurations are calculated and  summarized in Table 5.1.

Table 5.1: Impedance-width of PTLs for different signal and ground conductor configurations

|   PTL Impedance (Ω) | PTL Signal Layer   | PTL Ground Layers   |   Width (µm) |
|---------------------|--------------------|---------------------|--------------|
|                12.5 | M3                 | M2-M4               |          2.2 |
|                10   | M3                 | M2-M4               |          2.8 |
|                 8   | M3                 | M2-M4               |          3.6 |
|                10   | M3                 | M1-M4               |          4.3 |
|                 8   | M3                 | M1-M4               |          5.2 |

## 5.2.2 PTL Receiver Bias Margins as a function of Impedance

A test structure comprising a single junction driver, 1 mm long M2-M3-M4 PTL, and a 2 junction receiver,  was  designed and fabricated in  the MIT-LL SFQ5ee fabrication node.  We observed  from  measurements  that  the  PTL  drivers  consistently  have  significantly  higher  bias margins. Hence the PTL performance is characterized by the receiver margins. The measurements reported here have been performed using Octopux [68], using ICE-T [34].

The receiver bias margins with respect to the target design voltage of 2.6 mV are reported. We  observe  in  the  plot  of  Figure 5.3,  the  average  margins  across  4  wafer  locations  with  the standard deviation. The wider M2-M3-M4 (symmetric) PTL (3.6 µm) has a lower characteristic impedance  (8 Ω)  and  larger  margins.  A  similar  observation  from  circuit  simulations  is  thus confirmed.

Figure 5.3: Receiver bias margins as a function of impedance for the M2-M3-M4 PTL. Lower impedance PTLs have higher bias margins. This result identifies the 8Ω PTL as a strong candidate for the cell library implementation.

<!-- image -->

## 5.2.3 Receiver Bias Margins for the 2 PTL architectures

Both the symmetric (M0-M1-M2 or M2-M3-M4) and asymmetric (M1-M2-M4 or M1M3-M4) PTLs are  to  be  used  for  routing,  hence  we  designed  test  structures  comprising  PTL drivers, receivers and 1 mm long PTLs. Figure 5.4 reports the receiver bias margins for both sets of these PTLs with characteristic impedances of 8 Ω and 10 Ω. Note that this measurement was performed using Octopux [68] but in liquid Helium. This can explain some of the differences in the margins between Figure 5.3 and Figure 5.4.

Both variants of the 8 Ω PTLs are found to satisfy the margin criterion. The center of the margin is shifted to the lower side. The asymmetric PTLs are found to have slightly higher margins

Figure 5.4: Receiver bias margins of the M2-M3-M4 and M1-M3-M4 PTLs for 8 Ω and 10 Ω impedances satisfy the margin criterion. 10 Ω PTLs have slightly reduced margins but may still be used in certain scenarios.

<!-- image -->

closer to ±30%. We observe that the 8 Ω PTL is a conservative design, and the 10 Ω PTL may also be used in cases where circuit area is an important constraint.

## 5.3 PTL Circuit Simulations

Accurate  PTL  simulation  methodology  is  required  for  complex  circuits  with  PTL interconnections. Circuit simulation helps improve the model-to-hardware correlation for PTLs. Time  domain  simulations  also  help  in  accurately  modeling  the  delay  of  PTLs  and  studying reflections, attenuation, and other properties. They can be further used for evaluating variants of drivers and receivers. In this section, we describe circuit simulation models used for PTLs, the electromagnetic  simulator-based  RLGC  model,  and  its  advantages  over  other  models.  A preliminary analysis of hardware correlation is also reported.

## 5.3.1 Adoption of Multi-Layer Transmission Line Model for PTLs

A distributed transmission line-based inductor-capacitor (LC) model has been designed with  the  L  and  C  values  obtained  from  microstrip  line  calculators,  such  as  SLINE,  based  on approximate analytical expressions [93]. The L and C values are approximated for a stripline in this. The advantage here is that the model can be easily used in SPICE simulators. However, it is inadequate  to  accurately  capture  high-frequency  behavior  such  as  reflections.  It  also  requires manual length scaling for different PTL lengths.

Sonnet electromagnetic (EM) simulator [66] is more accurate than a circuit model. We have  already  established  in  the  previous  section  that  the  PTL  impedance  correlates  well  with measurement results, by means of the TDR measurement. The advantage of using EM data such as  S  parameters  is  that  they  are  an  accurate  representation  of  the  frequency  response  of  a

transmission line. One can also incorporate the dielectric loss tangent as a function of frequency. We can also verify PTL behavior using Smith charts, easily plotted on an EM tool such as Sonnet. Different geometries of PTLs can also can also be simulated and studied. Furthermore, bends, and inter-layer transitions, along the length of the PTL, can also be simulated. Secondary effects such as DC coupling and cross-talk can also be simulated. The disadvantage of this approach is that it is  impractical  to  export  simulation  results  from  Sonnet  to  SPICE  for  each  PTL  configuration. Table 5.2 shows an example of the memory and simulation time per frequency point as a function of the length of the PTL, in Sonnet.

Table 5.2: The simulation time and memory requirement increases with PTL length

|   PTL length simulated (µm) |   Time/Frequency (s) |   Memory Required (MB) |
|-----------------------------|----------------------|------------------------|
|                          80 |                   95 |                    542 |
|                         200 |                  760 |                   3529 |

The  EM  simulation  is  performed  in  Sonnet  from  0  to  300 GHz  nominally  with  a combination  of  the  adaptive  band  sweep  (ABS)  and  linear  sweep  to  obtain  accurate  results. Previously, a Sonnet extracted lumped circuit model was used to generate driver/receiver circuit parameters [94]. This approach is limited as a lumped model can only be derived at a particular frequency. With the objective of importing these results in SPICE, we propose incorporating the Resistance Inductance Conductance Capacitance (RLGC) data generated from an EM simulation (see Figure 5.5), into a SPICE simulator. For example, the Cadence Virtuoso environment has a multi-layer,  multi-conductor transmission line model, 'mtline', in their analogLib library. This accepts RLGC data as an input and has the option for parametrizing length. This is the main benefit of using the RLGC model, as it allows for SPICE simulation of arbitrary lengths of PTLs with a single RLGC file generated in Sonnet, by simulating a PTL of an appropriate length.

For the highest frequency that we want to transmit on the PTL, the length of the PTL ( l ) to

Figure 5.5: Example of the RLGC data file generated for an 80 µm long, 8 Ω M2 -M3M4 PTL from an EM simulation. All values are reported per meter. This file can be used to simulate much longer lengths in SPICE simulators.

| ; < FTYP RLGC 12 ; < LENGTH 8e-005   | ; < FTYP RLGC 12 ; < LENGTH 8e-005                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| FORMAT                               | Freq: L1:1 R1:1 C1:1 G1:1                                                                                           |
| 1.0e9 :                              | ----------------------------------------------------------- 9.77632887e-8 2.03445684e-5 1.53106828e-9 3.2638717e-11 |
| 1.0e10 :                             | ----------------------------------------------------------- 9.77620803e-8 1.76107065e-7 1.53106479e-9 1.5866086e-11 |
| 1.5e10 :                             | ----------------------------------------------------------- 9.77609054e-8 6.2261177e-10 1.5310604e-9 2.1092558e-12  |

be simulated in Sonnet for RLGC data generation is l &lt;  where  is the wavelength on the line. This restriction on the length for RLGC data arises as for a length equal to  the S11 will be zero, for any L, C combination. Hence, we choose a line length that is approximately 170 degrees or less in electrical length.

The SFQ pulse propagation time for a 1 mm long 8 Ω M2-M3-M4 PTL is compared for SLINE, RLGC, S2P, and LC models. The LC model is a distributed model with L and C values from Sonnet. It lacks the length parametrization and the frequency dependence of RLGC. While S2P results are the most accurate, the simulated times for the LC and RLGC results closely match the S2P, as seen in Table 5.3.

Table 5.3: Comparison of SFQ pulse propagation time for different PTL models

| PTL Model   |   SFQ Pulse propagation time for 1 mmPTL length (s) |
|-------------|-----------------------------------------------------|
| SLINE       |                                               10.8  |
| RLGC        |                                               12.97 |
| LC          |                                               13.17 |
| S2P         |                                               13.03 |

## 5.3.2 Model to Hardware Correlation

We compare the measurement results for low-frequency Octopux measurement for (a) an 8 Ω M2-M3-M4 PTL and (b) 8 Ω M1-M3-M4 PTL with their corresponding simulation results. The PTLs were simulated with a data rate of 200 ps. We find a good correlation between the PTLs and their corresponding simulations. In test, as seen in Table 5.4, the M1-M3-M4 PTL reported slightly higher margins. The simulation could capture this improvement.

Table 5.4: Low frequency model to hardware correlation between measured and simulated margins for the 8 Ω M2 -M3-M4 PTL, with symmetric ground planes and the 8 Ω M1-M3-M4 PTL with asymmetric ground planes.

| Type       |   Measured Margins Max (%) |   Measured Margins Min (%) |   Simulated Margins Max (%) |   Simulated Margins Min (%) |
|------------|----------------------------|----------------------------|-----------------------------|-----------------------------|
| Symmetric  |                       20.7 |                      -33.9 |                       27.65 |                      -34.3  |
| Asymmetric |                       20.5 |                      -38.1 |                       26.79 |                      -40.62 |

In  the  high-frequency  measurement  results  for  PTLs  reported  in  [28],  resonance  was observed for both the PTL variants between 30-40 GHz. Resonance mitigation techniques have been  further  developed  and  discussed  in  [27].  High-frequency  simulations  of  both  the  PTLs (symmetric  and  asymmetric  ground  planes)  identified  the  resonant  frequencies  with  good correlation.  We  can  also  study  the  margin  behavior  for  frequencies  higher  than  67  GHz,  a maximum for many high-speed generators. In Figure 5.6, the maximum and minimum receiver

Figure 5.6: Model to hardware correlation for the high-frequency operation of (a) M2M3-M4 PTL and (b) M2-M3-M4 PTLs. The resonant frequencies at 35 GHz and 40 GHz for these two variants are captured in the simulation.

<!-- image -->

<!-- image -->

bias margins are plotted as a function of the frequency of operation. At the resonant frequencies, the measurements show maximum shrinkage of margins, indicating a very small operating region. The simulation, however, captures this behavior by showing a sharp reduction in the minimum margins around the resonant frequency without capturing the absence of operation. In the future, we plan to introduce non-idealities such as surface resistance of Nb and dielectric loss tangent to improve the correlation in margins.

## 5.4 Conclusion

We have proposed, measured, and validated the PTLs with symmetric and asymmetric dual ground planes in the MIT-LL SFQ5ee fabrication node that could be used as part of a cell library, such as the SuperTools cell library. We have observed that lowering PTL impedance improves the receiver margins. An optimum trade-off between the margins and PTL width has been performed, and  the  8 Ω  impedance  has  been  chosen.  We  have  also  reported  on  a  PTL  circuit  simulation methodology and have established a model-to-hardware correlation.

## Conclusion

Rapid Single Flux Quantum (RSFQ) circuits  are a promising candidate for  high-speed, low-power  digital circuitry applications. Scaling this technology, however, has multiple challenges, such as the need for improved fabrication yield, development of more sophisticated simulation tools, reduction of DC bias currents, etc. This thesis focuses on addressing the issue of DC bias current reduction using the serial biasing technique, focusing on speed and reliability. The Chapters of this thesis address different aspects of bias current reduction by separately discussing bias current management, interface circuitry, and scalability.

Chapter  2  of  the  thesis  presents  a  new  grapevine  biasing  technique  for  managing  bias currents on serially biased islands. This involves creating dedicated return current paths for the bias currents resulting in a well-behaved current distribution on the island. It is then implemented on RSFQ circuits, such as the digital decimation filter (DDF) and the 3-to-2 parallel counter. These circuits were successfully tested at both low (LF) and high (HF) frequencies. At LF, the serially biased  DDF  showed  no  degradation  in  operating  margins  compared  to  its  parallel  biased counterpart. At HF, the serially biased parallel counters successfully operated with open margins up to 20 GHz with a BER&lt;10 -12 . The experiments in this Chapter confirm the effectiveness of the grapevine biasing technique. This Chapter shows that without optimizing a circuit for a single bias, it is difficult to attribute low margins exclusively to the serial biasing scheme. The measurements

in this Chapter also demonstrate the necessity of a serially biased circuit to support nontrivial input data streams for testing.

Chapter 3 reports a high-speed driver-receiver pair (DRP) circuit for serially biased circuits that transfer SFQ pulses with galvanic isolation across the floating islands. It presents a PRBS generator-based testbed for DRP characterization. The fabricated DRP was successfully tested up to 60 GHz with open margins and a BER&lt;10 -12 . This Chapter compares and contrasts the grapevine (GV), developed in the previous Chapter, with the straightforward (SF) biasing schemes using the DRP  testbed.  It  shows  the  benefit  of  the  GV  over  the  SF  biasing  scheme  in  both  test  and electromagnetic simulations. It demonstrates the need for GV biasing for small bias currents. It identifies low mutual inductance in the DRP transformer and magnetic flux trapping as potential reasons for operating margin shrinkage.

Chapter 4 of this thesis presents the serial biasing technique for an EDA-based design flow of RSFQ circuits. Based on the IARPA SuperTools cell library, it develops all the components of the scheme, such as the composite DRPs, and GV biasing, and proposes rules for layout assembly that are compatible with a synthesis tool. The DRPs developed in this Chapter were observed to operate up to 50 GHz successfully and with open margins (BER&lt;10 -12 ). It  presents a thorough characterization of the DRPs,  focusing on their performance as a function of islands, interconnections  used  on  the  island,  and  the  impact  of  crosstalk  between  DRPs,  on  operating margins. It also presents factors limiting margins. This Chapter demonstrates how electromagnetic simulations can be used to develop layout features and design rules, which, when implemented by a designer, could result in a robust and conservative design. The proven methods developed in this Chapter could be used to serially bias RSFQ circuits with around 10 6 Josephson junctions.

Chapter 5 presents the design, simulation, and measurement of Passive Transmission Lines (PTLs)  used  for  routing  SFQ  signals  without  needing  active  circuitry  such  as  JTLs.  This  is important for a complex serially biased circuit as it results in lower bias currents on each island, potentially  simplifying  current  management.  This  Chapter  develops  two  PTL  architectures  for routing library cells and demonstrates good correlation for PTL impedance in test and simulation. It characterizes the PTL performance as a function of the receiver bias margins while also showing how lowering characteristic impedance resulted in wider receiver bias margins. An optimum tradeoff between impedance and bias margins is achieved in this Chapter. It also characterizes the PTLs, in measurement, up to 67 GHz and shows a promising model-to-hardware correlation between the simulation and the fabricated chips.  Establishing such correlations  is  key  to  enabling  PTLs  as interconnects in large-scale RSFQ circuits.

This thesis presents circuit techniques that enable the design of complex RSFQ circuits. Chapters 2, 3, and 4 focus on systematically developing the serial biasing technique for reducing the large DC bias currents associated with these circuits. Chapter 5 addresses the same problem but  from  the  perspective  of  SFQ  interconnects,  an  essential  component  of  any  scaled  design. Central  to  the  widespread  adoption  of  these  techniques  by  the  superconductor  electronics community is reliability in the form of wide operating margins. While high operating speed is undoubtedly one of the most attractive features of RSFQ circuits, wide margins at such rates are a must for deployment on the field. Improvements in the areas such as fabrication upgrades and design  tool  development  will  significantly  help  in  achieving  reliable  operation,  making  this research product ready.

## References

- [1] H. K. Onnes, 'The resistance of pure mercury at helium temperatures,' Commun. Phys. Lab. Univ. Leiden , vol. 12, 1911.
- [2] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, 'Theory of superconductivity,' Physical Review , vol. 108, no. 5, pp. 1175 -1204, December 1957.
- [3] T. Van Duzer and C. W. Turner, Principles of Superconductive Devices and Circuits , Prentice Hall, 1999.
- [4] W.  Meissner  and  R.  Ochsenfeld,  'Ein  neuer  Effekt  bei  Eintritt der Supraleitfähigkeit,' Naturwissenschaften , vol. 21, no. 44, pp. 787 -788, November 1933.
- [5] F. London and H. London, 'The electromagnetic equations of the supraconductor,' Proceedings of the Royal Society of London. Series A -Mathematical and Physical Sciences, vol. 149, no. 866, pp. 71 -88, March 1935.
- [6] A. M. Kadin, Introduction to Superconducting Circuits , Wiley, 1999.
- [7] K.  K.  Likharev, Dynamics  of  Josephson  Junctions  and  Circuits ,' Gordon  and  Breach  Science Publishers, 1986.
- [8] D. E. McCumber, ' Effect of ac impedance on dc voltage-current characteristics of superconductor weaklink junctions,' Journal of Applied Physics , vol. 39, no. 7, pp. 3113 -3118, June 1968.
- [9] S.  K.  Tolpygo et  al. ,  'Advanced fabrication  processes  for  superconductor  electronics:  current status and new d evelopments,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, pp. 1 -13, Aug 2019.
- [10] O. Mukhanov, V. K. Semenov, and K. K. Likharev, 'Ultimate performance of the RSFQ logic circuits,' IEEE Trans. Magn. , vol. 23, no. 2, pp. 759 -762, Mar 1987.
- [11] O. Mukhanov, S. V. Rylov, V. K. Semenov, and S.V. Vyshenskii, 'RSFQ Logic arithmetic,' IEEE Trans. Magn. , vol. 25, no. 2, pp. 857 -860, Mar 1989.
- [12] K.  K.  Likharev  and  V.  K.  Semenov,  'RSFQ logic/memory  family:  a  new  Josephson-junction technology for sub-terahertz-clock-frequency digital s ystems,' IEEE Trans. Appl. Supercond. , vol. 1, no. 1, pp. 3 -28, Mar 1991.

- [13] W. Chen, A. V . Rylyakov, V. Patel, J. E. Lukens, and K. K. Likharev, 'Rapid single flux quantum tflip flop operating up to 770 GHz,' IEEE Trans. Appl. Supercond. , vol. 9, no. 2, pp. 3212 -3215, Jun 1999.
- [14] D. Gupta et al. , 'Digital channelizing radio frequency receiver,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 430 -437, Jun 2007.
- [15] O. A. Mukhanov, D. Gupta, A. M. Kadin, and V. K. Semenov, 'Superconductor analog -to-digital converters,' Proceedings of the IEEE , vol. 92, no. 10, pp. 1564 -1584, October 2004.
- [16] A. Inamdar, A. Sahu, J. Ren, S. Setoodeh, R. Mansour, and D. Gupta, 'Design and evaluation of flash ADC,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, pp. 1 -5, Jun 2015.
- [17] A. Inamdar, A. Sahu, J. Ren, A. Dayalu, and D. Gupta, 'Flash ADC compa rators and techniques for their evaluation,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Art no. 1400308, Jun 2013.
- [18] T. V. Filippov, S. V . Pflyuk, V. K. Semenov, and E. B. Wikborg, 'Encoders and decimation filters for superconductor oversampling ADC s,' IEEE Trans. Appl. Supercond. ,  vol. 11, no. 1, pp. 545 -549, Mar 2001.
- [19] T. V . Filippov, S. Sarwana, A. Sahu, A. F. Kirichenko, and D. Gupta, 'Multi -bit mixers for digitalRF receivers,' IEEE Trans. Appl. Supercond. , vol. 21, no. 3, pp. 818 -822, Jun 2011.
- [20] T.  V .  Filippov,  A.  Sahu,  A.  F.  Kirichenko,  and  D.  Gupta,  'Look -up  table  for  superconductor digitalRF predistorter,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 561 -564, Jun 2007.
- [21] A.  E.  Lehmann et al. ,  'Embedded  RSFQ  pseudorandom  binary  sequence  g enerator  for multichannel  highspeed  digital  data  link  testing  and  synchronization,' IEEE  Trans.  Appl. Supercond. , vol. 27, no. 4, Art no. 1301806, Jun 2017.
- [22] J. X. Przybysz, E. J. Dean, P. D. Dresselhaus, D. L. Miller, A. H. Worsham, and S. V. Polonsky, 'Spread spectrum data transfer from dewar to dewar at 2 gigachips per second,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 982 -985, Mar 2001.
- [23] M. Dorojevets, C. L. Ayala, N. Yoshikawa, and A. Fujimaki, '16 -Bit wave-pipelined sparse-tree RSFQ adder,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Art no. 1700605, Jun 2013.
- [24] M. Eren Çelik et al. , 'Fast RSFQ and ERSFQ parallel c ounters,' IEEE Trans. Appl. Supercond. , vol. 30, no. 7, pp. 1 -4, Oct 2020.
- [25] T. V. Filippov et al. , '20 GHz operation of an asynchronous wave -pipelined RSFQ arithmetic-logic unit,' Physics Procedia , vol. 36, pp. 59 -65, May 2012.

- [26] V.  V  Talanov et  al. ,  'Propagation  of  picosecond  pulses  on  superconducting  transmission  line interconnects,' Supercond. Sci. Technol. , vol. 35, no. 5, Art no. 055011, 2022.
- [27] B. Chonigman et al. , 'Optimization of passive transmission lines for single flux quantum c ircuits,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Art no. 1301206, Aug 2021.
- [28] A. Shukla, B. Chonigman, A. Sahu, D. Kirichenko, A. Inamdar, and D. Gupta, 'Investigation of passive transmission lines for the MIT-LL SFQ5ee p rocess,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Art no. 3500707, Aug 2019.
- [29] D.  E.  Kirichenko,  S.  Sarwana,  and  A.  F.  Kirichenko, 'Zero static  power dissipation biasing of RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 21, no. 3, pp. 776 -779, Jun 2011.
- [30] O.  A.  Mukhanov,  'Energy -e fficient  single  flux  quantum  technology,' IEEE  Trans.  Appl. Supercond. , vol. 21, no. 3, pp. 760 -769, Jun 2011.
- [31] N.  Takeuchi,  D.  Ozawa,  Y.  Yamanashi,  and  N.  Yoshikawa,  'An  adiabatic  quantum  flux parametron as an ultra-lowpower logic device,' Supercond. Sci. Technol. ,  vol. 26, no. 3, Art no. 035010, 2013.
- [32] N. Takeuch i, Y. Yamanashi, and N. Yoshikawa, 'Energy efficiency of adiabatic superconductor logic,' Supercond. Sci. Technol. , vol. 28, no. 1, Art no. 015003, 2015.
- [33] Q. P. Herr, A. Y. Herr, O. T. Oberg, and A. G. Ioannidis, 'Ultra -lowpower superconductor logic,' Journal of Applied Physics , vol. 109, no. 10, Art no. 103903, May 2011.
- [34] V. V. Dotsenko et al. , 'Superconductor integrated circuit (IC) testing with the integrated cryogenic electronics testbed (ICET),' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, Art no. 1200407, Jun 2017.
- [35] R. P. Robertazzi, I. Siddiqi, and O. Mukhanov, 'Flux trapping experiments in single flux quantum shift registers,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 3164 -3167, Jun 1997.
- [36] B. Ebert, T. Ortlepp, and F. H. Uhlmann, 'Experimental study of the effect of flux trapping on the operation of RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 607 -610, Jun 2009.
- [37] S. Narayana, Y. A. Polyakov, and V. K. Semenov, 'Evaluation of flux trapping in superconducting circuits,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 640 -643, Jun 2009.
- [38] Y.  Yamanashi,  H. Imai,  and  N.  Yoshikawa,  'Influence  of magnetic  flux  trapped  in  moats  on superconducting integrated circuit o peration,' IEEE Trans. Appl. Supercond. , vol. 28, no. 7, pp. 1 -5, Oct 2018.

- [39] C.  J.  Fourie  and  K.  Jackman,  'Software  tools  for flux  trapping  and magnetic field analysis in superconducting circuits,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Art. no. 1301004, Aug 2019.
- [40] C.  J.  Fourie  and  K.  Jackman,  'Experimental verification  of  moat  design  and  flux  trapping a nalysis,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Art no. 1300507, Aug 2021.
- [41] A. Inamdar, J. Ren, and D. Amparo, 'Improved model -to-hardware correlation for superconductor integrated circuits,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Art no. 1300308, Jun 2015.
- [42] A. Inamdar et al. , 'Development of superconductor advanced integrated circuit design flow using Synopsys t ools,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Art no. 1301907, Aug 2021.
- [43] M.  Pedram  and  Y.  Wang,  'Design automation  methodology  and  tools  for  superconductive electronics,' 2018 IEEE/ACM International Conference on Computer-Aided Design (ICCAD) , pp. 1 -6.
- [44] C.  Fourie,  'Single  flux  quantum  circuit  technology  and  CAD  overview,' 2018  IEEE/ACM International Conference on Computer-Aided Design (ICCAD) , pp. 1 -6.
- [45] C. L. Ayala, O. Chen, and N. Yoshikawa, 'AQFPTX: adiabatic quantum-flux-parametron timing eXtraction t ool,' 2019 IEEE International Superconductive Electronics Conference (ISEC) , pp. 1 -3.
- [46] 'IARPA SuperTools Program, 2018,  Ac cessed on: Jan. 30, 2021. [Online]. Available: https://iarpa.gov/index.php/research-programs/supertools .'
- [47] V.  K.  Semenov  and  M.  A.  Voron ova, 'DC  voltage  multipliers: a novel  application of synchronization in J osephson junction arrays,' IEEE Trans. Magn. , vol. 25, no. 2, pp. 1432 -1435, Mar 1989.
- [48] V. K. Semenov and Y. A. Polyakov, 'Circuit improvements for a voltage multiplier,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 550 -553, Mar 2001.
- [49] M. W. Johnson, Q. P. Herr, D. J. Durand, and L. A. Abelson, 'Differential SFQ transmission using either inductive or capacitive coupling,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 507 -510, Jun 2003.
- [50] S. B. Kaplan, 'Serial biasing of 16 modular circuits at 50 Gb/s,' IEEE Trans. Appl. Supercond. , vol. 22, no. 4, Art no. 1300103, Aug 2012.
- [51] K. Ehara, A. Takahashi, Y. Yamanashi, and N. Yoshikawa, 'Development of pulse transfer circuits for serially biased SFQ circuits using the Nb 9-layer 1μm process,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Art no. 1300504, Jun 2013.

- [52] K. Sano et al. , 'Reduction of the supply current of single-flux-quantum time-to-digital converters by current recycling t echniques,' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, pp. 1 -5, Jun 2017.
- [53] V. K. Semenov and Y. A. Polyakov, 'Current recycling: new result s,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Art no. 1302304, Aug 2019.
- [54] N.  K.  Katam,  B.  Zhang,  and  M.  Pedram,  'Ground plane  partitioning  for  current  recycling  of superconducting  c ircuits,' 2020  Design,  Automation  &amp;  Test  in  Europe  Conference  &amp;  Exhibition (DATE) , pp. 478 -483.
- [55] G. Krylov and E. G. Friedman, 'Partitioning RSFQ Circuits for current r ecycling,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Art no. 1301706, Aug 2021.
- [56] A. Shukla et al. , 'Pulse interfaces and current management techniques for serially biased RSFQ c ircuits,' IEEE Trans. Appl. Supercond. , vol. 32, no. 4, Art no. 1300407, Jun 2022.
- [57] S. S. Meher et al. , 'Superconductor standard cell library for advanced EDA d esign,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Art no. 1300807, Aug 2021.
- [58] A. M. Kadin, R. J. Webber, and S. Sarwana, 'Effects of superconducting return currents on RSFQ circuit performance,' IEEE Trans. Appl. Supercond. , vol. 15, no. 2, pp. 280 -283, Jun 2005.
- [59] H. Terai, Y. Kameda, S. Yorozu, A. Fujimaki, and Z. Wang, 'The effects of dc bias current in large -scale SFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 502 -506, Jun 2003.
- [60] S. Nagasawa et al. , 'Nb 9 -layer fabrication process for superconducting large-scale SFQ circuits and its process evaluation,' IEICE Trans. Electron. , vol. E97-C, no. 3, pp. 132 -140, Mar 2014.
- [61] T.  Ando et  al .,  'Three -dimensional  adiabatic  quantum-flux-parametron  fabricated  using  a double-activelayered niobium process,' Supercond. Sci. Technol., vol. 30, 2017, Art. no. 075003.
- [62] A. M. Kadin, R. J. Webber, and D. Gupta, 'Current leads and optimized thermal packaging for superconducting systems on multistage cryocoolers,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 975 -978, Jun 2007.
- [63] J.  H.  Kang  and  S.  B.  Kaplan,  'Current  recycling  and  SFQ  signal  transfer  in  large  scale  RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 547 -550, Jun 2003.
- [64] T. V . Filippov, A. Sahu, S. Sarwana, D. Gupta, and V. K. Semenov, 'Serially biased components for digital-RF r eceiver,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 580 -584, Jun 2009.

- [65] M. Igarashi, Y. Yamanashi, N. Yoshikawa, K. Fujiwara, and Y. Hashimoto, 'SFQ pulse transfer circuits using inductive coupling for current recycling,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 649 -652, Jun 2009.
- [66] 'Sonnet User's Guide -Manual of the Program Sonnet. North Syracuse, NY, USA: Sonnet Software Inc., 2007,' 2007.
- [67] T.  V.  Filippov et  al. ,  'Parallel counters  for  low-pass  phase  modulation-d emodulation  ADCs,' IEEE Trans. Appl. Supercond. , vol. 28, no. 4, Art no. 1400105, Jun 2018.
- [68] D.  Y.  Zinoviev  and  Y.  A.  Polyakov,  'Octopux: an  advanced  automated  setup  for  testing superconductor circuits,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 3240 -3243, Jun 1997.
- [69] A.  Kirichenko,  S.  Sarwana,  D.  Gupta, and  D.  Yohannes,  'Superconductor  digital  receiver components,' IEEE Trans. Appl. Supercond. , vol. 15, no. 2, pp. 249 -254, Jun 2005.
- [70] S.  Polonsky,  P.  Shevchenko,  A.  Kirichenko,  and  D.  Zinoviev,  'PSCAN'96: new  software  for simulation and optimization of complex RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 2685 -2689, Jun 1997.
- [71] S.  K.  Tolpygo,  E.  B.  Golden,  T.  J.  Weir,  and  V.  Bolkhovsky,  'Mutual  and self-inductance  in planarized  multilayered  superconductor  integrated  circuits:  microstrips,  striplines,  bends, meanders,  ground  plane  p erforations,' IEEE  Trans.  Appl.  Supercond. ,  vol.  32,  no.  5,  Art  no. 1400331, Aug 2022.
- [72] C. J. Fourie, O. Wetzstein, J. Kunert, and H. G. Meyer, 'SFQ circuits with ground plane hole -assis ted inductive coupling designed with InductEx,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Art no. 1300705, Jun 2013.
- [73] J. M. Jaycox and M. B. Ketchen, 'Planar coupling scheme for ultra low noise D C SQUID s,' IEEE Trans. Magn. , vol. 17, no. 1, pp. 400 -403, Jan 1981.
- [74] D. Amparo, M. Eren Celik, S. Nath, J. P. Cerqueira, and A. Inamdar, 'Timing characterization for RSFQ cell l ibrary,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Art no. 1300609, Aug 2019.
- [75] T. V . Filippov, Y. A. Polyakov, V. K. Semenov, and K. K. Likharev, 'Signal resolution of RSFQ c omparators,' IEEE Trans. Appl. Supercond. , vol. 5, no. 2, pp. 2240 -2243, Jun 1995.
- [76] V. K. Semenov, T. V. Fil ippov, Y. A. Polyakov, and K. K. Likharev, 'SFQ bala nced comparators at a finite sampling rate,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 3617 -3621, Jun 1997.

- [77] T.  Filippov,  A.  Sahu, M.  Erencelik, D.  Kirichenko,  M.  Habib,  and D.  Gupta,  'Gray  Zone  and Threshold Current Measurements of the Josephs on Balanced Comparator,' IEEE Transactions on Applied Superconductivity , vol. 31, no. 5, 2021, doi: 10.1109/TASC.2021.3063329.
- [78] A. Inamdar et al ., '64 GHz operation of the pseudo random bit sequence generator using the dual RSFQ/ERSFQ standard cell li brary,' to appear in the IEEE Transactions on Applied Superconductivity.
- [79] A. Sahu, M. E. Çelik, D. E. Kirichenko, T. V . Filippov, and D. Gupta, 'Low -power digital readout circuit for superconductor nanowire single-photon d etectors,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Art no. 1301306, Aug 2019.
- [80] M.  E.  Celik et  al. ,  '25 -GHz  operation  of  ERSFQ  time-to-digital  c onverter,' IEEE  Trans.  Appl. Supercond. , vol. 31, no. 5, Art no. 1301805, Aug 2021.
- [81] A. Sahu, T. V. Filippov, and D. Gu pta, 'Components for superconductor digital -RF predistorter,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 585 -589, Jun 2009.
- [82] S.  B.  Kaplan,  A.  Kirichenko,  O.  A.  Mukhanov,  and  S.  Sarwana,  'A  prescaler  circuit  for  a superconductive time-to-digital converter,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 513 -516, Mar 2001.
- [83] M.  Tanaka et al. ,  'Demonstration  of  a  single -flux-quantum  microprocessor  using  passive transmission lines,' IEEE Trans. Appl. Supercond. , vol. 15, no. 2, pp. 400 -404, Jun 2005.
- [84] Y. Kameda, S. Yorozu, and Y. Hashimoto, 'A new design methodology for single-flux-quantum (SFQ) logic circuits using passive-transmission-l ine (PTL) wiring,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 508 -511, Jun 2007.
- [85] N. Kito, K. Takagi, and N. Takagi, 'A fast wire-routing method and an automatic layout tool for RSFQ digital circuits considering wire-length m atching,' IEEE Trans. Appl. Supercond. , vol. 28, no. 4, Art no. 1300105, Jun 2018.
- [86] K. Takagi et al. , 'SFQ p ropagation properties in passive transmission lines based on a 10-Nb-layer structure,' IEEE Trans. Appl. Supercond. , vol. 19, no. 3, pp. 617 -620, Jun 2009.
- [87] T.  V.  Filippov et  al. ,  'Experimental investigation  of  ERSFQ  circuit  for  parallel  multibit  data t ransmission,' 2017 16th International Superconductive Electronics Conference, ISEC 2017 , pp. 1 -4.
- [88] D.  Gupta,  W.  Li,  S.  B.  Kaplan,  and  I.  V .  Vernik,  'High -speed  interchip  data  transmission technology for superconducting multi-chip modules ,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 731 -734, Mar 2001.

- [89] S. Narayana, V. K. Semenov, Y. A. Polyakov, V. V. Dotsenko, and S. K. Tolpygo, 'Design and testing  of  high-speed  interconnects  for  superconducting  multichip  modules,' Supercond.  Sci. Technol. , vol. 25, no. 10, 2012, Art no. 105012.
- [90] S. B. Kaplan, V. V. Dotsenko, and D. Tolpygo, 'High -speed experimental results for an adhesivebonded superconducting multichip module,' IEEE Trans. Appl. Supercond. ,  vol.  17,  no.  2,  pp. 971 -974, Jun 2007.
- [91] S.  Setoodeh, R. R. Mansour, and D. Gupta, 'Multi -layer low temperature superconducting Kband  filter  and  diplexer  design,' 2013  IEEE  MTT-S  International  Microwave  Symposium  Digest (MTT) , pp. 1 -4.
- [92] A. R. Kerr, ''Surface Impedance of Superconductors and Normal Conductors in EM Simulators', NRAO  Report,  1999.  Available  at  http://library.nrao.edu/public/memos/alma/memo245.pdf,' 1999.
- [93] W. H. Chang, 'The inductance of a superconducting strip transmission line,' Journal of Applied Physics , vol. 50, no. 12, 1979.
- [94] S.  Razmkhah  and A.  Bozbey,  'Design  of  the passive  transmission  lines  for  different  stripline widths and i mpedances,' IEEE Trans. Appl. Supercond. , vol. 26, no. 8, Art no. 1301506, Dec 2016.