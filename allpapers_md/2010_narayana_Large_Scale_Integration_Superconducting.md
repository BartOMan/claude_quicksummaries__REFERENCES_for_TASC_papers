## S S St t t o o on n ny y y B B Br r ro o oo o ok k k U U Un n ni i i v v ve e er r rs s s i i i t t t y y y

<!-- image -->

<!-- image -->

The official electronic file of this thesis or dissertation is maintained by the University Libraries on behalf of The Graduate School at Stony Brook University .

© © © A A A l l l l l l R R R i i i g g g h h h t t t s s s R R R e e e s s s e e e r r r v v v e e e d d d b b b y y y A A A u u u t t t h h h o o o r r r . . .

## Large Scale Integration Issues in Superconducting Circuits

A Dissertation Presented by Supradeep Narayana to The Graduate School in Partial Fulfillment of the Requirements for the Degree of Doctor of Philosophy in Electrical Engineering Stony Brook University

May 2010

## Copyright by

## Supradeep Narayana 2010

## Stony Brook University

The Graduate School

## Supradeep Narayana

We, the dissertation committee for the above candidate for the Doctor in Philosophy degree, hereby recommend acceptance of this dissertation.

## Alex Doboli, Advisor of Dissertation Associate professor, Department of Electrical and Computer engineering

Vasili K. Semenov, Co-Advisor of Dissertaion Principle Investigator, Department of Physics and Astronomy

Ridha Kamoua, Chairperson of defense Associate Professor, Undergraduate Program Director, Department of Electrical and Computer engineering

Dmitri Donetski, Assistant Professor, Department of Electrical and Computer engineering

Dmitri V. Averin, Professor Department of Physics and Astronomy

The dissertation is acceptable by the Graduate School.

Lawrence Martin Dean of the Graduate School

## Abstract of the Dissertation

## Large Scale Integration Issues in Superconducting Circuits

by

Supradeep Narayana

Doctor of Philosophy in

Electrical Engineering

Stony Brook University

## 2010

Superconducting  digital  logic  technology,  Rapid  Single  Flux  Quantum  (RSFQ),  is established  as  the  fastest  technology  in  microelectronics  based  on  Josephson  junction devices.  Technological  challenges  in  large  scale  integration  of  superconductor  circuits (RSFQ)  namely:  flux  trapping,  low  power  dissipation  and  multi-chip  modules  are addressed here. One of the main limitations of the integration of the RSFQ circuits is flux trapping, which arises due to the presence of residual magnetic field during transition of the  circuit  into  superconducting  state.  Flux  trapping  is  an  unusual  problem  specific  in only  superconducting  circuits.  The  effect  of  flux  trapping  in  RSFQ  circuits  is  studied, with  a  controlled  3-D  magnetic  field  setup,  quantitatively.  Layout  configuration  with different  moat  patterns  making  RSFQ  circuits  tolerant  to  external  magnetic  field  upto 20mG was also developed.

Low power issue was addressed by developing a new logic family. Power independent logic, an improved form of RSFQ logic, enables the circuits to operate only when needed and  circuits  can  be  switched  off  the  remaining  time;  thereby  eliminating  static  power consumption  by  retaining  the  logic  state  of  the  circuit.  Flux  trapping  has  also  been investigated in power independent cells.

Current recycling is a technique to reduce the bias current applied for the operation of the  RSFQ  circuits.  In  this  technique  the  cells  are  biased  by  serial  connections.  The reduction in supply current is proportional to number of blocks connected in series The effect of magnetic field on the operating margins of the current recycling circuits has also been studied.

Operation  of  Multi-chip  modules,  one  of  the  most  viable  solutions  to  develop  large scale  circuits,  was  demonstrated.  Multi-chip  modules  with  lithographically  designed bumps  is  presented  where  data  transmission  rate  between  two  superconducting  chips exceed  100GHz.  Finally,  the  development  of  the  multi-modulator  ADC  for  low  noise front end under-development is discussed.

## TABLE OF CONTENTS

| LIST OF FIGURES...................................................................................................VII      |                                                                                                             |
|----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| LIST OF TABLES...................................................................................................          | XIV                                                                                                         |
| ACKNOWLEDGEMENTS.....................................................................................                      | XXI                                                                                                         |
| 1. INTRODUCTION                                                                                                            | ....................................................................................................1       |
| 1.1 SUPERCONDUCTIVITY                                                                                                      | .............................................................................................1              |
| 1.2 JOSEPHSON JUNCTION                                                                                                     | .............................................................................................2              |
| 1.3 FLUX QUANTIZATION                                                                                                      | ..............................................................................................6             |
| 1.4 GENERATION OF FLUX QUANTA...............................................................................7              |                                                                                                             |
| 1.5 RSFQ CIRCUITS                                                                                                          | ....................................................................................................7       |
| 1.5.1 PRINCIPLE COMPONENTS OF RSFQ CIRCUITS......................................................8                         |                                                                                                             |
| 1.6 LARGE SCALE RSFQ CIRCUITS..............................................................................10              |                                                                                                             |
| 1.6.1 MOTIVATION                                                                                                           | ...................................................................................................10       |
| 1.7 CONTRIBUTION                                                                                                           | .....................................................................................................13     |
| 1.8 LIMITATIONS                                                                                                            | ........................................................................................................15  |
| 2. FLUX TRAPPING IN SUPERCONDUCTING CIRCUITS: THEORY                                                                       | AND                                                                                                         |
| EXPERIMENTS .........................................................................................................17    |                                                                                                             |
| 2.1 INTRODUCTION                                                                                                           | .....................................................................................................17     |
| 2.2 THEORETICAL FACTS.............................................................................................17       |                                                                                                             |
| 2.3 NUMERICALSIMULATIONS OF MAGNETIC FORCEON VORTICES                                                                      | ..............................20                                                                            |
| 2.4 HOWTRAPPED FLUX AFFECTS SUPERCONDUCTING CIRCUITS...................................22                                  |                                                                                                             |
| 2.5 RSFQ CIRCUITS FOR FLUX TRAPPING EXPERIMENTS ...............................................23                          |                                                                                                             |
| 2.5.1 MEASUREMENTPROCEDURE ............................................................................23                  |                                                                                                             |
| 2.6 EXPERIMENTAL SETUPS.........................................................................................24         |                                                                                                             |
| 2.7 ANALYSIS OF EXPERIMENTAL RESULTS                                                                                       | .................................................................26                                         |
| 2.7.1 GLOBALANALYSIS OF THE CIRCUIT                                                                                        | ..................................................................26                                        |
| 2.7.2 MARGINSOF INDIVIDUALD CELLS                                                                                          | ...................................................................27                                       |
| 2.8 DISCUSSION..........................................................................................................29 |                                                                                                             |
| 3. MOATS IN SUPERCONDUCTING CIRCUITS ..................................................34                                  |                                                                                                             |
| 3.1 INTRODUCTION                                                                                                           | .....................................................................................................34     |
| 3.2 BASIC DESIGN CONSIDERATIONS OF MOATS............................................................35                     |                                                                                                             |
| 3.3 MOAT PATTERNS                                                                                                          | .................................................................................................36         |
| 3.4 THRESHOLD LIMIT OF MOATPATTERN                                                                                         | ...................................................................43                                       |
| 3.5 EXPERIMENTAL RESULTS.......................................................................................44          |                                                                                                             |
| 3.6 EMPIRICAL RULES FOR DEVELOPING MOATPATTERNS                                                                            | ...........................................45                                                               |
| 3.7 FABRICATION DEPENDENCY .................................................................................46             |                                                                                                             |
| 3.8 DISCUSSION                                                                                                             | .........................................................................................................46 |
| 4. POWER INDEPENDENT RSFQ LOGIC CIRCUITS..........................................48                                       |                                                                                                             |

| 4.1 INTRODUCTION                                                                                                                                                                  | .....................................................................................................48   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 4.2.BASICS OF POWER INDEPENDENT OPERATION                                                                                                                                         | ........................................................48                                                |
| 4.3 DEVELOPING POWER INDEPENDENT RS FLIP-FLOP                                                                                                                                     | ................................................50                                                        |
| 4.4 INVESTIGATION OF POWER INDEPENDENT SHIFT REGISTER                                                                                                                             | ......................................51                                                                  |
| 4.4.1 DESIGN OF 6-BIT SHIFT REGISTER WITHPOWER INDEPENDENT CELLS                                                                                                                  | ..................51                                                                                      |
| 4.4.2 EXPERIMENTAL RESULTS                                                                                                                                                        | .................................................................................52                       |
| 4.5 FLUX TRAPPING IN POWER INDEPENDENT RSFQ CELLS                                                                                                                                 | ..........................................53                                                              |
| 4.6 DISCUSSIONAND CONCLUSION..............................................................................60                                                                      |                                                                                                           |
| 5. CURRENT RECYCLING: TECHNIQUE AND APPLICATION .......................61                                                                                                         |                                                                                                           |
| 5.1 INTRODUCTION                                                                                                                                                                  | .....................................................................................................61   |
| 5.2 SERIAL BIASING CIRCUIT TECHNIQUE                                                                                                                                              | ....................................................................62                                    |
| 5.2.1 EXPTERIMENTAL VERIFICATION OF CURRENTRECYCLING CIRCUIT                                                                                                                      |                                                                                                           |
| 5.3 SUMMING AMPLIFIER BASED OUTPUTDRIVER: APPLICATION OF FLOATING GROUNDS                                                                                                         | .....................65                                                                                   |
| JTL……………………………………………………………………………..……...67                                                                                                                                         |                                                                                                           |
| 5.3.1EXPERIMENTAL RESULTS OF SUMMING AMPLIFIERS…………………………70                                                                                                                       |                                                                                                           |
| 5.4 EFFECT OF EXTERNALMAGNETICFIELD…………………………………………..72                                                                                                                           |                                                                                                           |
| 5.4.1 IMPACTOF MAGNETIC FIELD ON 10-STAGE FTL BASED OUTPUTDRIVER……75 5.5 DISCUSSION ANDCONCLUSION .............................................................................75 |                                                                                                           |
| 6.1 INTRODUCTION                                                                                                                                                                  | .....................................................................................................77   |
| 6.2MCM MODELING..................................................................................................77                                                               |                                                                                                           |
| 6.2.1NEW BUMP STRUCTURE                                                                                                                                                           | .....................................................................................79                   |
| 6.3 TEST CIRCUIT........................................................................................................83                                                        |                                                                                                           |
| 6.4 EXPERIMENTAL RESULTS.......................................................................................84                                                                 |                                                                                                           |
| 6.5 DISCUSSIONAND CONCLUSION                                                                                                                                                      | ..............................................................................86                          |
| 7. MULTIMODULATION ADC CONCLUSION AND FUTURE                                                                                                                                      | WORK..............90                                                                                      |
| 7.1 INTRODUCTION .....................................................................................................90 7.2 BEHAVIORALSYSTEM MULTIMODULATOR ADC                  | ...........................90                                                                             |
| SIMULATION OF                                                                                                                                                                     |                                                                                                           |
| 7.3 CIRCUIT LEVEL DESIGN AND SIMULATION..............................................................93                                                                           |                                                                                                           |
| 7.3.1 DETERMINTATION OF CIRCUITPARAMETERS FOR ADC........................................93                                                                                       |                                                                                                           |
| 7.3.2 TRANSFORMER DESIGN ....................................................................................94                                                                   |                                                                                                           |
| 7.3.3 LC LOW PASS FILTER DESIGN ............................................................................96                                                                    |                                                                                                           |
| 7.5 PSCAN SIMULATION OF THE 4-MODULATOR ADC                                                                                                                                       | ..................................................99                                                      |
| 7.6 DISCUSSIONAND FUTURE WORK........................................................................102                                                                          |                                                                                                           |
| AND FUTURE WORK..............................................................103                                                                                                  |                                                                                                           |
| 8. CONCLUSION 8.1 CONCLUSIONS                                                                                                                                                     | ....................................................................................................103   |
| 8.2 RECOMMENDATIONS FOR FUTURE WORK                                                                                                                                               | ............................................................104                                           |
| REFRENCES.............................................................................................................107                                                         |                                                                                                           |
| APPENDIX................................................................................................................114                                                       |                                                                                                           |

## LIST OF FIGURES

| Figure 1.1 Temperature dependence of resistance of a superconducting material ............2                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
| Figure 1.2 RSJ model for Josephson junction..................................................................3                 |
| Figure 1.3 I-V characteristic for unshunted (a) and resistively shunted (b) Josephson                                          |
| junction....................................................................................................................4  |
| Figure 1.4 Asingle junction interferometer.....................................................................7               |
| Figure 1.5 AJosephson transmission line (JTL), where single flux quantum is transferred                                        |
| through J1 by entering J1-L2-L3-J2. ........................................................................8                  |
| Figure 1.6 Two Junction Comparator..............................................................................9              |
| Figure 2.1 Distribution of surface currents in superconducting film with a circular virtual                                    |
| (or probe) hole v and a moat. The currents are induced by flux frozen in circular                                              |
| hole .......................................................................................................................22 |
| Figure 2.2 Structure of the counter-flow shift register consisting ofD cells (a) and timing                                    |
| JTL splitters (b). Note that D cells have extra current terminals (Probe) connected                                            |
| with the separate power line with zero nominal bias voltage...................................25                               |
| show                                                                                                                           |
| Figure 2.3 Layout of the test circuit (a) and one of D cells (b). Solid black lines                                            |
| holes (moats) in the lower ground plane.................................................................25                     |
| Figure 2.4 (a) cold head of the Cryo-cooler (b) 3D Helmholtz coil setup.......................26                               |
| Figure 2.5 Spread of upper and lower are bias margins for major components of the test                                         |
| circuit. The stripes show the minimal margins required for further testing of                                                  |
| cells.......................................................................................................27                 |
| individual                                                                                                                     |
| Figure 2.6 The probability of too narrow margins or incorrect operation at different                                           |
| perpendicular magnetic fields.................................................................................28               |
| individual cells. (b) Shows the same data but 'convolved' position of cells in four                                            |
| groups of 4-bit shift registers..................................................................................28            |

| Figure 2.8 Deviations of margins for all 16 cells repeatedly measured at different                                                                                                                                                              |        |        |    |                  |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|----|------------------|
| magnetic fields ......................................................................................................30                                                                                                                        |        |        |    |                  |
| Figure 2.9 Probabilities of deviations of margins as functions of normal magnetic field.                                                                                                                                                        |        |        |    |                  |
| ..............................................................................................................................31                                                                                                                |        |        |    |                  |
| Figure 2.10 Probabilities of deviations of margins as functions of tangential field.........32                                                                                                                                                  |        |        |    |                  |
| Figure 2.11 Probabilities of deviations of D flip-flop threshold currants caused by flux                                                                                                                                                        |        |        |    |                  |
| trapping in tangential (a) and normal (b) magnetic fields. Please note that the                                                                                                                                                                 |        |        |    |                  |
| tangential fields are larger than normal ones. As a result, it would be incorrect to use                                                                                                                                                        |        |        |    |                  |
| this plot to compare sensitivities to tangential and normal fields.............................33                                                                                                                                               |        |        |    |                  |
| Figure 3.1 It is a 6bit counter clock shit register. The chip was fabricated at Hypres with                                                                                                                                                     |        |        |    |                  |
| 1kA/cm2 process. JJ count 996 ..............................................................................39                                                                                                                                  |        |        |    |                  |
| Figure 3.2 Block diagram of the shift register. ..............................................................38                                                                                                                                |        |        |    |                  |
| Figure 3.3 Layouts configurations for different moat patterns. ................................39,40                                                                                                                                            |        |        |    |                  |
| Figure 3.4 Deviation of the threshold current induced by frozen flux as a function of applied magnetic field perpendicular to the chip. Solid vertical lines show threshold magnetic field that separates acceptable and inacceptable values of |        |        |    |                  |
| the the ambient magnetic field. Different plots (see text) correspond to different moat                                                                                                                                                         |        |        |    |                  |
| configurations.. ......................................................................................................41                                                                                                                       |        |        |    |                  |
| Figure 3.5 Bubbles represent the probability of a deviation of threshold current caused by trapped vortices. Small bubbles correspond to the deviations in 1-4 µ A range,                                                                       |        |        |    |                  |
| medium bubbles correspond to 4-20 µ A deviations, large bubbles indicate deviations                                                                                                                                                             |        |        |    |                  |
| that are greater than 20uA. .....................................................................................42                                                                                                                             |        |        |    |                  |
| 3.6 Threshold fields (in mG) for investigated moat patterns. Names corresponding microphotographs in Figure. 3.3 are shown below the                                                                                                            |        |        |    |                  |
| (b) KL1025............................................................................................................47                                                                                                                        |        |        |    |                  |
| 3.7 The threshold current deviation for layout 1e, for mask releases (a)                                                                                                                                                                        |        |        |    |                  |
| Figure 4.1 Asingle junction SQUID as the simplest power independent                                                                                                                                                                             |        |        |    |                  |
| cell.................49                                                                                                                                                                                                                         |        |        |    |                  |
| KL1094                                                                                                                                                                                                                                          |        |        |    |                  |
|                                                                                                                                                                                                                                                 | Figure |        |    |                  |
|                                                                                                                                                                                                                                                 |        | Figure | of | columns.......43 |

| Figure 4.2 Transformation of a conventional RSFQ (a) RS flip-flop into a (b) independent cell . ..............................................................................................50                    | power                                                                                                                              |                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| Figure 4.3 Power Independent D flip-flop. Bias current IPI does 2 things: it 'activates'                                                                                                                            |                                                                                                                                    |                                       |
| SQUID with junction J0 and power the cell during its normal operation.................52                                                                                                                            |                                                                                                                                    |                                       |
| Figure 4.4 Current (upper trace) and voltage waveforms illustrating the                                                                                                                                             | power                                                                                                                              |                                       |
| independent operation of D cell. Note that the 'activation' procedure could larger current IPI than those during the regular circuit operation.                                                                     | ...........................53                                                                                                      | require                               |
| Figure 4.5 The microphotograph of the shift registers of the power independent                                                                                                                                      | cells.                                                                                                                             |                                       |
| The first three registers are designed with power independent cells ........................54                                                                                                                      |                                                                                                                                    |                                       |
| Figure 4.6 Low speed testing of one shift registers. The logic '1'applied to the input                                                                                                                              |                                                                                                                                    |                                       |
| (two                                                                                                                                                                                                                | clock                                                                                                                              | 6                                     |
| lower traces) is read out from the output (the second from top trace) after cycles (middle traces).............................................................................................55                   |                                                                                                                                    |                                       |
| Figure 4.7 Three layout configurations for PI Dflip-flop . ............................................56                                                                                                           |                                                                                                                                    |                                       |
| Figure 4.8 Threshold deviations for corresponding layouts configurations in figure                                                                                                                                  | 4.7.57                                                                                                                             |                                       |
| Figure 4.9 Probability of flux trapping in the each cells for the corresponding layout figure 4.7.. .............................................................................................................58 | in                                                                                                                                 |                                       |
| Figure 5.1 (a) Block diagram of current recycling digital transmission line.(b) microphotograph of the layout digital transmission line..........................................63                                 | The                                                                                                                                |                                       |
| Figure 5.2 Circuit schematic for magnetic coupled SFQ pulse transfer between and receiver. ..........................................................................................................64             | driver                                                                                                                             |                                       |
| Figure 5.3 Layout for magnetic coupled SFQ pulse transfer between driver and                                                                                                                                        |                                                                                                                                    |                                       |
| receiver                                                                                                                                                                                                            | . ..............................................................................................................................65 |                                       |
| Figure 5.4 The complete block diagram of the serial biasing                                                                                                                                                         |                                                                                                                                    |                                       |
| Figure 5.5 The microphotograph of the chip for demonstrating current recycling .                                                                                                                                    |                                                                                                                                    |                                       |
| 5.6 The digital waveform of the input and three outputs as shown in figure                                                                                                                                          |                                                                                                                                    |                                       |
| ..........................................67                                                                                                                                                                        |                                                                                                                                    |                                       |
| The traces 1,3,5 are the outputs and 2 is the input trace                                                                                                                                                           |                                                                                                                                    |                                       |
| Figure                                                                                                                                                                                                              |                                                                                                                                    |                                       |
|                                                                                                                                                                                                                     | 5.4.                                                                                                                               |                                       |
|                                                                                                                                                                                                                     | .........66                                                                                                                        |                                       |
|                                                                                                                                                                                                                     |                                                                                                                                    | method.............................66 |

