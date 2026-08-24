## Scalability of Superconductor Electronics: Limitations Imposed by AC Clock and Flux Bias Transformers

Sergey K. Tolpygo , Senior Member, IEEE

Abstract -Flux transformers are the necessary component of all superconductor digital integrated circuits utilizing flux biasing and ac power excitation and clocking of logic cells, e.g., adiabatic quantum flux parametron (AQFP), reciprocal quantum logic (RQL),superconducting sensor arrays, qubits, etc. On average, one transformer is required per one Josephson junction. We consider limitations to the integration scale (device number density) imposed by the critical current of the ac power transmission lines (primaryofthetransformers) and cross-coupling between the adjacent transformers. The former sets the minimum linewidth and the mutual coupling length in the transformer, whereas the latter sets the minimum spacing between the transformers. Decreasing linewidth of superconducting (Nb) wires increases kinetic inductance of the transformer's secondary, decreasing its length and mutual coupling to the primary. This limits the minimum size. As a result, there is a minimum linewidth w min ∼ 100 nm, which determines the maximum achievable scale of integration. Using AQFP circuits as an example, we calculate dependences of the AQFP number density on linewidth for various types of microstrip-based and stripline-based transformers and inductors available in the SFQ5ee fabrication process developed at MIT Lincoln Laboratory, and estimate the maximum circuit density as a few million AQFPs per cm 2 . We propose an advanced fabrication process for a 10 × increase in the density of AQFP and other ac-powered circuits. In this process, inductors are formed from a patterned bilayer of a geometrical inductance material, Nb, deposited over a layer of high kinetic inductance material, e.g., NbN. Individual pattering of the bilayer layers allows to create stripline inductors in a wide range of inductances, from the low values typical to Nb striplines to the high values typical for NbN thin films, and preserve sufficient mutual coupling in stripline transformers with extremely low cross-talk. Energy efficiency of ac-powered circuits is limited by dielectric losses in the ac power transmissions lines. Problems of scaling associated with multiphase ac power distribution are discussed.

Index Terms -Adiabatic quantum flux parametron (AQFP), cross-talk, inductance, kinetic inductance, microstrip, mutual inductance, NbN, reciprocal quantum logic (RQL), RSFQ, SFQ circuits, stripline, superconductor electronics, superconducting flux transformer, superconductor integrated circuit.

Manuscript received 5 October 2022; revised 12 December 2022; accepted 14 December 2022. Date of publication 19 December 2022; date of current version 5 January 2023. This work was supported by the Under Secretary of Defense for Research and Engineering via Air Force Contract under Grant FA8702-15D-0001. This article was recommended by Associate Editor I. V. Vernik.

The author is with the Lincoln Laboratory, Massachusetts Institute of Technology, Lexington, MA 02421 USA (e-mail: sergey.tolpygo@ll.mit.edu).

Color versions of one or more figures in this article are available at https://doi.org/10.1109/TASC.2022.3230373.

Digital Object Identifier 10.1109/TASC.2022.3230373

## I. INTRODUCTION

S UPERCONDUCTOR digital electronics easily beats CMOS and prospective beyond CMOS technologies in such important performance metrics as energy dissipation and processing speed. Superconductor single flux quantum (SFQ) electronics [1] hold the record in clock speed of simple circuits, about 770 GHz [2], and in its much slower, adiabatic implementations can operate with energy per bit near the Landauer's thermodynamic limit k B T ln 2 [3], [4], [5], [6]. However, these performanceadvantagessofarhavenotbenefitedanylarge-scale computational system because integration scale of superconductor digital circuits is currently three to four orders of magnitude lower than that of the CMOS circuits. For instance, the largest demonstrated circuits in superconductor electronics have about one million Josephson junctions (JJs) [7], [8], whereas the modern CMOS circuits have over 50 billion transistors, a 50000 × difference [9].

Due to the recent progress in fabrication technology of niobium-based superconductor integrated circuits, the minimum feature size was reduced to 120 nm [10], [11]. This allowed for an increase in the circuit density to about 1.5 · 10 7 Nb/Al-AlO x /Nb JJs per square centimeter [10], [12], about 10-fold increase from the previous level [7]. For a comparison, the present density of CMOS circuits is 1000 × higher, about 1.4 · 10 10 transistors per cm 2 [9]. The largest demonstrated density of superconductor JJ-based random access memory is 1 Mbit cm -2 [13]. For a comparison, RAM technology based on spin-transfer torque magnetic RAM, the so-called STT-MRAM, operating at room temperature has a 1000 × higher density [14], although it uses devices similar to multilayered sandwich-type JJs.

In [15], the author argued that superconductor digital electronics is fundamentally less scalable than semiconductor electronics because of the fundamental difference in information encoding. Indeed, in superconductor electronics, information is encoded, stored, and transferred by magnetic flux quanta created by superconducting currents circulating in closed superconducting loops (inductors) interrupted by JJs. In semiconductor electronics, information is encoded by a stationary electric charge on the gates of field-effect transistors. Obviously, localized charge on a capacitor occupies less space than the moving chargesuperconducting loop current. Hence, charge-based devices can always be made smaller and their circuits made denser and more scaled-up than flux-based devices and circuits.

1051-8223 © 2022 IEEE. Personal use is permitted, but republication/redistribution requires IEEE permission. See https://www.ieee.org/publications/rights/index.html for more information.

The goal of this article is to establish fundamental limits on the scalability, i.e., the maximum circuit density, of ac-powered superconductor digital electronics, imposed by two basic components of all superconductor integrated circuits: inductors and transformers. Limitations imposed by resistively shunted sandwich-type(trilayer) JJs like Nb/Al-AlO x /Nbwerediscussed in [15].

A problem of superconducting transformers has emerged with advancement of ac-powered and ac-clocked superconductor logic solutions instead of the dc-powered RSFQ logic [1]. Starting from the original parametric quantron (PQ) [3], [16], [17] and going to its analogs and reincarnations-dc flux parametron [18], [19], quantum flux parametron (QFP) [20], [21], and adiabatic quantum flux parametron (AQFP) [22], [23]-all logic solutions based on parametric devices require a multiphase ac excitation. These ac signals are inductively coupled (via transformers) to the devices in order to modulate their Josephson inductance (critical current of JJs) and produce a change in the logic state and a parametrically amplified output current upon applying a weak input current I in. The only exception is a dc-powered nSQUID logic whose devices, nSQUIDs, use transformers to create a large negative mutual inductance between the SQUID arms [4], [24].

Another example is reciprocal quantum logic (RQL) [25], [26], which requires four-phase ac power delivered via transformers to propagate positive and negative SFQ pulses in the same direction along Josephson transmission lines (JTLs), and provide energy to and synchronization of RQL gates.

In addition to the power and clock delivery in all types of superconductor logic and memory circuits, superconducting qubit circuits, superconducting sensor arrays, etc., superconducting flux transformers (mutual inductors) are used to provide flux biasing, signal inverting (NOT function), and coupling between cells.

As an example, for numerical simulations with well-defined parameters, we will consider what is now known as AQFP cell shown in Fig. 1(a). It is identical to QFP and PQ cells, and may only slightly differ in parameter values. The AQFP logic requires, at least, one ac transformer per JJ. Therefore, the circuit density (device number density) cannot be higher than the density of the transformers. A very similar analysis to the offered below can be easily done for RQL gates and their JTLs, which typically require one transformer per two junctions [25], [26], [27], and for any other ac-powered logic, memory, and quantum circuits.

## II. AC EXCITATION AND DC FLUX TRANSFORMERS: PHYSICAL LIMITATIONS

## A. Main Features of AC Excitation Transformers

The typical use of transformers in superconductor electronics is to provide a dc flux bias and/or ac flux excitation to logic cells with amplitude Φ 0 γ ; typically, γ = 2 . Very often, e.g., in AQFP, both dc flux bias Φ dc = Φ 0 / 2 and ac excitation are required. They can be applied either via the same or two separate transformers. For simplicity, we consider only the first case,

Fig. 1. (a) Schematics of PQ, QFP, and AQFP cells. It consists of two identical RF SQUIDs connected in parallel. In the adiabatic regime of operation, the typical parameters of AQFPs are β L ≡ 2 πI c 1 L 2 / Φ 0 = 0 . 2 , β Lq ≡ 2 πI c 1 L q / Φ 0 = 1 . 6 , and I c 1 = 50 µ A is the critical current of junctions J 1 [33], [34]. (b) Sketch of a top view of a planar transformer between the primary inductor L 1 , a part of the ac-power transmission line, and the QFP cell inductors L 2 which are either microstrip (one ground plane, not shown) or stripline (two ground planes) inductors with length l L , laying in the same or adjacent plane as the L 1 . The mutual running length of the inductors L 1 and L 2 , which determines their total mutual inductance M , is l m . The full QFP consists of two connected half-cells (RF SQUIDs). Also shown is the second row of QFPs. Their inputs are inductively coupled to other QFPs via the output inductor L out. Spacing S y between the QFP rows (or the ac power lines) determines their cross-coupling-ac excitation in QFP#2 produced by the power line of the QFP#1 in the same column, and vice versa. Spacing S x determines cross-coupling between the output transformers L q , L out of QFPs in the same row. For the actual layout examples, see [37]. Inductor L q needs to be placed perpendicular to inductors L 1 and L 2 in order to minimize direct coupling of the ac excitation to the output.

<!-- image -->

requiring γ = 1 , because using two transformers increases the total transformer area by about 2 × .

In order to provide the required dc bias and ac excitation, the mutual running length of the transformer primary wire, L 1 , and the transformer secondary wire, L 2 , should be

<!-- formula-not-decoded -->

where I ex = I dc + I ac is the amplitude of the total excitation current that is fed into the L 1 , and M l is the mutual inductance per unit length between the primary and secondary wires.

On the other hand, the transformer secondary, L 2 is always a part of the logic cell and its inductance is determined by the cell design parameter

<!-- formula-not-decoded -->

where I cJ is the critical current of the cell JJ. Hence, length of the inductor L 2 is given by

<!-- formula-not-decoded -->

where L Ll is the inductance per unit length of the secondary.

Obviously, the transformer with the smallest area in this simple two-wire configuration can only be formed if l m ≤ l L or if

<!-- formula-not-decoded -->

Note that for AQFPs shown in Fig. 1, the total length of the ac excitation transformer secondary is 2 l L because it consists of two connected SQUIDs. Hence, the AQFP transformer can only be formed if l m ≤ 2 l L . Multiturn transformers with l m &gt; 2 l L are possible but will not be considered here because they always occupy much larger area and, hence, restrict the circuit density more than the simplest parallel-wire transformer shown in Fig. 1(b).

The mutual inductance, M , of any two conductors is always smaller than the magnetic part of the self-inductance L M of the conductors

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where L Kl is kinetic inductance per unit length of a wire with thickness t and width w , λ is the magnetic field penetration depth, κ ≤ 1 is the coupling coefficient between the magnetic inductances of the primary, and L M 1 and the secondary, L M 2 . If the primary and secondary are formed by inductors of the same type with equal magnetic inductance per unit length, L M 1 l = L M 2 l = L Ml , the required primary excitation current from (4) is

<!-- formula-not-decoded -->

This current is significantly larger than I cJ and must increase with decreasing the cross-section of the inductors , i.e., with increasing the scale of integration.

On the other hand, I ex must be smaller than some maximum current I max related to the critical current, I c , of superconducting (Nb) wires forming the transformer

<!-- formula-not-decoded -->

where α &lt; 1 is a safety factor and j c is the superconductor critical current density. Hence, the minimum possible inductor cross-sectional area A = wt can be found from the condition

<!-- formula-not-decoded -->

which is not a quadratic equation because of a nontrivial dependence of L Ml and κ on t and w .

In superconductors, the fundamental limit to the j c is the Ginzburg-Landau critical current density j GL c given by

<!-- formula-not-decoded -->

where B c is the thermodynamic critical magnetic field of the superconductor and λ is the magnetic field penetration depth [28]. Using the microscopic theory [29], Bardeen [30] expressed the depairing critical current density as

<!-- formula-not-decoded -->

where B c 0 and ∆ 0 are the thermodynamic critical field and the energy gap at zero temperature T = 0, respectively; ρ is the film resistivity in the normal state, and λ (0) = ( /planckover2pi1 ρ µ 0 π ∆ 0 ) 1 / 2 .

