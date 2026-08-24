## Serially Biased Components for Digital-RF Receiver

Timur V. Filippov, Anubhav Sahu, Saad Sarwana, Deepnarayan Gupta, and Vasili K. Semenov

AbstractReduction of total bias current using the serial biasing technique is required for RSFQ-based digital-RF receiver realization. This will have a major impact on reducing the size, weight and power consumption of the complete cryocooled receiver system. The approach is based on partitioning a homogeneous design into several isolated islands biased in series and transmitting SFQ pulses between islands, over moats through inductively-coupled driver-receiver-pairs (DRPs). Experimental data on testing of 100 DRPs connected in series are reported and bit-error-rate estimates are given. Our goal is to serially bias two sets of homogeneous circuit blocks in the digital-RF receiver design: (1) digital decimation filter (DDF) bit slices, and (2) output drivers. The correct operation of test chips containing four bit-slices of a second-order DDF, partitioned into 2 and 4 islands, are demonstrated. Results of 8 output drivers, serially biased on 2, 4, and 8 islands, are reported. Design issues of scaling to a digital-RF receiver, containing 18-20 DDF bit slices and 16 output drivers are discussed.

Index TermsADC, digital-RF receiver, RSFQ, serial biasing.

## I. INTRODUCTION

C ONVENTIONAL design of RSFQ integrated circuits requires parallel biasing of most Josephson junctions, leading to a large total bias current of order 1 A or more in complex circuits such as those for a digital-RF receiver [1]. Reduction of total bias current by serial biasing of circuit blocks facilitates realization of cryocooled superconductor electronic systems with large-scale digital circuitry. Bias current leads are among the primary contributors to a cryocooler's heat load, scaling proportionately with the total current in an optimum configuration [2]. Furthermore, magnetic fields induced by large currents affect operation of RSFQ circuits [3].

The concept of serial biasing (Fig. 1) has been well-known since the early days of RSFQ technology [4] with several groups demonstrating the principle of operation [5]-[7]. Our work is motivated by the development of digital-RF receivers (also called ADRs) [1], which in their simplest version draws 1.1 A of current [8]. The most complex part of this receiver, the decimation filter [9], is amenable to serial biasing since it consists of a homogenous array of identical circuit blocks. The high-voltage output driver circuit is another homogeneous structure drawing a large bias current. Serial biasing of the

Manuscript received August 16, 2008. This work was supported in part by Office of Naval Research Contract N00014-05-C-0097.

T. V. Filippov, A. Sahu, S. Sarwana and D. Gupta are with Hypres, Inc., Elmsford, NY 10523 USA (e-mail: tfil@hypres.com).

V. K. Semenov is with Physics &amp; Astronomy Department, State University of New York, Stony Brook, NY 11794 USA (e-mail: vasili.semenov@stonybrook. edu).

Digital Object Identifier 10.1109/TASC.2009.2018426

Fig. 1. Biasing of RSFQ circuits: parallel biasing (a) and serial biasing (b). The total amount of current required by traditional biasing is the bias current of a block /73 multiplied by the number of blocks n. For serial biasing the entire required bias current is equal to .

<!-- image -->

/73 two decimation filters and their output drivers, partitioned into blocks of 4-8, reduces the total bias current by 60-70%.

## II. DRIVER-RECEIVER PAIR

The simplified schematic of a driver-receiver pair (DRP) is shown in Fig. 2. The SFQ pulse propagates through the driver (junctions JD1-JD4) to introduce an SFQ pulse into the receiver formed by junctions JR1-JR2. The driver and receiver are separated by a moat and coupled to each other magnetically. Note that junctions JD3-JD4 reside on the same common ground as the rest of the driver by means of a superconductor base electrode 'tongue' spread over the moat.

In order to evaluate the performance of a large number of DRPs, which would be necessary for serially biased decimation filters and output drivers, a special chip with 100 DRPs was designed (Fig. 3) and fabricated using the standard dualHYPRES process [10] with and 4.5 . 三 1

