## Superconductor Logic Implementation with All-JJ Inductor-Free Cell Library

Haolin Cong, Sasan Razmkhah, Mustafa Altay Karamuftuoglu, Massoud Pedram

Abstract -Single flux quantum (SFQ) technology has garnered significant attention due to its low switching power and high operational speed. Researchers have been actively pursuing more advanced devices and technologies to further reduce the reliance on inductors, bias, and dynamic power. Recently, innovative magnetic Josephson junction devices have emerged, enhancing the field of superconductor electronics (SCE) logic. This paper introduces a novel cell library design that relies entirely on Josephson junctions (JJs), showing promising potential for eliminating the need for inductors in conventional SFQ cells. This results in a 55% reduction in cell size and an 80% decrease in both static and dynamic power consumption. The proposed library implements a half flux quantum (HFQ) logic, where each pulse duration is half that of a single flux quantum pulse. The paper presents the schematics of the basic cells, emphasizing critical circuit parameters and their margins. Additionally, it examines layout blueprints, showcasing the advantageous areasaving characteristics of the proposed design.

Index Terms -Superconductor Electronics, Single Flux Quantum, Half Flux Quantum, All-JJ

## I. INTRODUCTION

S INGLE flux quantum (SFQ) technology [1] holds great potential for advancing the next generation of VLSI (largescale integration) circuits. Among SFQ logic circuits, the Rapid SFQ (RSFQ) logic family stands out, offering extremely high operational speeds. RSFQ utilizes Josephson Junctions (JJs), known for their ultra-fast picosecond (ps) switching times. RSFQ logic cells exhibit swift responses with a clockto-output delay of 10ps , enabling RSFQ systems to excel in the 40GHz to 60GHz range [2]-[4]. Josephson Junctions require significantly less energy to switch than CMOS technology, potentially as low as 10 -19 J / bit . This efficiency sets RSFQ systems apart as more power-efficient alternatives. The RSFQ domain has garnered substantial attention, with studies covering circuit and system designs [5]-[7], innovative layout designs [8], [9], and notable progress in electronic design automation (EDA) tools and algorithms [10], [11].

Despite the numerous advantages offered by RSFQ circuits, they are confronted with significant challenges. RSFQ circuit integration density remains relatively low, accommodating only around 10,000 logic gates within a 1cm 2 chip area. This limitation is the key limiting factor to meet the logic circuit requirements of various applications. Additionally, RSFQ circuits lack dense on-chip memory and require substantial bias currents for their operation. Given these obstacles, it becomes

H. Cong, S. Razmkhah and M. Pedram are with the Department of Electrical and Computer Engineering, University of Southern California, Los Angeles, CA 90007 USA (e-mail: haolinco@usc.edu; razmkhah@usc.edu; karamuft@usc.edu; pedram@usc.edu)

imperative to explore alternative logic circuit families capable of overcoming these challenges and driving the advancement of SFQ technology.

At the core of superconductor circuits lies the JJ. Serving as the active component in an SFQ circuit, the JJ adopts the standardized Superconductor-Insulator-Superconductor (SIS) configuration. The dynamic behavior of a JJ is encapsulated by the current-phase relation (CPR), which relies on parameters such as the current density ( J s ), the critical current density ( J C ) at which the JJ exits the superconducting state, and the phase difference ( ϕ ) spanning two superconducting layers. This simplified CPR equation assumes a consistent supercurrent tunneling through the JJ's barrier while maintaining temperatures well below the critical threshold. Importantly, this equation accurately approximates the behavior of the SIS JJs and serves as the cornerstone for most SPICE-based simulation engines.

The MITLL SFQ5ee process [12], [13] is an exemplary technology that employs a Nb/Al -AlO x /Nb type junctions, with the superconducting layers composed of Nb and the insulator being AlO x . By replacing the insulator layer with a magnetic material featuring a built-in magnetic field, the SIS JJ transforms into a magnetic junction (MJJ) [14], [15]. The MJJ has been extensively studied for its unique properties, giving rise to innovative devices like the π -junction ( π -JJ), ϕ -junction ( ϕ -JJ), and 2 ϕ -junction ( 2 ϕ -JJ), which have piqued the interest of researchers.

Researchers are actively pursuing the development of faster, more efficient, and compact technology. However, reducing the size of inductors in SFQ circuits poses an important challenge due to increasing mutual inductance and cross-talk in SFQ circuit layouts, limiting further reductions in the width and spacing of metal lines. While the kinetic inductor offers a potential solution, it has its own challenges. Addressing this issue, the work outlined in [16] attempts to eliminate the need for inductors and enhance SFQ circuit scalability by utilizing logic cells (such as AND and OR gates, Not and XOR gates, non-destructive readout D-flipflops) with 2 ϕ -junctions. Simultaneously, efforts are underway to leverage the 2 ϕ -junction to minimize dynamic power consumption in SFQ systems, as explored in [17]. This study introduced three novel cells incorporating the 2 ϕ -junction: a Josephson transmission line (JTL), an inverter, and an OR gate. Compared to conventional RSFQ cells, these cells utilize half flux quantum (HFQ) pulses, resulting in reduced latency and switching power. However, it is important to note that this study lacks detailed circuit parameters, and the three cells do not constitute a complete standard cell library to meet fundamental functional