| Figure 5.7 The (a) schematic of the floating transmission line and its (b) block diagram . ..............................................................................................................................68                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Figure 5.8 The (a) schematic of the N floating transmission lines and its (b) block                                                                                                                                                               |
| diagram..................................................................................................................68                                                                                                                       |
| Figure 5.9 The microphotograph of the summing amplifier based output drivers - designs based on serial and parallel connections- containing both . ........................69                                                                     |
| 5.10 (a) The layout of the parallel connected summing amplifier based on floating                                                                                                                                                                 |
| Figure transmission line. (b) Shows the microphotograph of the summing amplifier .                                                                                                                                                                |
| .......69                                                                                                                                                                                                                                         |
| Figure 5.11 Measurements of the driver shown. Three inputs are operational at bias currents from 1.3 mA to 1.9 mA. One input has lower margins (from 0.85 mA 0.98 mA). Please note that horizontal axis shows only half of total applied current. |
| to bias ..................................................................................................................70                                                                                                                      |
| Figure 5.12 Layout output drivers with (a) 10 floating transmission lines and (b) 20 floating transmission lines connected in series. ......................................................71                                                    |
| Figure 5.13 Measurement of output voltage of the driver shown as a function of bias                                                                                                                                                               |
| current. It is easy to see that at nominal bias (2.0 mA) the load circuit could be from 0 ma to 0.5                                                                                                                                               |
| Figure 5.14 . Measurement of the driver with 20 FTLs. The driver operates at                                                                                                                                                                      |
| mA.....................................................................................................71                                                                                                                                         |
| bias current from 1.5 mAto 2.0 mA..............................................................................72                                                                                                                                 |
| Figure 5.15 The affect of magnetic filed on margins of the operations. (a) x-axis ,(b) y-                                                                                                                                                         |
| axis and (c) z-axis, are the direction of the magnetic field applied to the circuit as shown . ..................................................................................................................73                               |
| 5.16 Margins of the circuit due to the scan of 360 degrees of magnetic filed. orientation of the chip to the axis of the magnetic field is also shown as reference. 74                                                                            |
| The                                                                                                                                                                                                                                               |
| Figure                                                                                                                                                                                                                                            |
| Figure 5.17 The affect of magnetic filed on the output of the driver (10 serially                                                                                                                                                                 |
| the magnetic field applied to the circuit as shown...................................................76                                                                                                                                           |
| 6.1 32-channel module; (A) Block diagram, (B) photo (C) photo of                                                                                                                                                                                  |
| PCB.......................................................................................................................78                                                                                                                      |
| 1-channel                                                                                                                                                                                                                                         |
| Figure                                                                                                                                                                                                                                            |
| connected FTL) operations. (a) x-axis ,(b) y-axis and (c) z-axis, are the direction of                                                                                                                                                            |

C

| Figure 6.2 PI model with all the parasitic components are shown. (b) PI model used for simulation . ............................................................................................................79                                                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Figure 6.3 Scattering parameters S11 and S21 for the pi model in figure 6.2b.. .............79                                                                                                                                                                                                                                                                                                                                                                        |
| Figure 6.4 Structure of a wide-band chip-to-chip connection. Signal bump (in the center) is surrounded by 4 ground bumps. Bumps are deposited into the centers of Nb contact pads. Superconducting microstrip line (MSL) is connected to the signal bump. It has a specially shaped end overlapping a cut in the ground plane in order to provide impedance matching and increase the transmission bandwidth. .................81                                     |
| Figure 6.5 Block diagram of the ring oscillator used for testing SFQ pulse transmission                                                                                                                                                                                                                                                                                                                                                                               |
| Figure 6.6 (a) Microphotograph of the lithographically defined bumps.(b) The complete chip-set of the multi-chip module...........................................................................84                                                                                                                                                                                                                                                                  |
| Figure 6.7 The frequency of transmission of SFQ pulses between the flip-chip and the MCM carrier in the ring oscillator at various numbers of flux quanta circulating in the ring for the typical MCM. The maximum of 16 SFQ pulses can be inserted into the ring oscillator. The speed of circulation of the pulses was controlled by varying the bias on the JTL.................................................................................................86 |
| Figure 6.8 The upper and lower margins of the receiver bias current at different rates of SFQ pulse transmission between the flip-chip and the MCM carrier with Au bumps. The MSL length is 2210 µm. The wafer was bumped using 1.8 µ m Au deposited by e-beam evaporation. The MCM was bonded by a compatible                                                                                                                                                        |
| Figure 6.9 The upper and lower margins of the receiver bias current vs the SFQ transmission rate between the flip-chip and the MCM carrier for InSn bumps. the chip and the carrier were bumped by immersion in molten InSn alloy at 150 o and bonded by reflow and a cryogenically compatible adhesive. The MSL length 2210                                                                                                                                          |
| Figure 6.10 The upper and lower margins of the receiver bias current vs the SFQ transmission rate between the flip-chip and the MCM carrier for InSn bumps. separate branch from left to right corresponds to the different number of SFQ circulating in the ring oscillator. Ageometric resonance in the MSL at ~ 44 GHz be seen. InSn bumps were used in this MCM.........................................................88                                        |
| cryogenically adhesive...............................................................................................87 pulse Both                                                                                                                                                                                                                                                                                                                                    |
| bumps                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| C                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| is                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| µm.................................................................................................................87                                                                                                                                                                                                                                                                                                                                                 |
| pulse pulses                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Each                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| can                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

| Figure 7.1 Asimulink Matlab model for behaviroal-level system simulation................91                                                                                                                                                                                                                                                                                                                                                                |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Figure 7.2 Spectrum for 1,2,4,8 modulators PMD ADC................................................92                                                                                                                                                                                                                                                                                                                                                      |
| Figure 7.3 SNR(dB) versus Signal Power (dBFs) of 1,2,4,8 modulatorsPMD ADC. ....93                                                                                                                                                                                                                                                                                                                                                                        |
| Figure 7.4 The Layout of the transformer coil. The Number of turns N=12, with primary inductance Lpri=27nH and secondary inductance Lsec=19nH. The inner radius, Ri= , Outer radius, Ro=, Width, W= . (b) the 3D view of the simulated transformer( cell size 2.5x2.5 um , air =250um, si_substrate= 250um, separation from ground ring and outer coil radius 75um )...................................................................................95 |
| Figure 7.5 The schematic developed for the transformer based on the values extracted by simulation. .............................................................................................................96                                                                                                                                                                                                                                       |
| Figure 7.6 Schematic of the 5 th order Butterworth Low pass filter, R1=R2=50 ohm, C1=C2=5.15pF, L1=L3=4.92nH, L2=15.9nH . ......................................................96                                                                                                                                                                                                                                                                        |
| Figure 7.7 Amplitude and phase charaternistics of a normalize 5 th order Butterworth filter ......................................................................................................................97                                                                                                                                                                                                                                      |
| Figure 7.8 The bilayer spiral is shown above, with N=12 turns. The spiral inductor is constructed with N=6, in M2 and M3 layers. The 3D view of the bilayer spiral is shown above, with N=12 turns. The spiral inductor is constructed with N=6, in M2 and M3 layers.(cell size 2.5x2.5 µ m, air =250 µ m, si_substrate= 250 µ m, separation from ground ring and outer coil radius 75 µ m).………………………………………………………………………….. 98                             |
| Figure 7.9 The Complete Layout of the 5 th order Butterworth Low Pass filter is shown. The two capacitor are constructed between M2 and the ground layer M0.. .............98                                                                                                                                                                                                                                                                             |
| Figure 7.10 The schematic of the 4 multi-modulator PSCAN simulation ......................99                                                                                                                                                                                                                                                                                                                                                              |
| Figure 7.12 The correct operation of the front end of the multi-modulator ADC,                                                                                                                                                                                                                                                                                                                                                                            |
| the diffential output pulses . .......................................................................................101                                                                                                                                                                                                                                                                                                                                 |
| Figure 7.13 The complete layout constructed for the 2-modulator design . ..................101                                                                                                                                                                                                                                                                                                                                                            |
| Figure A1.1 RSFQ Splitter .......................................................................................114                                                                                                                                                                                                                                                                                                                                      |
| Figure A1.2 RSFQ Confluence buffer . .....................................................................115                                                                                                                                                                                                                                                                                                                                             |

| Figure A1.3 RSFQ D Flip-flop                          |                                            | .................................................................................115   |
|-------------------------------------------------------|--------------------------------------------|----------------------------------------------------------------------------------------|
| Figure A1.4 RSFQ SMSL driver                          |                                            | . ............................................................................116      |
| Figure A1.5 RSFQ SMSL receiver                        |                                            | ..........................................................................117          |
| Figure A1.6 (a) DC/SFQ converter (b) SFQ/DC converter | . .....................................118 |                                                                                        |

## LIST OF TABLES

| Table 6.1 Maximum transfer rate achieved for MSL lengths with Au bumps Wafer                                               |
|----------------------------------------------------------------------------------------------------------------------------|
| KL1084,.................................................................................................................88 |
| Table 6.2 Maximum transfer rate achieved for MSL lengths with InSn bumps Wafer                                             |
| KL1057,.................................................................................................................88 |
| Table 7.1 Inductances of spiral inductor for LC lowpass filter , ...............................97                         |

## ACKNOWLEDGEMENTS

Life  during  my  graduate  studies  at  Stony  Brook would  not  have  been  fulfilling without the guidance, support, encouragement, friendship and  love of  many wonderful people. I would like to take this opportunity to express my gratitude to most of them.

First of all, I would like to thank Professor Vasili Semenov for providing a very stimulating  scientific  environment;  introducing  me  to  the  challenging  problems  and constantly showing  new  opportunities and sharing his vision of superconducting electronics, physics and technology. This dissertation would not be possible without his help and support.

I would like to thank Dr. Yuri Polyakov for teaching me all aspects of cryogenic measurements and sharing with me untold secrets of the trade of experimental procedures in physics.

Special thanks to Prof. Alex Doboli for his help and advice during the course of my studies at Stony Brook. His support has been indispensable.

I would also like to thank Prof. Harbans Dhadwal, Prof. Murali Subba Rao, Prof. Petar Djuric and Prof. John Murray for their help during my various stages of graduate studies.

I thank Prof. D. Donetski, Prof. R. Kamoua and Prof. D. V. Averin for serving as members of my defense committee.

Many people in the RSFQ Lab have provided with assistance and support during the  stay  and  I  share  great  memories  with  them.  Thanks  to  all  members  of  this  lab  for assistance at various  stages:  Amol Inamdar, Anubhav Sahu, Alan Rodricks, Jie Yu, Jie Ren, Girish, and Nathan Broggrern.

I  have  made  friends  for  life  at  the  university  in  Prashant,  Samrat,  Abhinay, Gajendra,  Abin,  Clarence,  Nilotpal,  Ravish,  Gaurav,  Ashwin,  Balani,  Kuashal,  Tobi, Gopal,  Ashish,  Vikas,  Girish  and  Prasanna,  with  whom  I  share  great  memories.  Their support, encouragement and friendship have been crucial. I  would  also  like  to  thank  Prof.  Sergey  Tolpygo,  Dr  Oleg  Mukhanov  and  Dr Deep Gupta at Hypres Inc. for fruitful discussions and Hypres Inc. fabrication team for fabricating the circuits. I  would  also  like  to  thank  Dr  Deborah  Van  Vechten  for  her  support  from  the Office of Naval research. Finally,  I  want  to  thank  my  parents  and  my  brother.  Without  their  support  and understanding, I would not be here now.

## Chapter 1 Introduction

## 1.1 Superconductivity

When  a  material  loses  all  its  resistance  then  the  material  is  said  to  become superconducting. The temperature when  materials  lose their resistance  is called critical temperature, TC. Superconductivity was discovered by Kamerlingh Onnes in 1911 after cooling mercury (Hg), with liquid Helium (He). The field of superconductivity has now developed  over  the  years.  With  the  discovery  of  high  temperature  superconductivity nearly 20 years ago has given a new life into this field.

The  origin  of  superconductivity  is  that  below  the  critical  temperature  electrons condense into Cooper pairs, which are two electrons with opposite spins. When electrons form Cooper pairs, they no longer follow fermion statistics, because the total spin is equal to zero. Instead all the  Cooper pairs condense into the same state (the superconducting condensate); thereby they can move without resistance in the superconductor. In figure 1.1(b) shows the typical distribution of electrons and Cooper pair's versus temperature. At critical temperature Cooper pairs are formed and their density grows with decreasing temperature and saturates below Tc [1, 2].

Some of the main reasons as to why the area of superconducting is attractive to electronics are very low resistance, very high frequency operation and Josephson effect. In most of the electronics application Niobium is used as the superconducting material. Its critical temperature is around 9.2k.

Figure  1.1:  Temperature  dependence  of  (a)  resistance  (b)  electrons  and  Cooper  pairs  density  in superconducting material

<!-- image -->

## 1.2 Josephson junction (JJ)

In  superconducting  electronics  the  active  component  is  the  Josephson  junction (JJ).  The  Josephson  effect occurs  in  a  weak  link  contact  between  two  superconducting electrodes.  The  main  phenomena  taking  place  in  a  JJ  is  the  static  and  the  dynamic Josephson effects.

The static  Josephson (DC) effect [1,2,3,4], is the tunneling of current through a weak link without any applied voltage. The maximum possible current is limited by the critical  current,  I C.  Below  IC  the  current  consists  only  of  the  super  current,  IS.  IS  is  a function  of  the  phase  difference Φ = χ 1 -χ 2  of  the  superconducting  condensate  wave function  between  the  two  electrodes  of  the  JJ.  In  the  simplest  case,  this  relation  is sinusoidal

<!-- formula-not-decoded -->

The AC or dynamic Josephson effect [1,2,3,4], takes place when the current that flows through the Josephson junction is higher than the critical value, I &gt; IC. In case an average voltage, V exists across the junction, which gives continuous oscillations of the phase Φ with the angular frequency ω .

Figure 1.2: RSJ model for Josephson junction.

<!-- image -->

The dynamics of the Josephson junction can be explained in terms of Resistive Shunted Junction (RSJ) model as shown in figure 1.3. IS is the super current through the junction, Id is the displacement current through the capacitor, IR is the resistive current through the insulating barrier and IF is the fluctuation current.

<!-- formula-not-decoded -->

The Josephson inductance of the junction can be defined as

<!-- formula-not-decoded -->

With the help of the model one can define the characteristic frequencies of the system: Inverse relaxation time

<!-- formula-not-decoded -->

and plasma frequency

<!-- formula-not-decoded -->

The dynamics of the Josephson junction depends on the ratio between relaxation time and plasma  frequency  as  know  as  a  dimensionless  parameter  called  Stewart-McCumber parameter:

<!-- formula-not-decoded -->

The parameters of the Josephson junctions can be quite different depending on materials used and the way how Josephson junction has been formed. The most common type is the Superconductor/Insulator/Superconductor  (SIS)  Nb/AlOx/Nb  tunnel  junctions.  These junctions typically have 1 &gt;&gt; C β and I-V curve consists of two branches: superconducting branch with zero voltage and resistive branch with highly non-linear resistance. When the current  exceeds  the  critical  current,  junction  jumps  into the  resistive  state  with  voltage equal to the gap voltage of the electrodes,

. 2.6 2 mV V ∆ ≈ = At higher currents the voltage scale is given by the so called characteristic  voltage, N C R I ,  for  tunnel  junctions  which  is  about e R I N C 2 ≈π∆ .  Due  to the high capacitance of the barrier the I-V curve of the SIS junctions is highly hysteretic.

Figure 1.3: I-V characteristic for unshunted (a) and resistively shunted (b) Josephson junction.

<!-- image -->

Associated with capacitance plasma oscillations of the tunnel junction can be damped by the small shunting resistance, RSHUNT, as it shown on figure 1.2. In the over- damped case with, N SHUNT R R &gt;&gt; ,  the  total  resistance  R  in  the  RSJ  model  can  be  approximated  by RSHUNT and equation for RSJ model can be written as

<!-- formula-not-decoded -->

Introduction of the shunt resistor gives reduction of the β c and correspondingly reduction of the hysteresis on the I-V curves as it shown on figure 1.3(b). In the highly over damped case with β c &lt; 1 relaxation time τ N = RC is less than period of the plasma oscillations and switching of the junction into the resistive state gives periodic tray of the Single Flux Quantum (SFQ) voltage pulses with the area

<!-- formula-not-decoded -->

and the dissipated energy is

<!-- formula-not-decoded -->

For  fixed β c,  the  characteristic  voltage  ICR  and  switching  time τ C  of  the  over  damped junctions depends on a critical current density JC available at the fabrication process:

According to [8,9,18], the data encoding for the SFQ logic is stated as 'arrival of SFQ pulse  at  a  terminal  of  an  elementary  cell  during  the  current  clock  period  indicates  the binary value 1, while the absence of the voltage pulse is 0. '

The above property can also be used to relate the phase drop across the junction. If  the  total  flux  in  the  superconducting  loop  is Φ ,  and  the  loop  is  interrupted  by  a Josephson  junction  (as  in  a  single  junction  interferometer,  figure  1.4)  then  the  phase difference φ across the junction is given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

For the typical range of the critical current densities in the currently available processes between 30A/cm2 and 20KA/cm2 the switching time is in the range from 10 to 0.05ps and energy dissipated per one single switching event is in the range from 10 -20 to 10 -17 J.

## 1.3 Flux quantization

Magnetic flux quantization forms the basis of data encoding in RSFQ technology [8,9,18]. Given area A, flux of the magnetic field B is an integral multiple of magnetic flux quantum Φ 0 .

<!-- formula-not-decoded -->

## 1.4 Generation of Flux Quanta

SFQ  pulses  can  be  generated  a  single  junction  interferometer  [8,9].  It  can  be described  as  a  superconducting  closed  loop  with  two  leads  and  interrupted  by  a Josephson junction. The total flux Φ generated by the total current (internal and external)

Figure1.4: A single junction interferometer.

<!-- image -->

<!-- formula-not-decoded -->