For niobium, B c ( T ) = B c 0 (1 -T 2 /T 2 c ) , T c = 9.1 K, and B c 0 = 0.155 T, giving B c = 0 . 122 T at 4.2 K. The measured value of the penetration depth in our Nb films at 4.2 K is λ = 90 nm. Then, (11) gives j GL c (4 . 2 K) = 0.59 A/ µ m 2 for our Nb films at 4.2 K, which agrees with the value following from (12) and the measured values of ∆ 0 and residual ρ in our films. The measured critical current density j c in Nb wires with w ≈ t ≈ 200 nm is somewhat lower than this theoretical value, about 0.37 A/ µ m 2 [10], [31]. Since j c may decrease further with reducing the wire dimensions, e.g., due to increasing Nb contamination and resistivity, it would be practical to take αj c = 0.25 A/ µ m 2 , a 33% lower value than the measured critical current density, in order to have some safety margin.

To proceed further with (10) and find the dependence of the transformer area on the linewidth, we need to specify the type of the transformer in order to determine L Ml and κ . Before going to numerical results, as a simple illustration, we consider a transformer formed by two parallel microstrips laying in the same plane.

For superconducting microstrips with rectangular crosssection, the magnetic part of the inductance per unit length is given in [32] by

<!-- formula-not-decoded -->

where d 1 is the dielectric thickness between the microstrip and the ground plane, and µ is the magnetic permeability of the dielectric, hereafter assumed to be 1. From the fabrication process practicality, we are mostly interested in narrow wires with deeply scaled features w ≈ t and w,t /lessmuch 2( d 1 + λ ) . In this case, the minimum cross-section area is given by solution of the equation

<!-- formula-not-decoded -->

To solve (14), let us use the typical parameters of ac excitation and flux bias transformers in AQFPs as an example: I cJ = 50 µ A, γ = 1 , and β L = 0 . 2 [22], [33], [34]. In the widely used fabrication process SFQ5ee [35], transformers using Nb microstrips M6aM4 (standing for microstrips with the signal

trace on the layer M6 above the M4 ground plane in [35]) with d 1 = 615nmarethemostconvenientbecausetheyaretheclosest to the layer of JJs. Solution of (14) at κ = 1 gives the smallest cross-section area of the primary wire A min = 1.34 · 10 -2 µ m 2 , corresponding to the minimum linewidth and the film thickness of about ( A min ) 1 2 ≈ 116 nm. At smaller cross-sections, the required transformer cannot be made because the excitation current required to induce Φ 0 flux amplitude in the transformer secondary would exceed the critical current of the transformer primary wire. Achieving the largest coupling κ = 1 in the transformer is not possible. For a more realistic κ = 0.5, solution of (14) gives A min = 2.18 · 10 -2 µ m 2 and ( A min ) 1 2 = 148 nm.

The minimum linewidth following from the minimum crosssection area determines the minimum possible coupling length between the transformer primary and secondary, i.e., the minimum possible size of the ac-powered cell along the ac power transmission line. Existence of the minimum linewidth and of the minimum cell size is the first limit on scalability of ac-powered superconductor electronics (AQFP, RQL, etc.) caused by the finite superconducting critical current of the primary wire in the ac and dc flux-biasing transformers. This limit can be reached already in a 90-nm technology node and 90-nm linewidth. Further reduction of the linewidth would not significantly increase the density of superconductor integrated circuits using ac powering of logic gates. This is our first conclusion.

## B. Output Coupling Transformer in AQFP and Inductor L q

In this subsection, we consider limitations on the cell height (in the y -direction perpendicular to the ac power transmission line) and width. For specificity, we use the typical parameters of AQFPs, whereas the same arguments and estimates apply to other types of ac-powered superconductor logics.

Length of the inductor L q in AQFP in Fig. 1, l q , is given by

<!-- formula-not-decoded -->

where L ql is inductance per unit length of inductor L q , which may differ from the per length inductance of the excitation transformer secondary L Ll . At the typical AQFP parameters, I cJ = 50 µ Aand β Lq = 1.6, L q is 10.53 pH; at L ql ∼ 1 pH/ µ m, l q is about 10 µ m.

Inductor L q needs to be placed perpendicular to the inductors L 1 and L 2 , forming a T-shape, in order to minimize direct coupling of the ac excitation to the output. The aspect ratio of this 'T' in the typical AQFP cell (width to length ratio) is 2 l L /l q = 1:4 because the ratio of the optimal parameters β q /β L = l q /l L is 1.6:0.2 = 8:1.

Consider inductive coupling with mutual inductance M q between the L q and the output inductor L out connected to the next AQFP or forming a part of the buffer which sums up the output currents of three AQFPs comprising the majority (MAJ3) gate [37]. Parametrically amplified input current I in creates a current

<!-- formula-not-decoded -->

in the L q , which in turn creates a current

<!-- formula-not-decoded -->

in the output inductor. The maximum value of L out can be determined from the condition I out ≥ I in ≈ 10 µ A, which is the current required to drive the next AQFP. This gives

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The latter determines the maximum distance over which the AQFP output data can be sent over without amplification, i.e., the maximum length of the inductor L out ; L outl is inductance per unit length of the output inductor. Using M ql ∼ 0.3 pH/ µ m, l q = 10 µ mand L outl ∼ 1 pH/ µ m, we get l out ∼ 60 µ m, about 6 l q . Decreasing L outl by increasing the output inductor width may help in transmitting data to 10 × larger distances than the height of the AQFP cell.

The superconducting material and cross-section of wires for inductors L q and L out are selected such that both currents I q (16a) and I out (16b) are smaller than the critical current of the corresponding wires. For Nb wires with αj c = 0.25 A/ µ m 2 , the minimum cross-section of L q is A min = 8 · 10 -4 µ m 2 , which is an order of magnitude smaller than A min following from (14) and corresponds to the wire dimensions ( A min ) 1 2 ∼ 30 nm. This is the ultimate limit to reduction of the linewidth of Nb wires.

## C. QFP Minimum Area and Maximum Circuit Density

The minimum possible area of the typical QFP is A QFP = 2 l L l q = β L β q Φ 2 0 2 π 2 L Ll L ql I 2 cJ if the area occupied by the junctions J 1 , the transformer primary, and vias between the inductors can be neglected. If the JJs cannot be hidden inside this rectangle, their area, which in the simplest case is A JJ = 2 I cJ /J c , needs to be added; J c is the Josephson critical current density of the junctions, e.g., J c = 100 µ A/ µ m 2 in the SFQ5ee fabrication process [35]. Then, the QFP maximum number density is

<!-- formula-not-decoded -->

where χ &lt; 1 is the area filling factor. The density (18a) is maximized at

<!-- formula-not-decoded -->

Using parameters of the optimized AQFP cells, β L = 0.2 and β q = 1.6 [33], [34], [39], J c = 100 µ A/ µ m 2 , and the maximum expected value L Ll = L ql ≈ 1 pH/ µ m for Nb inductors, we get I opt cJ = 191 µ A and the maximum density of parametrons n QFP ( I opt cJ ) = 1.75 · 10 7 cm -2 at χ = 1 . Unfortunately, this I opt cJ is too high for using in AQFPs from the standpoint of energy dissipation, which is proportional to I cJ . To provide ultralow dissipation in these adiabatic devices, I cJ is reduced as much as possible to a level set by an acceptable bit error rate (BER) in complex circuits; BER grows exponentially with I cJ reduction. The most typical value is I cJ = 50 µ A [33], [34], [39], a factor of four lower than I opt cJ .

At I cJ = 50 µ A, (18a) gives n QFP = 3 . 5 · 10 6 cm -2 at χ = 1 . This is our second conclusionthe number density of AQFPs using Nb inductors is limited from above to about three million AQFPs per cm 2 , corresponding to about 1 · 10 6 cm -2 density of AQFP majority gates composed of three (MAJ3) AQFPs. Increasing the Josephson critical current density to J c = 600 µ A/ µ m 2 , which is available in MIT LL fabrication processes [36], [37], has negligible effect on n QFP since the device density at low I cJ values is fully determined by the AQFP inductors; see (18a).

The n QFP estimate above does not account for possible limitations caused by a finite supercurrent-carrying capacity of the ac power transformer and for a possibility of using inductors with higher L ql values. Accounting for these factors requires a detailed analysis given in Section III but does not change the order of magnitude of the maximum density of AQFPs.

Increasing L ql values significantly above 1 pH/ µ m can be done using kinetic inductance (7). For instance, a 40-nm thick Mo 2 N film used in the SFQ5ee process [35] has L Kl ≈ 8 /w pH/ µ m ( w is in micrometers) [38], which is &gt;&gt; 1 pH/ µ m at w &lt; 1 µ m. However, a short strip of kinetic inductor can be used only if L q is galvanically coupled to the next AQFP, the so-called directly coupled AQFP [40]. If inductive coupling to the next AQFP is required, the mutual inductance M q between the short strip of a kinetic inductor and the output inductor L out , which is proportional to the length of L q , is going to be small. Careful optimization is needed in this case, as will be discussed in Section III. Also, j c of kinetic inductors is much smaller than j c of Nb because of a much larger λ in (13). For instance, if the L q is made of a 40-nm-thick Mo 2 N kinetic inductor in the SFQ5ee process, its critical current would be reached at w ≤ 0.5 µ m [38]. Nevertheless, implementation of specially optimized kinetic inductors in AQFPs, and in superconductor electronics in general, could substantially decrease the size of logic cells and increase their number density [15].

## D. Cross-Coupling of Transformers and Circuit Density

Another factor limiting the practical density of transformers and ac-powered cells is cross-talk between them. AC-powered cells are arranged along transmission lines forming a power grid feeding ac power into them, as shown schematically in Fig. 1(b) for QFPs; see also [34] and [39]. Cells arranged along one horizontal power transmission line induce some ac excitation in the cells coupled to the adjacent transmission lines of the grid. The minimum distance S min between the adjacent rows of the ac-powered cells is determined by the acceptable level of cross-coupling between their transformers. We define this cross-coupling as the ratio of the mutual inductance M cross between the primary L 1 of the transformer in one row and the secondary L 2 of the transformer in the adjacent row to the mutual M inductance within the same transformer. This ratio determines the ac excitation amplitude induced by a transmission line feeding one row of the cells, e.g., QFPs, into the adjacent rows of the cells below and above.

In a given fabrication process, the minimum practical spacing between the adjacent rows of QFPs is set by the max[ l q , S min ] , where S min is the spacing at which the maximum acceptable level of cross-talk is reached. As an example, we will hereafter use 5% cross-talk as this maximum acceptable level. Reducing the length l q below the S min would not increase n QFP. Hence, S min sets the maximum value of L ql required to maximize the density of QFPs, e.g., by using kinetic inductors

<!-- formula-not-decoded -->

where S min is in micrometers.

Wealso need to consider cross-coupling between the adjacent QFPs in the same row, i.e., coupling between parallel inductors L q and L out in two adjacent QFPs. Current I q 1 in QFP #1 induces flux Φ 21 = M q 21 I q 1 in the adjacent QFP #2 and current I out 21 in its output inductor L 2 out. Reliable operation of the circuit may require this flux to be small in comparison with flux Φ 0 created by ac excitation in QFP #2 and the induced current to be small in comparison to self-current I out 22 (16) at the output of QFP #2. As in the case of ac excitation transformers, we define cross-coupling between the output transformers as

<!-- formula-not-decoded -->

Its maximum tolerable value sets the minimum spacing S q between inductors L q and L out in the adjacent QFPs in the same row along the ac power transmission line.

## III. MICROSTRIP TRANSFORMERS AND QFP NUMBER DENSITY

For more accurate estimates of the number density of the ac transformers and QFPs, in the following sections, we will consider all types of possible transformers with the goal to minimize the area of the QFP cell.

## A. QFP Transformers Formed by Two Parallel Microstrips in One Plane

Mutual inductance of two microstrips in the same plane decreases slowly with distance between the centers of their cross-sections, p x = w + s , and is given in [32] by

<!-- formula-not-decoded -->

Fordefiniteness, we take parameters of the most advanced fabrication processes for superconductor electronics: the SFQ5ee process [35]. These parameters and the process cross-section are given in [Table I, 11] and [Fig. 1, 32]. Nb wires are on the process layer M6 with thickness t = 200 nm, 200-nm thick Nb ground plane is layer M4, and the dielectric thickness between them is d 1 = 615 nm. The currently allowed minimum linewidth and spacing between the microstrips in the same plane is 250 nm. Hopefully, with the progress of fabrication technology, narrower lines and gaps between metal lines with dielectric fill will becomepossible, e.g., due to the development of a damascene-type processing allowing for much smaller spacings s ∼ w .

Fig. 2 shows the mutual inductance per unit length of two microstrips M6 above M4 ground plane (M6aM4) as a function of their linewidth at spacing s = 250 nm and the microstrip

