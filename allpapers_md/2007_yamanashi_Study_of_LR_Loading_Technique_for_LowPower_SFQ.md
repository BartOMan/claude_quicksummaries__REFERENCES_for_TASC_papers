## Study of LR-Loading Technique for Low-Power Single Flux Quantum Circuits

Yuki Yamanashi, Takanobu Nishigai, and Nobuyuki Yoshikawa

AbstractA single-flux-quantum (SFQ) circuit is thought to be very suitable as a peripheral circuit for superconducting quantum bits (qubits), which can manipulate and detect the qubit state at a temperature state similar to qubits. Even though the power consumption of SFQ circuits is extremely small, it is still sufficient to heat the substrate at a temperature below 1 K. We have investigated and demonstrated low-power SFQ circuits for this application, using the LR-loading technique, which can reduce the static power consumption of the SFQ circuits. Simulation results show that the ratio of the switching speed to the time constant of the bias circuit is important for the stable operation of low-power SFQ circuits. The static power consumption of SFQ circuits can be reduced to the same order as the dynamic power consumption through optimization of the circuit parameters. We have designed and tested a low-power SFQ clock generator using the LR-loading technique and confirmed its stable operation at 4.2 K, where the power consumption is reduced by 93% compared with ordinary biased circuits.

Index TermsJosephson logic, quantum bit, SFQ circuit, superconducting devices, superconducting integrated circuits.

## I. INTRODUCTION

A QUANTUM computer can perform tasks far more efficiently than classical computers by using the quantum states of quantum bits (qubits). Superconducting qubits, which utilize macroscopic quantum effects in superconductors, are very promising candidates for practical qubit applications, because they are solid-state devices and can be easily integrated using conventional fabrication processes [1], [2].

To realize a quantum computer composed of a large number of qubits, high-speed manipulation and highly accurate detection of the qubit states is required. For superconducting qubits, a single flux quantum (SFQ) circuit [3] is attractive for that purpose, because of its excellent ability in terms of speed, power and sensitivity. Compatibility of the materials and operating temperature is also an advantage. To date, several methods for the manipulation and detection of the superconducting qubits states using SFQ circuits have been proposed and demonstrated [4]-[6]. These methods are useful for the scaling up of quantum computers, because the direct connection between qubits and room-temperature electronics can be reduced considerably, resulting in the decrease of thermal noise and heat flow from the room temperature environment.

Manuscript received August 29, 2006. This work was supported by CREST, Japan Science and Technology Agency.

The authors are with theDepartment of Electrical and Computer Engineering, Yokohama National University, Yokohama 240-8501 Japan (e-mail: yamanasi@yoshilab.dnj.ynu.ac.jp).

Digital Object Identifier 10.1109/TASC.2007.898608

Even though the power consumption of SFQ circuits is very small compared with semiconductor circuits, it is still quite large for the qubit application to prevent thermal influence to the qubits and maintain a sufficiently low operating temperature. In this study, we have investigated a method to decrease the static power consumption of the SFQ circuits using a LR-loading technique.

## II. LR-LOADING TECHNIQUE

Power consumption of SFQ circuits is divided into static and dynamic parts. Dynamic power consumption arises from the switching event at the Josephson junction itself. The at a junction is denoted as PD PD

<!-- formula-not-decoded -->

where is the quantum flux , and and are the critical current and switching frequency of the Josephson junction, respectively. Dynamic power consumption is essential for circuit operation and cannot be reduced without reducing the circuit performance. Typical parameter conditions used for the qubit application were as follows: and , so that can be obtained. Static power consumption is caused by on-chip bias resistors, which supply a constant bias current to the circuit. The at a bias circuit is given by Φo 二

<!-- formula-not-decoded -->

where and are the bias current and voltage of the bias circuit, respectively. If we assume and , we obtain , where is the shunt resistance of the junction. is typically two orders of magnitude larger than . Therefore, a reduction of the static power consumption of the SFQ circuits to the same level as the dynamic power consumption is a reasonable goal for the low-power SFQ circuit design.

Fig. 1 shows a schematic of an equivalent circuit of a Josephson transmission line (JTL) from our cell library [7] for operation at 4.2 K. The bias current is supplied to the junction by an off-chip bias voltage and an on-chip bias resistor . The bias voltage is 2.5 mV, which is selected as much larger than the amplitude of the voltage pulse at the junction, in order to supply a constant current to the circuit. The simple reduction of the bias resistance reduces the static power consumption at the bias resistor. However, it results in the impulsive decrease of the bias current and causes deterioration of the circuit operation and the interaction between circuits. Vb

and

Fig. 1. Schematic of an equivalent circuit for a JTL with a conventional bias circuit.

<!-- image -->

Fig. 2. Schematic of an equivalent circuit for a LR-loaded JTL. A large inductance /76 is inserted to the bias circuit.

<!-- image -->

For stable operation of low-power SFQ circuits, we have investigated the LR-loading technique [8]. Fig. 2 shows a circuit schematic of a LR-loaded JTL. In this circuit, a large inductance is inserted in the bias circuit to prevent the impulsive decrease of the bias current. The bias current is determined by , and the static power consumption is given by , which scales down with the decrease in when is constant. Rb