1

requirements. In another study, an interface is introduced to bridge SFQ circuits and HFQ circuits [18].

This paper introduces a comprehensive standard cell library based on 2 ϕ -junction technology, encompassing four essential logic cells (inverter, AND gate, OR gate, and XOR gate), five transmission blocks (Josephson transmission line (JTL), splitter, merger, passive transmission line (PTL) transmitter and receiver), one storage cell (DFF), and two I/O interface blocks (DC/SFQ and SFQ/DC converters.) This library caters to the fundamental requirements of a general-use system.

We validate the functionality of each cell using the JoSIM simulator [19]. Furthermore, we optimize the circuits using qCS [20], achieving commendable margins. Critical circuit parameters and their margins are meticulously presented, along with projected layout areas for the cells using the MITLL SFQ5ee process. Notably, a simulated 2 ϕ -junction device is included. In Section III, we delve into the design intricacies of each cell within the library, concluding with a summary. Additionally, this section outlines the methodology employed for estimating layouts and offers a comparative analysis with a conventional RSFQ cell library. Lastly, Section V provides a concluding perspective for this paper.

## II. 2 ϕ -JUNCTION

Recent research has revealed intriguing phenomena at the 0 -π transition, where the fundamental sinusoidal term of the current-phase relation (CPR) vanishes, rendering highorder harmonic terms significant [21]. In a study by [22], a single superconductor-ferromagnet-superconductor (SFS) junction employing a Cu 47 Ni 53 alloy barrier is realized with two parallel superconducting inductors: a readout inductor and a small shunt inductor. The readout inductor couples with a commercial DC superconducting quantum interference device (SQUID) sensor, detecting flux Φ within the readout loop.

Through measurements of the CPR across various barrier thicknesses and temperatures, reference [22] establishes a π -periodic behavior, putting to rest alternative explanations except for a second-order CPR. Consequently, the CPR is redefined as follows:

<!-- formula-not-decoded -->

This gives rise to a new device known as the 2 ϕ -JJ, characterized by the CPR:

<!-- formula-not-decoded -->

The 2 ϕ -JJ possesses intriguing properties: it features a currentphase relation with a period of π rather than 2 π , undergoes switching with a π phase jump, and produces a half flux quantum ( 1 2 Φ 0 = 1 . 03 × 10 -15 Wb ) accompanied by a π phase shift for each switching event [17]. These characteristics have fueled additional research into the utilization of 2 ϕ junctions.

## III. LOGIC CELL IMPLEMENTATION WITH 2 ϕ -JJS

In the 2 ϕ -JJ based design, most cells adhere to the conventional RSFQ cell structures, except inductors, which are replaced by normal JJs (0-JJs.) The 2 ϕ -JJ serves as the switching component. Consequently, a logic '1' for this logic family is represented by a half flux quantum pulse, with the voltage · time product being half that of a full flux quantum ( 1 2 Φ 0 = 1 . 03 × 10 -15 Wb .) This modification eliminates the need for inductors in the cell design, thereby avoiding the disadvantages and inconveniences associated with large inductances in RSFQ logic circuits.

Although the designed inductors are eliminated, parasitic inductors unavoidably exist in every connection. Therefore, an intrinsic 0 . 5 pH inductance is assumed for each connection during the design process. According to simulations, the tolerance to parasitic inductance exceeds 100% ( 0 pH to &gt; 1 pH .) Note that all parasitic inductances are omitted in the following schematics to improve the clarity of the figures.

To confirm the behavior of the JJ models, we simulate the I-V characteristic of the 0, π , and 2 ϕ JJs [23] and compare them in Fig.1. The difference between 0-JJ and 2 ϕ -JJ is in the switching behavior. Each junction switches when the voltagetime integration exceeds the flux quantum requirement. The 2 ϕ -JJ switches twice when the 0-JJ switches once while receiving an equivalent amount of flux quantum. The area under the voltage-time graph of a 0-JJ pulse is always ϕ 0 whereas 2 ϕ -JJs create a pulse with half that value.

Fig. 1: Simulation I-V of 0, π and 2 ϕ JJs.

<!-- image -->