We designed a chip (Fig. 3(b)) with 80 of 100 driver-receiver pairs transferring pulses between isolated, serially-biased islands. The rest of the drivers and receivers are connected to a global chip ground. For simplicity, we show a block diagram (Fig. 3(a)) with 12 driver-receiver pairs, 8 used to connect separate serially-biased islands, and the rest of the drivers and receivers connected to a global chip ground and biased in parallel. The DRPs are connected in series so that the driver (D) and the receiver (R) of the same pair belong to different islands separated by moats depicted by dashed lines. All isolated islands are biased in series. The driver and receiver of the same island are separated from each other by 2 segments of Josephson transmission line.

In this experiment, a stream of SFQ pulses from an external source is split into two paths: the first goes along the whole chain of 100 DRPs to be written into a NOT cell, the second reads out

Fig. 2. Driver-receiver pair (DRP) for serially biased circuits: simplified schematic (a) and layout (b). The schematic is drawn to help identification of junctions (darker circles) in the layout. The double dashed line in the schematic symbolizes a moat that separates two islands and makes junctions of driver (JD1-JD4) and receiver (JR1-JR2) connected to different grounds respectively.

<!-- image -->

the state of the NOT cell. Since the pulse train is periodic, there is no need to equalize the two delay paths. The NOT cell detects errors in propagation; in the case of correct operation, no output from the NOT cell is produced. The true, non-inverted output at the end of the chain was also monitored to control propagation of a pulse along the chain.

We observed no errors at a maximum clock rate of 3.2 GHz in 30 minutes of acquisition time through 80 serially biased DRPs. This gives a bit-error rate of . We estimate that 80 DRPs is a typical number required to serially bias lowpass analog-to-digital converter (LP ADC) being developed at HYPRES [1]. Therefore, we can expect an error-free (DRPs based) operating interval of at a clock frequency of 20 GHz. Note that the typical data acquisition time at present is about at the same frequency. 2 ×

Fig. 4 shows the BER measured as a function of bias voltage applied to the 80-DRP chain, top and bottom edges. The bias margin of the 80-DRP chain is 7%, whereas the margins of parallel-biased 10-DRP chains on the top and bottom edges are each 16%. Such narrowing of the bias margin may be attributed to a single weak link in the chain.

## III. SERIALLY BIASED OUTPUT DRIVERS

A set of four chips were designed to prove correct operation of serially biased output drivers, which are used in ADC or ADR chips [1] to facilitate interface with room-temperature electronics. Eight output drivers were partitioned into 2, 4 and 8 islands. The design on the 4th chip was biased using the traditional parallel scheme as a reference. An 8-bit binary counter with nondestructive read-out was used as a source of signal to be

Fig. 3. Simplified block diagram (a) and layout (b) of BER experiment based on 100 DRPs connected in series. Both inverted (NOT OUT) and direct (OUT) outputs are labeled. Dashed line in (b) illustrates propagation of applied pulse along chain of DRPs to be written into NOT cell and read out by next pulse applied through short (solid line) path.

<!-- image -->

Fig. 4. BER experiment at 500 MHz. Margin on serial-biased cells (solid line) is narrower than margins on parallel-biased cells along top and bottom edges (dashed lines of two types).

<!-- image -->

represented by the output drivers. Fig. 5 shows a typical output. One can see that the output frequency goes down from top to

Fig. 5. Outputs of serially biased output drivers. Only 6 bits are shown.

<!-- image -->

TABLE I BIAS CURRENT REQUIRED

| Numberof Islands   |   Current(mA) |
|--------------------|---------------|
| None               |         74.5  |
| 2                  |         38.45 |
| 4                  |         19.85 |
| 8                  |         10.75 |

bottom as the binary counter divides input frequency by 2 at each stage.

No degradation in the output drivers' performance (output amplitude, rising and falling times) was observed compared to the chip with parallel biasing. The required bias current scales properly with number of islands (see Table I). The value of current provided in the table was calculated as a middle point of zone of correct operation for different chips and does not scale exactly by factor of 2. Moreover, the number of DRPs per island varies from chip to chip and also influences the required current.

## IV. SERIALLY BIASED DIGITAL FILTER

We used our standard digital filter diagnostic test chip, comprising 4 identical slices of a second-order digital decimation filter [9], to prove the concept of serial biasing in the case of a relatively complex digital design. The homogeneous design of the digital filter was partitioned into 2 islands (2 slices per island) as shown in Fig. 6. The islands were separated from the global chip ground by a set of moats, all biases were combined and 20 DRPs were used to distribute pulses to, from and between islands.

