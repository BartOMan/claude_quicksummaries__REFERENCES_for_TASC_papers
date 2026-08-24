Received April 24, 2022, accepted May 19, 2022, date of publication May 23, 2022, date of current version May 27, 2022.

Digital Object Identifier 10.1 109/ACCESS.2022.3177206

## High Efficiency and Voltage Conversion Ratio Bidirectional Isolated DC-DC Converter for Energy Storage System

YU-EN WU , (Member, IEEE), AND BO-HAU PAN

Department of Electronic Engineering, National Kaohsiung University of Science and Technology, Kaohsiung 82444, Taiwan

Corresponding author: Yu-En Wu (yew@nkust.edu.tw)

ABSTRACT This paper proposes a high efGLYPH&lt;28&gt;ciency and conversion ratio bidirectional isolated DC-DC converter with three-winding coupled inductor, which can fulGLYPH&lt;28&gt;l storage system charging and discharging. The proposed topology is improved from traditional Buck-Boost converter. By integrating coupled inductor and switched-capacitor into power stage, the proposed converter can achieve the merits of isolation and bidirectional power GLYPH&lt;29&gt;ow. The proposed topology has only four switches and a common core coupled inductor, which greatly reduces design costs and achieves high step-up/step-down voltage gain without excessive duty cycles or high turns ratios. In addition, the proposed also has the function of leakage inductance energy recovery, which can recover all the energy stored in the leakage inductance to improve efGLYPH&lt;28&gt;ciency, and the main switches has a zero voltage switching (ZVS) feature. This paper implements a 500 W converter to verify the feasibility of the proposed topology through software simulation and experiment results, and conducts theoretical analysis, formula derivation, operation principle analysis, and non-ideal analysis. Finally, the experimental results show that the highest efGLYPH&lt;28&gt;ciency of the step-up and step-down modes are 96.8% and 96.4%, respectively.

INDEX TERMS Bidirectional DC-DC converter, zero voltage switching, three-winding coupled inductor.

## I. INTRODUCTION

Since the industrial revolution, power generation driven by petrochemicals, coal and liqueGLYPH&lt;28&gt;ed natural gas has caused a series of damage to the environment. Therefore, in recent years, countries around the world have also realized the importance of renewable energy and vigorously advocated renewable energy [1]GLYPH&lt;21&gt;[3]. Renewable energy is natural energy, such as solar energy, wind energy, tidal energy, geothermal energy, hydroelectric power and biogas. However, due to irresistible factors, such as weather, environment, etc., the aforementioned renewable energy sources will become unstable. In order to make up for the power shortage in the process of green energy power generation, an energy storage system needs to be added to make the entire system more complete. When the production of green energy is too much, the excess electric energy will be stored in the energy storage system, and when the peak electricity is used, the energy storage system will be activated to distribute

<!-- image -->

The associate editor coordinating the review of this manuscript and approving it for publication was Alexander Micallef .

VOLUME 10, 2022

the overall electric energy. Therefore, as shown in Fig.1, a distributed generation system [4]GLYPH&lt;21&gt;[6] is needed to assist the renewable energy system. The distributed power generation system plays an important role in the Micro-grid system, reducing the excessive consumption of traditional energy.

With the development of green energy, the demand for converters has increased. Compared with the traditional converters in the past, converters nowadays have more complexity and functional requirements; furthermore, the application level is more extensive. Bidirectional converters are indispensable in green energy system. Besides power supply applications for green energy system, bidirectional converters are also widely used in electric vehicle (EV), hybrid electric vehicles (HEV), plug-in hybrid electric vehicles (PHEV), uninterruptible power system (UPS), battery energy storage system (BESS) and renewable energy systems, etc., the importance of bidirectional converters can be seen from the above, it can effectively reduce the number of components, increase the power density and reduce production costs. The common non-isolated bidirectional converter is to transform Boost, Buck-Boost, SEPIC and other unidirectional

<!-- image -->

FIGURE 1. Configuration of diversified generation system with energy storage system.

<!-- image -->

<!-- image -->

converters, which has the advantages of low cost, high circuit stability, and strong practicability. However, they are limited by the duty cycle, and traditional non-isolated converters cannot provide a higher voltage conversion ratio.

Non-isolated bidirectional DC-DC converters [7], [8] are derived from traditional converters. The main circuits of the above topologies all use switched-capacitor voltage doubler technology [9]GLYPH&lt;21&gt;[11] to achieve high voltage gain ratio. However, in order to achieve voltage gain, switchedcapacitor technology increases the number of components and increases conduction losses. The topologies of [12], [13] use cascade and coupled inductor technologies respectively. In [12], the voltage gain is better than the traditional Buck-Boost bidirectional converter through the cascade technology. In [13], the active clamp circuit can recover the leakage inductance energy of the coupled inductor to achieve ZVS and improve the conversion efGLYPH&lt;28&gt;ciency.