Fig. 2. Parameters of Φ 0 -excitation in-plane transformers using microstrips M6 above M4 ground plane (M6aM4), spaced at s = 250 nm in the SFQ5ee process; the transformers cross-section is sketched in the inset. Mutual inductance of the two microstrips per unit length, M l (right scale): black dash (21); (·)-numerical simulations using wxLC [41]. Self-inductance per unit length, L Ll (right scale): black solid curve is the sum of magnetic (13) and kinetic (17) inductances; ( /squaresolid )-numericalsimulationsusingwxLC.ThicknessesofNblayers forming the microstrips: t M 6 = 200 nm, M4 ground plane t M 4 = 200 nm; dielectric thickness d 1 = 615 nm, λ = 90 nm. Solid red curve is the mutual running length l m (1) required to induce Φ 0 in the AQFP secondary formed by two inductors L 2 , assuming the maximum allowed current density of 0.25 A/ µ m 2 in the primary inductors L 1 . The top solid blue curve is the length 2 l L (3) of the two inductors L 2 in the AQFP cell at I cJ = 50 µ A and β L = 0 . 2 . Below the w min ≈ 70 nm, corresponding to the circled intersection, l m &gt; 2 l L and transformers with the required mutual inductance M cannot be formed. Dash-dot curve is 0 . 1 l q ; l q is the length (15) of M6aM4 microstrip inductor L q with the same width as the L 1 and L 2 ; at β Lq = 1 . 6 , l q = 8 l L . Short dash is 0.01 l out ; l out is the maximum length (17b) of the output inductor L out, assuming it is also a M6aM4 microstrip with the same width w , coupled at s = 250 nm to the microstrip L q along the full length of the L q .

<!-- image -->

self-inductance per unit length (dash curve, scale on the right). It also shows the required mutual running length l m in (1) of the primary L 1 , the length 2 l L in (3) of the secondary formed by two inductors L 2 (solid red curve). To show in the same scale, we also plotted 1/10 th of the l q given by (15) and 1/100 th of the l out given by (17b), assuming that the output transformer is also formed by two M6aM4 microstrips spaced at s = 250 nm, i.e., that the output transformer is of the of same design as the ac excitation transformer. In addition to analytical expressions given in [32], we used a very accurate numerical inductance extractor wxLC developed by M. Khapaev [41] and λ = 90 nm for all Nb layers. The analytical and numerical, shown by solid symbols, results are practically indistinguishable.

Below the linewidth w min ≈ 67 nm, the required mutual running length of the ac excitation line l m needs to be longer than the total length 2 l L of the QFP inductors L 2 in order to provide a Φ 0 sum of the dc flux bias and ac excitation amplitude without exceeding the maximum allowed current I max = αj c w min t M 6 = 3.5 mA in the primary. The parallel-line microstrip transformer with the required parameters cannot be formed using smaller linewidths . The minimum cross-section area of the primary w min t M 6 = 0.0134 µ m 2 perfectly agrees with the A min estimated using (14) in Section II-A.

For hypothetical transformers with s = w , the excitation current limit is reached below w min ≈ 50 nm, corresponding to I max ≈ 2.5 mA, due to a stronger mutual coupling in the transformer.

In practical circuits, we want to reduce the ac excitation current I ex in the primary as much as possible in order to minimize ac power loss caused by dielectric losses in the transmission lines, which grows as I 2 ex . The minimum I ex is obtained at the largest possible mutual running length at a given linewidth, i.e., at l m = 2 l L . In this case, the full QFP transformer consisting of twoparallel wires in the same plane has area A tr = 2 l L (2 w + s ) , where l L is given by (3). The minimum size of the rectangular QFP cell for tiling is (2 l L + s ) × (2 w +2 s + l q ) , where (2 l L + s ) is the minimum possible tiling pitch in the x -direction along the ac power transmission line, and (2 w +2 s + l q ) is the tiling pitch (effective height of the QFP cell) in the y -direction.

## B. Cross-Coupling of Planar Microstrip-Based Transformers and the Limits on QFP Number Density

To mitigate cross-coupling between two parallel transformers in the adjacent rows of QFPs, e.g., shown in Fig. 1(b), the spacing S y between the primary of transformer #1 and the secondary of transformer #2 should be much larger that the spacing s between the wires in the transformer. The cross-coupling M ( S, w ) /M ( s, w ) between two M6aM4 microstrip-based planar transformers is shown in Fig. 3(a) for a few linewidths, where M ( s, w ) is given by (21) at s = 250 nm and M ( S, w ) is given by (21) with S replacing s . Numerical simulations using wxLC [41] are shown by (·) and perfectly agree with (21).

We see that providing a low cross-talk between the in-plane microstrip transformers requires quite large spacings, e.g., crosstalk below 10% requires S &gt; 2.5 µ m and below 5% requires S ≥ 3.75 µ m. The cross-talk increases with increasing w and decreases with decreasing s .

The maximum acceptable cross-talk level depends on the circuit. For specificity, we hereafter take 5% as the maximum acceptable cross-talk level. This defines the minimum spacing between the transformers, S min ( w,s ) , a function of the in-transformer linewidth and spacing. This function is shown in Fig. 3(b) for the planar M6aM4 microstrip transformers with s = 250 nm (solid blue curve) in the SFQ5ee process and for the transformers with w = s (red dash curve).

If we restrict the spacing S y between the horizontal rows of the QFPs to the largest of the l q + s and S min in order to keep cross-talk between the ac excitation transformers at the acceptable level, the number density of the QFPs becomes

<!-- formula-not-decoded -->

where χ ≤ 1 is the area filling factor.

Linewidths w &lt; w min cannot be used in the QFP ac excitation transformers because of the critical current limitation, but can be used for the inductor L q . In this case, the cell height continues to decrease because reduction of the inductor L q width, w q , reduces l q , whereas the cell effective width (2 l L + s ) remains constant and equal 2 l L ( at w min ) + s . Hence, if w &lt; w min and

Fig. 3. (a) Cross-coupling M ( S, w )) /M ( s, w )) between in-plane (planar) microstrip-based transformers with various linewidths and in-transformer spacings, s , as a function of spacing S between the adjacent transformers. All the curves were calculated using (21) for the transformers using M6aM4 microstrips; (·)-numerical simulations using wxLC software [41] for w = 110 nm. (b) Dependence of the spacing S min at which mutual inductance between the transformers reduces to 5% of the in-transformer mutual inductance, referred to as a 5% cross-coupling distance, on the linewidth: blue squares-transformers with the primary to secondary spacing s = 250 nm; red dots-transformers in a hypothetical process with s = w for w ≤ 250 nm. Solid blue line and red dash curve are, respectively, a linear fit S min ( w,s ) = 3 . 57 + 2 . 63 × 10 -3 w and parabolic fit S min ( w,s ) = 2 . 357 + 9 . 51 × 10 -3 w -8 . 3 × 10 -6 w 2 in these two cases; here S min is in micrometers and w is in nanometers.

<!-- image -->

<!-- image -->

l q + s ≥ S min, the number density of QFPs is given by

<!-- formula-not-decoded -->

In the opposite case S min &gt; l q + s , the number density is given by

<!-- formula-not-decoded -->

Fig. 4. Theoretical number density (assuming 100% area filling, χ = 1) of AQFPs using M6aM4 microstrip inductors and transformers in the SFQ5ee process with parameters of Nb inductors L 1 , L 2 , and L q given in Fig. 2 for the AQFPcellinFig. 1. Inset shows the cross-section of the AQFP transformers. The bottom blue solid ( w &gt; w min ) and short dash ( w &lt; w min ) curves correspond to s = 250 nm and spacing S x between the AQFP in the x -direction set by the 5% cross-coupling distance S q ( w,s ) because 2 l L + s &lt; S q ( w,s ) at all linewidths, whereas spacing S y in the y -direction is set by the size of the AQFP cell, l q + s . The black solid and short dash curves correspond to the n QFP determined only by the physical dimensions of the AQFPs, respectively (22a) and (22b), ignoring cross-coupling. The uppermost red dash-dot curve is (24) for a hypothetical process with s = w and the physical dimensions of the AQFP, ignoring cross-coupling between AQFPs in the same horizontal row. The red dash and short dash curves in the middle also correspond to s = w but account for the cross-coupling in the same row (24b), using the dependence S q ( w,s ) = S min ( w,s ) in Fig. 3(b); see text. Cross-coupling between the adjacent rows in the y -direction can be neglected in all the cases because l q + s &gt; S min ( w,s ) at all the linewidths.

<!-- image -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Using Nb microstrips M6aM4 as AQFP inductors in the SFQ5eeprocess gives l q ≥ S min for all linewidths down to about 20nm.Hence,(22a)appliesifweignorecross-couplingbetween adjacent QFPs in the same row; see below. Dependences (22a) and (22b) for QFPs with the M6aM4 inductors and transformers with s = 250 nm are shown in Fig. 4 by the solid black ( w ≥ w min) and black dash ( w &lt; w min) curves.

So far, we have ignored cross-talk between the data output transformers L q , L out of adjacent QFPs in the same horizontal row. However, placing adjacent QFPs in the same row at the minimum spacing s = 250 nm gives the horizontal spacing S x between inductors L q in the range 2.75 ≤ 2 l L + s ≤ 3.85 µ m. At these distances, the cross-talk between the parallel output inductors can be very substantial as follows from (21) and Fig. 3(a). So the QFPs may need to be placed further apart in the x -direction (along the ac transmission line) and spaced at some distance S q to reduce the output cross-talk to the acceptable level. Then, (22a) and (22b) are replaced by,

respectively, following equations:

<!-- formula-not-decoded -->

where we use w also for the width of the inductors L q .

If the minimum spacing of QFPs in both the x -and y -directions are set by the acceptable cross-coupling, then

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

If the acceptable cross-talk level between the adjacent inductors L q is the same as between the excitation transformers, e.g., less than 5%, then S q = S min because the output inductors are of the same type as in the ac excitation transformers. Then, the minimumpitchofAQFPplacementinthesamerowis S min + w , and the number density of AQFPs using the planar M6aM4 transformers is given by (24a) and (24b). The corresponding number density of AQFPs is shown in Fig. 4 by the lowest blue solid (24a) and short-dash (24b) curves calculated using the dependences in Fig. 3(b) and S q ( w,s ) = S min ( w,s ) .

For the currently available SFQ5ee process with s = 250 nm and already demonstrated linewidth w ≈ 110 nm [10], [11], the theoretical AQFP number density is about 3.5 · 10 6 cm -2 , set by the physical dimensions of the AQFP and ignoring in-row cross-talk. This numerical analysis agrees perfectly with the simple estimate obtained in Section II-C and based on (18a). The maximum density reduces to about 2.5 · 10 6 cm -2 if cross-talk needs to be kept below the 5% level. These densities correspond to, respectively, 1.17M and 0.83M MAJ3 logic gates per cm 2 . We emphasize that the considered AQFPs are about 30 times smaller in area than 30 µ m × 40 µ mAQFP buffer cells used in [39].

Reducing spacing between superconducting lines below 250 nm in a hypothetical future development of the SFQ5ee process would bring some increase to the device density, as follows from (21)-(24) and Fig. 3(b). For instance, using s = w would increase mutual coupling in the planar transformer, resulting in w min ≈ 50 nm. Cross-coupling between the microstrip transformers would also noticeably decrease, resulting in S q (5%) = S min (5%) ≈ 2.75 µ m at w = 50 nm, as shown in Fig. 3(b). This minimum spacing can be used to estimate the absolutely maximum possible value of n QFP in this technology.

Even at w = 40 nm, l q = 5.66 µ m is still twice as large as the S min, and the n QFP is still given by (22a) and (22b), as shown in Fig. 4 by the uppermost dash-dot red curve, reaching about 9 · 10 6 cm -2 at w = 50 nm. If the placement pitch S x of AQFPs in the same row is set by the 5% cross-talk requirement between the output transformers S q = S min ( w,s ) , the n QFP is given by (24a) and (24b), and shown in Fig. 4 by the red dash ( w ≥ w min ) and short dash ( w &lt; w min ) curves, respectively, reaching about 6.2M cm -2 at w = 40 nm.

Foramorerealistic 90-nm process ( w = s = 90nm), n QFP = 4.65 · 10 6 cm -2 and 3.80 · 10 6 cm -2 without and with accounting for the in-row cross-talk, respectively. This is less than 33% increase over the density of AQFPs at w = 90 nm and s = 250 nm, which would hardly justify a very complex process development required for achieving the much smaller spacing s = 90 nm.

## C. AQFPs With M6aM4 Microstrips and Kinetic Inductor L q

