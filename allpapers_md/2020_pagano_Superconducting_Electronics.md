## Superconducting Electronics

Sergio Pagano

Dipartimento di Fisica 'E.R. Caianiello' Università di Salerno Italy

## l SQUIDs

- l Voltage Standards
- l Digital Circuits
- l Radiation Detectors

## Superconducting Electronics

## Kilogram

## ThePtlrKilogramat theBIPM

## Meter

Lengthof thepath travelledbylightinvacuum during a timeintervalof1/299792458ofasecond

## Second

9192631770timestheperiodof thehyperfine-structureradiationof133Cs

## Voltage

Connected toSIvia thevoltagebalance:0.3ppm

Current

Connected toSIvia the currentbalance:0.3ppm ortracedbacktoVolt,Second,Meterviathe calculable capacitor/=dO/dr=CdU/d

## Resistance

Connected to SIvia calculable capacitor(1/oC):0.045ppm

The goal is to define the units through fixed universal constants Last revision 2018

## The International System of Units

## SI-Units

SI:SystemeInternationaled'Unites

International System of Units:

Meter-Kilogram-Second-AmpereMKSA （+mol,cd,andK)

<!-- image -->

<!-- image -->

## Connecting the electrical quantities

PracticalVolt reprodjction

precision of voltage standard

<!-- image -->

## The resistively shunted model RSJ of a Josephson junction

<!-- image -->

## RF effects: Shapiro steps

<!-- image -->

if the frequency f = 70 Ghz à U n = n 0.145 mV , n is limited to few units à need for arrays

Stepsofconstantvoltage:

$$U=n·（h/2e)·f$$

Conventional (underdampedjunctions)

<!-- image -->

- HystereticIVC
- Semistablesteps
- Voltagehardlyadjustable

10-VJosephsonvoltagestandard (13920SISjunctions)

<!-- image -->

usedbymorethan50labsworld-wide commerciallyavailablefromIPHT,Hypres

## Programmablevoltagestandards

<!-- image -->

## OverdampedJosephsonjunctions(β.&lt;1):

<!-- image -->

- shuntedSiSjunctions

<!-- image -->

Current

<!-- image -->

- SNSjunctions
- S-Sc-Sjunctions
- SINis junctions

## Binarydividedseriesarray

Application:D/Aconverterwithfundamentalaccuracy

## SiNisJosephsonjunction

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

## Synthesizedwaveforms

- 1-Varray(8192SINIS-JJ) microwavefrequency:7oGHz
- Maximumvoltage:1,188V (correspondstoanrmsof 0,840Vforasinewave)

<!-- image -->

<!-- image -->

## 400-Hzsinewavegeneratedwith13binarybits

16samples

<!-- image -->

64samples

256samples

## NIST USA

## Fabrication &amp; Design of Superconducting Circuits

- Boulder MicroFabrication Facility
- Superconducting integrated circuits
- Uniform junctions, barrier materials, low-defect fabrication
- Microwave circuit design
- Lumped element inductors &amp; capacitors, power splitters, coplanar waveguides, simulation &amp; modelling

<!-- image -->

from P. Dresselhaus' talk, ISEC2017

(12 x 17) mm 2 PJVS Chip Microwave Input

<!-- image -->

## Flat Spots of 16 Arrays with 16800 Junctions

from P. Dresselhaus' talk, ISEC2017

<!-- image -->

## NIST Cryocooled PJVS System

- Integrated system
- Bias electronics DC &amp; MW
- Cryogenics
- Superconducting devices
- Turn-key integrated system
- Automation software
- Optimize &amp; check quantum states, flat spots
- Performs measurements
- Specific measurement techniques needed for different applications

from P. Dresselhaus' talk, ISEC2017

<!-- image -->

14

## First Comparisons of  1 V AC Josephson Voltage Standard Sources

<!-- image -->

JAWS

- Statistical uncertainty of first intercomparisons of 1 V AC JAWS voltages are now below 0.1 m V/V
- Systematic errors are ~1 m V/V for kilohertz frequencies

- l SQUIDs
- l Voltage Standards
- l Digital Circuits
- l Radiation Detectors

## Superconducting Electronics:

## The End of the Moore's Law in Digital Electronics

