## Bias Distribution in ERSFQ VLSI Circuits

Gleb Krylov and Eby G. Friedman, Department of Electrical and Computer Engineering University of Rochester Rochester, New York 14627 Email: gleb.krylov@rochester.edu

Abstract -Rapid single flux quantum (RSFQ) circuits have recently attracted considerable attention as a promising beyond CMOS technology for exascale computing. Unlike conventional CMOS circuits, RSFQ circuits require a specific bias current delivered to each Josephson junction, making robust bias networks an issue of great importance for large scale integration. ERSFQ is an energy efficient, inductive bias scheme for RSFQ circuits, where power dissipation is drastically lowered by eliminating the bias resistors while the cell library remains unchanged. An ERSFQ bias scheme requires the introduction of multiple circuit elements - current limiting Josephson junctions, bias inductors, and Josephson transmission lines. Multiple guidelines exist for the effective design of these structures. In this paper, additional parameter guidelines and design techniques are presented to decrease physical area and dynamic power dissipation while improving bias margins. These guidelines and techniques are applicable to automating the synthesis of bias networks to enable large scale ERSFQ circuits.

## I. INTRODUCTION

With the slower scaling of conventional CMOS circuits, considerable research efforts have been expended to determine a suitable technology replacement or supplement for a variety of compute intensive applications [1]. For high performance supercomputers, cloud computing, and quantum computation, superconductive electronics (SCE) is a promising beyond CMOS technology [2]. Although cryogenic refrigeration is necessary to operate these circuits, the energy per bit for SCEbased supercomputers, including the refrigeration expenses, is lower by one to three orders of magnitude as compared to typical CMOS levels [3].

Multiple SCE logic families exist with a different organization of basic gates, bias networks, and signaling methodologies. The focus of this paper is on the original and most mature of these families, rapid single flux quantum (RSFQ) [4], and, in particular, a recently introduced energy efficient version, ERSFQ [5].

A major obstacle for improving the large scale integration of RSFQ circuits is the lack of EDA tools [6]. Current research is aimed at both adapting existing CMOS-based industrial tools and developing novel tools for SFQ technology [7]. RSFQ gates are current biased, and, unlike CMOS, require a precise bias current to maintain correct functionality. Over- and underbiased gates can produce logic errors. Proper distribution of

The effort depicted is supported by the Department of Defense (DoD) Agency - Intelligence Advanced Research Projects Activity (IARPA) through the U.S. Army Research Office under Contract No. W911NF-17-9-0001. The content of the information does not necessarily reflect the position or the policy of the Government, and no official endorsement should be inferred.

the bias currents within SFQ circuits is therefore essential to maintain correct operation. This issue is critical for continuing the integration of SFQ circuits towards LSI and VLSI levels of complexity. As the bias lines in SFQ circuits are lossless and inductive, these EDA tools require a novel set of guidelines, heuristics, and algorithms for the automated generation of bias networks for SFQ-based VLSI circuits. In this paper, guidelines specific to bias current delivery in ERSFQ circuits are presented.

The paper is organized as follows. In section II, a brief background of RSFQ technology is provided, with a focus on the bias networks and related energy efficient structures. In section III, the elements within ERSFQ circuits that regulate or affect the bias distribution network are described. In section IV, a semi-automated analysis methodology is presented. This methodology is used to develop design guidelines for ERSFQ bias networks, as described in section V. In section VI, some conclusions are offered.

## II. BACKGROUND

In this section, a brief background on RSFQ circuit structures, operation, and biasing is provided. In subsection II-A, RSFQ circuits and related operational principles are reviewed. In subsections II-B and II-C, respectively, RSFQ bias networks are described and related energy efficient circuit modifications are discussed.

## A. RSFQ circuit operation

RSFQ technology [4] is a logic family for cryogenic superconductive computing based on Josephson junctions (JJ) and niobium interconnect, which exhibits superconductivity at 4.2 K - the standard operational temperature for these circuits, typically cooled by liquid helium. Magnetic flux within a superconductive loop is quantized. In an RSFQ logic family, information is represented as single flux quantum (SFQ) pulses - voltage pulses with a quantized area of Φ 0 ≈ 2 . 07 mV · ps in particular, the occurrence or absence of an SFQ pulse during a specific clock period. RSFQ gates are composed of different combinations of superconductive loops storing and not storing a magnetic flux quantum depending upon the target function. These gates are typically clocked, where a logic zero is represented as the absence of an SFQ pulse within a clock period.

Each SFQ pulse corresponds to a shift in the superconductive phase difference across a critically damped (shunted) [8] JJ by 2 π - an event referred to as switching a JJ. SFQ pulses