The main density limiter of AQFPs in the SFQ5ee process is a very large length of the inductor L q . It is determined by the β q value, which is set by the optimization of the range of adiabatic switching between the two flux states encoding information in AQFPs; see, e.g., [34]. Let us assume that in a hypothetical, next generation process, we can introduce an additional layer of kinetic inductors close to the layer of JJs and use it to make l q + s ≤ S min ( w,s ) , the length set only by the cross-talk requirements. This would bring the AQFPs in the regime (23) or (25). The only apparent drawback of reducing l q significantly is a proportional reduction of the mutual inductance M q in the output transformer between L q and L out, and of the data transfer length l out in (17b). This reduction can be partially compensated by increasing the width of the output inductor and thereby decreasing its inductance per unit length L outl in (17b).

Using (19), the optimum value of the linear inductance of the kinetic inductance material replacing Nb in the M6aM4 microstrips for L q would be L ql ≈ 2.8 pH/ µ m, a factor of 4 higher value than the linear inductance of 250-nm-wide Nb microstrips M6aM4. For the reasonable width of the L q , w q = 250 nm, the required sheet inductance is 0.7 pH/sq, a factor of 10 lower than the sheet inductance of the 40-nm Mo 2 N films [38] currently used in the SFQ5ee process as rf choke kinetic inductors for biasing ERSFQ circuits [42].

If in the hypothetical fabrication process we preserve somehow Nb microstrips M6aM4 in the ac excitation transformer, the n QFP could be increased up to the limit set only by the acceptable cross-talk between the AQFPs. For this, the pitch of the AQFP placement in y -direction should be 2 w + s + S min, and the pitch in the x -direction should be S x = S q + w q , where w q is the width of the kinetic inductor L q , because in the entire range of linewidths in Fig. 4, the physical width of the AQFP transformers 2 l L + s is less than S q (5%) . Due to the critical current limitation, the minimum expected value of w q is about 200 nm. In the described case, the expected number density of AQFPs using a kinetic inductor L q depends very weakly on the w and w q as can be seen from the lowest black curve in Fig. 5. Below w min = 50 nm, n QFP in this regime does not increase because the height of the AQFP cell is set by the S min ( w min , s ) and no longer depends on the linewidth. The saturation value ( n QFP ) max = 5.6 · 10 6 cm -2 is larger than the number density which could be achieved using the ultranarrow Nb wires; see the

Fig. 5. Theoretical number density (assuming 100% area filling, χ = 1) of AQFPs n QFP in a hypothetical process using Nb microstrip inductors M6aM4 in the ac excitation transformers and a kinetic inductor L q with width w q = 200nm and length l q + s = S min ( w,s ) , where S min ( w,s ) is a 5% cross-coupling spacing between the AQFP primary in one row and the AQFP secondary in the adjacent row shown in Fig. 3(b). Inset: a layout sketch, aerial view, of the inductors in two AQFPs located in the adjacent rows running along transmission lines in the horizontal xdirection. The bottom solid black curve (25) corresponds to s = 250 nm and the AQFP placement pitch in the x -direction equal to S x = S q ( w q ) + w q determined by the 5% cross-coupling level between inductors L q and L out in the adjacent AQFPs in the same horizontal row. The dash black curve (23) corresponds to the n QFP at S x equal the physical width of the ac transformer 2 l L + s and S y = S min ( w,s ) . Red dash-dot curve (23a) corresponds to a hypothetical process with spacing s = w in the excitation transformer and the AQFP cell size 2 l L + s determined by the transformer length; the number density saturates below w min = 50 nm at n QFP = 20.2M per cm 2 , a level given by (23b). Red short-dash curve also corresponds to the case s = w , but with spacing between the inductors L q set by a 5% cross-coupling level S q ( w q ) = 3.92 µ maccording to the data in Fig. 3(b) (red dots).

<!-- image -->

bottom blue curves in Fig. 4. More importantly, these densities can be achieved at modest and already demonstrated linewidths and spacings, and only require implementing a kinetic inductor for L q .

If a more aggressive process with s = w is used, even higher values of n QFP could be achieved as shown in Fig. 5 by the uppermost dash-dot curve, corresponding to (23a), because of a smaller cross-talk and smaller S min between the ac transformers; see Fig. 3(b). At w &lt; w min, the n QFP saturates at ( n QFP ) max = 2 · 10 7 cm -2 , a level given by (23b) at w = w min = 50 nm. This packing density could provide up to 6.7M MAJ3 logic gates per cm 2 and would be an 8 × improvement over the standard SFQ5ee process. However, it may still be not sufficient for general purpose computing applications.

It appears that no significant increase in the circuit density is possible with microstrip inductors in planar transformers, mainly because of their strong cross-coupling. Accounting for other omitted components, e.g., JJs and interlayer vias, may only reduce the maximum densities estimated above.

## D. AQFP Transformers Formed by Aligned Microstrips on the Vertically Spaced Planes

The area of AQFP ac excitation transformers can be decreased, at least by a factor of three, if microstrips forming the

Fig. 6. Parameters of the ac excitation transformers using aligned equal-width microstrips M7aM4 and M6aM4 for the transformers primary and secondary, respectively. Inset: cross-section of the transformer. Top blue curve is the total length 2 l L (3) of two AQFP inductors L 2 (microstrips M6aM4) forming the transformer secondary, at β L = 0 . 2 , I cJ = 50 µ A. The bottom red solid curve is mutual running length l m in (1) of the transformer primary (microstrip M7aM4) and the transformer secondary required to provide a Φ 0 flux excitation (dc + ac) in the secondary at the excitation current I max (9) in the primary, assuming the maximum current density in Nb of 0.25 A/ µ m 2 . Below w min ≈ 65 nm, l m &gt; 2 l L and the required flux excitation cannot be provided without exceeding the critical current of Nb wire M7 in the transformer primary. Mutual inductance betweentheM7aM4andM6aM4microstripsperunitlength M l calculated using (26) at d 1 = 615 nm, d 2 = 1015 nm, λ = 90 nm, and t M 4 = t M 6 = t M 7 = 200 nm is shown by the bottom black dash line; (·)-numerical simulations using wxLC and the same parameters. Self-inductance of M7aM4 microstrips per unit length, L M7 aM 4 l , the sum of (13) and (7), is shown by the solid magenta curve; ( )-numerical simulations using wxLC [41]. Dash-dot blue curve is 0 . 1 l q = 0 . 8 l L (at β q = 1.6) calculated using (15) and assuming that inductor L q is a M6aM4 microstrip of the same width as the L 1 and L 2 . Black short-dash curve is the 1/100th of the length of inductor L out calculated using (17b) and M q = M l l q , assuming that it is a M7aM4 microstrip aligned over the L q and having the of the same linewidth w .

<!-- image -->

transformer have the same width and locate above each other, over the same ground plane. In this case A tr = 2 l L w .

If L 2 of the AQFP is the M6aM4 microstrips considered in Section III-A and III-B, the only convenient transformer primary is a microstrip M7aM4 with the signal trace on niobium layer M7. Mutual inductance per unit length of two microstrips with widths w 1 and w 2 , and thicknesses t 1 , t 2 , located on different planes is given in [32] by

<!-- formula-not-decoded -->

where d 2 and d 1 are the dielectric thicknesses between the respective signal traces and the ground plane, and p x = s + w 1 + w 2 2 is the horizontal distance between the geometrical centers of the microstrips' cross-sections. In the SFQ5ee process, t 1 = t 2 = 200 nm for both layers M6 and M7, d 1 = 615 nm, and d 2 = 1015 nm, corresponding to the interlayer dielectric thickness of 200 nm.

Mutualinductance(26)ofthealignedmicrostripsM7aM4and M6aM4, p x = 0 , is shown in Fig. 6 by the lowest black dash line along with the numerically simulated dependence shown by solid dots (·). Self-inductance per unit length of M7aM4 microstrips is given by the sum of (7) and (13).

Fig. 7. Cross-talk between vertical transformers formed by the aligned equalwidth M7aM4 and M6aM4 microstrips as a function of spacing between the transformers. Cross-talk is defined as mutual inductance between the primary of transformer #1 (Tr1) and the secondary of transformer #2 (Tr2) normalized to the mutual inductance inside the transformer. All curves were calculated using (26): solid curve corresponds to the parameters of the SFQ5ee process and w = 250 nm; dash curve is for w = w min = 65 nm; dash-dot curve corresponds to a hypothetical process with reduced to 100 nm dielectric thickness between layers M6 and M7, instead of 200 nm in the SFQ5ee. S min is defined as the spacing at which the tolerable level of cross-coupling, set as 5% in this case, is reached. Dependence of S min on w is very weak and an average value S min = 4.53 µ m will be used to characterize the entire range of linewidths of interest w min ≤ w ≤ 300 nm.

<!-- image -->

Similarly to the planar transformers in Fig. 2, the required mutual running length of wires l m in the 'vertical' transformer needs to become longer than the two AQFP inductors L 2 (the transformer secondary) at w min &lt; ∼ 65 nm because the sum of the ac and dc currents in the primary required to induce flux Φ 0 in the AQFPreaches the maximum allowed value I max = αj c w min t = 3.25 mA. The required transformer cannot be formed using narrower wires. The minimum cross-section w min t M 7 = 0.013 µ m 2 agrees perfectly with A min estimated in Section II-A from the solution of (14).

Cross-talk between two parallel vertical M7-M6aM4 transformers is shown in Fig. 7 as a function of spacing S between them, for two linewidths w = 250 and 65 nm. Cross-talk is defined as the ratio of the mutual inductance between the M7 wire in transformer #1 and the M6 wire in transformer #2 to the mutual inductance in the transformer. The cross-talk very weakly depends on the w ; it reduces below the 5% level at S ≥ S min = 4.62 and 4.44 µ m, respectively, at w = 65 and 250 nm. Hence, instead of using a function S min ( w ) as in Section III-B, we can simply use a single averaged value S min = 4.53 µ m in the entire range of linewidths of interest. Overall, the cross-talk between the vertical transformers is larger than between the planar M6-M6aM4 transformers in Fig. 3 because d 2 is significantly larger than d 1 .

If L q is an M6aM4 microstrip with the same width as the L 2 , its length l q is the same as was described in Section III-B, Fig. 2, and l q &gt; S min. Hence, the AQFP number density only slightly differs from (22) and, neglecting cross-coupling in the same row

## AQFPswithtransformersM7aM4-M6aM4

Fig. 8. Theoretical number density of AQFPs using vertical transformers formed by aligned, equal-width microstrips M7aM4 (transformer primary) and M6aM4(transformer secondary) as a function of their linewidth. Inset: Top view of the AQFP cell placement along the ac power and dc flux bias transmission lines marked as dc + ac. The black solid and dash curves at the bottom correspond to Nb microstrips in the SFQ5ee process and the AQFP cell vertical spacing S y = l q + s set by the physical height of the cell and the cell effective width S x = S q + w set by the 5% cross-talk spacing S q equal approximately 4.53 µ m in the entire range of the linewidths. Blue solid and dash curves also correspond to Nb microstrips, but the cell placement pitch set by the physical width S x = 2 l L + w , ignoring the cross-talk. The uppermost red solid and red dash-dot curve in the middle correspond to a hypothetical process, in which AQFPinductor L q trace on the M6 level is made of a kinetic inductance material with width w q = 200 nm to reduce its length below the critical cross-coupling distance S min while preserving Nb microstrips as inductors L 2 in the ac excitation transformer.

<!-- image -->

of AQFPs, is

<!-- formula-not-decoded -->

This dependence is shown in Fig. 8 by the solid blue curve in the middle. At w = 65 nm and s = 250 nm, (27a) gives n QFP ≈ 6 · 10 6 cm -2 , corresponding to about two million MAJ3 gates per cm 2 .

Using w &lt; w min for the inductor L q reduces it length l q . The AQFP number density in this case is similar to (22b) and given by

<!-- formula-not-decoded -->

This dependence is shown in Fig. 8 by the blue dash curve. If cross-coupling between the AQFP outputs needs to be kept below a certain level, the adjacent inductors L q in the same row need to be spaced at a safe distance S q , and the AQFP number density reduces to

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

These dependences are shown by the lowest black solid and dash curves in Fig. 8 for a 5% cross-coupling requirement S q = S min = 4.53 µ m, following from Fig. 7.

Since for all considered linewidths, l q + s &gt; S min , the y -direction size of the AQFP cell can be reduced by using a kinetic inductor for L q to make l q + s ≤ S min . In this hypothetical process, the number density of AQFPs is similar to (23) and given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

These dependences are shown in Fig. 8 by the red solid curve saturating at ( n QFP ) max = 1.02 · 10 7 cm -2 , according to (29b).

And, finally, when the cross-talk is the factor in choosing the x - and y - placement pitches, the number density is given by

<!-- formula-not-decoded -->

and reaches the constant density at w &lt; w min

<!-- formula-not-decoded -->