The exponential growth of energy consumption by computing and network systems has become an increasingly important issue.

During the last fifty years the density of integration has followed an almost exponential increase and promises to continue for about another decade before reaching the technology physical limits. However a large integration level comes with a large energy dissipation , that has reached the level of 100 W/cm 2 . Such level of energy dissipation already limits the maximum clock frequency to about 4 GHz and poses severe limitation to the number of active elements in a chip that can be powered at any time.

From https://www.karlrupp.net/2018/02/42-years-of-microprocessor-trend-data/

<!-- image -->

## The End of the Moore's Law in Digital Electronics

<!-- image -->

This is a particularly important problem for high performance computing .

<!-- image -->

The top performing Chinese Sunway TaihuLight: 10 Million cores, 10 20 Flop/s, has a power requirement close to 15 MW , one third of which is used for cooling.

| www.top500.org   |
|------------------|

## Electricity consumption is a growing issue also for large Data Centers

In 2013, U.S. data centers consumed an estimated 91 billion kilowatt-hours of electricity , equivalent to the annual output of 34 large (500-megawatt) coal-fired power plants . Data center electricity consumption is projected to increase to roughly 140 billion kilowatt-hours annually by 2020 , the equivalent annual output of 50 power plants, costing American businesses $13 billion annually in electricity bills and emitting nearly 100 million metric tons of carbon pollution per year.

## Why superconducting digital electronics?

Josephson junction based superconducting electronics has been proposed as a possible solution for high performance computing because of the possibility to reach much higher clock frequencies ( up to 200 GHz ) and great energy efficiency .

<!-- image -->

<!-- image -->

## A brief history of Josephson digital circuits development

l

First efforts at IBM in 1967

l

l Voltage-state projects at IBM, Sperry, TRW, Berkeley MITI project l in Japan, some in Europe

l

l

Early 1980's

l

Important fabrication developments (full refractory material)

l

l

1985

l

First publication on rapid single flux quantum (RSFQ) circuits

l

l

1991 - 2010

l

RSFQ is adopted as main digital technology

l

l

2010-present

l

Development of Energy-Efficient superconducting digital families

## Distinguishing Features of Superconducting Digital Circuits

- Need a large numbers of devices (many thousands for useful circuits)
- Need CAD tools (some tools made for semiconductors are usable, but others need modification)
- Small margins (allowed variation of power supply level)
- No gain (unlike transistor circuits)
- Lack of adequate memory (4-kbit memory demonstrated)
- Layout for flux management (1 cm 2 chip has 500 flux quanta if B = 0.1 mG . Circuits must be protected.)

## LTS Interconnections

Most interconnections are in microstrip configuration

Prior to 1985 --Pb alloy (basis of the 1967-1983 IBM project and early Japanese projects)

Currently niobium is the 'workhorse' for large circuits; operation at 4-5 K. (Key inventions were AlO x grown barriers and the whole wafer process with subtractive etching.)

Microstrip Inductance per square for Nb L  ~ 0.50 pH/ square

NbN technology based on NbN/MgO/NbN L  ~ 0.75 pH/ square Advantage over Nb: Tc ~ 15 K so operation temperature ~ 8-10 K Disadvantage: Large and variable penetration depth and inductance/square

## MgB2   technology

In some cases Tc = 40 K, so potentially usable with simple refrigerator Early state of development, only a small number of junctions have been demonstrated; none at 40 K.

## Choosing a Technology

## High Tc materials

Most developed candidate is YBa2Cu3O with Tc = 90 K

The usual rule of operating 0.5 - 0.7 of Tc suggests operating at 45 K - 63 K But noise currents and voltages increase with temperature.

Excessive error rates if T &gt; 30 K.

Critical current spread: σ = 6% (6 σ = 36%)

Too large for digital circuits, except small demonstration gates.

Need a breakthrough-a new controllable way to make Josephson junctions.

## Choosing a Technology

## NiobiumJosephsonJunctionsforDigital Circuits

TheonlyJJtechnologyforcircuitswithlargenumbersofjunctions withsufficientcontrolistheNb/AlO/Nbtunneljunction.

TypicalI-V ofahigh-quality tunneljunction