In the following sections, we will explore the specifics of each cell, presenting schematic diagrams accompanied by a table listing parameter values and associated cell margins. Additionally, we will provide simulation waveforms to demonstrate the correct functionality of each cell. Preliminary layouts have been generated for these cells to assess potential area savings. However, it's essential to note that, at present, no existing technology offers the 2 ϕ -JJ in a fabrication stack-up. Consequently, these layouts cannot be fabricated in any facility known to the authors. For our layout design, we employed the MITLL SFQ5ee process parameters with a simulated 2 ϕ -JJ device. To maintain clarity and minimize redundancy, we will only present an example layout of the OR gate in the summary section, providing readers with a preliminary physical view of the cell layouts.

## A. Wiring cells

1) Josephson Transmission Line (TP-JTL): Fig.2 illustrates the schematic of a JTL block. Within this schematic, devices denoted by square boxes (J1 and J3) represent the 2 ϕ -JJs, while those without boxes are 0-JJs (J2 and J4.) Notably, the structure is duplicated, meaning that J1/J3, J2/J4, and I1/I2

Fig. 2: Schematic of the Josephson Transmission Line (JTL).

<!-- image -->

Fig. 3: Simulation waveform of the Josephson Transmission Line (JTL) with added noise.

<!-- image -->

TABLE I: Parameter values and margins of JTL

| Components   | Values   | Margins   |
|--------------|----------|-----------|
| J1,J3        | 70 µA    | 71%       |
| J2,J4        | 80 µA    | 97%       |
| I1,I2        | 45 µA    | 88%       |
| Bias         | 1 mV     | 88%       |

<!-- image -->

Fig. 4: Schematic of the splitter cell.

<!-- image -->

Time (ps)

Fig. 5: Simulation waveform of the splitter cell with added noise.

TABLE II: Parameter values and margins of splitter cell

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1           | 65 µA    | 98%       | I1           | 70 µA    | 100%      |
| J2,J3        | 73 µA    | 99%       | I2,I3        | 45 µA    | 70%       |
| J4,J5        | 80 µA    | 88%       | Bias         | 1 mV     | 88%       |
| J6,J7        | 80 µA    | 90%       |              |          |           |

are identical. This design ensures the JTL cell's repeatability, allowing for the creation of a JTL chain by connecting the OUT port to a subsequent JTL IN port without introducing unnecessary components.

Fig. 6: Schematic of the merger cell.

<!-- image -->

Fig. 7: Simulation waveform of the merger cell with added noise.

<!-- image -->

TABLE III: Parameter values and margins of merger cell

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1,J4        | 83 µA    | 75%       | J8           | 93 µA    | 82%       |
| J2,J5        | 151 µA   | 100%      | I1,I2        | 27 µA    | 100%      |
| J3,J6        | 62 µA    | 91%       | I3           | 120 µA   | 81%       |
| J7           | 40 µA    | 100%      | Bias         | 1 mV     | 72%       |

As depicted, J1 replaces the inductor that is present in the previous RSFQ JTL, forming a J1-J2-J3 loop that establishes a phase equation. This equation ensures that the integration of the phase difference, starting from the positive terminal of J1 through J2, FJ3, and back to J1, amounts to an integer multiple of 2 π . When a half-flux-quantum (HFQ) pulse arrives from the IN port, J1 switches and generates another HFQ pulse, which then propagates to the next device. This mechanism facilitates the transmission of the HFQ pulse along the JTL. The simulation waveform is depicted in Fig.3, and the component values can be found in Table I. Notably, the critical margin for JTL is 71% dictated by J1/J3.

- 2) SPLITTER: Similar to SFQ cells, HFQ logic cells have a fan-out of one. Therefore, a splitter is employed to duplicate the pulse. Fig.4 presents the schematic of the splitter cell. In this arrangement, J1 receives the pulse from the IN port, and the looping current is divided into two branches. This division triggers J5 and J4 separately, generating an HFQ pulse at each output port. The simulation waveform is displayed in Fig.5, and the component values can be found in Table II. Notably, the critical margin for the splitter is 70% dictated by the current bias I2/I3.
- 3) MERGER: Fig. 6 illustrates the schematic of the merger cell, often referred to as a confluence buffer. When it receives an HFQ pulse from either input port (e.g., IN1), the pulse triggers the corresponding junction (J1). This action increases

Fig. 8: Schematic of the D Flip-flop.

<!-- image -->

Fig. 9: Simulation waveform of the D Flip-flop with added noise.

<!-- image -->

TABLE IV: Parameter values and margins of DFF

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1           | 63 µA    | 68%       | J5           | 117 µA   | 97%       |
| J2           | 65 µA    | 90%       | I1           | 31 µA    | 100%      |
| J3           | 86 µA    | 75%       | I2           | 32 µA    | 100%      |
| J4           | 74 µA    | 85%       | Bias         | 1 mV     | 88%       |