These dependences are shown in Fig. 8 by the nearly horizontal red dash-dot and short-dash lines. The maximum number density in (30b) is ( n QFP ) max = 4.4 · 10 6 cm -2 at the kinetic inductor L q width w q = 0.2 µ m. This is a bit lower number than for the planar M6-M6aM4 transformers because of a larger S min-the spacing at which the cross-coupling reduces to below 5%.

The n QFP can be increased in a hypothetical fabrication process by using smaller thicknesses t 1 , t 2 , and d 2 to increase the mutual inductance in the transformer and decrease crosscoupling. For instance, at t 1 = t 2 = 200 nm and d 2 = 915 nm, corresponding to the interlayer dielectric thickness between the M7 and M6 wires of 100 nm and ∆ d = d 2 -d 1 = 300 nm in (26), the S min would decrease to about 3.8 µ m, as shown in Fig. 7.

To conclude, the achievable number densities of AQFPs using vertical microstrip-based transformers are comparable to those obtainable with the planar microstrip transformers in Section III-B because both types of the transformers have close values of the mutual inductance and similarly strong cross-coupling-the main drawback of using microstrips.

## IV. STRIPLINE TRANSFORMERS AND AQFP NUMBER DENSITY

## A. Stripline Transformers in the SFQ5ee Process

It is well known that cross-talk can be substantially reduced using stripline inductors with two ground planes instead of microstrips with one ground plane. The mutual inductance per unit length between two superconducting striplines is given in [32] by

<!-- formula-not-decoded -->

where H is the dielectric thickness between the ground planes and h i = d i + t i 2 is the distance between the bottom ground plane and the geometrical center of the cross-section of the i th signal wire, p x is the in-plane (horizontal) distance between the geometrical centers of the stripline cross-sections. At large distances, M l exponentially decreases with increasing p x , with a decay length p 0 = ( H +2 λ ) /π .

In the existing SFQ5ee process, two parallel M6aM4bM7 (standing for M6 above M4 below M7) striplines can be used for a planar stripline-based transformer near the JJs. In this case, H = 1015 nm and p 0 = 380 nm. Other possibilities would involve layers below the JJs and require multiple vias, leading to larger cell areas.

Because of a lower self-inductance and three times lower mutual inductance of the M6aM4bM7 striplines compared to the M6aM4 microstrips, lengths of the inductors L 2 and L q , and the minimum width, w min = 105 nm, shown in Fig. 9, are noticeably larger in this case than in Fig. 2. This leads to larger AQFP cell sizes and smaller n QFP shown by a solid black curve in Fig. 10. However, cross-coupling between the stripline-based transformers is dramatically lower than between the microstripbased transformers. Assuming a purely exponential decay, a 5% cross-coupling is expected at S min ≈ p 0 | ln 0 . 05 | = 1.14 µ m.The cross-coupling calculated using the full expression (31) at the in-transformer spacing s = 250 nm and numerical simulations give S min = 1.34 µ m; see Fig. 11.

ThenumberdensityofAQFPsusingM6aM4bM7striplinesin Fig. 10 is given by (22a) and (22b) because l q /greatermuch S min and 2 l L + s &gt; S min in the entire range of w . Using w &lt; w min is possible for the inductor L q , while keeping the excitation transformer linewidth at w min; this reduces the length l q and the AQFP cell area. At w = 60 nm, n QFP ≈ 3.7 · 10 6 cm -2 and limited only by the cell size and not by the cross-talk. This is slightly lower a number than one can get using the M6aM4 microstrip inductors, for which the AQFP number density is limited by the cross-talk; see the lowest curve labeled 24b in Fig. 4.

If using a kinetic inductor, we could reduce the length of the inductor L q to l q = S min = 1.34 µ m, the maximum number density would increase dramatically to n QFP ≈ 1.8 · 10 7 cm -2 , as shown in Fig. 10, whereas the in-row and betweenrows cross-talk would remain below 5%. In the next section, we will consider the fabrication process required to achieve this.

<!-- image -->

Fig. 9. Parameters of Φ 0 -exitation transformers using M6aM4bM7 striplines spaced at s = 250 nm in the SFQ5ee process with parameters: d 1 = 615 nm, H = 1015 nm, λ = 90 nm, and t M 4 = t M 6 = t M 7 = 200 nm. Inset: cross-section of the M6-M6aM4bM7 transformers. Solid red curve is the mutual coupling length l m in (1) of the striplines required to induce Φ 0 in the transformer secondary at the maximum possible current density in Nb of the transformer primary as a function of the striplines' linewidth. The uppermost solid blue curve is the length 2 l L of the transformer secondary, using (3) at β L = 0 . 2 , I cJ = 50 µ A. The magenta dot curve is self-inductance of the M6aM4bM7 striplines per unit length, L l , the scale is on the right axis; the bottom black dash curve is mutual inductance M l per unit length between the striplines at s = 250 nm; and the scale is on the right axis. The blue dash-dot curve is l q /10 from (15), which is equal 0.4 l L , assuming that inductor L q is a M6aM4bM7 stripline of the same linewidth as in the excitation transformer. The short dash black curve is l out/100 calculated using (17b) and M q = M l , assuming that inductor L out is also a M6aM4bM7 stripline spaced from the L q at 250 nm. Below w min ≈ 105 nm, the primary current inducing the Φ 0 excitation at the coupling length l m = 2 l L exceeds 5.25 mA, the I max of Nb wires. The assumed maximum excitation current density in the primary stripline is 0.25 A/ µ m 2 .

Fig. 10. Number density of AQFPs using striplines M6aM4bM7 spaced at s = 250 nm in all transformers as a function of striplines' linewidth. The bottom solid and dash black curves are for AQFPs using Nb striplines on the layer M6 in the SFQ5ee process with M4 and M7 ground planes at H = 1015 nm; below w min = 105 nm, the linewidth of only inductor L q , w q , can be reduced to increase the AQFP density, as shown by the black dash curve. The top dash-dot blue curve is for a hypothetical process using Nb striplines in the ac excitation transformer L 1 , L 2 , and a kinetic inductor L q , placed on the level of M6, with length equal to the 5% cross-talk length S min = 1.34 µ mat w = w min = 105 nm.

<!-- image -->

Fig. 11. Cross-coupling between stripline transformers as a function of spacing S between them: (·)-transformers formed by two striplines M6aM4bM7 spaced at s = 250 in the SFQ5ee process using M4 and M7 ground planes at H = 1015 nm, w = w min = 105 nm; ( /squaresolid )-transformers formed by two striplines M6aM4bM8 spaced at s = 250 nm in the SFQ7ee process using M4 andM8groundplanesat H = 1415nm, w = w min = 80nm,( )-transformers formed by a stripline M7aM4bM8 (dielectric thickness between M4 and M7 d 2 = 1015 nm, the SFQ7ee process) aligned over a stripline M6aM4bM8; width of both striplines w = w min = 95 nm; red short dash is for the same striplines but with w = 200 nm. All the shown curves were calculated using (31), points are numerical simulation using wxLC [41]. In all the cases, we used λ = 90 nm, and thicknesses of the Nb layers t M 4 = t M 6 = t M 7 = t M 8 = 200 nm.

<!-- image -->

## V. ADVANCED FABRICATION PROCESS SFQ7EE FOR SUPERCONDUCTOR LOGIC/MEMORY USING AC EXCITATION

## A. Nb Stripline Transformers in the SFQ7ee Optimized Process

In order to utilize the advantages of a very low cross-talk between stripline transformers, small S min, and substantially increase the number density of logic cells using flux transformers and ac excitation, we need to engineer an optimized fabrication process. From (31), the mutual inductance is maximized by decreasing the vertical distance between the signal wires h 2 -h 1 and placing them such that h 2 + h 1 = H , i.e., symmetrically in the middle between the ground planes at around H/ 2 . These conditions could be nearly satisfied if we add a niobium layer M8 above the layer M7 in the SFQ5ee process. This would allow us to use M6aM4bM8 striplines in planar transformers and M7aM4bM8 striplines in vertical transformers. If we use 200 nm interlayer dielectric I7 (between M7 and M8), the distance between the ground planes M4 and M8 would become H = 1415 nm, giving the decay length p 0 = 508 nm. The corresponding fabrication process, titled SFQ7ee, is currently under development at MIT LL. Its cross-section is shown in Fig. 12.

Self- and mutual-inductances of Nb striplines M6aM4bM8 and M7aM4bM8 in the SFQ7ee process are shown in Fig. 13(a). Results of the analysis of transformers in the SFQ7ee process is shown in Fig. 13(b). For the planar M6-M6aM4bM8 excitation transformers in AQFPs, we get w min ≈ 80 nm at spacing between

Fig. 12. Cross-section of an advanced process node SFQ7ee with 10 superconducting layers: layers M0-M4 and M7-M8 are Nb layers with 200 nm thickness; M5 is Nb layer, junction base electrode, with 150 nm thickness; M6 is NbN/Nb bilayer with 200 nm thickness; R5 is Mo or MoN x resistor layer, 40 nm thickness; L0 is Mo 2 N kinetic inductor, 40 nm thickness; Pad is Nb/Pt/Au contact pad metallization; I0-I4, I6, and I7 are vias in SiO 2 interlayer dielectric with 200 nm thickness; I5 via is in 280 nm thick dielectric. In comparison to the standard SFQ5ee node, SFQ7ee has an additional Nb layer M8. The layer M6 can be deposited either as a 200-nm Nb layer or as a NbN/Nb bilayer, e.g., with equal 100/100 nm thicknesses. In the latter case, 100-nm thick NbN kinetic inductors can be formed by selectively etching the top Nb layer of the bilayer, while the full bilayer can be used to form regular, low-value, geometrical inductors, as well as ac power and data transmission lines.

<!-- image -->

the M6 strips s = 250 nm and w min ≈ 55 nm in the hypothetical case of s = w . In the former case, at w = 80nm, l L = 1.52 µ m, l q ≈ 12 µ m, and a 5% cross-talk is reached at S min = 1.73 µ m; see Fig. 11. We note that S min slightly decreases with increasing the linewidth. Hence, we used the largest S min corresponding to the w min for the given type of the transformers.

If we use a stripline M7aM4bM8 as the transformer primary aligned over an equal-width stripline M6aM4bM8 secondary, the results are very similar: w min ≈ 95 nm; at w = 95 nm, l L = 1.58 µ m, l q ≈ 12.6 µ m, and a 5% cross-talk is reached at S min = 1.65 µ m. Hence, in the SFQ7ee process with Nb inductors, the number density of the AQFPs using stripline inductors is limited only by the lengths of the inductors, especially by the inductor L q , and given by (22a). It is shown in Fig. 14 by the bottom curves. In the practical range of the linewidth, w &gt; ∼ 80 nm, the AQFP number density is below 4 · 10 6 cm -2 .

## B. Thin-Film Kinetic Inductors

The only way to significantly increase n QFP, close to 18M per cm 2 , and utilize the advantages of striplines for lowering the cross-talk, is to reduce l q down to l q ∼ S min by using a kinetic inductor, as shown in Fig. 14 by the two top curves. To achieve this, the process layer stack would need a layer of kinetic inductors near the JJ layer, in addition to geometrical inductors and ac power transmission lines formed by Nb layers.

The first option for adding a layer of kinetic inductors near the JJ layer would be to replace the layer of resistors R5 in the SFQ5ee process stack if shunt resistors for JJs are not needed or can be moved below the layer of JJs as in the SC1 and SC2 processes [43], [11]. With this modification, the contact to the junctions' top electrode, J5, and to this kinetic inductor layer, K5, would be made by the layer M6 through vias, respectively, C5J and C5K, where label C5K would replace C5R in the existing SFQ5ee process. In case the shunt resistors are needed, they can

<!-- image -->

(a)

Fig. 13. (a) Self- and mutual-inductance per unit length of niobium stripline inductors in the SFQ7ee process nodes with 10 superconducting layers and parameters: H = 1415 nm (dielectric thickness between M4 and M8 ground planes); d 1 = 615 nm, dielectric thickness between M4 and M6; and d 2 = 1015nm,dielectric thickness between M4 and M7. Thickness of all the Nb layers is 200 nm. Solid symbols ( /squaresolid ) and (·) show the mutual inductance extracted using wxLC [41], the solid curves are the analytical expression (31). (b) Lengths of stripline inductors in the AQFPs: top solid blue line-length 2 l L (3) of the AQFP cell inductors L 2 if made as M6aM4bM8 stripline; dash red curve-length l m (1) of the AQFP primary providing Φ 0 flux excitation if made as M7aM4bM8 stripline; solid red curves-length l m (1) of the ac transformer primary providing Φ 0 flux excitation if made as M6aM4bM8 stripline spaced at either 250 nm from the transformer secondary L 2 (top red curve) or at s = w (bottom red curve). Dash-dot blue curve is 0 . 1 l q (15), which equals 0.8 l L if inductor L q is the same M6aM4bM7 stripline as the L 2 . Short black dash and blue dot curves at the bottom are 0 . 01 l out (17b); l out is the maximum length of the output inductor L out if it is made as M7aM4bM8 stripline (blue dot) or as M6aM4bM8 stripline spaced from L q at s = 250 nm (black short dash).

