<!-- image -->

## Superconductor digital electronics: Scalability and energy efficiency issues (Review Article)

Sergey K. Tolpygo

Citation: Low Temperature Physics 42 , 361 (2016); doi: 10.1063/1.4948618

View online: http://dx.doi.org/10.1063/1.4948618

View Table of Contents: http://scitation.aip.org/content/aip/journal/ltp/42/5?ver=pdfcov

Published by the AIP Publishing

## Articles you may be interested in

Ultra-low-power superconductor logic

J. Appl. Phys. 109 , 103903 (2011); 10.1063/1.3585849

Microelectronically fabricated Li Co O 2 ∕ Si O 2 /polycrystalline-silicon power cells planarized by chemical mechanical polishing

J. Vac. Sci. Technol. B

24 , 562 (2006); 10.1116/1.2167989

Single-charge devices with ultrasmall Nb ∕ Al O x ∕ Nb trilayer Josephson junctions

J. Appl. Phys. 97 , 054501 (2005); 10.1063/1.1855399

Room-temperature demonstration of low-voltage and tunable static memory based on negative differential conductance in silicon single-electron transistors

Appl. Phys. Lett. 85 , 6233 (2004); 10.1063/1.1839643

Integration issues for 850 nm optical modulators on Si electronics by direct epitaxy

J. Vac. Sci. Technol. B 15 , 886 (1997); 10.1116/1.589503

<!-- image -->

10 mK to 800 K

LHe/LN2 Cryostats

Cryocoolers

Magnet Systems

DilutionRefrigeratorSystems

Micro-manipulatedProbeStations

sales@janis.com www.janis.com Click to view our product web page.

<!-- image -->

## Superconductor digital electronics: Scalability and energy efficiency issues (Review Article)

Sergey K. Tolpygo a)

Lincoln Laboratory, Massachusetts Institute of Technology, Lexington, Massachusetts 02420, USA (Submitted February 10, 2016)

Fiz. Nizk. Temp. 42 , 463-485 (May 2016)