In the LR-loaded SFQ circuits, the time constant of the bias circuit must satisfy the following relationship,

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where is the SFQ pulse width, which has a typical value of 2 ps for a 2.5 Nb process, and is the clock period. Equation (3) is the condition to avoid the impulsive decrease of the bias current during the switching event at the junction. Equation (4) ensures the average bias current for the circuit when the SFQ pulses propagate the junction at high frequency. 2

In addition, the bias inductance must be much larger than the circuit inductance , so that the SFQ pulses will not escape to the bias circuit, Lb

<!-- formula-not-decoded -->

Fig. 3. Block diagram of the simulated circuit.

<!-- image -->

Fig. 4. The dependence of the propagation delay for a 100-stage LR-loaded JTL with various values of the bias resistance /82 . /73 /61 /73 /61 /50/49/54 /22 /65 , /73 /61 /51/48/48 /22 /65 , /76 /61 /52 /58 /56 /112/72 in Fig. 2. The SRL 2.5 /107/65 /61 /99/109 Nb standard process is assumed.

<!-- image -->

## III. OPTIMIZATION OF CIRCUIT PARAMETERS

Equations (3) and (4) provides the parameter conditions for the time constant of the bias circuits, which is for the and 2.5 Nb process. In this section we will investigate the dependence of the circuit operation properties on the time constant using circuit simulations. Fig. 3 shows a block diagram of a simulated circuit, which is composed of a 100-stage LR-loaded JTL. In the simulation, two SFQ pulses with 100 ps time intervals are input to the JTL array, and the propagation delay and the change of the time interval between two SFQ pulses have been calculated. &gt;L&gt;S 100 ps

Fig. 4 shows the dependence of the propagation delay on the time constant for various values of . Note that the for the conventional JTL from our cell library is 8.35 . It can be seen that the propagation delay steeply increases when the time constant approaches the pulse width . This is because the impulsive decrease of the bias current deteriorates the circuit operation. It can also be seen that the increase in the propagation delay is larger for a smaller , because the condition of (5) is not satisfied for a smaller .

Fig. 5 shows the dependence of the time interval on the time constant for various value of . The time interval between two SFQ pulses increases after the propagation through the LR-loaded JTL array when the time constant approaches the initial time interval . This increase in the time interval is due to the reduction in the bias current for the second SFQ pulse. Because it takes time for the bias current to return to the initial condition after junction switching, the second SFQ △T 100

Fig. 5. The dependence of the time interval /1 /84 between two SFQ pulses on the time constant /28 for the various value of /82 after propagating a 100-stage LR-biased JTL. The initial time interval is /1 /84 /61 /49/48/48 /112/115 . The used circuit parameters are same to those of Fig. 4.

<!-- image -->

pulse has a smaller bias current when is large. These tendencies become remarkable when the bias resistance is small. T Rb

It should be noted here that further reduction of the power consumption is possible by reducing the critical current of the junction. If the critical current of each junction is reduced, the inductances and have to be increased to keep the product constant and from the (5). The bias resistor also has to be increased to keep constant from the (3) and (4). As a result, the static power consumption is decreased in proportion to . L T

## IV. DEMONSTRATION OF LR-LOADED SFQ CIRCUITS

We have designed several basic cells using the LR-loading technique. Fig. 6 shows a mask layout of the LR-loaded JTL cell. It should be noted that a low-power SFQ circuit is implemented only by modifying the bias circuit of existing cells from our cell library for 4.2 K operation. Therefore the critical current of the Josephson junction, which is approximately 200 in the JTL, is not reduced in this study. According to the simulation results from the preceding section, all cells are designed so that the time constants of the bias circuits become 40 ps, when a 20% increase in the propagation delay is allowed at 10 GHz operation. Table I lists the simulated and measured DC bias margins for several basic cells, where the simulation results assume 10 GHz operation, whereas the experimental results were obtained using low-speed tests. It can be seen that all cells have DC bias margins larger than 20%, which is large enough for the circuit application.

To evaluate the stability of low-power SFQ circuits, the error rate of a low-power SFQ clock generator was measured. Fig. 7 shows a block diagram of the SFQ clock generator investigated. The system is composed of a ring-oscillator type clock generator with a SFQ pulse counter, which generates high-frequency SFQ pulses [3], [10]. The frequency of the output SFQ pulse train is 14.6 GHz at the designed bias point. The clock generator contains 242 Josephson junctions and the power consumption is estimated to be 4.3 . Note that the power consumption of the 28

Fig. 6. Mask layout for a LR-loaded JTL cell. The circuit is designed using the SRL 2.5 /107/65 /61 /99/109 Nb standard process [9]. The time constant for the bias circuit /40 /28 /61 /76 /61/82 /41 is designed to be 40 ps. /82 /61 /48 /58 /54 /10 , and /76 is 24 pH.

<!-- image -->

Fig. 7. Block diagram of a low-power clock generator with a pulse counter. RTFF denotes a resettable T flip-flop.