<!-- image -->

be moved into the position R4 below the layer M5, as in the SC1 process [43].

Since this K5 layer would replace a thin layer of resistors in the R5position, only a thin film with similar thickness could be used, e.g., a 40-nm Mo 2 N film used in the SFQ5ee process for bias inductors on the L0 layer. It has the sheet inductance of 8 pH/sq [36]. Another option would be a thin, 40 to 50 nm, NbN film

Fig. 14. Number density of AQFPs in the SFQ7ee process using Nb striplines M6aM4bM8andM7aM4bM8inthetransformers (the bottom curves) and using a kinetic inductor for L q (the top two curves), χ = 1. Solid and dash-dot blue curves at the bottom correspond to all inductors made as M6aM4bM8 striplines spaced at s = 250 nm; below w min = 80 nm only the width of the inductor L q canbereducedtodecreaseitslengthandincreasethenumberdensity.Thebottom red dash curve corresponds to the excitation transformer primary L 1 made as M7aM4bM8 stripline aligned over the equal-width secondary M6aM4bM8; below w min = 95 nm only the width of the inductor L q can be reduced to decrease its length l q and increase the number density. The top red short dash curve corresponds to the ac excitation transformers with M7aM4bM8 primary, having lower cross-talk ( S min = 1.65 µ mat w = w min) than if the primary is a M6aM4bM8 stripline spaced at s = 250 nm from the secondary ( S min = 1.73 µ m at w = w min). Both top curves assume that the length of the inductor L q is adjusted to the value of S min shown, the 5% cross-talk spacing, by using a kinetic inductor with the required sheet inductance.

<!-- image -->

with a similar sheet inductance [44]. Using these high kinetic inductance materials would result in very short inductors having very small mutual coupling to other inductors. For instance, at w q = 0.25 µ m, this would give l q ≈ 0.33 µ m, which is too short a length to provide sufficient coupling to the output inductor L out. Indeed, the strongest coupling to a K5 trace located at d 1 = 505 nm ( h 1 = 525 nm) is achieved if the L out trace is on the neighboring layer M6 at d 1 = 615 nm ( h 1 = 715 nm). Then, using (31) or numerical simulations, we get the linear mutual inductance M ql ≈ 0.32 pH/ µ mand the total mutual inductance M q = M ql l q ≈ 0.1 pH. According to (17b), this small mutual inductance would allow to transfer the output data only over distances below about 2 µ m.

Hence, for transferring the output data to larger distances, we need to use smaller sheet inductances in the range from 1.5 to 1.75 pH/sq determined by the largest desired length l q ≈ S min. Increasing thickness of the K5 layer significantly for achieving lower inductance is not desirable because this would require a full planarization of the K5 layer and increase the total dielectric thickness between the layers M5 and M6. The latter would make filling in of etched I5 vias by Nb of the M6 layer more difficult and reduce the via critical current. Therefore, we think that this approach is not practical and consider below another option.

## C. NbN/Nb Bilayer of Kinetic/Geometric Inductors

The second option is to implement bilayer inductors-instead of the current 200-nm Nb layer M6 deposit a 200-nm NbN/Nb

Fig. 15. Processing an in-situ deposited NbN/Nb bilayer, layer M6, to form kinetic inductors and geometrical inductors on the layer contacting Josephson junctions, J5: (a) cross-section of the structure after the first photolithography; (b) after selective etching of the top Nb layer, using a very thin etch-stop layer between NbN and Nb layers of the bilayer; (c) top view of the second photolithography defining kinetic inductors; and (d) final top view of the patterned composite inductor after NbN etching and photoresist removal. This inductor consists of a geometrical inductance part formed by the full bilayer and the kinetic part formed by the patterned NbN.

<!-- image -->

bilayer. By pattering individual layers of this bilayer independently, as shown in Fig. 15, we can create inductors in a very wide range of inductance values while maintaining an appropriate level of mutual inductance between them as explained below.

Inductance of a bilayer, L bi can be calculated as a parallel connection of inductances of the individual layers L NbN and L Nb, assuming a sharp step-like change in the current density at the NbN/Nb interface

<!-- formula-not-decoded -->

where M NbN , Nb is the aiding mutual inductance between the NbN and Nb layers of the bilayer. Our measurements [44] show that magnetic field penetration depth (London penetration depth) in reactively sputtered NbN films is approximately 490 nm, whereas it is 90 nm in the deposited Nb [11], [32]. Hence, in any practical range of the thicknesses of the individual layers, L NbN /greatermuch L Nb due to a much larger kinetic inductance of the NbN film, while geometrical inductances of both layers are nearly the same due to their close geometry and location. Also, L NbN /greatermuch M NbN , Nb because the mutual inductance is smaller than the geometrical inductance of each layer, and M NbN , Nb &lt; L Nb . As a result, inductance of the bilayer (per unit length) is completely determined by the inductance of the top Nb layer, L bi &lt; ∼ L Nb.

Adesired value L of an inductor with length l can be obtained by etching the top Nb layer from the bilayer over length l NbN.

Dependence of inductance of the equal thicknesses, 100/100 nm, Nb/NbN bilayer M6 (biM6) per unit length calculated using (32) as a function of the bilayer linewidth is shown in Fig. 16 for biM6aM4aM7 and biM6aM4bM8 striplines along with the inductance of the top Nb layer of the bilayer. In the entire range of the linewidths, the bilayer stripline inductance is only about 2% lower than of the stripline using just the 100 nm top Nb layer of the bilayer, Hence, for all practical calculations L bi ≈ L Nb.

Fig. 16. Inductance per unit length of NbN/Nb bilayer, L bi (thickness of the NbN and Nb layers is 100 nm) as layer M6 in striplines biM6aM4bM7 (solid black curve) and biM6aM4bM8 (blue dash curve) calculated using (32). Inset: cross-section of the bilayer striplines. Thicknesses of all layers correspond to the SFQ7ee process: t M 4 = t bi M 6 = t M 7 = t M 8 = 200 nm and dielectric thicknesses are given in the inset. Inductance of the 100-nm Nb strip of the bilayer, L Nb used in (32) is shown by open black and solid blue points. Mutual inductance per unit length between the layers of the bilayer, M NbN , Nb used in (32) is shown by the dash-dot curves for two dielectric thicknesses H between the ground planes, corresponding to the two types of the striplines. All self- and mutual-inductance values were extracted using wxLC software [41].

<!-- image -->

Neglecting inductance associated with electrical current redistribution between the bilayer and the bottom NbN layer near the ends of the etched Nb, the resultant inductance can be treated as a serial connection of the NbN (mostly kinetic) inductor and the full bilayer (mostly geometric) inductor, giving

<!-- formula-not-decoded -->

As was shown in [32], mutual inductance between two inductors with small cross-sections does not depend on their superconducting properties. Therefore, in the first approximation, mutual inductance between the partially etched bilayer and Nb stripline inductor on layer M7 can be represented as

<!-- formula-not-decoded -->

and between the partially etched bilayer and the bilayer strip M6 as

<!-- formula-not-decoded -->

where M NbN ,biM 6 and M NbN ,M 7 are mutual inductances per unit length between, respectively, a stripline in the bottom NbN layer of the bilayer and the parallel stripline in the full bilayer, and between the NbN stripline and Nb stripline inductor M7; M bi M 6 ,biM 6 and M bi M 6 ,M 7 are mutual inductances per unit length between, respectively, two striplines made of the bilayer, and between the bilayer stripline and the M7 stripline. All these mutual inductances can be easily calculated using (31) because they do not depend on superconducting properties of the signal strips [32].

Fig. 17. Parameters of the ac excitation transformer and the AQFP cell inductors using Nb striplines M7aM4bM8 as the transformer primary and NbN/Nb bilayer striplines biM6aM4bM8 as the transformer secondary and the inductor L q . Top Inset: cross-section of the stripline transformers using bilayers NbN/Nb (on the right side) and bilayers with etched Nb (on the left side). The assumed thicknesses of the NbN and Nb layers in the bilayer is 100 nm. Below w min = 118 nm, the excitation current in the transformer primary stripline needs to exceed the critical current of the Nb wire of 6 mA in order to induce a total flux of Φ 0 in the secondary. The short-dash magenta line shows the length l q of the inductor L q = 10.53 pH if the inductor would be made completely out of the 100-nm-thick NbN film of the bilayer. The dash-dot black line shows 0 . 1 l q if the full length of the inductor is made of the bilayer. The bottom solid black line shows the length of the etched off Nb of the bilayer, i.e., the length l NbN of the kinetic part of the bilayer inductor, see the bottom inset, required to make l q = 1.4 µ mso that l q + s = S min = 1.65 µ m, the 5% cross-talk length.

<!-- image -->

## D. AQFPs With NbN/Nb Bilayer of Kinetic/Geometric Inductors

Let us estimate dimensions of an AQFP using Nb stripline M7aM4bM8 for the ac excitation transformer primary, and NbN/Nb bilayer stripline biM6aM4bM8 for inductors L 2 (the secondary) and the output inductor L out, and a patterned bilayer for the inductor L q = 10.53 pH. Mutual inductance per unit length of the bilayer stripline and M7aM4bM8 stripline, M bi M 6 ,M 7 is the same as of Nb striplines M6aM4bM8 and M7aM4bM8 shown in Fig. 13(a) because they have the same locations and geometrical dimensions; see (31) and [32]. Therefore, dependence of the required mutual length on the linewidth, l m ( w ) in (1) is also the same as shown in Fig. 13(b) by the red dash curve. Using inductance per unit length of the 100/100 nm NbN/Nb bilayer, we calculate the total length of the excitation transformer secondary, 2 l L ( w ) shown in Fig. 17. The minimum linewidth of the primary determined from the condition l m ( w ) = 2 l L ( w ) is w min = 118 nm, the largest value in all the considered cases due to the smallest value of 2 l L which in turn is a result of a higher inductance of the biM6 layer than of the 200-nm Nb M6 layer in all the other cases. In the entire range of the linewidths, 2 l L + s /greatermuch S q = S min for the stripline transformers; see Fig. 11. So the cross-talk in the same row of AQFPs can be ignored.

The l q can be adjusted to any desired lengths between the shortest, L q /L NbN ( w ) , and the longest lengths, L q /L bi M 6 ( w ) ,

## AQFPsusingNbandNbN/Nbbilayerstriplineinductors

Fig. 18. Theoretical number density of AQFPs using NbN/Nb bilayer and Nb stripline inductors in the proposed advanced version of the SFQ7ee process; see text. For these AQFPs, the placement pitch in the x -direction, S x is set by the physical width of the AQFP cell 2 l L and the minimum spacing s used in the process, because it is larger than the cross-talk length S q = S min = 1.65 µ m. The y -direction placement pitch S y of the AQFP rows is set equal the 5% cross-talk spacing S min = 1.65 µ m. This sets the length l q of the AQFP inductor L q which is made by etching Nb off the NbN/Nb bilayer on length l NbN shown in Fig. 17.

<!-- image -->

as shown in Fig. 17, respectively, by short-dash magenta and dash-dot black lines; here L NbN ( w ) and L bi M 6 ( w ) are widthdependent linear inductances of, respectively, the NbN layer and of the NbN/Nbbilayer. This l q adjustment can be done by etching the top Nb layer of the bilayer on its full length or only on a part l NbN of it; see the bottom Inset in Fig. 17. To minimize cross-talk between the adjacent rows of AQFPs, we need l q + s ≤ S min. For the vertical stripline transformers, S min weakly depends on w and S min = 1.65 µ m at a practical minimum width of the bilayer inductors w = 100 nm; see Fig. 11, blue dash-dot and red short dash curves.

TherequiredNbetchlengthtogetthecompositeinductorwith L q = 10.53 pH and l q = 1.40 µ m (at s = 250 nm), i.e., the length of the kinetic part l NbN is shown in Fig. 17. This etch length is certainly within the capabilities of the existing SCE fabrication technology. Making shorter l q by etching a larger length of Nb off the bilayer strip is certainly possible. This would decrease the cell size but increase the cross-talk and also decrease the data output length l out. In practice, the actual length will be a design-dependent and adjustable parameter.

Fig. 18 shows the theoretical number density (29a) and (29b) of the AQFPs using the proposed fabrication process with the bilayer inductors. As can be seen, densities above 22M cm -2 , corresponding to over 7M MAJ3 gates per cm 2 , can be reached at very modest linewidths of all the inductors, which are fully within capabilities of the existing fabrication technology. This is the main result of this section.