Common isolated bidirectional converters are forwardGLYPH&lt;29&gt;yback converters [14]GLYPH&lt;21&gt;[16] and bridge converters [17]GLYPH&lt;21&gt;[19], which have the advantages of high circuit stability and strong practicability. The isolated bidirectional DC-DC converters [20]GLYPH&lt;21&gt;[23] which were based on a basic bidirectional GLYPH&lt;29&gt;yback converter. In [20], the circuit has the advantages of leakage inductance recovery, ZVS, and high conversion efGLYPH&lt;28&gt;ciency. The increased auxiliary power supply terminal makes the current continuous, which improves the problem of large current ripple of the traditional forward and GLYPH&lt;29&gt;yback converter. In [21], this topology consists of a set of interleaved GLYPH&lt;29&gt;yback converters on the low-voltage side and two converters similar to the half-bridge converters on the high-voltage side, and combines the LCD snubber circuit to recover the energy of the leakage inductance and improve the conversion efGLYPH&lt;28&gt;ciency. In [22], this topology is composed of a Buck-Boost converter, a forward-GLYPH&lt;29&gt;yback converter and a switched-capacitor voltage doubler circuit. It has a very high voltage gain ratio, and has ZVS feature in the switch to improve conversion efGLYPH&lt;28&gt;ciency. There are many differences between this paper and [22], such as circuit architecture, operating principles, circuit analysis, experimental results and advantages (higher efGLYPH&lt;28&gt;ciency and using fewer parts), etc.

In [23], an isolated bidirectional bridge converter was proposed. The primary side of this topology is an improved push-pull converter, which adds a switch to achieve ZVS, while the secondary side is a full-bridge topology. Compared with the traditional bidirectional full-bridge converter, the converter uses a three-switch topology on the low-voltage side to replace the full-bridge structure. It can save the cost of the drive circuit, and can better ensure the stability of the entire system.

## II. CIRCUIT ARCHITECTURE AND OPERATIONAL PRINCIPLES

The proposed isolated bidirectional DC-DC converter in this paper, as shown in Fig. 2(a). The components are deGLYPH&lt;28&gt;ned as follows. VL and VH are the low-side and high-side power ports, respectively. The S1 to S4 are power switches, where DS1 to DS4 and CS1 to CS4 represent the body diodes and parasitic capacitances of the switches, respectively. The capacitors C1 to C4 , three-winding coupled inductor are also part of the proposed topology. The coupled inductor is composed of leakage inductance Llk1 , Llk2 and Llk3 , magnetizing inductance Lm1 and turns ratio n .

FIGURE 2. The proposed topology: (a) diagram of the bidirectional isolated DCGLYPH&lt;21&gt;DC converter and (b) the definitions for the equivalent circuit diagram.

<!-- image -->

The operation principle of the proposed converter in step-up mode and step-down mode is analyzed. The corresponding components, voltage polarity and current direction of the converter are shown in Fig. 2(b). The magnetic components operate in CCM mode. In order to describe and simplify the operation of the converter, assume the following V

- 1) The capacitance C1, C2, C3 and C4 values are assumed to be large enough.
- 2) All switches are assumed to be ideal, and body diodes and parasitic capacitance are considered.
- 3) The values of the leakage inductance Llk1, Llk2 and Llk3 are much smaller than magnetizing inductance Lm1.
- 4) The turns of N1 is equal to N2 but less than N3, and the ratio of N3 / N1 and N2 / N1 are deGLYPH&lt;28&gt;ned as n.

## A. STEP-UP MODE

In the step-up mode, the switches S1 and S2 are complementary signals Vgs1 and Vgs2 , and the signals of S3 and S4 are OFFstate. The key waveforms of the step-up mode are shown in Fig. 3. This operation can be divided into GLYPH&lt;28&gt;ve modes in an operating cycle, and the modes are shown in Fig. 4(a)-(e).

FIGURE 3. Key waveforms of proposed topology in step-up mode.

<!-- image -->

## 1) MODE 1 [t0 GLYPH&lt;24&gt; t1]

This mode starts at time t D t0, all switch signals are in OFF state. The leakage inductance Llk1 extracts the energy from the parasitic capacitance CS1 of the switch S1 to achieve ZVS and the parasitic capacitances CS2 of the switch S2 storage energy until the switch S2 is turned OFF. The energy of the magnetizing inductance Lm1 is

VOLUME 10, 2022

<!-- image -->

IEEE AccesS'

FIGURE 4. Equivalent circuit diagram of in step-up mode, (a) Mode 1, (b) Mode 2, (c) Mode 3, (d) Mode 4, and (e) Mode 5.

<!-- image -->

released to the high voltage side VH , the capacitor C4 is charged but the capacitor C3 is discharged. While the current of the body diode DS4 on switch S4 drops to zero,

<!-- image -->

Mode 1 ends. The equivalent circuit of Mode 1 shown as Fig. 4(a).

## 2) MODE 2 [t1 GLYPH&lt;24&gt; t2]

This modes begins as switch S1 is turned ON at t D t1, the switch signal Vgs1 is in ON state and the switch signal Vgs2 is in OFF state. The low voltage side VL supplies energy to magnetizing inductance Lm1 and leakage inductance Llk1 and is also transmitted to the high voltage side VH and the capacitor C3 through the coupled inductor and via the body diode DS3 of the switch S3, while the low voltage side VL and the capacitor C1 provide energy to the capacitor C2 and the leakage inductance Llk2. At the same time, the capacitor C4 starts to release energy to high voltage side VH . Mode 2 ends while switch S1 is turned OFF. The equivalent circuit of Mode 2 is shown as Fig. 4(b).

## 3) MODE 3 [t2 GLYPH&lt;24&gt; t3]

