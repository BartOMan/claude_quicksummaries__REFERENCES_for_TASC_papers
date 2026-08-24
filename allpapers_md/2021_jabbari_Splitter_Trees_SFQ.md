## Splitter Trees in Single Flux Quantum Circuits

Tahereh Jabbari , Student Member, IEEE , Gleb Krylov , Student Member, IEEE , Jamil Kawa, and Eby G. Friedman , Fellow, IEEE

Abstract -Theincreasing complexity of modern rapid single flux quantum (RSFQ) circuits has made the issue of multiple fanout of growing importance. Most RSFQ gates can only drive a single output. Splitter gates can however distribute an SFQ pulse to multiple fanout. To drive N SFQ gates, N -1 splitters with a fanout of two are required. Large splitter trees are often used in high speed VLSI complexity SFQ systems. These splitters require significant area and increase the path delay. In this paper, three area and power efficient splitter topologies for large scale RSFQ circuits are introduced. These SFQ splitters are an active splitter tree with fewer JJs, a passive splitter, and a multi-output active splitter. A methodology is presented for determining when to use passive or active splitters. Tradeoffs among the number of JJs, bias current of each stage, and delay are reported along with a marginanalysis. The proposed splitters greatly reduce the required bias currents and delay of large scale RSFQ circuits by enabling multiple fanout. The methodologies and techniques are applicable to automated layout and clock tree synthesis for large scale SFQ integrated circuits.

Index Terms -Single flux quantum, electronic design automation, superconducting integrated circuits, superconductive digital electronics.

## I. INTRODUCTION

S UPERCONDUCTIVE electronics and, specifically, rapid single flux quantum (RSFQ) circuits are attracting significant attention as a promising ultra-low power and ultra-high speed circuit technology for beyond CMOS exascale supercomputers [1], [2]. SFQ gates exhibit switching delays on the order of a few picoseconds and a switching energy of ∼ 10 -19 J - suitable for high performance, energy efficient systems [3], [4]. The energy dissipated by modern CMOS devices is approximately two to three orders of magnitude greater than the energy dissipated by SFQ circuits [5], which demonstrates the promise of SFQ technology as a replacement for CMOS for supercomputers and data

Manuscript received November 27, 2020; revised March 8, 2021; accepted March 25, 2021. Date of publication April 5, 2021; date of current version May 14, 2021. This work was supported by the Department of Defense (DoD) Agency-Intelligence Advanced Research Projects Activity (IARPA) through the U.S. Army Research Office under Contract W911NF-17-9-0001. The effort depicted is supported by the Department of Defense (DoD) Agency-Intelligence Advanced Research Projects Activity (IARPA) through the U.S.Army Research Office under Contract No. W911NF-17-9-0001. The content of the information does not necessarily reflect the position or the policy of the Government, and no official endorsement should be inferred. (Corresponding author: Tahereh Jabbari.)

Tahereh Jabbari, Gleb Krylov, and Eby G. Friedman are with the Department of Electrical and Computer Engineering, University of Rochester, Rochester, NY 14627 USA (e-mail: gkrylov@ur.rochester.edu; friedman@ece.rochester.edu). Jamil Kawa is with the Synopsys Inc., Mountain View, CA 94043 USA.

Color versions of one or more figures in this article are available at https: //doi.org/10.1109/TASC.2021.3070802.

Digital Object Identifier 10.1109/TASC.2021.3070802

1051-8223 © 2021 IEEE. Personal use is permitted, but republication/redistribution requires IEEE permission. See https://www.ieee.org/publications/rights/index.html for more information.

centers [6]-[8]. The energy of point-to-point CMOS interconnects is approximately six orders of magnitude greater than the energy dissipated by a passive superconductive interconnect [7], [9]. Superconductive IC technology is also suitable for high performance computing applications and has been demonstrated to operate at frequencies approaching 80 GHz for an RSFQ arithmetic logic unit with an 8 b datapath [10], [11]. Circuits have been fabricated with over 361,600 JJs in the MIT Lincoln Laboratory SFQ5ee process [12]. Significant advancements in manufacturingsuperconductiveelectronicsforprospectiveexascale computing systems have enabled circuit densities exceeding one million JJs per cm 2 with a feature size of 350 nm for the MIT Lincoln Laboratory SFQ5ee process [12]-[18] - sufficient to enable large scale SFQ circuits. The lack of electronic design automation (EDA) tools, however, is currently a serious issue complicating the development of complex SFQ circuits. EDA tools require a novel set of guidelines, methodologies, and algorithms for automated layout and interconnect routing. With the development of EDA tools for superconductive electronics [4], [19]-[22], the complexity of SFQ circuits is expected to greatly increase.