## VI. DISCUSSION

We have considered two main factors limiting the integration scale-device number density-of superconductor integrated circuits using ac power for logic and/or memory cell excitation and clocking: critical current of superconducting transformers and their cross-coupling. We used parameters of the fabrication processes developed at MIT LL and parameters of the AQFP cells as an example for detailed numerical simulations. Below we discuss how our general conclusions depend on the selected fabrication process, the typical critical current of the cell JJs I cJ , the type of superconductor logic, and so on.

From (14), the minimum cross-sectional area and the minimum linewidth of ac power delivery transmission lines are directly proportional to, respectively, I cJ /β L and ( I cJ /β L ) 1 / 2 regardless of the cell type. In this respect, cells using smaller critical currents and larger β L than the considered AQFP cells, e.g., RQL cells, allow for smaller w min than in the AQFP cells. However, the cell area is proportional to the β L . So logic types using larger β L values, larger than 1.6 in AQFPs, e.g., RQL [25], [26], [27], would in general have lower densities than the densities estimated in Sections III-V for the AQFP cells.

The wave impedance of superconducting striplines Z 0 = ( L l /C l ) 1 / 2 grows rapidly with decreasing the linewidth due to the growing kinetic inductance and diminishing capacitance, and becomes larger than 50 Ω at w &lt; ∼ 250 nm, see Fig. 4 in [11], where C l is capacitance per unit length. We assumed that impedancematchingtotheacpowersourcecanbedoneoff-chip, whereas the standard design practice is to use a fixed-width 50 Ω transmission lines on the chips. The latter only decreases circuit density compared to the given estimates.

Increasing I cJ increases the circuit density until the maximum density is reached at some I opt cJ at which the area occupied by the circuit JJs is approximately equal to the area occupied by the circuit inductors. At I cJ &gt; I opt cJ the density decreases. The I opt cJ weakly increases with increasing the process Josephson critical current density. However, increasing I cJ proportionally increases power dissipation in the circuit junctions and also increases ac power loss caused by dielectric losses in the transmission lines, which grows as I 2 cJ because the ac excitation current grows proportionally to I cJ . As a result, selection of I cJ is made based on the total energy dissipation requirements for the circuit and on the tolerable level of the circuit BER, not on the circuit density optimization.

Since magnetic inductance and mutual inductance of the microstrip and stripline inductors depends logarithmically on the linewidth, signal trace thickness, and dielectric thickness, our main results weakly depend on the exact parameters of the fabrication process selected for the analysis. Moreover, the main parameters of different fabrication processes are very similar to the MIT LL processes considered; see, e.g., [45].

## A. Scaling Problems With AC Power Distribution and AC Power Dissipation

Yet another problem impeding scaling up ac-powered superconductor digital circuits is delivery of multiphase ac power and associated on-chip power losses. To illustrate severity of this problem, let us estimate ac power requirements and dielectric losses in a large-scale integrated circuit containing, say, N = 10 7 AQFP cells. Let us use a conservative linewidth of the ac

transformer primary stripline M7aM4bM8 of 200 nm in the most advanced SFQ7ee process which, at this linewidth, could provide AQFP density of 1.6 · 10 7 cm -2 at below 5% cross-talk; see Fig. 18. The length of the AQFP cell along the ac power transmission line is 2 l L = 2.8 µ m; see Fig. 17. The total length of the ac power transmission lines required to deliver ac power to all the AQFP cells is l ac = (2 l L + s ) N = 30 m. This is 150 times larger than the ac wavelength, λ clk ≈ 20 cm at the typical clock frequency, f cl, of 5 GHz.

Delivery of the, typically four-phase, ac excitation/clock current from one or multiple sources as a traveling wave is not possible because different AQFPs along the transmission lines will be experiencing different phases due to propagation delays. The only option is to create a power distribution tree, a power grid, with all branches much shorter than λ clk / 10 ≈ 2 cm which, hopefully, can work as lamped elements maintaining the same ac phase along the branch and the required phase difference between the different branches. The number of the branches and the required ac power splitters is equal to the number of AQFP rows, or l ac /a , where a is the row length; at a = 1 cm, this number is 3000.

At w = 200 nm, stripline M7aM4bM8 has Z 0 = 62.5 Ω and C l = 168.1 pF/m, based on the relative dielectric constant ε = 4.6 for the SiO 2 interlayer dielectric in our fabrication processes [46] and capacitance extraction software [41]. The total capacitance of the power grid is C = C l l ac = 5.04 nF. The ac current amplitude in the AQFP primary under consideration, I ac, creating a Φ 0 / 2 peak excitation in the AQFP secondary wire is about 2.13 mA. Hence, the ac peak voltage on each branch of the power tree is V ac = I ac Z 0 ≈ 0.133 V. Since each branch needs 2.13 mA peak current, the total peak current I tot in the tree trunk is 3000 × 2.13 mA ≈ 6.4 A. Hence, the total ac power required to be delivered to and taken away from the chip should be P = 1 2 I tot V ac = 0.43 W.

The peak energy stored in the grid is E = CV 2 ac / 2 = 4.46 · 10 -11 J. The ac power loss due to dielectric losses in the grid capacitor C is P loss = 2 πEf clc tan δ ≈ 2.1 mW, where the dielectric loss tangent for our low-temperature deposited SiO 2 is tan δ ≈ 1.5 · 10 -3 [46]. At the same time, dynamic power consumption due to adiabatic switching of the AQFP cells is P d = NE sw f clk = 50 nW, based on the AQFP switching energy of 1 · 10 -21 J [22], [34], [47]. So the parasitic dissipation in the power grid is 42 times larger than the useful power dissipation related to the AQFP operation. As a result, the real AQFP circuits have much lower, about 42 times lower, energy efficiency than what is typically claimed [47] based solely on the switching energy consideration.

On-chip power dissipation of 2.1 mW at 4 K is equivalent to 2.1 W power consumption at room temperature because the cryocooling penalty is about 1000 W per W [15]. This total power consumption by a 10-million-devices, 3.3 million gates, chip is comparable to or even larger than the power consumption by CMOS chips with similar complexity.

## VII. CONCLUSION

For each type of superconducting transformers, there is a minimum cross-sectional area A min ∼ 1.5 · 10 -2 µ m 2 and the corresponding minimum linewidth w min ∼ 0.1 µ m of the ac power transmission line, the transformer primary, below which the superconducting current providing flux excitation required for the cell operation exceeds the critical current of the wire. This critical current as well as the mutual inductance set the minimum mutual coupling length between the transformer primary and secondary and hence the minimum size of the logic or memory cells in the x -direction, along the ac power line. On the other hand, reduction of the linewidth of the transformer secondary L 2 increases its kinetic inductance and, hence, decreases its length since the total inductance is set by the cell design parameter β L . This length reduction decreases the mutual coupling in the transformer and prevents transformer miniaturization.

Mutual coupling (cross-talk) between adjacent transformers is strong and long-ranged if transformers use microstrip inductors. This presents a serious problem and limits the scale of integration. Cross-talk diminishes exponentially with spacing between the transformers if stripline inductors are used instead of microstrips. However, mutual coupling of striplines is much weaker than of the microstrip, which increases the size of the stripline-based transformers.

Using parameters of AQFP cells as a typical example, we have estimated the maximum number density of AQFP circuits for all types of microstrip and stripline inductors which can be formed near the JJs in fully planarized fabrication processes for superconductor electronics developed at MIT Lincoln Laboratory. We have shown that, at the SFQ5ee process minimum linewidth and spacing w = s = 250 nm, the theoretical AQFP number density is about 1M per cm 2 . Reduction of Nb linewidth to about 60 nm in the future processes may increase the AQFP number density to a few million per cm 2 .

We have shown that the circuit density can be substantially increased by using kinetic inductors, e.g., patterned NbN films instead of Nb, mainly geometrical, inductors. Since short strips of kinetic inductors have very small mutual coupling, we have proposed to use bilayer inductors, e.g., NbN/Nb bilayers consisting of a layer of kinetic inductor (material with large λ ) covered by a layer of geometrical inductor (material with small λ , niobium). Partial patterning of the top Nb layer of the bilayer enables making kinetic inductors with a wide range of inductance values from the patterned bottom layer, whereas using the full bilayer allows for making small-value inductors and preserves sufficient mutual coupling.

Additional design flexibility is provided by selecting thicknesses of the individual layers in the bilayer. As an example, we have considered a 100/100 nm NbN/Nb bilayer as the layer M6 in a future fabrication process node SFQ7ee having nine superconducting layers, three of which are above the layer of JJs. We have calculated parameters of the transformers and dimensions of the AQFP cells using Nb striplines M7aM4bM8 for ac power delivery and striplines biM6aM4bM8 with patterned Nb of the bilayer for the AQFP cell inductors. We have found that the proposed advanced fabrication process with bilayer inductors allows for the highest AQFP number density among all the considered processes and options, reaching above 22M AQFPs per cm 2 , corresponding to about 7M MAJ3 logic gates per cm 2 , at modest linewidths w &gt; ∼ 120 nm, which are within the

capabilities of the fabrication equipment and existing fabrication processes for superconductor electronics.

The current status of the SFQ7ee process and NbN/Nb bilayer inductors will be published elsewhere [48].

Although all the calculations were done for the typical parameters of AQFP cells, the same conclusions and scaling estimates, withsmallmodifications, are applicable to all other circuits using ac power and/or transformers such as RQL, nSQUID circuits [4], ac-biased SFQ circuits with ac/dc converters [49], and circuits with SFQ biasing [50], and likely to neuromorphic bioSFQ circuits [51] using flux transformers in artificial superconducting neurons.

The proposed bilayer inductors could benefit miniaturization of all superconductor digital circuits, especially those using small values of I cJ and correspondingly large values of cell inductors.

Energy efficiency of adiabatic and nonadiabatic ac-powered superconductor digital circuits is limited by dielectric losses in the ac power transmission lines. Superconductor ac-powered circuits can be made overall significantly lower power consuming than CMOS circuits only if we either implement interlayer dielectrics with loss tangent tan δ ∼ 10 -5 , which requires development of a new fabrication technology, or significantly reduce the ac excitation/clock frequency, to about 0.1 GHz, or both.

The estimated maximum cell number density of ac-powered circuits of about 2 · 10 7 cm -2 should be considered as the upper limit to the achievable scale of integration of superconductor electronics utilizing inductively coupled ac excitation and clocking.

Capacitive coupling of RQL cells to the power grid, instead of inductive coupling, was patented a few years ago [52], despite that capacitors have been used in ac power distribution circuits during at least the last 150 years and that most of the superconducting qubit circuits have been using capacitive coupling to the ac transmission lines for the last 20 years. It has not been demonstrated for RQL and AQFP cells. Scaling limitations of this approach require a separate discussion.

Aseparate discussion is also required of potential applications of superconductor ac-clocked logics and memories for which the scale of integration and performance estimated in Sections IIIVI would be sufficient. For instance, whether it is sufficient for applications in general purpose or high-performance computing, data centers, artificial neural networks and neuromorphic processors, cold processors for quantum computers, cold processors for large arrays of cold sensors, etc.

## ACKNOWLEDGMENT

I am grateful to Vasili Semenov and Timur Filippov for many interesting discussions of scalability of superconductor electronics, to Vladimir Bolkhovsky for the numerous discussions of NbN films and bilayer inductors, and to Mark Gouker and Leonard Johnson for their interest in this article. Any opinions, findings, conclusions, or recommendations expressed in this material are those of the author and do not necessarily reflect the views of the Under Secretary of Defense for Research and Engineering or the U.S. Government. Notwithstanding any copyright notice, U.S. Government rights in this article are defined by DFARS 252.227-7013 or DFARS 252.227-7014 as detailed above. Use of this article other than as specifically authorized by the U.S. Government may violate any copyrights that exist in this article. The U.S. Government is authorized to reproduce and distribute reprints for Governmental purposes notwithstanding any copyright annotation thereon.

## REFERENCES