are transferred across the circuit using two distinct types of transmission lines - active Josephson transmission lines (JTL) and passive transmission lines (PTL) [9]. Multiple advantages and disadvantages exist for each type of transmission line [10]; however, for energy efficient bias networks, only JTLs are relevant, as described in section III.

A JTL is a chain of grounded, shunted JJs connected in parallel by small inductors ( ∼ 2 pH). The phase of these JJs changes by 2 π upon the arrival of an SFQ pulse, regenerating and passing the pulse along. As the inductance between the JJs is typically fixed, the length of a JTL is the number of stages (or JJs) within a transmission line.

## B. Bias distribution in RSFQ circuits

The primary parameter of a Josephson junction is the critical current I c , which corresponds to the transition between states with a zero and nonzero voltage across a JJ and is directly related to the physical area of the JJ. The JJs within an RSFQ circuit are directly or indirectly biased to a specific fraction of I c to maintain proper operation [4]. Local bias distribution within each gate is performed by an inductive network, consisting of inductors and JJs, with one or two bias network connections per gate. Each gate is typically individually optimized - the inductance and critical current of the JJs are chosen to produce robust operation and small delay.

The objective of a bias distribution network within a complex RSFQ circuit is to supply a precise bias current to each gate. In conventional RSFQ circuits, the bias current is distributed and regulated by a resistive tree network [4]. The current is typically supplied off-chip and transferred to the gates by superconductive wires, where each cell contains a bias resistor. Unlike CMOS bias networks, which exhibit some distributed resistance per length, an RSFQ bias network is lossless until the point of load [5]. Within each cell, the bias current is distributed by inductive current division, where the nonlinear inductance of the JJs should also be considered.

The resistors within the gates dissipate significant static power, approximately 60 times greater than the dynamic power dissipated during a JJ switching process ( P D = I b ∗ Φ 0 ∗ f s , ∼ 13 nW per gate) [11]. Moreover, most of this power dissipation occurs close to the thermally sensitive superconductive elements. Multiple solutions have been proposed to mitigate this static power dissipation in RSFQ circuits [12], [13].

All of these issues and concerns emphasize the importance of correct and efficient distribution of bias currents within large scale SFQ circuits. These bias distribution structures need to be synthesizeable by prospective SFQ EDA tools to support the increasing complexity of RSFQ circuits. In this paper, guidelines, tradeoffs, and techniques for efficient current bias networks are presented.

## C. Energy efficient SFQ

In energy efficient SFQ (ERSFQ) [5], the dissipative resistors used within RSFQ are replaced with Josephson junctions and superconductive inductors, eliminating the static power

Fig. 1: Bias distribution schemes, a) conventional RSFQ, and b) ERSFQ

<!-- image -->

dissipation, thereby reducing the total energy dissipation of these circuits by two orders of magnitude [11]. These JJs function as current limiters - when the current passing through these bias JJs approaches the critical current I c , the inductance of the JJ rapidly increases. If the current exceeds I c , the bias JJ momentarily transitions into a voltage state, diverting any additional current within the bias network. Conversion between RSFQ and ERSFQ gates does not require any changes to existing cell libraries, only affecting the bias distribution elements [14]. This conversion is schematically depicted in Figure 1. In the next section, the circuit elements within the ERSFQ bias networks are described.

## III. ERSFQ CIRCUIT ELEMENTS

Multiple modifications are necessary to support inductive bias distribution. Switching the bias JJs produces current fluctuations on the order of Φ 0 /L B , where L B is the bias inductance connected in series with the bias JJ [5]. A large L B therefore reduces the bias current ripple, although a large inductor ( ∼ 500 pH) typically requires significant area.

The average voltage for a gate switching at a frequency f s is Φ 0 ∗ f s . To prevent current redistribution, the voltage on the bias bus should be higher than any gate voltage within the circuit. This constraint is achieved by connecting the bias bus to the clock line - the average voltage on the clock line is guaranteed to be equal or greater than any gate voltage, since the clock operates at the highest frequency in a circuit. The clock line is connected to a structure called a feeding JTL (FJTL) to increase both the stability of the voltage reference and the bias margins.

An FJTL is schematically depicted in Figure 2. An FJTL is a JTL consisting of multiple stages, where each stage is connected to the bias bus by a large inductor L B . This JTL is typically terminated, and the output is not utilized. The FJTL establishes a robust voltage reference for the bias bus of an ERSFQ circuit, and improves the margins of operation by supplying additional or receiving excess bias current.