the current in the respective branch (J1-J2-J3-J7), leading to the switching of J7, resulting in an output pulse. Concurrently, a buffering junction on the other branch (in this case, J6 for input from IN1) is triggered to counteract the backward flux flow towards the other input port (IN2). Specifically, J3 and J6 serve as barriers to prevent the reverse propagation of pulses. In the event that two input pulses arrive simultaneously or within a small time window (several picoseconds), only one output pulse is generated at the OUT port. The simulation waveform is depicted in Fig. 7, illustrating both the input and output waveforms and the phases of J3 and J6 to demonstrate how they inhibit backpropagation. Detailed component values can be found in Table III. It's worth noting that the critical margin for the merger is 72%, determined by the overall bias voltage.

## B. Memory cells

1) D FLIP-FLOP: Fig.8 illustrates the schematic of the DFF (Data Flip-Flop.) When an HFQ pulse arrives from the input port D, it is stored within the J1-J2-J3 loop as a clockwise looping current. This action increases the bias current of J3. Consequently, when an HFQ pulse arrives from the CLK port, it triggers J3, generating an HFQ pulse at the output port Q. In cases where no HFQ is stored, the incoming pulse from CLK triggers the J4 junction, resulting in no output at Q. The simulation waveform is displayed in Fig.9, and the component values are detailed in Table.IV. Notably, the critical margin for the DFF is 68% dictated by J1.

Fig. 10: Schematic of the 2 ϕ -based NDRO memory cell.

<!-- image -->

Fig. 11: Simulation waveform of the NDRO cell with added noise.

<!-- image -->

TABLE V: Parameter values and margins of NDRO cell

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1           | 75 µA    | 100%      | J7           | 58 µA    | 100%      |
| J2,          | 63 µA    | 58%       | J8           | 48 µA    | 70%       |
| J3,          | 44 µA    | 94%       | J9           | 107 µA   | 76%       |
| J4           | 139 µA   | 94%       | I1           | 236 µA   | 100%      |
| J5           | 88 µA    | 57%       | I2           | 123 µA   | 70%       |
| J6           | 56 µA    | 97%       | I3           | 128 µA   | 75%       |

2) NDRO: Non-destructive memory cells are widely used as a memory unit in SFQ circuits. The DFF cell is a traditional Destructive Read-Out (DRO) unit that stores a single bit of information. Its core architecture is a simple storage loop that stores flux from input and releases it to output by a clock signal. In contrast to the DRO, NDRO does not release the pulse by the clock signal and requires a reset pin to clear the stored value within its storage loop. Fig.10 shows the structure of the NDRO cell. The NDRO design values are shown in Table.V. The simulation waveform can be observed in Fig.11.

## C. Logic cells

- 1) TP-OR: To grasp the concept of the OR gate's operation, consider it as two DFFs driven by the same clock and followed by a merger, as depicted in Fig.12. The DFF cell has already been discussed, rendering it unnecessary to reiterate its details. The subsequent merging section possesses the same structure as the previously introduced merger. However, there are slight differences in component values as the tool automatically optimizes them. These optimized values are displayed in Table.VI, with the critical margin being 40% dictated by J1/J4. The simulation waveform can be observed in Fig.13.

2) TP-AND: As depicted in Fig.14, the AND gate adopts an identical structure to the OR gate. However, it manipulates the key components, specifically the merging part, to ensure that the output junction J7 necessitates at least two HFQ

Fig. 12: Schematic of the OR gate.

<!-- image -->

Fig. 13: Simulation waveform of the OR gate.

<!-- image -->

TABLE VI: Parameter values and margins of OR gate

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1,J4        | 95 µA    | 40%       | J8           | 74 µA    | 69%       |
| J2,J5        | 100 µA   | 67%       | I1,I2        | 25 µA    | 93%       |
| J3,J6        | 83 µA    | 37%       | I3           | 83 µA    | 99%       |
| J7           | 68 µA    | 73%       | Bias         | 1 mV     | 44%       |

<!-- image -->

Fig. 14: Schematic of the AND gate.

<!-- image -->

Time (ps)

Fig. 15: Simulation waveform of the AND gate.

TABLE VII: Parameter values and margins of AND gate

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1,J4        | 70 µA    | 97%       | J8           | 74 µA    | 85%       |
| J2,J5        | 140 µA   | 99%       | I1,I2        | 31 µA    | 100%      |
| J3,J6        | 72 µA    | 94%       | I3           | 32 µA    | 100%      |
| J7           | 99 µA    | 98%       | Bias         | 1 mV     | 92%       |

<!-- image -->

Fig. 16: Schematic of the XOR gate.

<!-- image -->

Time (ps)

Fig. 17: Simulation waveform of the XOR gate.

TABLE VIII: Parameter values and margins of XOR gate

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1,J4        | 87 µA    | 46%       | J9           | 80 µA    | 89%       |
| J2,J5        | 95 µA    | 75%       | I1,I2        | 31 µA    | 79%       |
| J3,J6        | 72 µA    | 40%       | I3           | 63 µA    | 88%       |
| J7           | 70 µA    | 20%       | I4           | 39 µA    | 39%       |
| J8           | 72 µA    | 22%       | Bias         | 1 mV     | 26%       |

