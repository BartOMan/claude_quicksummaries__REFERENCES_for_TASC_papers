## SUPERCONDUCTIVE SINGLE FLUX QUANTUM LOGIC DEVICES AND CIRCUITS: STATUS, CHALLENGES, AND OPPORTUNITIES

M. Pedram USC ECE pedram@usc.edu https://discoverexpedition.usc.edu/

http://coldflux.usc.edu/ Talk given at ISLPED

## Going Faster with Less Energy

- Very high clock frequencies
- High single-threaded performance through short switching times and fast signal propagation
- Ultra low switching energy
- Energy related to the generation of the bit information should be made as small as possible

Superconductor circuits meet both of the aforesaid requirements and have become a strong candidate for a beyond-CMOS computing fabric. This technology is known for the high clock frequencies, 2-50 GHz, and the low energy dissipation per logical operation, down to several zJ [1].

[1] K. K. Likharev and V. K. Semenov, RSFQ logic/memory family: A new Josephson-junction technology for sub-terahertz-clock-frequency digital systems, IEEE Trans.  Appl. Supercond. 1, 3 (1991). [2] N. Takeuchi, Y. Yamanashi, and N. Yoshikawa, Measurement of 10zJ energy dissipation of adiabatic quantum flux-parametron logic using a superconducting resonator, Appl. Phys. Lett. 102, 052602 (2013).

## The Case for Superconductor Circuits

WHY SCE

System-level energy consumption (GFlops/Joule)

<!-- image -->

Neural network inference energy consumption (TOPs/Joule)

<!-- image -->

## Single Flux Quantum Logic

- Ginsburg-Landau theory: Superconductivity is a second-order phase transition, where an ordered state emerges from a disordered state at low temperatures
- Bardeen-Cooper-Schrieffer theory: Superconductivity is the condensation of bound pairs of electrons, where these Cooper pairs are connected through electron-phonon interactions
- Logic circuits based on magnetic flux quantization rather than conductance modulation
- Allows discrete representation of information in the form of Single Flux Quantum (SFQ)

𝚽𝚽 𝟎𝟎 = ℏ / 𝟐𝟐𝟐𝟐 ≈ 𝟐𝟐 . 𝟎𝟎𝟎𝟎 × 𝟏𝟏𝟎𝟎 -𝟏𝟏𝟏𝟏 volt-second (amperehenry=weber)

ℏ is the Planck constant, e is the electron charge

- Only an integer number of flux quanta can exist in a superconductive loop

<!-- image -->

- Josephson junction (JJ) is the nonlinear switching element in superconductive circuits
- Consists of two superconductors that are weakly coupled through a tunnel barrier (insulator)
- Superconducting state phase difference 𝜙𝜙 exists over JJ, producing supercurrent:

<!-- image -->

𝐼𝐼 𝑗𝑗 ( 𝑡𝑡 ) = 𝐼𝐼 𝐶𝐶 sin 𝜙𝜙 ( 𝑡𝑡 ) with 𝑑𝑑𝜙𝜙 / 𝑑𝑑𝑡𝑡 = 2 𝜋𝜋𝑉𝑉 𝑗𝑗 ( 𝑡𝑡 )/ Φ 0 where 𝐼𝐼 𝐶𝐶 denotes JJ critical current and Φ 0 = ℏ /( 2𝑒𝑒 ) (Josephson equations define current-phase relationship and its evolution)

- DC Josephson effect : Constant DC current bias 𝐼𝐼 𝑗𝑗 &lt; 𝐼𝐼 𝐶𝐶 results in constant phase difference 𝜙𝜙 and zero voltage across JJ (tunneling of Cooper pairs through barrier produces supercurrent w/o applied voltage)
- AC Josephson effect : Constant voltage 𝑉𝑉 𝑗𝑗 applied across JJ results in linearly increasing phase difference and current oscillating at 𝑓𝑓 = 2 𝜋𝜋𝑉𝑉 𝑗𝑗 ( 𝑡𝑡 )/ Φ 0