At the beginning of this mode at the time t D t2, all switch signals are in OFF state. The leakage inductance Llk2 extracts the energy from the parasitic capacitance CS2 of the switch S2 to achieve ZVS. The parasitic capacitances CS1 of the switches S1 storage energy until the switches S1 is in OFF state. The low voltage side VL continuously transmits energy to the high voltage side VH , while the current of the body diode DS3 on switch S3 drops to zero, Mode 3 end. The equivalent circuit of Mode 3 is shown as Fig. 4(c).

## 4) MODE 4 [t3 GLYPH&lt;24&gt; t4]

In Mode 4, the time starts from t D t3, the switch signal Vgs2 is in ON state and the switch signal Vgs1 is in OFF state. The magnetizing inductance Lm1 and the capacitor C2 releases energy to the high voltage side VH and the capacitor C4 through the coupled inductor and via the body diode DS4 of the switch S4. Meanwhile, the capacitor C3 starts to release energy to high voltage side VH . The leakage inductance Llk1 releases energy to the capacitor C1 through the switch S2 until the current in S2 is zero, and the Mode 4 ends. The equivalent circuit of Mode 4 is shown as Fig. 4(d).

## 5) MODE 5 [t4 GLYPH&lt;24&gt; t5]

Mode 5 at time t D t4, the switch signals is consistent with the previous mode. The capacitor C1 continues to charge but capacitor C2 continues to discharge. Mode 5 ends while switch S2 is turned OFF. The equivalent circuit of Mode 5 is shown as Fig. 4(e).

## B. STEP-DOWN MODE

In the step-down mode, the operating signals are also complementary signals, Vgs1 and Vgs3 are one set, and Vgs2 and Vgs4 are another set. The key waveforms of the step-down mode are shown in Fig 5. There are seven modes in this operating cycle, and the modes are shown in Fig. 6(a)-(g).

## 1) MODE 1 [t0 GLYPH&lt;24&gt; t1]

In Mode 1 begins at the time t D t0, all switch signals are in OFF state. The high voltage side VH charges the parasitic capacitance CS6 to make the switch S6 turned OFF. At this time, a negative current draws the electric charges on the parasitic capacitance CS5 of the switch S5 to achieve ZVS. The energy of capacitor C1 is stored by the leakage inductance Llk1. The inductor L1 releases energy to the low voltage side VL . While the switch signals Vgs3 , Vgs4 and Vgs5 are in ON state, Mode 1 ends. The equivalent circuit of Mode 1 is shown as Fig. 6(a).

## 2) MODE 2 [t1 GLYPH&lt;24&gt; t2]

This stage begins as switch S1 and S3 are turned ON and switch S2 and S4 are turned OFF at t D t1, the switch signal Vgs1 and Vgs3 are in ON state and the switch signal Vgs2 and Vgs4 are in OFF state. The energy of the magnetizing inductance Lm1 is continuously transmitted to the low voltage side VL . The capacitor C1 continues to discharge, while the current of the leakage inductance Llk2 drops to zero, Mode 2 ends. And the equivalent circuit of Mode 2 is shown as Fig. 6(b).

FIGURE 5. Key waveforms of proposed topology in step-up mode.

<!-- image -->

## 3) MODE 3 [t2 GLYPH&lt;24&gt; t3]

At the beginning of this mode at the time t D t2, the switch signals is consistent with the previous mode. The capacitor C3 releases energy to the low voltage side VL through the coupled inductor, while the capacitor C2 provides energy to

VOLUME 10, 2022

the low voltage side VL and the capacitor C1. At the same time, the high voltage side VH starts to charge the capacitor C4. Mode 3 ends while all switches are turned OFF. The equivalent circuit of Mode 3 is shown as Fig. 6(c).

## 4) MODE 4 [t3 GLYPH&lt;24&gt; t4]

In Mode 4, the time starts from t D t3, all switch signals are in OFF state. The high voltage side VH charges the parasitic capacitance CS3 of the switch S3 until the switch S3 is turned OFFand the leakage inductance Llk3 extracts the energy from the parasitic capacitance CS4 of the switch S4 to achieve ZVS. The energy of the magnetizing inductance Lm1 starts to store energy. Meanwhile, the leakage inductance Llk1 and Llk2 are released to the low voltage side VL via the body diode DS1 of the switch S1, while CS3 reaches the voltage of VH , Mode 4 ends. The equivalent circuit of Mode 4 shown as Fig. 6(d).

## 5) MODE 5 [t4 GLYPH&lt;24&gt; t5]

At time t D t4, the switch signals Vgs1 and Vgs3 are in OFF state and the switch signals Vgs2 and Vgs4 are in ON state. The capacitor C1 supplies energy to magnetizing inductance Lm1 and leakage inductance Llk1 but capacitor C2 continues to release energy to leakage inductance Llk2, The capacitors C3 continues discharged until the current of switch S4 drops to zero, Mode 5 ends. The equivalent circuit of Mode 5 is shown as Fig. 6(e).

## 6) MODE 6 [t5 GLYPH&lt;24&gt; t6]

At time t D t5, the switch signals is consistent with the previous mode. The capacitor C1 continues to supply energy to magnetizing inductance Lm1 and leakage inductance Llk1. While the current of the switch S2 drops to zero, Mode 6 ends. The equivalent circuit of Mode 6 is shown as Fig. 6(f).

## 7) MODE 7 [t6 GLYPH&lt;24&gt; t7]

At the beginning of this mode at the time t D t6. The leakage inductance Llk2 starts to provide energy to the capacitor C2. While all switches are turned OFF, Mode 7 ends. And the equivalent circuit of Mode 7 is shown as Fig. 6(g).