For testing we used an approach based on continual comparison of experimental data with the predictions of a computer logical simulator that includes mathematical description of all cells and their responses to data and clock pulses (see [9] for a detailed description). So we were able to compare any measured response at output terminals with the simulator prediction at

Fig. 6. Layout of serially-biased digital decimation filter. Four slices are placed into 2 islands and separated from global chip ground by set of moats.

<!-- image -->

Fig. 7. Test results of serially-biased digital decimation filter of 2nd order.

<!-- image -->

the end of each clock period using the automated Octopux test system [11].

The correct operation of 4 slices partitioned into 2 islands is illustrated in Fig. 7. The Data and Nyquist clock (NC) pulses are applied during each master clock (MC) period. As a result the upper integrator formed by T-flip-flops with non-destructive read-out (TN) counts input data from 0 to 15 and then produces a carry output (CRN). The lower integrator formed by T-flip-flops with destructive read-out (TD) produces a carry pulse CRD almost always because the Nyquist clock applied during each clock period resets it and any number provided by the upper integrator produces the carry pulse. The outputs OUT1-4 show correct operation of the binary counter formed by the upper integrator.

Typically, five independent current biases are used in our regular decimation filter design. As expected, the total current for 4 slices required in the traditional biasing scheme was reduced by a factor of 2 by partitioning the design into 2 islands and combining all bias currents together. However to improve flexibility and enhance operating margins we also designed a version of the test chip where the top and the bottom integrators were placed on different islands. This case required additional DRPs to provide pulse exchange between the top and the bottom islands. Note that the addition of DRPs does not ruin the timing scheme of an existing design if the number of DRPs in each competing

Fig. 8. Spectrum of full-size LP ADC with 16 serially biased output drivers partitioned into 8 islands.

<!-- image -->

path is kept the same. For example, each TN module of the upper integrator provides two pulses (master clock and data) to each TD module. The relative timing between the master clock and data remains unaltered by adding the extra DRP in each path.

Before converting a parallel-biased circuit to a serially biased one with a combined bias, it must be optimized to get wide overlapping margins for all biases and prove these margins experimentally. Our experience shows that serial biasing narrows design margins and limits exploration of operating regions for a design that is optimized through independent bias nets. So such a conversion should be only considered as a final stage for verified and proven designs.

## V. LP ADC WITH SERIALLY BIASED OUTPUT DRIVERS

Our next milestone was the design of a full-size LP ADC chip with 16 serially biased output drivers. Two versions of the ADC with 4 and 8 islands were designed. Complete operability of the 8-island version was demonstrated at master clock frequencies up to 10 GHz without any degradation of its performance compared to its conventional counterpart [8] as illustrated in Fig. 8. The correct scaling of the original large (120 mA) bias current was observed. The total number of DRPs on chip was 32 to supply each driver with reset and set pulses during each Nyquist clock period.

## VI. ADC WITH SERIALLY BIASED DECIMATION FILTER

Next, we designed another full-sized LP ADC with a serially biased digital decimation filter and output drivers to prove the feasibility of a large-scale digital circuit biased in series.

Fig. 9 shows the central part of a 10 mm 10 mm chip that comprises a LP modulator and 18 bit slices of the 2nd order digital filter, suitable for a decimation ratio of 256. The total count of Josephson junctions is about 6000. Digital outputs are produced from 16 of the more significant bits of the digital filter; the first two slices do not contribute bits of significance. These 16 filter slices and their corresponding output drivers are serially biased by a factor of 4. The perceptive reader can distinguish 4 ×

Fig. 9. Layout of serially biased LP ADC chip (central part is shown). Each group of 4 bits of DDF and output drivers is placed on 3 islands and utilizes 24 DRPs.

<!-- image -->

large blocks of design separated from each other in Fig. 9. Actually each block consists of 3 islands (as marked in Fig. 9) and comprises 4 bits of filter and drivers. The top islands are devoted to the TN integrator. The TD integrator and output drivers are on separate islands also. We decided to keep the TN and TD modules separate to improve flexibility. The chip was designed and submitted for fabrication.