Some guidelines currently exist on the proper design of these components and the dependence of the bias network properties on the load characteristics [15]-[19]. The dependence of the margins on the operating frequency of a feeding JTL has been studied [15]; no benefit exists from increasing the frequency of the FJTL clock beyond the clock frequency of the load circuit. Another study has suggested optimal values for some of the ERSFQ component parameters, such as the bias inductance and the size of the FJTL [17].

Fig. 2: Feeding JTL connected to an SFQ clock line acting as a voltage reference.

<!-- image -->

Some commonly used ad hoc design approaches exist [15], [16]. One rule of thumb is related to the size of the feeding JTL, which is typically chosen to ensure the FJTL bias current is about 25% to 30% of the load bias current. As the size of the feeding JTL affects the physical area and bias current of the circuit, strict guidelines are required to integrate ERSFQ circuits into an industrial EDA flow. These design guidelines are further discussed in section V.

## IV. EXAMPLE CIRCUIT AND ANALYSIS METHODOLOGY

An ERSFQ bias network is composed of a variety of different elements, where each gate contains a highly nonlinear JJ as a current regulator. This structure makes infeasible the development of closed-form analytic expressions describing the behavior of the bias network. An analysis of the bias network is therefore limited to observations of trends and the effects of different component parameters on circuit behavior.

For this analysis, a semi-automated script is used to perform multiple circuit simulations in the WRSpice simulator [20] to extract behavioral trends. Two primary circuit components in an ERSFQ bias network exist, as described in section III - the load, requiring a bias current I B , and a feeding JTL, which functions as a voltage source with a maximum average voltage V B . This topology is schematically shown in Figure 3. In this paper, the topology is used to extract parametric trends.

Fig. 3: Topology of the ERSFQ biased circuit used in this analysis.

<!-- image -->

A generic ERSFQ circuit is used as a standard load; specifically, a shift register composed of multiple D flip flops combined with JTLs. The shift register is synchronized by an H-tree clock distribution network consisting of a binary tree with splitter gates [4]. The data source generates a train of SFQ pulses with a specific pattern, representing the input data.

The primary metric of robustness of operation in RSFQ circuits is the bias margins. The bias margins are a measure of the additional or absent bias current tolerated by a circuit. The ERSFQ bias networks affect the bias margins due to dynamic redistribution of the bias currents between the FJTL and the many loads. The ERSFQ bias margins are limited, however, by the intrinsic bias margins of a properly biased and optimized RSFQ circuit. These margins typically do not exceed 20% for circuits of intermediate complexity, and are often lower for more complex circuits [21]. It is therefore infeasible to optimize an ERSFQ bias network within a large circuit to achieve margins of operation wider than 20% to 30%.

In ideal conditions, the FJTL is used only to establish a voltage reference; the current regulation capabilities are not utilized. To analyze these capabilities, the ERSFQ bias network is also evaluated in both overbiased and underbiased conditions. An underbiased condition corresponds to the case where the supplied bias current is lower than the target design objective. An overbiased condition occurs when the supplied bias current exceeds the target design objective. In section V, these conditions are evaluated for a range of supplied bias currents.

## V. GUIDELINES FOR ERSFQ BIAS NETWORKS

In this section, certain parametric trends in bias networks are discussed, and guidelines for ERSFQ bias network design tools are proposed. In subsection V-A, the effect of the bias inductance on current variations is compared to theoretical expectations. In subsection V-B, two different topologies of an FJTL stage are considered in terms of the bias distribution and energy efficiency. In subsection V-C, the effect of the bias margins of an FJTL on the overall circuit bias margins is discussed.

## A. Bias inductance

ERSFQ gates are connected to a bias bus through large bias inductors. These inductors reduce the amplitude of the bias current ripple, thereby reducing the probability of erroneously switching the JJs within the logic gates. A comparison of an analytic expression of the magnitude of the current ripple to simulations is described in this subsection to verify the correctness of the analysis process.

The simulated dependence of the current variations on the bias inductance is illustrated in Figure 4, where zero on the vertical axis is the average bias current. The overlapping plots depict the deviation from the average current for three different FJTL sizes. The simulated bias current variations are in good agreement with the theoretical value of Φ 0 /L B [5] and with simulation results from [17]. This example supports the application of this simulation analysis methodology to more complex parametric analysis. Similar to the results presented in [17], additional inductance beyond 200 to 300 pH produces a negligible decrease in bias variations as compared to a typical bias current of an RSFQ gate.

## B. Topology of FJTL stage

One of the primary design decisions in the automated synthesis of ERSFQ bias networks is the topology of the FJTL stage. Two methods exist for designing these structures - with [11], [17] and without [5], [22] a bias limiting JJ within the