## III. STEADY-STATE ANALYSIS

While analyzing the circuit, the analysis is operated in CCM. The switching period is TS, the signals Vgs1 and Vgs2 are turned ON for time D1TS and turned OFF for time (1-D1)TS, in step-up mode. In step-down mode, the signals Vgs1 and Vgs3 are turned ON for time D3TS and turned OFF for time (1-D3)TS, the while switching period is TS. The following assumptions need to be made when the proposed topology is analyzed V

- 1) All components are ideal, regardless of internal resistance and parasitic effects.
- 2) The capacitance of all capacitors is large enough, making the voltage of capacitors constant.
- 3) The leakage inductance of the coupled inductor is ignored.
- 4) Ignore the circuit operation mode in the dead time.
- 5) The ideal turns ratio is represented by n D N3/ N1 D N3/N2 and n is deGLYPH&lt;28&gt;ned as coupled inductor turns ratio.

VOLUME 10, 2022

<!-- image -->

## A. STEP-UP MODE

## 1) VOLTAGE GAIN ANALYSIS

The VH is the sum of the voltages of VC3 and VC4 , it can be expressed as

<!-- formula-not-decoded -->

In order to derive the high voltage side VH, the relationship between VC1 , VC2 , VC3 , VC4 and low voltage side VL must be derived respectively.

During D1TS, the switch signals is turned ON by Vgs1 , as shown in the equivalent circuit in Fig. 4(b). According to Kirchhoff's voltage law (KVL), the voltage at Lm1 can be expressed as

<!-- formula-not-decoded -->

During (1-D1)TS, the switch signals Vgs1 is turned OFF and the equivalent circuit is shown in Fig. 4(e). According to KVL, the voltage at Lm1 can be expressed as

<!-- formula-not-decoded -->

According to the voltage-second balance of the inductor, the amount of current change in the steady-state during switching must be zero, expressed as

<!-- formula-not-decoded -->

Substituting (2) and (3) into (4), the voltage of capacitors C1, C2, C3 and C4 can be obtained as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Finally, substituting (7) and (8) into (1), the voltage gain in step-up mode Gstep-up can be derived as

<!-- formula-not-decoded -->

According to (9), the voltage gain in the step-up mode Gstep-up, the relationship between the duty cycle D1 and the turns ratio n is shown in Fig. 7.

## 2) VOLTAGE AND CURRENT STRESSES ANALYSIS OF COMPONENTS

According to the switching sequence in step-up mode, the voltage stress relative to S1, S2, S3 and S4 can

<!-- image -->

IEEE AccesS'

FIGURE 6. Equivalent circuit diagram of in step-down mode, (a) Mode 1, (b) Mode 2, (c) Mode 3, (d) Mode 4, (e) Mode 5, (f) Mode 6, and (g) Mode 7.

<!-- image -->

be expressed as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

According to Kirchhoff's current law (KCL) and amperesecond balance, the peak current relative to S1, S2, S3 and S4

VOLUME 10, 2022

FIGURE 7. Voltage gain of the proposed topology in step-up mode.

<!-- image -->

can be expressed as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

## 3) MAGNETIC COMPONENTS DESIGN

The magnetic components of the proposed topology are designed in CCM, the maximum and minimum current of the magnetic components Lm1 can be calculated by

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

The ripple current and average current of Lm1 can be determined by

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

When the current iLm1,min is equal to zero, the magnetic components are operated in boundary conduction mode (BCM). Substituting (20) and (21) into (19), the current iLm1,min and the Lm1 formula in BCM can be expressed as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Under this conditions of the high voltage side is 400 V, the current of high voltage side IH ; BCM is 0.1875 A, the switching frequency fs is 40 kHz and the turns ratio n is 4, the result

VOLUME 10, 2022

<!-- image -->

IEEE AccesS'

of substituting (23) is shown in Fig. 8. When the value of Lm1is greater than the BCM curve, Lm1 is operated in CCM; otherwise, it is operated in DCM.

FIGURE 8. The curve of Lm1,BCM in step-up mode.

<!-- image -->

The peak-to-peak value of the capacitor ripple can be calculated by using the inGLYPH&lt;29&gt;ow and outGLYPH&lt;29&gt;ow capacitor current. The capacitor ripple voltage can be expressed as

<!-- formula-not-decoded -->

The voltage ripple of each capacitor is 1 VC1 / VC1 , 1 VC2 / VC2 , 1 VC3 / VC3 and 1 VC4 / VC4 , and the each capacitance value can be obtained as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

## B. STEP-DOWN MODE

## 1) VOLTAGE GAIN ANALYSIS

The low voltage side VL is the voltage of the magnetizing inductance Lm1, it can be expressed as

<!-- formula-not-decoded -->

During D3TS, the switch signals Vgs1 and Vgs3 are turned ON, as shown in the equivalent circuit in Fig. 6(c). According to KVL, the voltage at Lm1 can be expressed as

<!-- formula-not-decoded -->

During (1-D3)TS, the switch signals Vgs1 and Vgs3 are turned OFF, and the equivalent circuit is shown in Fig. 6(f). According to KVL, the voltage at Lm1 can be obtained as

<!-- formula-not-decoded -->

<!-- image -->

IEEE AccesS'