Due to some key limitations in SFQ as compared to CMOS such as gate-level pipelining and fanout constraints, many EDA tools developed for CMOS can not be used for SFQ technology; however, general synchronization principles and techniques commonly used in CMOS are applicable to SFQ technology [23], [24]. Novel design concepts, automation tools, and architectures for SFQ circuits, therefore, require development to exploit the inherent high performance and low power characteristics of SFQ circuits.

Driving multiple RSFQ gates is a challenging issue in automated layout and clock tree synthesis (CTS) due to the limited fanout capability of RSFQ circuits. Unlike conventional CMOS, RSFQ gates and flip flops exhibit a fanout of one. Splitters provide multiple fanout, although increase the physical area and power dissipation. To drive multiple fanout, a binary tree of splitters is often used where n -1 splitters with a fanout of two are needed to produce n outputs [6], [25], [26]. These splitters significantly increase the delay, power, and area of a clock distribution network. Yamada and Fujimaki [27] proposed a passive splitter with a fanout of four for ballistic signal distribution in the routing layer. The driver for this passive splitter requires significant bias current and area. Novel splitter circuits are therefore desirable to support larger fanout while managing the delay, bias currents, and area.

Fig. 1. Active splitter tree with shared JJs and a fanout of four, (a) circuit, and (b) operational waveforms. I C 1 = 350 µ A, I C 2 = I C 3 = 250 µ A, I bias = 600 µ A, L 1 = 1.2 pH, and L 2 = L 3 = 1.6 pH.

<!-- image -->

In this paper, several SFQ splitters are proposed and evaluated. Astandard SFQ splitter is described in section II. Splitter topologies to support multiple outputs with less area, lower delay, and improved bias margins are introduced in section III. Novel SFQ splitters including an active splitter tree with fewer JJs, a passive splitter, and a multi-output splitter are presented in section III. A comparison of different splitter trees is provided in section IV. The paper is concluded in section V.

## II. SFQ SPLITTERS

Propagating a signal to multiple outputs is a common requirementindigital VLSI circuits. RSFQ gates, since this logic family is pulse based, cannot however support more than a single fanout. A standard logic gate can therefore drive only one other cell. Due to the limited fanout of SFQ circuits, the distribution of SFQ data and clock pulses is a primary concern in complex SFQ circuits. A special SFQ splitter gate is required to convert an SFQ pulse into multiple SFQ pulses without a significant decrease in the amplitude of the voltage pulse. An SFQ splitter is typically connected at the output of an SFQ gate when driving multiple fanout.

A standard active splitter with a fanout of two is shown in Fig. 1(a) [28]. The two output waveforms of the splitter gate are illustrated in Fig. 1(b). The simulated bias margins of a splitter with a fanout of two is approximately -60 % and +65 % when connected to a Josephson transmission line (JTL) at the input and output of the splitter. In this paper, the output delay of a standard splitter is the propagation delay between π switching the input JJ J 1 and π switching the output JJ J 2 . The delay of the splitter is about 3 ps (for the 10 kA/cm 2 SFQ5ee process).

In active splitters, JJs can be cascaded to support multiple fanout. To achieve the desired output pulse at each fanout, the size (area and critical current) of the input JJ is made greater than the size of the output JJs. The size of the input JJ is dependent upon the number of outputs. In a standard active splitter with a fanout of two, the input junction J 1 is √ 2 times [1], [28]-[30] larger than the standard JJs used in a JTL. The input JJ J 1 in Fig. 1(a) provides the needed energy for driving the two output JJs, J 2 and J 3 .

An important issue in standard active splitters is the limited fanout, typically two, and the large bias current. To support multiple fanout, an active splitter tree is used which significantly