pulses to generate an output pulse. The simulation waveform is illustrated in Fig.15, and the component values are provided in Table.VII. Notably, the critical margin for the merger is 85%, dictated by J8.

3) TP-XOR: The schematic of the XOR gate is illustrated in Fig.16. In contrast to the AND or OR gate, there is an additional junction (J7) after the merging point of the two input branches. With J7 in place, when pulses arrive from both branches (corresponding to the case: A=1 and B=1), J7 switches, while J8 remains inactive, resulting in no output pulse. Conversely, in situations where only one pulse is received from either of the branches (corresponding to the cases: A=1, B=0, or A=0, B=1), J8 is triggered, producing the output pulse. The simulation waveform is visualized in Fig.17, and the component values can be found in Table.VIII. Notably, the critical margin for the merger is 20%, dictated by J7.

4) TP-INV: Fig.18 displays the schematic of an inverter. The upper section of the cell has a splitter-like structure, but one branch is merged with the clock branch of a DFF-like structure at the bottom. Consequently, when the clock signal arrives, the first part of the inverter generates '11' or '10' based on whether an input pulse was stored. Subsequently, the following XOR-like structure completes the inversion operation. The simulation waveform is depicted in Fig.19, and the component values are provided in Table.IX. Notably, the critical margin for the merger is 16%, dictated by J14 and J15.

Fig. 18: Schematic of the inverter.

<!-- image -->

Fig. 19: Simulation waveform of the inverter.

<!-- image -->

TABLE IX: Parameter values and margins of the inverter

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1           | 85 µA    | 43%       | J2           | 77 µA    | 69%       |
| J3           | 95 µA    | 52%       | J4           | 70 µA    | 48%       |
| J5           | 82 µA    | 62%       | J6           | 80 µA    | 81%       |
| J7           | 80 µA    | 61%       | J8,J11       | 96 µA    | 76%       |
| J9,J12       | 101 µA   | 85%       | J10,J13      | 78 µA    | 64%       |
| J14          | 80 µA    | 16%       | J15          | 82 µA    | 16%       |
| J16          | 90 µA    | 67%       | I1           | 43 µA    | 63%       |
| I2           | 40 µA    | 79%       | I3           | 57 µA    | 65%       |
| I4,I5        | 37 µA    | 79%       | I6           | 70 µA    | 73%       |
| I7           | 40 µA    | 36%       | Bias         | 1 mV     | 22%       |

## D. Interface cells

1) PTL Driver AND Receiver: Fig.20 presents the schematic for both the PTL transmitter/driver (TX) and receiver (RX). These structures have JTL-like designs, with the PTL driver featuring a serial resistor at the output port for impedance matching. In this configuration, the characteristic impedance is set to four ohms, although designers can select practical values for their technology and adjust circuit parameters accordingly. The simulation waveform is displayed in Fig.21, and the component values can be found in Table.VIII. It's worth noting that the critical margin for the PTL driver is 81%, dictated by J1, and the critical margin for the PTL receiver is 81%, dictated by J7.

2) DC/SFQ CONVERTER: Fig.22 is the DC/SFQ converter schematic. R1 is a serial input resistor which converts the input voltage to current. The resistor can be implemented onchip (this design) or off-chip. A large inductor L1 follows the input resistor. At the rising edge of the input, L1 reveals high impedance, and most of the current will flow through J2, which triggers an HFQ pulse at the output port. When the input voltage becomes steady, L1 is equivalent to a short connection, and the input current will flow through L1 to the ground, leaving J2 untouched. The simulation waveform is shown in

Fig. 20: Schematic of the PTL driver and receiver.

<!-- image -->

Fig. 21: Simulation waveform of the PTL driver and receiver.

<!-- image -->

TABLE X: Parameter values and margins of PTL driver and receive

| Components   | Values     | Margins         | Components        | Values                                   | Margins                 |
|--------------|------------|-----------------|-------------------|------------------------------------------|-------------------------|
| J1           | 80 µA      | 81% 84% 88% 94% | J5 J6 J7 J8 I3 I4 | 75 µA 61 µA 80 µA 80 µA 62 µA 45 µA 1 mV | 88% 87% 81% 84% 81% 88% |
| J2           | 80 µA      |                 |                   |                                          |                         |
| J3           | 70 µA      | 100%            |                   |                                          |                         |
| J4           | 83 µA      | 100%            |                   |                                          |                         |
| R1           | 0 . 5 ohms | 100%            |                   |                                          |                         |
| I1           | 45 µA      |                 |                   |                                          |                         |
| I1           | 49 µA      |                 | RX bias           |                                          | 88%                     |
| TX bias      | 1 mV       | 100%            |                   |                                          |                         |

