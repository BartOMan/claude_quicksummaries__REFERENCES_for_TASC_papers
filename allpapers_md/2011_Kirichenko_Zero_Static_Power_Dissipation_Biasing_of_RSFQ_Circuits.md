## Zero Static Power Dissipation Biasing of RSFQ Circuits

D. E. Kirichenko, S. Sarwana, and A. F. Kirichenko

AbstractWe present a novel, resistor-free approach to dc biasing of RSFQ circuits, known as Energy-efficient RSFQ (ERSFQ). This biasing scheme does not dissipate energy in the static (non-active) mode, and dissipates orders of magnitude less power than traditional RSFQ while operating. Using this approach, we have designed, fabricated and successfully tested at low and high speed a D flip-flop with complementary outputs and several static frequency dividers. We present the method, demonstrate experimental results, and discuss future implementations of ERSFQ.

Index TermsCryogenic, detector readout, low power, power efficient, RSFQ, SFQ, switching energy.

## I. INTRODUCTION

T HE problem of static power dissipation in RSFQ logic has been discussed since its invention in 1987 [1]. It was widely perceived at the time that solving this problem was not very urgent while demonstrating small-scale devices. Since then, a number of attempts to reduce the power dissipation in bias resistors in RSFQ circuits have been undertaken [3]-[5]. None of them were completely successful. A comprehensive review of these attempts was made in [2].

Meanwhile, with the maturity of RSFQ technology, getting rid of static and reducing total power dissipation has become a very important problem. Cryocooler-based RSFQ LSI systems require sharp reduction in power dissipation. In the emerging fields of digital detector readout and qu-bit control circuitry, static power dissipation is considered a 'deal breaker'. That is why many researchers have applied considerable efforts to solving this problem.

The first and the most practical idea was to reduce value of bias resistors and serially connecting them with large superconducting inductances. A moderate-size circuit was designed using this approach and successfully tested at low speed [3]. Unfortunately, an RSFQ circuit, biased with such scheme, can only operate at frequencies ., where is the voltage on the bias buss. f ≤ Vb

Fig. 1 shows a simple example that illustrates this approach. In a common RSFQ situation, one part of a circuit transmits SFQ pulses at frequency while another part does not. This creates a dc voltage drop between these two parts . fc △V 二 fc

Manuscript received August 02, 2010; accepted December 01, 2010. Date of publication January 13, 2011; date of current version May 27, 2011. Supported in part by the US DoD Contract W911NF-09-C-003.

The authors are with HYPRES, Inc., Elmsford, NY 10523, USA (e-mail: alex@hypres.com).

Color versions of one or more of the figures in this paper are available online at http://ieeexplore.ieee.org.

Digital Object Identifier 10.1109/TASC.2010.2098432

Fig. 1. The biasing scheme of RSFQ with reduced bias resistors and series inductors.

<!-- image -->

This voltage drop in turns creates a dc bias current redistribution, thus limiting circuit performance to low frequencies. In the more general case, a working RSFQ circuit creates dc voltage drops between its parts equal to or less than . This, in turn, leads to bias current redistribution causing circuit malfunction. Assuming that any part of an RSFQ circuit can withstand 10% of dc bias current deviation, we get the maximum operating frequency . Therefore, reducing the value of bias resistors reduces power dissipation and performance at the same time. 2 0.1

Replacing bias resistors with shunted Josephson junctions (as in [7]) does not solve the problem of bias current redistribution. In this case, when the number of idle junctions is much higher than the number of JJs transmitting SFQ pulses, the circuit will not properly function because of the same bias current redistribution. The only way to eliminate current redistribution is using a dc voltage source instead of a dc current source as the power supply. Then, different parts of the circuit do not influence each other through the power line.

A more radical approach to the problem is developing alternative logic families to RSFQ, e.g. [4], [5]. None of these ideas have been sufficiently practical and beneficial to become accepted. The recently suggested RQL logic [6] looks very attractive in terms of power dissipation, but requires multi-phase ac power. A multiphase powered circuit of reasonable complexity level usually has significant problems working at high frequency (say, above 10 GHz). This difficulty may be why there have been no published reports to date on an RQL circuit working at high frequency.

Fig. 2. The biasing scheme of ERSFQ.

<!-- image -->

## II. ERSFQ: ENERGY-EFFICIENT RSFQ

## A. General Idea

Replacing each bias resistor with a Josephson junction as a current distributing element seems to be a natural idea [7]. The Josephson junction's critical current is a natural current-limiting phenomenon. When a shunted Josephson junction is connected to a very small dc voltage source, the resulting dc component of the current through the junction is almost precisely equal . This allows us to use a non-hysteretic Josephson junction as a dc current distribution element (Fig. 2).

The necessary condition of such current distribution scheme is that the voltage on power line should be equal to or greater than the maximum possible dc voltage in the powered circuit. For all RSFQ circuits (with the exception of output amplifiers and some exotic SFQ pulse multipliers [8]), the maximum possible dc voltage is . In order to create such a voltage source, we use a Josephson transmission line (JTL) biased by common with the circuit power line through large superconductive inductors. We call it a 'feeding JTL', for its functionality is to serve as an additional supply of bias current. By applying SFQ pulses from the circuit's clock source to the feeding JTL, we create an exact dc voltage on the bias line. A mac 二