Fig. 2. Active splitter tree with shared JJs and a fanout of four. I C 1 = 500 µ A, I C 2 = I C 3 = 350 µ A, I C 4 to I C 7 = 250 µ A, I b 1 = 700 µ A, I b 2 = I b 3 = 500 µ A, L 1 = 1.2 pH, and L 2 = 1.6 pH.

<!-- image -->

increases the total bias current and physical area. Novel area and power efficient splitter topologies that support multiple outputs are presented in Section III.

## III. NOVEL SFQ SPLITTER TOPOLOGIES

In this section, three novel splitter topologies to support multiple fanout are proposed to reduce delay, bias current, and physical area. A margin analysis is also presented, and tradeoffs and limitations of the different configurations are discussed. An active splitter tree with fewer Josephson junctions is introduced in section III-A. A passive splitter is introduced in section III-B. A multi-output splitter is introduced in section III-C.

## A. Active Splitter Tree With Fewer JJs

A topology for an active splitter tree with fewer JJs is described in this section. An active splitter tree with a fanout of four is shown in Fig. 2. The proposed active splitter requires fewer JJs since the initial splitter stage shares the last JJ with the following stage. The input junction J 1 is two times ( √ 2 × √ 2 ) larger than the output junctions due to cascading two standard splitters [1], [28]-[30]. The output junctions, J4 to J7 , amplify the SFQ pulse at the splitter outputs.

The proposed active splitter with fewer JJs uses less area and is faster. For the proposed active splitter with four outputs, two fewer JJs are required as compared to a standard active splitter due to sharing of the JJs between the two stages. The delay of the proposed active splitter tree and a standard active splitter tree with a fanout of four is, respectively, 6 and 7 ps (in a 10 kA/cm 2 process technology). The effect of the output inductance of the first splitter and the input inductance of the second splitter is also included in the delay of the splitter trees.

The simulated bias current margins of the proposed splitter tree connected to the JTL buffers at both the input and output are -35%, +22%. The margins of the critical current for the input JJ, middle JJs, and output JJs are, respectively, ( -60%, +15%), ( -55%, +40%), and ( -60%, +70%). The inductances exhibit wide margins, ± 60%. Note that the proposed active splitter tree

Fig. 3. Passive splitter configuration with a fanout of two. I b 1 = 150 µ A, I C 1 = 250 µ A, I C 2 = 175 µ A, I b 2 = 150 µ A, and the characteristic impedance of each line is 8 Ω (in a 10 kA/cm 2 technology).

<!-- image -->

exhibits smaller bias margins as compared to a standard splitter tree ( -60%, +65%). Due to the different size of the junctions within the proposed splitter tree, the JJs are biased at different critical currents. This difference in bias currents lowers the bias margins. Increasing the bias current of each stage lowers the delay [31]. The bias margins also shrink with an increase in bias current. A tradeoff between the bias margins and delay in the active splitter tree therefore exists. A splitter configuration with wider margins produces a longer delay as compared to a standard active splitter. Decreasing the bias current of each stage by 10% produces a wider positive margin of ± 33% and a longer delay of 9 ps.

A primary issue of the proposed topology is the larger size of the JJs (by a factor of √ 2 ) within the splitter tree due to the cascaded splitters. The input junction of each splitter stage is the output junction of the previous splitter stage. This structure significantly increases the size of the initial input junction within the splitter tree. Placing a chain of JTL elements with a progressively higher critical current before the splitter tree enhances the interface of the splitter tree with the RSFQ gates. The size of the JJs in a chain of JTLs depends upon the initial input junction of the splitter tree and the fanout of the tree.

## B. Passive Splitter

A passive splitter divides an SFQ pulse into two pulses. This topology can be placed within the routing layers. The topology of a passive splitter to support multiple outputs is described here. The proposed passive splitter is adapted from [27], [32]. The passive splitter described in [27] requires large JJs and bias currents within the driver. In this paper, a topology for a passive splitter is presented to decrease the area and bias currents while increasing the bias margins. The passive splitter, depicted in Fig. 3, consists of superconductive stripline segments, a common driver, and a separate receiver. The JJ of the driver is connected to a passive splitter and launches an SFQ pulse onto a PTL line. The PTL receiver consists of one slightly underdamped JJ and a large inductance. The input inductor and resistor in the receiver improve the impedance match between the PTL and receiver.