Overdamped JJ (small R and C), with Stewart-McCumber parameter ꞵ C ≈1 is critically damped; this is the primary type of JJ

<!-- image -->

Resistively capacitively shunted junction (RCSJ) model

<!-- image -->

- Rapid SFQ (RSFQ), invented c. 1985 by O. Mukhanov, V. Semenov, and K. Likharev
- Pulse-based logic family, inherently synchronous, limited fanout drive
- Basic element of RSFQ logic is superconducting loop interrupted by one or more JJs
- If the loop inductance 𝐿𝐿 is high enough such that 𝐼𝐼 𝐶𝐶 𝐿𝐿 ≥ Φ 0 , then SFQ can be held in the loop as a persistent current representing logical one, whereas an absence of SFQ means logical zero
- Magnetic flux ejected from a superconducting loop through a JJ takes the form of tiny voltage pulses (mV, ps)
- Building blocks of SFQ circuits
- Transfer and storage sections
- Decision-making pairs

Time

<!-- image -->

<!-- image -->

<!-- image -->

## Josephson Transmission Line

Josephson Transmission Line (JTL) shows how the SFQ devices transfer the information

The SQUID of JTL has one stable state. In this state, the current flow through both JJs is close to their critical current

<!-- image -->

## Josephson Transmission Line

<!-- image -->

When we send an input voltage pulse to the JTL, the current flow through the J 1 is increasing and it exceeds the critical current

J1 switches and creates a voltage pulse, the new pulse will increase the current flow through J 2 , then J 2 will switch and create an output voltage

<!-- image -->

<!-- image -->

## RSFQ Inverter

<!-- image -->

<!-- image -->

## RSFQ Logic Gates

<!-- image -->

## Key Advantage: Passive Transmission Lines

<!-- image -->

- Superconducting transmission is dispersion free, i.e., we have ballistic propagation of an SFQ pulse [5]
- Speeds up to 1/3 of the speed of light are achieved ( Typical delay: 10 ps/mm )
- Needs PTL driver and receiver circuits, Delay scales linearly with PTL length [6].
- Must be impedance matched to the JJs of driver and receiver circuits. Junctions in the latest fabrication processes allow about 5 to 10 Ω lines, which reduces line width for tighter integration.

## PTLs are a highly appealing feature in RSFQ circuits.

- [5] Takagi, Katsumi, et al. "SFQ propagation properties in passive transmission lines based on a 10-Nb-layer structure." IEEE Transactions on Applied Superconductivity 19.3 (2009): 617-620.
- [6] P. l. Roux, K. Jackman, J. A. Delport and C. J. Fourie, "Modeling of Superconducting Passive Transmission Lines," in IEEE Transactions on Applied Superconductivity, vol. 29, no. 5, pp. 1-5, Aug. 2019, Art no. 1101605.

## Fabrication Technology

- Existing fabrication processes: ISTEC-AIST, 2.5 kA/cm 2 (Japan), MIT-LL 10 kA/cm 2  (USA).

<!-- image -->

Stacked/

[7] S. K. Tolpygo, V. Bolkhovsky, D. E. Oates, R. Rastogi, S. Zarr, A. L. Day, T. J. Weir, A. Wynn, and L. M. Johnson, Superconductor electronics fabrication process with MoNx kinetic inductors and self-shunted Josephson junctions, IEEE Trans. Appl. Supercond. 28, 1100212 (2018).

## Unique Characteristics of SFQ Logic