Predominanttypeofdigitalcircuitis theRapidSingleFluxQuantum (RSFQ)logicfamily,whichrequires nearlynon-hystereticI-V.

<!-- image -->

To achieve the non-hysteretic form of I-V, a resistor R is connected in shunt with the tunnel junctions to make b c   ~   1- 2

## Switching time of a hysteretic Josephson junction à ns scale

<!-- image -->

## Switching time of a shunted junction (1 junction SQUID) à ps scale

<!-- image -->

## SFQandFluxQuantization

<!-- image -->

n=0

"1""

n=1

## FundamentalLimitsforIntegratedElectronics

<!-- image -->

<!-- image -->

## SFQCircuitElements

Currentbiased Josephsonjunction

```
Ideal:I=Isin v(t)=（Φ√π)dp/dt @phase difference I.critical current Rnormal state resistance Φ=h/2e=2.0679x10-15Wb
```

<!-- image -->

Superconductingring StoresSingleFluxQuanta

<!-- formula-not-decoded -->

```
Thejunction can act as: SFQtransferelement: a 2πphase slippagegenerates a voltage pulse V(t)dt=Φin the 1-4ps range Oscillator: VDc=Φf;V=IRdefines the maximum operation speed e.g.145μV-70GHz
```

Both circuitelementscanbe combinedtocomplexlogic circuits

## BasicSFQCircuits

<!-- image -->

| Buffer               | ConfluenceBuffer          | Pulse Splitter    |
|----------------------|---------------------------|-------------------|
| One-way transmission | Combinesinputs ("fan-in") | Provides"fan-out” |

<!-- image -->

## SFQ pulses are too fast for semiconducting eletronics need for interface circuits

<!-- image -->

## Typical SFQCircuit

<!-- image -->

## FiguresofMerit

| Linewidth (um)                 | 3.5   | 1.5   | 0.8                 |
|--------------------------------|-------|-------|---------------------|
| cellspercm                     | 104   | 3x104 | 10²                 |
| Speedoflargescalecircuits(GHz) | 10-40 | 40-80 | 70-130 0.1          |
| Minimumpower                   | 0.03  | 0.06  |                     |
| (uWpercell)                    |       |       | K.K.Likharev et al. |

- -Verylowenergy dissipation
- High speed operation(700 GHz for small circuits demonstrated)
- Dispersion freepulsepropagation
- Lowoperation temperatures
- Linewidth&gt;200nm for conventional Nb technology largerjunctionnumberrequires smallerparameterspread

Generation andmaintenance ofpermanent SFQpulse circulation Reliability of circuit operation:BER&lt;10 16

<!-- image -->

<!-- image -->

## ApplicationPotential

| Application                                                                                                                                                                                                                                                                                                                                                | Junction count                          | Market Size                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-------------------------------------------------------------------|
| integrated SIS receiverswith correlator digital multichannel SQUID arrays DCvoltage standards ACvoltage standards, digital synthesiser A/D converters D/Aconverters de/acquantum voltmeters time-digital converters digital SFQ test circuitsfor rfmetrology coding'decodingsystems for secure communications frequeney dividers, digital frequency meters | 10° 105 10* 105 10* 10² 105 10* 10* 10² | Small Medium Small Medium Large Medium Large Medium Medium Medium |
| transient recorders samplers digital beam forming microwave antennas read-out for multipixel focal plane array imagers TeraFLOPSworkstation PetaFLOPScomputer                                                                                                                                                                                              | 500 10* 10 ? ？ 106 1000x106             | Medium Medium Medium ?? 2? Medium ??                              |

69

SCENET Roadmap for superconducting digital electronics

## Nb-NbN3umtechnology

<!-- image -->

Implementation of a 8bit shift register circuit withanewNb-NbN3um technology developed at CEA-Grenoble MTS-Foundry;(the design of a similar 16-bit shift register done by University of Savoie is represented in theupper part of the figure).

## Fabricationprocess(NECJapan)

<!-- image -->

<!-- image -->

## Features

- ·9 Nb layers with planarized SiO 2 .
- ·Nb/AlOx/Nb JJs with J c of 10 kA/cm 2 .
- ·Reduced feature size to 0.8 m m.

<!-- image -->