The proposed passive splitter with two outputs requires fewer JJs while also lowering the delay and requiring less area for long interconnects. Due to the absence of the extra buffer stages, active splitter, and an additional PTL driver in a passive splitter with a fanout of two, six fewer JJs are required to drive an SFQ pulse over the same length as compared to a standard active splitter with two PTLs. The delay of the proposed passive splitter with a fanout of two (including the driver, receiver, and PTL lines) is 10.5 ps (in a 10 kA/cm 2 process technology [33], [34]).

The primary issues of this approach are that the impedance match and load of each branch of the splitter segment affect the bias margins and pulse attenuation characteristics. Due to the coincidence of the input SFQ pulse in a transmission line with the reflection of the previous pulse, resonant effects can occur in long PTL lines [7] which degrade the matching characteristics, decrease bias margins, and/or produce incorrect circuit behavior. The matched driver and receivers [35] sufficiently match the impedance between the two output passive splitter with other RSFQ gates.

Thebiasmarginshavebeenevaluatedfortheproposedpassive splitter topology. The passive splitter segment is modeled as a lossless transmission line with a characteristic impedance of 8 ohms for each path. The bias margins of the passive splitter with a matched driver and receiver connected to the JTL buffers are -45%, +28%. The margins of the critical current of the JJ within the driver and receiver are, respectively, ( -35%, +85%) and( -30%,+55%)Themarginsoftheinductanceinthereceiver are -85%, +25%.

ComplexRSFQcircuitsmanufacturedinamodernfabrication technology utilize multiple metal layers [33], [34]. These layers are frequently grouped into two categories - active gate layers, where the JJs and close connections are located, and routing layers, reserved for typically long, passive transmission lines. The choice of whether to use an active or passive splitter is based on the physical characteristics of the splitters and interconnect layers. A splitter tree composed of standard 1:2 splitters requires greater area within the active gate layer. For this splitter, a separate interconnect segment is frequently required to connect distant SFQ gates, increasing both the area and delay. The proposed passive splitter requires less area within the active gate layer. The passive splitter can be used for both data and clock signals.

## C. Multi-Output Active Splitter

A topology for a multi-output active splitter is described in this section. Active splitters with a fanout of three and four are depicted in Fig. 4. The standard output junctions amplify the SFQ pulse at each output. The input junction of the splitters is larger than the output junctions to provide sufficient energy for driving three and four standard output JJs. The circuit parameters, such as the inductances, critical current of the JJs, and bias currents, affect the bias margins. All of the circuit parameters are chosen to bias each of the JJs to 0.8 of the critical current with one bias current source. The bias margins of the splitter with a fanout of three and four are, respectively, -33%, +39% and -30%, +35% with identical load circuits connected to each

Fig. 4. Aactive splitter with multiple outputs, a) fanout of three. I b 1 = 1 mA, I C 1 = 430 µ A, I C 2 to I C 4 = 250 µ A, L 2 = 1 pH, and L 3 to L 5 = 1.7 pH, and b) fanout of four. I b 2 = 1.3 mA, I C 1 = 500 µ A, I C 2 to I C 5 = 250 µ A, L 2 = 1.32 pH, and L 3 to L 6 = 2.64 pH.

<!-- image -->

output of the splitter. The margins of the critical current of the input and output JJ within the splitter with a fanout of three are, respectively, ( -80%, +45%) and ( -50%, +60%). The margins of the inductances are ± 70%. In the active splitter with a fanout of four, the margins of the critical current of the input and output JJ are, respectively, ( -55%, +45%) and ( -45%, +35%). The inductances also exhibit wide margins, ± 80%. The output delay of a splitter with a fanout of three and four is, respectively, 2.5 ps and 3.5 ps.

A tradeoff between the delay and bias margins exists in the proposed multi-output splitter. A higher bias current is closer to the critical current, affecting the robustness while decreasing the delay. This condition reduces the positive bias margin of the splitter. Due to the number of outputs and the large input JJ, the bias margins of the proposed splitter are narrower than a standard active splitter. Active splitters with multiple fanout transfer an SFQ pulse to the multiple independent outputs while requiring less area, power, and delay.

The input inductance L 1 of the multi-output splitter plays an important role in ensuring correct operation due to the large input junction. This inductance manages the leakage current between the splitter and the previous SFQ cell [36]. The inductance margins are ± 30% which is sufficient for large scale circuits.