To prevent dynamic current redistribution and to increase the impedance of the local bias current source, large inductances were serially connected to the bias junctions, providing filtering of the ac components. The maximum bias current dynamic deviation in this case is . At , the current fluctuations do not exceed 5 . Lb

The circuit needs to be biased with the dc current value just under the total critical current of bias junctions. So, in the passive state (when the clock is not applied), an ERSFQ circuit does not dissipate any power at all (zero static power dissipation). After turning it on, i.e. applying a clock from the clock source, the total power dissipation of an ERSFQ circuit becomes , where is the total bias current for the circuit (from the dc current source) and is its operating clock frequency. This is orders of magnitude less than the amount of power dissipated in traditional RSFQ circuits. P Ib

Fig. 3. A layout fragment of an ERSFQ circuit.

<!-- image -->

Albeit the additional power dissipates in the voltage source (the feeding JTL), its value varies between zero and approximately a quarter of the total power dissipation in the ERSQ circuit. This value depends on the particular design of the circuit. In an RSFQ circuit, clock is transmitted via tree of clock JTLs. These JTLs as good voltage source for power buss as the feeding JTL. To our estimate, in an ERSFQ circuit, the total critical current of all clock JTLs, including the feeding JTL, should be in excess of 25% of the total dc bias current. Some ERSFQ circuits may not require a feeding JTL at all, maintaining dc bias voltage with their clock-distributing JTLs.

## B. ERSFQ Design and Layout

The major advantage of ERSFQ is its absolute compatibility with traditional RSFQ, meaning that any existing RSFQ circuit can be easily converted to ERSFQ by attaching a feeding JTL to the bias line and simple substitution of bias resistors with corresponding couples. The fragment of an ERSFQ circuit designed for the standard HYPRES 4.5 process [10] is shown in Fig. 3. Jb Lb

Onecan easily see large ( 400 pH) bias inductors consuming substantial space on a chip. Luckily, bias inductances are not restricted in value, so they can be moved to any place on a chip. Currently, we are working on 'moving' these inductances under the ground plane by adding an extra superconductor layer to the process. This layer may be made of a superconductor with a high kinetic inductance.

The other drawback of ERSFQ is its expectedly high time jitter due to unavoidable bias current fluctuation is . The obvious solution to that is increasing value of a bias inductor and generally employing pipeline architecture in designing large circuits. Lb

Fig. 4 shows a microphotograph of the fabricated ERSFQ circuit. In order to obtain large inductance, ground planes were removed from under the inductor.

## III. EXPERIMENTAL VERIFICATION OF ERSFQ

## A. Low-Frequency Functionality Test

We have designed and fabricated several chips [9] in order to benchmark ERSFQ technology. Fig. 5 shows one chips with logic cells designed in both (ERSFQ and RSFQ) standards. This was done to experimentally verify any differences in operational margins of the two technologies. The output amplifiers have a separate power bus and are designed in standard RSFQ for the obvious reason.

The chip contains two (ERSFQ and RSFQ) versions of a D flip-flop with complementary outputs [10] (see also Fig. 4) and

<!-- image -->

Fig. 4. Microphotograph of ERSFQ D flip-flop with complementary outputs.

Fig. 5. ERSFQ chip for low-frequency comparison test.

<!-- image -->

Fig. 6. ERSFQ DFFC gate low-speed test.

<!-- image -->

two versions of a static frequency divider by 16. For the sake of comparison, both versions of the cells were made using the same design template and look alike (the RSFQ version of each cell was made by replacing bias JJs with resistors in its ERSFQ counterpart). The chip also had an inductance test structure, which showed very good agreement with the designed value (0.4 nH). Lb

The functionality test results of a DFFC gate are shown in Fig. 6. The circuit operated within 22% bias current margins. The operating region includes the case when the total bias current exceeds the total critical current of bias junction, in which case there is static power dissipation.

<!-- image -->

Fig. 7. ERSFQ static frequency divider by 16 low-speed test.

<!-- image -->

Fig. 8. ERSFQ static frequency divider by .

<!-- image -->

/50

Fig. 9. Experiment on high-speed BER measurement of ERSFQ static frequency divider by .

<!-- image -->

/50 26% bias current margins. For some reason, the margins were even higher than those of its RSFQ counterpart.

## B. High-Frequency Test

To perform the high-speed test, we have chosen a static frequency divider by (Fig. 8). This circuit is an excellent test bench for ERSFQ high-speed functionality. 220

Each stage (out of total 20) of the frequency divider (TFF) operates at its own frequency, i.e. creating a different dc voltage drop. The correct operation of this circuit at high frequency should undoubtedly confirm the correctness of the ERSFQ bias scheme.

