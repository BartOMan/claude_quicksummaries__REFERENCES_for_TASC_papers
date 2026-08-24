## Application of Phase-Based Circuit Theory to RSFQ Logic Design

Lieze Schindler , Member, IEEE , and Coenrad J. Fourie , Senior Member, IEEE

Abstract -In contrast to transistor-based semiconductor circuits, there is currently no widely accepted formalized circuit theory or design methodology for superconductor rapid single flux quantum (RSFQ) logic circuits. Experienced designers intuitively consider flux loops, nodal phase, and branch currents when making design choices, but the lack of a formalized design process makes it difficult for inexperienced RSFQ circuit designers to construct a functioning logic cell without a reference. This results in new circuit designers, mostly recycling templates from published circuit designs without fully understanding why the circuits function as they do. Inexperienced RSFQ circuit designers often follow an iterative process where cell parameter values are adjusted, and the cell is run through electronic simulation engines until the desired functionality is reached. We propose the development of a formalized circuit design theory for RSFQ logic from first principles using phase-based circuit analysis. The circuit is designed using dc analysis to establish the dc operating point of the circuit. Phase-based analysis and simulation are then used to verify the dynamic circuit functionality. To demonstrate this method, we discuss examples for well-knownRSFQcells.Weanalyzetheinitialoperatingmarginsof these designs and discuss design accuracy and efficiency. Methods for current regulation to minimize current leakage between cells are discussed. We also present how this design methodology can be used to design new circuits such as an RSFQ XNOR cell. We investigate how an inverting (NOT) cell can be combined with other logic cells to minimize cell latency.

Index Terms -Circuit design, RSFQ, superconductor integrated circuits.

## I. INTRODUCTION

T RANSISTOR-BASED semiconductor circuit design utilizes widely accepted circuit theories and design methodologies. It is, therefore, possible for inexperienced circuit designers to design semiconductor circuits which function as intended. The rapid single flux quantum (RSFQ) logic family [1] currently has no widely accepted circuit theory or formalized design methodology for circuit design. Although much work has gone

Manuscript received October 25, 2021; revised January 6, 2022; accepted January 9, 2022. Date of publication January 13, 2022; date of current version February 2, 2022. This work was supported in part by the Office of the Director of National Intelligence (ODNI), Intelligence Advanced Research Projects Activity (IARPA), via the U.S. Army Research Office, under Grant W911NF-17-1-0120, and in part by the National Research Foundation of South Africa under Grant 105859. This article was recommended by Associate Editor I. V. Vernik. (Corresponding author: Lieze Schindler.)

The authors are with the Stellenbosch University, Stellenbosch 7600, South Africa (e-mail: liezeschindler@gmail.com; coenrad@sun.ac.za).

Color versions of one or more figures in this article are available at https://doi.org/10.1109/TASC.2022.3142278.

Digital Object Identifier 10.1109/TASC.2022.3142278

into the development of how high-level functional models of RSFQcircuits can be realized [2]-[8], little effort has been done to formalize the education of basic RSFQ logic cell design [9]. It is well known in the RSFQ design community that RSFQ circuits should be designed with consideration of phase over junctions or aroundloops, but the methods are not formalized. RSFQ cells are often published with parameter values, but little or no indication is given on how these values were calculated or obtained. The aim with this research is to allow inexperienced circuit designers to design RSFQ circuits as easily as they can design simple transistor logic gates. To do this, the complexity and physics of RSFQ circuits should be reduced to a few engineering circuit equations.

Here we present a formalization of circuit design theory for RSFQ logic from first principles using phase-based equations. The circuit is designed using phase-based equations to establish a dc operating point. Circuit simulation engines, such as JoSIM [10], [11], PSCAN [12], [13], JSIM [14], or WRSpice [15], are used to verify the dynamic circuit functionality. A methodology for analyzing and adapting these phase-based equations can then be used to investigate and improve the operating margins of the circuit. This approach provides a method to improve operating margins of basic RSFQ circuits without the intense computational power required by traditional circuit optimization methods, such as the center of gravity method. We present three design examples-A Josephson transmission line (JTL), a D flip-flop (DFF), and a circuit which combines a NOT gate with an exclusive OR (XOR) cell. This research provides a summary of the work done in [9] and also provides an additional example on how to implement the design of RSFQ circuits using the phase-based equation theory developed in Ref.[9]. This research forms part of the IARPA SuperTools program [16][18] and aims to expand the knowledge of RSFQ logic cell design.

## II. RSFQ BASICS

RSFQ logic utilizes magnetic flux quanta passed between decision elements [1]. Associated current passes through inductive connections, resulting in short-voltage pulses, also known as SFQ pulses, as shown in Fig. 1(a). These pulses are used for data representation in RSFQ logic. In standard RSFQ logic, if an SFQ pulse is present during a certain time period, it represents a binary '1' and the lack of a pulse represents a binary '0.' An SFQ pulse has an area equal to one flux quantum as evaluated

1051-8223 © 2022 IEEE. Personal use is permitted, but republication/redistribution requires IEEE permission. See https://www.ieee.org/publications/rights/index.html for more information.

Fig. 1. (a) SFQ pulse generated by junction with (b) associated 2 π junction phase shift. Figure adapted from [1].

<!-- image -->

Fig. 2. Schematic of different RSFQ building blocks.

<!-- image -->

through

<!-- formula-not-decoded -->

WhenanSFQpulseprogresses into a Josephson junction (JJ), it can result in instantaneous current through the JJ, which is larger than the junction critical current, I c . The I c refers to the maximumamountofcurrentwhichcanflowthroughthejunction before the junction undergoes a 2 π phase shift, as shown in Fig. 1(b), and is related to the area of the junction and the critical current density of the fabrication process. This 2 π phase-shift is also referred to as the switching of a junction and leads to the reproduction of an SFQ pulse.