Alayout of the active multi-output splitter with three outputs is depicted in Fig. 5. The physical dimensions of the circuit are 40 µ m × 40 µ m. The layout is based on the MIT LL SFQ5ee fabrication process for a 10 kA/cm 2 process technology [33], [34], [37]. A layout of the active splitter with a fanout of four has the same physical dimensions as the splitter with a fanout of three. The dimensions of the driver and receiver for the passive splitter are 40 µ m × 20 µ m [35]. Using the same design rules and guidelines for the layout, the active splitter tree with shared JJs exhibits a larger area as compared to the multi-output splitter. The dimensions of the active splitter tree are 40 µ m × 60 µ m.

## IV. COMPARISON OF SPLITTER TOPOLOGIES

The proposed splitters are compared in this section. Tradeoffs between the bias margins and delay of each of the splitter topologies are also discussed. The different topologies of the splitter trees with a fanout of two to sixteen are compared to

Fig. 5. Layout of the proposed active splitter with three outputs.

<!-- image -->

review the physical area and power characteristics of each of the splitter topologies.

An important application of efficient splitter trees and multioutput splitters is the clock distribution network [38]-[40]. A clock signal is required for most SFQ gates. The clock pulse is therefore split many times and distributed to multiple gates. The clock distribution network requires significant area and delay due to the many JJs within the active splitter trees. The proposed area and power efficient splitters can significantly reduce the overall delay and power dissipation of a clock network.

The bias margins and delay of a splitter with different fanout are listed in Table I. The active splitters are connected by the PTL segment within the splitter tree. The standard splitter exhibits wider positive bias margins, while requiring significant area and power. For a fanout of four, the proposed active splitter with fewer JJs and the passive splitter exhibit narrower bias margins but require less area and bias current as compared to a standard active splitter. Both the active multi-output splitters and the standard active splitter exhibit a similar negative margin of -30%. The active multi-output splitters with a fanout of three and four, respectively, exhibit an acceptable positive margin of +40%and+35%.Themulti-output splitters require significantly less bias current, area, and delay. The passive splitter exhibits a narrower margin as compared to the active splitters but requires less area within the active gate layers.

In the active splitter trees, PTL segments are frequently required to connect the splitter stages within a tree. These PTL segments significantly increase the overall delay, area, and power of a system. The proposed passive splitter requires less area and delay to drive an SFQ pulse over the same length as compared to the active splitter topologies.

The proposed multi-output splitter trees require fewer JJs and less area as compared to both active and passive splitter trees. The proposed splitters also require less bias current per output as compared to a standard active splitter. The ratio of the total

TABLE I COMPARISON OF SPLITTERS WITH DIFFERENT NUMBER OF OUTPUTS

bias current of a splitter tree to the number of outputs is listed in Table I. This ratio can be used to compare the efficiency of different splitter topologies. The proposed multi-output splitters exhibit higher power and area efficiency than the active splitter trees.

An important tradeoff between the bias margins and delay exists in the proposed active splitters. The delay and positive bias margin are lower with a higher bias current. An active splitter with wide bias margins exhibits a greater delay and dissipates less power. These tradeoffs among these different splitter topologies affect the choice of splitter for inclusion within automated routing and CTS tools.

## V. CONCLUSION

The single fanout of RSFQ circuits is an important issue in automated layout and clock tree synthesis of VLSI complexity RSFQ circuits. Pulse splitters enable multiple fanout for RSFQ gates. Passive and active splitter topologies with fewer JJs to support multiple fanout are proposed in this paper. These splitters exhibit lower area, power dissipation, and delay.

A margin analysis is also presented for the different multioutput splitter topologies. The active multi-output splitters effectively manage the area, delay, and bias currents in VLSI complexity RSFQ circuits. Design guidelines and tradeoffs are also presented for the passive and active splitters. These guidelines are applicable for use in automated layout and clock tree synthesis tools.

## ACKNOWLEDGMENT

The authors would like to thank O. A. Mukhanov for helpful discussions. The content of the information does not necessarily reflect the position or the policy of the Government, and no official endorsement should be inferred.

## REFERENCES