High Yield High Speed High Density

## 16kbitmemory

<!-- image -->

NEC

## Superconducting vs Semiconducting Digital Electronics

<!-- image -->

## RSFQ CPU development

## Bit-Serial Architecture (Complexity-Reduced)

<!-- image -->

CORE1 α LV (2013) 3869 JJs, 35 GHz 400 MIPS, 0.23 mW

<!-- image -->

CORE1 α MPU (2003) 15 GHz, 4999 JJs 167 MIPS, 1.6 mW

<!-- image -->

## Bit-Slice/Parallel Architecture

<!-- image -->

<!-- image -->

## CORE100 MPU (2015)

Bit-serial m P no memory 100 GHz, 3073 JJs 3073 JJs 800 MIPS 1.0 mW 800 GIPS/W

Stored-program computing demo

Bit-Parallel m P 50 GHz ALU 8b bit-parallel ALU (2017) 50 GHz, 4868 JJs 1.4 mW 36000 GIPS/W Gate-Level Pipelining

<!-- image -->

<!-- image -->

<!-- image -->

CORE e2 MPU (2014-2016) Bit-serial m P Memory Embedded 50 GHz, 10000-20000+ JJs 500 MIPS 2.4 mW 210 GIPS/W

<!-- image -->

bit-slice ALU (2015) 50 GHz, 3481 JJs

<!-- image -->

<!-- image -->

Masamitsu Tanaka et al. High-Throughput Bit-Parallel Arithmetic Logic Unit Using Rapid Single-Flux-Quantum Logic, IEEE T AS 2017

Energyefficiency

## Superconducting vs Semiconducting Digital Electronics

<!-- image -->

Estimation of performances of a 32-bit single-core microprocessor based on the experiments

## Main Issues Left for Practical Applications

High-frequency operation of bit-parallel processing

Energy-efficient SFQ circuits

Energy-efficient power supply for dc-powered SFQ circuits

Large capacity memory

Interfacing between SFQ circuits and room temperature electronics

Large scale integration

## Issue for Energy-Efficiency

<!-- image -->

R b is used for providing a constant current to each Josephson junction.

Power consumption at R b (Static power consumption)

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Power consumption at R s (Dynamic power consumption)

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Necessity for eliminating static power consumption.

## DC-Powered Energy-Efficient SFQ Circuits

## Bias resistors are replaced with inductors and junctions.

## ERSFQ circuit (Hypres)

<!-- image -->

D. E. Kirichenko, et al., IEEE Trans. Appl. Supercond., 21 , 776(2011).

## Advantage

- p The base of design has been established because resources obtained from the RSFQ circuits can be used.
- p PTLs can be used as interconnects.
- p Possibly suitable to higher density because no mutual coupling is used.

## Disadvantage

- p Difficult to make energy-efficient voltage supply around 0.1 mV.

## AC-Powered Energy-Efficient SFQ Circuits

## Circuits are driven by AC currents provided via transformers.

## Example Reciprocal Quantum Logic (Northrop Grumman)

<!-- image -->

Q. P. Herr, et al., J. Appl. Phys., 109 , 103903 (2011).

## Advantage

- p Provided AC currents are used as clock signals.
- p NOT logic is easy to be made.
- p The above means the RQL can be made up of smaller number of junctions.

## Disadvantage

- p Transformers are needed for all the gates, indicating downsizing to submicron scale is difficult.
- p High-frequency design technique is essential for operation.

## AC-Powered Energy-Efficient SFQ Circuits

## Circuits are driven by AC currents provided via transformers.

## Example

## Adiabatic Quantum Flux Parametron