The correct operation of a static frequency divider is shown in Fig. 7. The ERSFQ version of the circuit was operating within While it is common in the RSFQ community to regard testing of a T flip-flop by its dc I-V curve [11] as substantiated proof Authorized licensed use limited to: Mayo Clinic Libraries. Downloaded on January 17,2024 at 17:04:58 UTC from IEEE Xplore.  Restrictions apply.

Fig. 10. Block diagram of ERSFQ detector digital readout.

<!-- image -->

of correct high-speed operation, phase-locked generation of serially connected dc SQUIDs may be confused with the correct operation of the TFF. A more valid experiment would be direct measurement of the bit-error rate (BER). The block diagram of this experiment is shown in Fig. 9.

In this experiment, we used two phase-locked frequency generators; one for the high-frequency clock and the other for the reference signal. The maximum frequency we can apply to the chip through our standard cryoprobe is about 30 GHz. We used an on-chip double-rate converter to double the clock frequency. So, the first stage of the frequency divider could operate at 60 GHz. Then, after dividing by factor of , the signal goes through the output amplifier to an oscilloscope, where it is compared with the reference signal.

The circuit worked correctly at up to 67 GHz of clock frequency within 16% dc bias current margins. This shows that it could have worked at much higher frequency, and 33 GHz is just a limit of our high-frequency setup.

At the nominal bias, we observed a 10-ns phase creep between the output and the reference signal during 9 hours. That gives us a BER estimate below .

## IV. ERSFQ IMPLEMENTATION

As the first implementation of ERSFQ, we are currently developing sensitive ADC for detector's digital readout (see Fig. 10).

The key idea is to keep the digital part of the ADC in the inactive state until receiving a signal from the detector. While in the inactive mode, the ADC does not affect the sensitivity of the detector connected to its input coil. And, upon detecting an event, it is instantly being switched to the operational mode by applying a clock signal from the external source with a simple ERSFQ NDRO element. We believe that this type of digital readout [12] will be extremely useful in the low-temperature detectors field.

## V. CONCLUSIONS

Wehavepresented a novel approach to biasing RSFQ circuits. It provides zero static and minimal total power dissipation. We have designed and successfully demonstrated three ERSFQ circuits at low frequency including D flip-flop with complementary outputs and two static frequency dividers. We also have demonstrated complete operation of a 20-stage static frequency divider at frequency up to 67 GHz within 16%operating margins. The measured bit-error rate was below . As an attractive implementation of this technology, we are developing a sensitive digital readout for low-temperature detectors.

## ACKNOWLEDGMENT

The authors thank D. Donnelly, R. Hunt, J. Vivalda, D. Yohannes, and S.K. Tolpygo for chip fabrication. We also thank O.A. Mukhanov, M. Manheimer and S. Holmes for fruitful discussions.

## REFERENCES

- [1] K. Likharev and V. Semenov, 'RSFQ logic/memory family: A new Josephson-junction technology for sub-terahertz clock-frequency digital systems,' IEEE Trans. Appl. Supercond. , vol. 1, pp. 3-28, Mar. 1991.
- [2] O. A. Mukhanov, 'Energy-efficient single flux quantum technology,' IEEE Trans. Appl. Supercond , this issue.
- [3] A. Rylyakov and K. Likharev, 'Pulse jitter and timing errors in RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 9, pp. 3539-3444, June 1999.
- [4] S. Polonsky, 'Delay insensitive RSFQ circuits with zero static power dissipation,' IEEE Trans. Appl. Supercond. , vol. 9, pp. 3535-3538, June 1999.
- [5] A. H. Silver and Q. P. Herr, 'A new concept for ultra-low power and ultra-high clock rate circuits,' IEEE Trans. Appl. Supercond. , vol. 11, pp. 333-336, June 2001.
- [6] Q. P. Herr, 'Single Flux Quantum Circuits,' US Patent 7,724,020, issued May 25, 2010.
- [7] L. Eaton and M. Johnson, 'Superconducting Constant Current Source,' US Patent 7,002,366, issued Feb. 21, 2006.
- [8] V. K. Semenov, 'Digital to analog conversion based on processing of the SFQ pulses,' IEEE Trans. Appl. Supercond. , vol. 3, pp. 2637-2640, Mar. 1993.
- [9] HYPRES Design Rules. [Online]. Available: http://www.hypres.com
- [10] A. F. Kirichenko, V. K. Semenov, Y. K. Kwong, and V. Nandakumar, '4-bit single flux quantum decoder,' IEEE Trans. Appl. Supercond. , vol. 5, no. 2, p. 2857, 1995.
- [11] W. Chen, A. V. Rylyakov, V. Patel, J. E. Lukens, and K. K. Likharev, 'Superconductor digital frequency divider operating up to 750 GHz,' Appl. Phys. Lett. , vol. 73, pp. 2817-2819, Nov. 1998.
- [12] A. Fujimaki, Y. Hogashi, S. Miyajima, and T. Kusumoto, 'Event-driven dual channel oversampled analog-to-digital converter for a detector system,' IEEE Trans. Appl. Supercond , submitted for publication.