- [1] K. K. Likharev and V. K. Semenov, 'RSFQ logic/memory family: A. new josephson-junction technology for sub-terahertz-clock-frequency digital systems,' IEEETrans.Appl. Supercond. , vol. 1, no. 1, pp. 3-28, Mar. 1991.
- [2] K. Gaj, E. G. Friedman, and M. J. Feldman, 'Timing of multi-gigahertz rapid single flux quantum digital circuits,' J. VLSI Signal Process. Syst. , vol. 16, no. 2/3, pp. 247-276, Jun./Jul. 1997.
- [3] T. R. Lin and M. Pedram, 'Retiming for high-performance superconductive circuits with register energy minimization,' Proc. IEEE/ACM Int. Conf. Comput.-Aided Des. , Nov. 2020, pp. 1-9.
- [4] D. K. Brock, 'RSFQ technology: Circuits and systems,' Int. J. High Speed Electron. Syst. , vol. 11, no. 1, pp. 307-362, Mar. 2001.
- [5] T. N. Theis and H. S. P. Wong, 'The end of moore's law: A. new beginning for information technology,' Comput. Sci. Eng. , vol. 19, no. 2, p. 41-50, Mar. 2017.
- [6] T. Jabbari and E. G. Friedman, 'Global interconnects in VLSI complexity single flux quantum systems,' Proc. Workshop Syst.-Level Interconnect: Problems Pathfinding Workshop , 2020, pp. 1-7.
- [7] T. Jabbari, G. Krylov, S. Whiteley, J. Kawa, and E. G. Friedman, 'Repeater insertion in SFQ interconnect,' IEEE Trans. Appl. Supercond. , vol. 30, no. 8, Dec. 2020, Art. no. 5400508.
- [8] S. N. Shahsavani, T. Lin, A. Shafaei, C. J. Fourie, and M. Pedram, 'An integrated row-based cell placement and interconnect synthesis tool for large SFQ logic circuits,' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, Jun. 2017, Art. no. 1302008.
- [9] T. Jabbari, G. Krylov, S. Whiteley, J. Kawa, and E. G. Friedman, 'Resonance effects in single flux quantum interconnect,' Proc. Government Microcircuit Appl. Crit. Technol. Conf. , Mar. 2020, pp. 1-5.
- [10] J. Y. Kim and J. H. Kang, 'High frequency operation of a rapid single flux quantum arithmetic and logic unit,' J. Korean Phys. Soc. , vol. 48, no. 5, pp. 1004-1007, May 2006.
- [11] T. V. Filippova et al. , '20 GHz operation of an asynchronous wavepipelined RSFQ arithmetic-logic unit,' Phys. Procedia , vol. 36, pp. 59-65, Sep. 2012.
- [12] S. K. Tolpygo and V. Semenov, 'Increasing integration scale of superconductor electronics beyond one million josephson junctions,' J. Phys.: Conf. Ser. , vol. 1559, Sep. 2020, Art. no. 0112002.
- [13] S. K. Tolpygo, 'Superconductor digital electronics: Scalability and energy efficiency issues,' LowTemp.Phys. , vol. 42, no. 5, pp. 361-379, May 2016.
- [14] V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, 'AC-Biased shift registers as fabrication process benchmark circuits and flux trapping diagnostic tool,' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, Jun. 2017, Art. no. 1301409.
- [15] S. Tolpygo, E. B. Golden, T. J. Weir, and V. Bolkhovsky, 'Inductance and mutual inductance of superconductor integrated circuit features with sizes down to 120 nm. part I,' Jan. 2021, arXiv:2101.07457 .
- [16] S. K. Tolpygo et al. , 'Fabrication processes for superconductor electronics: Current status and new developments,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1102513.
- [17] V. K. Semenov, Y. A. Polyakov, and S. Tolpygo, 'Very large scale integration of josephson-junction-based superconductor random access memories,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1302809.
- [18] V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, 'New AC-Powered SFQ digital circuits,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1301507.