Superconductor digital electronics using Josephson junctions as ultrafast switches and magneticflux encoding of information was proposed over 30 years ago as a sub-terahertz clock frequency alternative to semiconductor electronics based on complementary metal-oxide-semiconductor (CMOS) transistors. Recently, interest in developing superconductor electronics has been renewed due to a search for energy saving solutions in applications related to high-performance computing. The current state of superconductor electronics and fabrication processes are reviewed in order to evaluate whether this electronics is scalable to a very large scale integration (VLSI) required to achieve computation complexities comparable to CMOS processors. A fully planarized process at MIT Lincoln Laboratory, perhaps the most advanced process developed so far for superconductor electronics, is used as an example. The process has nine superconducting layers: eight Nb wiring layers with the minimum feature size of 350 nm, and a thin superconducting layer for making compact high-kinetic-inductance bias inductors. All circuit layers are fully planarized using chemical mechanical planarization (CMP) of SiO2 interlayer dielectric. The physical limitations imposed on the circuit density by Josephson junctions, circuit inductors, shunt and bias resistors, etc., are discussed. Energy dissipation in superconducting circuits is also reviewed in order to estimate whether this technology, which requires cryogenic refrigeration, can be energy efficient. Fabrication process development required for increasing the density of superconductor digital circuits by a factor of ten and achieving densities above 10 7 Josephson junctions per cm 2 is described. Published by AIP Publishing. [http://dx.doi.org/10.1063/1.4948618]

## 1. Introduction

May 3, 2016 is the 100th anniversary of birth of Kirill Borisovich Tolpygo, a prominent theoretical physicist widely recognized for his contributions to condensed matter physics, crystal lattice dynamics, physics of semiconductors and dielectrics, and also biophysics. 1-5 Among his many works on application of mathematical and quantummechanical methods to biological systems, a significant part was devoted to developing an understanding of the mechanisms of high-energy efficiency of living organisms, in particular the mechanisms of chemical energy conversion into mechanical energy in muscles and muscle contraction. In 1978 Tolpygo proposed a mechanism of muscle contraction that results from a sequential transfer of proton excitation, a proton exciton, along a chain of hydrogen bonds between two biopolymers, an actin-myosin pair. 6,7 A pulling force is produced due to lowering the excited proton energy and shortening the bond length. 8 The initial excitation is provided by hydrolysis of an adenosine-triphosphate (ATP) molecule. A high-energy efficiency of muscle contraction is explained in this model as due to energy recycling-the energy remaining in a hydrogen bond after a microscopic displacement of the polymers is transferred to a neighboring bond along the chain, and so on. 9 The original model was further developed by Tolpygo and his collaborators in a series of work; see Refs. 10-12 and references therein. It is likely that the idea of nearly complete energy recycling in muscles of living organisms can also be applied to explaining a high-energy efficiency of information processing by a human brain, the most energy efficient computer created so far.

The energy efficiency of electronics, in particular computers, has become a very important problem due to an exponential growth of energy consumption by computational and internet-related systems: supercomputers, data centers, personal computers, etc., which is expected to reach /C24 15% of the total energy consumption in the world in the very near future. Any increase in energy efficiency of electronic systems, or of any area of human activity, would provide tremendous economic and environmental benefits by reducing global warming, achieving sustainable economic development, and protecting the environment. All these topics were of great interest and importance to Tolpygo, who lectured and published on them profoundly in the later part of his life.

Conventional digital electronics is based on complementary metal-oxide-semiconductor (CMOS) transistor technology where information is encoded by the voltage state of a field effect transistor (FET). The energy dissipation is caused by charging and discharging of the circuit interconnects and gate capacitors of FETs and the gate current leakage in the 'OFF' state of transistors. The charging energy is not recycled. Since the invention of the first integrated circuits in the 1960s, semiconductor digital electronics has demonstrated a nearly exponential growth of the integration scale and circuit complexity. The number of transistors per chip has grown by more than eight orders of magnitude, reaching over 1 /C2 10 9 (1B) in modern processors and over 20B in field programmable gate arrays (FPGA). At the same time the size of transistors, their gate length, has shrunk from tens

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

of microns down to 14 nm and continues to decrease. Although the gate length has been approaching the physical limits, there is little doubt that semiconductor industry will continue to pack more transistors per chip by using threedimensional (3D) integration and other approaches for at least another decade. The progress comes at a higher and higher cost, and the main hurdle is energy dissipation. It has reached /C24 100 W/cm 2 , a factor of 10 /C2 higher than the heat density of electric hot plates and induction burners, and a factor of 1000 /C2 higher than the solar energy density. Energy dissipation limits the clock frequency of processors to /C24 4 GHz and determines the amount of the so-called 'dead silicon,' transistors which are not powered at any given time in order to prevent the chip temperature from exceeding the thermal limit.

In the area of high-performance computing, the main interest is in advancing supercomputers from the current PFLOPS-scale (10 15 FLOPS, Floating-Point Operations per Second) to exascale computing, corresponding to 10 18 FLOPS and beyond. 13 A survey of the top 10 supercomputers 14,15 gives their power consumption in 2015 at /C24 0.1 GW, with the most powerful supercomputer in 2015, Chinese Tianhe-2 (33.9 PFLOPS), consuming about 17.8 MW for operation and another 6.4 MW for cooling. A linear projection from this performance to a 1 EFLOPS (1000 PFLOPS) supercomputer using the same technology gives about 800 MW consumption, the output of an average utility power plant. Current efforts in energy-efficiency improvements of supercomputers target a reduction of this figure to about 20 MW by about 2020. 16

Superconductor electronics (SCE) utilizing Josephson junctions (JJs) as switching devices was historically considered for applications in high-performance computing mainly due to a potential for much higher clock rates (up to a factor of 50 /C2 higher) than those offered by the CMOS technology at that time. 17 Recently, superconductor digital electronics has been re-evaluated as having a potential for energyefficient computing, and energy consumption budgets and other technology requirements have been formulated. 16 A major research program, Cryogenic Computing Complexity (C3), was started in the US in August 2014 in order to develop the technology and demonstrate a prototype of a complete superconducting computer with 10-GHz target clock frequency. 18

Superconductor digital electronics operates at cryogenic temperatures, typically around 4.2 K, and there is currently no technology to enable operation of complex superconducting circuits at significantly higher temperatures. Therefore, the energy required for cryogenic refrigeration must be included in the energy-efficiency calculations, which should include the energy dissipation in the circuits as well as all other sources of the heat load such as input/output data and power cables, thermal radiation, etc. Superconductor electronics is also not self-sufficient. A superconducting circuit cannot operate without auxiliary semiconductor electronics such as power supplies, clock generators, output amplifiers, etc. Their energy consumption must also be included in the efficiency calculations.

In order to become competitive with CMOS electronics, superconducting circuits must reach a very large scale of integration (VLSI) that would enable circuit functionalities and complexities required for computing. A result of the author's survey of the Josephson junction count, the simplest measure of circuit complexity, in fully operational superconducting digital circuits, including also JJ-based memory and quantum annealing circuits, fabricated during the last 25 years is shown in Fig. 1.

The data represent circuits made in the US and Japan by historically the most successful and currently available fabrication processes for SCE: by HYPRES 1 kA/cm 2 2 and 4.5 kA/ cm processes developed at HYPRES, Inc.; 35-48 by NECISTEC 2.5-kA/cm 2 standard process, 49-64 by ISTEC-AIST 10kA/cm 2 advanced process (ADP and ADP2), 26,53,61,65-74 by the MIT Lincoln Laboratory 10-kA/cm 2 process SFQ4ee, 75,76 and by D-Wave Systems, Inc. 31-34 Since any successful integrated circuit is usually a product of a joint work of circuit design and fabrication teams, Fig. 1 characterizes the state of affairs in both the superconducting circuit design and the circuit fabrication areas achieved during the last 25 years. A solid line in Fig. 1 shows an exponential growth with doubling the number of JJs in circuits every 4.5 years. This exponent is a factor of 3 smaller than in the exponential growth demonstrated by CMOS industry during the same period by doubling the number of transistors every 18 months, often referred to as Moore's law. A dashed line in Fig. 1 shows an exponential growth required for achieving goals of the C3 program, doubling the number of JJs per circuit every year.

At present, superconducting digital circuits have about five orders of magnitude lower integration scale than the typical CMOS circuits. For example, the largest demonstrated Single Flux Quantum (SFQ) circuits have only about 10 5 Josephson junctions 68,75,76 whereas CMOS circuits routinely have over 10 10 transistors. Assuming that all progress in CMOS industry stops right now and superconductor electronics will be capable of sustaining the pace of doubling the number of JJs every year, it will take more than 16.5 years to catch up with the complexity of current CMOS circuits. Several causes of this gigantic disparity have been cited:

FIG. 1. The total number of Josephson junctions in fully operational superconducting integrated circuits reported in journal publications and conference proceedings. The circuits were made by the following fabrication processes: HYPRES 1kA/cm, 19 HYPRES 4.5kA/cm 2 , 20-22 NEC-ISTEC 2.5 kA/cm 2 standard process, 23,24 ISTEC-AIST advanced processes ADP 25,26 and ADP2, 27 MIT-LL SFQ4ee process, 28-30 and D-Wave Systems process for quantum annealing processors. 31-34 The VLSI boundary corresponds roughly to 10 5 logic gates or /C24 10 6 JJs. A dashed line shows doubling the number of JJ in circuits every year.

<!-- image -->

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

insufficient funding; lack of profit-driven investments in SCE; immaturity of the fabrication processes and of integrated circuit design tools, etc. If these were the real causes, the corresponding solutions would be trivial: increase funding; develop circuit design tools; use the modern design and fabrication tools; and improve the fabrication process. In the past there have been a few studies predicting the pace of SCE technology development. For instance, in Ref. 77 circuits with 1M (10 6 ) JJs were envisioned by 2005, with 10M JJs in 2008, and PFLOPS-scale superconducting computing in 2011. But no one can see the future and obviously none of these predictions turned out to be correct.

In the present work we look a little deeper and, after a brief review of the operation principles and fabrication processes, look at the physical limitations of 'classical' SCE and critically analyze whether this technology is energy efficient and scalable to the integration levels required for highperformance computing. We also discuss potential approaches for reducing energy dissipation and increasing the integration scale. Superconducting qubits and numerous problems specific to their implementation in integrated circuits for quantum annealing and gate-based quantum computing will not be considered.

## 2. Fabrication and scalability of SFQ circuits

Superconductor digital electronics utilizes magnetic-flux (fluxoid) quantization in superconducting loops to define and process bits of information. It is often called SFQ electronics. Nonhysteretic Josephson junctions are used as ultrafast switches. There are three main types of SFQ logic developed to date: Rapid Single Flux Quantum (RSFQ) logic/memory family 78,79 and its two new 'energy-efficient' versionsERSFQ 80 and eSFQ 81 -differing from RSFQ only by the biasing schemes; Reciprocal Quantum Logic (RQL); 82 and Quantum Flux Parametron (QFP) logic 83,84 and its adiabatic (AQFP) implementation. 85,86

All superconducting digital circuits present a network of Josephson junctions interconnected by superconducting wires (inductors). DC bias currents are distributed using a network of bias resistors and a common voltage rail in RSFQ circuits or a network of bias inductors and JJs in ERSFQ and eSFQ. Multi-phase ac bias and clock signals in RQL and QFP circuits are distributed using a network of passive transmission lines (PTLs) and coupling transformers. The required switching properties of JJs are achieved using on-chip resistive shunting of hysteretic tunnel Josephson junctions. So, making superconducting integrated circuits reduces to making large networks of JJs, inductors, resistors, and transmission lines.

## 2.1 SFQ electronics fabrication processes

In the semiconductor industry the manufacturing processes are classified by the minimum feature size, which is the gate length of the FETs. Historically, the processes in SCE are classified by the critical current density, Jc of the Josephson junctions, e.g., 10-kA/cm 2 process, which is the material property rather than the feature size characteristic. Although the area, A of the junctions is related to Jc as A ¼ I c /J c , the connection with the process resolution capability is lost since JJs are not the smallest feature in circuits. Also, the ability to route various data and clock signals and interconnect logic cells grows with increasing the number of wiring layers available. So this number and the minimum wiring feature size are also important characteristics. A review of fabrication processes up to 2004 can be found in Ref. 87

At present, there are three advanced fabrication processes for SCE: at the National Institute of Advanced Industrial Science and Technology (AIST) in Japan; at DWave Systems, Inc., using Cypress Semiconductor foundry in Bloomington, Minnesota; and at the MIT Lincoln Laboratory. The AIST process was reviewed in detail in Refs. 27 and 66. It has two versions: advanced process (ADP) with 10 Nb layers; and ADP2 with 9 Nb layers. Their main limitation is the use of i -line photolithography, which limits the minimum feature size to /C24 0.8 l m, and the use of 3-in. wafers. The D-Wave process has 6 Nb layers, 0.25l m minimum feature size, and is set on 200-mm wafers. There is no published description of the process, but some information can be found in Refs. 31-34. This proprietary process has been used mainly for making quantum annealing processors operating at mK temperatures, which is a very different application than the digital SFQ electronics.

In our recent work, 28-30 we developed a fabrication process with eight Nb wiring layers and one layer of high-kinetic-inductance material for bias inductors, one layer of Nb/ Al-AlO x /Nb Josephson junctions, and full planarization, including the layer of Josephson junctions. So the total number of superconducting layers is nine. This process node was termed SFQ5ee, where 'ee' denotes that the process is tuned for making energy efficient circuits for IARPA C3 Program. 18 Here we give a brief review of the MIT-LL fabrication process.

The cross-section of the process is shown in Fig. 2. The target parameters of the layers as they appear in the processing and minimum feature sizes (critical dimensions) are given in Table 1. In comparison with the SFQ4ee process described in Refs. 28-30, a more advanced SFQ5ee node offers the following enhancements:

- (i) The minimum linewidth and spacing for all metal layers, but M0, M1, M5 and R5, is reduced to 0.35 and 0.5 l m, respectively;

FIG. 2. Focused-ion-beam-made (FIB) cross-section of a wafer fabricated by the SFQ5ee process. 30 The labels of metal layers and vias are the same as in Table 1. The additional layers in SFQ5ee process with respect to the previous process node SFQ4ee are: a high-kinetic-inductance layer under M0 and a layer of mfl-range resistors between M4 and M5 layers.

<!-- image -->

TABLE 1. Critical dimensions and layer parameters of SFQ5ee process.

|                |                        |                |                | Critical dimension   | Critical dimension   |              |
|----------------|------------------------|----------------|----------------|----------------------|----------------------|--------------|
| Physical layer | Photolithography layer | Material       | Thickness (nm) | Feature (nm)         | Space (nm)           | I c a or R s |
| L0             | L0                     | MoN x          | 40 6 10        | 2000                 | 500                  | 0.5          |
| C0             | C0                     | SiO 2          | 60 6 10        | 500                  | 500                  |              |
| M0             | M0                     | Nb             | 200 6 15       | 500                  | 500                  | 20           |
| A0             | I0                     | SiO 2          | 200 6 30       | 500                  | 500                  | 20           |
| M1             | M1                     | Nb             | 200 6 15       | 500                  | 500                  | 20           |
| A1             | I1                     | SiO 2          | 200 6 30       | 500                  | 500                  | 20           |
| M2             | M1                     | Nb             | 200 6 15       | 350                  | 500                  | 20           |
| A2             | I2                     | SiO 2          | 200 6 30       | 500                  | 500                  | 20           |
| M3             | M3                     | Nb             | 200 6 15       | 350                  | 500                  | 20           |
| A3             | I3                     | SiO 2          | 200 6 30       | 500                  | 500                  | 20           |
| M4             | M4                     | Nb             | 200 6 15       | 350                  | 500                  | 20           |
| A4             | I4                     | SiO 2          | 200 6 30       | 800                  | 800                  | 20           |
| M5             | M5                     | Nb             | 135 6 15       | 700                  | 700                  | 20           |
| J5             | J5                     | AlO x /Nb      | 170 6 15       | 700                  | 1000                 | 100 c        |
| A5a            | I5                     | Anodic oxide d | 40 6 2         | 700                  | 700                  |              |
| A5b            | I5                     | SiO 2          | 170 6 15       | 700                  | 700                  | 20           |
| R5             | R5                     | Mo             | 40 6 5         | 500                  | 500                  | 2 6 0.3      |
| A5c            | C5                     | SiO 2          | 70 6 5         | 500                  | 500                  | 20           |
| M6             | M6                     | Nb             | 200 6 15       | 350                  | 500                  | 20           |
| A6             | I6                     | SiO 2          | 200 6 30       | 700                  | 700                  | 20           |
| M7             | M7                     | Nb             | 200 6 15       | 350                  | 500                  | 20           |
| A7             | I7                     | SiO 2          | 200 6 30       | 1000                 | 1000                 | n/a          |
| M8             | M8                     | Au/Pt/Ti       | 250 6 30       | 2000                 | 2000                 | n/a          |

SiO2 was deposited by plasma enhanced chemical vapor deposition (PECVD) at 150 /C14 C.

- (ii) The minimum size of etched vias and their metal surround is reduced to 0.5 and 0.35 l m, respectively;
- (iii) The sheet resistance of the resistor layer is increased to 6 X /sq by utilizing a nonsuperconducting MoN x film, offering a choice of either 2 X /sq or 6 X /sq planar resistors for JJ shunting and biasing;
- (iv) An additional thin superconducting layer with highkinetic inductance is added below the first Nb layer M0 in order to enable compact bias inductors;
- (v) An additional resistive layer is added between Nb layers M4 and M5 in order to enable interlayer, sandwich-type resistors with resistance values in the m X range for minimizing magnetic flux trapping and releasing unwanted flux from logic cells.

The process consists basically of three main modules: wiring layer module; JJ module; and resistor/kinetic-inductor module. The wiring layer module is shown in Fig. 3.

All wiring layers are processed identically as follows: (a) Nb layer Mi deposition; (b) deep-UV photolithography; (c) high-density plasma etching; (d) photoresist dry/wet strip. Then metrology steps follow: scanning electron microscopy (SEM) inspection, critical dimension (CD) and thickness measurements. Planarization of the etched metal layer is done by a chemical mechanical planarization (CMP), using the steps shown in Fig. 3(e) deposition of a /C24 2.5 /C2 times thicker SiO2 over the patterned metal layer; (f) polishing SiO2 to the required level, using a CMP tool Mirra from Applied Materials, Inc. This is followed by the measurements of the remaining dielectric thickness in 49 points on the wafer, using an elipsometer, and redeposition of SiO2, if needed, to achieve the target ILD thickness in Table 1. Then, the next photolithography is done on the flat surface of SiO2, Fig. 3(g),

FIG. 3. Processing module of the wiring layers: (a) deposition of a wiring layer M (b) deep-UV photolithography; (c) Nb etching in high-density plasma; (d) photoresist dry/wet strip; (e) plasma enhanced chemical vapor deposition (PECVD) of SiO2 interlayer dielectric for planarization; (f) chemical mechanical planarization (CMP) of the interlayer dielectric (ILD) to the required thickness; (g) deep-UV photolithography of the interlayer dielectric layer I i; (h) SiO2 etching; (i) photoresist dry/wet strip and surface cleaning; (j) deposition of the next Nb wiring layer Mi þ 1. This next Nb layer fills in the etched contact holes in the ILD, thus forming superconducting vias between Nb layers. The sequence of steps is repeated as many times as required by the number of wiring layers.

<!-- image -->

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

in order to etch contact holes through the dielectric to the layer Mi, steps (g)-(i) in Fig. 3. Finally, the next wiring layer Mi þ 1 is deposited. This sequence of steps is repeated as many times as the number of wiring layers.

All metal layers used in the process (Nb, Al, Mo) are deposited on 200-mm Si wafers by dc magnetron sputtering using a multi-chamber cluster tool (Endura from Applied Materials, Inc.) with base pressure of 10 /C0 8 Torr. SiO2 interlayer dielectric (ILD) is deposited at 150 /C14 C, using a plasma enhanced chemical vapor deposition (PECVD) system Sequel from Novellus (Lam Research Corporation). Thickness uniformity of the deposited oxide is r ¼ 2%, where r is standard deviation (normalized to the mean value). Photolithography is done using a Canon FPA-3000 EX4 stepper with 248 nm exposure wavelength, UV5 photoresist, and AR3 bottom antireflection coating. Etching of all metal and dielectric layers is done in a Centura etch cluster (Applied Materials, Inc.), using Cl2/Ar-based chemistry for metals and CHF3-based chemistry for dielectrics. Etched vias I0, I1, etc. are filled by Nb of the following metal layer.

Josephson junction fabrication was described in detail in Ref. 28 and the JJ module is shown in Fig. 4.

The Nb/AlO x -Al/Nb trilayer process developed in Ref. 88 has been the most successful process for making Josephson tunnel junctions and is used in our work. It consists of a Nb base-electrode deposition (150 nm) followed by in-situ Al deposition (8 nm) and oxidation in pure oxygen at 8 mTorr to achieve the aluminum oxide, AlO x , thickness required for 100 l A/m Josephson critical current density. A Nb counterelectrode completes the trilayer sandwich. After etching the counter-electrode to define the Josephson junctions, the surface of the tunnel barrier is exposed. To prevent the barrier degradation around the perimeter of the junctions, anodic oxidation is used to form a /C24 50nm oxide layer on all exposed surfaces, Fig. 4(d). This oxide protects the junctions and

FIG. 4. Josephson junction fabrication module: (a) Nb/AlO x -Al/Nb trilayer deposition over the patterned SiO2 layer. The base electrode of the trilayer fills the etched contact holes, making I4 vias to the bottom Nb layer, M4. (b) deep-UV photolithography of the counter electrode to form a junction etch mask; (c) junction etching, stopping on AlO x /Al layer; (d) anodization; (e) photolithography of the base electrode layer; (f) etching of the base electrode, forming wiring layer M5; (g) deposition of a thick SiO2 for planarization; (h) CMP to the level of the Josephson junctions to expose their top surface.

<!-- image -->

allows further processing steps: (e) photolithography; and (f) etching of the bottom electrode in order to define Nb wiring layer M5 interconnecting the JJs and connecting them to the bottom layers, Fig. 4. Then, the etched structures are planarized to the level of the tops of JJs as shown by steps (g) and (h).

In order to form resistively shunted JJs, the following resistor process module is used, Fig. 5. A similar module is used to process the very first layer in the process stack-up, the layer of kinetic inductors, L0, Fig. 1. A resistor layer (Mo or MoN x ) is deposited on the planarized surface. After the photolithography, resistors are selectively etched in highdensity plasma, stopping on Nb and SiO2. A thin, with /C24 70 nm thickness, SiO2 layer is deposited on top to isolate the resistors. Contact holes to the top and bottom electrodes of the junctions and to the resistors are etched. Nb wiring layer M6 is deposited. This M6 layer and layers above it are processed using the wiring module shown in Fig. 3.

The final process cross-section is shown in Fig. 2 and a zoom-in of a cross-section through the junction is shown in Fig. 6. The full 9-superconductor-layer process has more than 400 processing steps.

A perceived simplicity and alleged low cost of the fabrication process were historically cited as one of the main advantages of SFQ electronics. 77,79 At the time of RSFQ introduction in the US in 1991, the only commercial fabrication process for SCE had only three superconducting niobium layers for interconnecting Josephson junctions, a minimum feature size of 3.5 l m, used Nb/AlO x /Nb Josephson junctions, and 3-in. wafers. 19 At that time, these process features corresponded to about Intel's process used to make the semiconductor processors in 1982, and so the process was about 10 years behind, see Table 2. The first and very simple RSFQ circuits containing tens of JJs showed great promise and were setting the clock speed records. So, from this starting point, it was tempting to forecast a fantastic growth in future. Since none of the original RSFQ technology proponents was involved with or experienced in integrated circuit technology and manufacturing, it was natural to assign circuit failures to

FIG. 5. Resistor/kinetic-inductor process module: (a) resistor deposition; (b) resistor photolithography, high-density plasma etching and photoresist striping; (c) SiO2 layer deposition, 70nm thickness; (d) photolithography and etching of contact holes to JJ and resistor C5, photolithography and etching of contact holes to the base electrode of JJs, M5; (e) Nb wiring layer deposition, M6. Nb layer M6 and layers above it are processed using the wiring module in Fig. 3. The resistor minimum length is determined by the minimum spacing s between superconducting wires and contact holes surround sr shown in (e).

<!-- image -->

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

FIG. 6. FIB-made cross-section of a 1l mJosephson junction. In this particular case, the contact C5 is larger than the junction J5, so the M6 wire overhangs the junction. The opposite situation when C5 is smaller than J5 was shown in Fig. 5. Anodic oxide layer formed on the junction sidewalls and the surface of M5 by anodization is clearly visible.

<!-- image -->

immaturity of the fabrication processes 77 and suggest that their major improvement would be a simple task requiring only very modest investments and second-hand tools from retiring nodes of CMOS manufacturing lines. 17 After 25 years of the SFQ fabrication-technology development, it is clear that these assessments were incorrect. The minimum linewidth of SCE processes has shrunk down to 0.25 l m, the number of superconducting wiring layers has increased from 3 to 9, and the wafer size has increased to 200 mm. So, the features of the currently available SCE processes match and exceed the Intel's process used to manufacture Pentium II processors in 1997, see Table 2. However, no SFQ-based computers or digital circuits with complexities comparable to any of the CPUs shown in Table 2 have emerged.

## 3. Physical constraints on VLSI of SFQ electronics

By comparing the features of the SCE fabrication processes described above with CMOS processes given in Table 2, one could expect that superconducting circuits with a similar integration scale, similar number of JJs in a few million range, and of similar functionality should be possible to fabricate if the appropriately designed circuits become available. Below we examine this expectation by accounting for the specifics of SFQ circuits.

## 3.1 Josephson junctions

Firstly, we estimate the maximum possible density of unshunted junctions in SFQ circuits. The total area occupied by a circular junction in M5 (base electrode) or M6 (top wiring) planes is

<!-- formula-not-decoded -->

TABLE 2. Semiconductor processors and fabrication processes.

| Processor   | Transistor count   |   Min linewidth ( l m) |   No. of metal layers |   Year introduced |   Chip area (mm 2 ) |
|-------------|--------------------|------------------------|-----------------------|-------------------|---------------------|
| Intel 80186 | 55k                |                   3    |                     2 |              1982 |                  60 |
| Intel 80286 | 134k               |                   1.5  |                     2 |              1982 |                  49 |
| Intel 80386 | 275k               |                   1.5  |                     2 |              1985 |                 104 |
| Intel 80486 | 1.2M               |                   1    |                     3 |              1989 |                 173 |
| Pentium     | 3.1M               |                   0.8  |                     3 |              1993 |                 294 |
| Pentium Pro | 5.5M               |                   0.5  |                     4 |              1995 |                 307 |
| Pentium II  | 7.5M               |                   0.35 |                     4 |              1997 |                 195 |
| Pentium III | 9.5M               |                   0.25 |                     5 |              1999 |                 128 |

FIG. 7. The maximum density of Josephson junctions in SFQ circuits as a function of the average I c of the SFQ cells. Resistively shunted and unshunted JJs in the current technology node 2 SFQ5ee (Jc ¼ 0.1 mA/ l m 2 , sr ¼ s/ 2 ¼ 0.25 l m) are shown by the solid lines; self-shunted JJs in a hypothetical technology node with Jc ¼ 2.5 mA/ l m 2 and sr ¼ s/2 ¼ 0.1 l m are shown by the dashed line. A 100% area coverage is assumed, k ¼ 1.

<!-- image -->

where Jc , r , sr , and s are the Josephson critical current density, the junction radius, base electrode and top wire (M6) surround of the junction, and spacing to the next object, respectively. Then, using s /2 ¼ sr ¼ 0.25 l m from Table 1, we plotted in Fig. 7 the maximum density of unshunted JJs, nJ ¼ k/AJ as a function of their critical current I c , assuming a 100% area coverage, k ¼ 1. In the range of the critical currents typically used, from 100 l A to 300 l A, nJ is from about 15M to 30M JJs per cm. This coverage, of course, is impossible to achieve in a circuit because JJs need to be interconnected to other circuit components. At a more realistic k ¼ 0.5, nJ is comparable to the density of transistors in the processors in Table 2, but three orders of magnitude less than the typical density of modern CMOS transistors. This gap cannot be closed even if the junction technology is pushed to the ultimate values: Jc increased 25 folds to /C24 2.5 mA/ l m 2 ; 92 sr and s /2 reduced to 100 nm; and the number of JJ layers increased to two, still giving only nJ /C24 5 /C2 10 8 JJ/cm 2 .

SFQ circuits utilize nonhysteretic junctions. In the existing technology this is achieved by resistive shunting of the tunnel junctions as shown in Fig. 5. The top view of a resistively shunted junction (RSJ) is shown in Fig. 8. The total area of the RSJ includes the junction area AJ , resistor area, and the area of vias and wires connecting the JJ and the resistor. This area includes also the overlap between wires M5 and M6 and the contact holes and the junction by amount sr ,

a process parameter given in the design rules document. Below we estimate the total RSJ area in order to estimate the maximum circuit density.

SFQ circuits utilize RSJs with critical damping, i.e., with McCumber-Stewart 89,90 parameter b c ¼¼ 2 p IcR 2 n C = U 0 /C25 1, where U 0 /C17 h = 2 e is the flux quantum, C is the junction capacitance, Rn is the damping resistance assumed to be a parallel combination of the junction internal resistance R and the shunt resistance Rs , see inset in Fig. 9. The inductance Ls associated with the superconducting connections to the shunt and of the shunt itself makes damping frequency-dependent, which is usually neglected in SFQ circuit design. The internal resistance is usually approximated by a piecewise function

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where Vg ¼ 2 D / e is the gap voltage in the symmetrical tunnel junction, D is the energy gap in the electrodes, RN is the normal state tunnel resistance, Rsg is the subgap resistance, and c is the temperatureand JJ-quality-dependent coefficient, c &gt; 1. Then, neglecting Ls, the damping resistance at low voltages V &lt; Vg is Rn ¼ c RNR/( c Rn þ Rs) .

The typical current-voltage characteristics of JJs in the MIT Lincoln Laboratory process using Nb/Al-AlO x /Nb tunnel junctions with Josephson critical current density of 10 kA/cm 2 (100 l A/ l m 2 ) are shown in Fig. 9 for the unshunted junction (curve 4 ) and junctions of the same size with three different values of the shunt resistor corresponding the characteristic voltage Vc ¼ I cRn of 0.30 mV (curve 1), 69 mV (curve 2 ), and 0.96 mV (curve 3), and to b c ¼ 0.2, and 2, respectively.

At the specific capacitance value of 70 fF/ l m 2 given in the SFQ5ee process design rules, the characteristic voltage of the junctions at b c ¼ 1 is Vc ¼ IcRn /C25 686 l V. At Jc ¼ 100 l A/ l m 2 used in the process, Rsg /C29 Rs , RN , c /C25 10 in (2), and its contribution can be neglected in the estimates of the shunt resistor here. Then, the shunting resistor value is simply Rs ¼ Vc /( JcA) ¼ 686/ I c , where Rs is in ohms and I c in l A. The area of a resistor Rs ¼ R sq l/w with the minimum linewidth w and length l depends on the sheet resistance of the material used, Rsq and other process parameters, see Ref. 30

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

because the resistor length cannot be made shorter than l min ¼ s þ 2 sr , about 1 l m in the current process node. At Rsq ¼

FIG. 8. Top view of a resistively shunted JJ showing JJ counter electrode J5, JJ bottom electrode M5, resistor R5, contact holes C5 and I5, and wiring layer M6 providing connections between the JJ and the resistor. All metal wires M5 and M6 must overlap (surround) the JJ and all contact holes by some amount, sr according to the process design rules.

<!-- image -->

FIG. 9. Current-voltage characteristics of resistively shunted Josephson junctions in the MIT-LL fabrication process SFQ5ee with Jc ¼ 100 l A/ l m 2 . Data for 1.6l m-diameter junctions with three different shunt resistors Rs are shown: Rs ¼ 1.6 X (1) ; Rs ¼ 3.73 X (2) ; Rs ¼ 5.4 X (3) , corresponding to Vc /C17 IcRn values of 0.30, 0.69, and 0.96 mV, respectively. These values in turn correspond to b c ¼ 0.2, 1, and 2, respectively. The top I-V curve 4 is for the unshunted JJ. Inset shows the circuit diagram. The shunt inductance associated with the current path from the JJ along the resistor to the I5 via and back to the JJ along the M5 electrode, Ls /C24 1 pH, is usually neglected. However, it causes an internal Ls-C resonance with the junction capacitance, corresponding to a step at /C24 0.5 mV in curve 2 .

<!-- image -->

2 X / sq , the boundary corresponds to Rs ¼ 4 X Therefore, all JJs with I c /C21 172 l A have shunts in the regime (3b). We need to add the area of two C5 and one I5 vias with surround, which is approximately 3( w þ 2 sr ) 2 in the regime (3a) and ( w þ 2sr ) 2 þ 2( s þ 2 sr )( w þ 2 sr ) R sq / Rs in the regime (3b), and account for the spacing to the next feature, where w is the minimum size of features, see Table 1.

Then the total area of an RSJ becomes

<!-- formula-not-decoded -->

for I c &lt; [ w /( s þ 2 sr )] Vc / R sq /C25 172 l A, and

<!-- formula-not-decoded -->

for I c /C21 172 l A.

The maximum possible density of RSJs nRSJ ¼ 1/ ARSJ following from (4) is plotted in Fig. 7, bottom curve. It is significantly lower than the maximum density of unshunted junctions. The maximum density is about 8.3M RSJs per cm 2 and nearly independent of the critical current of JJs in the range from /C24 70 l A to /C24 175 l A. The RSJ area in this range is ARSJ /C24 12 l m 2 . The maximum density of RSJs in SFQ circuits can be estimated as k/ARSJ by using in (4) the most frequently encountered, or the average, critical current h I c i and the area filling factor k /C24 0.5. Inspection of all RSFQ, ERSFQ, etc. cells in Refs. 77-81, and 91 shows that h I c i /C25 175 l A. It is a result of selecting I c /C25 100 l A as the minimum value used in the cells, based on the maximum

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

acceptable bit error rate. Since the junction must be connected to inductors, the RSJ area coverage of 25% to 50% is more realistic, reducing the maximum circuit density to about 2M to 4M RSJs per cm 2 .

## 3.2 Statistical variations of Josephson junctions

As was shown above, the maximum density of RSJs is nearly independent of the choice of h I c i and sufficient to place a few million of JJs on a 1-cm 2 chip. However, it is important to check if they all can be yielded with critical currents within the required margins. From the circuit design standpoint, statistical variations of JJ critical currents, as well as thermal and quantum noise, induce storage, decision, and timing errors and determine the bit error rate in SFQ circuits. 93 From the fabrication process standpoint this is related to the so-called parametric yield-the fabrication yield of devices with parameters lying within a given range 6 M with respect to the targeted mean value. The SFQ cells are designed to tolerate some relatively large deviations. For instance, all critical currents of the junctions can be changed by about 6 30% if changed uniformly, or any single junction can deviated from the target by the 6 30% if all other JJs are on target, etc. However, random deviations of all junctions and all inductors in the cells cause significant margin shrinkage. The typical bias margins reported for the circuits shown in Fig. 1 are often less than 6 10% especially at high clock frequencies.

The statistics of JJ critical currents fabricated by our planarized process was studied in Ref. 28 and can be described as approximately Gaussian with the standard deviation depending strongly on the junction size. This dependence comes from the fluctuations of the junction area caused by photolithography and tunnel barrier transparency fluctuations, both increasing with decreasing the junction diameter. Statistical data in Ref. 28 can be converted into the dependence of the standard deviation of I c (normalized to the mean value) on the critical current (in l A) as

<!-- formula-not-decoded -->

where the dimensional prefactor is in l A 1/2 and I 0 is the critical current cut-off-the process resolution characteristic corresponding to the critical current of the smallest resolvable junction. In the SFQ5ee process using 248-nm photolithography, this minimum size is about 250 nm and I 0 /C25 5 l A.

The probability that a JJ critical current is within the circuit margins 6 M is given by the error function p ¼ erf ð M = ffiffiffiffiffiffi ffi 2 r I p Þ . For an N-junction circuit, the probability (yield Y) that all JJs are within 6 M range is Y ¼ p N . Then, the fabrication-yield-limited maximum number of JJs in a circuit is

p

ffiffiffiffiffiffi ffi

<!-- formula-not-decoded -->

where Y min is the minimum acceptable circuit yield. This dependence at Y min ¼ 50% and 90% is plotted in Fig. 10 for three different values of the circuit margins M: 15%, 10%, and 5%. Also shown is the maximum number of RSJ which can be placed on a chip with area A ch

(7)

FIG. 10. The maximum number of Josephson junctions which can be yielded with a required probability (circuit yield) Y by the current fabrication process SFQ5ee and with all junctions having the critical current within the circuit margins 6 M , as given by (6) and (5). Dashed lines and solid lines correspond to Y ¼ 0.5 and Y ¼ 0.9, respectively. Also shown is the maximum number of resistively shunted JJs kA ch / ARSJ which can be placed on a chip with 1 cm 2 and 2 cm 2 area at 50% area coverage, k ¼ 0.5, and Jc ¼ 100 l A/ l m 2 .

<!-- image -->

at fill factor k ¼ 0.5 and A ch ¼ 1 cm 2 and 2 cm 2 .

At critical currents smaller than the point of intersection of (6) and (7) the maximum number of JJs in the operational circuits is determined by the I c spreads, acceptable circuit yield, and the circuit margins. At higher critical currents, this number is limited only by the junction area and can be increased by increasing the size of the chip. It can be seen that at h I c i /C25 175 l A and above, as was chosen in RSFQ originally, the size of the circuit (JJ count) is not limited by the parametric yield of the current process even for poorly designed circuits with 6 5% margins, and the circuit parametric yield above 50% can be reached even on large-area chips /C24 2cm 2 with about 10M RSJs. However, the current desire for energy efficiency requires reducing h I c i well below this number, see Sec. 4. Below h I c i¼ 50 l A, a value popular in many RQL and AQFP designs and used in Ref. 16 for calculating SCE electronics power budgets, the circuit complexity will be limited by the fabrication process unless circuits with very wide margin can be designed.

It is author's experience, however, that the practical yield of complex circuits is much lower than the parametric yield following from the assumed normality of the parameter distribution used in our estimates here. In practice, the circuit yield is determined by defects and outlier devices, i.e., devices in the far tails of the distribution. The probability of outliers increases with decreasing the junction size. The distribution is often skewed and the tails are usually nonGaussian. Often they can be described by the Weilbull statistics with a simple exponential decay. A more detailed description of this subject is beyond the scope of this work and will be presented elsewhere. However, the message of this is that decreasing h I c i below /C24 75 l A is expected to compromise the circuit yield in the current technology node.

## 3.3 Limitations on scaling caused by bias currents

RSFQ-based circuits, including ERSFQ and eSFQ, use a parallel dc biasing of JJs from a common voltage rail. The

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

typical bias current is 0.7 I c . The total bias current I tot grows proportionally to the number of JJs and can be estimated as

<!-- formula-not-decoded -->

where NRSJ is the number of JJs in the circuit, giving about 122 A per 1M JJs. It is clear that such large currents cannot be supplied to and handled by thin-film superconducting layers at 4K. Large bias currents also create large stray magnetic fields and cause magnetic flux trapping and circuit margin degradation. The maximum current which has successfully been delivered to the largest operational RSFQ circuit is /C24 3 A, 69 with a substantial margin degradation of some of its subcircuits. This total-bias-current limitation caused the saturation in the number of JJs in RSFQ circuits at /C24 12 000 (12k) JJs, which can be seen in Fig. 1 during a 10-year period from /C24 2004 to 2014. All circuits with JJ count over 20k shown in Fig. 1 used various ac serial-biasing schemes.

RSFQ-based circuits or any circuits with parallel biasing are not scalable beyond about 20k to 30k JJs. To mitigate this problem, serial biasing of RSFQ circuits was proposed a long time ago 94 and demonstrated in relatively simple circuits in Refs. 95-97. Serial basing, also known as current recycling, requires breaking a circuit into m isolated islands and recycling the return current from the ground planes of one island to bias in series the next island, thus reducing the total current by a factor of m . The current drawn by each island must be equal, and the input and output currents must not add currents to the serially biased circuits. This is achieved by transferring microwave clock and SFQ data between the islands through transformers using driverreceiver pairs. 98 For an m-bit processor, a natural recycling scheme would be between the m individual bits. Since the number of JJs per island should be kept at /C24 10k level in order to keep the total current below 2 A, the number of islands in a 2M-junction circuit becomes &gt; 100, requiring lots of inter-island interface circuitry with its own biasing. This complicates design and decreases the circuit density. Presently, there are no readily available and proven solutions for making VLSI SFQ circuits with current recycling, and many technical problems remain to be solved.

RQL and QFP circuits use multiphase ac currents for clock and bias, so the total current only weakly increases with NRSJ . The technical difficulties with ac biasing lie in the proper distribution of these high-frequency currents along PTLs to each junction and the negative effect on the circuit density caused by the PTLs and coupling transformers.

## 3.4 Heating of resistors

Many SFQ circuits use resistors and resistive dividers for distributing dc bias currents and matching rf impedance. These resistors are in direct contact with superconducting wires on M6 layer through C5 vias. Heat dissipated in the resistors increases the local temperature and decreases the critical current of wires and JJs, and in extreme cases can turn them into the normal state. This should be mitigated by a proper sizing of resistors and wires, and proper spacing of high-current-carrying resistors from other circuit elements sensitive to temperature increase.

The amount of heat dissipated in a thin-film resistor with sheet resistance Rs , width w , and length l per unit time is

<!-- formula-not-decoded -->

where I is the current. In the steady state, this amount of heat power is balanced by the heat conduction through the circuit layers into the substrate and into liquid helium (or a cryocooler) cooling the chip surfaces. The amount of heat that can be removed due to conduction can be estimated as

<!-- formula-not-decoded -->

where AR ¼ 2 lw is the resistor surface area, R th is the effective thermal resistance, and D T is the resistor temperature increase. Equating (9) and (10) we get

<!-- formula-not-decoded -->

i.e., the resistor temperature increases inversely with the resistor width squared. There is a maximum temperature increase D T max above which Nb wires in contact with the resistor will transition into the normal state at a given current and given bath temperature. This sets the maximum value of the current in the resistor as

<!-- formula-not-decoded -->

The maximum current one can supply through the resistor without turning the contacting Nb wires into the normal state is inversely proportional to the square root of the sheet resistance. So the desire to increase R sq in order to minimize the resistor area, see (3a), is at odds with the resistor heat handling capabilities. Since heating of SFQ circuits is highly undesirable, (11) and (12) put strong restrictions on the minimum width of resistors that can be used or the currents they can handle, strongly impacting the integration scale.

The thermal resistance at both interfaces of the resistor is not exactly known. For a metal surface in contact with liquid helium at 4.2 K, the typical thermal resistance Rth is about 1 Kl m 2 / l W. Using this value of Rth, Rs ¼ 2 X /sq, and D T max ¼ T cNb /C0 4.2 K ¼ 5K we estimated the maximum current per unit width of the resistor as I max/ w ¼ ¼ 2.2 mA/ l m. Simple measurements of I-V characteristics of Nb wires in contact with Mo resistors of different width done in this work give I max/ w ¼ 1.3 mA/ l m. This value translates into the effective thermal resistance of Rth /C25 3 Kl m 2 / l W (3 /C2 10 6 K-m 2 /W) for the circuit resistors buried deep into the multilayered structure with multiple interfaces between Nb and SiO2 layers (Fig. 1).

Resistor heating makes it almost impossible to achieve very large integration scale in circuits with parallel biasing. For instance, distributing 244 A bias current in a circuit with 2M JJs, considered in Sec. 2.3, would require a total width of bias resistors of /C24 20 cm.

## 3.5 Circuit inductors

Yet another constraint comes from the circuit inductors, since every JJ in an SFQ circuit is connected to an inductor. By inspecting the published RSFQ and RQL cells and circuits, we note that the average superconducting loop with JJs in the designs has a dimensionless parameter b L ¼ 2 p IcL / U 0 /C24 2, where L is the inductance. We denote this average value

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

as h b L i . Each inductor occupies area AL ¼ (L/ ' )(w þ s ), where ' , w and s are the inductance per unit length, inductor linewidth, and spacing between the inductors, respectively. The maximum inductor density grows linearly with the average critical current of SFQ cells as

<!-- formula-not-decoded -->

where mL is the number of physical layers of inductors, k is the filling factor. In order to minimize cross-talk between inductors, stripline configuration is used predominantly. This requires three superconducting layers: one signal layer and two ground planes. So, a process with eights superconducting layers may have up to three completely independent layers of inductors. The smallest inductor linewidth in our process is 0.35 l m and spacing is 0.5 l m, so w þ s ¼ 0.85 l m. At this linewidth, the typical stripline inductance per unit length is ' /C25 0.6 pH/ l m. 29 Since, on average, each RSJ requires an inductor, the maximum circuit density can be estimated by equating nRSJ and nL .

The plot of (13) is shown in Fig. 11, along with nRsJ and nj as a function of the average critical current h I c i , for a few values of h b L i and mL , and k ¼ 0.5. (It should be noted that some fraction of the area is occupied by vias providing connections between the inductors and the junctions, which may reduce the actual value of k below 0.5.) We can see that circuits with two layers of inductors can reach the maximum of about 3M components (both RSJs and inductors) per 1-cm 2 chip if h I c i is larger than about 35 l A. Circuits with just one layer of inductors may still reach the same complexity if h I c i is larger than /C24 75 l A. The latter approach has been taken in designing ac-biased shift registers, 75 and circuits with densities over 0.6M RSJs per cm 2 have been demonstrated. Recently these shift registers have been redesigned and fabricated at MIT-LL by the SFQ5ee process. Operational circuits with 1.3M RSJs per cm 2 density and over 65 000 RSJs have been demonstrated; 99 see Fig. 12. Testing of shift registers with 144 000 RSJs is the work in progress.

FIG. 11. The maximum density of circuit inductors in the SFQ5ee process as a function of the average critical current in SFQ cells h I c i , assuming the average h b L i ¼ 2 and mL ¼ 2 (curve 1 ), where mL is the number of independent layers of inductors. Also shown are: h b L i ¼ 3, mL ¼ 2 (curve 2 ); h b L i ¼ 2, mL ¼ 1 (curve 3 ); and h b L i ¼ 3, mL ¼ 1 (curve 4 ); the density of shunted and unshunted junctions nRSJ and nJ . Inductance per unit length of 0.6 l H/ l m(Ref. 29) was used, and the area fill factor k ¼ 0.5 was assumed.

<!-- image -->

FIG. 12. An example of the unit cell (bit) of the ac-biased shift registers. 99 The cell dimensions are 20 l m /C2 15 l m, the RSJ density is 1.3 /C2 10 6 RSJs per cm 2 . A 16363-bit fully operational circuit has 65536 RSJs. The minimum linewidth, mL , and I c used were 0.4 l m, 1, and 125 l A, respectively.

<!-- image -->

At h I c i lower than the intersection point of the nL ( I c ) and nRSJ ( I c ) dependences, the circuit complexity is limited by the number of inductors and, at higher h I c i , by the number of junctions. Circuits with h I c i larger than about 125 l A are not limited by inductors at all, only by the area occupied by RSJs.

It is also clear from Fig. 11 that increasing mL beyond 2 by increasing the number of superconducting layers in the process will not increase the circuit density, because it is limited by the density of RSJs. However, more layers may add more flexibility in routing the clock, bias, and data paths.

It is interesting to note that, if the resistive shunts could be eliminated by using self-shunted JJs with the same I c and the similarly tight parameter spreads as the shunted tunnel junctions, the circuit complexities can reach about 10M (JJ/ inductors) per 1-cm 2 chip by choosing h I c i in the range from /C24 120 l A to 190 l A.

## 4. Energy dissipation and efficiency of SCE

## 4.1 RSFQ-based and RQL circuits

RSFQ logic was proposed more than 30 years ago as a replacement of Josephson latching logic used by IBM in its early attempt to build a Josephson-junction-based computer in the 1970s-early 1980s. In RSFQ logic/memory the information is encoded by the presence (logic 1) or absence (logic 0) of a single flux quantum U 0 ¼ h/2e in a logic cell and is transferred between the cells in the form of picosecond-wide SFQ voltage pulses. An SFQ pulse is a voltage pulse generated across a Josephson junction when the phase difference across the junction flips by 2 p as a result of some external perturbation, e.g., a current pulse. The second Josephson relation 100 d u = dt ¼ ð 2 e = /C22 h Þ V guarantees that these SFQ pulses have a quantized area equal to a single flux quantum Ð V ð t Þ dt ¼ U 0 /C25 2 : 07 mVps or 2.07 pH mA. The process of SFQ pulse generation can be also viewed as a passage of a flux quantum through the junction. Accordingly, if a junction is embedded into a superconducting loop, such a passage also changes (reduces or increases) the flux through the loop

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

by U 0. A complete description of SFQ logic was given in Ref. 79 and the cell library can be found in Ref. 91. Each cell has separate data inputs and outputs, and clock lines. SFQ pulses encoding data and clock are distributed on two different networks of JTLs and PTLs. In the time domain, logic '1' is encoded by the arrival of a data SFQ pulse (on the data input) between two clock pulses (on the clock input), whereas logic '0' corresponds to no data pulse between the clock pulses.

To provide reliable switching by an SFQ pulse and set the direction of SFQ pulse/flux propagation, almost all JJs in the circuits are current-biased at a value I b /C25 0.7 I c, using a network of either bias resistors and a common voltage rail (as in RSFQ) or a network of inductors and current-limiting junctions (as in ERSFQ, eSFQ), or their combinations.

The average dynamic-power dissipation in an SFQ circuit utilizing Josephson junction switching (RSFQ, ERSFQ, eRSFQ, RQL) can be estimated as

<!-- formula-not-decoded -->

where N is the number of Josephson junctions in the circuit, f cl is the clock frequency, a is the activity coefficient, the fraction of JJs switching during the clock period, h E sw i is the average energy loss per switching.

It is well known that a resistively capacitively shunted junction (RCSJ) has a potential energy described by a tilted washboard potential

<!-- formula-not-decoded -->

where EJ ¼ I c U 0 = ð 2 p Þ is the Josephson energy and i ¼ I b /Ic is the normalized bias current. When switched by an SFQ pulse, the junction goes from one potential minimum of (15) to another separated by a 2 p phase difference. The energy difference between the two minima is D E ¼ 2 p iEJ . Since the junction is critically damped or overdamped, all of this energy is dissipated in the resistor, and there is no energy left for recycling and increasing the efficiency of the information processing. Hence, the average energy loss per switch is

<!-- formula-not-decoded -->

where h Ib i is the average bias current. This energy should not be confused terminologically with the switching energy-the energy required to flip the junction's phase by 2 p . The latter equals to the height of the potential barrier between the two adjacent minima of (15) and can be made arbitrarily small by increasing the bias current.

Using the typical value h Ib i ¼ 0.7 h I c i , following from the circuit speed optimization, and assuming a random mix of 'ones' and 'zeros' ( a /C25 0.5), the average power loss in an RSFQ-type circuit is

<!-- formula-not-decoded -->

The RQL circuits use four-phase ac currents for JJ biasing and circuit clock. 82 A reciprocal pair of SFQ pulses (positive and negative) during the clock period encodes '1' and no pulses encode '0.' This encoding increases the energy loss by a factor of two, and for a random mix of 'ones' and 'zeroes' results in a ¼ 1 in (14). Also, according to Ref. 82, the switching of JJs by an ac-bias current occurs at a current smaller than I c . As a result, the energy dissipation in RQL circuits with random data can be approximated by

<!-- formula-not-decoded -->

where h I c i is the weighted average of the critical current of the junctions. 82 The difference between (18) and the RSFQbased case (17) is completely negligible.

Inspection of all RSFQ cells in Refs. 77-79, and 91 shows that the average critical current h I c i ¼ 0.175 mA. This gives the average energy loss h E sw i ¼ 2.5 /C2 10 /C0 19 J or 0.25 aJ per JJ switching in RSFQ, ERSFQ, and eSFQ circuits. This is a factor of 6 /C2 10 3 times larger energy loss than the Landauer's minimum energy-per-bit requirement for irreversible computing, kBT ln 2 101 at T ¼ 4.2 K; kB is the Boltzmann constant. It is important to stress that the minimum critical current used in the SFQ cells is typically a factor of two lower than the average as a wide range of JJs values is used in the cells. However, the minimum critical current sets the maximum acceptable bit error rate 77,79 and typically is about 0.1 mA. Changing the minimum I c value by a factor of m would automatically change the h I c i and the h E sw i by the same factor.

Another important quantity is the energy loss per a single-bit operation (SBOP). It is different from h E sw i because any logic gate (Boolean) operation requires switching of multiple JJs, so

<!-- formula-not-decoded -->

where NSBOP is the average number of JJ switches required. This number in RSFQ and RQL cells is about 10. For instance, OR gate has 12 JJs, XOR gate has 9 JJs, AND gate 11 JJs, etc. 77,79,91 Recall that three SFQ pulses (3 switches) are required just to encode '1' and two switches to encode '0.' So, h ESBOP i /C25 10 h E sw i /C25 2 : 5 aJ :

In order to compare the energy efficiency of the cryogenic electronics with room-temperature electronics we need to account for the energy loss associated with cryocooling. Removing P cold from the chip at 4.2 K requires a cryocooler (a heat machine) consuming a much larger power, P hot at 300 K, given by

<!-- formula-not-decoded -->

where e ¼ ge id is the energy efficiency of the cryocooler and e id ¼ T cold ð T hot /C0 T cold Þ /C25 T cold = T hot is the efficiency of an ideal thermal machine (Carnot efficiency) and g &lt; 1 is a nonideality factor. Depending on the cryocooler size and type, this factor changes from g /C24 0.02 for the small-scale ( /C24 1.5 W at 4.2 K) pulse-tube coolers to /C24 0.20 for the largest-scale Linde helium liquefiers with /C24 400-kW wall power requirements, see, e.g., Table 1 in Ref. 16. The inverse efficiencies of these two types of cryocoolers, 1/ e sm ¼ 3520 and 1/ e l ¼ 352, are used hereafter for all power consumption estimates as the upper and the lower boundaries.

In order to determine which technology is more energy efficient, CMOS or SFQ, we need to compare the power loss in two circuits performing a similar function or a similar amount of information processing. The performance and power loss in the CMOS-based processors can easily be

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

TABLE 3. Power dissipation in CMOS and hypothetical VLSI SFQ processors.

| Unit    |   f cl (GHz) |   N (10 9 JJs or transistors) | P cold at 4.2K (W)   |   P hot (W) lower bound g ¼ 0.2 |   P hot (W) upper bound g ¼ 0.02 |
|---------|--------------|-------------------------------|----------------------|---------------------------------|----------------------------------|
| SFQ     |            4 |                           1.4 | 0.71                 |                             250 |                             2500 |
| i7-4790 |            4 |                           1.4 | -                    |                              88 |                               88 |

measured, are well known and can be found in Ref. 102. The power dissipation is typically below 140 W. For instance, Intel's quad-core Core i7-4790 Haswell CPU using 22-nm technology node has 88-W power dissipation at f cl ¼ 4 GHz, performance of about 200 GFLOPS, and N ¼ 1.4 /C2 10 9 transistors. 103 Unfortunately, superconducting processors of comparable complexity do not exist, and the achieved integration scale differs by 5 orders of magnitude. So, to make a comparison, we need to make some assumptions. Below, we provide a few estimates of the upper and lower bounds on the power consumption in VLSI SFQ circuits.

Firstly, we note that the number of JJs in RSFQ and RQL logic gates and memory cells is comparable or even larger than in CMOS logic gates and memory. Secondly, superconducting processor architectures that are being developed use algorithms developed for CMOS computers and emulate their architectures, using adders, multipliers, etc., see, e.g., Refs. 47, 63-67, 71-74, and 104. It is reasonable to assume then that a superconducting processor with N junctions operating at f cl will be processing about the same amount of information (perform the same logic and memory functions) as a CMOS-based processor with N transistors clocking at the same frequency. Then, using f cl ¼ 4 GHz, N ¼ 1.4 /C2 10 9 JJs, and h E sw i ¼ 2.5 /C2 10 /C0 19 J estimated above for h I c i ¼ 0.175 mA, we get from (17) and (18) P cold ¼ 0.71 W, see Table 3. This is a low power compared with about 100 W power consumed by the CMOS chip operating at room temperatures.

However, depending on the cryocooler used, the total power consumption by our hypothetical SFQ circuit is from P hot /C25 250 W to 2.5 kW, a factor of /C24 3 /C2 to 30 /C2 larger than in the CMOS processor of the same complexity. This, perhaps, is a rather surprising result for many readers. Of course, a fraction of transistors in the CMOS processor is sleeping at any given moment in order to prevent overheating. This was not taken into account in our estimate. The same approach can also be implemented in SFQ electronics.

Because this result may look too pessimistic, we decided to check it by comparing the power requirements per GFLOPS in CMOS and SFQ implementations. The only existing data for operational bit-serial, single-precision (32bit) floating-point adders (FPA) and floating-point multipliers (FPM) made in RSFQ technology were reported in Ref. 69. They have, respectively, 16 830 JJs and 18 766 JJs. (For a comparison, a 32-bit adder requires about 3000

transistors.) The measured performance is shown in Table 4 along with the data for an i7-4790 Haswell CPU. We used the above cited thermal efficiencies of the cryocooler to get the lower and upper bounds of power consumption and computation efficiency (in GFLOP per joule) at room temperature. Basically, we get the same result as above: RSFQbased FPA and FMP are 2 to 20 times less efficient than the off-shelf CPU, Table 4. The numbers reported in Ref. 69 correspond to the RSFQ circuits using bias resistors with significant static power dissipation. If this dissipation is eliminated by using, e.g., ERSFQ approach, the computation efficiency may improve by a factor of /C24 10, making the SFQ circuits competitive if implemented in a very large-scale system, but still losing in efficiency if used in a small-scale system.

If the average critical current in SFQ circuits can be reduced by a factor of five, to 35 l A, somehow keeping the acceptable bit error rate determined by the smallest junctions in the circuit, the total energy dissipation in complex SFQ circuits with account for refrigeration may become somewhat lower than in their CMOS counterparts. Note, however, that we have not accounted for any power consumption associated with auxiliary electronics, thermal radiation, and heat conduction via cryogenic cables.

A more optimistic estimate of computation efficiency of SFQ processors can be obtained by estimating naively the energy consumption per PFLOP, using the energy per single bit operation h ESBOP i estimated above. Depending on the circuit architecture, a 32-bit floating-point operation requires about 1500 single-bit operations (for adders) and somewhat more for multipliers. Then, the lower bound on the energy loss per FLOP at 4.2 K is h ESBOP i /C25 2000 h ESBOP i /C25 5 /C2 10 /C0 15 J, or 5 J per PFLOP, giving a computation efficiency of /C24 0.2 PFLOP/J at 4.2 K or from about 57 to 570 GFLOP/J at 300 K. This is from 25 to 250 times better than CMOS, see Table 4. Unfortunately, there are currently no architectural solutions to realize this ultimate computation efficiency because superconductor electronics does not have compact and efficient memory, whereas memory is abundant in semiconductor computers.

So, it follows from the estimates above that cryogenic computational systems based on the SFQ logic versions utilizing JJ switching and emulating CMOS architectures will likely be faster than the CMOS-based but not necessarily more energy efficient. This has a very simple reasonrequirements for switching elements used in any computing

TABLE 4. Power dissipation and performance of RSFQ 69 and CMOS floating-point processors.

| Unit    |   f cl (GHz) |   Throughput (GFLOPS) | Power at 4.2K (mW)   | Power dissipation at room- T (W)   | Efficiency at room-T (GFLOP/J)   |
|---------|--------------|-----------------------|----------------------|------------------------------------|----------------------------------|
| FPA     |           58 |                  2.23 | 4.92                 | 1.7-17 a                           | 0.13-1.3                         |
| FPM     |           59 |                  2.36 | 5.76                 | 2.0-20 a                           | 0.12-1.2                         |
| i7-4790 |            4 |                200    | …                    | 88                                 | 2.27                             |

system are basically the same and independent of the operating temperature. These are requirements of reliability, drivability, and communications: fast switching times /C24 1 ps, immunity to the thermal noise and parameter spreads (low bit error rates), and ability to drive other parts of the system and communicate with them. These requirements set the minimum ratio E sw /kBT , typically /C24 10, for the switches used in a computer, where T is its operating temperature. Then, of two computers operating with the same Esw/kBT ratio and having similar architectures, the one requiring refrigeration to T cold may become more energy efficient than a computer operating at T hot only if the refrigerator is nearly ideal, g /C21 1 /C0 T cold / T hot, which is not possible at cryogenic temperatures.

## 4.2 Adiabatic quantum flux parametron (AQFP) circuits

Among the superconducting digital technologies developed to date only AQFP circuits can be truly energy efficient. AQFP is the same QFP invented by E. Goto more than 30 years ago, see Refs. 83 and 84 and references therein, but operated in a slow (adiabatic) regime. 85,86 Instead of using JJ switching to move fluxons, as in RSFQ and RQL, the information in QFP is encoded by a fluxon location in a doublewell potential, in the left ('0') or the right ('1') well, and moved by adiabatically varying the shape of the potential, using ac bias currents. The measured energy dissipation at 5 GHz operation is extremely low, /C24 0.1 I c U 0 per bit 147 and can be further reduced. QFP is very similar in the operation principle to a much older device-parametric quantron. 148,149 Theoretically, these types of parametric devices can provide for the lowest energy consumption in computations. 150

Because parallel pipelining is very natural for AQFP, processors with higher computational efficiency than ERSFQ, RSFQ, and RQL can be designed. 151 According to estimates in Ref. 151, the computational energy efficiency of some algorithms implemented in AQFP could be 7 orders of magnitude higher, with account for refrigeration, than of CMOS circuits.

## 4.3 Summary

A very inquisitive reader may ask why our assessment of energy efficiency of RSFQ and RQL technologies for high-performance computing differs from the one made in Ref. 16, which indicated that RQL might be able to meet the efficiency requirement. The difference comes from simple arithmetic. In the simplistic estimate of the power required to compute 1 PFLOPS, see Eq. (1) in Ref. 16, the junction activity factor a was double-counted: the first time implicitly in the estimate of energy per switch in the RQL (1/3) h I c i U 0 , which already includes a ¼ 1/2; and the second time explicitly in the power estimate based on the number of gates per FLOPS. Also, in this estimate, the minimum critical current of JJs of 25 l A was used instead of the weighted average h I c i entering (16)-(19), which is typically a factor of two larger than the minimum I c . As a result the power per PFLOPS was probably underestimated by about a factor of four, and the energy efficiency was overestimated by the same amount. The use of the minimum I c in energyconsumption estimates is very typical for reviews of SCE; see, for example, Refs. 77, 79, and 118. It implies that a superconducting computer (circuit) can be built from the identical junctions having the minimum critical current and the minimum area. This could suffice for an order-of-magnitude estimate, but it is not a valid assumption.

## 5. Future work

The choice of the most promising directions of future work strongly depends on the strategic goals one wants to accomplish. In a limited funding environment, setting the priorities and optimizing the strategy should be done thoroughly because 'no one can have his cake and eat it too,' and diverting time, efforts, and funding toward one area may leave the other one starving, and so on. The author's selection is given below and should not be construed in any form as funding recommendations.

## 5.1 Energy-efficient computing

If the primary goal is energy efficiency, then a clear winner among the existing and relatively mature technologies is AQFP, because its energy consumption, including refrigeration can be made a few orders of magnitude lower than in the existing room-temperature technologies. However, the clock speed of truly energy-efficient AQFP circuits is limited to /C24 7 GHz. Due to the use of multiple transformers and ac power, the cell area is currently large and the integration density is low. The limits on the integration scale are the same as for other types of SCE as described in the previous sections. Unfortunately, there is currently no work on AQFP circuits for high-performance computing anywhere except Japan. Interestingly, however, most of the control circuitry in D-Wave quantum annealing processors operating at tens of mK is based on QFPs due to their ultralow power dissipation.

Even higher energy efficiency is promised by reversible (or almost reversible) computing. Ideas of reversible computing with superconducting circuits were discussed in Refs. 107-110. Simple circuits, shift registers, with energy-per-bit near the Landauer's thermodynamic limit kBT ln 2 have already been demonstrated. 110 Larger circuits with richer functionalities need to be developed and fabricated. Unfortunately, the progress in the area of superconducting reversible computing has been slow due to lack of funding.

As was shown above, the energy efficiency of SFQ processors utilizing junction switching and CMOS architectures, i.e., designed by replacing CMOS logic cells by SFQ logic cells, is marginal, and the energy saving may not be sufficient to warrant the effort. Therefore, the obvious way of making SFQ processors more energy efficient is to employ different information processing solutions and architectures that would require significantly fewer JJs than transistors to implement, and would not require external memories. These ideas have been discussed to some extent but require practical development. For instance, Semenov in Ref. 105 argued that RSFQ blocks should be implemented in a way that preserves their inherent logic and memory functions, and makes use of the simplicity and record-high speed of SFQ T-flipflops 106 instead of replicating CMOS logic cells. Interesting to note, the RSFQ technology inventors stated in their original comprehensive review 79 that 'a universal von-Neumanntype computer is probably the worst device for implementation using the RSFQ (or any other superfast) technology,'

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

and explain why. Somehow this message and the idea that RSFQ blocks with their logic/memory functions are cellular automata or finite-state machines rather than CMOStype logic gates were forgotten in the course of the last 25 years.

Unfortunately, the only idea that is being actively worked on is the most trivial one-reducing the average critical current h I c i in SFQ cells. This reduction has a clear limit /C24 50 l A, below which the circuit density, bit error rate, and circuit yield will be substantially compromised, and hence cannot be a long-term strategy. On this road, RQL has currently a big advantage because of the serial biasing. For instance, SFQ circuits with the largest JJ count per chip demonstrated so far have been the RQL shift registers 76 made by the MIT-LL SFQ4ee process. 28 It does not mean that RQL is a better technology however, only that its problems are in a different area. RSFQ-based circuits are clearly behind in JJ count due to the parallel biasing and associated problems. Therefore, the prime goals should be in developing serial-biasing (current recycling) solutions suitable for multimillion-JJ circuits. Without solving this problem, RSFQ-based circuits, in the author's opinion, have no future in high-performance computing or other applications requiring VLSI.

## 5.2 High-speed computing

On the other hand, if the primary goal is the computation speed, high clock frequency, and energy dissipation is secondary, then the technology selection and the development priorities are very different. RSFQ is clearly the fastest digital technology developed so far, and capable of reaching /C24 70 GHz clock frequencies in the current technology node and over 100 GHz if the Jc is increased to 0.5 mA/ l m 2 and beyond. Therefore, development of current recycling for VLSI circuits becomes the priority number one. Since resistive biasing has no place in superconductor VLSI due to heating, ERSFQ becomes a clear winner if its inductive biasing approach can be scaled up to the VLSI. RQL and AQFP circuits will probably lose the speed competition because of the multiphase ac biasing.

Design development priorities in this case are also different. Instead of reducing the critical current h I c i , it should be increased and optimized for junctions with higher Jc, increased to /C24 0.5 mA/ l m 2 and above, perhaps self-shunted JJs, which will likely have larger parameter spreads at the same sizes as the current tunnel junctions with Jc ¼ 100 l A/ l m 2 .

As priority number two, I would rate the development of new architectural solutions that do not copy the standard CMOS. It is the author's opinion that SCE electronics cannot win or even be competitive if it mimics CMOS, because of the five orders of magnitude difference in integration scale.

Number three on my list would be the development of fast and compact JJ-based memories that do not use magnetic materials and magnetic tunnel junctions discussed in Refs. 111-113, a development that may take many years. Josephson random access memories (RAM) have been demonstrated in older process nodes with large features and low RAM densities. 23,114,115,152 They should be improved and implemented in the advanced process nodes using more advanced materials and smaller features.

## 5.3 VLSI technology development

The main advantage of RSFQ-based processors is that they can run much faster (likely 25 times) than the 4 GHz offered by CMOS because energy dissipation on the chip is significantly reduced, see (17), (18), and moved instead to a much larger cryocooling system at room temperature. So, our hypothetical chip with 1.4B JJs can run at 100 GHz and dissipate only about 18 W at 4.2 K. The typical power that can be removed from the chip without raising its temperature more than 1 K in liquid He is /C24 1 W/cm 2 . So this chip can be cooled if its active area is larger than /C24 18 cm 2 . This should be an easy task because a SCE chip with 1.4B RSJs would have an area of 700 cm 2 at the present maximum density of 2M RSJs per cm 2 . A chip of this area is difficult to imagine and would be impossible to manufacture, so a superconducting multichip module (MCM) with about 200 of 2-cm 2 chips could be dreamed of as an equivalent. The required MCM technology with SFQ interchip communication data rates exceeding 100 GHz has been demonstrated; see Refs. 116 and 117 and references therein.

This example demonstrates that the development of VLSI technology for SCE trumps all the priorities mentioned above. Without solving the scalability problem, development of SFQ processors has no merit. Note that fabrication technology development and implementation of new materials and processes are usually much more expensive and time consuming than circuit design because the former requires expensive and sophisticated processing equipment whereas the latter requires only good ideas and engineers with CMOS-based computers. This simple truth was mainly ignored during the last 25 years.

Many ideas of what could be done have been floated around. I briefly review them in order to rate their impact on increasing the circuit density and feasibility of implementation. To be specific, let us set an increase in the circuit density by a factor of ten, i.e., achieving 2 /C2 10 7 cm /C0 2 density of JJs and inductors, as the primary near-term goal. (The author simply cannot imagine a 200-chip MCM for our 1.4B-JJ processor, but can imagine a 20-chip MCM.)

## 5.3.1. Self-shunted, high-Jc junctions

Getting rid of resistive shunts would have the largest impact on the circuit density, as is clear from Fig. 7, and would shorten the fabrication process by eliminating the resistor module, Fig. 5. This requires replacing the hysteretic SIS tunnel junctions with nonhysteretic junctions. In this context, we would like to clear up one of the misconceptions in this area, which appeared in Refs. 77, 119, and 153 and crept into many other publications. It is an incorrect assertion that all tunnel junctions become self-shunted at high Jc , e.g., /C24 100kA/cm 2 in the case of Nb-based junctions. This misconception is a result of a simple-minded application of the McCumber-Stewart 89,90 parameter b c ¼ 2 p IcR 2 n C = U 0, derived for a linear shunt resistor, to tunnel junctions with nonlinear, voltage-dependent, damping (2). Then, using RN as a damping resistance at all voltages, noting that the expression can be rewritten as b c ¼ 2 p ð IcRN Þ 2 Cs = ð Jc U 0 Þ , where Cs is the junction specific capacitance, and that Ic Rn is the electrode material property /C24 D / e , it may appear that b c /C20 1 can be obtained by mere increasing the Jc . This is, of course, incorrect because there are not enough electronic states at V &lt; Vg to provide damping (Rsg

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

/C29 RN ), and switching back into V ¼ 0 state is hysteretic. Therefore, self-shunting can be induced only by increasing the density of states in the gap or in the barrier allowing for a substantial ohmic conduction (junction 'leakage') at V &lt; Vg . This can be achieved by introducing defects in the tunnel barrier, e.g., pin-holes and oxygen vacancies, 120-124 or by using junction barriers with direct conduction such as normal metals, doped semiconductors, etc. However, high-quality tunnel junctions, e.g., using Nb2O5 and AlNx barriers instead of AlO x , remain highly hysteretic at Jc values much larger than 100 kA/ cm 2 . 125-127 This makes Nb/Al-AlN x /Nb tunnel junctions unattractive for VLSI applications requiring self-shunted JJs, although they are perfectly good junctions for SIS detector applications.

Among devices with direct conduction, relatively high values of Vc required for digital applications have been demonstrated by Nb-based junctions with amorphous Si barriers doped by various impurities creating deep levels near the middle of the band gap, like Nb, W, etc.; see Ref. 128, references therein, 129-131 and many older works, e.g., Refs. 132-134. From the author's point of view, their only advantage is that, at large levels of doping ( /C24 10%), self-shunting and nonhysteretic behavior is obtained. The other properties are rather drawbacks. Their Vc s are inferior to Nb/AlO x /Nb junctions at the same Jc, and the temperature dependence of the critical current is stronger than in SIS junctions. The self-shunting in these devices is likely due to inelastic and resonance tunneling via multiple localized sates, percolation paths, within the barrier. 128,135 As a result of this unusual conduction mechanism, the I-V characteristics are nonlinear and deviate from the RCSJ model; the devices also have unusually high specific capacitance, which is larger than in SIS devices. The circuit clock speeds based on these devices are also reduced by /C24 30% with respect to the same circuits made with SIS junctions. 130 It is not clear whether a -Sidoped devices are reproducible at submicron dimensions required for their implementation in VLSI circuits, because of the percolation-type current transport and possible fluctuations in the number of localized centers and resonant paths. A good uniformity of a -Si:Nb barriers in voltage standard applications was demonstrated using JJs with areas of hundreds of square micrometers. These data cannot be projected onto submicron-scale devices.

Therefore, the most important task is to evaluate the critical current spreads of a -Si-doped JJs with submicron dimensions at critical current densities in the range from 0.1 mA/ l m 2 to about 1 mA/ l m 2 by using the modern processing tools similar to the one used in Refs. 28-30. Somehow this has not been done despite these junctions being around for over 35 years. (Sperry Corporation was trying to commercialize superconducting devices and circuits using Nb and NbN junctions with doped a -Si, a -Ge, and Si-Ge barriers in the 1980s.) The same comment applies to highJc Nb/AlO x -Al/Nb junctions. Their subgap transport is due to multiple Andreev reflections via defects, most likely oxygen vacancies, in the barrier. So they could be viewed as approaching the metal-insulator transition from the opposite side than a -Si-doped barriers. There has been a claim that, at highJc , the transport mechanism in Nb/AlO x -Al/Nb junctions becomes universal, 136 so the junction-to-junction variations could be small. However, the experimental basis for this is about 200 highJc JJs studied in Refs. 92 and 137, which is not sufficient to build a VLSI technology on. So, the nearterm goals should be the evaluation of 2 junctions with Jc ¼ 0.5 mA/ l m 2 , five times larger than it is in the SFQ5ee process, in order to measure their parameter spreads and selfshunting.

One of the drawbacks of all compact self-shunted JJs is self-heating. Heating in the RSJs is negligible because the ESW is dumped into the resistor whose area is much larger than the JJ area. In the self-shunted JJs the same energy dissipates inside the junction and creates nonequilibrium quasiparticles. Energy density and heating increase with increasing Jc. The maximum clock frequency of these devices may then be determined by the energy relaxation rate in order to prevent memory effects and time jitter associated with the influence of one switching on the next and difference in activity factors in different parts of the circuit.

## 5.3.2 Number of junction layers

Increasing the number of independent JJ layers to two is beneficial and may increase the JJ density by a factor of 2 /C2 . The work in this direction is currently underway at AIST in Japan. A larger increase would likely have no proportional effect on the density because of the need for interconnecting and through vias reducing the available area.

## 5.3.3 Compact inductors

The next in importance is the increase in inductor density nL . This can be done by decreasing their area, increasing the inductance per unit length, and increasing the number of layers, mL . Increasing mL above two will have little impact because of the vias and cross-talk problems. At small spacing between the inductors /C24 0.25 l m, the crosstalk between the inductors on the same layer or between the layers becomes significant. So the inductors must be isolated by the ground planes and vias between them, boxed into a coaxialtype configuration. This reduces the maximum density and defeats the purpose.

Let us take as an example, the average inductor in the cells of the ac-biased shift register in Refs. 75 and 99 and shown in Fig. 12. Its value is about 6 pH, and in the current process it occupies the area of /C24 8.5 l m 2 . A factor of ten increase in nL means that its area needs to be reduced to /C24 0.85 l m 2 . This can be achieved by using a thin layer of a high-kinetic-inductance material like MoN x or NbN x for signal inductors, similar to our SFQ5ee process for bias inductors. 30 It is well known that the kinetic inductance of thin superconducting films Lk ¼ l 0 k 2 /t is much larger that their geometric inductance if k /C29 t and k 2 / t /C29 w, where k is magnetic field penetration depth, t and w are the film thickness and width, respectively. The kinetic-inductor layer can be placed in a close proximity to JJs, e.g., between layers J5 and M6 instead of the layer of resistors, R5 in Fig. 2, since with self-shunted JJs resistive shunts will no longer be required. The I c of this kinetic inductor should be a factor of 2 /C2 larger than I c of JJs, or about 0.25 mA. Then, using a typical value of inductance per square of /C24 5 pH/sq, e.g., for a 60-nm-thick MoN x film, and the film width of 0.5 l m to guarantee the critical current, the kinetic inductor length will be 0.6 l m and the area, accounting for a 0.25l m line

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

spacing, will be about 0.5 l m 2 . Adding vias to the inductor will double the area. A compact via process has been demonstrated. 138 So one layer of kinetic inductors near the selfshunted JJs can increase the circuit density by a factor of ten, and two layers by a factor of /C24 20 /C2 .

The use of kinetic inductors does not help in reducing the area of inductive couplers and transformers in RQL and AQFP circuits, which depend on the geometric mutual inductance. The author has no readily available solutions for increasing the density of RQL and AQFP circuits by a factor of ten, except for reducing the minimum linewidth and spacing of inductors down to /C24 100 nm.

## 5.3.4 JJs as inductors

Nonswitching Josephson junctions can be used as circuit inductors. This idea is very old, but so far has been only implemented in superconducting persistent-current qubits 139,140 and their advanced versions, 141 and in tunable rf filters. 142 A segment of Josephson transmission line with JJs replacing all inductors would look like the one shown in Fig. 13.

The area saving can only be achieved if a vertical stack of inductor junctions is used. In order to preserve the design of all main SFQ cells, the minimum number of junctions in the stack should be three. Then, a quantizing inductor with a 2 p total phase shift can be formed using two LJ units shown in Fig. 13 (top panel). The phase across each JJ in the stack will be /C24 p /3, far enough from p /2 when the critical current is reached. We would like to term a switching JJ and three stacked nonswitching inductor-JJs a complementary pair, or a CLJJ pair, as shown in Fig. 13. Accordingly, circuits built using this technology can be termed complementary-SFQ circuits or CSFQ circuits.

Since there is no switching speed requirement for the inductor-junctions in the stack, the Vc of the junctions can be lower than of the switching JJs. Then, a much simpler technology of SNS junctions can be used to form the stack, where N is a normal metal compatible with the process, e.g., Al, Mo, Ti, etc. No doped a -Si or other fancy barriers are required. They could also be used, but are not necessary.

The ability to apply bias and signal at the point between the JJ and LJ is important and shown explicitly in the circuit diagrams. The fabrication process can be sketched briefly as shown in Fig. 14.

FIG. 13. A complementary JJ-inductor pair, a CLJJ pair, formed by a junction and a vertical stack of three nonswitching JJs, LJ. The ability to apply bias and signals at the point between the JJ and LJ is important and shown explicitly in the circuit diagrams in the top panel. Bottom panel: a segment of Josephson transmission line (JTL) using CLJJ pairs, i.e., with all inductors replaced by series arrays of nonswitching Josephson junctions LJ . The switching junctions are J1, J2, etc., I b is the bias current.

<!-- image -->

FIG. 14. A process for making complementary LJ-JJ pairs, CLJJ pairs: regular JJs coupled to inductors formed by three stacked nonswitching JJs. After finishing the switching JJ planarization step, see Fig. 4(h), the resistor module in Fig. 5 can be abandoned because we plan to use self-shunted JJs. Then, a wiring layer M6 will be deposited and patterned (b). After M6 planarization by the dielectric CMP, a multilayer Nb-M-Nb-M-Nb-M-Nb will be deposited on the planar surface and patterned to form a vertical stack of three JJs, LJ , where M is the barrier metal (c). Finally all LJ stacks will be planarized to their tops, similar to the JJ planarization described in the text. Top wiring will be deposited and patterned to interconnect the JJ-inductors, not shown here.

<!-- image -->

The typical critical current of nonswitching JJs, I cL can be estimated from the typical value of b L /C24 2, using instead of magnetic inductance L the Josephson (kinetic) inductance LJ ¼ 3 U 0 /(2 p ICL ), which gives ICL ¼ (3/ b L ), or I cL /C24 1.5 I c . To satisfy our 10 /C2 density increase requirement, the LJ area should be less than 1 l m 2 , so the critical current density of nonswitching JJs should be larger than 100 l A/ l m 2 .

The process shown in Fig. 14 would be relatively easy to implement. However, the drawback of replacing thin-film inductors with JJ-inductors is that a very simple and highly reliable device-a narrow strip of high-kinetic-inductance material-is replaced by much more complex and less reliable devices using a multilayered stack of JJs. The JJs in the stack need to have (nearly) identical critical currents. This is a serious complication of the process and a potential impediment to the process reliability and yield. Moreover, implementation of CLJJ pairs does not solve the problem of miniaturization of inductive couplers and transformers in RQL and AQFP circuits.

## 5.3.5 Phase shifters and pi-junctions

The use of phase shifters based on pi-junctions with ferromagnetic barriers has been discussed and demonstrated in Refs. 143-145. Despite their useful features and interesting physics, adding pi-junctions would have a negative impact on the circuit density, because the critical current density of pi-junctions is a factor of /C24 100 lower than in regular 0-junctions and their area accordingly is a 100 /C2 times larger. The existing advanced fabrication processes have so many superconducting layers that this function (phase shifting) could be easily realized by using a miniature rings and narrow wires to provide magnetic bias; see, e.g., Ref. 146.

## 6. Conclusion

In order to evaluate whether SFQ electronics is scalable to VLSI levels required for achieving computation complexities comparable to CMOS processors, we have reviewed the current state of the fabrication technology for superconducting digital circuits based on single-flux-quantum encoding of information. We have described the limitations imposed on

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

the circuit density by Josephson junctions, circuit inductors, shunt and bias resistors, parameter spreads, etc. We have shown that the currently achievable maximum circuit density of resistively shunted Josephson junctions and inductors is about 2 /C2 10 6 cm /C0 2 , which is almost four orders of magnitude lower than the density of transistors in modern CMOS circuits.

We have described the fabrication-process development required for increasing the density of SFQ digital circuits by a factor of ten, including self-shunted Josephson junctions, kinetic inductors, complementary JJ-inductor pairs (CLJJ) using Josephson inductance of stacked, nonswitching junctions, etc. Energy dissipation in superconducting circuits has been also reviewed in order to estimate whether SFQ electronics, which requires cryogenic refrigeration, can be energy efficient in comparison with CMOS. We estimated that energy dissipation in SFQ circuits based on JJ switching, such as RSFQ, ERSFQ, RQL, and having comparable complexity to the modern CMOS processors will be comparable to that in CMOS processors when refrigeration energy is taken into account.

The energy efficiency can be improved if innovative circuit architectures could be developed, which use much fewer JJs than transistors for the same information processing and have minimum use of external memories. The most energy efficient technology is adiabatic quantum-flux parametron (AQFP), which can run at /C24 7 GHz clock frequency. RSFQ and its 'energy efficient' versions remain the fastest digital superconductor technology capable of clock frequencies over 100 GHz, if energy efficiency is not a primary goal. However, it cannot be scaled to VLSI until serial-biasing and current-recycling VLSI technology are developed. The main scalability problem of SFQ digital electronics stems from its advantages-magnetic flux information encoding and SFQ voltage pulse transferring, resulting in large-area SFQ cells. It is clear that confining magnetic flux takes much larger volume and effort than confining charge in the gates of CMOS transistors. As a result, the complexity of SCE digital electronics is expected to remain relatively low unless unforeseen breakthroughs happen.

Superconductor electronics has many advantages in applications where the cryogenic environment is mandatory and dictated by the system performance requirements that cannot be met by any other means. For instance: as control electronics and cryogenic data processors for very large arrays of cryogenic sensors; control electronics for analog quantum computing based on superconducting quantum annealers; for gate-based quantum computing with superconducting qubits; and for application-specific ultrafast circuits. There is no doubt that (nearly) reversible superconducting circuits, approaching and crossing the thermodynamic limit, will soon be demonstrated as well as many other interesting circuits. However, the impact of SFQ electronics on generalpurpose and high-performance computing, in my opinion, will remain low in the foreseeable future because of the insufficient scale of integration.

I am very grateful to all my colleagues at MIT Lincoln Laboratory who are involved with fabrication process development for superconductor electronics, especially to Vladimir Bolkhovsky and Scott Zarr, to Terry Weir and Alex Wynn for their part in device testing, and to Mark Gouker and Leonard Johnson for the discussions and management of the program. I would like to thank Vasili K. Semenov, Alex F. Kirichenko, Timur Filippov, Quentin Herr, Marc Manheimer, and D. Scott Holmes for useful discussions. My special thanks are to Daniel E. Oates for reading the manuscript and suggesting numerous improvements.

This research was based upon work supported by the Office of the Director of National Intelligence (ODNI), Intelligence Advanced Research Projects Activity (IARPA), via Air Force Contract FA872105C0002. The views and conclusions contained herein are those of the author and should not be interpreted as necessarily representing the official policies or endorsements, either expressed or implied, of the ODNI, IARPA, or the U.S. Government. The U.S. Government is authorized to reproduce and distribute reprints for Governmental purposes notwithstanding any copyright annotation thereon.

a) Email: sergey.tolpygo@ll.mit.edu

1 K. B. Tolpygo, 'K stoletiyu so dnya rozhdeniya,' Fiz. Tv. Tela 58 , 1036 (2016).

2 V. V. Rumyanysev and K. V. Gumennyk, J. Photonic Mater. Technol. 1 , 1 (2015).

3 A. A. Borgardt, Fiz. The. Vysokih Davleniy 11 (4), 19 (2001); A. A. Borgardt and V. A. Telezhkin, ibid. 6 (3), 7 (1996).

4 K. B. Tolpygo, Ukr. Fiz. Z. 36 , 1279 (1991).

5 A. A. Galkin, Z. S. Gribnikov, S. I. Pekar, E. I. Rashba, O. V. Snitko, and V. I. Sheka, Fiz. Tv. Tela 10 , 6 (1976).

6 K. B. Tolpygo, Stud. Biophys. 69 , 35 (1978).

7 K. B. Tolpygo, Biofizika 27 , 95 (1982).

- 8 V. A. Telezhkin, K. B. Tolpygo, and S. K. Tolpygo, Ukr. Fiz. Z. 24 , 1679 (1979).
- 9 S. V. Bespalova, V. A. Telezhkin, K. B. Tolpygo, and S. K. Tolpygo, Ukr. Fiz. Z. 25 , 1858 (1980).

10 K. B. Tolpygo, J. Mol. Struct. 299 , 185 (1993).

- 11 S. V. Bespalova and K. B. Tolpygo, J. Mol. Struct. 291 , 245 (1991).
- 12 S. V. Bespalova and K. B. Tolpygo, J. Math. Chem. 18 , 179 (1995).
- 13 R. F. Service, Science 335 , 394 (2012).
- 14 See www.top500.org for Top500.
- 15 See www.green500.org for The Green500 List.
- 16 D. S. Holmes, A. L. Ripple, and M. A. Manheimer, IEEE Trans. Appl. Supercond. 23 (3), 1701610 (2013).
- 17 F. Bedard, N. Welker, G. R. Gotter, M. A. Escavage, and J. T. Pinkston, Superconducting Technology Assessment (National Security Agency Office Corp. Assessments, Fort Meade, MD, USA, 2005).
- 18 M. A. Manheimer, IEEE Trans. Appl. Supercond. 25
- (3), 1301704 (2015). 19 L. S. Yu, C. J. Berry, R. E. Drake, K. Li, R. M. Patt, M. Radparvar, S. R.
- Whitley, and S. M. Faris, IEEE Trans. Magn. 23 , 1476 (1987).
- 20 D. Yohannes, S. Sarwana, S. K. Tolpygo, A. Sahu, Yu. A. Polyakov, and V. K. Semenov, IEEE Trans. Appl. Supercond. 15 (2), 90 (2005).
- 21 D. Yohannes, A. Kirichenko, S. Sarwana, and S. K. Tolpygo, IEEE Trans. Appl. Supercond. 17 (2), 181 (2007).
- 22 S. K. Tolpygo, D. Yohannes, R. T. Hunt, J. A. Vivalda, D. Donnelly, D. Amparo, and A. F. Kirichenko, IEEE Trans. Appl. Supercond. 17 (2), 946 (2007).
- 23 S. Nagasawa, Y. Hashimota, H. Numata, and S. Tahara, IEEE Trans. Appl. Supercond. 5 (2), 2447 (1995).
- 24 H. Numata and S. Tahara, IEICE Trans. Electron. E84-C , 2 (2001).
- 25 S. Nagasawa, K. Hinode, T. Satoh, H. Akaike, Y. Kitagawa, and M. Hidaka, Physica C 412-414 , 1429 (2004).
- 26
- A. Fujimaki, K. Takagi, N. Takagi, and N. Yoshikawa, Physica C 469 1578 (2009).
- S. Nagasawa, T. Satoh, K. Hinode, Y. Kitagawa, M. Hidaka, H. Akaike, ,
- 27 S. Nagasawa, K. Hinode, T. Satoh, M. Hidaka, H. Akaike, A. Fujimaki, N. Yoshikawa, S. Nagasawa, K. Takagi, and N. Takagi, IEICE Trans. Electron. E97-C (3), 132 (2014).
- 28 S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, L. M. Johnson, M. A. Gouker, and W. D. Oliver, IEEE Trans. Appl. Supercond. 25 (3), 1101312 (2015).
- 29 S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, C. J. Galbraith, L. M. Johnson, M. Gouker, and V. K. Semenov, IEEE Trans. Appl. Supercond. 25 (3), 1100905 (2015).

Reuse of AIP Publishing content is subject to the terms at: https:/publishing.aip.org/authors/rights-and-permissions. Download to IP:  129.55.20.20 On: Wed, 01 Jun 2016

- 30 S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, A. Wynn, D. E. Oates, L. M. Johnson, and M. A. Gouker, IEEE Trans. Appl. Supercond. 26 (3), 1100110 (2016).
- 31 M. W. Johnson, P. Bunyk, F. Maibaum, E. Tolkacheva, A. J. Berkley, E. M. Chapple, R. Harris, J. Johansson, T. Lanting, H. Perminov, E. Ladizinsky, T. Oh, and G. Rose, Supercond. Sci. Technol. 23 (6), 065004 (2010).
- 32 R. Harris, J. Johnson, A. J. Berkley, M. W. Johnson, T. Lanting, S. Han, P. Bunyk, E. Ladizinsky, T. Oh, I. Perminov, E. Tolkacheva, S. Uchaikin, E. M. Chapple, C. Enderud, C. Rich, M. Thom, J. Wang, B. Wilson, and G. Rose, Phys. Rev. B 81 , 134510 (2010).
- 33 P. I. Bunyk, E. M. Hoskinson, M. W. Johnson, E. Tolkacheva, F. Altomare, A. J. Berkley, R. Harris, J. P. Hilton, T. Lanting, A. J. Przybysz, and J. Whittaker, IEEE Trans. Appl. Supercond. 24 (4), 1700110 (2014).
- 34 T. Lanting, A. J. Przybysz, A. Yu. Smirnov, F. M. Spedalieri, M. H. Amin, A. J. Berkley, R. Harris, F. Altomare, S. Boixo, P. Bunyk, N. Dickson, C. Enderud, J. P. Hilton, E. Hoskinson, M. W. Johnson, E. Ladizinsky, N. Ladizinsky, R. Neufeld, T. Oh, I. Perminov, C. Rich, M. C. Thom, E. Tolkacheva, S. Uchaikin, A. B. Wilson, and G. Rose, Phys. Rev. X 4 , 021041 (2014).
- 35 O. A. Mukhanov, IEEE Trans. Appl. Supercond. 3 (1), 2578 (1993).
- 36 O. A. Mukhanov, IEEE Trans. Appl. Supercond. 3 (4), 3102 (1993).
- 37 O. A. Mukhanov and A. F. Kirichenko, IEEE Trans. Appl. Supercond. 5 (2), 2461 (1995).
- 38 S. V. Rylov and R. P. Robertazzi, IEEE Trans. Appl. Supercond. 5 (2), 2260 (1995).
- 39 A. F. Kirichenko, V. K. Semenov, Y. K. Kwong, and V. Nadakumar, IEEE Trans. Appl. Supercond. 5 (2), 2857 (1995).
- 40 S. B. Kaplan, A. F. Kirichenko, O. A. Mukhanov, and S. Sarwana, IEEE Trans. Appl. Supercond. 11 (1), 513 (2001).
- 41 O. A. Mukhanov, V. K. Semenov, W. Li, T. V. Filippov, D. Gupta, A. M. Kadin, D. K. Brock, A. K. Kirichenko, Y. A. Polyakov, and I. V. Vernik, IEEE Trans. Appl. Supercond. 11 (1), 601 (2001).
- 42 A. Kirichenko, S. Sarwana, D. Gupta, I. Rochwarger, and O. Mukhanov, IEEE Trans. Appl. Supercond. 13 (2), 454 (2003).
- 43 D. Gupta, T. V. Filippov, A. F. Kirichenko, D. E. Kirichenko, I. V. Vernik, A. Sahu, S. Sarwana, P. Shevchenko, A. Talalaevskii, and O. A. Mukhanov, IEEE Trans. Appl. Supercond. 17 (2), 430 (2007).
- 44 I. V. Vernik, D. E. Kirichenko, T. V. Filippov, A. Talalaevskii, A. Sahu, A. Inamdar, A. F. Kirichenko, D. Gupta, and O. A. Mukhanov, IEEE Trans. Appl. Supercond. 17 (2), 442 (2007).
- 45 A. Sahu, T. V. Filippov, and D. Gupta, IEEE Trans. Appl. Supercond. 19 (3), 585 (2009).
- 46 A. Inamdar, S. Rylov, A. Talalaevskii, A. Sahu, S. Sarwana, D. E. Kirichenko, I. V. Vernik, T. V. Filippov, and D. Gupta, IEEE Trans. Appl. Supercond. 19 (3), 670 (2009).
- 47 T. V. Filippov, M. Dorojevets, A. Sahu, A. Kirichenko, C. Ayala, and O. Mukhanov, IEEE Trans. Appl. Supercond. 21 (3), 847 (2011).
- 48 A. F. Kirichenko, I. V. Vernik, J. A. Vivalda, R. T. Hunt, and D. T. Yohannes, IEEE Trans. Appl. Supercond. 25 (3), 1300505 (2015).
- 49 S. Nagasawa, Y. Hashimoto, H. Numata, and S. Tahara, IEEE Trans. Appl. Supercond. 5 (2), 2447 (1995).
- 50 M. Ito, K. Kawasaki, N. Yoshikawa, A. Fujimaki, H. Terai, and S. Yorozu, IEEE Trans. Appl. Supercond. 15 (2), 255 (2005).
- 51 T. Yamada, M. Yoshida, T. Hanai, A. Fujimaki, H. Hayakawa, Y. Kameda, S. Yorozu, H. Terai, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 15 (2), 324 (2005).
- 52 Y. Hashimoto, S. Yorozu, Y. Kameda, A. Fujimaki, H. Terai, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 15 (2), 356 (2005).
- 53 M. Tanaka, T. Kondo, N. Nakajima, T. Kawamoto, Y. Kamiya, and A. Fujimaki, IEEE Trans. Appl. Supercond. 15 (2), 400 (2005).
- 54 Y. Kameda, S. Yorozu, Y. Hashimoto, H. Terai, A. Fujimaki, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 15 (2), 423 (2005).
- 55 K. Fujiwara, N. Nakajima, T. Nishigai, M. Ito, N. Yoshikawa, A. Fujimaki, H. Terai, and S. Yorozu, IEEE Trans. Appl. Supercond. 15 (2), 427 (2005).
- 56 K. Saitoh and F. Furuta, IEEE Trans. Appl. Supercond. 15 (2), 445 (2005).
- 57 Y. Yamanashi, M. Tanaka, A. Akimoto, H. Park, Y. Kamiya, N. Irie, N. Yoshikawa, A. Fujimaki, H. Terai, and Y. Hashimoto, IEEE Trans. Appl. Supercond. 17 (2), 474 (2007).
- 58 H. Park, Y. Yamanashi, K. Taketomi, N. Yoshikawa, M. Tanaka, K. Obata, Y. Ito, A. Fujimaki, N. Takagi, K. Takagi, and S. Nagasawa, IEEE Trans. Appl. Supercond. 19 (3), 634 (2009).
- 59 H. Hara, K. Obata, H. Park, Y. Yamanashi, K. Taketomi, N. Yoshikawa, M. Tanaka, A. Fujimaki, N. Takagi, K. Takagi, and S. Nagasawa, IEEE Trans. Appl. Supercond. 19 (3), 657 (2009).
- 60 I. Kataeva, H. Akaike, A. Fujimaki, N. Yoshikawa, N. Takagi, K. Inoue, H. Honda, and K. Murakami, IEEE Trans. Appl. Supercond. 19 (3), 665 (2009).
- 61 I. Kataeva, H. Akaike, A. Fujimaki, N. Yoshikawa, S. Nagasawa, and N. Takagi, IEEE Trans. Appl. Supercond. 19 (3), 809 (2009).
- 62 F. Miyaoka, T. Kainuma, Y. Shimamura, Y. Yamanashi, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 21 (3), 823 (2011).
- 63 T. Kainuma, Y. Shimamura, F. Miyaoka, Y. Yamanashi, N. Yoshikawa, A. Fujimaki, K. Takagi, N. Takagi, and S. Nagasawa, IEEE Trans. Appl. Supercond. 21 (3), 827 (2011).
- 64 R. Nakamoto, S. Sakuraba, T. Sato, and K. Nakajima, IEEE Trans. Appl. Supercond. 21 (3), 852 (2011).
- 65 M. Dorojevets, C. L. Ayala, N. Yoshikawa, and A. Fujimaki, IEEE Trans. Appl. Supercond. 23 (3), 1700605 (2013).
- 66 M. Dorojevets, A. K. Kasperek, N. Yoshikawa, and A. Fujimaki, IEEE Trans. Appl. Supercond. 23 (3), 1300104 (2013).
- 67 M. Dorojevets, C. L. Ayala, N. Yoshikawa, and A. Fujimaki, IEEE Trans. Appl. Supercond. 23 (3), 1700104 (2013).
- 68 M. Hidaka, S. Nagasawa, K. Hinode, and T. Satoh, IEEE Trans. Appl. Supercond. 23 (3), 1100906 (2013).
- 69 X. Peng, Q. Xu, T. Kato, Y. Yamanashi, N. Yoshikawa, A. Fujimaki, N. Takagi, K. Takagi, and M. Hidaka, IEEE Trans. Appl. Supercond. 25 (3), 1301106 (2015).
- 70 Y. Sakashita, Y. Yamanashi, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 25 (3), 1301205 (2015).
- 71 X. Peng, Y. Shimamura, Y. Yamanashi, N. Yoshikawa, A. Fujimaki, K. Takagi, N. Takagi, and M. Hidaka, in Proceedings of 14th International Superconductive Electronics Conference, ISEC'2013, Cambridge, Massachusetts, July 7-11 (2013), p. 35.
- 72 T. Kato, Y. Yamanashi, N. Yoshikawa, A. Fujimaki, Takagi, K. Takagi, and S. Nagasawa, in Proceedings of 14th International Superconductive Electronics Conference, ISEC'2013, Cambridge, Massachusetts, July 7-11 (2013), p. 56.
- 73 A. Akitomo, Y. Yamanashi, and N. Yoshikawa, in Proceedings of 14th International Superconductive Electronics Conference, ISEC'2013, Cambridge, Massachusetts, July 7-11 (2013), p. 102.
- 74 M. Tanaka, K. Takata, R. Sato, A. Fujimaki, T. Kawaguchi, Y. Ando, K. Takagi, N. Takagi, and N. Yoshikawa, in Proceedings of 15th International Superconductive Electronics Conference, ISEC'2015, Nagoya, Japan, July 6-9 (2015), p. DS-001-INV.
- 75 V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, IEEE Trans. Appl. Supercond. 25 , 1301507 (2015).
- 76 Q. P. Herr, J. Osborne, M. J. A. Stoutimore, H. Hearne, R. Selig, J. Vogel, E. Min, V. V. Talanov, and A. Y. Herr, Supercond. Sci. Technol. 28 , 124003 (2015).
- 77 P. Bunyk, K. Likharev, and D. Zinoviev, Int. J. High Speed Electron. Syst. 11 , 257 (2001).
- 78 K. K. Likharev, O. A. Mukhanov, and V. K. Semenov, IEEE Trans. Magn. 23 , 759 (1987).
- 79 K. K. Likharev and V. K. Semenov, IEEE Trans. Appl. Supercond. 1 (1), 3 (1991).
- 80 D. F. Kirichenko, S. Sarwana, and A. F. Kirichenko, IEEE Trans. Appl. Supercond. 21 (3), 776 (2011).
- 81 M. H. Volkmann, A. Sahu, C. J. Fourie, and O. A. Mukhanov, Supercond. Sci. Technol. 26 (1), 015002 (2013).
- 82 Q. P. Herr, A. Y. Herr, O. T. Oberg, and A. G. Ioannidis, J. Appl. Phys. 109 , 103903 (2011).
- 83 M. Hosoya, W. Hioe, J. Casas, R. Kamikawai, Y. Harada, Y. Wada, H. Nakane, R. Suda, and E. Goto, IEEE Trans. Appl. Supercond. 1 (2), 77 (1991).
- 84 Y. Harada, H. Nakane, N. Miyamoto, U. Kawabe, E. Goto, and T. Soma, IEEE Trans. Magn. 23 , 3801 (1987).
- 85 N. Takeuchi, D. Ozawa, Y. Tamanashi, and N. Yoshikawa, Supercond. Sci. Technol. 26 (3), 035010 (2013).
- 86 K. Inoue, N. Takeuchi, K. Ehara, Y. Yamanashi, and N. Yoshikawa, IEEE Trans. Appl. Supercond. 23 (3), 1301105 (2013).
- 87 L. A. Abelson and G. L. Kerber, Proc. IEEE 92 , 1517 (2004).
- 88 M. Gurvitch, M. A. Washington, and H. A. Huggins, Appl. Phys. Lett. 42 , 472 (1983).
- 89 D. E. McCumber, J. Appl. Phys. 39 , 3113 (1968).
- 90 W. C. Stewart, Appl. Phys. Lett. 12 , 277 (1968).
- 91 RSFQ @ SUNY Stony Brook.
- 92 V. Patel and J. E. Lukens, IEEE Trans. Appl. Supercond. 9 (2), 3247 (1999).
- 93 A. V. Rylyakov and K. K. Likharev, IEEE Trans. Appl. Supercond. 9 (2), 3539 (1999).

- 94 V. K. Semenov and M. A. Voronova, IEEE Trans. Magn. 23 , 1476 (1987).
- 95 V. Semenov and Y. Polyakov, IEEE Trans. Appl. Supercond. 11 (1), 550 (2001).
- 96 J. H. Kang and S. B. Kaplan, IEEE Trans. Appl. Supercond. 13 (2), 547 (2003).
- 97 T. V. Filippov, A. Sahu, S. Sarwana, D. Gupta, and V. K. Semenov, IEEE Trans. Appl. Supercond. 19 (3), 580 (2009).
- 98 M. Igarashi, Y. Yamanashi, N. Yoshikawa, Kan Fujiwara, and Yoshihito Hashimoto, IEEE Trans. Appl. Supercond. 19 (3), 649 (2009).
- 99 V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, ASC (unpublished).
- 100 B. D. Josephson, Phys. Lett. 1 , 251 (1962).
- 101 R. Landauer, IMB J. Res. Dev. 5 , 183 (1961).
- 102 List of CPU power dissipation figures.
- 103 Transistor count.
- 104 M. Dorojevets, Z. Chen, C. L. Ayala, and A. K. Kasperek, IEEE Trans. Appl. Supercond. 25 (3), 1300408 (2015).
- 105 V. K. Semenov, IEEE Trans. Appl. Supercond. 23 (3), 1700908 (2011).
- 106 W. Chen, A. V. Rylyakov, V. Patel, J. E. Lukens, and K. K. Likharev, Appl. Phys. Lett. 73 , 2817 (1998).
- 107 V. K. Semenov, G. V. Danilov, and D. V. Averin, IEEE Trans. Appl. Supercond. 13 (2), 938 (2003).

108

V. K. Semenov, G. V. Danilov, and D. V. Averin, IEEE Trans. Appl.

Supercond.

17

(2), 455 (2007).

- 109 J. Ren, V. K. Semenov, Y. A. Polyakov, V. Averin, and J.-S. Tsai, IEEE Trans. Appl. Supercond. 19 (3), 961 (2009).
- 110 J. Ren and V. K. Semenov, IEEE Trans. Appl. Supercond. 21 (3), 780 (2011).
- 111 K. Senapati, M. G. Blamire, and Z. H. Barber, Nat. Mater. 10 , 849 (2011).
- 112 V. Ryazanov, V. V. Bol'ginov, D. S. Sobanin, I. V. Vernik, S. K. Tolpygo, A. M. Kadin, and O. A. Mukhanov, Phys. Proc. 36 , 35 (2012).
- 113 T. A. Larkin, V. V. Bol'ginov, V. S. Stolyarov, V. V. Ryazanov, I. V. Vernik, S. K. Tolpygo, and O. A. Mukhanov, Appl. Phys. Lett. 100 , 222601 (2012).
- 114 S. Nagasawa, K. Hinode, T. Satoh, Y. Kitagawa, and M. Hidaka, Supercond. Sci. Technol. 19 , S325 (2006).
- 115 S. Nagasawa, T. Satoh, Y. Kitagawa, and M. Hidaka, IEEE Trans. Appl. Supercond. 17 (2), 177 (2007).
- 116 S. K. Tolpygo, D. Tolpygo, R. T. Hunt, S. Narayana, Y. A. Polyakov, and V. K. Semenov, IEEE Trans. Appl. Supercond. 19 (3), 598 (2009).
- 117 S. Narayana, V. K. Semenov, Y. A. Polyakov, V. Dotsenko, and S. K. Tolpygo, Supercond. Sci. Technol. 25 , 105012 (2012).
- 118 O. Mukhanov, IEEE Trans. Appl. Supercond. 21 (3), 760 (2011).
- 119 D. K. Brock, A. M. Kadin, A. F. Kirichenko, O. A. Mukhanov, S. Sarwana, J. A. Vivalda, W. Chen, and J. E. Lukens, IEEE Trans. Appl. Supercond. 11 (2), 369 (2001).
- 120 R. E. Miller, W. H. Mallison, A. W. Kleinsasser, K. A. Delin, and E. M. Macedo, Appl. Phys. Lett. 63 , 1423 (1993).
- 121 A. W. Kleinsasser, R. E. Miller, W. H. Mallison, and G. B. Arnold, Phys. Rev. Lett. 72 , 1738 (1994).
- 122 A. W. Kleinsasser, IEEE Trans. Appl. Supercond. 11 (1), 1043 (2001).
- 123 S. K. Tolpygo, D. J. C. Amparo, R. T. Hunt, J. A. Vivalda, and D. T. Yohannes, IEEE Trans. Appl. Supercond. 23 (3), 1100305 (2013).
- 124 S. K. Tolpygo and D. Amparo, J. Appl. Phys. 104 , 063904 (2008).
- 125 A. W. Kleinsasser and R. A. Burhman, Appl. Phys. Lett. 37 , 841 (1980).
- 126 A. W. Kleinsasser, W. H. Mallison, and R. E. Miller, IEEE Trans. Appl. Supercond. 5 (2), 2318 (1995).
- 127 G. L. Kerber, A. W. Kleinsasser, and B. Bumble, IEEE Trans. Appl. Supercond. 19 (3), 159 (2009).
- 128 A. L. Gudkov, M. Yu. Kupriyanov, and A. N. Samus, J. Exp. Theor. Phys. 114 , 818 (2012).
- 129 D. Olaya, B. Baek, P. Dresselhaus, and S. Benz, IEEE Trans. Appl. Supercond. 18 (4), 1797 (2008).
- 130 D. Olaya, P. Dresselhaus, S. Benz, A. Herr, Q. P. Herr, A. G. Ioannidis, D. L. Miller, and A. W. Kleinsasser, Appl. Phys. Lett. 96 , 213510 (2010).
- 131 P. Dresselhaus, M. Elsbury, D. Olaya, C. J. Burroughs, and S. P. Benz, IEEE Trans. Appl. Supercond. 21 (3), 693 (2011).
- 132 H. Kroger, C. N. Potter, and D. W. Jillie, IEEE Trans. Magn. 15 , 488 (1979).
- 133 D. Jillie, L. N. Smith, H. Kroger, L. W. Currier, C. Potter, D. M. Shaw, and R. L. Payer, IEEE J. Solid State Circuits 18 , 173 (1983).
- 134 H. Kroger, L. Smith, D. Jillie, J. Thaxter, R. Aucoin, L. Currier, A. Potter, D. Shaw, and P. Willis, IEEE Trans. Magn. 21 , 870 (1985).
- 135 I. A. Devyatov and M. Yu. Kuprianov, JETP Lett. 59 , 200 (1994).
- 136 Y. Naveh, V. Patel, D. V. Averin, K. K. Likharev, and J. E. Lukens, Phys. Rev. Lett. 85 , 5404 (2000).
- 137 V. Patel, 'Current transport properties of Nb/AlOx/Nb Josephson junctions with high barrier transparencies,' Ph.D. thesis (State University of New York at Stony Brook, NY, 2001).
- 138 S. K. Tolpygo, V. Bolkhovsky, T. Weir, L. Johnson, W. D. Oliver, and M. A. Gouker, Supercond. Sci. Technol. 27 , 025016 (2014).
- 139 J. E. Mooij, T. P. Orlando, L. Levitov, L. Tian, C. H. van der Wal, and S. Lloyd, Science 285 , 1036 (1999).
- 140 T. P. Orlando, J. E. Mooij, L. Tian, C. H. Van der Wal, L. Levitov, S. Lloyd, and J. J. Mazo, Phys. Rev. B 60 , 15398 (1999).
- 141 V. E. Manucharyan, J. Koch, L. I. Glazman, and M. H. Devoret, Science 326 , 113 (2009).
- 142 V. Kaplunenko and G. Fisher, Supercond. Sci. Technol. 17 , S145 (2004).
- 143 A. Ustinov and V. Kaplunenko, J. Appl. Phys. 94 , 5405 (2003).
- 144 A. Feofanov, V. Oboznov, V. Bol'ginov, J. Lisenfeld, S. Poletto, V. V. Ryazanov, A. N. Rossolenko, M. Khabipov, D. Balashov, A. B. Zorin, P. N. Dmitriev, V. P. Koshelets, and A. V. Ustinov, Nat. Phys. 6 , 593 (2010).
- 145 M. Khabibov, D. Balashov, F. Maibaum, M. I. Khabipov, D. V. Balashov, F. Maibaum, A. B. Zorin, V. A. Oboznov, V. V. Bolginov, A. N. Rossolenko, and V. V. Ryazanov, Supercond. Sci. Technol. 23 , 045032 (2010).
- 146 O. Wetzstein, T. Ortlepp, R. Stolz, J. Kunert, H. G. Meyer, and H. Toepfer, IEEE Trans. Appl. Supercond. 21 (3, 814 (2011).
- 147 N. Takeuchi, Y. Yamanashi, and N. Yoshikawa, Appl. Phys. Lett. 102 , 052602 (2013).
- 148 K. K. Likharev, IEEE Trans. Magn. 13 , 242 (1977).
- 149 K. K. Likharev, S. V. Rylov, and V. K. Semenov, IEEE Trans. Magn. 21 , 947 (1985).
- 150 K. K. Likharev, Int. J. Theor. Phys. 21 , 311 (1982).
- 151 Q. Xu, Y. Yamanashi, and N. Yoshikawa, in Extended Abstracts of 15th International Superconductive Electronics Conference, ISEC'2015, DSP21, Nagoya, Japan (2015).
- 152 H. Namata, S. Nagasawa, and S. Tahara, IEEE Trans. Appl. Supercond. 7 (2), 2282 (1997).
- 153 A. M. Kadin, C. A. Manchini, M. J. Feldman, and D. K. Brock, IEEE Trans. Appl. Supercond. 11 (1), 1050 (2001).

This article was published in English in the original Russian journal. Reproduced here with stylistic changes by AIP Publishing.