| Cell Name   | DC Bias Margins at 10 GHz by simulations   | DC Bias Margins by low-speed measurements   |
|-------------|--------------------------------------------|---------------------------------------------|
| JTL         | -30 to +45%                                | -65 to +41 %                                |
| DFF         | -27 to +45 %                               | -44 to +38 %                                |
| RTFF        | -27 to +39 %                               | -26 to +25%                                 |
| NDRO        | -10 to +27 %                               | -22 to +21%                                 |

TABLE I DC BIAS MARGINS OF BASIC CELLS USING THE LR-LOADING TECHNIQUE

<!-- image -->

same clock generator using the conventional biasing technique is 61.1 .

In order to measure the error rate of the clock generator, the number of output SFQ pulses was counted by another SFQ pulse counter designed using a conventional biasing technique. The -pulse generation and error check were repeated many times and the bit error rate of the clock generator was estimated [10]. Fig. 8 shows the bit-error-rate of the low-power clock generator as a function of the bias current at 4.2 K. No error is observed at the optimum biasing point, which corresponds to a bit error rate less than . The test result indicates that the low-power SFQ

Fig. 8. Bit-error-rate for a SFQ pulse generator with control circuits as a function of the DC bias current. Fitting curves are obtained using the error function [11]. The DC bias current is normalized by the design value.

<!-- image -->

circuit has stable operation, although the power consumption is reduced by 93% compared with that of ordinary biased circuits.

## V. CONCLUSION

We have investigated and demonstrated low-power SFQ circuits using the LR-loading technique, which reduces the static power consumption of SFQ circuits. Simulation results indicate that the relation of time scales, that is, the pulse width, the operating frequency, and the time constant of the bias circuit, are very important for stable operation of the circuit. Based on the simulation results, we have implemented several basic cells using the LR-loading technique, and have experimentally shown their large DC bias margins. The power consumption of the cells is reduced by 93% compared with conventional SFQ cells. Further reduction of the power consumption is possible by reducing the critical current of the junction for low-power operation. The bit-error-rate of the low-power clock generator was also measured, and was lower than . This technique reduces the static power consumption of SFQ circuits to the same level as the dynamic power consumption and enabled the implementation of large-scale SFQ circuit system into a dilution refrigerator for control of superconducting quantum bits.

## REFERENCES

- [1] Y. Nakamura, Y. A. Pashkin, and J. S. Tsai, 'Coherent control of macroscopic quantum states in a single-Cooper-pair box,' Nature , vol. 398, pp. 789-788, Apr. 1999.
- [2] I. Chiorescu, Y. Nakamura, C. J. P. M. Harmans, and J. E. Mooij, 'Coherent quantum dynamics of a superconducting flux qubit,' Science , vol. 299, pp. 1869-1872, Mar. 2003.
- [3] K. K. Likharev and V. K. Semenov, 'RSFQ logic/memory family: A new Josephson-junction technology for sub-terahertz-clock-frequency digital systems,' IEEE Trans. Appl. Supercond. , vol. 1, pp. 3-28, Mar. 1991.
- [4] R. C. Rey-de-Castro, M. F. Bocko, A. M. Herr, C. A. Mancini, and M. J. Feldman, 'Design of an RSFQ control circuit to observe MQC on an rf-SQUID,' IEEE Trans. Appl. Supercond. , vol. 11, pp. 1014-1017, Mar. 2001.
- [5] V. K. Semenov and D. V. Averin, 'SFQ control circuits for Josephson junction qubits,' IEEE Trans. Appl. Supercond. , vol. 13, pp. 960-965, Jun. 2003.
- [6] Y. Yamanashi, M. Ito, A. Tagami, and N. Yoshikawa, 'Observation of quantized energy levels in a Josephson junction using SFQ circuits,' IEEE Trans. Appl. Supercond. , vol. 15, pp. 864-867, Jun. 2005.
- [7] S. Yorozu, Y. Kameda, H. Terai, A. Fujimaki, T. Yamada, and S. Tahara, 'A single flux quantum standard logic cell library,' Physica C , vol. 378-381, pp. 1471-1474, Sep. 2002.
- [8] N. Yoshikawa and Y. Kato, 'Reduction of power consumption of RSFQ circuits by inductance-load biasing,' Supercond. Sci. Technol. , vol. 12, pp. 918-920, Nov. 1999.
- [9] S. Nagasawa, Y. Hashimoto, H. Numata, and S. Tahara, 'A 380 ps. 9.5 mWJosephson 4-kbit RAM operated at a high bit yield,' IEEE Trans. Appl. Supercond. , vol. 5, pp. 2447-2452, Jan. 1995.
- [10] M.Ito, N. Nakajima, K. Fujiwara, N. Yoshikawa, A. Fujimaki, H. Terai, and S. Yorozu, 'Design and implementation of SFQ programmable clock generators,' Physica C , vol. 412-414, pp. 1550-1554, Jun. 2004.
- [11] Q. P. Herr, M. W. Johnson, and M. J. Feldman, 'Temperature-dependent bit-error rate of a clocked superconducting digital circuit,' IEEE Trans. Appl. Supercond. , vol. 9, pp. 3594-3597, Jun. 1999.