- [19] K. Gaj, Q. P. Herr, V. Adler, A. Krasniewski, E. G. Friedman, and M. J. Feldman, 'Tools for the computer-aided design of multigigahertz superconducting digital circuits,' IEEE Trans. Appl. Supercond. , vol. 9, no. 1, pp. 18-38, Mar. 1999.
- [20] C. J. Fourie, 'Digital superconducting electronics design tools - status and roadmap,' IEEE Trans. Appl. Supercond. , vol. 28, no. 5, Aug. 2018, Art. no. 1300412.
- [21] M. A. Manheimer, 'Cryogenic computing complexity program: Phase 1 introduction,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1301704.
- [22] Y. Kameda, S. Yorozu, and Y. Hashimoto, 'A new design methodology for SingleFlux-Quantum (SFQ) logic circuits using passive-transmission-line (PTL) wiring,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 508-511, Jun. 2007.
- [23] N. K. Katam, J. Kawa, and M. Pedram, 'Challenges and the status of superconducting single flux quantum technology,' Proc. IEEE Design, Automat. Test Europe Conf. Exhib. , Jun. 2019, pp. 1-7.
- [24] N. K. Katam and M. Pedram, 'Logic optimization, complex cell design, and retiming of single flux quantum circuits,' IEEE Trans. Appl. Supercond. , vol. 28, no. 7, Oct. 2018, Art. no. 1301409.
- [25] N. Katam, A. Shafaei, and M. Pedram, 'Design of multiple fanout clock distribution network for rapid single flux quantum technology,' Proc. IEEE Asia South Pacific Des. Automat. Conf. , Feb. 2017, pp. 384-389.
- [26] T. Jabbari, J. Kawa, and E. G. Friedman, 'H-tree clock synthesis in RSFQ circuits,' Proc. IEEE Baltic Electron. Conf. , Oct. 2020, pp. 1-5.
- [27] T. YamadaandA.Fujimaki,'Anovelsplitterwithfourfan-outsforballistic signal distribution in single-flux-quantum circuits up to 50 Gb/s,' Jap. J. Appl. Phys. , vol. 45, no. 9, pp. L262-L264, Feb. 2006.
- [28] 'Stony brook RSFQ cell library,' Jun. 2019. [Online]. Available: http: //www.physics.sunysb.edu/Physics/RSFQ/Lib/PB/split.html
- [29] T. V. Duzer and C. W. Turner, Principles of Superconductive Devices and Circuits , 2nd ed., Upper Saddle River, NJ, USA: Prentice-Hall, 1981.
- [30] M. L. Schneider and K. Segall, 'Fan-out and fan-in properties of superconducting neuromorphic circuits,' J. Appl. Phys. , vol. 128, no. 21, Dec. 2020, Art. no. 214903.
- [31] M. Otsubo, Y. Yamanashi, and N. Yoshikawa, 'Improvement of operating margin of SFQ circuits by controlling dependence of signal propagation time on bias voltage,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Jun. 2013, Art. no. 1300904.
- [32] O. Mukhanov, 'Transformation and perspectives of digital superconducting electronics,' in Proc. Eur. Conf. Appl. Supercond. , Sep. 2017, pp. 1-42.
- [33] S. K. Tolpygo et al. , 'Advanced fabrication processes for superconducting verylarge-scale integrated circuits,' IEEETrans.Appl.Supercond. , vol. 26, no. 3, Apr. 2016, Art. no. 1100110.
- [34] S. K. Tolpygo et al. , 'Inductance of circuit structures for MIT LL superconductor electronics fabrication process with 8 niobium layers,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1100905.
- [35] T. Jabbari, G. Krylov, S. Whiteley, E. Mlinar, J. Kawa, and E. G. Friedman, 'Interconnect routing for large scale RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1102805.
- [36] M. Maruyama, M. Hidaka, and T. Satoh, 'Improved high-T c superconductor sampler circuits using josephson transmission line buffers,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 401-404, Jun. 2003.
- [37] S. S. Meher, C. Kanungo, A. Shukla, and A. Inamdar, 'Parametric approach for routing power nets and passive transmission lines as part of digital cells,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1101307.
- [38] E. G. Friedman, 'Clock distribution design in VLSI circuits - an overview,' in Proc. IEEE Int. Symp. Circuits Syst. , May 1993, pp. 1475-1478.
- [39] K. Gaj, E. Friedman, M. Feldman, and A. Krasniewski, 'A clock distribution scheme for large RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. AS-5, no. 2, pp. 3320-3324, Jun. 1995.
- [40] E. G. Friedman, 'Clock distribution networks in synchronous digital integrated circuits,' Proc. IEEE , vol. 89, no. 5, pp. 665-692, May 2001.