Fig. 4: Dependence of current variations on bias inductance. The dashed line is the analytic expression.

<!-- image -->

Fig. 5: Dependence of load bias current on supplied bias current for critically damped and overdamped bias JJs in a FJTL. The FJTL contains 64 stages, corresponding to 50% of the load bias current. The critical current of the bias JJ is normalized to 250 µ A.

<!-- image -->

JTL stage. Furthermore, different damping conditions for this bias JJ should be considered [17].

In underbiased circuits, no effect occurs from the presence of the bias limiting JJs within the FJTL. As the bias of each individual stage is lower than the critical current of the bias limiting JJ, these JJs never switch, only slightly adding to the bias inductance as well as significantly increasing the area.

A comparison of the bias regulation capability for a FJTL without the bias JJ, as well as a FJTL with different sizes of the bias JJ is shown in Figure 5. Note that no difference in the bias current distribution occurs in the underbiased circuits. For the overbiased circuits, the FJTL without bias JJs produces a preferable bias distribution for the overbiased case (a smaller bias current in the load). From Figure 5, the FJTL with overdamped bias junctions follows the same trend, although the bias distribution with overdamped bias JJs is improved.

## C. Bias margins of FJTL

The purpose of a FJTL in an ERSFQ circuit, apart from providing a voltage source, is to absorb excess bias current in the overbiased circuits and to provide additional bias current to the underbiased circuits. A FJTL therefore experiences large

Fig. 6: Dependence of actual bias current on supplied bias current for FJTL with same size and different bias margins (8.4% to 43.6%).

<!-- image -->

current variations as part of the intended behavior. Despite the FJTL being a robust circuit with wide margins, bias variations can exceed these margins, resulting in incorrect operation of the FJTL. It is therefore important to consider the effects of the FJTL bias margins on the overall bias margins of a circuit.

In overbiased circuits, a FJTL can switch more frequently, raising the voltage on the bias bus, expending additional energy. In underbiased circuits, a FJTL can either skip an SFQ pulse or completely cease operation, resulting in a loss of the voltage source and incorrect bias distribution. Wider FJTL bias margins improve the energy efficiency in overbiased circuits. In underbiased circuits, wider FJTL bias margins can increase the bias current in the load, ensuring the circuit operates properly at lower bias levels.

As confirmed in Figure 6, wider bias margins of the FJTL improve the distribution of the bias current in underbiased circuits, and enable correct operation with a lower supplied bias current. The benefits of higher FJTL bias margins diminish beyond a bias margin of 40%.

## VI. CONCLUSIONS

In this paper, the bias distribution network for a cryogenic electronics technology - ERSFQ logic - is discussed. Robust bias networks are essential for the integration of ERSFQ circuits into LSI and VLSI complexity systems. The proposed guidelines enable more robust ERSFQ circuits resistant to severe variations in bias current. For different components within the bias network, trends are considered and advantageous tradeoffs are discussed.

The proposed guidelines provide a means to decrease the bias current of an FJTL, and thereby reduce physical area and power dissipation. By reducing the size of the FJTL, the overall bias current of a circuit can be lowered, supporting further increases in circuit complexity. The proposed guidelines can be integrated into commercial EDA bias network design tools for prospective ERSFQ VLSI circuits, incentivizing SFQ as a promising beyond CMOS technology.