For RSFQ logic, JJs are typically shunted with a resistor to be nonhysteretic, unless a fabrication process with self-shunted junctions is used.

RSFQ logic cells can be constructed through three basic RSFQ building blocks shown in Fig. 2. Each block consists of inductor, JJ, and bias current source elements. The transfer block transfers an SFQ pulse from one physical location to another. To achieve this, the value for the inductor is set as L ∼ Φ 0 / 2 I c , where I c is the critical current of the JJ. The storage block stores an SFQ pulse within a junction-inductor loop. This is achieved bysetting the inductor value to L ∼ Φ 0 /I c . The decision block is implemented through two JJs with different I c values to control whether an SFQ pulse is transmitted or not. The typical relation between the critical currents of the two decision junctions is I c 2 = √ 2 I c 1 [1].

## III. PHASE-BASED RSFQ CIRCUIT DESIGN METHODOLOGY

## A. Methodology

Kirchhoff's current law (KCL) and Kirchhoff's voltage law (KVL) are two commonly used circuit analysis methods taught to undergraduate students. These analysis methods are easy to understand and implement on basic circuits and powerful enough to find application in numerical circuit simulation tools. For this reason, we develop a circuit analysis method for RSFQ circuits using KCL and a KVL equivalent. As such, the circuit must be described in terms of the current flowing through a node or the phase difference over an element. As discussed in Section II, the basic RSFQ circuit elements are JJs, inductors, and current sources. The influence of shunt resistors for dc analysis is negligible as current will always flow through a superconductor instead of a resistive material.

Once the circuit is described in terms of the current through a node or the phase difference across a circuit element, KCL and the KVL equivalent can be used to construct circuit equations [9]. If the number of unknowns matches the number of circuit equations, Newton's method can be used to solve the values of the unknowns, also known as the root values. Newton's method is a mathematical algorithm used to iteratively approximate the root values of a function set. An initial guess for the unknown values is required. The next guess for the root is then calculated through

<!-- formula-not-decoded -->

where x n is the initial or previous guess, f ( x n ) is the function set, J ( x n ) is the pseudo-inverse Jacobian of f ( x n ) , and n is the number of iterations completed. The restrictions and special cases of Newton's method are widely available in the literature. For the purpose of this research, a script implementing Newton's method was developed by assuming that a nonsingular and nonzero J ( x n ) can be constructed through the circuit equations.

## B. Phase-Based Josephson Junction Model

Various models have been developed to represent the JJ in an electrical circuit. A popular model is the resistively capacitively shunted junction (RCSJ) model [19], which represents the JJ as an inductor in parallel with a capacitor and resistor. The RCSJ model is sufficient for modeling critically damped superconductor-insulator-superconductor tunnel junctions used in various fabrication processes. The current through a JJ is described through [20]

<!-- formula-not-decoded -->

where I c is the critical current of the junction, ϕ is the phase difference over the junction, and R and C the internal junction

Fig. 3. Definition of 2 π phase-shift for a switching JJ.

<!-- image -->

resistance and capacitance, respectively. The Josephson phasevoltage relation is defined through [1]

<!-- formula-not-decoded -->

We can combine (3) and (4) to describe the current through a JJ in terms of the phase

<!-- formula-not-decoded -->

For dc analysis, dϕ/dt = 0 can be assumed. Therefore, (5) can be reduced to represent the dc current through a JJ in terms of phase as

<!-- formula-not-decoded -->

The switching of a JJ occurs when i &gt; I c . The current through the JJ, while switching occurs, is described through (5) and causes a 2 π phase-shift over the JJ, as defined in Fig. 3. Once the 2 π phase-shift has occurred, dϕ/dt = 0 regains validity and the current through the JJ subsides back to (6) [9]. The statement that the influence of the JJ's shunt resistor is negligible during dc analysis is also verified through (6). The following definitions are formalized, with reference to Fig. 3, for a phase-shift observed during circuit analysis.

- /a114 If the current is taken in the positive i direction, a +2 π phase-shift is observed.
- /a114 If the current is taken in the negative i direction, a -2 π phase-shift is observed.

## C. Phase-Based Inductor Model

Considering the RCSJ model, the phase-voltage relation over an inductor for dc analysis can be characterized through (4) [9]. The voltage over an inductor is

<!-- formula-not-decoded -->

Combining (4) and (7), a relation between phase difference over an inductor and current through an inductor can be established

<!-- formula-not-decoded -->

Thus, the current through an inductor in terms of phase, defined in Fig. 4, is derived as

<!-- formula-not-decoded -->

Fig. 4. Current through inductor in terms of phase difference over inductor.

<!-- image -->

TABLE I SUMMARY OF PHASE-BASED COMPONENT MODELS

Fig. 5. Schematic of simplified JTL circuit.

<!-- image -->

/negationslash where ϕ = ϕ 1 -ϕ 2 . If ϕ 1 = ϕ 2 , then current will flow through the inductor and no current will flow through the inductor if ϕ 1 = ϕ 2 .

A summary of the phase-based component models is presented in Table I.

## IV. BASIC RSFQ CIRCUIT DESIGN EXAMPLE

The JTL is used for transmitting and reconstructing SFQ pulses. Although the most basic JTL has one biased JJ, most RSFQ JTLs are symmetrical and use two transfer blocks, as shown in Fig. 5. The JTL provides a basic example of how to analyze a circuit using phase-based circuit analysis. We include parasitic inductance of the connections to ground for completeness. Firstly, a dc analysis is done to determine how the current from the bias current source is distributed within the circuit. For this analysis, the following assumptions are made.

- 1) The phase at φ 1 equals the phase at φ 2 so that no current flows through L 1 .
- 2) The phase at φ 5 equals the phase at φ 7 so that no current flows through L 4 .