<!-- image -->

Fig. 22: Schematic of the DC/SFQ converter.

Fig. 23: Simulation waveform of the DC/SFQ converter.

<!-- image -->

TABLE XI: Parameter values and margins of DC/SFQ converter

| Components   | Values                     | Margins            | Components   | Values              | Margins        |
|--------------|----------------------------|--------------------|--------------|---------------------|----------------|
| R1 J1 J2 J3  | 50 ohms 83 µA 71 µA 100 µA | 100% 98% 100% 100% | I1 L1 Bias   | 48 µA 6 . 7 pH 1 mV | 100% 100% 100% |

Fig.23, and the component values are listed in Table.XI. The critical margin of the PTL driver is 98% on J1.

3) SFQ/DC CONVERTER: Fig.24 shows the SFQ/DC converter schematic. When an input pulse comes, it breaks the

Fig. 24: Schematic of the SFQ/DC converter.

<!-- image -->

Fig. 25: Simulation waveform of the SFQ/DC converter. After passing through a low pass filter (LPF), the DC signal level shows around 100 µ V amplitude.

<!-- image -->

TABLE XII: Parameter values and margins of SFQ/DC converter

| Components   | Values   | Margins   | Components   | Values   | Margins   |
|--------------|----------|-----------|--------------|----------|-----------|
| J1           | 112 µA   | 91%       | J2           | 104 µA   | 100%      |
| J3           | 70 µA    | 100%      | J4           | 78 µA    | 100%      |
| J5           | 70 µA    | 97%       | J6           | 80 µA    | 100%      |
| J7           | 80 µA    | 100%      | J8           | 80 µA    | 100%      |
| L1           | 0 . 5 pH | 100%      | L2           | 3 pH     | 93%       |
| I1           | 45 µA    | 100%      | I2           | 26 µA    | 100%      |
| I3           | 48 µA    | 100%      | I4           | 22 µA    | 100%      |
| Rout         | 50 ohm   | 100%      | Bias         | 1 mV     | 87%       |

quiescent state of the cell and leads the output junction J5 to start oscillating. Another input pulse will then pull the cell back to its initial state. While in active mode, the SFQ/DC converter will keep pumping out current through the L1. The serial resistor R out forms a low pass filter with the off-chip wire inductance and the equivalent load of the oscilloscope, which is usually used to monitor the output of a chip. Fig.25 is the simulation waveform. The input signal is at the top. The middle plot is the observed voltage after L1, and the bottom is the signal at the oscilloscope. As we can see, the output state changes every time an input pulse comes. The component values are listed in Table.XII. The critical margin of the PTL driver is 87% on the overall bias voltage.

## IV. RESULTS AND IMPLEMENTATION

## A. Random Pattern Generator

A random pattern generator has been implemented to evaluate the library cells, as depicted in the schematic shown in Fig.26. Two DFF chains are formed, with signals tapped from various points in these chains using splitters. These signals are then directed to XOR gates. Subsequently, the outputs of the two XOR gates are combined with the initial signals, creating a feedback data loop. This configuration generates two random

Fig. 26: Schematic of the random pattern generator.

<!-- image -->

Fig. 27: Simulation waveform of the random pattern generator.

<!-- image -->

data series inputs to the subsequent stages: the AND gate, inverter, and OR gate. All cells in Fig.26 are synchronized with a clock signal, although the clock signal is not displayed to maintain diagram clarity and readability.

Fig.27 presents the simulation waveform of this microsystem. The top waveform represents the clock signal distributed to all the cells. 'Series 1' and 'Series 2' denote the bit series at the outputs of the two DFF chains, while 'OUT' signifies the output of the final OR gate. This microsystem effectively demonstrates the correct functionality of the employed cells and showcases the system integration capability of the halfflux quantum standard cells.

The above explanation described the HFQ standard cell library design utilizing the 2 ϕ -junction. Additionally, prototype layouts were created for each cell using a simulated technology based on the published MITLL SFQ5ee process. An extra layer, the 2 ϕ -junction layer, was assumed to enable the implementation of the 2 ϕ -junction. Fig.28 provides an illustration of the OR gate layout. The layout predominantly comprises four metal layers (M4 - M7), three metal vias, one resistor layer, two junction layers for 0-JJ and 2 ϕ -JJ respectively, one resistor contact layer, and one junction contact layer.

In Fig.28, it's evident that eliminating the inductor results in a more compact layout. Furthermore, as technology advances, the area could potentially be further reduced. Table.XIII provides a comprehensive list of all the cells implemented in this library, including the number of junctions (0-JJ and 2 ϕ -

TABLE XIII: Summary of the 2 ϕ -JJ based library cells