- [1] K. K. Likharev and V. K. Semenov, 'RSFQ logic/memory family: A new Josephson-junction technology for sub-terahertz-clock-frequency digital systems,' IEEETrans.Appl. Supercond. , vol. 1, no. 1, pp. 3-28, Mar. 1991.
- [2] W. Chen, A. V. Rylyakov, V. Patel, J. E. Lukens, and K. K. Likharev, 'Superconducting digital frequency dividers operating up to 750 GHz,' Appl. Phys. Lett. , vol. 73, pp. 2817-2819, Nov. 1998.
- [3] K. Likharev, 'Dynamics of some single flux quantum devices: I Parametric quantron,' IEEE Trans. Mag. , vol. 13, no. 1, pp. 242-244, Jan. 1977.
- [4] V. K. Semenov, G. V. Danilov, and D. V. Averin, 'Negative-inductance SQUID as the basic element of reversible Josephson-junction circuits,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 938-943, Jun. 2003.
- [5] J. Ren and V. K. Semenov, 'Progress with physically and logically reversible superconducting digital circuits,' IEEE Trans. Appl. Supercond. , vol. 21, no. 3, pp. 780-786, Jun. 2011.
- [6] N. Takeuchi, Y. Yamanashi, and N. Yoshikawa, 'Measurements of 10 zJ energy dissipation of adiabatic quantum-flux-parametron logic using a superconducting resonator,' Appl. Phys. Lett. , vol. 102, Feb. 2013, Art. no. 052602.
- [7] V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, 'AC-biased shift registers as fabrication process benchmark circuits and flux trapping diagnostic tool,' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, Jun. 2017, Art. no. 1301409.
- [8] 5000-qubit Advantage chip , D-Wave Systems, Inc , 2020. [Online]. Available: https://www.dwavesys.com/solutions-and-products/systems/
- [9] Transistor count , Dec. 20, 2020. [Online]. Available: https://en.wikipedia. org/wiki/Transistor\_count
- [10] S. K. Tolpygo et al., 'A 150-nm process node of an eight-Nb-layer fully planarized process for superconductor electronics,' IEEE CSC &amp; ESAS Superconductivity News Forum (global edition), no. 49, Mar. 2021. Invited presentation Wk1EOr3B-01 at Appl. Supercond. Conf., ASC 2020, Oct. 2020. [Online]. Available: https://snf.ieeecsc.org/sites/ieeecsc.org/files/documents/snf/abstracts/ STP669%20Tolpygo%20invited%20pres.pdf
- [11] S. K. Tolpygo, E. B. Golden, T. J. Weir, and V. Bolkhovsky, 'Inductance of superconductor integrated circuit features with sizes down to 120 nm,' Supercond. Sci. Technol. , vol. 34, Jun. 2021, Art. no. 085005, doi: 10.1088/1361-6668/ac04b9.
- [12] S. K. Tolpygo and V. K. Semenov, 'Increasing integration scale of superconductor electronics beyond one million Josephson junctions,' J. Phys.: Conf. Ser. , vol. 1559, 2020, Art. no. 012002.
- [13] V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, 'Very large scale integration of Josephson-junction-based superconductor random access memories,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1302809.
- [14] EMD4E001G-1Gb Spin-transfer Torque MRAM , Dec. 20, 2020. [Online]. Available: https://www.everspin.com/family/emd4e001g?npath=3557
- [15] S. K. Tolpygo, 'Superconductor electronics: Scalability and energy efficiency issues,' Low Temp. Phys. /Fizika Nizkikh Temp. , vol. 42, no. 5, pp. 463-485, May 2012, doi: 10.1063/1.4948618.
- [16] K. K. Likharev, G. M. Lapir, and V. K. Semenov, 'Properties of the superconducting loop closed with the Josephson junction with variable critical current,' Sov. Tech. Phys. Lett. , vol. 2, pp. 809-814, Sep. 1976.
- [17] K. K. Likharev, S. V. Rylov, and V. K. Semenov, 'Reversible coveyer computation in array of parametric quantrons,' IEEE Trans. Mag. , vol. 21, no. 2, pp. 947-950, Mar. 1985.
- [18] K. Loe and E. Goto, 'Analysis of flux input and output Josephson pair device,' IEEE Trans. Mag. , vol. 21, no. 2, pp. 884-887, Mar. 1985, doi: 10.1109/TMAG.1985.1063734.
- [19] E. Goto and K. F. Loe, DCFluxParametron.ANewApproachtoJosepshon Junction Logic . Singapore: World Scientific, 1986.
- [20] Y. Harada, H. Nakane, N. Miyamoto, U. Kawabe, E. Goto, and T. Soma, 'Basicoperationofquantumfluxparametron,' IEEETrans.Magn. , vol. 23, no. 5, pp. 3801-3807, Sep. 1987, doi: 10.1109/TMAG.1987.106557.

- [21] M.Hosoyaetal., 'Quantum flux parametron: A single quantum flux device for Josephson supercomputer,' IEEETrans.Appl.Supercond. , vol. 1, no. 2, pp. 77-89, Jun. 1991.
- [22] N. Takeuchi, D. Ozawa, Y. Tamanashi, and N. Yoshikawa, 'An adiabatic quantum flux parametron as an ultra-low-power logic device,' Supercond. Sci. Technol. , vol. 26, no. 3, Mar. 2013, Art. no. 035010.
- [23] K. Inoue, N. Takeuchi, K. Ehara, Y. Yamanashi, and N. Yoshikawa, 'Simulation and experimental demonstration of logic circuits using an ultra-low-power adiabatic quantum-flux-parametron,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Jun. 2013, Art. no. 1301105.
- [24] V. K. Semenov, G. V. Danilov, and D. V. Averin, 'Classical and quantum operation modes of the reversible Josephson-junction logic circuits,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 455-461, Jun. 2007.
- [25] Q. P. Herr, A. Y. Herr, O. T. Oberg, and A. G. Ioannidis, 'Ultralow-power superconducting logic,' J. Appl. Phys. , vol. 109, 2011, Art. no. 103903.
- [26] A. Y. Herr et al., 'An 8-bit carry look-ahead adder with 150 ps latency and submicrowatt power dissipation at 10 GHz,' J. Appl. Phys. , vol. 113, Jan. 2013, Art. no. 033911.
- [27] Q. P. Herr et al., 'Reproducible operating margins on a 72800-device digital superocnudcting chip,' Supercond. Sci. Technol. , vol. 28, Oct. 2015, Art. no. 124003.
- [28] L. Ginzburg and L. D. Landau, 'On the theory of superconductivity,' Zh. Eksp. Teor. Fiz. , vol. 20, pp. 1064-1082, 1950.
- [29] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, 'Theory of superconductivity,' Phys. Rev. , vol. 108, no. 5, pp. 1175-1204, Dec. 1957.
- [30] J. Bardeen, 'Critical fields and currents in superconductors,' Rev. Mod. Phys. , vol. 34, no. 4, pp. 667-681, Oct. 1962.
- [31] S. K. Tolpygo, V. Bolkhovsky, T. Weir, L. Johnson, W. D. Oliver, and M. A. Gouker, 'Deep sub-micron stud-via technology of superconductor VLSI circuits,' Supercond. Sci. Technol. , vol. 27, Jan. 2014, Art. no. 025016, doi: 10.1088/0953-2048/27/2/025016.
- [32] S. K. Tolpygo, E. B. Golden, T. J. Weir, and V. Bolkhovsky, 'Mutual and self-inductance in planarized multilayered superconductor integrated circuits: Microstrips, striplines, bends, meanders, ground plane perforations,' IEEETrans. Appl. Supercond. , vol. 32, no. 5, Aug. 2022, Art. no. 1400331, doi: 10.1109/TASC.2022.3162758.
- [33] N. Takeuchi et al., 'Adiabatic quantum-flux-parametron cell library designed using a 10 kA cm -2 niobium fabrication process,' Supercond. Sci. Technol. , vol. 30, Jan. 2017, Art. no. 035002.
- [34] N. Takeuchi, K. Ehara, K. Inoue, Y. Yamanashi, and N. Yoshikawa, 'Margin and energy dissipation of adiabatic quantum-flux-parametron logic at finite temperature,' IEEE Trans. Appl. Supercond. , vol. 23, no. 3, Jun. 2013, Art. no. 1700304, doi: 10.1109/TASC.2012. 2232336.
- [35] S. K. Tolpygo et al., 'Advanced fabrication processes for superconducting very large scale integrated circuits,' IEEETrans. Appl. Supercond. , vol. 26, no. 3, Apr. 2016, Art. no. 1100110.
- [36] S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, L. M. Johnson, M. A. Gouker, and W. D. Oliver, 'Fabrication process and properties of fully planarized deep-submicron Nb/Al-AlO x -Nb Josephson junctions for VLSI circuits,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1101312, doi: 10.1109/TASC.2014.2374836.
- [37] S. K. Tolpygo et al., 'Properties of unshunted and resistively shunted Nb/AlO x -Al/Nb Josephson junctions with critical current densities from 0.1 to 1 mA/ µ m 2 ,' IEEETrans. Appl. Supercond. , vol. 27, no. 4, Jun. 2017, Art. no. 1100815, doi: 10.1109/TASC.2017.2667403.
- [38] S. K. Tolpygo et al., 'Superconductor electronics fabrication process with MoN x kinetic inductors and self-shunted Josephson junctions,' IEEE Trans. Appl. Supercond. , vol. 28, no. 4, Jun. 2018, Art. no. 1100212.
- [39] N. Takeuchi, Y. Yamanashi, and N. Yoshikawa, 'Adiabatic quantumflux-parametron cell library adopting minimalist design,' J. Appl. Phys. , vol. 117, May 2015, Art. no. 173912, doi: 10.1063/1.4919838.
- [40] N. Takeuchi, K. Arai, and N. Yoshikawa, 'Directly coupled adiabatic superconductor logic,' Supercond. Sci. Technol. , vol. 33, no. 6, May 2020, Art. no. 065002, doi: 10.1088/1361-6668/ab87ad.
- [41] M. M. Khapaev, 'Extraction of inductances of a multi-superconductor transmission line,' Supercond. Sci. Technol. , vol. 9, pp. 729-733, 1996.
- [42] D. E. Kirichenko, S. Sarwana, and A. F. Kirichenko, 'Zero static power dissipation biasing of RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 21, no. 3, pp. 776-779, Jun. 2011, doi: 10.1109/TASC.2010.2098432.
- [43] S. K. Tolpygo et al., 'Advanced fabrication processes for superconductor electronics: Current status and new developments,' IEEE Trans. Appl. Supercond. , vol. 29, no. 5, Aug. 2019, Art. no. 1102513, doi: 10.1109/TASC.2019.2904919.
- [44] S. K. Tolpygo, E. B. Golden, T. Weir, and V. Bolkhovsky, 'Self and mutual inductance of NbN and bilayer NbN/Nb inductors in planarized fabricaiton process with Nb ground planes,' 2022, arXiv:2210.10705 , submitted to IEEE Trans. Appl. Supercond., Applied Supercond. Conf. ASC 2022 presentation 1EPo2A-8.
- [45] S. Nagasawa et al., 'Nb 9-layer fabrication process for superconducting large-scale SFQ circuits and its process evaluation,' IEICE Trans. Electron. , vol. E97-C, no. 3, pp. 132-140, Mar. 2014.
- [46] D. E. Oates, S. K. Tolpygo, and V. Bolkhovsky, 'Submicron Nb microwave transmission lines and components for single-flux-quantum and analog large-scale superconducting integrated circuits,' IEEE Trans. Appl. Supercond. , vol. 27, no. 4, Jun. 2017, Art. no. 1501505, doi: 10.1109/TASC.2017.2649842.
- [47] O. Chen et al., 'Adiabatic quantum-flux-parametron: Towards building extremely energy-efficient circuits and systems,' Sci. Rep. , vol. 9, Jul. 2019, Art. no. 10514, doi: 10.1038/s41598-019-46595-w.
- [48] S. K. Tolpygo et al., 'Progress toward superconductor electronics fabrication process with planarized NbN and NbN/Nb layers,' IEEE Trans. Appl. Supercond. , 2022, ASC 2022 presentation 1EOr2C-01.
- [49] V. K. Semenov, Y. A. Polyakov, and S. K. Tolpygo, 'New AC-powered SFQ digital circuits,' IEEE Trans. Appl. Supercond. , vol. 25, no. 3, Jun. 2015, Art. no. 1301507, doi: 10.1109/TASC.2014.2382665.
- [50] V. K. Semenov, E. B. Golden, and S. K. Tolpygo, 'SFQ bias for SFQ digital circuits,' IEEE Trans. Appl. Supercond. , vol. 31, no. 5, Aug. 2021, Art. no. 1302207, doi: 10.1109/TASC.2021.3067231.
- [51] V. K. Semenov, E. B. Golden, and S. K. Tolpygo, 'A new family of bioSFQ logic/memory cells,' IEEETrans. Appl. Supercond. , vol. 32, no. 4, Jun. 2022, Art. no. 1400105, doi: 10.1109/TASC.2021.3138369.
- [52] A. Y. Herr, Q. P. Herr, and J. A. Strong, 'Capacitevely coupled superconducting integrated circuits powered using alternating current clock signals,' U.S. Patent 10, 608,044, Mar. 2020.