Considering these assumptions, we choose I c 1 = I c 2 = 250 µ A as a base design value for the JTL circuit. The inductor design for a transfer block is L ∼ Φ 0 / 2 I c . Therefore L ≈ 4 pHand L 1 = L 2 = L 3 = L 4 = 0 . 5 L , as each inductor forms half of the inductor within a transfer block. The JJs are designed to be biased at 0 . 7 I c to correspond to circuits designed in [1]. We therefore define a new variable, the bias current coefficient ( b cc ), which is used to describe the ratio of current used for biasing junctions. Thus, for this example,

TABLE II COMPARISON BETWEEN CALCULATED AND SIMULATED VALUES FOR THE RSFQ JTL CIRCUIT

<!-- image -->

Fig. 6. Two JTLs connected together to illustrate current leakage.

Fig. 7. Operating margins of the designed JTL when (a) two identical JTLs are connected and (b) when two JTLs with identical JJs, but different biasing currents are connected.

| B1:90.0[   | ###############################         | 154.8   |
|------------|-----------------------------------------|---------|
| B2:89.6[   | ################################        | 154.9   |
| IB1: 53.5[ | #############################           | ]74.4   |
| L1:90.0[   |                                         | 190.0   |
| L2:90.0[   | ####################################### | ]90.0   |
| L3:90.0[   | ######################################  | ]90.0   |
| L4:90.0[   | ####################################### | 190.0   |
| B1:90.0[   |                                         | ]46.3   |
| B2:90.0[   | #############################           | 146.0   |
| IB1: 43.0[ | ###########################             | ]80.2   |
| L1:90.0[   |                                         | 190.0   |
| L2:90.0[   | ######################################  | 190.0   |
| L3:90.0[   |                                         | 190.0   |
| L4:90.0[   | ####################################### | 190.0   |

b cc = 0 . 7 and I B 1 = b cc 2 I c = 350 µ A. For this example, we assume L p = 0 . 2 pH.

To derive the phase-based circuit equations, we consider the phase at ϕ 4

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

Evaluating KCL at ϕ 4 gives

<!-- formula-not-decoded -->

Fig. 8. Simplified schematic of DFF circuit design with connected loads.

<!-- image -->

Fig. 9. Mealy finite state machine diagram of DFF.

<!-- image -->

TABLE III VALUE COMPARISON FOR THE INITIAL DESIGN DFF CIRCUIT CURRENT DISTRIBUTION WITHIN THE RESET STATE WITH OPEN PORTS

Combining (10) and (11) and rearranging (12), we derive two functions with two unknowns

<!-- formula-not-decoded -->

TABLE IV VALUE COMPARISON FOR THE INITIAL DESIGN DFF CIRCUIT CURRENT DISTRIBUTION WITHIN THE SET STATE WITH OPEN PORTS

and

<!-- formula-not-decoded -->

Function f 1 ( i 1 , i 2 ) represents a clockwise phase loop through the JTL in terms of i 1 and i 2 . Thus, it is feasible to evaluate RSFQcircuitsintermsofphaseloopsandcurrentthroughnodes. Newton's method is implemented to solve the two unknown currents. Newton's method requires an initial guess for all unknown values. To avoid a complex arcsin function, the initial guess for the current flowing through a JJ must not be larger than the JJ's critical current. The initial guess of i 1 = i 2 = 0 µ A is chosen. Implementing Newton's method, the unknown values converge to i 1 = i 2 = 175 µ A. Table II shows the comparison between the calculated values of the current distribution using Newton's method and the simulated values.

/negationslash

/negationslash

Wenowconsider the effect of connecting the designed JTL to other circuits, through connecting another JTL as a load cell, as shown in Fig. 6. If ϕ 5 = ϕ 8 , no current will flow through L 4 and L 5 , leading to i 3 = 0 . This is referred to as load balancing. Butif ϕ 5 = ϕ 8 , then i 3 will flow through L 4 and L 5 . If i 3 = 0 , thencurrentleakageoccursbetweenthecircuitsandthedesigned bias current distribution is distorted. This can affect the operating margins of the circuit and, in extreme cases, cause the circuit to malfunction. Fig. 7 is used to illustrate how current leakage can influence the operating margins of a circuit. The circuit in Fig. 6 is placed within a testbench and simulated. The operating margins when ϕ 5 = ϕ 8 are shown in Fig. 7(a). The bias current source I B 2 is now reduced to 300 µ A, so that ϕ 5 = ϕ 8 , and the resulting operating margins are shown in Fig. 7(b). It is seen that the current leakage caused by the reduced bias current at I B 2 has a significant effect on the operating margins. The critical margin at I B 1 decreases from 53.5% to 43.0%. It is therefore important to consider load-balancing when designing RSFQ cells which are meant to be connected directly to another RSFQ cell.

/negationslash

Minimal current leakage will occur when the phase over the load input junction is equal to the phase over the designed cell output junction. We can thus model a load in terms of a phase source and an inductor. The load JTL in Fig. 6 can subsequently be modeled as a phase source, with a phase equal to ϕ 8 , connected to the L 5 inductor. We can assume that all RSFQ cells, with direct connection between cells, will be designed to have an identical load phase during the startup state. A standard phase load can therefore be used for simulation of the circuits when designing and analyzing RSFQ cells.

## V. DFF CIRCUIT DESIGN EXAMPLE

## A. Initial Design

The DFF is a multistate device used to transmit an input set pulse synchronized with a reset (typically clock) signal. A basic DFF can be designed with three or four junctions [1]. Here, we design a more rugged DFF with seven junctions, as shown in Fig. 8. This includes matching JJs in the form of half-JTL stages at every input and output, as well as parasitic inductances to ground. The DFF has two states-a 'set' state where an input signal has been received at a and a 'reset' state where an input signal has been received at clk . The 'reset' state can also refer to the 'startup' state of the DFF before any input signal has been received. The Mealy finite state machine diagram, extracted through TimEx [21], is shown in Fig. 9. The 'set' state is shown as state 1 and the 'reset' state is shown as state 0.

The RSFQ DFF circuit consists of transfer blocks, a storage block at J 3 -L 3 and a decision pair at J 4 -J 5 . The J 2 junction also forms a decision pair with J 3 to act as a buffer junction if more than one input pulse is received before a reset input signal.

For the initial DFF design, we choose I c = 250 µ A, b cc = 0 . 7 , and I c 1 = I c 3 = I c 4 = I c 6 = I c 7 = I c . We set √ 2 I c 2 = √ 2 I c 5 = I c for the decision pair blocks. The inductor design for a transfer block is L ∼ Φ 0 / 2 I c . Therefore, L ≈ 4 . 14 pH and L 1 = L 5 = L 7 = 0 . 5 L as each inductor forms half of the inductor within a transfer block. The inductor design for a storage block is L ∼ Φ 0 /I c ; therefore, the storage inductor is set as L 3 = 8 . 27 pH. The values for the designed inductors are L 1 = L 5 = L 7 = 2 . 07 pH and L 2 = L 4 = L 6 = 4 . 14 pH. The bias current sources are selected as I B 1 = I B 3 = I B 4 = b cc I c = 175 µ A and I B 2 = I c = 250 µ A. We assume L p = 0 . 2 pH.

1) Reset State: The 'reset' state indicates that an input reset signal was received by the DFF. Alternatively, it can also indicate that no input signals have been received and that the circuit is in a 'startup' state. The DFF is analyzed using the phase-based component models established in Table I. The following assumptions are made to simplify initial circuit analysis.

- 1) No phase change over L 1 so that i 10 = 0 µ A.
- 2) No phase change over L 5 so that i 11 = 0 µ A.
- 3) No phase change over L 7 so that i 12 = 0 µ A.

Applying these assumptions, we assume an open connection at a , clk , and Q . We use phase-change loops through the circuit to develop five initial phase-based equations for the DFF. Analyzing the current distribution of the four bias current sources provides another four equations to complete the nine equations needed for the nine unknown currents i 1 to i 9 . The DFF, operating within the reset state, can therefore be described

TABLE V VALUE COMPARISON FOR THE INITIAL DESIGN DFF CIRCUIT CURRENT DISTRIBUTION WITH CONNECTED LOADS

through the following equations:

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

<!-- image -->

Fig. 10. Testbench for RSFQ circuits adapted from [21].

Fig. 11. Operating margins of the initial RSFQ DFF cell design.

| JoSIM Tools 1.1.3           | JoSIM Tools 1.1.3           | JoSIM Tools 1.1.3           | JoSIM Tools 1.1.3           | JoSIM Tools 1.1.3           |
|-----------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|
| B1:                         | 50.7[                       | ################            | ]63.7                       |                             |
| B2                          | :56.9                       | #############               | 136.8                       |                             |
| B3                          | ：35.8                       | ###########                 | ]43.9                       |                             |
| B4                          | ：62.1                       | ############                | 120.7                       |                             |
| B5                          | 22.8                        | ########                    | 136.7                       |                             |
| B6 ：                        | 0'06                        | #####################       | ]59.0                       |                             |
| B7:                         | 0'06                        | #####################       | 58.4                        |                             |
| IB1:                        | 88                          | 共共共共共共共共共共共共共共共共共共共共共共共共共井  | 0'06                        |                             |
|                             | IB2: 47.5                   | ############                | 1 35.4                      |                             |
|                             | IB3: 85.2                   |                             | 0'06                        |                             |
|                             | IB4: 84.5                   | #########################   | 0'06                        |                             |
| L1:                         | 0'06                        |                             | 0'06                        |                             |
| L2:                         | 0'06                        | ######################      | 1 66.4                      |                             |
| L3                          | ： 57.7                      |                             | 1 48.6                      |                             |
| L4                          | 0'06:                       | ######################      | 61.8                        |                             |
| L5                          | 0'06:                       |                             | 0'06                        |                             |
| L6                          | :68.5[                      | #######################     | 1 0'06                      |                             |
|                             | L7:90.0[                    |                             | 190.0                       |                             |
| Criticalmargin:20.7%['B4+'] | Criticalmargin:20.7%['B4+'] | Criticalmargin:20.7%['B4+'] | Criticalmargin:20.7%['B4+'] | Criticalmargin:20.7%['B4+'] |

Fig. 12. Global operating margins of initial RSFQ DFF cell design.

| JoSIMTools 1.1.3              | JoSIMTools 1.1.3              | JoSIMTools 1.1.3              |
|-------------------------------|-------------------------------|-------------------------------|
| XJ:26.6                       | ### 共共共共共共共共共共共共井             | 88.7                          |
| XI:46.7                       | ####                          | 29.6                          |
| XL:69.7                       | 共共共共共井                        | 44.2                          |
| IC:72.2                       | 共井井共井共井共共井 共共井共共共共井共井共共井      | 0'06                          |
| BCC:78.3[                     |                               | 19 0'06                       |
| Criticalmargin: 26.6 %['XJ-'] | Criticalmargin: 26.6 %['XJ-'] | Criticalmargin: 26.6 %['XJ-'] |

Newton's Method, described in (2), is used to iteratively solve the values of i 1 to i 9 . Table III shows the comparison between the calculated and simulated values for the current distribution in the DFF circuit for the reset state with open connections at a , clk , and Q . It is seen that the calculated values correspond to the simulated values. The difference is negligible and stems from limits in numerical precision.

2) Set State: The 'set' state indicates that an input set signal has been received by the DFF. When a single input set signal is received, junctions J 1 and J 3 switch and a flux quantum is stored within the J 3 -L 3 -J 4 loop. If another input set signal is received before a input reset signal, junction J 2 switches. The following assumptions are made to adapt (15)-(23) to account for the phase shift within the DFF.

- 1) The state change from reset to set causes the phase over J 1 and J 3 to increase with 2 π .
- 2) No phase change over L 1 so that i 10 = 0 µ A.
- 3) The phase over the remaining junctions stay unchanged from the reset state to the set state.

Considering these assumptions, it is found that (15) and (18)(23) still hold true for the set state. The 2 π phase-shift over J 1

Fig. 13. Operating margins of the adapted DFF implementing current regulation for the reset state.

| B1:53.9[   | ################           | ]58.6   |
|------------|----------------------------|---------|
| B2:57.6    | #############              | ]35.4   |
| B3:35.2    | ###########                | ]44.6   |
| B4:57.4    | ###########                | ] 24.0  |
| B5 ：25.9   | ########                   | 1 38.2  |
| B6 0'06:   |                            | ] 0'69  |
| B7:90.0    | 共共共共共共共共共井共共共共共共共共共共共共井    | 73.2    |
| IB1:88.0   | 共共共共共共共共共共共共共共共共共共共共共共共共共井 | 1 0'06  |
| IB2:48.4   | ############               | 1 35.9  |
| IB3:87.6   |                            | 77.3    |
| IB4:87.8   | 共共共共共共共共共共共共共共共共共共共共共共井    | 1 68.5  |
| L1:90.0    | ########################## | 0'06    |
| L2:90.0    | ######################     | 64.1    |
| L3:54.4    | #################          | ] 62.0  |
| L4:90.0    | ######################     | 1 65.0  |
| L5:90.0    |                            | 1 0'06  |
| L6:90.0    | 共共共共共共共共共共共共共共共共共共共批共共共共共井 | 1 0'06  |
| L7:90.0[   | ########################## | 0'06    |

Fig. 14. Global operating margins of adapted DFF implementing current regulation for the reset state.

| JoSIM Tools 1.1.3            | JoSIM Tools 1.1.3            |                              |
|------------------------------|------------------------------|------------------------------|
| XJ:27.0                      | #### 共共共共共共共共共共共共井           | 190.0                        |
| XI:47.2                      | 共共共共共共井 ###井                 | ]30.1                        |
| XL:6 64.4                    | 共共共共共共共共井 共共共共共井             | 42.3                         |
| IC :73.0                     | 共共共共共共共共共井                   | 0'06                         |
| BCC:82.0                     | 共共共共共共共共井井井井 共共共共共共共共井       | 60.9                         |
| Critical margin:27.0%['x]-'] | Critical margin:27.0%['x]-'] | Critical margin:27.0%['x]-'] |

and J 3 in the set state influences (16) and (17) as follows:

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

Newton's method is once again used to iteratively solve the values of i 1 to i 9 for the set state through (15) and (18)-(25). The set state of the DFF is simulated through a phase source and inductor load connected at a , as shown in Fig 8, in JoSIM [11]. Although other simulation engines, such as PSCAN, also enable the use of phase-mode analysis, JoSIM was developed for the ColdFlux project [17] and is therefore used for simulation.

Table IV shows the comparison between the simulated and calculated current distribution values. It is seen that the calculation difference is much larger for the set state than the reset state shown in Table III. This is mainly attributed to the assumptions that no current flows through L 1 , L 5 , and L 7 . The DFF is designed for minimum current leakage during the reset state through load-balancing. When the state of the DFF changes to the set state, the current distribution within the circuit changes and can affect the phases at the input and output ports. This can lead to current leakage, which is not accounted for in the initial phase-based equations used to describe the current distribution within the DFF. Adding additional matching junctions reduces the magnitude of the current leakage, but increases the layout size and power consumption of the cell. It is therefore important to include the possible leakage currents within the phase-based equations.

## B. Extended Design

Many RSFQ cells have multiple states in which they operate. As the current distribution within the circuit changes with each state, it is important to know what effect this current redistribution will have on load circuits connected to the cell. The currents through the input and output ports must therefore be included within the phase-based equations. These currents for the DFF are i 10 , i 11 , and i 12 shown in Fig. 8. We extend the nine phase-based equations for the initial DFF design with three equations to include the phase loops through the input and output ports

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

where P 1 , P 2 , and P 3 are the amplitudes of the respective phase sources. To account for the additional currents, (19), (22), and (23) are adapted as follows:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

and

TABLE VI VALUE COMPARISON FOR THE DFF CIRCUIT DESIGN CURRENT DISTRIBUTION WITH CONNECTED LOADS

Fig. 15. Schematic of the XNOR cell.

<!-- image -->

The extended phase-based equations describing the current distribution within the DFF along with the possible leakage currents, for the reset state, are represented by (15)-(18), (20), (21), and (26)-(31). The current distribution for the set state is described through (15), (18), (20), (21), and (24)-(31). The test circuit in Fig 8 is used to simulate the DFF for both the reset and set states. All load circuits use an inductor and phase source to represent a standard JTL cell, as designed in IV. The phase source amplitude is set as the phase at ϕ 2 or ϕ 5 in Fig. 5 for I c = 250 µ A with the junctions biased at 0 . 7 I c . The resulting calculated and simulated currents for both the reset and set states are listed in Table V. It is seen that the current distribution within the DFF, along with the leakage currents, can accurately be calculated with the extended phase-based equations.

## C. Current Regulation

The initial values for the bias current sources can be adjusted to ensure that the current leakage is minimized when the DFF is connected to loads. To regulate the leakage currents, i 10 , i 11 , and i 12 , we adjust which values are considered fixed and which values are variables within the set of phase-based equations. We therefore set i 10 , i 11 , and i 12 to a constant 0 µ A and I B 1 , I B 3 , and I B 4 are changed from constant values to variables. Current regulation can be implemented to minimize the leakage

TABLE VII PARAMETER DESIGN VALUES FOR RSFQ XNOR CELL

current in either the reset or set state. Solving the extended phase-based equations, we extract the adapted values for the bias current sources as I B 1 = 162 µ A, I B 3 = 200 µ A, and I B 4 = 212 µ A for minimum current leakage in the reset state and I B 1 = 208 µ A, I B 3 = 166 µ A, and I B 4 = 162 µ A for minimum current leakage in the set state. The current distribution for the DFF with current regulation design is shown in Table VI.

## D. Operating Margins

The functionality of the designed circuits can be confirmed by simulating the circuits within a testbench. An example testbench, which can be used to evaluate several possible input combinations, is shown in Fig. 10. The DFF designed in Section V is placed as the device under test and the JTL designed in Section IV is used as the load.

The operating margins of the DFF are extracted using JoSIMtools [22]. The simulated operating margins for the DFF are

Fig. 16. Operating margins of unoptimized RSFQ XNOR cell as designed with phase-based equations.

| JoSIM                        | Tools 1.1.3                  | Tools 1.1.3                  | Tools 1.1.3                  |                              |
|------------------------------|------------------------------|------------------------------|------------------------------|------------------------------|
| B1 ：                         | 68.6                         | #################            | ]51.4                        |                              |
| B2                           | 34.2                         | #######                      | ]18.4                        |                              |
| B3                           | 18.0                         | #######                      | ]36.3                        |                              |
| B7                           | 34.5                         | ###&#124;#####               | ]23.5                        |                              |
| B8                           | 8.5                          | ####                         | ]22.6                        |                              |
| B9                           | 90.0                         | ######################       | ]65.1                        |                              |
| B10 ：                        | 65.0                         | ###############              | ]41.2                        |                              |
| B11                          | 38.1                         | ######                       | ]13.1                        |                              |
| B12                          | 41.9                         | #########                    | ]26.6                        |                              |
| B13                          | 46.0                         | ##############               | 155.3                        |                              |
| B14                          | 20.0                         | ####                         | ]16.4                        |                              |
| B15 ：                        | 16.6                         | ##&#124;##                   | ]15.6                        |                              |
| B16 ：                        | 54.6                         | #########                    | 1 9.2                        |                              |
| B17                          | 12.2                         | ##&#124;#                    | 117.7                        |                              |
| B18                          | 34.5                         | ################             | 173.6                        |                              |
| IB1                          | 72.9                         | #######################      | 0'06                         |                              |
| IB2                          | 28.7                         | #######                      | 22.6                         |                              |
| IB5                          | 0'06                         | ##########################   | 0'06                         |                              |
| IB6                          | 53.0                         | ####################         | 0'06                         |                              |
| IB7                          | 57.6                         | ###################          | 74.4                         |                              |
| IB8                          | 12.2                         | ##&#124;#                    | ]13.6                        |                              |
| 681                          | 0'06                         | ######################       | 62.7                         |                              |
| IB10:                        | 0'06                         | ####################         | 48.6                         |                              |
| L1                           | 0'06                         | ##########################   | 0'06                         |                              |
| L2                           | 76.4                         | ##############               | 1 22.8                       |                              |
| L4                           | 57.9                         | ###############              | 48.8                         |                              |
| L10                          | 0'06                         | ##########################   | 0'06                         |                              |
| L11                          | 0'06                         | ######################       | ] 64.1                       |                              |
| L14                          | 49.3                         | ############                 | '6                           |                              |
| L15                          | 0'06                         | ##########################   | 0'06                         |                              |
| L16                          | 0'06                         | ##########################   | 1 0'06                       |                              |
| L17                          | 0'06                         | #########################    | 1 80.1                       |                              |
| L22                          | 41.7                         | #########                    | 1 22.6                       |                              |
| L24                          | 60.9                         | ######################       | 1 0'06                       |                              |
| L25 :                        | 0'06                         | ##########################   | 0'06                         |                              |
| Critical margin: 8.5%['B8-*] | Critical margin: 8.5%['B8-*] | Critical margin: 8.5%['B8-*] | Critical margin: 8.5%['B8-*] | Critical margin: 8.5%['B8-*] |

Fig. 17. Global operating margins of unoptimized RSFQ XNOR cell as designed with phase-based equations.

| JoSIMTools 1.1.3             | JoSIMTools 1.1.3             | JoSIMTools 1.1.3             |
|------------------------------|------------------------------|------------------------------|
| XJ:71.3                      | ###############              | 1 25.9                       |
| XI:10.3                      | ##                           | 一 8'6                        |
| XL:48.6                      | #####井# #                    | 12.4                         |
| IC :73.6                     | 共共共共共共共共共共井 ####             | 26.1                         |
| BCC:22.2[                    | ######                       | 22.6                         |
| Critical margin: 9.8%['XI+'] | Critical margin: 9.8%['XI+'] | Critical margin: 9.8%['XI+'] |

shown in Fig. 11. The critical margin is +20 . 7% and is caused by J 4 . Fig. 12 provides the global operating margins for the junction critical current (XJ), bias current (XI), and the inductances (XL) of the designed DFF cell. Following [23], a circuit can be considered robust if the global margins XJ, XI, and XL meet or exceed ± 20 , ± 30 , and ± 40% , respectively. Fig. 12 shows that the designed DFF meets this criteria except for the XI global margin, which is +29 . 6% . To improve these margins without applying computationally expensive optimization procedures, we now consider adapting the phase-based equations to regulate dc current distribution within the cell.

<!-- formula-not-decoded -->

Fig. 18. KCL equations for the designed RSFQ XNOR cell.

<!-- formula-not-decoded -->

Fig. 19. Phase-loop equations for the designed RSFQ XNOR cell.

The operating margins of the adapted DFF circuit is shown in Fig. 13. The critical margin is increased to +24 . 0% for J 4 . The global operating margins for the adapted DFF is shown in Fig. 14 and it can be seen that the adapted DFF meets the criteria for global operating margins specified in [23]. Implementing this method of current regulation through phase-based equations provides the user with a better nominal operating point of a cell, which can also provide a better starting point for additional optimization procedures, when considering circuits with narrow operating margins. To further improve margins, the cell can undergo additional optimization procedures, as optimization tools can consider both the static and dynamic behavior of a circuit during the optimization process [24].

## VI. CONCEPTUAL COMPLEX CIRCUIT DESIGN

One major constraint with larger RSFQ circuits is that NOT gates are often required to invert signals. These inverting cells typically require a clock signal to perform the NOT function. Therefore, multiple NOT gates within a large circuit can lead to significant throughput latency. Signal-balancing problems caused by these delays can also be significant.

A conceptual example of how a NOT gate can be integrated within an XOR gate is now presented. The fundamentals of the phase-based equations are used to form an XNOR cell, which can perform the XOR and NOT function within a single clock cycle. The XNOR cell presented in Ref.[25] is used as a foundation for the design of an XNOR cell using phasebased equations. The schematic of the RSFQ XNOR cell is shown in Fig. 15. Inductors L 3 , L 7 , L 9 , L 12 , L 13 , L 18 -L 21 , and L 23 are parasitic inductors included within the cell due to physical layout constraints. For this example, these inductors are chosen to be 1 pH. JJs connected to ground also present parasitic inductances, marked as L p [x] , set at 0.2 pH for this example.

To design an RSFQ XNOR cell, we start with a typical RSFQ XOR cell. When the XOR cell received an input pulse from input port a , a fluxon is stored within the J 2 -L 3 -J 3 -L 4 -L 9 -J 7 -J 8 loop due to the storing inductor L 4 . The same concept applies when the XOR only receives an input from port b . The clock input is connected to a splitter in order to split the clock signal. The one leg of the splitter feeds the clock pulse to the XOR cell. The other leg sends the signal through a JTL in order to delay the pulse. The delay of the JTL can be adjusted through increasing or decreasing the value of the bias current source. If a clock signal is received while a fluxon is stored within the XOR section, J 8 will switch. J 15 is set to be much smaller than J 8 and slightly smaller than J 16 . Thus, if junction J 8 switches, it causes J 15 to also switch. The inductor L 22 is designed as a storage inductor. Therefore, the switching of J 15 leads to the fluxon being stored within the J 15 -L 19 -L 22 -J 16 -L 21 -L 20 storage loop. It is important that J 15 switches before the delayed clock pulse arrives in order to store the fluxon. When the delayed clock pulse arrives at the storage loop containing a stored fluxon, it leads to the switching of J 16 . The delayed SFQ pulse therefore does not transmit through L 23 to J 17 and no output is generated. If no fluxon is stored within the XOR cell, J 8 and J 15 will not switch when a clock pulse arrives at the XOR section of the cell. The delayed clock pulse will travel through the JTL section, and the empty storage loop, and cause J 17 to switch and generate an output pulse.

The intended functionality of the designed RSFQ XNOR cell is verified through JoSIM simulation as well as TimEx extraction [21]. We choose I c = 250 µ A and b cc = 0 . 7 and use JoSIM-tools [22], [26] to extract the operating margins. Fig. 16 provides the operating margins for each individual component within the XNOR cell. It is important to note that these margins are extracted from the draft XNOR cell before any optimization operations have been applied. Designing the cell using phase-based equations provides a much better starting point for circuit optimization compared to circuits designed without considering phase. Fig. 17 provides the global operating margins for the junction critical current (XJ), bias current (XI), and the inductances (XL) of the designed XNOR cell. The operating margins in Fig. 17 also show that, for this draft XNOR design, I c can be varied between 66 and 315 µ A and b cc has margins of ± 22 % . TimEx is used to extract the maximum clock frequency as 49 GHz and the clock to output throughput as

24.5 ps. Both these extracted values can be improved through implementing optimization procedures on the draft design. An optimized version of the designed XNOR cell is included within the ColdFlux RSFQ cell library [17], [18], [27]. For version 2.1 of this library, the optimized XNOR cell has an extracted maximum clock frequency of 70 GHz and a throughput delay of 21.8 ps.

## VII. DESIGN EXCEPTIONS

Special cases exist where circuit design using Newton's method is not possible. An example of this is the SFQDC circuit. This circuit converts an SFQ pulse at the input to a constant dc voltage at the output. This circuit is typically inserted at the output of a chip so that it is possible to measure the functionality of a chip without high-frequency measuring equipment. The SFQDChascertain JJs that constantly undergo a 2 π phase-shift, even during dc operation. There is, therefore, fluctuating current within the circuit loops due to the switching JJs. Due to the current fluctuation, Newton's method will not converge.

## VIII. CONCLUSION

A phase-based circuit analysis technique was formalized for analysis and design improvement of RSFQ logic circuits. Phasebased component models were established and design examples, a two-junction single-state JTL, a seven-junction, two-state DFF, and a conceptual XNOR cell, were evaluated. We found that it is possible to accurately calculate the current distribution for a circuit at dc operation using the established phase-based circuit equations and Newton's method. The effect of analyzing a circuit in isolation was discussed along with possible current leakage effects when the circuit is then connected to other circuits. The phase-based equations were extended to include possible circuit current leakage and current regulation techniques were discussed to minimize current leakage. The designed JTL and DFF circuits were simulated within a testbench circuit and the operating margins were extracted. A conceptual design for a morecomplexRSFQcell,anXNOR,wasdiscussed.TheXNOR provides an example of how a NOT cell can be incorporated within an RSFQ logic cell to minimize clock cycles required for a logic operation. The shortcomings and design exceptions for the developed RSFQ design method were also discussed. The formalized design method is shown to deliver nominal circuit designs with satisfactory operating margins. It can be extended to other cells in the RSFQ logic family and can be used to provide a formalized teaching methodology for inexperienced RSFQ circuit designers.

## APPENDIX

The complete set of phase-based equations for the design of the RSFQ XNOR cell is provided. This allows the reproduction of results and serves as an additional example of how the phase-based equations can be used to design and analyze RSFQ circuits. The KCL equations for designing the RSFQ XNOR is shown in Fig. 18 and the phase-loop equations are shown in Fig. 19.

## ACKNOWLEDGMENT

The authors would like to thank Dr. J. Delport for his continuous support with JoSIM and Dr. R. Bakolo and Dr. P. le Roux for many fruitful discussions.

## REFERENCES

- [1] K. K. Likharev and V. K. Semenov, 'RSFQ logic/memory family: A new Josephson-junction technology for sub-terahertz-clock-frequency digital systems,' IEEETrans.Appl. Supercond. , vol. 1, no. 1, pp. 3-28, Mar. 1991.
- [2] H. Toepfer, T. Harnisch, J. Kunert, S. Lange, and H. F. Uhlmann, 'Formal description of the functional behavior of RSFQ logic circuits for design and optimization purposes,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 3630-3633, Jun. 1997.
- [3] K. Gaj, C.-H. Cheah, E. G. Friedman, and M. J. Feldman, 'Functional modeling of RSFQ circuits using verilog HDL,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 3151-3154, Jun. 1997.
- [4] P. Bunyk and V. K. Semenov, 'Design of an RSFQ microprocessor,' IEEE Trans. Appl. Supercond. , vol. 5, no. 2, pp. 3325-3328, Jun. 1995.
- [5] S. V. Polonsky, J. C. Lin, and A. V. Rylyakov, 'RSFQ arithmetic blocks for DSP applications,' IEEE Trans. Appl. Supercond. , vol. 5, no. 2, pp. 2823-2826, Jun. 1995.
- [6] N. Yoshikawa and J. Koshiyama, 'Top-down RSFQ logic design based on a binary decision diagram,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 1098-1101, Mar. 2001.
- [7] J. Koshiyama and N. Yoshikawa, 'A cell-based design approach for RSFQ circuits based on binary decision diagram,' IEEE Trans. Appl. Supercond. , vol. 11, no. 1, pp. 263-266, Mar. 2001.
- [8] N. Kito, K. Takagi, and N. Takagi, 'Conversion of a CMOS logic circuit design to an RSFQ design considering latching function of RSFQ logic gates,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1300905.
- [9] L. Schindler, 'The development and characterisation of a parameterised RSFQcell library for layout synthesis,' Ph.D. dissertation, Elect. Electron. Eng. Dept., Stellenbosch Univ., Mar. 2021.
- [10] J. A. Delport, K. Jackman, P. Le Roux, and C. J. Fourie, 'JoSIMSuperconductor SPICE simulator,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1300905.
- [11] J. A. Delport, 'JoSIM,' 2018, Accessed: Oct. 25, 2021. [Online]. Available: https://github.com/JoeyDelp/JoSIM/
- [12] S. Polonsky, P. Shevchenko, A. Kirichenko, D. Zinoviev, and A. Rylyakov, 'PSCAN'96: New software for simulation and optimization of complex RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 7, no. 2, pp. 2685-2689, Jun. 1997.
- [13] P. Shevchenko, 'PSCAN2 superconductor circuit simulator.,' 2016, Accessed: Jan. 6, 2022. [Online]. Available: http://pscan2sim.org/index.html
- [14] E. S. Fang and T. Van Duzer, 'A Josephson integrated circuit simulator (JSIM) for superconductive electronic applications,' Ext. Abs. ISEC , Tokyo, Japan, 1989.
- [15] Whiteley Research, Inc. 2017. Sunnyvale, CA, USA, Accessed: Jan. 6, 2022. [Online]. Available: http://www.wrcad.com
- [16] IARPA SuperTools program. 2016, Accessed: Jan. 6, 2022. [Online]. Available: https://www.iarpa.gov/index.php/research-programs/ supertools
- [17] C. J. Fourie et al. , 'ColdFlux superconducting EDA and TCAD tools project: Overview and progress,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1300407.
- [18] L. Schindler, J. A. Delport, and C. J. Fourie, 'The ColdFlux RSFQ cell library for MIT-LL SFQ5ee fabrication process,' IEEE Trans. Appl. Supercond ., vol. 42, no. 2, Mar. 2022, Art. no. 1300207.
- [19] D. E. McCumber, 'Effect of ac impedance on dc voltage-current characteristics of superconductor weak-link junctions,' J. Appl. Phys. , vol. 39, no. 7, pp. 3113-3118, 1968.
- [20] K. K. Likharev, Dynamics of Josephson Junctions and Circuits . New York, NY, USA: Gordon and Breach, 1986.
- [21] C. J. Fourie, 'Extraction of DC-biased SFQ circuit verilog models,' IEEE Trans. Appl. Supercond. , vol. 28, no. 6, Sep. 2018, Art. no. 1300811.
- [22] P le Roux, 'JoSIM-Tools,' 2019, Accessed: Oct. 25, 2021. [Online]. Available: https://github.com/qedalab/josim-tools
- [23] S. S. Meher et al. , 'Superconductor standard cell library for advanced EDA design,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Aug. 2021, Art. no. 1300807.
- [24] P. le Roux and C. Fourie, 'Distance-to-failure-maximization optimization algorithm for SFQ logic cells,' IEEE Trans. Appl. Supercond ., vol. 30, no. 7, Oct. 2020, Art. no. 1301405.
- [25] R. S. Bakolo and C. J. Fourie, 'New implementation of RSFQ superconductive digital gates,' SAIEE Afr. Res. J. , vol. 104, no. 3, pp. 90-96, 2013.
- [26] C. J. Fourie 'TimEx,' 2018, Accessed: Oct. 25, 2021. [Online]. Available: https://github.com/sunmagnetics/TimEx
- [27] L. Schindler, 'ColdFlux RSFQ cell library,' 2018, Accessed: Oct. 25, 2021. [Online]. Available: https://github.com/sunmagnetics/RSFQlib