The total number of DRPs required is given by the expression , where and are the numbers of islands and bits per islands respectively. For the LP ADC shown in Fig. 9 this gives 84 DRPs. For a full channelizer with two decimation filters and two sets of output drivers, the number of required DRPs goes up. For example, 136 DRPs are required for a channelizer with two serially biased 12-bit 2nd-order decimation filters, each partitioned into 4 3-bit blocks, and each block containing 3 islands. 4((N; 十 1)Np 十 Ni

## VII. CONCLUSION

We have developed all the required components to convert a conventional parallel-biased digital-RF channelizing receiver into a serially-biased one. Appropriate scaling of bias current, up to a factor of 8, has been established with both output drivers and digital filter components. We have also designed serial biasing in relatively complex ADC and digital-RF receiver designs. The ability to serially bias relatively complex digital circuitry opens up another dimension in optimizing large-scale RSFQ integrated circuits and systems.

The inter-island interface circuitry, comprising one or more DRPs, does require additional bias current and chip space. This design overhead increases as we partition the circuitry into many very small islands. On the other hand, the higher the degree of serial biasing, the lower is the total bias current, which in turn helps lessen the size, weight, and power consumption of cryocooled superconductor digital systems. Future designs will have to balance these factors to arrive at the optimum partitioning scheme. Reduction of bias currents should also alleviate the flux trapping problems associated with large bias currents.

## ACKNOWLEDGMENT

The authors thank, D. Donnelly, R. Hunt, J. Vivalda, D. Yohannes, J. Coughlin, and S. K. Tolpygo of the HYPRES fabrication team for producing the chips. We would also like to thank A. F. Kirichenko, S. K. Tolpygo and D. E. Kirichenko for stimulating discussions, and A.M. Kadin for editorial efforts.

## REFERENCES

- [1] D. Gupta, T. V. Filippov, A. F. Kirichenko, D. E. Kirichenko, I. V. Vernik, A. Sahu, S. Sarwana, P. Shevchenko, A. Talalaevskii, and O. A. Mukhanov, 'Digital channelizing radio frequency receiver,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 430-437, June 2007.
- [2] A. M. Kadin, R. J. Webber, and D. Gupta, 'Current leads and optimized thermal packaging for superconducting systems on multistage cryocoolers,' IEEE Trans. Appl. Supercond. , vol. 17, no. 2, pp. 975-978, June 2007.
- [3] A. M. Kadin, R. J. Webber, and S. Sarwana, 'Effects of superconducting return currents on RSFQ circuit performance,' IEEE Trans. Appl Supercond. , vol. 15, no. 2, pp. 280-283, June 2005.
- [4] V. K. Semenov and M. A. Voronova, 'DC voltage multipliers: A novel application of synchronization in Josephson junction arrays,' IEEE Trans. Magn. , vol. 23, pp. 1476-79, March 1987.
- [5] V. Semenov and Y. Polyakov, 'Circuit improvements for a voltage multiplier,' IEEETrans. Appl. Supercond. , vol. 11, pp. 550-553, March 2001.
- [6] J. H. Kang and S. B. Kaplan, 'Current recycling and SFQ signal transfer in large scale RSFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 547-550, June 2003.
- [7] M. W. Johnson, Q. P. Herr, D. J. Durand, and L. A. Abelson, 'Differential SFQ transmission using either inductive or capacitive coupling,' IEEE Trans. Appl. Supercond. , vol. 13, no. 2, pp. 507-510, June 2003.
- [8] I. V. Vernik, D. E. Kirichenko, V. V. Dotsenko, R. J. Webber, R. Miller, P. Shevchenko, D. Gupta, and O. A. Mukhanov, 'Progress in the development of cryocooled digital channelizing RF receivers,' IEEE Trans. Appl. Supercond. , submitted for publication.
- [9] T. V. Filippov, S. V. Pflyuk, V. K. Semenov, and E. B. Wikborg, 'Encoders and decimation filters for superconductor oversampling ADCs,' IEEE Trans. Appl. Supercond. , vol. 11, pp. 545-549, Mar. 2001.
- [10] HYPRESDesignRulesHYPRES,Inc[Online].Available: http://www. hypres.com/pages/download/designrules/DesignRules.pdf
- [11] D. Y. Zinoviev and Y. A. Polyakov, 'Octopux: An advanced automated setup for testing superconductor circuits,' IEEE Trans. Appl. Supercond. , vol. 7, pp. 3240-3243, June 1997.