Substituting (30) and (31) into (4), the voltage of capacitors C1, C2, C3 and C4 can be obtained as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The voltage of Lm1 is equal to the voltage of VC3 divided by n. Finally, substituting (32) into (29), the voltage gain in step-down mode Gstep-down can be derived as

<!-- formula-not-decoded -->

FIGURE 9. Voltage gain of the proposed topology in step-down mode.

<!-- image -->

According to (36), the voltage gain in the step-down mode Gstep-down, the relationship between the duty cycle D3 and the turns ratio n is shown in Fig. 9.

## 2) VOLTAGE STRESS ANALYSIS OF COMPONENTS

According to the switching sequence in step-down mode, the voltage stress relative to S1, S2, S3 and S4 can be expressed as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

According to Kirchhoff's current law (KCL) and amperesecond balance, the peak current relative to S1, S2, S3 and S4 can be expressed as

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

## 3) MAGNETIC COMPONENTS DESIGN

The maximum and minimum current of the magnetic components Lm1 can be calculated by

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

The ripple current and average current of Lm1 can be determined by

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

When the current iLm1,min is equal to zero, the magnetic components are operated in boundary conduction mode (BCM). Substituting (47) and (48) into (46), the current iLm1,min can be expressed as

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

Under this conditions of the high voltage side is 400 V, the current of high voltage side IH ; BCM is 0.1875 A, the switching frequency fs is 40 kHz and the turns ratio n is 4, the result of substituting (50) is shown in Fig. 10. When the value of Lm1 is greater than the BCM curve, Lm1 is operated in CCM; otherwise, it is operated in DCM.

FIGURE 10. The curve of Lm1,BCM in step-down mode.

<!-- image -->

VOLUME 10, 2022

## 4) EFFICIENCY ANALYSIS OF COMPONENTS

The conduction loss of a component is derived by using the current peak value to derive its RMS value, and then using the RMS value to calculate the conduction loss of each component. Therefore, the total power losses PLoss of the proposed converter can be expressed as equation (51). Where, PS1,loss -PS4,loss represents the conduction loss of S1 -S4 , PC1,loss -PC4,loss represents the operating loss of C1 -C4 , while PLlk1,loss -PLlk3,loss represents the operating loss of leakage inductance Llk1 -Llk3 .

<!-- formula-not-decoded -->

Thenon-ideal conversion efGLYPH&lt;28&gt;ciency GLYPH&lt;17&gt; step GLYPH&lt;0&gt; up and GLYPH&lt;17&gt; step GLYPH&lt;0&gt; down can be determined by

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

And the non-ideal voltage gain of the converter can be calculated as

<!-- formula-not-decoded -->

And

<!-- formula-not-decoded -->

As shown in Fig. 11(a)-(d), substituting the conduction losses of the component into (52)-(55), it can be concluded that when the load increases, the non-ideal voltage gain and non-ideal efGLYPH&lt;28&gt;ciency will continue to decrease. The speciGLYPH&lt;28&gt;cations of the proposed converter used in these GLYPH&lt;28&gt;gures have been assumed to be VL D 48, VH D 400 V, n D 4, rds1 D rds2 D 5 : 9 m GLYPH&lt;127&gt; , rds3 D rds4 D 190 m GLYPH&lt;127&gt; , rC1 D rC2 D 50 m GLYPH&lt;127&gt; , rC3 D rC4 D 500 m GLYPH&lt;127&gt; and rL1 D rL2 D rL3 D 50 m GLYPH&lt;127&gt; .

## IV. EXPERIMENTAL DESIGN AND RESULTS

The common battery voltage is about 48V, and the DC bus voltage is about 400V. Therefore, the recommended converter design parameters are 48V for the low-side voltage VL and 400V for the high-side voltage VH . The magnetic component is designed to be 15% of the full load of the BCM, where IH is 0.1875A and IL is 1.5624A. The maximum allowable voltage ripple of C1 and C2 is 10% generally, and the high-side capacitors C3 and C4 are 1%. In addition, the electrical speciGLYPH&lt;28&gt;cations of the recommended topology are shown in TABLE 1. The photograph of the proposed bidirectional converter is shown in Fig. 12. The microcontroller is dsPIC30F4011and the type of controller is PI controller. The output voltage in the step-up and step-down mode of the converter is captured to the MCU for compensation with the PWM signal.

VOLUME 10, 2022

<!-- image -->

IEEE AccesS'

FIGURE 11. Non-ideal of the proposed topology in step-up mode (a) voltage gain and (b) efficiency, and non-ideal of the proposed topology in step-down mode (c) voltage gain and (d) efficiency.

<!-- image -->

FIGURE 12. Photograph of the proposed topology, (a) main circuit, and (b) control circuit.

<!-- image -->

<!-- image -->

In the measurement results, because the ZVS effect of the switches element is not obvious at light load, the following measured waveforms are all presented under the condition of full load.

In Fig. 13(a)-(e), the key waveforms measured in the step-up mode at a full load of 500 W. Fig. 13(a) is the complementary signal of Vgs1 and Vgs2 , and the measured waveforms of leakage inductance Llk1 and Llk2 . The measured waveforms of Vds and ids of switches S1 and S2 are shown in Figure 13(b). The measured current waveforms ids1 and ids2

<!-- image -->

IEEE AccesS'

TABLE 1. The electrical specifications of the proposed topology.