- [1] M. A. Manheimer, 'Cryogenic Computing Complexity Program: Phase 1 Introduction,' IEEE Transactions on Applied Superconductivity , vol. 25, no. 3, pp. 1-4, June 2015.
- [2] I. I. Soloviev, N. V. Klenov, S. V. Bakurskiy, M. Y. Kupriyanov, A. L. Gudkov, and A. S. Sidorenko, 'Beyond Moore's Technologies: Operation Principles of a Superconductor Alternative,' Beilstein Journal of Nanotechnology , vol. 8, pp. 2689-2710, November 2017.
- [3] D. S. Holmes, A. L. Ripple, and M. A. Manheimer, 'Energy-Efficient Superconducting Computing - Power Budgets and Requirements,' IEEE Transactions on Applied Superconductivity , vol. 23, no. 3, p. 1701610, June 2013.
- [4] K. K. Likharev and V. K. Semenov, 'RSFQ Logic/Memory Family: a New Josephson-Junction Technology for Sub-Terahertz-ClockFrequency Digital Systems,' IEEE Transactions on Applied Superconductivity , vol. 1, no. 1, pp. 3-28, March 1991.
- [5] D. E. Kirichenko, S. Sarwana, and A. F. Kirichenko, 'Zero Static Power Dissipation Biasing of RSFQ Circuits,' IEEE Transactions on Applied Superconductivity , vol. 21, no. 3, pp. 776-779, January 2011.
- [6] K. Gaj, Q. P. Herr, V. Adler, A. Krasniewski, E. G. Friedman, and M. J. Feldman, 'Tools for the Computer-Aided Design of Multigigahertz Superconducting Digital Circuits,' IEEE Transactions on Applied Superconductivity , vol. 9, no. 1, pp. 18-38, March 1999.
- [7] C. J. Fourie, 'Digital Superconducting Electronics Design Tools -Status and Roadmap,' IEEE Transactions on Applied Superconductivity , vol. 28, no. 5, pp. 1-12, August 2018.
- [8] A. M. Kadin, C. A. Mancini, M. J. Feldman, and D. K. Brock, 'Can RSFQ Logic Circuits be Scaled to Deep Submicron Junctions?' IEEE Transactions on Applied Superconductivity , vol. 11, no. 1, pp. 10501055, March 2001.
- [9] T. Jabbari, G. Krylov, S. Whiteley, E. Mlinar, J. Kawa, and E. G. Friedman, 'Interconnect Routing for Large-Scale RSFQ Circuits,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 5, pp. 1-5, August 2019.
- [10] T. Jabbari, G. Krylov, S. Whiteley, J. Kawa, and E. G. Friedman, 'Global Signaling for Large Scale RSFQ Circuits,' Proceedings of the Government Microcircuit Applications &amp; Critical Technology Conference , March 2019.
- [11] O. A. Mukhanov, 'Energy-Efficient Single Flux Quantum Technology,' IEEE Transactions on Applied Superconductivity , vol. 21, no. 3, pp. 760-769, June 2011.
- [12] N. Yoshikawa and Y. Kato, 'Reduction of Power Consumption of RSFQ Circuits by Inductance-Load Biasing,' Superconductor Science and Technology , vol. 12, no. 11, pp. 918-920, November 1999.
- [13] S. Polonsky, 'Delay Insensitive RSFQ Circuits With Zero Static Power Dissipation,' IEEE Transactions on Applied Superconductivity , vol. 9, no. 2, pp. 3535-3538, June 1999.
- [14] S. S. Meher, C. Kanungo, A. Shukla, and A. Inamdar, 'Parametric Approach for Routing Power Nets and Passive Transmission Lines as Part of Digital Cells,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 5, pp. 1-7, August 2019.
- [15] C. Shawawreh, D. Amparo, J. Ren, M. Miller, M. Y. Kamkar, A. Sahu, A. Inamdar, A. F. Kirichenko, O. A. Mukhanov, and I. V. Vernik, 'Effects of Adaptive DC Biasing on Operational Margins in ERSFQ Circuits,' IEEE Transactions on Applied Superconductivity , vol. 27, no. 4, pp. 1-6, June 2017.
- [16] I. V. Vernik, A. F. Kirichenko, O. A. Mukhanov, and T. A. Ohki, 'Energy-Efficient and Compact ERSFQ Decoder for Cryogenic RAM,' IEEE Transactions on Applied Superconductivity , vol. 27, no. 4, pp. 1-5, June 2017.
- [17] N. K. Katam, O. Mukanov, and M. Pedram, 'Simulation Analysis and Energy-Saving Techniques for ERSFQ Circuits,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 5, pp. 1-7, August 2019.
- [18] M. B. Ketchen, J. Timmerwilke, G. W. Gibson, and M. Bhushan, 'ERSFQ Power Delivery: A Self-Consistent Model/Hardware Case Study,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 7, pp. 1-11, October 2019.
- [19] G. Li, J. Ren, Y. Wu, L. Ying, M. Niu, L. Chen, and Z. Wang, 'Research on the Bias Network of Energy-Efficient Single Flux Quantum Circuits,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 5, pp. 1-5, August 2019.
- [20] S. R. Whiteley, 'Josephson Junctions in SPICE3,' IEEE Transactions on Magnetics , vol. 27, no. 2, pp. 2902-2905, March 1991.
- [21] A. F. Kirichenko, I. V. Vernik, M. Y. Kamkar, J. Walter, M. Miller, L. R. Albu, and O. A. Mukhanov, 'ERSFQ 8-Bit Parallel Arithmetic Logic Unit,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 5, pp. 1-7, August 2019.
- [22] O. Mukhanov, A. F. Kirichenko, and D. E. Kirichenko, 'Low Power Biasing Networks for Superconducting Integrated Circuits,' U.S. Patent No. 9,853,645, December 26, 2017.