- Different active and passive components
- Two-terminal JJ's and inductors vs. 3-terminal transistors and capacitors in CMOS
- Superconducting interconnect
- Josephson transmission lines (JTLs) and passive transmission lines  with small series resistors to prevent flux storage (PTLs) vs. lossy interconnect in CMOS
- Different suites of basic cells
- Simple clocked cells (NOT, AND, OR, XOR, DFF, NDRO) and some clockless cells (delay cells, splitters) vs. complex multi-input logic cells in CMOS
- Different drive capability
- Very low fanout count (typically just one fanout) vs. large fanout drive capability in CMOS
- Full-path balancing requirement
- The input signals of each cell must arrive within one clock window for the correct operation of SFQ circuits
- Expensive to implement feedback loops and conditionals
- No dense on-chip memory
- Large area
- Theoretical estimation of the maximum density of SFQ-based circuits utilizing geometric inductance of wires gives ∼ 10 7 JJ/cm 2 . Further decrease of the linewidth and spacing is problematic because of a nearly exponential growth in the mutual inductance and crosstalk between the inductors. Kinetic inductances help, but their effectiveness at smaller scales is questionable [8b].

[8b] I. I. Soloviev, V. I. Ruzhickiy, S. V. Bakurskiy, N. V. Klenov, M. Yu. Kupriyanov, A. A. Golubov, O. V. Skryabina, and V. S. Stolyarov, Superconducting digital circuits without inductors, arXiv.org &gt; cond-mat &gt; arXiv:2011.05856v1.

## Gate -level pipelining

- Since each gate has a clock, all the input should travel the same cycle to arrive at any gate
- The most common way to balance the path is by adding DRO cells. However, there are other ways to achieve this goal, such as optimizing the synthesis process

<!-- image -->

<!-- image -->

## Gate -level pipelining

- Since each gate has a clock, all the input should travel the same cycle to arrive at any gate
- The most common way to balance the path is by adding DRO cells. However, there are other ways to achieve this goal, such as optimizing the synthesis process

<!-- image -->

<!-- image -->

## Gate -level pipelining

- Since each gate has a clock, all the input should travel the same cycle to arrive at any gate
- The most common way to balance the path is by adding DRO cells. However, there are other ways to achieve this goal, such as optimizing the synthesis process

<!-- image -->

<!-- image -->

## Fanouts

- In SFQ logic, fan-out is not free. A splitter can duplicate a pulse and then drive two pins
- In SFQ logic, a merger makes two SFQ pulses drive the same pin possible

<!-- image -->

## Cooling Cost

One big question has been how much the energy needed for cooling will increase a superconducting computer's energy budget. But advocates suggest it might not be much. The power drawn by commercial cryocoolers leaves 'considerable room for improvement,' Elie Track and Alan Kadin of the IEEE's Rebooting Computing initiative recently wrote. Even so, they say, 'the power dissipated in a superconducting computer is so small that it remains 100 times more efficient than a comparable silicon computer, even after taking into account the present inefficient cryocooler.'

<!-- image -->

## IARPA SuperTools Program: ColdFlux Tools

<!-- image -->

## qPALACE: ColdFlux Frontend Design Tools

<!-- image -->

## Full Path Balancing Requirement

## · Gate-level pipeline:

- Most of SFQ gates (except a few gates such as splitter, merger, TFF, etc.) require receiving a clock signal to transfer the stored quantum flux to their output. This data transfer resets the superconducting current loop and destroys internal state of the logic gate. Need specialized Non-Destructive Read Out (NDRO) gates to maintain internal state after readout.

## • Full Path Balancing (FPB):

- Due to the gate-level pipelining in SFQ, length of any path from any primary input to a gate in terms of the clocked elements should be the same.

<!-- image -->

Correct operation

<!-- image -->

## qSyn: A Path Balancing Technology Mapper Targeting the SFQ logic

## · Motivation:

- High overhead of path balancing D flipflops (PB-DFFs)
- Choose mapping solutions that minimize the total JJ count, including JJ's in the logic gates and PB-DFFs

## Conventional mapping solution:

<!-- image -->

[8] G. Pasandi, and M. Pedram, ''A Dynamic ProgrammingBased, Path Balancing Technology Mapping Algorithm Targeting Area Minimization,'' in IEEE Int. Conf. on Computer-Aided Design (ICCAD) , Nov. 2019.