show that the switches S1 and S2 have ZVS in the step-up mode. In Fig. 13(c), there are measured waveforms of Vds and ids of switches S3 and S4 . The measured current waveforms Vds3 and Vds4 show that the voltage stress of switches S3 and S4 is the high-side voltage VH 400V. Fig. 13(d) shows the measured waveforms of the voltages of capacitors C1 , C2 , C3 , and C4 in the proposed topology. It can be known that the sum of the voltages of C3 and C4 is the high-side voltage VH 400 V. In Fig. 13(e), shows the soft switching measurement waveforms of Vds and ids of S1 and S2 in one switching cycle.

The key waveforms measured at a full load of 500 W in the step-down mode are shown in Fig. 14(a)-(e). Fig. 14(a) is the complementary signal of Vgs3 and Vgs4 , and the measured waveforms of the leakage inductances Llk1 and Llk2. The measured waveforms of Vds and ids of switches S1 and S2 are shown in Fig. 14(b). The measured current waveforms Vds1 and Vds2 show that the voltage stress of switches S1 and S2 is equal to 100 V. In Fig. 14(c), there are measured waveforms of vds and ids of switches S3 and S4. The measured current waveforms ids3 and ids4 show that switches S3 and S4 have ZVS in the step-down mode. Fig. 14(d) shows the voltage measurement waveforms of capacitors C1, C2, C3, and C4 in the proposed topology. It can be seen that all capacitor voltages are constant. In Fig. 14(e), shows the soft switching measurement waveforms of Vds and ids of S3 and S4 in one switching cycle.

The conversion efGLYPH&lt;28&gt;ciency of step-up mode and step-down mode are shown in Fig. 15, respectively. In the step-up mode, the highest conversion efGLYPH&lt;28&gt;ciency point is 96.8%

FIGURE 13. 13. Experimental results of proposed topology in the step-up mode at full load of 500 W, (a) Waveforms of V gs1 , V gs2 , i lk1 and i lk2 , (b) V ds and i ds of S1 and S2, (c) V ds and i ds of S3 and S4, and (d) Voltage of C1, C2, C3 and C4, (e) V ds and i ds of S1 and S2 in one switching cycle.

<!-- image -->

operated under 100 W-150 W. In the step-down mode, the highest conversion efGLYPH&lt;28&gt;ciency point is 96.2% operated under 100 W-200 W.

In addition, calculate the conduction losses of each component according to the equations in (52)-(55). Fig. 16(a) and Fig. 16(b) shows the losses in step-up mode and step-down mode at full load of 500 W, respectively. It can be known that in the step-up mode, the high-side voltage switches cause larger conduction losses due to the forward voltage of the body diode. In the step-down mode, the conduction losses of the switches are greatly reduced due to the use of synchronous rectiGLYPH&lt;28&gt;cation technology.

To verify the performance and understand the advantages and disadvantages of the proposed topology, compare the number of components of a different bidirectional converters, the complexity of the PWM signal and the voltage gain, etc. In TABLE 2, a comparison with other bidirectional converters [7], [8], [20], and [21] is summarized.

Fig. 17(a) and Fig. 17(b) show the comparison of the voltage gain with other bidirectional converters in step-up mode and step-down mode, respectively. When the turns ratio is n D 4, the voltage gain of the converter is only lower

FIGURE 14. Experimental results of proposed topology in the step-up mode at full load of 500 W, (a) Waveforms of V gs3 , V gs4 , i Lk1 and i Lk2 , (b) V ds and ids of S1 and S2, (c) V ds and i ds of S3 and S4, and (d) Voltage of C1, C2, C3 and C4, (e) V ds and ids of S3 and S4 in one switching cycle.

<!-- image -->

FIGURE 15. Efficiency of the proposed converter in step-up and step-down mode.

<!-- image -->

than [21], but the number of components in the [21] topology is twice that of the proposed converter.

The conversion efGLYPH&lt;28&gt;ciency of the proposed topology and the topology proposed in [7], [8], [20], and [21] are compared in the step-up mode and the step-down mode, respectively, as shown in Fig. 18(a) and Fig. 18(b). In [7] and [8], in order to increase the voltage gain ratio, excessive component losses are caused and the conversion efGLYPH&lt;28&gt;ciency is reduced. The best topology is [20], which has higher conversion efGLYPH&lt;28&gt;ciency in step-down mode, but its disadvantage is the low voltage gain

<!-- image -->

IEEE AccesS'

FIGURE 16. Conduction losses distribution (a) in step-up mode, and (b) in step-down mode.

<!-- image -->

FIGURE 17. Comparison of the voltage gain (a) in step-up mode, and (b) in step-down mode.

<!-- image -->

ratio. The highest overall voltage gain ratio is [21], but the circuit components are also the most, so higher conversion efGLYPH&lt;28&gt;ciency cannot be achieved. Overall, the conversion efGLYPH&lt;28&gt;ciency of the converter proposed in this thesis has good performance in step-up mode and the step-down mode, respectively, and the proposed topology has a higher voltage gain ratio.

In Fig. 19(a) and (b) shows the step variation of output load of proposed topology in step-up mode and step-down mode. The VL is 48 V and the VH is 400 V. While the output load is step changed between half load and full load. It can be

<!-- image -->

IEEE AccesS'

FIGURE 18. Comparison of efficiency (a) in step-up mode, and (b) in step-down mode.

<!-- image -->

TABLE 2. The comparison of related literatures on bidirectional converters.

seen that the output voltage (VH/VL) is very stable and is not greatly affected by load changes.