(Yokohama Nat'l Univ.)

<!-- image -->

## Advantage

- p Very small energy consumption because of no phase jump in switching.
- p All the logic operations are achieved based on a single 'majority' gate, leading to the robustness to the process variation.

## Disadvantage

- p Operating frequency is relatively low.
- p Difficult to make long interconnects.
- p DC offset currents are needed for operation.

## Energy-Efficiency in Superconducting Digital Circuits

<!-- image -->

Energy Consumption = Total power x Clk cycle

Number of devices

STP: AIST 2.5-kA/cm 2 Nb/AlO x /Nb Standard Integrated Circuit Process.

ADP: AIST 10-kA/cm 2 Nb/AlO x /Nb Advanced Integrated Circuit Process

## Issues for Large Scale Integration

D Flip-Flop: 40 x 80 μ m (Assuming Min. I c = 50 µA)

Line and space: 1 μ

m

<!-- image -->

## The Memory issue

A major difficulty for superconductive electronics is the low integration scale available today (about five orders of magnitude larger). In particular memory elements are currently based of flux quanta trapped in a superconducting loop and represent a critical point with their minimum cell size of the order of 15 μ m × 15 μ m .

New proposals to build superconducting memories have been made, mostly employing hybrid Josephson junction - CMOS RAM , and Magnetic Josephson Junctions (MJJ)

## Cryogenic Magnetic Memories

Hybrid circuits with cryogenic magnetoresistive memory elements (JJ+metal spintronics) Memory cell based on spintronic elements with addition of JJs (for low impedance) or nanowire switches (for high impedance) Memory devices:

- Cryogenic Spin Torque transfer (CST)
- Cryogenic Spin Hall effect (CSHE) elements
- JJ periphery (address decoders, sense, etc.)

<!-- image -->

<!-- image -->

## Cryogenic Magnetic Memories

<!-- image -->

Schematic view of a four-terminal SISF 1 IF 2 S device and its biasing

<!-- image -->

I c ( H ) dependence for the SIS junction while sweeping an external in-plane magnetic field in two opposite directions (five overlapped curves for five consecutive scans are shown).

SEM micrograph of an actual SISF1 IF 2 S device

<!-- image -->

M ( H ) dependence at 10 K for 5 mm ´ 11 mm chip with unpatterned SISF1 IF 2 S multilayer used to fabricate the four-terminal devices. | M / M max | has two considerably different values at H =0, which correlates with the I c ( H ) dependence.

<!-- image -->

Ivan P. Nevirkovets et al., A multi-terminal superconducting-ferromagnetic device with magnetically-tunable supercurrent for memory application, IEEE TAS 2018

## Superconducting Nanowire Memory device

<!-- image -->

The device is based on the Heat Assisted Magnetic Recording , a technique being explored for next generation hard disks. The idea is to heat a small magnetic volume and bring it above its Curie temperature for a short time. At the same time a magnetic field is applied that, although much smaller of the coercive field at the base temperature, can induce a magnetization in the affected volume while it is still cooling.

Advantages : sub-micrometer memory cell size, ns write and read operation, non destructive reading, static memory operation

Issues : identify proper magnetic material (low Tcurie), optimize superconducting/ferromagnetic interface, develop proper digital read/write circuits

<!-- image -->

## Few words on quantum computing

## Universal fault-tolerant quantum computer

The holy grail of quantum information science. Allows one to run useful quantum algorithms which achieve exponential speed ups over their classical counterparts. However the overhead of quantum error correction estimates 1M-5M qubits

## Approximate quantum computer

A quantum device which does not need fault tolerance, with the goal of demonstrating a useful application by interacting with a classical computing system, e.g. quantum chemistry, optimization. Estimate 1K-5K qubits

## Quantum Advantage/Supremacy*

Quantum advantage is an idea that before any useful quantum computer is built it may be possible to demonstrate a special purpose application whose output cannot be simulated as fast using existing classical computers.  Estimate 50-100 qubits

*Arute, F., Arya, K., Babbush, R. et al. Quantum supremacy using a programmable superconducting processor. Nature 574, 505-510 (2019). 53 Qubits 200s instead of 10.000years (IBM claims 2.5days)

## Superconducting digital logic for Quantum Computing

Today existing Quantum computers operate at very low temperatures ( 10-20 mK ) and are based on superconductors and Josephson junctions each Qubit requires interconnection to room other Qubits and to room temperature electronics to be programmed and read.

as the number of needed Qubits increases, there is a limit to the feasible number of connections from LT to RT

Local superconducting control electronics, already at LT although not at 20 mK, could overcome this difficulty and allow scaling up of number of Qubits

<!-- image -->

01/10/2020

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

## IBM Q experience

<!-- image -->

## Launched May 2017

Program 5 qubit quantum processor from any web browser