#Gates: 11, #PB-DFFs: 9, logical depth: 4, gate area: 37 units, total area: 61 units

<!-- image -->

## qSyn mapping solution:

<!-- image -->

#Gates: 12, #PB-DFFs: 2, logical depth: 3, gate area: 42 units, total area: 56 units

## Retiming of Sequential Circuits with Feedback Loops

## · 3-bit counter [9]:

[9] G. Pasandi, and M. Pedram, 'qSeq: Full Algorithmic and Tool Support for Synthesizing Sequential Circuits in Superconducting SFQ Technology,'' ICCAD 2021.

```
module counter （clk，rst，en，count); input clk, rst， en; output reg[2:0]count; always @(posedge clk) if (rst) count<= 3'd0; else if (en) count<=count+3'd1; endmodule
```

## Six loops:

```
Loop 1: 6 → 5 →7 Loop 2: 2 → 4 → 5 → 7 →3 Loop 3: 11 → 13 → 15 Loop 4: 10 → 12 → 13 → 15 → 14
```

```
Loop 5: 20 → 18 → 23
```

Loop 6: 22 →21 →19 →17 →18 →23

<!-- image -->

<!-- image -->

## Clocking

<!-- image -->

- Single clock architecture: all clocked cells are fed with the same clock to
- The input signals for correct operation must arrive within a clock window for each cell
- Dual clock architecture [10]: clocked cells are fed with fast and slow clock signals to form a partially path balanced (PPB) circuit
- Frequency relation: 𝑓𝑓 𝑓𝑓𝑓𝑓𝑓𝑓𝑓𝑓 = Θ +1 𝑓𝑓 𝑓𝑓𝑠𝑠𝑠𝑠𝑠𝑠 where Θ ∈ ℤ + ∪ {0}
- The input signals for correct operation arrive within Θ + 1 clock windows for each cell
- Balancing register count can be reduced with the increase of Θ

## ColdFlux, 2018 25 Supporting a Dual Clocking Architecture

<!-- image -->

## Definitions:

Tslow

slack: delay of pulses between fast and slow clock sources

𝐿𝐿𝑃𝑃 𝑓𝑓𝑠𝑠𝑠𝑠𝑠𝑠

: a clock path from slow clock works as the launch path

𝐶𝐶𝑃𝑃 𝑓𝑓𝑓𝑓𝑓𝑓𝑓𝑓

: a clock path from fast clock works as the capture path

𝑃𝑃𝐷𝐷 𝐴𝐴𝐴𝐴𝐴𝐴

: propagation delay of AND

: reset delay of NDRO

𝑅𝑅𝑒𝑒𝑠𝑠𝑒𝑒𝑡𝑡 𝐴𝐴𝐴𝐴𝑁𝑁𝑁𝑁

## Timing constraints:

<!-- formula-not-decoded -->

<!-- image -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- image -->

## Example of the Dual Clocking Architecture

- 4bit adder: λ=4
- Input values: a 0 =0101, a 1 =1011, a 2 =0010, a 3 =1001, b 0 =0110, b 1 =1000, b 2 =1011, b 3 =0110, c in =1010.
- Output values: S 0 =1001, S 1 =0101, S 2 =0011, S 3 =0101, C out =1010.

<!-- image -->

On average, NPB (no path balancing) and PPB (partial path balancing) reduce area by 2× and 15.38%, respectively, compared to FPB (full path balancing) case.

<!-- image -->

## Conclusion

- Under the ColdFlux project we have been developing:
- EDA flows  and tools for better design, optimization and layout of SFQ circuits in magnetic environments, with RSFQ, ERSFQ and AQFP logic circuits
- The open-source design framework and tool suite will be made available to the public!
- In spite of much progress, key challenges exist in way of physical scaling, controlling stray electromagnetic fields, supporting multiple clock, doing current recycling, design centering to improve operating margins, designing dense on-chip memory, etc.