Figure 20 shows the input and output current ripple operated under load variation. It can be seen from the GLYPH&lt;28&gt;gure that the current ripple is still quite small when the load changes, which shows the stability of the circuit. According to the measurement results of load GLYPH&lt;29&gt;uctuations, it can be seen that the system stabilization time needs to be about 70 GLYPH&lt;22&gt; s.

FIGURE 19. Step variation of output load of the proposed topology. (a) Step-up mode (b) Step-down mode.

<!-- image -->

FIGURE 20. The input and output current ripple operated under load variation, (a) input current ripple, and (b) output current ripple.

<!-- image -->

## V. CONCLUSION

This paper proposes a novel bidirectional isolated DC-DC converter. The proposed topology has the following

VOLUME 10, 2022

advantages: (1) high voltage gain ratio and galvanic isolation; can be widely used in energy storage systems; (2) bidirectional energy transfer, the leakage inductance energy can be effectively recovered, and the main switch of the proposed topology has ZVS; (3) fewer components, greatly reducing development and design costs; (4) high conversion efGLYPH&lt;28&gt;ciency, which can reduce power conversion losses.

The topology proposed in this paper can be conGLYPH&lt;28&gt;rmed its feasibility and correctness through theoretical analysis, simulation and experimental results. In the implementation, it is concluded that the highest efGLYPH&lt;28&gt;ciency of the step-up mode or step-down mode are 96.8% and 96.4%, respectively.

## REFERENCES

- [1] J. Zeng, W. Qiao, L. Qu, and Y. Jiao, ''An isolated multiport DCGLYPH&lt;21&gt;DC converter for simultaneous power management of multiple different renewable energy sources,'' IEEE J. Emerg. Sel. Topics Power Electron. , vol. 2, no. 1, pp. 70GLYPH&lt;21&gt;78, Mar. 2014.
- [2] X. Sun, Y. Shen, Y. Zhu, and X. Guo, ''Interleaved boost-integrated LLC resonant converter with GLYPH&lt;28&gt;xed-frequency PWM control for renewable energy generation applications,'' IEEE Trans. Power Electron. , vol. 30, no. 8, pp. 4312GLYPH&lt;21&gt;4326, Aug. 2015.
- [3] M. C. Mira, Z. Zhang, A. Knott, and M. A. E. Andersen, ''Analysis, design, modeling, and control of an interleaved-boost full-bridge threeport converter for hybrid renewable energy systems,'' IEEE Trans. Power Electron. , vol. 32, no. 2, pp. 1138GLYPH&lt;21&gt;1155, Feb. 2017.
- [4] W.Chen, P. Rong, and Z. Lu, ''Snubberless bidirectional DCGLYPH&lt;21&gt;DC converter with new CLLC resonant tank featuring minimized switching loss,'' IEEE Trans. Ind. Electron. , vol. 57, pp. 3075GLYPH&lt;21&gt;3086, 2010.
- [5] J.-H. Jung, H.-S. Kim, M.-H. Ryu, and J.-W. Baek, ''Design methodology of bidirectional CLLC resonant converter for high-frequency isolation of DC distribution systems,'' IEEE Trans. Power Electron. , vol. 28, no. 4, pp. 1741GLYPH&lt;21&gt;1755, Apr. 2013.
- [6] Z. Wang and H. Li, ''An integrated three-port bidirectional DCGLYPH&lt;21&gt;DC converter for PV application on a DC distribution system,'' IEEE Trans. Power Electron. , vol. 28, no. 10, pp. 4612GLYPH&lt;21&gt;4624, Oct. 2013.
- [7] Y. Zhang, Q. Liu, Y. Gao, J. Li, and M. Sumner, ''Hybrid switchedcapacitor/switched-quasi-Z-source bidirectional DCGLYPH&lt;21&gt;DC converter with a wide voltage gain range for hybrid energy sources EVs,'' IEEE Trans. Ind. Electron. , vol. 66, no. 4, pp. 2680GLYPH&lt;21&gt;2690, Apr. 2019.
- [8] Y. Zhang, W. Zhang, F. Gao, S. Gao, and D. J. Rogers, ''A switchedcapacitor interleaved bidirectional converter with wide voltage-gain range for super capacitors in EVs,'' IEEE Trans. Power Electron. , vol. 35, no. 2, pp. 1536GLYPH&lt;21&gt;1547, Feb. 2020.
- [9] Y. F. Wang, L. K. Xue, C. S. Wang, P. Wang, and W. Li, ''Interleaved highconversion-ratio bidirectional DC-DC converter for distributed energystorage systems-circuit generation, analysis, and design,'' IEEE Trans. Power Electron. , vol. 31, no. 8, pp. 5547GLYPH&lt;21&gt;5561, Aug. 2016.
- [10] Y. Zhang, Y. Gao, L. Zhou, and M. Sumner, ''A switched-capacitor bidirectional DCGLYPH&lt;21&gt;DC converter with wide voltage gain range for electric vehicles with hybrid energy sources,'' IEEE Trans. Power Electron. , vol. 33, no. 11, pp. 9459GLYPH&lt;21&gt;9469, Nov. 2018.
- [11] A. Iqbal, M. D. Siddique, B. P. Reddy, P. K. Maroti, and R. Alammari, ''A new family of step-up hybrid switched-capacitor integrated multilevel inverter topologies with dual input voltage sources,'' IEEE Access , vol. 9, pp. 4398GLYPH&lt;21&gt;4410, 2021.
- [12] S. H. Hosseini, R. Ghazi, and H. Heydari-Doostabad, ''An extendable quadratic bidirectional DCGLYPH&lt;21&gt;DC converter for V2G and G2 V applications,'' IEEE Trans. Ind. Electron. , vol. 68, no. 6, pp. 4859GLYPH&lt;21&gt;4869, Jun. 2021.
- [13] M. Packnezhad and H. Farzanehfard, ''Bidirectional soft-switching converter with reduced current ripple at low-voltage side,'' IEEE J. Emerg. Sel. Topics Power Electron. , vol. 9, no. 4, pp. 4668GLYPH&lt;21&gt;4675, Aug. 2021.
- [14] F. Zhang and Y. Yan, ''Novel forwardGLYPH&lt;21&gt;GLYPH&lt;29&gt;yback hybrid bidirectional DCGLYPH&lt;21&gt; DC converter,'' IEEE Trans. Ind. Electron. , vol. 56, no. 5, pp. 1578GLYPH&lt;21&gt;1584, May 2009.
- [15] R. J. Wai and J. J. Liaw, ''High-efGLYPH&lt;28&gt;ciency-isolated single-input multipleoutput bidirectional converter,'' IEEE Trans. Power Electron. , vol. 30, no. 9, pp. 4914GLYPH&lt;21&gt;4930, Sep. 2015.