| Cell names       |   Number of JJs | Critical margins   | Areas     | Bias current   | Areas (RSFQ)   | Bias current (RSFQ)   |
|------------------|-----------------|--------------------|-----------|----------------|----------------|-----------------------|
| JTL              |               4 | 71%                | 225 um 2  | 90 µA          | 625 um 2       | 180 µA                |
| DFF              |               5 | 68%                | 375 um 2  | 63 µA          | 625 um 2       | 212 µA                |
| NDRO             |               9 | 55%                | 625 um 2  | 487 µA         | 2500 um 2      | 863 µA                |
| Merger           |               8 | 72%                | 550 um 2  | 174 µA         | 625 um 2       | 375 µA                |
| Splitter         |               7 | 70%                | 494 um 2  | 160 µA         | 625 um 2       | 309 µA                |
| OR               |              18 | 37%                | 1263 um 2 | 259 µA         | 2500 um 2      | 475 µA                |
| AND              |              18 | 85%                | 1263 um 2 | 220 µA         | 2500 um 2      | 530 µA                |
| XOR              |              19 | 20%                | 1428 um 2 | 290 µA         | 2500 um 2      | 435 µA                |
| PTL driver       |               4 | 81%                | 429 um 2  | 93 µA          | 625 um 2       | 265 µA                |
| PTL receiver     |               4 | 81%                | 369 um 2  | 107 µA         | 625 um 2       | 252 µA                |
| DC/SFQ converter |               3 | 98%                | 479 um 2  | 48 µA          | 1875 um 2      | 450 µA                |
| SFQ/DC converter |               8 | 87%                | 876 um 2  | 141 µA         | 3125 um 2      | 1025 µA               |

Fig. 28: An example layout of the OR gate.

<!-- image -->

JJ) and critical margins. It also compares estimated layout areas and bias current with a conventional RSFQ library we implemented. On average, the HFQ cells exhibit a 50.8% reduction in area and a 61% decrease in bias current compared to the conventional RSFQ library.

## V. CONCLUSION

An HFQ standard cell library employing the 2 ϕ -junction is demonstrated. The detailed design methodology encompasses schematic representations, component values, and their respective margins for each available block within the standard cell library. The library includes essential components such as inverters, AND, OR, XOR gates, JTLs, splitters, mergers, PTL drivers, PTL receivers, DFFs, DC/HFQ converters, and HFQ/DC converters. Compared to conventional RSFQ cells, this new design necessitates less bias current, reduces reliance on inductors, enhances stability and scalability, and occupies about 55% smaller area. These advancements position the HFQ logic family as a compelling contender for the next generation of VLSI circuits.

## ACKNOWLEDGMENT

This work was partly supported by the National Science Foundation (NSF) through the project Expedition: Discover (Design and Integration of Superconducting Computation for Ventures beyond Exascale Realization) under Grant 2124453.

## REFERENCES