We can see that the total flux can be fixed by applying an external current to introduce a phase difference. At a higher value of the external current the voltage pulse is produced (in  accordance  with  Faraday's  law,  rate  of  change  of  flux  result  in  the  generation  of voltage).  The  shape  of  the  voltage  pulse  is  very  close  to  that  of  a  Gaussian.  But  the voltage pulse must satisfy the constraints of eq. 1.9.                                                    In other words the change of flux through the interferometer is exactly one magnetic flux quantum.

## 1.5 RSFQ Circuits

The  Meisner  effect  [1,2,3,4,6]  and  Josephson  effect  form  the  basis  for  of superconducting digital electronics. These effects allow storing information in the form of one single flux quanta and transferring them at high speeds via switching of Josephson junctions in the networks.

Rapid  single  flux  quantum  technology  (RSFQ)  was  introduced  in  1985  [8,9] suggesting  a  new  approach  to  the  existing  Josephson  junction  digital  computing.  In

RSFQ  the  binary  state  is  not  presented  by  the  DC  voltage  state  of  the  gates  but  by magnetic  flux  quanta  expressed  in  very  short  voltage  pulses.  Emanating  from  the properties of the overdamped Josephson junction, the following section introduces to the principles of the technology and basic circuit elements of RSFQ circuits.

## 1.5.1 Principle Components of RSFQ circuits

In figure 1.5, the basic idea of RSFQ is presented: to pass the information about the flux state from one loop to another using the dynamics of the flux transients [7,8,9]. A 2 π jump  in  Josephson  phase Φ across  the  junction  corresponds  to  one  flux  quantum passing through the junction.

Figure1.5: A Josephson transmission line (JTL), where single flux quantum is transferred through J1 by entering J1-L2-L3-J2.

<!-- image -->

Figure  1.5  has  many  essential  elements  of  a  typical  RSFQ  circuit;  overdamped Josephson junctions J1 and J2 break the superconducting loop formed by inductances L2, L3  and  the  ground  plane.  Both  junctions  are  biased  by  current  source  IB  so  that  the current  flowing  through  each  junction  is  close  but  smaller  than  the  critical  value  Ic.  A flux quantum arriving from the input 'in' (from the left) of the circuit drives the current

through the junction J1 above the critical value and for a short time, of the order 5ps, a voltage pulse is formed across the junction J1.

After  the  junction  J1  returns  to  the  superconducting  state,  the  flux  quantum  is trapped inside the loop J1-L2-L3-J2 ground plane loop. What happens next is determined by the parameters of the circuits. If the inductance of the loop L2+L3 is large enough, so that the induced change in current ∆ I through the junction J2 ( ∆ I~ Φ /L1) is not sufficient to exceed its critical value, the state with a trapped flux is stable and the loop stores the information. If the inductance of the loop is smaller, so that current through the junction J2 exceeds its critical value, the junction flips, making a 2 π turn in phase Φ and the flux quantum leaves the loop through J2 in the same manner as it entered it through J1.

Figure1.6: Two Junction Comparator

<!-- image -->

The other basic  idea of RSFQ  is using a two junction comparator, as shown  in figure  1.6,  controlled  by  a  quantizing  inductance  L1.  The  parameters  of  the  circuit  are chosen so that when an SFQ voltage pulse arrives at the two terminals input and 'T', the flux stored in the loop to the left of the junction J2 is released and appears on the output. When there is no stored flux, the current through J2 is smaller and further from its critical

value so with the arrival of the two read terminal of the pulse junction J3 flips and there is no output. Two junction comparators are the basis of every RSFQ design.

## 1.6 Large Scale Integration of Superconducting Circuits

Superconducting SFQ electronics is a unique technology, that delivers the fastest digital  circuits  with  extremely  low  energy  dissipation  [7,  10,  60].  But  it  is  still  an emerging technology and as a result it is very easy to compile a list of technical problems that remain to be solved.

Flux  trapping,  power  dissipation,  heat  dissipation,  integration  of  MCM  and returning  path  of  ground  currents  [71]  are  some  of  the  crucial  problems in the technological  development  aspects  that  must  be  overcome  to  increase  the  prospects  of large  scale  integration  of  RSFQ  circuits.  Today,  circuits  of  over  20,000  Josephson junctions  have  been  reported  [11,63,70,  80]  and  circuits  of  5000  Josephson  junctions have been tested at high speeds up to 80GHz [61,68,86,87].

In this thesis, integrated test circuits have been fabricated and tested that contain nearly  2000  Josephson  junctions.  The  goal  is  to  use  test  results  from  these  circuits investigated to resolve the difficulties that arises in the design of large SFQ circuits. The area  of  development  of  smaller  cryogenic  coolers  is  also  necessary  to  make  RSFQ technology more easily accessible, but this area is beyond scope of discussion here.

## 1.6.1 Motivation

In  this  thesis,  we  would  like  to  address  some  of  the  most  important  aspects  of RSFQ circuit technology for large scale integration.

## 1.6.1.1 Flux trapping

Josephson junction circuits are highly sensitive to magnetic fields. This sensitivity derives from the small size of the magnetic flux quantum; one flux quantum is equivalent to 2 x 10 -7 gauss  in  a  1-cm 2 area.  (The  magnetic  field  of  the  earth  is  ~  0.4 gauss.)  JJ  circuits  are  shielded  from  local  magnetic  fields,  such  as  the  earth's  field,  by high permeability shields. The field inside 'good' shields can be as low as a few milligauss. Flux trapping occurs at unpredictable locations in superconducting films as they are cooled through their superconducting transition temperature, Tc. The flux is trapped in  the  films,  in  the  form  of  Abrikosov  vortices  [1,6],  where  superconductivity  in  that region is  lost and  has  magnetic  field  lines penetrating the  film.  Flux trapped  in ground planes  can  significantly  affect  working  of  a  SFQ  circuits,  from  reducing  the  operating margins to completely rendering the circuit inoperable. One method for alleviating this effect is to intentionally trap the flux in holes (called moats) placed in the ground plane, such that circuit operation is not affected. There is no standard system for designing and locating moats.

## 1.6.1.2. Low power RSFQ circuit- Power independent RSFQ cell

Even though the power dissipation in RSFQ circuits is low, it is relatively high for the  temperature  of  4.2K.  The  prospects  of  RSFQ  circuits  have  now  expanded  largely from digital logic to realization of fast superconducting digital computers [13,53,54,61,67].  The  wide  range  of  circuits  makes  it  the  reason  for  different  power requirements for the systems. A good system designed for any application is desired to have minimum or no static power dissipation, which are high in RSFQ circuits.

## 1.6.1.3. Current Biasing of RSFQ circuits:

Chips with a large number of junctions require large bias currents. Even assuming all JJs are at minimum IC of 100 µA, a 10 6 -JJ chip will require 100A. Efficient methods of supplying bias current to the circuit components on-chip have to be demonstrated for large scale circuits. A method to bias large circuit blocks in series (referred to as current recycling  or  current  re-use)  will  be  essential  for  large  junction-count  chips  in  order  to reduce the total current supplied to the chip to a manageable value. Both capacitive and inductive methods of current recycling have been demonstrated at a small scale (fewer than 100 junctions) [56,57,58]. Current recycling can reduce the heat load in the power lines into the cryostat, but does not eliminate the on-chip static power dissipation.

## 1.6.1.4 Multi-chip modules:

To  develop  large  scale  RSFQ  circuits,  one  of  the  convenient  methods  is  using flip-chip technology [55,59,86,87,89]. Flip chip technology [85] has been used for many years in semiconductor technology, but in superconducting electronics they have enjoyed lower  success.  One  of  the  fundamental  limitations  is  the  low  quality  (high  parasitic inductance  and  capacitance)  of  the  high  frequency  bumps  of  the  flip  chip.  The  high parasitics of the bumps lower the limit of the transmission rate between the two bonded superconducting chips. The transfer rate between the bonded superconducting chips must be able comparable to the operating speed of on-chip components which above 100GHz.

## 1.6.1.5 Multi-modulator ADC design

Superconducting Modulators have  been demonstrated for high quality [11]. But one of the limitations has been due to the noisy nature of the front end of the ADC [14]. To overcome  the  limitation  and  improve  the  SNR  and  dynamic  range,  the  number  of

modulators can be increased and also the design of the pickup coil transformer should be improved. A possible incorporation of a low pass filter will improve the operation.

## 1.7 Contributions

## 1.7.1 Flux Trapping

- -An  empirical  model  has  been  presented  for  analyzing  parasitic flux  trapping in superconducting circuits.
- -A quantitative analysis of the effect parasitic  flux  trapping  on  the  operation  of  RSFQ circuits has been studied using shift registers. The method was also used in determining: fabrication spread, probability of flux trapping in circuits, effect of flux trapping on bias of  the  circuit,  and  locating  defective  cells  in  RSFQ  circuits  (which  can  limit  the operating margin of the entire circuit)[44].
- -A complete experimental setup and methodology, with 3D magnetic field control, has been  developed  for  investigating  parasitic  flux  trapping  in  cryo-coolers  and  Helium Dewars. The setup can be used to study flux trapping in other superconducting digital circuits [44].
- -A new set of moat protocols were also studied for parasitic flux trapping to determine the  layout  configuration  which  are  most  resistant  to  parasitic  flux  trapping.  The  most resistant moat configuration has been able to prevent flux trapping upto 20mG, which is comparable to Earth's magnetic field [45].
- -Flux trapping studies  have also  been  carried  out  on  the  power  independent  circuits,  a logic family for power independence [48].

## 1.7.2 Low Power RSFQ circuits

-A  new concept of  low power superconducting circuits, power independent RSFQ cell was developed. The power independent logic circuits are able to retain logic state of the circuit, when the bias power is switched off. So, the power independent circuits can be biased only when the circuits  are needed  for operation and switched off the remaining period of time, eliminating static power dissipation. The logic was incorporated into shift register  design,  fabricated  and  experimentally  tested  with  ±20%  margins.  The  concept was  demonstrated  using  a  6bit  counter  shift  register  in  both  1kA/cm2  and  4.5kA/cm2 [49].

## 1.7.3 Current Cycling in RSFQ Circuits

-Current recycling has been implemented and tested to reduce current bias to the circuit. The principle of the method is to reuse current from one part of the circuit to bias another part;  it  is  possible  to the  lossless  nature of the superconducting devices. The technique was successfully demonstrated for a digital transmission line with over 1000 junctions on the chip.

-The  technique  of  current  recycling  was  also  used  to  develop  high  frequency  output drivers for SFQ circuits I/O interfaces.

-The impact of magnetic field on the operating margins was also studied on the current recycling  circuits.  The  methodology  of  experiments  we  were  also  able  to  study  the physical structure of the fabricated circuits.

## 1.7.4 Multi-Chip Modules

-We were able to successfully demonstrate the digital data transfer at over 110 GHz by using  a  newly  designed  bump  structure  for  connecting  the  two  superconducting  chips. The bump structure has parasitic reduced, thereby increasing the resonant frequency to

75GHz [47].

## 1.7.5 Multi-Modulator ADC Design

- -A  design  of  the  architecture  for  Multi-modulator  with  low  noise  and  high  sensitivity front end has been presented.
- -New dipole transformer has been developed for low noise and high tolerance to external magnetic fields.

## 1.8 Limitations

## 1.8.1 Flux Trapping

- -The fundamental limitation of the method used for quantifying the effect of flux trapping effects on the circuits is that our circuit has to operate correctly. The exact location of the flux  frozen cannot be determined by our method. Also the probability of flux trapping, determined for each cell, will depend on the number of measurements carried out as the results are quantitative in nature.

## 1.8.2  Low Power RSFQ circuit- Power independent RSFQ cell

- -The  power  independent  circuits  have  to  be  turned  on  every  time  when  we  wish  to execute the circuits to perform a function. The circuits also have large inductances and hence occupy larger area of than the corresponding conventional RSFQ cells.

## 1.8.3  Current Recycling in RSFQ Circuits

- -The  circuits  are  implemented  on  floating  grounds  and  susceptible  to  larger  transients, and so must have filters to lower these transients in serial biasing circuits. Even though they  lower total current applied to the chip, the on chip dissipation  is  not reduced. The area of the current recycling circuits is also larger due to the additional circuits used to implement this technique, a driver and receiver must be attached to each block biased by

current recycling.

- -The  circuits  using  inductive  biasing  are  more  sensitive  to  magnetic  field  than  the conventional  biasing  due  to  the  use  of  larger  number  of  transformers  involved.  The transformers can couple with reminiscent magnetic fields can affect the operation.
- -If capacitive coupling is used in the technique, the area occupied by capacitors is going to very high compared to the area otherwise occupied.

## 1.8.4  Multi-Chip Modules

-The multichip modules bumps have higher resonating frequency but it is still within the operating  range  of  the  frequency  and  reduces  the  operating  margins  of  circuits.  Better bonding techniques will improve yield of the multi-chip modules.

## 1.8.5  Multi-Modulator ADC

-The  task  of  synchronization  is  greatly  increased  and  additional  circuitry  has  to  be developed for this purpose. Also, impact of jitter in the ADCs have not been addressed which are widely responsible for lower dynamic range and SNR.

## Chapter 2 Flux trapping in Superconducting Circuits: theory and experiments 2.1 Introduction

Magnetic  flux  gets  trapped  during  cooling  below  transition  temperature,  Tc,  in superconducting films and causes serious problems for superconducting devices such as operation  errors  [19,44,45].  The  problem  of  flux  trapping  is  uniquely  existent  only  in superconducting  circuits.  However,  since  flux  trapping  is  unique  to  superconductor electronics and its solution cannot be acquired from another branch of microelectronics. The  closest  analogy  to  this  problem  in  conventional  semiconductor  technology  is  the sensitivity of circuits to elementary particles that affect the circuits during their operation

## 2.2 Theoretical Facts

Discussions of flux trapping are almost as old as Josephson junction technologies. For example, good observations of flux trapping in narrow films and wide ground planes were originally reported in 1982 [20] (see also discussion  in [32]).Holes  in the ground plane  of  the  superconducting  circuits  known  as  Moats,  reduces  the  impact  of  flux trapping of Josephson  junction circuits were suggested and experimentally  investigated [21].

The  physics  of  flux  trapping  after  [20]  is  as  follows:  'As  the  film  temperature T approaches TC , small areas of superconductivity began to appear. As T decrease further, these areas grow larger, and new ones appear, and the superconducting areas begin to join up. … As the superconducting areas join up, however, some normal areas will become surrounded  entirely.  As  this  occurs  the  flux  within  the  normal  area  will  adjust  to  the nearest  integer  number  of  quanta.  Thus  only  if  there  is  more  than  1/2 Φ 0  threading  the

normal region will a vortex be trapped in this region.'

The physics of moats in wide superconducting films is explained in [21,22,35,36, 45,72].  The  effect  of  moat  pattern  on  flux  trapping  is  presented  in  chapter  3.  In  this chapter  a  review  of  the  general  properties  of  a  vortex  in  a  superconducting  film  is presented that will help in determining the effect of vortices on superconducting circuits. Force F , applied to a vortex can be presented as the gradient of vortex energy E :

<!-- formula-not-decoded -->

The energy E, in turn can be split into terms E k and E m with very different properties. Term E k,  describes  the  energy  concentrated  within  the  film  in  the  tiny  vortex  kernel bordered  by  the  larger  of  2  characteristic  lengths ξ (coherence  length)  and λ (London penetration  depth)  [1,2,6].  Each  of  them  depends  on  factors  such  as  temperature,  film substance, deposition processes and internal stress in the film. It is important to note that a  short  range  pinning  forces  is  defined  by  local  variations  of ξ and λ as  well  as  film thickness, d .

Term E m, describes the energy of magnetic field H, outside the vortex kernel. This energy  term  is  responsible  for  the  long  range  interactions  of  the  vortex  with  other vortices, edges of the film and external magnetic field. Energy E m,  (in contrast to E k ) is universal and can be accurately calculated for different film geometries. For example, in endless films, field H, is  spherically  symmetric and attenuates inversely proportional to the squared distance from the kernel r :

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

E m is as

and H B 0 =µµ .All  magnetic  vortex  interactions  can  be  reduced  to  the  calculation  of Lorentz  force  between  the  vortex  holding  magnetic  flux, 0 Φ and  surface  current  with linear density of, J H flowing in the vicinity of the vortex kernel (see [25,26]):

<!-- formula-not-decoded -->

In thick films ( t &gt;&gt; λ ), it is more convenient to analyze two independent currents j Hi (i=1, 2)  flowing  along  the  upper  and  lower  film  surfaces.  The  values  of  these  currents  are numerically equal (but orthogonal) to corresponding magnetic fields H i :

<!-- formula-not-decoded -->

Using the equations from above, the interaction of two vortices located at distance d from each other directly follows from (2.2), (2.4) and (2.5):

<!-- formula-not-decoded -->

Where negative and positive signs correspond accordingly to co-and counter orientations of the fields in the vortices.

To calculate the interaction of the vortex with the perpendicular magnetic field, it is enough to find the distribution of surface currents induced by this field and to use this distribution  in  eq.  2.4.  Finally,  the  interaction  of  a  vortex  with  the  straight  edge of  the film can be explained in terms of the vortex interaction with its mirrored image. We can verify that the distribution of surface currents induced by one vortex located at distance, d, from the straight edge of the film coincides with those caused by two counter oriented vortices  remote  from  each  other  at  distance, d 2 .  Identical  current  (and  therefore  fields) distributions definitely lead to equal attraction forces (2.6) for both geometries.

The  presented  theory  allows,  for  example,  the  calculation  of  the  perpendicular magnetic field, B C, critical for the entrance of vortices into a superconducting strip with

width, w .  Experimental results support the relationship ( 2 ~ 1/ w Bc ),  as  reported in [23]. Later  references  to  a  similar  formula  containing  an  accurate  numerical  factor  can  be found in [4,24,39]:

<!-- formula-not-decoded -->

This universal formula takes into account only the external (or magnetic) vortex energy E m, but it gives a very reasonable match for the known experiments with Nb, PbIn and PbAu films [23].

## 2.3 Numerical Simulations of Magnetic Force on Vortices

According to eq. (2.7) a large ground plane  film with w ~  5  mm  would  give  a low-critical field. In other words, a low magnetic field initiates the entrance of numerous vortices.  However,  each  vortex  that  enters  the  film  decreases  the  external  field  and  in equilibrium the entered  vortices completely  compensate  for the external  field. In other words,  for  wide  films  the  effect  of  the  external  field  can  be  reduced  to  the  collective multi-vortex interactions. As mentioned above, it is well known that the undesirable drift of  vortices  along  the  film  can  be  prevented  by  moats  that  'catch'  those  vortices, converting them into magnetic flux permanently frozen in the hole.

For single layer structures, the effect of long moats can be estimated with ease. The vortex located near a moat 'sees' its boundary as the straight edge of the film. As we mentioned above, the vortex is attracted to this edge according to (2.6) with effective d that  is  twice  as  long  as  the  real  distance  to the  edge.  If  this  force  exceeds  the  pinning force then the vortex falls into the moat; the banks of the moat are vortex free.

The borders of guarded areas can be described as lines where the attraction force between a virtual vortex and the moat equals the pinning force. If the film is uniform for

pinning forces then the borders of the guarded areas coincide with the corresponding line of equal attraction forces. These lines can be numerically calculated using the 3D-MLSI package [27,28] developed for calculation of self and mutual inductances of superconducting film structures. This is possible due to the duality between the magnetic energy and inductance of a hole L with a frozen vortex:

<!-- formula-not-decoded -->

eq. (2.8) implicitly connects the force (2.1) with a dependence of the inductance on its position in the film. For example, the circular hole centered at point x moves toward the film edge with coordinate x =0. According to (2.1) and (2.6) we can find that

<!-- formula-not-decoded -->

The  first  term  here  is  the  integration  constant  selected  to  satisfy  Ketchen's  formula D L 0 =µ for the  inductance of  a circular hole with diameter, D [29].  Now generalized formula for hole with center distance d &gt;&gt; D /2 from the film edge:

<!-- formula-not-decoded -->

Note that the  force  is  proportional  according  to  first  derivatives  of  eq.  (2.9)  and  eq. (2.10) does not depend on hole diameter, D .  As a result, the parameter is relatively free and can be chosen to optimize the accuracy of numerical simulations.

Typical simulation results using the 3D-MLSI package are shown in figure 2.1. The figure shows a distribution of the surface currents in the film with the hole imitating a virtual vortex and the real moat.

Inductance calculations for numerous positions of the virtual vortex and mapped the attraction forces were calculated to find the gradients of reversed inductances of the

hole. These results were further used for the moat design in chapter 3.

Figure 2.1 Distribution of surface currents in superconducting film with a circular virtual (or probe) hole v and a moat. The currents are induced by flux frozen in circular hole

<!-- image -->

## 2.4 How Trapped Flux Affects Circuits

The  frozen flux can affect the superconducting circuits by two  different mechanisms:  It  can  either  directly  penetrates  into  Josephson  junctions  or  it  can  be coupled with the magneto-sensitive gates.

Josephson  junctions  are  relatively  small  and  therefore  their  properties  will  be affected only if the vortices are frozen in junction electrodes [31]. This effect is minimal if vortices penetrated both electrodes and are well aligned. In this case, the effective area of the Josephson junction is reduced only on ~ ξ 2 . The area becomes much larger (~ a 2 ) if the vortices in the upper and counter electrodes are mutually misaligned at a distance, a . The effect will be catastrophic if the vortex is frozen only in one electrode. In this case, the magnetic field of the vortex covers a significant fraction of the junction area causing the critical currents of the Josephson junctions to be dramatically affected by the frozen vortices.  The  probability  of  such  an  event  is  very  low  as  indicated  by  eq.  (2.7).  This

equation shows that small junction electrodes have high critical fields. The probability of the damaging effect increases if the base electrode is much larger than the junction area, or if the base electrode is strongly coupled to the practically endless ground plane.

The  magnetic  coupling  of  the  frozen  vortices  with  RSFQ  devices  or  any  other magnetically sensitive gates is much more common than the first mechanism discussed above. This is because even flux trapped in the moats would also be coupled with gate components; i.e., it is difficult to completely eliminate coupling circuits with frozen flux. It is more realistic to try to reduce this coupling. 3D-MLSI package [27,28] has been used to estimate the coupling vortex and RSFQ circuit components, which is about 0.2 Φ 0 .

## 2.5 RSFQ Circuits for Flux Trapping Experiments

Shift  register  developed  in  [32]  has  been  used  to  study  flux  trapping  in  RSFQ circuits. The important feature of D cells is an additional bias terminal probe connected with a separate power line (figure. 2.2). A nominal bias voltage applied to the line is zero which  does  not  affect  the  circuit  operation.  However,  a  voltage  was  applied  and  the margins were measured for normal circuit operation.

## 2.5.1 Measurement Process:

The measurement procedure is as follows: First that the whole circuit is checked if  it  is  completely operational  for at least one set of bias voltages. This set of  bias was used to write into the register a digital code containing many logic '0's and logic '1' that selects the investigated cell. The selection takes place due to a large circulating current (figure  2a)  in  the  storage  loop.  This  current  affects  the  margin  of  the  cell  for  probe current. At the same time the margin was affected by the current induced by flux frozen in the vicinity of the loop.

The  operating  margins  were  measured  by  numerous  times  for  correct  cell operation  at  different  values  of  the  probe  voltage.  The  test  result  was  extracted  by returning to the nominal set of biases and reading out the content of the whole register. The circuit  was  capable  of  operating  as  a  collection  of  digital  SQUIDs.  The  complete measurement cycle is operated for a number of sophisticated sequence of data and clock pulses as well as variation of bias voltages. The OCTOPUX setup [33] was for the entire measurement procedure.

Another shift register technique [42] requires some extra hardware but in return dramatically simplified the testing procedure.

## 2.6 Experimental Setups

Two experimental setups were used for the experiments. One of them was based on 0.5 W 2-stage close-cycle refrigerator 'Coolpower 4.2GM'from Leybold Cryogenics. For  testing  a  superconducting  circuits  we  developed  a  special  cold  head  (figure.  2.4) providing  about  a  5.2  K  operation  temperature.  The  other  setup  is  our  chip  holder immersed  in  a  commercial  Helium  Dewar  (4.2  K).In  both  setups,  thermo-cycling  or 'defluxing' procedure (the chip is heated above critical temperature to expel the frozen flux  and  then  allowed  to  cool)  was  provided  under  OCTOPUX  control  using  off-chip heaters  and  thermometers.  Additionally,  the  chip  temperature  was  measured  by  the observation of the transition into the superconducting state of Niobium strips located on the  chips  but  not  involved  in  the  operation  of  the  investigated  circuit.  (Each  test  chip contains  two  similar  shift  registers).  The  figure  2.4(b)  shows  the  3D  Helmholtz  coil arrangement for providing magnetic field during the experimentation.

Figure  2.2:  Structure  of  the  counter-flow  shift  register  consisting  of  D  cells  (a)  and  timing  JTL splitters  (b).  Note  that  D  cells  have  extra  current  terminals  (Probe)  connected  with  the  separate power line with zero nominal bias voltage

<!-- image -->

Figure 2.3: Layout of the test circuit (a) and one of D cells (b). Solid black lines show holes (moats) in the lower ground plane

<!-- image -->

Margins for the current probe usually measured with about 0.5 µ A accuracy. This accuracy was achieved due to averaging over about 50 to 1,000 primitive measurements (for  details  see  [13]).  About  50  thermo-cycles  at  each  of  the  different  values  of intentionally applied magnetic fields in both normal and tangential directions.

Figure 2.4: (a)Cold head of the Cryo-cooler(b)3D Helmholtz coil setup

<!-- image -->

## 2.7 Analysis of Experimental Results

## 2.7.1 Global Analysis of the circuit

As  we  already  mentioned  after  each  thermo-cycle,  circuit  operation  as  a  shift register is checked. It can be seen that the probability of incorrect operations depends on the applied magnetic field.

In  figure  2.5  the  lower  and  upper  margins  for  5  independent  bias  voltages  is shown. Four upper plots (starting from the top one) illustrate margins for DC/SFQ and SFQ/DC converters, timing JTL/splitters, micro-strip interfaces and finally the conventional  D  cell biases.  They  are important  for  comparison  of flux trapping sensitivities of mentioned circuit components.  However, below we will focus only on the probe bias margins shown as the lowest plot in figure 2.5.

The horizontal coordinate for all plots is the applied magnetic field. The stripes (pink color) in the middle of the plots mark the 'restricted' zone where the margins are

too low for reliable investigation. As a result, all experimental points within the stripes are eliminated from the circuit analysis.

Figure 2.5: Spread of upper and lower are bias margins for major components of the test circuit. The stripes show the minimal margins required for further testing of individual cells.

<!-- image -->

## 2.7.2 Margins of Individual D Cells

Earlier it was described in the procedure that allows extracting margins for any of 16 D flip-flop cells. Figure 2.7 shows upper margins for each of the 16 measured cells. First,  the  fabrication  spread  is  extremely  low  (about ± 5 µ A).  The  shift  register  is organized  as  4  groups  of  4-bit  registers  (figure.  2.3a)  connected  by  micro-strip  lines, showing the deviations are mostly due to different positions of cells in the register. The plot shows that the pure fabrication spread within the same positions in different groups is  below  ±2 µ A.  This  is  a  very  interesting  observation  as  it  shows  'design  induced'

Figure 2.6: The probability of too narrow margins or incorrect operation at different perpendicular magnetic fields

<!-- image -->

Figure 2.7: Margins of D cells not affected by trapped flux. (a) Shows margins for 16 individual cells. (b) Shows the same data but 'convolved' position of cells in four groups of 4-bit shift registers

<!-- image -->

It is easy to see that at lower fields (below 3 mG) there are no noticeable fluxtrapping  induced  deviations  of  the  margins.  The  probability  of  flux  trapping  increases with  magnetic  field.    However  the  dominant  effect  here  is  caused  mostly  by  the  flux

trapping  in  cell  #13.  Moreover,  the  flux  trapping  in  this  cell  always  causes  the  same margin deviations (+ 32 µ A at negative fields and -32 µ A at positive fields).

Measured  deviations  of  margins  for  each  cell  into  3  groups:  small  deviations (below 4 µ A), medium deviations (4 µ A to 20 µ A) and large deviations (more than 20 µ A). Figure 2.9 shows the deviation due to the field applied in the normal direction and the figure 2.10 deviation probability as a function of parallel field.

Another interpretation of the probability of deviation is shown in figure 2.11. The probability  of  events  within  each  group  is  marked  by  circles  of  corresponding  size. These deviations are caused either by flux frozen in moats located close to the cells or in remote timing JTLs. (In the latter case the flux affects the propagating delay that in turn  affects  the  operation  margins.)  Only  few  of  the  several  cells  are  affected  by  flux trapping. This is especially true for the large margins deviations. More specifically, only one cell (#13) shows the dramatic impact of flux trapping. There are 9 more cells that have been affected at least one time. The rest 6 cells have not been affected at all. The variation of flux trapping from cell to cell indicates its close connection with microscopic fabrication imperfections. This is a positive observation because technological imperfections are easier to overcome than fundamental limitations.

## 2.8 Discussion

The influence of flux trapping on the operation of RSFQ cells has been evaluated using  PSCAN [18],  3dMLSI and other  models.  A  complete  methodology  to  study  the effects of flux trapping in superconducting circuits was established. The experiments of flux trapping were carried out in both in a closed-cycle setup and measured several other chips using both the cryo-cooler and Dewar setups. We were able to establish that the

worst case coupling between a vortex and the circuit component was about 0.2 Φ 0 .  The perpendicular magnetic field only significantly affects the circuits in flux trapping with tangential  magnetic fields  not contributing.  The established experimental methodology also can be used to determine defective cells. This measurement technique complements SQUID visualization techniques [34,35,36,52].

Figure 2.8 Deviations of threshold current for all 16 cells repeatedly measured at different magnetic fields.

<!-- image -->

Figure 2.9: Probabilities of deviations of margins as functions of normal magnetic field.

<!-- image -->

Figure 2.10: Probabilities of deviations of margins as functions of tangential field

<!-- image -->

Figure 2.11: Probabilities of deviations of D flip-flop threshold currants caused by flux trapping in tangential (a) and normal (b) magnetic fields. Please note that the tangential fields are larger than normal ones. As a result, it would be incorrect to use this plot to compare sensitivities to tangential and normal fields.

<!-- image -->

## Chapter 3

## Moats in Superconducting Circuits

## 3.1   Introduction

As discussed, in the previous chapter, the frozen flux can affect the superconducting  circuits  by  two  different  mechanisms:  it  can  either  directly  'punch' Josephson  junctions  [32]  or  the  frozen  flux  could  be  directly  coupled  to  magnetosensitive SFQ gates [44].

The  first  necessary  step  in  preventing  flux  trapping  is  shielding  of  the  ambient (Earth)  magnetic  field.  However,  this  measure  has  proven  to  be  inadequate  response. Indeed,  the  flux  is  typically  trapped  by  single  flux  quanta.  Their  numerical  value: 7 0 ~ 2.07 10 -⋅ Φ G cm 2 is rather small and, as a result, the residual magnetic field B should be very low to keep the density of frozen flux quanta:

<!-- formula-not-decoded -->

Below one frozen flux quantum per chip. (As an example, eq. 3.1 gives n one flux quantum per cm 2 at B about 0.2 µ G or about  2 x10 6   times  below the Earth's  magnetic field.) It is difficult to achieve this level of attenuation, but even such attenuation does not solve the problem because there is a probability of flux trapping even in a magnetic field that is well below the threshold of one vortex per chip.

As a result, it is almost mandatory to allocate some space on superconductor chips for  special  traps  in  order  to  keep  frozen  vortices  far  enough  from  magneto-sensitive circuits. These traps or moats in the ground planes and other large superconducting films are  an  early  [21,22,72,73]  and  still  the  most  effective  way  to  reduce  the  sensitivity  of

superconductor circuits to flux trapping.

## 3.2   Basic Designs Consideration of Moats

Moats  of  different  sizes  and  shapes  demonstrate  different  efficiencies  for  flux trapping  [21,22,72].  However,  the  reported  results  have  no  clear  conclusion  on  the shapes, sizes and density of moats. So to get an idea on the type of solution, the particle observations are summarized.

In  most cases the critical  magnetic  field at which  moats are still able to trap all frozen  flux,  ranges  from  2  mG  to  20  mG  [45,].  These  fields  correspond  to  10 4 to  10 5 vortices per cm 2 or about 100 µ m to 30 µ m average distance between the vortices. This distance is comparable to or less than a typical cell size (135 µ m in our experiments).

It  is  difficult  to  estimate  the  efficiency  of  any  particular  combination  of  moats theoretically.  However, such estimations  for simple geometries are trivial:  Firstly,  it  is natural  to  suggest  that  the  moat  density  should  be  sufficiently  high  and  exceed  the expected  density  of  frozen  vortices.  This  is  important,  because  a  vortex  frozen  in  the moat  repulses  other  vortices  of  the  same  polarity  and  therefore  reduces  the  moat efficiency.

The requirement  for high  moat density contradicts another requirement that the moats be long. (To be efficient a moat should be longer than the distance between the moat  and  the  protected  area.)  It  is  possible  to  derive  formulas  for  different  moat geometries, (see, for example, discussion in [23]):

<!-- formula-not-decoded -->

The eq. 3.2, has proven to be reliable in estimating the critical fields for vortex expulsion

in  superconducting strips. Originally, it was derived for the critical magnetic field of a superconducting strip with width W [23, 29] but we noticed that it works even better if W is the distance between long and narrow moats.

It is important that the critical field is inversely proportional to the second power of the distance between moats. (As two examples we can note that 20 mG field is critical for about 25 µ m distance between the moats and a typical 400 mG Earth magnetic field would be critical at about 5.6 µ m moat spacing.)

## 3.3  Moat Patterns

The cells with one old design- previously used moat designs, all results in chapter 2 were obtained for this design- and 7 new moat patterns are shown in figure 3.3a. The dimensions  of  all  investigated  cells  are  135 µ m  x  135 µ m.  Moats  in  the  pictures  can easily be seen due to their darker intensity.

Our design was done in accordance to the layout that already existed (chapter 2 results). The moats were designed around the inductance and Josephson junctions in the layout and all unused space was filled with moats. Besides, it was useful to increase the inductances of bias resistors. To achieve this goal we opened moats under these resistors. The  higher  inductances  on  the  biasing  leads  also  reduce  power  consumption  during operation of the circuit. The technique is called L-R loading and is discussed in greater detail in [61]. Finally, where possible the cells were surrounded by moats that were not part of those cells. As we reported earlier in chapter 2, large circuits with such cells have been operational at residual fields below 2 mG to 5 mG. The moat pattern (figure 3.3e) could be described as medium length and medium density.

Figure 3.3a shows the small moat pattern where the moats are just placed around

the  Josephson  junction.  The  objective  of  this  design  is  that  to  check  if  just  protecting active structures such as Josephson junction are enough for reducing the probability of flux trapping.

Figure 3.3a shows the best of the investigated patterns that could be described as a combination  of  very  long,  but  rather  remote  moats  and  shorter  moats  bent  around  the edges  and  corners  to  be  placed  as  close  to  the  investigated  circuitry  as  possible.  The widths of the moats are 3 um.

Figure 3.3b  an  attempt  is  made  to  towards  a  regular  moat  pattern,  which  is 'interrupted'  by  the  circuitry.  More  exactly  the  moat  pattern  here  presents  a  set  of equally spaced (with 15 µ m distances) horizontal moats with bridges that are added only to keep the circuitry over the continuous ground plane. The widths of the moats are 3um.

Figure 3.3c corresponds to the oldest known recommendation [19,22] - all space not occupied by the circuitry should be occupied by large moats.

Figure 3.3d shows moats similar to the 'old' designs, as used in chapter 2, but with a larger density. In other words, the pattern is similar to those shown in figure. 3.3e but some additional superconducting 'walls' are added to split larger moats into a greater number of smaller moats.

Figure  3.3f  shows  moats  in  which  most  of  the  space  is  not  occupied  by  the circuitry, similar to the  figure 3.3c. But in this  layout the top ground plane is  not used here, which is supposed as superconducting protecting plane to shield external magnetic field during cooling.

In figures 3.3g and 3.3h, are based on continuous moat designs in which one and two continuous moat covering all the six cells are designed respectively. The moat widths

are 3um and are bent around corners to fit the design of the already existing Josephson junction layout.

All  the  patterns  discussed  above  have  a  common  drawback:  their  shapes  are defined  by  the  space  occupied  by  the  circuitry.  In  other  words,  first  we  design  the circuitry and only later we add some moats.

<!-- image -->

Figure 3.1: It is a 6bit counter clock shit register. The chip was fabricated at Hypres with 1kA/cm2 process. JJ count 996

<!-- image -->

CLK

Figure 3.2: Block diagram of the shift register.

Figure 3.3: Layouts configurations for different moat patterns.

<!-- image -->

Figure 3.3: Layouts configurations for different moat patterns.

<!-- image -->

Figure  3.4:  Deviation  of  the  threshold  current  induced  by  frozen  flux  as  a  function  of  applied magnetic field perpendicular to the chip. Solid vertical lines show the threshold magnetic field that separates acceptable and inacceptable values of the ambient magnetic field. Different plots (see text) correspond to different moat configurations .

<!-- image -->

Figure 3.5: Bubbles represent the probability of a deviation of threshold current caused by trapped vortices. Small bubbles correspond to the deviations in 1-4 µ A range, medium bubbles correspond to 4-20 µ A deviations, large bubbles indicate deviations that are greater than 20uA.

<!-- image -->

## 3.4 Threshold Limit of Moat Pattern

The process of measurements for these experiments has been described in detailed in  section  2.5  of  the  previous  chapter.  However,  the  test  chip  was  designed  with  the intention  of  multiple  I/O  for  obtaining  provisions  to  measure  number  of  different  shift registers on a single chip.

Figure3.6:  Threshold  fields  (in  mG)  for  investigated  moat  patterns.  Names  of  corresponding microphotographs in Figure 3. 3 are shown below the columns

<!-- image -->

The most recent revision of our test circuits (Figure 3.1) contains 6 independent shift registers that share only some clock and data auxiliary circuits. As a result, we are able to carry out a comparative study, for example, of six different moat patterns. This time we carried out our experiments at 4.2 K in a transport helium Dewar. The thermocycling  was  provided  under  OCTOPUX  [33]  control  using  off-chip heaters  and thermometers. The magnetic field was applied only during the chip cool down. Typically, we made 50 thermo-cycles at each magnetic field and totally about 10,000 thermo-cycles

for one experiment that usually lasts from 24 to 48 hours.

## 3.5 Experimental Results

As we  mentioned  in  the  previous  chapter  data  can  be  represented  in  numerous ways. The plot is a dependence of deviation of margins for 'Probe' currents from their nominal values (not affected by the flux trapping) as a function of magnetic field (Figure. 2.4, chapter 2). (Note that D cells have the extra current terminals 'Probe' connected to a separate power line with zero nominal bias voltage.) It is easy to see that the deviations are rare and small at low fields and much more frequent and greater at larger fields. Two solid  vertical  lines  in  figure  3.4  visually  separate  these  areas  and  show  critical  fields. Note that D cells have extra current terminals (Probe) connected with a separate power line with zero nominal bias voltage.

These  critical  fields  are  our  most  important  results  and  they  accumulated  for investigated  moat patterns  in  figure.  3.5.  This  figure  definitely  reflects  our  progress  in understanding  the  efficiencies  of  different  moat  patterns.  The  best  result  achieved  is about 20 mG. We would like to note that it is rather close to the simple forecast provided by eq. 3.2.

To see variations of flux trapping from cell to cell we use 'bubble' plots (Figure 3.6), in which the horizontal position of the bubble on the plot codes the cell number. The vertical  axes position of the  bubble shows (in a log scale) the probability of flux being trapped.  The  plots  show  bubbles  of  three  different  sizes.  The  small  bubbles  show  the probability  of  very  small  values  of  circulating  currents  (1 µ A to  4 µ A)  induced  by  the trapped flux.

So small currents are not dangerous for the cell, but we present these data as proof

of  the  high  accuracy  of  our  technique.  Besides,  we  believe  that  these  deviations  to  be expected because they are caused by vortices trapped in the moats. Medium bubbles (4 µ A to 20 µ A) correspond to damage that, we think, would not be acceptable for circuits that should operate near their speed limits or in the case of very large integration level. Finally  the  large  bubbles  (above  20 µ A)  correspond  to  damage  unacceptable  for  any practical circuits. Unfortunately the bubble plots contain data averaged over all values of applied  magnetic  field.  As  a  result,  they  depend  on  the  range  of  the  applied  fields. However, as we mentioned earlier here, we have the possibility of comparing properties of  similar  cells  in  one  register.  It  looks  as  though  all  the  cells  of  one  register  have statistically  equivalent  flux  trapping  properties.  However,  earlier  in  chapter  2,  we observed  that  some  cells  could  be  much  more  sensitive  to  flux  trapping  because  of undetected fabrication defects.

## 3.6 Empirical Rules for Developing Moat Patterns

Based on the above obtained we can formulate a set of guidelines for developing a RSFQ layout in which the circuits will be most resistive to parasitic flux trapping.

The procedure can be summarized as empirical rules

1. It is recommended that multiple long moats are used in the cell design.
2. The circuit elements must be designed in rectangular span of width around 50um. If circuit design span is larger than widths 50um, long rectangular moats must be incorporated within the design elements.
3. It is advisable to have at least only moat close to every Josephson junction. JJs are the most effected in the event of flux trapping and every precaution must be taken to safeguard them.

4. The  gap between the moat  holes must be much  smaller than moat  size only then the moat will have an effect.
5. The gap between two moat holes must not be too close that shielding current will exceed the critical current.
6. The bias lines will attract vortices when carrying high value of currents. So the bias lines must have moats close to it to trap the flux.
7. Care  should  be  taken  as  the  holes  not  cross  bias  lines  to  prevent  shorts  in  the circuits.
8. Use of multiple numbers of small moats should be avoided.

## 3.7 Fabrication Dependency

The effect of fabrication and flux trapping was also determined. When we tested two  circuits which  are schematically equivalent and also have the same  layout configurations, the effect of fabrication run can be found out.  It turns out that the flux trapping process is very less influenced by fabrication. This is evident in the figure 3.7 where the deviation of the threshold current is zero till the perpendicular magnetic field is of the order 7 mG.

## 3.8 Discussion

We  investigated  eight  moat  patterns  and  its  influence  on  flux  trapping  in superconducting circuits. The most important thing is to avoid serious mistakes such as leaving  large  chip  areas  without  moats  or  making  a  moat  only  in  one  ground  plane without a corresponding moat in the other ground plane.

100

Figure 3.7: The threshold current deviation for layout 1e, for mask releases (a) KL1094 (b) KL1025

<!-- image -->

Next, it is important to keep the distance between the moats as small as possible. At  20 µ m  to  30 µ m  distance  (that  is  easily  achievable  with  the  available  HYPRES technology) [82] the critical field could be as high as 20 mG. If Eq. 2 is correct then at 5 µ m  moat  spacing  the  critical  field  would  be  comparable  with  the  Earth's  (400  mG) magnetic field. This scale of dimensions is challenging for currently available superconductor technologies. This  is  because all  active circuitry  should  be  placed  over narrow (5 µ m) ground plane 'strips'. But this goal could be within the reach of any well developed  sub-micron  lithography  techniques  if  it  is  available  for  superconducting technology.

Finally, the moats should be sufficiently long. More exactly it is highly desirable that they are  longer than the distance between them. Fortunately we did not notice any indications that some moat shapes are worse than others. In other words, there is great freedom in selecting moat shapes and patterns that would fit practically any design style.

## Chapter 4

## Power Independent RSFQ logic cells

## 4.1 Introduction

Low  power  RSFQ  cells  are  essential  in  the  large  scale  integration  of  RSFQ circuits. The  dissipation of  power in RSFQ  circuits is small in comparison to semiconductor  devices,  but  high  for  the  temperature  range  of  4K.  The  main  source  of power loss is mainly due to the static dissipation in the bias resistors. The dynamic power dissipation,  due  to  the  switching  operations  of  the  junctions,  is  quite  low.  The  static power dissipation is a result of continued applied bias to the circuit, to maintain the logic state of the operating circuit.  Low power RSFQ circuits have been recently reported to be  used  as  support  circuits  for  developing  superconducting  quantum  computational structures  [18,19,70,81].    Mentioned  prospective  SFQ  circuits  are  diversified  and different kind of circuits would  require different  power  minimization  techniques [41,43,61,67,68,69,75,76,77].

## 4.2 Basics of Power Independent Operation

In  this  chapter,  we  discuss  a  new  technique,  where  circuits  are  able  to  perform some functions without any significant energy static dissipation. More exactly, we try to show that the suggested technique could be applied to any  RSFQ cell to obtain Power Independent (PI) operation. Power independence, means an ability to switch off circuits without any loss of stored information. As a result, power independent circuits could be powered only when logic operations should be performed [49,50].

The simplest power independent circuit with memory is a well-known single-junction SQUID [5] as shown  in  figure  4.1a.  The  single  junction  SQUID  is  a  superconducting

loop with sufficiently large loop inductance L interrupted by a single Josephson junction. The dynamics of single Josephson junction SQUID has been well known for many years now and will not be discussed in detail here. But, it may be sufficient to recap the flux modulation as a function of the bias current to the SQUID as shown in figure 4.1b. From the  figure  4.1b  we  can  see  that,  we  can    write  "1"  or  "0"  by  applying  large  enough positive  ( 1 th b I I &gt; )  or  negative  ( 0 th b I I &gt; )  bias  current b I .  The  device  continues  to remember  any  of  these  states  if  bias  current  is  switched  off  ( 0 = b I )  as  there  is  no dissipation in the superconducting loop.

Figure 4.1: A single junction SQUID as the simplest power independent cell

<!-- image -->

The introduced memory cell of single junction SQUID could be incorporated into RSFQ  flip-flops  and  logic  gates.  Before  we  discuss  the  operation  of  the  power independent RS flip flop let us understand the operation of RSFQ RS flip flop.

## 4.3 Developing Power Independent RS flip-flop

First, let us recap how a RS Flip-flop functions, shown in figure 4.2a. The J3, L, J4 loop is a two junction interferometer with 0 1.25 Φ = I L c , so it can store a flux quantum. The current in the loop can be expressed as the sum of the bias current equally divided between the two junctions and circulating current L I p / 2 = ±Φ .

Figure 4.2: Transformation of a conventional RSFQ RS flip-flop (a) into a power independent cell (b)

<!-- image -->

Initially,  the  circulating  current  is  counterclockwise,  representing  a  stored  '0'.  The currents when the bias is applied are p J I Ib I + = / 2) ( 3 and p J I Ib I -= / 2) ( 4 .

When input pluses are applied to the input (S) and reset (R) terminals, this causes circulating current to reverse polarity. When pulse arrives on the input, its current passes through the J2 (nearly biased at 0 Φ = ) and causes J3 to switch and the circulating current is  transferred to J4. The clockwise circulating current is representative of a stored '1'. Then, when a reset pulse is applied, it passes through J1 and into J4, thus causing it to switch. The voltage pulse developed during the switching reverses the circulating current, so again a '0' is stored in the loop; it simultaneously applies this SFQ voltage pulse to the output through J4.

The junctions J1 and J2 have lower critical currents than J3 and J4 and to protect

the  inputs  from  back  reaction  of  the  interferometer  if  pulses  come  under  the  wrong circumstances.

In the conventional circuit figure 4.2a, as discussed above, the magnetic bias is created by asymmetrically applying bias current b I . This magnetic bias disappears if the bias current is switched off. As a result the circuit keeps its internal state only as long as the bias current remains applied.

Figure 4.2b shows this transformation for the simplest RS flip-flop. The operation of the Power independent RS flip flop operates in the similar manner as the conventional RSFQ RS  flip  flop.  In  contrast  PI  cell  (figure  4.2b)  holds  its  magnetic  bias  inside  its SQUID, instead of a single quantizing inductance. To activate the SQUID and the circuit one  should  apply  large  enough  bias  current b I .  (Note  that  this  "activating"  current  is slightly  greater than  its  nominal  value  for  regular  logic  operation.)  Being  activated  the circuit remains magnetically biased (presumably by flux about /2 0 Φ ) even if bias current is  off.  Note  that  even  power  independent  circuits  should  be  powered  to  perform  logic operations, in order to provide the needed the additional magnetic flux bias.

## 4.4 Investigations of Power Independent Circuits

In  order to  investigate the  power  independent  RSFQ  flip  flop  we  simulated  the RSFQ  flip  flop.  The  clocked  RS  flip  flop,  where  the  reset  terminal  used  as  the  clock terminal can be used as the RSFQ D flip-flop.

## 4.4.1 Design of 6-bit Shift Register with PI cells

Figure 4.3 shows schematics of a D flip-flop re-optimized for operation in power independent  mode  at  4  K.  The  power  independent  D  flip-flop  has  the  single  junction interferometer that can be identified by schematic components L1, L2, LD4 and J0. The

interferer meter is biased by current IPI. The components in the figure 4.3 are represented by dimensionless PSCAN units, which are easier for computation.

Figure 4.4 illustrate  current  and  input  data  patterns  used  for  a  numerical  circuit optimization with PSCAN software package. The new feature of the simulation is a more complex  shape  of  applied  bias  current  IPI.  During  the  simulation  it  was  required  that junction J0 is switched only one time and when IPI current it applied for the first time. No other junctions switched when bias current goes down.

Figure 4.3 Power Independent D flip-flop. Bias current IPI does 2 things: it 'activates' SQUID with junction J0 and power the cell during its normal operation

<!-- image -->

## 4.4.2  Experimental Results

A 6-bit shift register with PI D cells has been designed and laid out for HYPRES fabrication  technology.  The  shift  register  has  been  incorporated  into  a  benchmark  test chip developed for a comparative study of flux trapping sensitivities of different D cells. (The revision of the test circuit has been presented in chapter 2.)

Figure 4.5 shows a  microphotograph of a  fully operational circuit (as shown  in figure 4.6) fabricated at HYPRES (1 KA/cm 2 technology). Bias current margins (±16%) for the only measured chip are about 2 times below our numerical estimations (35%).

The  figure  4.6  the  shift  register  was  tested  with  Octupux  setup,  where  the  low speed testing was used to confirm the correct operation of the shift registers. Since the shift register is a counter shift register, the clock and the data pulses travel in the opposite direction and this can be confirmed by the traces in figure 4.6.

Figure  4.4:  Current  (upper  trace)  and  voltage  waveforms  illustrating  the  power  independent operation of D cell. Note that the 'activation' procedure could require larger current IPI than those during the regular circuit operation

<!-- image -->

## 4.5 Flux Trapping in Power Independent RSFQ Cells

The  topic  of  flux  trapping  was  discussed  in  chapters  2  and  3  in  detail.  In  this chapter to complete the study of power independent cells in RSFQ cells, we investigate flux  trapping  in  power  independent  RSFQ  cells.  The  methodology  to  investigate, including  the  circuits  and  I/O,  are  the  same,  as  discussed  in  chapeter  2,3,  and  the designed chip can be seen in  figure 4.5.

Three different layouts configuration for the PI-RSFQ cells were investigated. It presents the results of  investigations  of  a  specially  developed  chip  that  contains  power

independent RSFQ cells with apparently the same schematics but different layouts. The goal of this experiment is to compare prospective design styles and to select those with the highest 'resistance' to the parasitic flux trapping and also compare with flux trapping in conventional RSFQ cells.

Figure 4.5: The microphotograph of the shift registers of the power independent cells. The first three registers are designed with power independent cells.

<!-- image -->

Figure  4.6:  Low  speed  testing  of  one  shift  registers.  The  logic  '1'applied  to  the  input  (two  lower traces) is read out from the output (the second from top trace) after 6 clock cycles (middle traces)

<!-- image -->

Figure 4.7: Three layout configurations for PI D flip-flop.(a)Josephson junctions are grounded only to the sky plane,(b) Josephson junctions are grounded by using sky plane and ground plane,(c) sky plane is absent.

<!-- image -->

Figure 4.8: Threshold deviations for corresponding layouts configurations in figure 4.7

<!-- image -->

Figure 4.9: Probability of flux trapping in the each cell for the corresponding layout in figure 4.7

<!-- image -->

The  results  of  the  flux  trapping  experiments  on  shift  registers  designed  with power independent cells  are  shown  in  figures  4.8  and  4.9.  The  method  to  explain  the results  shown we use the same  interpretation used  for figures 2.8 and 2.9 presented  in chapters 2. Based on the results presented, we can now deduce which is the best layout configuration.

The  lower  the  threshold  current  deviations  for  each  cell  with  varying  magnetic fields  are  the  better  the  configuration  against  parasitic  flux  trapping.  Deviations  of threshold currants caused by flux trapping magnetic fields are shown in the corresponding figure 4.8 for each layout in figure 4.7.  We can see that the best layout configuration is figure 4.7b.  We can observe that at lower fields (below 3 mG) there are no noticeable flux-trapping induced deviations of the margins in figure 4.8b, but in figure 4.8a the deviation is large. In figure 4.8c the threshold fields are much lower than figure 4.8a; figure 4.8b and deviation of the margins occurs at lower magnetic fields. The least deviations observed in the threshold current are in figure 4.8b over large magnetic fields. The graphs cannot be directly compared as the working threshold for each layout as the operating regions are different, but more or less each layout gives an insight as which of the layout is most resistant to parasitic flux trapping.

The probabilities of deviation of threshold currents are shown in figure 4.9.  We can see that the probability of large deviations of current (over 20 µ A, which are likely to cause the circuit to fail),  is small  for  figure 4.7b, but quit high  for figure 4.7a. We can also see that the probability of deviation of large current is least for figure 4.7c, but we have to keep in mind that the threshold operation limit for figure 4.7 is the least, so in that operating  region  it  works  best  (below  3mG  magnetic  field).    In  figure  4.9b,  we  do

however, see that one cell namely '5' of the shift register indicates a probability of  larger than the average for large deviations, we are likely to believe it is due to damage caused to the cell (such as a scratch) or presence of impurities in close proximity to it.

## 4.6 Discussion and Conclusion:

In  this  chapter,  we  have  successfully  proposed  and  demonstrated  a  new  low power technique called the power independent RSFQ cells. The operation of the power independent was verified by simulation. The power independent D flip flop was used to construct a 6 bit shift register and its operation was verified experimentally. Flux trapping experiments were also carried out on three different  layout configuration of the power independent D  flip-flop  layouts. The performance of Power  independent D  flip  flop  is inferior  than  conventional  D  flip  flop  towards  parasitic  flux  trapping,  which  can  be attributed to the single junction interferometer used as a memory element in the PI-RSFQ flip-flop.

## Chapter 5

## Current Recycling: Technique and Application

## 5.1 Introduction

One of the  main  advantages  of  RSFQ  circuit  is  that  only  dc  bias  is  needed.  It eliminates  the  cross-talk  problems  caused  by  ac  biasing  and  makes  designing  larger

blocks easier. However, in larger circuits the total dc bias current could add up to a few amperes and such large bias currents cause large heat dissipation, which is not preferred.

One  of  the  techniques  that  has  been  proposed  [10]  is  biasing  the  circuits  serially otherwise commonly known as 'current recycling'. Biasing large circuit blocks in series

(referred to as current recycling or current re-use) will essentially reduce the total current supply  for  the  superconducting  IC  to  a  manageable  value.  Both  capacitive  [57]  and

inductive  methods  [56]  of  current  recycling  have  been  demonstrated  at  a  small  scale.

Current  recycling  becomes  easier  at  higher  current  density  of  the  superconducting  IC.

Current recycling however has its limitations; it does not reduce the on-chip static power dissipation by the circuit blocks and also due to additional structures, the area occupied

by the circuit's increases.

In  this  chapter,  we  will  demonstrate  the  implementation  of  current  recycling technique using inductive coupling, also its application in the design of high frequency

drivers.  The  circuits  designed  by  current  recycling  technique  have  been  found  to  be highly sensitive to external magnetic fields.

61

## 5.2 Serial Biasing Circuit Technique

To demonstrate the method of current recycling, we have designed a Josephson junction transmission line (JTL) as shown in figure 5.1. The complete operating principle of the circuit is explained below.

The figure 5.1 shows structure of one module. The module consists of three parts, the driver, receiver and the payload. The payload is usually the circuit block that is used for  operation,  in  this  case  to  keep  matter  simple  a  JTL  has  been  used,  as  its  operating margins  are  very  high.  The  payload  can  otherwise  be  replaced  by  flip-flops,  filters,  or logic gates.

Before we explain the operation of the driver-receiver circuit, it  is  important to remember a few thumb rules for the current recycling design. For current recycling, the ground  planes  under  adjacent  circuit  blocks  must  be  separated  and  subsequent  blocks biased  in  series.  It  will  also  be  necessary  to  isolate  SFQ  transients  between  adjacent blocks. This may be achieved by low pass filters, but will need to avoid power dissipation in  the  filters.  Series  inductance  could  provide  high  frequency  isolation;  the  inductors could  be  damped  by  shunting  with  suitable  resistance,  such  that  there  is  no  DC dissipation.  Capacitive  coupling  between  adjacent  blocks  can  be  used  for  current recycling however they are not discussed here and also capacitors used for this method also occupy larger space compared to the inductive filtering method.

To demonstrate the technique, the circuit with 80 payloads (JTL) serially biased was considered. The payload block consists of a receiver and driver. The requirement for serial biasing of circuits is that

Figure 5.1: (a) Block diagram of current recycling digital transmission line.(b) The microphotograph of the layout digital transmission line

<!-- image -->

1.  The current drawn from each circuit must be equal
2.  The input and output must not add current to the serially biased circuits.

The  inputs  and  outputs  are  connected  via  galvanic  connection  to  satisfy  the  above requirements.

In figure 5.2, the complete schematic of the driver- receiver is shown. The driver and receiver circuits are completely different grounds (more clearly in the layout figure 5.3). An inductor connecting two Josephson junctions momentarily stores a single flux quantum while  an  SFQ  pulse  propagates  from  one  junction  to  another.  Typically,  this duration time is about 5picoseconds, depending on the circuit parameters. Between the times  when  J13  and  J14  generate  a  voltage  pulses,  the  magnetic  flux  stored  in  the inductor that connects J13 and J14 induces a current in the inductor, L1u, connecting J1

and J2.  With proper circuit parameters, this induced current causes a voltage pulse to be created on J1 and this pulse then propagates through J2 to be further processed. In this way, an SFQ signal pulse is transferred from one ground to another plane.

Figure 5.2: Circuit schematic for magnetic coupled SFQ pulse transfer between driver and receiver

<!-- image -->

In figure 5.3 the circuit layout is shown corresponding to the circuit schematic of figure 5.2. The bias current for the junction on the input side are passed to one ground plane  while  the  ground  for  the  junctions  on  the  output  side  is  isolated  from  the  other ground by a ground plane moat. The Josephson junction J13 and J14 are damped more heavily than other junctions to guarantee that minimum reflections take place at the end of the input JTL. Tight magnetic coupling is required between the pulse transmitting the JTL  and  the  pulse  receiving  JTL  to  obtain  a  robust  circuit  with  excellent  operational margins.  To  ensure  higher  coupling  holes  were  opened  in  both  the  upper  and  lower ground  planes  as  indicated.    The  complete  block  diagram  for  the  circuit  that  was fabricated is shown in figure 5.4. The complete fabricated chip that was tested is shown in figure 5.5.

Figure 5.3: Layout for magnetic coupled SFQ pulse transfer between driver and receiver

<!-- image -->

## 5.2.1 Experimental Verification of Current Recycling

The digital traces for the correct operation of the circuit are shown in figure 5.6. The measurements were carried out at low frequency using Octupux setup. The circuit tested  used  the  standard  I/O  blocks  of  SFQ/DC  converters  to  measure  the  operating margins of the circuits. The circuits were fabricated for both 1kA and 4.5KAcm2 Hypres tri-layer  Nb  technology.  The  circuit  has  margins  of  ±15%.  The  bias  current  to  obtain correct  operation  was  reduced  to  1.7mA;  otherwise  the  operation  of  80  blocks  with parallel biasing would require nearly 200mA.

Figure 5.4: The complete block diagram of the serial biasing method.

<!-- image -->

Figure 5.5: The microphotograph of the chip for demonstrating current recycling.

<!-- image -->

Figure 5.6: The digital waveform of the input and three outputs as shown in figure 5.4. The traces 1,3,5 are the outputs and 2 is the input trace

<!-- image -->

## 5.3 Summing Amplifier Output driver: application of floating grounds JTL

Based  on  the  principle  used  in  the  previous  section,  one  of  the  applications  is designing the summing array amplifier based high frequency output drivers.

Floating  Transmission  Line  (FTL)  that  receives  SFQ  pulses  from  a  conventional (grounded)  Josephson  Transmission  Line  JTL  (figure  5.7)  is  shown  here.  The  floating grounds are based on the same principle used in current recycling, which was discussed in  the  previous  section.  However,  in  the  digital  transmission  lines,  like  in  the  previous section, where the pulses were transferred, here the magnetic quantum fluxons are stored in the floating transmission block. FTL forms an outlet for a finite voltage value (by AC Josephson  effect),  which  can  be  controlled  by  bias,  and  can  be  used  as  a  driver  when connected in serial or parallel fashion. Originally, these kinds of devices were designed to operate  at  relatively  low  frequencies.  This  is  because  of  distorting  effect  of  parasitic capacitances of each of serially connected FTLs to the ground (figure 5.8). However, this distortion  could  be  presented  as  a  propagation  delay  in  a  parasitic  micro-strip  line

composed of the parasitic capacitances and  inductances of the wires connecting  FTLs. For  this  the  device  has  been  drastically  re-optimized  to  increase  the  maximum  load current to 0.4 mA.

In particular, the bandwidth of the device is dramatically increased if SFQ pulses are applied  to  FTLs  with  delays τ equal  to  corresponding  propagating  delays  in  serially connected FTLs. The output driver could be composed from two voltage multipliers with different gains (N1 and N2) as shown in Fig 5.8.

Figure 5.7: The (a) schematic of the floating transmission line and its (b) block diagram

<!-- image -->

Figure 5.8: The (a) schematic of the N floating transmission lines and its (b) block diagram.

<!-- image -->

Figure 5.9: The microphotograph of the summing amplifier based output drivers - designs based on serial and parallel connections- containing both

<!-- image -->

Figure  5.10:  (a)  The  layout  of  the  parallel  connected  summing  amplifier  based  on  floating transmission line. (b) Shows the microphotograph of the summing amplifier

<!-- image -->

Figure 5.9 shows the complete microphotograph of the drivers based on summing array amplifiers. We designed three structures one is the parallel connected FTLs which has number of controls based on number of blocks- N blocks have N controls, one for each-  and  the  layout  and  microphotograph  is  shown  in  figure  5.10.  The  other  two structures are serially connected with 10 and 20 FTL blocks whose layouts are shown in figure 5.11.

Figure  5.11:  Layout  output  drivers  with  (a)  10  floating  transmission  lines  and  (b)  20  floating transmission lines connected in series

<!-- image -->

## 5.3.1 Experimental Results of Summing Amplifiers

The measurement results for the parallel connected summing amplifier are shown in figure 5.12. The flat Plautus region in the output traces is the optimum region for the operation  of  the  circuits.  One  can  see  when  all  four  FTLs  are  switched  on  the  output voltage of the driver is 0.55mv with bias current margins being 0.85 mA to 0.98 mA. The measurement results for the serially connected blocks are shown in figure 5.13 and figure 5.14 for 10 and 20 FTL blocks, respectively. The flat Plautus region in the output traces is the optimum region for the operation of the circuits.

Figure  5.12:  Measurements  results  of  the  driver  are  shown.  Three  inputs  are  operational  at  bias currents from 1.3 mA to 1.9 mA. One input has lower margins (from 0.85 mA to 0.98 mA). Please note that horizontal axis shows only half of total applied bias current

<!-- image -->

Figure 5.13: Measurement of output voltage of the driver shown as a function of bias current. It is easy to see that at nominal bias (2.0 mA) the load circuit could be from 0 ma to 0.5 mA

<!-- image -->

Figure 5.14: Measurement of the driver with 20 FTLs. The driver operates at bias current from 1.5 mA to 2.0 mA 4k

<!-- image -->

## 5.4 Effect of External Magnetic field

The circuits -current recycling based JTLs and summing array amplifiers - were analyzed for the effect of parasitic residual magnetic field on the operating margins of the circuit. With the available 3D setup developed from previous experiments [chapters 2, 3] was  used.  The  application  of  magnetic  field  one  can  determine,  the  structure  of  the fabricated circuit, defects in fabrication and the magnetic properties of the circuit.

The circuit is still under active research but preliminary results show asymmetric effect of on the margins of the circuit. The figure 5.15 shows that affect of the parallel fields in both parallel directions and the normal direction.

<!-- image -->

(a)

<!-- image -->

(b)

Figure 5. 15: The affect of magnetic field on margins of the operations. (a) x-axis ,(b) y-axis and (c) zaxis, are the direction of the magnetic field applied to the circuit as shown

<!-- image -->

The  asymmetric  effect  is  assumed  due  to  internal  structure  of  the  fabricated circuit.  The  circuit  can  be  considered  to  be  similar  to  a  superconducting  loop.  The orientation of the loop can be estimated by the scanning the magnetic field over the entire horizontal plane (rotational magnetic field). This fact of single loop imitation or a number of  loops  orientated  in  the  same  manner  is  confirmed  by  figure  5.15,  which  shows  the rotation  of  magnetic  field  due  to  both  coils,  a  sine  wave  is  obtained  (so  it  can  be considered as a single coil or many coils in the same orientation ). The magnetic field coefficient that was applied on the X and Y axis were of the or Bx, By = 6.4mG/mA and Bz =1.5 mG/mA.

Figure 5.16: Margins of the circuit due to the scan of 360 degrees of magnetic filed. The orientation of the chip to the axis of the magnetic field is also shown as reference

<!-- image -->

The orientation of the coil can also be determined. In the figure 5.16 is the best angle, the angle at which the margins are same when no external magnetic is applied, is determined. This angle is set and the amplitude on both coils was scanned simultaneously.  The  best  angle  is  approximately  determined  from  calculations

(around (180 -165) =15 degree from x-axis). The orientation of the applied field for XY in figure 5.16 was with amplitude 128mG.

## 5.4.1 Impact of Magnetic Field on 10-stage FTL Based Output Driver

The experiments were carried out in the similar fashion as the current recycling ICs and the output voltage of the driver was noted. The circuit is most sensitive in the Y direction and least sensitive in the Z direction. The result is clear from the plots in figure 5.17. The magnetic field coefficient that was applied on the X and Y axis were of the or Bx, By = 6.4mG/mA and Bz =1.5 mG/mA.

## 5.5   Conclusion

The  current  recycling  technique  for  serially  biasing  RSFQ  cells  for  large  scale integration of RSFQ circuits is explored here. The application of current recycling based principles  was  used  to  design  output  drivers.  The  sensitivity  of  SFQ  cells  to  magnetic field caused by external magnetic field or by normal operation of (many) other cells in proximity was noted.  The excessive sensitivity to magnetic field could be easily hidden by other problems, which are difficult to notice without establishing experimentally.

Figure  5.17:  The  affect  of  magnetic  field  on  the  output  of  the  driver  (10  serially  connected  FTL) operations. (a) x-axis ,(b) y-axis and (c) z-axis, are the direction of the magnetic field applied to the circuit as shown.

<!-- image -->

## Chapter 6

## Multi-Chip Modules

## 6.1 Introduction

It  is  has  been  demonstrated  now  that  superconducting  microstrip  lines  (MSLs) [90] are able to process and transfer digital data with rates up to several hundred GHz [85,86].  The  complexity  and  functionality  of  Superconducting  ICs  are  limited  by  the logic cell density or, crudely, by the number of Josephson junctions (JJs) which can be placed on a single chip. For the existing IC fabrication technologies (see, e.g., HYPRES 4.5  kA/cm2  Josephson  critical  current  density  process  [81,82,83,84]),  the  maximum circuit  density  is  ~  2x10 4 JJs  per  chip.  To  increase  the  chip  functionality  one  of  the convenient  ways  to  increase  the  complexity  is  the  use  multichip  module  (MCM) technology otherwise commonly known as flip-chip technology. For MCM technology to be viable, the modules require transferring data between the two superconducting ICs at the  same  or  similar  rates  as  on-chip,  i.e.  up  to  several  hundred  Gbit/s  and  beyond.  In collaboration with Hypres Inc, we developed the new technology for the development of the inter-chip connection for ultra-high data transfer rate.

## 6.2 MCM Modeling

A  mentioned  above  the  MCM  contains  two  superconducting  IC  connected together with a bump. The microstrip lines, power lines and the ground bumps have to assembled in a manner that causes least scattering during data transfer between the two chips. The best configuration is illustrated in figure 6.1.

Figure 6.1: Structure of a wide-band chip-to-chip connection. Signal bump (in the center) is surrounded by 4 ground bumps [17]. (Courtesy R. Rafiq)

<!-- image -->

The figure 6.1 shows the complete structure of MCM, where two chips have to connect such that parasitic  in the entire  structure  has  to  be  at the  lowest  to  reduce  the effect of resonances. The model of the MCM can be represented by a simple PI model as shown  in  figure  6.2.  An  advantage  of  using  this  model  is  that  it  is  convenient  for extracting  the  parameters  for  designing  the  bumps  and  easy  for  simulations.  The simulations were carried out using SONNET software for estimating the parameters of the bumps.

In all the existing MCM bump structures we found that the parameters that could most affect the performance are the inductance of the bump and the capacitance between the two signal pads of the signal bump between the two chips.

Our simulation results  showed that the resistance of the  bump  is  small  and  not influential to reduce the performance of the MCM. The existing structure [17,55,64], the resonant frequency, a determent to optimal performance, is much lower due to relatively high  values  of  inductance  and  capacitance  of  the  bump.  To  increase  the  resonant frequency the parasitic, inductance of the bump and capacitance between the two chips have to be reduced.

Figure 6.2: (a) PI model with all the parasitic components is shown. (b) PI model used for simulation.

<!-- image -->

The pi model in figure 6.2b, with the values indicated, was used for simulation and we obtained resonant frequency of around 72GHz, as indicated in figure 6.3.

Figure 6.3: Scattering parameters S11 and S21 for the pi model in figure 6.2b

<!-- image -->

## 6.2.1 New Bump Structure

The arrangement of signal and ground contacts for inter-chip communication is a peripheral array shown in figure. 6.4. Each signal contact is surrounded by four ground contacts  which  can  also  be  shared  with  the  next  signal  contact.  The  signal  (data)  is coming along a microstrip line (width w ) formed in one of the superconducting layers and

marked MSL in figure. 6.4. The bumps are formed in the centers of the signal and ground contact  pads.  Their  diameter  is  smaller  than  the  diameter  of  the  contact  pads.  The microstrip  line  impedance  is  matched  to  a  load  or  a  driver  at  the  other  end  of  the microstrip line  [46,47].  Conventional  solder  bumps  have  relatively  large  parasitic inductance, p L that is acceptable for relatively slow semiconductor devices having a high, typically R = 50 Ω , impedance. However, high parasitic inductance is not acceptable for a low-impedance, typically ~ 2 Ω , and superconductor devices operating at about 100 GHz data  rate.  This  is  because  the  bump  inductance  limits  the  cutoff  frequency  for  signal transmission through the bump, cf ω , which can be crudely estimated as

<!-- formula-not-decoded -->

The parasitic  inductance  can  be reduced  by  reducing the contact pad size R 1 (figure. 6.4).  This  approach  however  has  evident  technological  limitations  if  the  bumps  are formed  by  manual  solder  wetting.  Besides,  this  reduction  is  rather  small  because  it  is proportional  only  to  ln( R 1)  .  Another  known  approach  is  to  compensate  the  series parasitic inductance by a proper parallel capacitor [46]

<!-- formula-not-decoded -->

However,  the  cutoff  frequency  for  this  solution  is  limited  by  the  resonant  frequency, giving the same answer as

<!-- formula-not-decoded -->

Figure  6.4:  Structure  of  a  wide-band  chip-to-chip  connection.  Signal  bump  (in  the  center)  is surrounded  by  4  ground  bumps.  Bumps  are  deposited  into  the  centers  of  Nb  contact  pads. Superconducting microstrip line (MSL) is connected to the signal bump. It has a specially shaped end overlapping  a  cut  in  the  ground  plane  in  order  to  provide  impedance  matching  and  increase  the transmission bandwidth.

<!-- image -->

Our new interconnect design actively utilizes advantages of several metallization levels  common  for  superconductor  integrated  circuit  technology.  The  ground  plane bumps occupying corners in figure 6.4 provide galvanic connections between the ground plane  layers  on  the  MCM  substrate  and  on  flip  chips.  Their  contact  pads  contain  all superconducting layers (from M0 to M3 in the HYPRES process) mutually connected via contact holes in isolating layers. The sequence of metal layers in the signal contact pad is identical  to  those  of  the  ground  contacts.  However,  the  patterns  of  the  layers  and therefore the bump properties are original. First, the signal contact pad is isolated from the ground plane by a narrow disk-shaped moat shown in white. The microstrip line is galvanically  connected  to  the  bump.  Second,  the  bump  end  of  the  microstrip  line  is shaped such that it overlaps the ground plane moat and behaves as a line with gradually

reducing width. One of the possible implementations of this transition is a 'misaligned' circular end shape formed in the same M2 layer as the microstrip, as shown in figure 6.4.

The  complementary  signal  bump  located  on  the  MCM  carrier  has  exactly  the same  design  but  is  just  mirrored  with  respect  to  the  y-axis.  As  a  result,  the  whole structure after flip-chip bonding behaves almost as a uniform microstrip line which has a transition  in the z-direction  from the MCM carrier (substrate) onto the flipped chip. Of course, the transition creates a parasitic inductance in the vertical z-direction. But for this geometry it is small and easy to calculate as

<!-- formula-not-decoded -->

where  the  sheet  inductance π 1)/2 2 / ln( R R Lw = .  Magnetic  gap, λ 2 + = t t m ,  where λ is magnetic  field  penetration  depth,  is  the  only  parameter  depending  on  the  spacing, t, between the substrate and the flip chip, i.e. on the bump height. It crudely equals to the distance between the ground planes on the MCM carrier and on the flip-chip. At m t m µ 3 = , . 3.8 pH Lw ≈

Another convenient feature of the suggested design is that N depends only on R 2 / R 1 ratio and does not depend on the contact pad and bump diameters. At R 2 / R 1=5, the number of  squares  equals  to  0.25.  As  a  result,  the  parasitic  inductance  is  about  1  pH. Even  for  a  very  low  (e.g.,  2 Ω )  impedance  of  the  mircostrip  line,  the  characteristic resonant frequency r ω according to eq. (6.3) is about 2x10 12 rad/sec corresponding to the cutoff frequency of about 300 GHz. In practice, the cutoff frequency can be even higher. This is because the parasitic inductance p L , is not a lump element but is distributed along the microstrip line with varying width. The distributed inductance can be compensated by a distributed capacitance. In the design, this compensation is achieved by widening the

microstrip line's end and increasing the overlap with the ground plane. The interconnect geometry shown in  figure. 6.4, includes this capacitive compensation. We adjusted the M2/MO overlap area at a fixed R 1 to achieve the bandwidth larger than 150 GHz. For the highest  possible  bandwidth,  both  the  direct  measurements  and  more  detailed  analysis should be carried out to ensure that the geometry is completely optimized.

Yet  another  advantage  of  the  proposed  design  is  that  the  signal  contact  pad, although contains the ground plane layer, is isolated from the circuit ground in the x-y plane by a moat rather than by the interlayer dielectric in the z-direction as is common to many conventional designs. This  makes  it possible to apply  significant pressure to the bump during flip-chip bonding without punching through the insulation and shorting the signal bump to the ground. Also the distributed capacitance can be varied independently of the size of contact pads and bumps.

## 6.3 Test Circuit

Figure 6.5: Block diagram of the ring oscillator used for testing SFQ pulse transmission between the flip  chip  and  the  active  MCM  carrier.  SFQ  driver  and  receiver  are  marked  DRV  and  RES, respectively

<!-- image -->

In figure 6.5 shown is the design of a simple ring oscillator. The bumps intersect the microstrip line between two superconducting ICs. A simple ring oscillator consists of confluence  buffer  or  a  merger,  delay  controllable  JTL,  driver  and  a  receiver.    The frequency  can  be  tuned  by  adjusting  the  bias  current  to  the  JTL.  The  choice  of  the frequency is a compromise between accuracy of the measured voltage and the ability to tune  the  frequency.  The  rotation  frequency  can  be  changed  in  strips  by  varying  the number of circulating pulses in the oscillator.

Figure 6.6: (a) microphotograph of the lithographically defined bumps.(b) The complete chip-set of the multi-chip module

<!-- image -->

## 6.4 Experimental Results

Test circuits were placed on both the flip chips and the MCM carriers. Their block diagram  is  shown  in  figure  6.5.  The  circuits  presented  ring  oscillators  for  testing transmission of single flux quantum (SFQ) pulses from the Josephson transmission line (JTL) on the chip through the bumps to the microstrip line on the carrier and back to the chip. Similarly, SFQ pulses generated on the carrier can be transmitted to the flip chip and back to the carrier. The length of the microstrip lines in different circuits was varied

from 300 µ m to 13 mm in order to see if there are any resonances or other limitations on the data rates associated with the length of the microstrips.

The speed of the pulse circulation was controlled by varying the bias on the JTL as well as by the number of flux quanta inserted into the ring. For a comparison, identical circuits were placed entirely on the chip and on the carrier, so the SFQ pulses do not need to propagate through the bumps. Testing was done using an automated set-up Octopux [33] .

Figure.6.8  shows  the  frequency  of  transmission  of  the  SFQ  pulses  through  the bumps  in  the  ring  oscillator  at  different  biases  of  the  JTL  controlling  the  SFQ  pulse propagation  speed.  Each  curve  from  left  to  right  in  figure  6.7  corresponds  to  a progressively increasing number of SFQ pulses moving in the ring from one to sixteen. Figure 6.8 shows the margins of operation of the receiver ( Res in figure 6.5) in the ring oscillator  as  a  function  of  SFQ  pulse  transmission  rate  in  the  ring.  The  receiver  is  the most sensitive part of the whole circuit, so the margins on its bias current are the most representative  of  the  circuit  operation.  The  maximum  SFQ  pulse  transmission  rate, max f observed  is  about  110  GHz.  Figure  6.9  the  operating  margins  of  the  receiver  are recorded with the flip-chip made by conventional solder technology.

Figure 6.7: The frequency of transmission of SFQ pulses between the flip-chip and the MCM carrier in the ring oscillator at various numbers of flux quanta circulating in the ring for the typical MCM. The maximum of 16 SFQ pulses can be inserted into the ring oscillator. The speed of circulation of the pulses was controlled by varying the bias on the JTL

<!-- image -->

Figure  6.9  shows  the  results  for  the  same  circuit  but  from  a  wafer  bumped manually  by  the  traditional  immersion  process.  The fmax ~  78  GHz  in  this  MCM  is somewhat lower than in the previous one with the Au bumps. However, by testing the ring oscillator located entirely on the flip-chip of this MCM, we found basically the same maximum transmission rate of SFQ pulses. It means that the observed fmax is not limited by  the  transmission  through  the  bumps  but  by  the  operation  speed  of  the  circuit  itself which varies somewhat from wafer to wafer.

The reproducibility of the performance of different circuits on the same MCM is shown in  two  tables  Table  6.1  and  Table  6.2,  for  the  two  typical  MCMs  from  two  different wafers. The circuit performance was recorded for different lengths of the microstrip lines.

Figure 6.8: The upper and lower margins of the receiver bias current at different rates of SFQ pulse transmission between the flip-chip and the MCM carrier with Au bumps. The MSL length is 2210 µm. The wafer was bumped using 1.8 µ m Au bumps deposited by e-beam evaporation. The MCM was bonded by a cryogenically compatible adhesive

<!-- image -->

.

Figure 6.9: The upper and lower margins of the receiver bias current vs the SFQ pulse transmission rate between the flip-chip and the MCM carrier for InSn bumps. Both the chip and the carrier were bumped by immersion in molten InSn alloy at 150 0C and bonded by reflow and a cryogenically compatible adhesive. The MSL length is 2210 µm

<!-- image -->

Figure 6.10: The upper and lower margins of the receiver bias current vs the SFQ pulse transmission rate between the flip-chip and the MCM carrier for InSn bumps. Each separate branch from left to right  corresponds  to  the  different  number  of  SFQ  pulses  circulating  in  the  ring  oscillator.  A geometric resonance in the MSL at ~ 44 GHz can be seen. InSn bumps were used in this MCM

<!-- image -->

Table 6.1: Maximum transfer for MSL length in Au bumps

Wafer KL1061, bumped by evaporated 1.8m µ Au

Table 6.2: Maximum transfer rate for MSL length in InSN bumps

| MSL Length(µm)   |   3580 |   3680 |   3760 |   3845 |   4315 |   7050 |
|------------------|--------|--------|--------|--------|--------|--------|
| max f (GHz)      |    104 |    108 |    108 |    109 |     88 |    105 |

Wafer KL1084, bumped by immersion in InSn melt

| MSL Length(µm)   |   1900 |   2210 |   2335 |   4475 |   7650 |   12895 |
|------------------|--------|--------|--------|--------|--------|---------|
| max f (GHz)      |     78 |     80 |     78 |     76 |     81 |      76 |

## 6.5 Discussion and Conclusion

We  have  developed  a  new  inter-chip  interconnect  design  and  the  wafer-level bumping process for superconductor integrated circuits, using evaporated or electroplated bumps  of  various  compositions  -  Ti/Pd/Au,  Ti/Pd/Cu/Au,  Ti/Pd//In/Au  -  in  order  to replace  the  manual  chip-level  immersion  bumping  in  molten  InSn.  A  large  number  of MCMs containing a  single  flip-chip  and  an  active  MCM  carrier  have  been  assembled using  adhesive  and  Reflow  bonding  processes.  The  maximum  chip-to-chip  SFQ  pulse transmission rates of 110 GHz was observed for the circuits fabricated by HYPRES 4.5 kA/cm2 process and using evaporated Ti/Pd/Au bumps of 1.8 µ m height. By testing the SFQ  pulse  transmission  on-chip  and  chip-to-chip,  it  was  found  that  the  maximum transmission frequency through the bumps is not limited by the employed interconnect design or the bump metallurgy but by the maximum speed of the test circuitry. Therefore, the developed design and the whole wafer bumping technology should be well suited for the future higher c j -  fabrication processes providing yet higher operating frequencies of superconductor integrated circuits.

## Chapter 7

## Design of the Multi-modulator ADC Architecture

## 7.1 Introduction

In  this  chapter, the  design  of  a  high  sensitivity  ADC  by  implementing  a  multimodulator  architecture  is  described  -  with  subsequent  modulators  sampling  the  time delayed  version  of  the  input  signal.  Superconducting  Phase  modulation  demodulation (PMD) ADCs [78], have been successfully demonstrated to operate at 20GHz [11]. In this chapter, the design steps in the development of the multi-modulator front end will be described without going to complete detail on the study of superconducting PMD ADCs. The design and simulation results are included of the multi-modulator; LC low pass filter and Transformer here.

As  the  input  signal  applied  to  each  modulator  is  correlated,  the  noise  for  each modulator  is  uncorrelated.  Consequently,  averaging  outputs  from  multiple  modulators effectively reduces the noise floor by the square root of the number of modulators used. The  signal  is  coupled  to  each  of  the  modulators  by  connecting  the  primaries  of  the transformers in series. Each transformer is designed as an LC transmission line, with the impedance  matched  to  the  load  impedance.  An  LC  low  pass  filter  (1GHz  cutoff frequency)  is  also  used  before  each  modulator  to  remove  the  high  frequency  noise components

## 7.2 Behavioral System Simulation of Multi-modulator ADC

A  Simulink  model,  as  shown  in  figure  7.1,  of  the  multi-modulator  ADC architecture at behavioral level was constructed, to examine the properties of the system. With a system level simulation it was shown that a 3 db dynamic range improvement was

achieved  for  every  doubling  of  the  number  of  modulators.  In  Simulink  simulations,  an LC  transmission  line  model  was  not  included  and  the  signals  to  all  comparators  are applied  simultaneously.  In  the implementation  of  ADC,  the  input  signal  to  each subsequent modulator is delayed by the LC transmission line and a delay compensation mechanism  is  required  before  the  outputs  of  the  modulators  are  added  in  a  parallel counter.  The  thermal  noise  for  each  comparator  is  modeled  by  adding  a  white  noise source with different seed. The outputs from the four modulators are added in a parallel counter and the data is further processed by the digital decimation filter.

Figure 7.1: A simulink model for a  4-modulator PMD ADC

<!-- image -->

Figure 7.2 shows the spectrum for the 1, 2, 4 and 8 modulators. A -3dBFs, 10 MHz sine wave  is  applied  as  the  input.  The  sampling  frequency  is  20.48  GHz,  and  the  SNR  is measured in 19.34 MHz bandwidth. The bandwidth was chosen, so as to not include the

second harmonic. The simulation results show a 3 dB dynamic range improvement for every doubling of the modulators.

Figure 7.2: Spectrum for 1,2,4,8 modulator PMD ADC

<!-- image -->

Figure  7.3  shows  the  improvement  of  performance  over  a  range  of  input  signal-  by plotting  SNR versus Signal power. An SNR  improvement over a range of  input signal power was observed. A 9db dynamic range improvement is obtained by using an eight Modulator ADC over a single modulator ADC.

Figure 7.3: SNR (dB) versus Signal Power (dBFs) of 1, 2, 4 and 8 Modulator ADC outputs

<!-- image -->

## 7.3 Circuit Level Design and Simulation

In  the  previous  section  we  showed,  using  behavioral  system  level  simulations,  the improvements that can be obtained using multi-modulator ADC designs. However, these simulations did  not  include  the  circuit  design  parameters,  which  crucial  in  determining the working of the ADC.

## 7.3.1 Determination of Circuit Parameters for ADC

The  multi-modulator  is  being  designed  for  cutoff  frequency  of  1GHz  low  pass  front end.  The  other  important  parameters  are  the  primary  and  secondary  inductances  of  the pick-up transformer and the Low pass filter characteristics as determined as shown

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Lower bound set by flux noise

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Higher Bound set by β L~ 2 π which implies Lsecondary * Ic = Φ 0 (Ic =120uA), Lsec = 17 pH

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

With  number  of  synchronization  channels  m=1,  Q  =  number  of  independent modulators (assume Q = 4), N = Decimation factor (assume N = 64) . For sensitivity of 90 dBm, assuming a 50 ohm load, the sensitivity in terms of current (LSB(I)) translates to 140 nA and for sampling frequency of 20GHz, we obtain M=400pH.

## 7.3.2 Transformer Design

The Transformer pick up coil was designed, is shown in figure 7.4, and was based on spiral inductors.  The  values  of  the  coil  were  estimated  using  Wheelers  formula inductance formula [2].

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

,  where Lspiral (in  nH), thickness (in µm) and Rmean (in µm) and N is the number of turns.

The  Coil  properties  were  extracted  using  SONNET,  a  3D  electromagnetic  simulator [30]. From formula 7.6, 7.7 and 7.8, Inductance of primary coil L (primary, calculated) = 17.6nH and from sonnet simulation Inductance of primary coil, L (primary, simulated) = 16.04nH. Inductance of secondary coil L (secondary, simulated) = 19.91nH, 1st resonant

frequency  from  sonnet simulation observed  at 3.1  GHz.  From  SONNET  simulation  we also obtain, the capacitance values; capacitance between coil and the ground, C=9.09pF and  capacitance  between  the  primary  and  the  secondary  coil  is  Cm=0.8pF.  The  Spice model  schematic  is  constructed,  from  the  simulations  of  the  transformer  is  shown  in figure 7.5.

Figure 7.4: The Layout of the transformer coil. The Number of turns N=12, with primary inductance Lpri=27nH and secondary inductance Lsec=19nH. The inner radius, Ri= , Outer radius, Ro=, Width, W=    .  (b) the  3D  view  of  the simulated  transformer(  cell  size 2.5x2.5  um   ,  air  =250um, si\_substrate= 250um, separation from ground ring and outer coil radius 75um )

<!-- image -->

Figure  7.5:  The  schematic  developed  for  the  transformer  based  on  the  values  extracted  by  3D electromagnetic simulation of the transformer.

<!-- image -->

## 7.3.3 LC Low Pass Filter Design

A low pass 5thorder Butterworth filter was designed with a cutoff frequency of 1GHz. The design characteristics of the filter are displayed along with its schematic in figure 7.6 and figure 7.7.

Figure 7.6:  schematic of the filter, R1=R2=50 ohm,  C1=C2=5.15pF, L1=L3=4.92nH, L2=15.9nH

<!-- image -->

Figure 7.7: The Amplitude (normalized) and Phase characteristics of the 5th order Butterworth filter

<!-- image -->

The  inductor,  for  the  LC  filter  (shown  in  figure  7.8a),  must  be  based  on  the  spiral inductor, as it is quite large compared to other RSFQ circuit elements. The spiral inductor designs,  properties  extracted  using  SONNET  simulations  (shown  in  figure  7.8b)  and theoretical calculations based on eqs.7.6,7.7.,7.8, are compared and results are shown in table 7.1.

Table 7.1: Inductance values of the spiral inductor coil for LC filter

| Coil structure (Spiral type, layer, turns, inductor type)   | Inductance ( calculated)   | Inductance ( simulated)   |
|-------------------------------------------------------------|----------------------------|---------------------------|
| (Single l, M2, 6,L3/L1)                                     | 6.3 nH                     | 6.34nH                    |
| (Single l, M3, 6,L3/L1)                                     | 6.3nH                      | 6.48nH                    |
| (bilayer ,M2 M3,12,L2)                                      | 25.2nH                     | 23.1nH                    |

Figure 7.8: The bilayer spiral is shown above, with N=12 turns. The spiral inductor is constructed with N=6, in M2 and M3 layers. The 3D view of the bilayer spiral is shown above, with N=12 turns. The  spiral  inductor  is  constructed  with  N=6,  in  M2  and  M3  layers.  (  cell  size 2.5x2.5  um   ,  air =250um, si\_substrate= 250um, separation from ground ring and outer coil radius 75um )

<!-- image -->

The  Complete  layout  for  the  low  pass  LC  filter  is  shown  in  figure  7.9.  The  Large capacitors are constructed between M2 layers and the ground layer M0, occupy an area of 340 µ m 2 each.

Figure 7.9: The Complete Layout  of the 5 th order  Butterworth Low Pass filter is shown. The two capacitor are constructed between M2 and the ground layer M0

<!-- image -->

## 7.4: PSCAN Simulation of the 4-modulator ADC

We have performed circuit  level  simulation  of  the  multi-modulator  architecture (including the schematic models of the LC filter and pickup transformer) using PSCAN [37]. The complete schematic for the 4-modulator ADC is shown in figure 7.10. For the design specifications, the  inter-modulator delay is of the orders of a few clock periods. Additional  active  transmission  lines  may  be  used  for  finer  delay  compensation.  This variable  delay  capability  also  helps  to  compensate  inter-modulator  delay  due  to  LC device mismatch.

Figure7.10: schematic of the 4 multi-modulator PSCAN simulations

<!-- image -->

The current through the primary of individual modulators are plotted to show the intermodulator delay (figure 7.11). The differentiated outputs at the end of each modulator are shown in figure 7.12.

Figure 7.11: The inter modulator delay

<!-- image -->

Figure 7.12: The operation of the front end of the multi-modulator ADC, the differetial output pulses are shown.

<!-- image -->

Figure 7.13: The complete layout constructed for the 2 -modulator design

<!-- image -->

## 7.5 Discussion and Future work

The multi-modulator design approach has been presented with its advantages over existing superconducting modulators. The current project of Multi-modulator ADC is still in progress. The design layout for 2-modulator ADC is shown in figure 7.13, due to the space  constraints  only  a  2-modulator  ADC  could  be  designed  in  a  5x5mm  chip.  The future designs of the layout will include a 4-modulator design and also include a low pass multi-modulator for cutoff frequency of 100MHz front end.

## Chapter 8

## Conclusion and Future Work

## 8.1 Conclusion

In this thesis, the large scale integration issues of digital superconducting circuits have been presented.

## 8.1.1 Flux Trapping:

-A  complete  theoretical  foundation  has  been  revisited  for  analyzing  parasitic  flux trapping in superconducting circuit. Also, the impact of flux trapping on the operation of

superconducting circuits was studied, using SONNET and PSCAN simulators.

-A  complete  experimental  methodology,  with  3D  magnetic  field  control,  has  been developed  for  investigating  parasitic  flux  trapping  in  superconducting  circuits,  for

quantitative analysis, in both cryo-coolers and Helium Dewars. Superconducting IC's of shift registers of 16bit and 6bit were designed and fabricated for investigating parasitic

flux trapping.

-A new set of moat protocols were also studied for parasitic flux trapping to determine the  best  layout  configuration.  The  most  resistant  moat  configuration  has  been  able  to

prevent flux trapping upto 20mG, which is comparable to Earth's magnetic field.

-Flux trapping studies were also carried out on the power independent circuits, a  logic family for low power circuits.

## 8.1.2 Power Independent Circuits

-A  new concept of  low power superconducting circuits, power independent RSFQ cell was  introduced,  to  eliminate  static  power  dissipate  in  logic  gates.  The  circuit  was

incorporated  into  shift  register  design,  fabricated  and  experimentally  tested  with  ±20% margins.

## 8.1.3 Current Biasing

- -Demonstration of current recycling for nearly 1k Josephson junction superconducting IC with  over  1000  junctions  and  fabricated  in  1KA/cm 2 technology  is  presented.  A  bias current reduction of 1/N was achieved, where N is the number blocks biased serially.
- -Development  and  analysis  of  summing  array  amplifiers,  for  high  frequency  output drivers, based on current recycling technique is presented. The output drivers, constructed by parallel (4 blocks) and serial ( 20 blocks) connections were able to obtain upto 0.4mv and 2mV output voltage respectively, with ±15 operating margins.
- -The effect of magnetic field on current recycling circuit margins has also been reported. Some  of  the  circuits  have  exhibited  asymmetric  operating  margins  for  the  magnetic scans.

## 8.1.4 Multichip Modules

-We have developed a new inter-chip interconnect design and the wafer-level bumping process for superconductor integrated circuits, using evaporated or electroplated bumps of various compositions - Ti/Pd/Au, Ti/Pd/Cu/Au, Ti/Pd//In/Au - in order to replace the manual chip-level immersion bumping in molten InSn.

- -The maximum chip-to-chip SFQ pulse transmission rates of 110 GHz was observed for the circuits fabricated by HYPRES 4.5 kA/cm2 process and using evaporated Ti/Pd/Au bumps of 1.8 µ m height.

## 8.2Future Work

## 8.2.1 Flux Trapping:

- -To  study and  determine  the  threshold fields for the layout configuration  under temperature gradient during the cooling transition through the critical temperature, which can have an effect on the parasitic flux trapping.
- -To design circuits resistant to flux trapping by changing the transaction temperatures of all or selected individual metallic layers. The idea is to provide magnetic shielding to the next layer as the circuit is being cooled.

## 8.2.2  Low Power RSFQ - Power Independent Circuit:

- -To design power independent circuits with a memory element- single junction SQUIDwith lower coil inductances.
- -To design power independent circuits with higher resistance to parasitic flux trapping, by enclosing the entire circuit or part of the circuit in a superconducting shield.
- -To design new circuits, such as programmable frequency divider, to study the high speed operating limits of the power independent circuits.

## 8.2.3 Current Biasing in RSFQ Circuits:

- -The current recycling circuits face limits on the scalability due to high transients in the coupling  circuits.  These  transients  can  be  eliminated  with  better  design  of  coupling circuits and incorporating filters for the purpose which are currently under development.
- -Enclosing  part  of  the  circuit  in  on-chip  superconducting  shields  to  make  them  more resistant to external magnetic fields.

## 8.2.3  Multi-chip Modules

- -To investigate the physical properties of the bumps, such as the cutoff frequency of the bumps,  the  resistance  of  the  bumps.  Also  alternative  methods  of  deposition  of  solder bumps and gold stud bumps that will guarantee better uniformity are been investigated.

-New designs must be developed to study the nature of transfer of pulses between two chips, if the bumps are of capacitive nature or inductive nature.

## 8.2.4 Multi-Modulator ADC

-The 4, 8-modulator ADC is  yet to be designed. A  multi-chip  module  for constructing multi-modulator ADC is a viable solution.

## REFERENCES

- [1] M. Tinkham,' Introduction to superconductivity', 2 nd Edition, Dover publications, 1996.
- [2] C.  W. Turner and T. Van Duzer, 'Princples  of Superconducting  devices and circuits',  2 nd Edition, Preintice Hall publications, 1999.
- [3] Alan  M.  Kadin,'  Introduction  to  Superconducting  Circuits',  Wiley-Interscience;  1  edition ,March 11, 1999.
- [4] K.K.Likharev  ,'  Dynamics  of  Josepshon  Junctions  and  circuits,'  Gordon  and  Breach publishers , 1985.
- [5] John Clarke and Alex  I.  Braginski  (Edited),'  The  SQUID  Handbook,'  Wiley-VCH publications, 2004.
- [6] V.V Schmidth,'The Physics of Superconductors,'P. Mueller and A.V. Ustinov, Eds. Berlin, Germany: Springer-Verlag, 1997.
- [7] Alexander.  V.  Rylyakov,'  Ultra-low-power  RSFQ  Devices  and  digial  autocorrelation  of Broadband Signals', Ph.D. Dissertation, SUNY Stony Brook, May 1997.
- [8] K.K.  Likharev  and  V.K.  Semenov,'  RSFQ  Logic/Memory  Family:  A  new  JosephsonJunction Technology for sub-Terahertz-clock-frequency digital systems,' IEEE Trans. Appl. Supercond. , Vol 1,No. 1, March 1991.
- [9] K.K.Likharev ,O.A. Mukhanov and V.K. Semenov,' Resistave single flux quantum logic for Josepshon-junction technology,' SQUID 85, Berlin ,Germany 1985.
- [10]  'Superconducting  Technology  Assessment',Report  of  national  security  agency  ,office  of corportate assessments,August 2005.
- [11]  O. A. Mukhanov, D. Gupta, A. M. Kadin, and V. K. Semenov, 'Superconductor Analog-toDigital Converters," Proceedings IEEE , vol. 92, no. 10., pp. 1564-1584, Oct. 2004.
- [12]  M.A, Nielsen and I.L. Chuang,'Quantum Computation and Quantum Information',Cambridge University Press, Cambridge,2000.
- [13]  D.K. Brock,E.K. Track and J.M. Rowell,'Supercondutor ICs:The 100-GHz second generation,' IEEE Spectrum, vol 37,Dec 2000,pp 40-46.
- [14]  S.R.  Norsworthy,  R.  Schreier,  and  G.C.  Temes,'Delta-Sigma  Data  Converters:Theory, Design and Simulation,' New York: IEEE Press 1997.
- [15]  J.F.  Bulzacchelli,'  Superconductor  Bandpass  Delta-Sigma  Modulator  for  direct  Analog-toDigital  Conversion  of  Mircowave  Radio,'Ph.D.  dissertation,  Massachusetts  Int.  Tech., Cambridge, 2003.

- [16]  T.V.Fillipov,S.V. Pflyuk,V.K.Semenov and E.B.Wikborg,' Encoders and decimation filters for superconductor oversampling ADCs ,' IEEE Trans Appl. Supercond ., vol 11, pp 545-549, Mar 2001.
- [17]  R.  Rafique,'  Superconducting  High  Speed  Passive Interconnects,' Ph.D.  dissertation, Chalmers University of Technology, Goteborg, Sweden, 2007.
- [18]  P.Bunyk, K.K. Likharev, and D. Zinoviev,' RSFQ technology: physics and deivces,' Int. J. High Speed Electron. Syst. , vol.11, pp.257-305, 2001.
- [19]  L.A. Abelson and G.L. Kerber,' Superconductor Integrated Circuit Fabrication Technology,' IEEE Proceeds., vol 92, no. 10, pp.1517-1533,Oct. 2004.
- [20]  M.A.  Washington  and  T.A.  Fulton,  'Observation  of  flux  trapping  threshold  in  narrow superconducting thin films', Appl. Phys. Lett ., vol. 40, pp. 848-50, 1 May 1982.
- [21]  S.  Bermon and T. Gheewala, 'Moat-guarder Josephson SQUIDs', IEEE Trans. On Magn . Vol. MAG-19, pp. 1160-64, May 1983.
- [22]  M.  Jeffery,  T.  Van  Duzer,  J.R.  Kirtley  and  M.B.  Ketchen,  'Magnentic  imaging  of  moatguarded superconducting electronic circuits', Appl. Phys. Lett . Vol. 67, pp. 18-21, Sep. 1995.
- [23]  G Stan,  S.B.  Field  and  J.M.  Martinis,  '  Critical  filed  for  complete  vortex  expulsion  from narrow superconducting strips', Phys. Rev. Lett . 92, 097003, pp. 1-4, Mar. 2004.
- [24]  I.L. Maksimov and G.M. Maksimova, 'Stability limits, structure and relaxation of a mixed state in superconducting films with a edge barrier', JETP Letters , pp. 423-429, Mar. 1997.
- [25]  D. Kouzoudis,  M.  Breitwisch  and  D.K.    Finnemore,  '  Edge  barrier pinning for a superconducting vortex', Phys. Rev. B , vol. 60, pp. 10508-12, Oct. 1999.
- [26]  C.P. Bean and J.D. Livingston,' Surface barrier in Type II superconductors', Phys. Rev. Lett ., vol 12, pp. 14-16, Jan. 1964.
- [27]  M.M.  Khapaev,  "Extraction  of  inductances  of  plane  thin  film  superconducting  circuits", Supercond. Sci. Technol ., 1997, vol. 10, pp. 389-394.
- [28]  M. M.  Khapaev, A.Yu. Kidiyarova-Shevchenko, P. Magnelind, and M. Yu. Kupriyanov, ' 3D-MLSI:  Software  package  for  inductance  calculation  in  multilayer  superconducting integerated circuits', IEEE Trans. on Applied Supercond. , vol. 11, pp. 1090-93, Jan. 2001.
- [29]  J.M. Jaycox and M.B. Ketchen, 'Planar coupling scheme for ultra-low noise DC SQUIDS', IEEE Trans. Appl. Magn ., vol 17, pp 400-403, Jan 1981.
- [30]  High Frequency Electromagnetic Software SONNET, Web page:  www.sonnetsoftware.com

- [31]  A.A.Golubov and M.Yu. Kupriyanov, 'Effect of solitary Abrikosov vortices on the properties of Josephson tunnel junctions', Sov. Phys. JETP vol. 65, pp. 849-55, Apr. 1987.
- [32]  V.K. Semenov, Yu.A. Polyakov, and W. Chao, 'Extraction of impacts of fabrication spread and  thermal  noise  on  operation  of  superconducting  digital  circuits', IEEE  Trans.  Applied Supercond. , vol. 9,pp. 4030-33,  Jun. 1999.
- [33]  D.  Zinoviev  and  Y.  Polyakov,  '  Octopux:  an  advanced  automated  setup  for  testing superconductor circuits', New York State Workshop on Academic Electronics, 1996.
- [34]  K. Tanaka, T. Morooka, A. Odawara, Y. Mawatari, S. Nakayama, A. Nagata, M. Ikeda, K. Chinone and M. Koyanagi, 'Study of trapped flux in superconducting thin film - observation by scanning SQUID microscope and simulation,' IEEE Trans. on Applied Supercond. , vol. 11,  pp. 230-34, Jun. 2001.
- [35]  K.  Suzuki,  H.  Kawamura,  M.  Maruyama, T.  Hato,  H.  Suzuki,  S.  Yorozu,  Y.  Kameda,  Y. Ishimaru, K. Nakayama, H. Wakana, S. Adachi, Y. Tarutani and K. Tanabe, 'Investigation of the flux state in single-flux-quantum circuits  with  moats by scanning SQUID  microscope', Superconductor Science and Technology , vol. 19, pp. 316-19, Mar. 2006.
- [36]  K. Suzuki, H. Suzuki, S. Adachi, T.Utagawa, U. Kawabe and K. Tanabe, 'Magnetic imaging of  high -Tc films with moat patterns by scanning SQUID microscope', Phyica C ,  pp. 130105, Sep. 2002.
- [37]  S. Polonsky,  V. Semenov,  and  P. Shevchenko.  'PSCAN:  Personal  superconductor  circuit analyzer,' Supercond. Sci. Technol. , vol. 4, pp 667-670, Nov. 1991.
- [38]  K. Tanaka, T. Morooka, A. Odawara, K. Chinone and Y. Mawatari , 'Optimized positions of Josephson  Junctions  to  prevent  trapping  of  magentic  fluxes  in  cooling  under  the  static environment', Physica C , vol. 402, pp. 371-380, Mar. 2004.
- [39]  S. L. Miller,  K.R.  Biagi,  J.  R. Clem,  and  D.K.  Finnemore,  'Critical  currents  of  cross-type superconducting-normal-superconducting junctions in perpendicular magnetic fields', Phys. Rev. B , 31.2684,pp. 2684-2695, Mar. 1985.
- [40]  P.I. Bunyk, S.V. Rylov, "Automated Calculation of Mutual Inductance matrices of multilayer superconductor integrated circuits," Ext. Abs. ISEC'93 , p.62, 1993
- [41]  V.K.  Semenov,  G.  Danilov  and  D.V.  Averin,  'Reversible  superconducting  circuits  using nSQUIDs ', IEEE Transactions Appl Supercond ., vol 17, no.2,  Jun 2007.
- [42]  H.Terai, M. Tanaka, Y. Yamanashi, Y.  Hashimoto, A. Fujimaki, N. Yoshikawa,  Z.  Wang, 'Diagnostic Test of Large-Scale SFQ Shift Register,' IEEE Trans. Appl. Supercond., vol. 17, no. 2, pp. 422-425, Jun 2007.

- [43]  V.K. Semenov and J. Ren, 'Stimulus and Read-Out Interfaces for nSQUID arrays',Extended abstract ISEC 2007 ,Report P-U07.
- [44]  Yu.A.  Polyakov,  S.  Narayana  and  V.K.  Semenov,  "Flux  trapping  in  superconducting circuits,' IEEE Trans. Appl. Supercond., vol. 17,no 2,pp.520-525, Jun 2007.
- [45]  Supradeep Narayana, Yu. A. Polyakov and V. K. Semenov,'Evaluation of Flux Trapping in Superconducting Circuits,' IEEE Trans. Appl. Supercond., vol. 19,no 3,pp.640-643, Jun 2009.
- [46]  S.K.Tolpygo,  D.  Tolpygo,  R.T.  Hunt,  S.  Narayana,  Yu.  A.  Polyakov  and  V.K.Semenov,' Wafer Bumping Process and Inter-Chip Connections for Ultra-High Data Transfer Rates in Multi-Chip Modules With Supercondutor Integrated Circuits,' IEEE Trans. Appl. Supercond., vol. 19,no 3,pp.598-603, Jun 2009.
- [47]  S.  Narayana,  Yu.  A.  Polyakov,  V.K.  Semenov,  S.K.  Tolpygo  and  R.T.  Hunt,'  Design  of Wafer-Bumps for  Multi-Chip  Modules  with  Ultra-High  Data  Transfer  Rates,'International supercondting electronics conference , Japan 2009.
- [48]  Supradeep Narayana and V.K. Semenov, 'Comparison of flux trapping in power independent and RSFQ D flip-flops,' 15 th US Workshop in Superconducting devices and circuits, 2008.
- [49]  S.  Narayana,  V.K.  Semenov  and  D.  Averin,  'Power  Minimization  Techniques  in  RSFQ Circuits,' manuscript under preparation.
- [50]  S.  Narayana  and  V.K.  Semenov  ,  'Power  Independent  RSFQ  Circuits  ',Extended  abstract ISEC 2007 ,Report P-U01.
- [51]  H. Terai,S. Yorozu,A. Fujimaki,N. Yoshikawa and Z. Wang,'Signal Intergrity in large-scale single-flux-qunatum  circuit',physica  c:superconductivity,vol  445-448,Oct  2006,pp  10031007.
- [52]  K.Suzuki , S. Yorozu,Y, Kameda and K. Tanabe,'Ivestigation of magnetic flux state in Nb SFQ circuits by scanning SQUID microscope', physica c:superconductivity,vol 445-448,Oct 2006,pp 1034-1036.
- [53]  M.Dorojovets and P.Bunky,'Architectural and implemenation chanlleges in designing highperfomance  RSFQ  processors:A  Flux-1  microprocessor  and  beyond,' IEEE  Trans.  Appl. Supercond. ,vol 13,No 2, Jun 2003,pp 446-449.
- [54]  P.Bunyk , M.Leung, and M.Dorojovets,'Flux-1 RSFQ microprocessor: Physical design and test results,' IEEE Trans. Appl. Supercond. ,vol. 13,No 2 , Jun 2003,pp 433-436.
- [55]  Q.Herr,M.wire and A. Simth,'High speed data link between digital superconductor chips,' Appl. Phys. Lett . Vol.80.pp 3210-3212,Apr 2002.

- [56]  M.W Johnson,Q.P. Herr,D.J. Durand and L.A. Abelson,'Differential SFQ transmission using Either  inductive  or  capacitive  coupling,' IEEE Trans. Appl. Supercond. ,  Vol  13,No  2,Jun 2005.
- [57]  C.K.  Teh, Y.  Enomoto  and  Y.  Okabe,'Current  recycling  technique  using  capacitive grounding,' Supercond. Sci. Technol. , vol.16.2003,pp 1513-1517.
- [58]  J.H. Kang and S.B. Kaplan,'Current recycling and SFQ signal transfer in Large scale RSFQ circuits,' IEEE Trans. Appl. Supercond. ,vol. 13,No. 2, Jun 2003,pp 547-551.
- [59]  J.H.  Kang  ,  D  Gupta  and  S.B.  Kaplan,'Demonstration  of  RSFQ  digitizer  on  a  mutichip module,' IEEE Trans. Appl. Supercond. ,vol. 12,No.3, Sep 2002,pp 1848-1852.
- [60]  W.Chen,A.V.Rylyakov,V.Patel,J.E. Lukens and K.K. Likharev,'Rapid single flux  quantum T-flipflop  operating  up  to  770  GHz,' IEEE  Trans.  Appl.  Supercond. ,vol.  19,No.1,Jun 1999,pp 3212-3215.
- [61]  S.  Tahara,S.Yorozu,Y.  Kameda,Y.  Hashimoto,H.Numata,T.  Satoh,W.  Hattori,  and  M. Hidaka,'Superconducting  digital  electronics,' IEEE  Trans.  Appl.  Supercond. ,vol.  11,Mar 2004,pp 463-468.
- [62]  O. Mukhanov, A. Inamdar, T. Filippov, A. Sahu, S. Sarwana, and V.K. Semenov,'Superconductor  components  for  direct  digital  synthesizer,' IEEE  Trans.  Appl. Supercond. ,2007
- [63]  D. Gupta, T.V. Filippov, A.F. Kirichenko, D.E. Kirichenko, I.V. Vernik, A. Sahu, S.Sarwana, P. Shevchenko, A. Talalaevskii, and O. A. Mukhanov,' Digital Channelizing radio frequency receiver', IEEE Trans. Appl. Supercond. ,2007.
- [64]  M.R. Rafique, H. Engseth, A.Kidiyarova-Shevchenko,'Optimization of high frequency flipchip interconnects for digital superconducting circuits,' Supercond. Sci. Technol, vol. 19,March 2006,pp. 354-361.
- [65]  N.  Yoshikawa  and  Y  kato,'  Reduction  of  power  consumption  of  RSFQ  circuits  by inductance-load biasing', Superconductor Sci. Technol. ,Vol. 12,pp. 918-920,1999.
- [66]  Stats Polonsky,'Delay insensitive  RSFQ circuits  with  zero  static  power  dissipation', IEEE Trans. Appl. Supercond. , vol 9 No2, pp 3535-39, June 1999.
- [67]  A.H. Silver  and  Q.  P.  Herr,'A  New  concept  for  ultra-low  power  and  ultra-high  clock  rate circuits', IEEE Trans. Appl. Supercond. , vol 11 No1, pp 333-37, March 2001.
- [68]  M.  Tanaka,T.  Kondo,N.  Nakajima,T.Kawamoto,Y.  Yamanashi,Y.  Kamiya,A.  Akimoto,A. Fujimaki,H. Hayakawa,N. Yoshikawa,H. Terai,Y. Hashimoto, and S. Yorozu,'Demonstration

of  a  single-flux-quantum  Microprocessor  using  passive  Transmission  lines', IEEE  Trans. Appl. Supercond., vol. 15, no.2, June 2005,pp. 400-403.

- [69]  T. Ortlepp, Ariando, O. Mielke, C. J. M. Verwijs, K. F. K. Foo, H. Rogalla, F. H. Uhlmann, and  H. Hilgenkamp,'Flip-Flopping fractional flux quanta,' vol. 312,no. 5779, Science 9, Jun 2006, pp 1495-1497.
- [70]  A. Silver, P. Bunyk , A. Kleinsasser and J. Spargo,"Vision for single flux quantum very large scale integrated technology", Supercond. Sci. Techno l. Vol.19,2006 ,S307-S311.
- [71]  A.M. Kadin, R.J. Webber and S. Sarwana," Effects of superconducting return  currents on RSFQ circuit performance", IEEE Trans. Appl. Supercond. , Vol 15,No. 2,June 2005.
- [72]  K. Fujiwara, S. Nagasawa, Y. Hashimoto, M. Hidaka, N. Yoshikawa, M. Tanaka, H. Akaike, A. Fujimaki, K. Takagi, and N. Takagi,' Research on Effective Moat configuration for Nb Multi-layer  Device  Structure,' IEEE Trans  Appl.  Supercond ,  vol  19,  No.  3,  Jun  2009, pp.607-610.
- [73]  B. Ebert, T. Ortlepp and F.H. Uhlmann,'Experimental Study of the Effect of Flux Trapping on the Operation of RSFQ Circuits,' IEEE Trans Appl. Supercond .,vol 19, no 3, Jun 2009, pp.611-616.
- [74]  K. Tagaki, M. Tanaka, S. Iwasaki, R. Kasagi, I. Kataeva, S. Nagasawa, T. Satoh, H. Akaike and A. Fujimaki,' SFQ Propagation Properties in Passive Transmission Lines Based on a 10Nb-Layer Stucture,' IEEE Trans Appl. Supercond .,vol 19, no 3, Jun 2009,pp.617-620.
- [75]  O.  Mielke,  T.  Ortlepp,  B.  Dimov,  and  F.H.  Uhlmann,'Phase  Engineering  Techniques  in Superconducting Quantum Electronics, J. Phys: Conf. Ser. ,97(012196):9,2008.
- [76]  A.V.  Ustinov  and  V.K.  Kapluenko,'Rapid  Single  Flux  Quantum  Logic  using π -Shifters,' Journal of Appl. Phys ., vol. 94,no.8, pp.5405-5407,2007.
- [77]  J.B. Majer, J.R. Butcher and J.E. Mooij,'Simple Phase Bias for Superconducting Circuits,' Appl. Phy. Lett., vol. 80, no. 19,pp. 3638-3648,2002.
- [78]  S.V. Rylov and R.P. Robertazzi,'Supercondutive high -resolution A/D converter with phase modulation and multi-channel timing arbitration ,' IEEE Trans Appl. Supercond ., vol. 5, pp. 2260-2263,1995.
- [79]  V.K. Semenov and A. Inamdar,' Limitations on Performance of Superconductor Oversampling ADCs ,' IEEE Trans. Appl. Supercond ., vol.15, no.2, Jun 2005.

- [80]  I.V.  Vernik,  D.E.  Kirichenko,  T.V.  Filippov,  A.  Talalaevskii,  A.  Sahu,  A.  Inamdar,  A.F. Kirichenko,  D.Gupta,  and  O.A.  Mukhanov,' Superconducting  High-Resolution  Low-Pass Analog-to-Digital Converters', IEEE Trans. Appl. Supercond. ,2007.
- [81]  F. Chiarello, P. Carelli, M.G. Castellano, C. Cosmelli, M.I. Khabipov, R. Leoni, G. Torrioli, A.B. Zorin, "Tunable flux qubits controlled by rapid single flux quantum logic: considerations  and  perspectives",  Extended  Abstracts,  10th  International  Superconductive Electronics Conference, ISEC 2005, P-C.04, Noordwijkerhout, NL, 2005.
- [82]  HYPRES Nb Process Design Rules (30-1000-4500 A/cm2), Process #03- 10-45. HYPRES, Inc., Elmsford, NY 10523.Available: http://www.hypres.com/pages/download/designrules/DesignRules.pdf
- [83]  S. K. Tolpygo, D. Yohannes, R.T. Hunt, J.A. Vivalda, D. Donnelly, D. Amparo, and A.F. Kirichenko, '20 kA/cm2 process development for superconductor integrated circuits with 80 GHz clock frequency,' IEEE Trans. Appl. Supercond ., vol. 17, pp. 946-951, June 2007.
- [84]  M. Hidaka, S. Nagasawa, K. Hinode, and T. Satoh, 'Improvements in fabrication process for Nb-based  single  flux  quantum  circuits  in  Japan,' IEICE  Trans.  Electron .,  vol.  E91-C,  pp. 318-324, Mar. 2008
- [85]  K.E. Yokoyama, G. Akerling, A.D. Smith, and M. Wire, 'Robust  superconducting die attach process,' IEEE Trans. Appl. Supercond. , vol. 7, pp. 2631-2634, June 1997.
- [86]  Y.  Hashimoto,  S.  Yorozu,  and  T.  Miyazaki,  'Transmission  of  singleflux-quantum  pulse between superconductor chips,' Appl.  Phys.  Lett .,  vol.  86,  pp.  072502-1  -  072502-3,  Feb. 2005
- [87]  Y.  Hashimoto,  S.  Yorozy,  T.  Satoh  and  T.  Miyazaki,  'Demonstration  of  chip-to-chip transmission  of  single-flux-quantum  pulses  at  throughputs  beyond  100  Gbps,' Appl.  Phys. Lett ., vol. 87, pp. 022502-022504, July 2005.
- [88]  Y.  Hashimoto,  S.  Yorozu,  and  Y.  Kameda,  'Development  of  cryopackaging  and  I/O technologies for high-speed superconductive digital systems ,' IEICE Trans. Electron .,  vol. E91-C, pp. 325-332, Mar.2008.
- [89]  S.  B.  Kaplan,  V.  Dotsenko,  and  D.  Tolpygo,  'High-speed  experimental  results  for  an adhesive-bonded superconducting  multi-chip  module,' IEEE Trans. Appl. Supercond., vol. 17, pp. 971-974, June 2007.
- [90]  S.V.  Polonsky,  V.K.  Semenov,  and  D.F.  Schneider  'Transmission  of  single-flux-quantum pulses  along  superconducting  microstrip  lines,' IEEE Trans. Appl. Supercond .,  vol.  3,  pp. 2598-2600, Mar. 1993.

## Appendix I

A compilation of some of the RSFQ cells and gates have been described which are used in the design of circuits, presented in chapters 2-7.

## A1.1 Splitter

SFQ pulses can  be replicated with JTL's having  two outputs. A single  junction cannot  drive  more  than  two  outputs.  A  tree  of  splitters  is  used  to  build  large  fanout circuits.

Figure A1.1: RSFQ splitter

<!-- image -->

## A1.2 Confluence Buffer

If  two pulses  have to be  merged a confluence buffer is used. Two buffer stages (comparators without quantizing inductance form buffers) constitute the CB as shown in figure A1.2. An SFQ pulse from in1 enter through J1 and leaves J5 , buffer junction J4 makes a 2 π phase jump preventing J2 from sending a pulse to in2 , a backward moving pulse. The arrival of two pulse will result in only one outgoing SFQ pulse (one pulse is rejected and only one is transmitted).

## A1.3 D Flip-flop

The clocked version of the RS flip-flop and the basic design is shown in figure A1.3. The clock is used as a reset for the RS flip-flop. The two states are 1 and '0' when a  flux  quantum  is  stored or  not  stored  in  J1-L1-J2  loop. Inductance  L1  is  a  quantizing inductance and an SFQ pulse arrives at the junction J1 waits for the clock signal to be released by J2. The junction J0 is optional and acts as a buffer in case two signals arrive

before the reset signal. Without junction J0, D flip-flop is just a direct combination of a JTL and a controlled two junction comparator.  The D flip-flop is used for construction of the  shift  registers  used  for  flux  trapping  studies.  More  details  will  be  illustrated  in  the following chapters.

FigureA1.2: RSFQ Confluence buffer

<!-- image -->

Figure A1.3:  RSFQ D flip-flop

<!-- image -->

## A1.4 Superconducting Microstrip lines (SMSL)

An SFQ pulse can be interpreted as a superposition of microwaves. SMSLs need two metal  layers:  one  for  signal  line  and  another  for  ground.  SMSL  introduces  certain dispersion  properties  at  high  frequency  where  effective  dielectric  constant  increases. However,  in  the  present  processes,  the  thickness  of  dielectric  layer  is  very  small.  So dispersion in SMSL is negligible for wide bandwidth. In the current process, the SMSL are low ohmic ( &lt; 50 Ω ). The implementation of high ohmic SMSLs is limited by Design Rules.

## A1.5 SMSL Driver

The  function  of  the  driver  is  to  send  a  single  SFQ  pulse  at  a  time  through  the connected SMSL. The resistance of SFQ driver  (0.25-05 ohm)  is used to decrease the quality factor of the resonator formed by the SMSL and thus to absorb all the traveling reflected  signal  generated  at  the  receiver  and  impedance  discontinuities.  The  Junction, JD, is designed with critical current slightly higher than that of JTL to compensate energy losses in the link due to series resistor and different impedance discontinuities.

Figure A1.4:  RSFQ SMSL driver

<!-- image -->

## A1.6 SMSL Receiver

The function of the receiver is a JTL with modified parameters. The critical current of the  receiving  input  junction  should  be  small  to  support  SFQ  pulses  with  very  small energy.

## A1.7 I/O interface

The interface structures for SFQ electronics that was used in the circuits were SFQ/DC converter and DC/SFQ converters.

## A1.7.1 Input:

High speed reception of input of NRZ signals can be done with the DC/SFQ converter. DC/SFQ converter generates one SFQ pulse at the rising  edge of the DC-signal  input. The  quantizing  loop  in  the  DC/SFQ  converter  is  J2-L1-J1-J3,  as  shown  in  figure A1.6a.When a sufficiently high input current is applied from the DC-source, junction J2 switches and generates an SFQ pulse to the output and an anti pulse to the quantizing loop.  The  captured  flux  in  the  quantizing  loop  reduces  the  current  through  junction  J2 below the critical current and increases the biasing of the junctions J1 and J3, junctions J1 and  J3  act  as  a  single  junction.  At  the  falling  edge  of  the  DC  signal  J1  and  J3  switch restoring the initial state of the quantizing loop. Junction J4 is used as a matching element to the other RSFQ cells.

Figure A1.5: RSFQ SMSL receiver.

<!-- image -->

Figure A1.6: (a) DC/SFQ converter (b) SFQ/DC converter

<!-- image -->

## A1.7.2 Output:

The output of the RSFQ circuit is generated by a conventional SFQ/DC converter as  shown  in  figure  A1.6b.  The  junction  J6  is  responsible  for  generation  of  the  output signal  is  embedded  into  quantizing  interferometer  J3-L4-L5-J5.  In  the  initial  state circulating  current  in  the  loop  flows  through  the  junction  J3  and  junction  J6  is  under biased  and  is  in  the  superconducting  state.  SFQ  pulse  arriving  to  the  input  induces switching of the junction J3 and changes direction of the circulating current. Parameters of the circuit adjusted than critical current and it switches to the resistive state. It remains in the resistive state until arrival of the second incoming SFQ pulse. The output voltage is fabrication process dependent and typically is in the order of a few hundreds µV.

Each input also connection to the SFQ/DC converter to monitor correctness of the input  test  pattern.  Combination  of  the  DC/SFQ  and  SFQ/DC  converters  are  the 'monitors'. The voltage bias level and the signal amplitude define the monitor operation.