VOLUME 10, 2022

<!-- image -->

IEEE AccesS'

- [16] N. M. Mukhtar and D. D.-C. Lu, ''A bidirectional two-switch GLYPH&lt;29&gt;yback converter with cross-coupled LCD snubbers for minimizing circulating current,'' IEEE Trans. Ind. Electron. , vol. 66, no. 8, pp. 5948GLYPH&lt;21&gt;5957, Aug. 2019.
- [17] C. Bai, B. Han, B.-H. Kwon, and M. Kim, ''Highly efGLYPH&lt;28&gt;cient bidirectional series-resonant DC/DC converter over wide range of battery voltages,'' IEEE Trans. Power Electron. , vol. 35, no. 4, pp. 3636GLYPH&lt;21&gt;3650, Apr. 2020.
- [18] H. Shi, K. Sun, H. Wu, and Y. Li, ''A uniGLYPH&lt;28&gt;ed state-space modeling method for a phase-shift controlled bidirectional dual-active half-bridge converter,'' IEEE Trans. Power Electron. , vol. 35, no. 3, pp. 3254GLYPH&lt;21&gt;3265, Mar. 2020.
- [19] R. Haneda and H. Akagi, ''Design and performance of the 850-V 100-kW 16-kHz bidirectional isolated DCGLYPH&lt;21&gt;DC converter using SiC-MOSFET/SBD H-bridge modules,'' IEEE Trans. Power Electron. , vol. 35, no. 10, pp. 10013GLYPH&lt;21&gt;10025, Oct. 2020.
- [20] R. Wai and Z. Zhang, ''Design of high-efGLYPH&lt;28&gt;ciency isolated bidirectional DC/DCconverter with single-input multiple-outputs,'' IEEEAccess , vol. 7, pp. 87543GLYPH&lt;21&gt;87560, 2019.
- [21] C.-L. Shen, H. Liou, T.-C. Liang, and H.-Z. Gong, ''An isolated bidirectional interleaved converter with minimum active switches and high conversion ratio,'' IEEE Trans. Ind. Electron. , vol. 65, no. 3, pp. 2313GLYPH&lt;21&gt;2321, Mar. 2018.
- [22] Y.-E. Wu and Y.-T. Ke, ''A novel bidirectional isolated DCGLYPH&lt;21&gt;DC converter with high voltage gain and wide input voltage,'' IEEE Trans. Power Electron. , vol. 36, no. 7, pp. 7973GLYPH&lt;21&gt;7985, Jul. 2021.
- [23] Y. Lu, Q. Wu, Q. Wang, D. Liu, and L. Xiao, ''Analysis of a novel zero-voltage-switching bidirectional DC/DC converter for energy storage system,'' IEEE Trans. Power Electron. , vol. 33, no. 4, pp. 3169GLYPH&lt;21&gt;3179, Apr. 2018.

<!-- image -->

YU-EN WU (Member, IEEE) was born in Chiayi, Taiwan, in 1964. He received the B.S. degree in electrical engineering from the Taiwan Institute of Technology, Taipei, Taiwan, in 1989, the M.S. degree in electrical engineering from Sun Yat-Sen University, Kaohsiung, Taiwan, in 1992, and the Ph.D. degree in electrical engineering from National Chung Cheng University, Chiayi, in 2005.

From 1992 to 2005, he was a Lecturer and an

Associate Professor at the Department of Electronic Engineering, Wu Feng Institute of Technology, Chia-Yi, Taiwan. He is currently a Professor with the Department of Electronic Engineering, National Kaohsiung University of Science and Technology. His research interests include bidirectional DC-DC converter and implementation of multi-inverter systems, power electronics, dsp based application systems, smart grid and renewable energy systems.

<!-- image -->

BO-HAU PAN was born in Taipei, Taiwan, in 1996. He received the B.S. degree in microelectronics engineering and the M.S. degree in electrical engineering from the National Kaohsiung University of Science and Technology, Kaohsiung, Taiwan, in 2019 and 2021, respectively. His research interests include renewable energy sources and power electronics.