- [1] K.K. Likharev, V.K. Semenov, 'RSFQ logic/memory family: a new Josephson-junction technology for sub-terahertz-clock-frequency digital systems', IEEE Transactions on Applied Superconductivity, Vol. 1 , Issue: 1 , March 1991
- [2] T. Kato et al., '60-GHz demonstration of an SFQ half-precision bitserial floating-point adder using 10 kA/cm2 Nb process,' 2013 IEEE 14th International Superconductive Electronics Conference (ISEC), 2013, pp. 1-3, doi: 10.1109/ISEC.2013.6604272.
- [3] I. Nagaoka, M. Tanaka, K. Inoue and A. Fujimaki, '29.3 A 48GHz 5.6mW Gate-Level-Pipelined Multiplier Using Single-Flux Quantum Logic,' 2019 IEEE International Solid State Circuits Conference - (ISSCC), 2019, pp. 460-462, doi: 10.1109/ISSCC.2019.8662351.
- [4] Razmkhah, Sasan and Febvre, Pascal, 'Superconducting Quantum Electronics,' in Beyond-CMOS, 2023, ch. 8, pp. 295-391, doi: 10.1002/9781394228713.ch8.
- [5] Y. Hironaka, T. Hosoya, Y. Yamanashi and N. Yoshikawa, 'Demonstration of Single-Flux-Quantum 64-B Lookup Table With Cryo-CMOS Decoders for Reconfiguration,' IEEE Transactions on Applied Superconductivity, vol. 32, no. 8, pp. 1-5, Nov. 2022, Art no. 1301305, doi: 10.1109/TASC.2022.3191984.
- [6] H. Cong, M. Li and M. Pedram, 'An 8-b Multiplier Using SingleStage Full Adder Cell in Single-Flux-Quantum Circuit Technology,' IEEE Transactions on Applied Superconductivity, vol. 31, no. 6, pp. 1-10, Sept. 2021, Art no. 1303110, doi: 10.1109/TASC.2021.3091963.
- [7] T. Kawaguchi, K. Takagi and N. Takagi, 'Rapid Single-Flux-Quantum Logic Circuits Using Clockless Gates,' IEEE Transactions on Applied Superconductivity, vol. 31, no. 4, pp. 1-7, June 2021, Art no. 1302407, doi: 10.1109/TASC.2021.3068960.
- [8] C. J. Fourie and K. Jackman, 'Experimental Verification of Moat Design and Flux Trapping Analysis,' IEEE Transactions on Applied Superconductivity, vol. 31, no. 5, pp. 1-7, Aug. 2021, Art no. 1300507, doi: 10.1109/TASC.2021.3051582.
- [9] H. F. Herbst, P. l. Roux, K. Jackman and C. J. Fourie, 'Improved Transmission Line Parameter Calculation Through TCAD Process Modeling for Superconductor Integrated Circuit Interconnects,' IEEE Transactions on Applied Superconductivity, vol. 30, no. 7, pp. 1-4, Oct. 2020, Art no. 1100504, doi: 10.1109/TASC.2020.3006988.
- [10] S. Yang, X. Gao, R. Yang, J. Ren and Z. Wang, 'A Hybrid Josephson Transmission Line and Passive Transmission Line Routing Framework for Single Flux Quantum Logic,' IEEE Transactions on Applied Superconductivity, 2022, doi: 10.1109/TASC.2022.3206280.
- [11] B. Zhang and M. Pedram, 'qSTA: A Static Timing Analysis Tool for Superconducting Single-Flux-Quantum Circuits,' IEEE Transactions on Applied Superconductivity, vol. 30, no. 5, pp. 1-9, Aug. 2020, Art no. 1700309, doi: 10.1109/TASC.2020.2970218.
- [12] S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, L. M. Johnson, M. A. Gouker and W. D. Oliver, 'Fabrication Process and Properties of FullyPlanarized Deep-Submicron Nb/Al- AlO x /Nb Josephson Junctions for VLSI Circuits,' IEEE Transactions on Applied Superconductivity, vol. 25, no. 3, pp. 1-12, June 2015, Art no. 1101312.
- [13] S. K. Tolpygo et al., 'Advanced Fabrication Processes for Superconducting Very Large-Scale Integrated Circuits,' IEEE Transactions on Applied Superconductivity, vol. 26, no. 3, pp. 1-10, April 2016, Art no. 1100110, doi: 10.1109/TASC.2016.2519388.
- [14] V. V. Ryazanov, V. A. Oboznov, A. Yu. Rusanov, A. V. Veretennikov, A. A. Golubov, and J. Aarts, 'Coupling of Two Superconductors through

- a Ferromagnet: Evidence for a π Junction', Phys. Rev. Lett, Vol. 86, Iss. 11 - Published 12 March 2001
- [15] B. Baek et al., 'Magnetic barrier structures for superconducting magnetic hybrid Josephson junctions,' 2013 IEEE 14th International Superconductive Electronics Conference (ISEC), 2013, pp. 1-3, doi: 10.1109/ISEC.2013.6604268.
- [16] I. I. Soloviev et al., 'Superconducting Circuits without Inductors Based on Bistable Josephson Junctions,' Phys. Rev. Applied 16, 014052 -Published 21 July 2021
- [17] I. Salameh, E. G. Friedman and S. Kvatinsky, 'Superconductive Logic Using 2 ϕ -Josephson Junctions With Half Flux Quantum Pulses,' in IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 69, no. 5, pp. 2533-2537, May 2022, doi: 10.1109/TCSII.2022.3162723.
- [18] D. Hasegawa et al., 'Demonstration of interface circuits between halfand single-flux-quantum circuits,' IEEE Transactions on Applied Superconductivity , doi: 10.1109/TASC.2021.3072846.
- [19] C. J. Fourie et al., 'Results From the ColdFlux Superconductor Integrated Circuit Design Tool Project,' in IEEE Transactions on Applied Superconductivity, vol. 33, no. 8, pp. 1-26, Nov. 2023, Art no. 1304926, doi: 10.1109/TASC.2023.3306381.
- [20] M. A. Karamuftuoglu, H. Cong and M. Pedram, 'qCS: quantum Circuit Studio,' 2023. [Online]. Available: https://github.com/Karamuft/qCS
- [21] E. Goldobin, D. Koelle, R. Kleiner, and A. Buzdin, 'Josephson junctions with second harmonic in the current-phase relation: Properties of ϕ junctions,' Phys. Rev. B 76, 224523 - Published 21 December 2007
- [22] M.J.A. Stoutimore et al., 'Second-Harmonic Current-Phase Relation in Josephson Junctions with Ferromagnetic Barriers,' Phys. Rev. Lett. 121, 177702 - Published 26 October 2018
- [23] S. Razmkhah and P. Febvre, 'JOINUS: A user-friendly open-source software to simulate digital superconductor circuits,' IEEE Transactions on Applied Superconductivity, 30(5), 1-7. 2020.