<!-- image -->

## ColdFlux Superconducting EDA and TCAD Tools Project: Overview and Progress

Coenrad Johann Fourie, Kyle Jackman, Matthys Botha, Sasan Razmkhah, Pascal Febvre, Christopher Lawrence Ayala, Qiuyun Xu, Nobuyuki Yoshikawa, Erin Patrick, Mark Law, et al.

## To cite this version:

Coenrad Johann Fourie, Kyle Jackman, Matthys Botha, Sasan Razmkhah, Pascal Febvre, et al.. ColdFlux Superconducting EDA and TCAD Tools Project: Overview and Progress. IEEE Transactions on Applied Superconductivity, 2019, 29 (5), pp.1300407. ￿10.1109/TASC.2019.2892115￿. ￿hal-02017339￿

## HAL Id: hal-02017339 https://hal.science/hal-02017339v1

Submitted on 31 Jan 2025

HAL is a multi-disciplinary open access archive for the deposit and dissemination of scientific research documents, whether they are published or not. The documents may come from teaching and research institutions in France or abroad, or from public or private research centers.

L'archive ouverte pluridisciplinaire HAL , est destinée au dépôt et à la diffusion de documents scientifiques de niveau recherche, publiés ou non, émanant des établissements d'enseignement et de recherche français ou étrangers, des laboratoires publics ou privés.

## ColdFlux Superconducting EDA and TCAD Tools Project: Overview and Progress

C. J. Fourie, Senior Member, IEEE , K. Jackman, M. M. Botha, Member, IEEE , S. Razmkhah, P. Febvre, C. L. Ayala, Member, IEEE , Q. Xu, Member, IEEE , N. Yoshikawa, Senior Member, IEEE , E. Patrick, M. Law, Y. Wang, M. Annavaram, Senior Member, IEEE , P. Beerel, Senior Member, IEEE , S. Gupta, Senior Member, IEEE , S. Nazarian, Member, IEEE , and M. Pedram, Fellow, IEEE

Abstract - The IARPA SuperTools program requires the development of superconducting electronic design automation (S-EDA) and superconducting technology computer aided design (S-TCAD) tools aimed at enabling the reliable design of complex superconducting digital circuits with millions of Josephson junctions. Within the SuperTools program, the ColdFlux project addresses S-EDA and STCAD tool research and development in four areas: (i) RTL synthesis, architectures and verification; (ii) analog design and layout synthesis; (iii) physical design and test; and (iv) device and process modeling/simulation and cell library design. Capabilities include, but are not limited to: device level modeling and simulation of Josephson junctions, modeling and simulation of the superconducting process manufacturing processes, powerful new electrical circuit simulation, parameterized schematic and layout libraries,  optimization,  compact SPICE-like model extraction, timing analysis, behavioral, register-transfer-level and logic syntheses, clock tree synthesis, placement  and  routing,  layout-versus-schematic  extraction,  functional verification, and the evaluation of designs in the presence of magnetic  fields  and  trapped  flux.  ColdFlux  consists  of  six  research groups from four continents. Here we present an overview of the current and planned activities related to the project, and justify design assumptions and decisions that were made to allow the development of design tools for million-gate circuits.

Index Terms -Design automation, Flux pinning, Integrated circuit synthesis, Process modeling, Superconducting integrated circuits

## I. INTRODUCTION

HE ColdFlux project, which falls under the IARPA SuperTools  program  [1],  is  focused  on  the  development  both front-end and back-end superconducting electronic design automation  (S-EDA)  and  technology  computer-aided  design (TCAD). The eventual goal of the project is to enable very large T

Manuscript received October 28, 2018. The research is based upon work supported by the Office of the Director of National Intelligence (ODNI), Intelligence Advanced Research Projects Activity (IARPA), via the U.S. Army Research Office grant W911NF-17-1-0120. (Corresponding author: Coenrad Fourie.)

- C. J. Fourie, K. Jackman and M. M. Botha are with Stellenbosch University, Stellenbosch, South Africa (phone: +2721 808-4029; e-mail: coenrad@sun.ac.za; kjackman@sun.ac.za; mmbotha@sun.ac.za).
- S. Razmkhah and P. Febvre are with IMEP-LAHC, University of Savoie Mont Blanc, Le Bourget du Lac, France (e-mail: sasan.razmkhah@univ-smb.fr; pascal.febvre@univ-smb.fr).
- C. L. Ayala and Q. Xu are with the Institute of Advanced Science, Yokohama National University, Yokohama 240-8501, Japan (e-mail: ayala@ynu.ac.jp; xuqiuyun-bj@ynu.jp).

scale integration (VLSI) design and verification of Superconductive Electronics (SCE) as a step toward the development of energy-efficient,  scalable  high  performance  computers.  As  a proof-of-concept demonstration, the ColdFlux team will undertake the design of a 64-bit Reduced Instruction Set Computer (RISC) microprocessor with the tools and cell libraries developed  under  the  project.  For  this  project,  we  limited  the  supported dc-biased logic families to Rapid Single Flux Quantum (RSFQ) [2] for proof-of-concept and ERSFQ [3] for energy efficiency. Support for ac-biased logic families is limited to Adiabatic Quantum Flux Parametron (AQFP) [4].

ColdFlux  results  are  predominantly  open-source,  so  that many of our design decisions are influenced by the availability of open-source modules.

In this paper we present the scope and intended deliverables of the ColdFlux project, list advantages above current state-ofthe-art and report on the progress made thus far.

## II. RTL SYNTHESIS, ARCHITECTURES AND VERIFICATION

## A. High-level and Register-Transfer Level (RTL) synthesis

Logic synthesis is the process of transforming a set of Boolean equations into a network of gates. We use ABC [5] as our logic synthesis platform and add SFQ-specific synthesis modules.

We have developed various logic optimization techniques, done design of multi-input RSFQ cells, and performed retiming to  minimize  the  overhead  of  path  balancing  D  Flip-Flops (DFFs) in SFQ designs [6]. We have developed two SFQ specific technology-independent logic optimization techniques [7]:

- N. Yoshikawa is with the Department of Electrical and Computer Engineering, Yokohama National University, Yokohama 240-8501, Japan (e-mail: nyoshi@ynu.ac.jp).
- E. Patrick and M. Law are with the University of Florida, USA (e-mail: erin.patrick@ece.ufl.edu; law@ece.ufl.edu);
- Y.  Wang  is  with  the  Department  of  Electrical  and  Computer  Engineering, Northeastern  University,  Boston,  MA  USA  (e-mail:  yanz.wang@northeastern.edu).
- M. Annavaram, P. Beerel, S. Gupta, S. Nazarian and M. Pedram are with the Department of Electrical Engineering, University of Southern California, Los Angeles, CA 90007 USA (e-mail: annavara@usc.edu; pabeerel@usc.edu; sandeep@usc.edu;  shahin@usc.edu; pedram@usc.edu).

Color versions of one or more of the figures in this paper are available online at http://ieeexplore.ieee.org.

Digital Object Identifier will be inserted here upon acceptance.

Template version 8.0d, 22 August 2017. IEEE will put copyright information in this area

See http://www.ieee.org/publications\_standards/publications/rights/index.html for more information.

balanced\_rewriting (brw) and balanced\_refactoring (brf). Both techniques  are  effective  in  reducing  the  total  gate  count.  We have also developed two algorithms for performing technology mapping of SFQ circuits with the goal of minimizing the DFF path balancing overhead and logical depth [8]. The logic optimization  procedures  are  incorporated  into  our  synthesis  tool called qPALACE, which will be released to the public soon.

## B. RTL simulation and verification

We use the open-source Verilog simulator Icarus Verilog, or iVerilog [9], to verify synthesized circuits.

## C. Design tool integration and IDE

The ColdFlux tool chain is designed as a collection of individual modules that work at least under Linux CentOS 7. Schematic and layout editing are done with XIC [10], and simulation, analysis, optimization and layout extraction modules are integrated with XIC. Tool design is modular to enable development and maintenance between around 30 developers over four continents. Most modules run from the terminal, with command line parameters and configuration files used to pass information and command and control functionality.

## D. Datapath synthesis and architectural optimization

One demonstrative end goal of the project is to use the SEDA tools to synthesize a RISC-V processor built from superconducting cell libraries. To this end we will explore potential (micro-)architecture  enhancements  to  account  for  the  limitations and opportunities of the new technology. From an architecture view point, the fundamental challenge with SFQ circuits is gate level pipelining, which can cause even simple arithmetic logic unit (ALU) operations such as multiply to take several cycles to complete. While the throughput of such a system can be maximized to operate at one operation per cycle through careful design,  in  the  targeted  CPU  single  threaded  performance  requires data dependent operations to be separated at least by the ALU latency. Since the hardware cannot be burdened with this task, we have been working on purely compiler-based methods to create independent instruction sequences. Rather than rely on programming languages such as C++,  we believe  a  new  domain-specific language (DSL) is necessary to allow programmers  to  express  instruction  independence,  similar  to  how CUDA allowed programmers to specify thread independence. While there is no current effort in DSL design, such an effort will have significant positive impact on performance. For now, we plan to hand optimize code placement for several kernels to demonstrate the performance on the RISC-V processor.

Reducing the producer-consumer delay in an ALU pipeline can also be accomplished by allowing eager data forwarding at the bit granularity. In this approach an ALU may forward results of its partial computations to the consumer instruction in a pipelined  manner.  Rather  than  waiting  for  the  worst-case  latency for computing the full result, a consumer instruction may start its execution earlier by operating on partial results that are forwarded  from  the producer. For instance, the least n- significant bits of computation from a producer can be used by the consumer. Such an approach requires ALU designs that forward partial results. To this end, we are exploring bit-skewed ALU design computation on the data bit can be staggered to enable eager forwarding.

We also explore the memory limitation of superconducting devices  as  an  architecture  challenge.  Since  designing  new memory architectures is outside of the scope of this project, we plan to use existing methodologies to design register files as the primary on-chip storage. Two types of register file can be implemented: a non-destructive read out (NDRO) register file and a much more area efficient destructive read out (DRO) register file.  A  DRO  register  file,  which  maximizes  on-chip  storage, loses its value after every read. However, most programs use registers to store frequently accessed data that may be read more than once. To account for these two competing demands, we are designing a heterogeneous register file consisting of a small set of NDRO registers and a larger number of DRO registers. We are  exposing  the  register  file  heterogeneity  to  our  compiler framework, which is under development and built on LLVM, to maximize the usage efficiency. From preliminary analysis we believe  that  a  compiler  can  isolate  single  use  registers  from multi-use registers (registers that are read more than once) and thus can exploit the heterogeneous register file design.

## E. Verification framework

Our open-source verification framework consists of formal, semi-formal and simulation-based tools, and algorithms, with partial reliance on the existing verification methodologies and open-source tools. There are however several key differences between SFQ and CMOS logic circuits, related to pulse signaling, gate fanout, ultra-deep (gate-level) pipelining, and path balancing, which should be considered. Our tool for logical equivalence checking (LEC) [11] first performs structural verification of the DUV (design under verification). In case of a successful pass on both path balancing and fanout count, functional checking is performed using conventional LEC. If the path balancing check fails, further processing is required, as a circuit may not be fully balanced, yet function correctly. The DUV is therefore transformed to its accurate clocked-based model. This transformation will unify structural and functional information of the SFQ circuit. A clocking control logic unit is also added to  control  the  inputs  and  a  logical  miter  circuit  is  then  constructed.  Next  a  Boolean satisfiability  (SAT) [12] instance is added to encode the miter circuit and finally a SAT solver is used to analyze the miter. To improve the verification scalability and coverage, we also plan to release a semi-formal verification platform based on UVM (Universal Verification Methodology) that can accelerate coverage directed test generation by running assertions in gate level and RTL abstractions [13]. We will also release a model checking [14] tool, which is capable  of  formally  proving  complex temporal properties at RTL that will mainly target control-intensive circuits. To validate our framework, we have also developed several SFQ circuit benchmarks that include faulty  designs  with  various  structural  and functional errors

## III. ANALOG DESIGN AND LAYOUT SYNTHESIS

## A. JoSIM Simulation engine

Although JSIM [15] and WRSpice [10] are available as opensource simulation engines for superconducting circuits, we developed a new superconducting circuit simulation engine, JoSIM [16] , for ColdFlux. JoSIM is the first simulation engine to support both voltage and phase-based simulation, so that it supports zero-voltage current flow in superconducting loops and can process our compact models where static magnetic fields couple to inductive loops with zero resistance [17].

In  addition  to  the  standard  Resistively  and  Capacitively Shunted Junction (RCSJ) model [18] [19], we aim to support the Werthamer microscopic tunnelling junction model [20] of the Josephson junction for more accurate simulation of AQFP [4] circuits with unshunted junctions and RSFQ circuits at ultimate clock frequencies. JoSIM thus combines the capabilities of JSIM and PSCAN [21] [22].

Other features of JoSIM include direct support for parameterized elements, optimization, margin analysis and simulation of circuits with more than 100,000 components.

JoSIM v2.0 (October 2018) is already available for use [23].

## B. Layout synthesis

Layout synthesis methods are developed to define circuit layouts as scripts with the aid of Python-based parameterized cells (PCells), or in combination with a layout synthesizer, Absynth, that we are developing. Absynth will integrate directly with parameter extraction tools such as InductEx [24] to allow parameter verification [25].

With layouts scripted as parameterized cells, resynthesis is possible when row dimensions are altered, track pitch changed, or process feature reductions become available. We will also integrate parameterized layout scripting and synthesis methods with Layout-versus-Schematic (LVS) and Design-Rule Checking (DRC) methods.

Part of our layout synthesis procedure is the synthesis of Passive Transmission Line (PTL)  interconnects as striplines ground plane stitching and through-ground vias along the routing paths generated by the placement and routing tools.

## C. Process Design Kit (PDK)

Process design kits consist of a set of files that contain descriptions of the basic building blocks of the process. Our PDK for the MITLL SFQ5ee process [26] already contains:

- 1) Primitive device library: symbols; device parameters.
- 2) Verification decks: InductEx layer definition files calibrated against measured experimental structures [27].
- 3) Technology data: Layer information, display attributes, process constraints.
- 4) Rule files: LEF format of abstracted layout data.
- 5) Simulation models of devices: Josephson junctions.

## IV. PHYSICAL DESIGN AND TEST

## A. Place-and-route and clock tree synthesis and routing

Our placement tool utilizes a row-based methodology [28]. The placement tool  for  SFQ  logic  cells  (qPlace)  implements global placement using one of the state-of-the-art algorithms, namely SimPL. In each iteration of this algorithm, two placement solutions are generated. 1) A placement solution calculated by solving a quadratic objective function (total HPLW) which  produces  a  lower-bound  solution  (in  terms  of  total HPWL).  2)  A  placement  solution  generated  by  legalizing lower-bound solution (upper-bound solution in terms of total HPWL) [29]. To discourage overlap in lower-bound solution, cell  locations  in  the  upper-bound  solution  work  as  anchors, providing pulling forces towards cells in the lower-bound solution. Therefore, in each iteration upper-bound solution of previous iteration changes the quadratic formulation. We implemented this algorithm in C++, improving the overall placement solution  and  runtime  significantly  with  respect  to  the  implementation of the seedling project. Although this algorithm provides a high-quality global solution, it does not necessarily give high quality solution in terms of longest path length (critical wire length).

Once the placement is done, clock tree synthesis must be performed to propagate the clock signal to all the clocked elements. In SFQ technology, most cells receive a clock signal. Additionally, all the cells have a fan-out of 1, and to propagate the signals to more than one fanout, splitters should be used. Thus, a complete H-tree with n clock sink nodes needs n -1 clock splitters  [30].  Large  number  of  splitters  significantly  increase  the total area dedicated to the clock network.

Our  tool  qGDR  integrates  a  global  router  and  a  detailed router to fulfill the full-chip routing task. The global router assigns loose connection paths for nets while attempting to minimize the number of used vias. The detailed router follows the global routing results to complete the routing task.  Development  of  the  detailed  router  is  based  on  open-source  tool (Qrouter) which greedily searches routing paths regardless of any  specific  physical  characteristics.  The  feedback  system  is further  embedded in qGDR to automatically increase routing tracks until all nets are routed. Following the MIT-LL SFQ5ee process technology, an 8-bit Kogge-Stone adder (KSA) of 638 nets is routed by qGDR in less than 20 seconds.

## B. Fault simulation, test pattern generation and built-in-selftest tools

Compared to CMOS, the power and performance benefits of SFQ come from the use of Josephson junctions instead of small feature sizes, hence defects are not a major cause of chip failures and process variations and other non-idealities become the leading causes of chip failure. Due to the nature of quantized pulse-based operation, even a highly-distorted pulse is still interpreted correctly but the timing of the pulse is affected. Hence, with a specific focus on dynamic timing verification and delay testing,  we  develop delay  fault  models and characterize cells

under process variations to identify delay fault excitation conditions, sensitization conditions, and error propagation conditions under the effect of process variations. We then propose a completely  new  timing  independent  Automatic  Test  Pattern Generation (ATPG) paradigm to select target delay sub-paths and generate test patterns that guarantee to excite the worst-case delay along a target delay sub-path. The new ATPG tools based on these methods will be released under ColdFlux. We are also developing a timing aware approach to improve the coverage and effectiveness  of  the  set  of  test  patterns  generated  by  our ATPG.

## C. Clocking

In  addition  to  the  potential  use  of  zero-skew  H-trees  (see [31]) for clock distribution networks (CDN), we developed an advanced  clocking  strategy  to  provide  more  scalability  and more resilience to variability.

We proposed the hierarchical chains of homogeneous cloverleaves clocking, (HC) 2 LC, a robust and self-adaptive clocking technique for generic and complex pipelines [32]. The proposed clocking methodology is an asynchronous CDN in the form of a hierarchical set of connected asynchronous loops. (HC) 2 LC nominally oscillates as fast as a synchronous H-tree, but due to its asynchronous nature, exhibits resilience to variations, slowing down when portions of the network are slow [33].  This clocking scheme inherits its robustness from the spatial correlation of various sources of variations [34] and the timing robustness of traditional counter-flow clocking. It trades off reasonable  area  and  power  overheads  for  higher  reliability,  as quantified by yield [35], and improved scalability.

## D. Timing analysis

We extract timing models for dc-biased RSFQ and ERSFQ cells  from  JoSIM  electrical  simulations  with  TimEx  [36],  of which version 2.03 (August 2018) is available for use [37]. Flux signatures are analyzed for each loop in a circuit under test, and all possible states-each corresponding to a unique flux signature-are found. Critical and delay timings between every pair of inputs are found. We use TimEx both for timing extraction and verification of cell functionality.

For timing verification, we developed vcd\_assert, of which version 1.0 is available [38], to expand the capability of opensource iVerilog simulations. This tool allows timing assertion verification on the outputs of iVerilog simulations, with timing specifications  provided  in  Standard  Delay  Format  (SDF),  so that both open-source and commercial Verilog simulators can be used for timing analysis.

For the extraction of timing models for ac-biased AQFP logic cells, we developed a separate tool called AQFPTX, of which version 1.0 has been delivered. The core extraction approach is similar to what was proposed in [39], but makes use of redefined  timing  parameters  suitable  for  SDF  file  generation  and provides a more user-friendly extraction configuration. As with TimEx, the simulation engine is JoSIM, although both extraction tools are compatible with JSIM [15] and JSIM\_n [40]. Furthermore, it can be used to verify cell-level functionality. Automatic  operation  margin  analysis  of  excitation  current  and  dc offset of AQFP cells with respect to timing parameter dependency is also planned for development.

We already delivered a first-order post place-and-route STA tool, SuperSTA [41].

We  also  developed  a  timing  characterization  method  that uses look-up tables (LUTs) [42] that are specifically designed for  SFQ  logic  circuits  and  is  similar  to  the  non-linear  delay model (NLDM) based LUTs for CMOS circuits. After investigating timing characteristics of SFQ cells, the following LUTs were chosen: Clock-to-Q delay of clocked cells, input-to-output delay of non-clocked cells (JTL, splitter, and merger) and output pulse width of each cell are stored in 2-dimensional (2D) LUTs indexed by (i) the first series inductance ( L series) and (ii) the difference ( IQ ) between the critical current and the bias current through the first grounded Josephson Junction after the output of the cell. Setup and hold times are stored in 1-dimensional (1D) LUTs based on the incoming pulse width.

## E. Thermal analysis

We are developing post-layout power and thermal analysis methods to determine local heating due to static and dynamic power dissipation, with accurate modeling of thermal resistance on-chip in a cryogenic environment [43]. Compact simulation models will include temperature parameters for every element such as inductors, of which the kinetic component is temperature dependent, and for every device such as a Josephson junction.  Temperature  support,  with  thermal  noise,  at  component and device level will be supported in JoSIM. Local temperature is used as well to estimate thermal noise in circuits and provide more  accurate  simulations  based  on  temperature-dependent physical parameters like critical currents and gap voltage [44].

## F. Margin calculation and yield analysis

Robustness of an SFQ gate indicates the tolerance of the gate to variations in electrical parameters of its components. Accordingly, a margin is defined as the amount of acceptable variation in an external parameter (e.g. bias current) or internal parameter (e.g. critical current IC and inductance values) for which the circuit continues to function correctly.

We have layout-extracted Monte Carlo models [45] and optimization methods that utilize Monte Carlo yield analysis [46]. For large circuits, we employ both traditional margin analysis [47]  and  probabilistic  methods  [48].  New  optimization  tools based on these methods as well as more advanced stochastic methods will be released under ColdFlux.

We also analyze operating margins in the presence of external magnetic fields [49] [50], and link this analysis to compact model extraction and experimental measurements [51] [52].

For AQFP logic, the AQFPTX tool used for timing extraction has a planned feature for also performing automatic operating margin analysis. The tool will be able to analyze how changes in the excitation power/clock and dc offset of AQFP affect the logical functionality of cells as well as the timing parameters. The analysis can generate SDF files for various corners of the operation margins so that one can carry out timing analysis for not just the nominal excitation amplitude and dc offset but also for their corner cases.

We have also developed a novel method for accurate margin calculation of (SFQ) logic cells in a superconducting electronic circuit. This method can be utilized as a figure of merit to estimate the robustness of a logic cell without the need for expensive Monte Carlo simulations. This was achieved through efficient state-space exploration of all variability parameters of a RSFQ cell structure. Using this method, distinct parameter dispersion (DPD) based yield of SFQ cells increases by 55% on average [53], compared with state-of-the-art techniques.

## V. TECHNOLOGY CAD AND CELL LIBRARY DESIGN

## A. Process and device modeling

Josephson junction parameters as a function of manufacturing steps is of key importance in the verification of VLSI circuit yield. We use Level Set Methods (LSM) [54], included in the FLOOXS process simulation tool extended to support devices and process steps for SCE Nb/Al-AlOx/Nb processes.

The output of the process simulation tool will be combined with the local equations that rule the thermal and electrical behavior  of  materials  and  devices  to  predict  the  properties.  To start with a first simplified approach we chose a phenomenological  electromagnetic  model based on the two fluid  model, associated with Maxwell laws to model the niobium material at the Schubnikov state where Hc 1 &lt; H &lt; Hc 2 since Josephson junctions work in this state in presence of a magnetic field. For the thermal  model  of  type  II  superconductors,  we  started  with  a simple linear model proposed by Maki [55]. In this model, the thermal conductance of the system depends on the concentration of quasiparticles and phonons in the superconductor lattice. This  dependency can be translated into a dependency on  the magnetic field of the superconductor.

## B. Parameterized DC/AC-biased cell libraries

Cell  libraries  are  required  to  demonstrate  the  capability  of tools for the ColdFlux project, and to allow verification of the tool chain. A parameterized DC-biased RSFQ and ERSFQ cell library has been developed. Test circuit layouts are being prepared. Cells are parameterized for adjustment of nominal IC -the  value  for  a  Josephson  junction  in  a  standard  Josephson Transmission Line - from 125 µ A to 250 µ A, and layouts are parameterized to adjust for cell height and cell width. For rowbased place-and-route purposes, all cells have fixed height, and width is variable as an integer multiple of the routing track pitch [28]. We use passive transmission line (PTL) for all gate-togate interconnects, with track pitch between 7 and 10 µ m depending on the characteristic impedance of the stripline PTL. Drivers and receivers are embedded into gate layouts to reduce junction count and delay times and optimized to reduce reflections [56]. In order to calculate maximum PTL length and maximum number of vias, we are developing high-frequency models of PTL to include the plasma frequency of superconductors and to account for dispersion and attenuation [57] [58].

An AC-biased AQFP standard cell library has been developed. We first designed four basic AQFP gates: buffer, inverter and constant 0 and constant 1. More complicated gates such as

AND, OR and MAJORITY are designed via the minimalist design  approach [59]  using  a  bottom-up  manner.  Although  the size of different cells varies, for example a buffer occupies an area of 15 µ m × 20 µ m, whereas the size of an AND gate is 45 µ m × 27.5 µ m, the ac/clock I/O position is fixed for row-based placing and routing in meander structure [60]. We use microstrip lines for gate-to-gate interconnects. The width of the microstrip line is 2.4 µ m, with 50 Ω impedance, for ac/clock propagation. Data delivery striplines are 5 µ m wide, with impedance of 7 Ω .

## C. Layout parameter extraction

For layout extraction we use the InductEx tool suite [24] [25], with additions [17] [61] [62] to support the ColdFlux requirements. InductEx was developed for self and mutual inductance extraction  from superconducting circuit layouts, but  we have since added support for flux trapping analysis [17] [62], external magnetic fields, and the calculation of ground plane return currents. The result is that InductEx can now extract compact models for circuits in the presence of an electromagnetic environment for post-layout verification of field operating margins and deterioration of operating margins due to bias and return current effects.

We are also developing methods to improve the efficiency of numerical electromagnetic field solvers for calculating current distributions  on  superconducting  integrated  circuit  structures. The  well-known  integral  equation-based  tool,  FastHenry,  is specifically considered [63]. It employs a multilevel fast multipole  algorithm  (MLFMA)  solver to reduce required  memory and accelerate the solution. This MLFMA solver introduces approximations into the system matrix representation, leading to a certain level of error in the output. An alternative, multilevel adaptive cross approximation solver with singular value decomposition recompression (MLACA-SVD) [64] [65] has been developed within FastHenry [66] [67]. Results show that the new solver requires less memory than FastHenry's MLFMA, for the same solution accuracy. It also offers  simple, comprehensive control over matrix approximation errors, such that a given solution may be obtained to any desired accuracy. A novel extension to the MLACA-SVD solver is reported [68], which yields a  further  30% reduction in required memory, without loss of accuracy.

## D. Design rule checking and layout-vs-schematic tools

Layout-versus-schematic (LVS) tools generate netlists from physical layouts (e.g. in GDSII format) and compare these to user-generated schematics for graph isomorphism. If the graphs are isomorphic, LVS is satisfied. If the designs are not isomorphic, the LVS tool must provide effective feedback to layout designer.

We started from previous work on LVS for superconductor integrated circuits [69], and developed a method that meshes layouts with Gmsh and the openCASCADE library and builds graphs from nodes at triangle centers and edges between touching triangles. The graphs are then simplified until edges represent unique components, such as junctions, inductors and resistors.

## E. Flux trapping analysis tools

Magnetic flux trapped in superconducting films [70], [71] interact with surrounding superconducting circuits, which can adversely affect circuit operations. Moats can be placed in the superconducting ground plane near sensitive regions to mitigate the effects of flux trapping [72].

An existing three-dimensional numerical solver, TetraHenry [73], has been modified to evaluate the effects of trapped flux on superconducting circuits. The Gibbs potential is used to calculate the probability of flux trapping and the self and mutual inductance between moats, holes and applied external magnetic fields.  The  extracted  mutual  inductances  can  then  be  used within SPICE simulations to determine the operating margins and yield of the circuit  for different combinations of trapped vortices  within  moats.  With  flux  trapping  analysis  tools  now available, a tool is under development to optimize the geometry (size and placement of moats and location of dc bias pads) so that yield an margins can be improved.

## F. Compact models

Physics driven device modeling is typically slow, so that empirical models (or compact models) that do not directly model the underlying physics are more useful for SPICE simulations.

Apart from the inclusion of temperature dependence in component values for compact SPICE models, we also include the electromagnetic environment through the effects of static magnetic fields, coupling from bias and ground return currents and trapped flux in the compact SPICE models. Compact model extraction  for  the  electromagnetic  environment  is  directly  supported by InductEx.

## VI. CONCLUSION

The ColdFlux project is delivering back-end tools for better design, optimization and layout of SFQ circuits in magnetic environments, with RSFQ, ERSFQ and AQFP libraries for rapid prototyping of circuit designs by new designers. Front-end tools for synthesis, placement and routing, with clock synthesis for both dc-biased and ac-biased logic families are also being delivered. Complemented with verification tools, from cell layout extraction to RTL verification and post place-and-route timing verification, the ColdFlux tool suite will be aimed at enabling faster, higher yield development and fabrication of SFQ VLSI systems.

## REFERENCES

- [1]   "IARPA SuperTools Program," [Online]. Available: https://www.iarpa.gov/index.php/researchprograms/supertools.
- [2]   K. K. Likharev and V. K. Semenov, "RSFQ logic/memory family: a new Josephson-junction technology for sub-terahertz-clock-frequency digital
3. systems," IEEE Trans. Appl. Supercond., vol. 1, pp. 328, 1991.
- [3]   D. E. Kirichenko, S. Sarwana and A. F. Kirichenko, "Zero static power dissipation biasing of RSFQ circuits," IEEE Trans. Appl. Supercond., vol. 21, pp. 776-779, 2011.
- [4]   N. Takeuchi, D. Ozawa, Y. Yamanashi and N. Yoshikawa, "An adiabatic quantum flux parameteron as an ultra-low-power logic device," Supercond. Sci. Technol., vol. 26, p. 035010, 2013.
- [5]   Berkeley Logic Synthesis and Verification Group, "ABC: A System for Sequential Synthesis and Verification," [Online]. Available: http://people.eecs.berkeley.edu/~alanmi/abc/.
- [6]   N. Katam and M. Pedram, "Logic optimization, complex cell design, and retiming of Single Flux Quantum circuits," IEEE Trans. Appl. Supercond., vol. 28, pp. 19, 2018.
- [7]   G. Pasandi and P. M., "Technology-independent logi synthesis targeting RSFQ circuits," 2018.
- [8]   G. Pasandi, A. Shafaei and M. Pedram, "SFQMap: A technology mapping tool for Single Flux Quantum logic circuits," in Proc. International Symposium on Cirucits and Systems (ISCAS) , 2018.
- [9]   "iVerilog," [Online]. Available: http://iverilog.icarus.com/.
- [10]   Whiteley Research, Inc., [Online]. Available: http://www.wrcad.com.
12. Vols. C-
- [11]   R. E. Bryant, "Graph-based algorithms for Boolean function manipulation," IEEE Trans. Comput., 35, pp. 677-691, 1896.
- [12]   S. A. Cook, "The complexity of theorem-proving procedures," in Proc. STOC '71 , Shaker Heights, 1971.
- [13]   F. Wang, H. Zhu, P. Xiao, Y. Xiao, P. Bogdan and S. Nazarian, "Accelerating coverage directed test generation for functional verification: a neural networkbased framework," in Proc. GLSVLSI , 2018.
- [14]   E. A. Emerson and E. M. Clarke, "Characterizing correctness properties of parallel programs using fixpoints," in Proc. ICALP , 1980.
- [15]   E. S. Fang and T. Van Duzer, "A Josephson integrated ciruit simulator (JSIM) for superconductive electronic applications," in Ext. Abs. ISEC , Tokyo, 1989.
- [16]   J. A. Delport, K. Jackman, P. Le Roux and C. J. Fourie, "JoSIM - Superconductor SPICE simulator," IEEE Trans. Appl. Supercond., submitted for publication.
- [17]   K. Jackman and C. J. Fourie, "Software tools for flux trapping and magnetic field analysis in superconducting circuits," IEEE Trans. Appl. Supercond., submitted for publication.
- [18]   W. C. Stewart, "Current-voltage characteristics of Josephson junctions," Appl. Phys. Lett., vol. 12, pp. 277280, 1968.
- [19]   D. E. McCumber, "Effect of ac impedance on dc voltage-current characteristics of superconductor weak-

- link junctions," J. Appl. Phys., vol. 39, pp. 3113-3118, 1968.
- [20]   N. R. Werthamer, "Nonlinear self-coupling of Josephson radiation in superconducting tunnel junctions," Phys. Rev., vol. 147, p. 255, 1966.
- [21]   S. Polonsky, V. Semenov and P. Shevchenko, "Pscan: personal superconductor circuit analyzer," Supercond. Sci. Technol., vol. 4, pp. 667-670, 1991.
- [22]   "PSCAN2 Superconducting circuit simulator," 2016. [Online]. Available: http://www.pscan2sim.org/.
- [23]   "JoSIM," [Online]. Available: https://github.com/JoeyDelp/JoSIM.
- [24]   "InductEx," [Online]. Available: http://www.inductex.info.
- [25]   C. J. Fourie, "Full-gate verification of superconductive integrated circuit layouts with InductEx," IEEE Trans. Appl. Supercond., vol. 25, p. 1300209, 2015.
- [26]   S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, L. M. Johnson, M. A. Gouker and W. D. Oliver, "Fabrication process and properties of fully-planarized deepsubmicron Nb/Al-AlOx/Nb Josephson junctions for VLSI circuits," IEEE Trans. Appl. Supercond., vol. 25, p. 1101312, 2015.
- [27]   C. J. Fourie, C. Shawawreh, I. V. Vernik and T. V. Filippov, "High-accuracy InductEx calibration sets for MIT-LL SFQ4ee and SFQ5ee processes," IEEE Trans. Appl. Supercond., vol. 27, p. 1300805, 2017.
- [28]   S. Nazar Shahsavani, T.-R. Lin, A. Shafaei, C. J. Fourie and M. Pedram, "An integrated row-based cell placement and interconnect synthesis tool for large SFQ logic circuits," IEEE Trans. Appl. Supercond., vol. 27, p. 1302008, 2017.
- [29]   S. Nazar Shahsavani, A. Shafaei and M. Pedram, "A placement algorithm for superconducting logic circuits based on cell grouping and super-cell placement," in Design, Automation &amp; Test in Europe Conference &amp; Exhibition (DATE) , 2018.
- [30]   N. Katam, A. Shafaei and M. Pedram, "Design of multiple fanout clock distribution network for Rapid Single Flux Quantum technology," in Proc. Asia and South Pacific Design Automation , 2017.
- [31]   Y. Kameda, S. Yorozu and Y. Hashimoto, "A new design methodology for Single-Flux-Quantum (SFQ) logic circuits using Passive-Transmission-Line (PTL) wiring," IEEE Trans. Appl. Supercond., vol. 17, pp. 508-511, 2007.
- [32]   R. N. Tadros and P. A. Beerel, "A Robust and SelfAdaptive Clocking Technique for SFQ Circuits," IEEE Trans. Appl. Supercond., vol. 28, no. 7, pp. 1-11, 2018.
- [33]   R. N. Tadros and P. A. Beerel, "A Robust and SelfAdaptive Clocking Technique for RSFQ Circuits -- The Architecture," in 2018 IEEE International Symposium on Circuits and Systems (ISCAS) , Florence, 2018.
- [34]   P. Bunyk, K. Likharev and D. Zinoviev, "RSFQ technology: Physics and devices," Int. J. High Speed
- Electronics and Systems, vol. 11, no. 01, pp. 257-305, 2001.
- [35]   R. N. Tadros and P. A. Beerel, "A Robust and Tree-Free Hybrid Clocking Technique for RSFQ Circuits -- CSR Application," in 16th International Superconductive Electronics Conference (ISEC) , Sorrento, 2017.
- [36]   C. J. Fourie, "Extraction of dc-biased SFQ circuit Verilog models," IEEE Trans. Appl. Supercond., vol. 28, p. 1300811, 2018.
- [37]   "TimEx," [Online]. Available: https://github.com/sunmagnetics/TimEx.
- [38]   "vcd\_assert," [Online]. Available: https://github.com/pleroux0/vcd\_assert.
- [39]   C. L. Ayala, N. Takeuchi, Q. Xu, Y. Narama, Y. Yamanashi, T. Ortlepp and N. Yoshikawa, "Timing extraction for logic simulation of VLSI adiabatic quantum-flux-parametron circuits," in IEICE, SCE Meeting, SCE2015-21 , Oct. 2015.
- [40]   J. Satchell, "Stochastic simulation of SFQ logic," IEEE Trans. Appl. Supercond., vol. 7, pp. 3315-3318, 1997.
- [41]   J. A. Delport and C. J. Fourie, "A static timing analysis tool for superconducting digital circuit applications," IEEE Trans. Appl. Supercond., submitted for review.
- [42]   N. Katam and M. Pedram, "Timing characterization for static timing analysis of Single Flux Quantum circuits," in EUCAS , 2017.
- [43]   A. Savin, J. P. Pekola, D. V. Averin and V. K. Semenov, "Thermal budget of superconducting digital circuits at subkelvin temperatures," J. Appl. Phys., vol. 99, p. 084501, 2006.
- [44]   V. Ambegaokar and B. I. Halperin, "Voltage due to thermal noise in the dc Josephson effect," Phys. Rev. Lett., vol. 22, pp. 1364-1366, 1969.
- [45]   C. J. Fourie, W. J. Perold and H. R. Gerber, "Complete Monte Carlo model description of lumped-element RSFQ logic circuits," IEEE Trans. Appl. Supercond., vol. 15, pp. 384-387, 2005.
- [46]   N. Yoshikawa and K. Yoneyama, "Parameter optimization of Single Flux Quantum digital circuits based on Monte Carlo yield analysis," IEICE Trans. Electron., Vols. E83-C, pp. 75-80, 200.
- [47]   C. A. Hamilton and K. C. Gilbert, "Margins and yield in single flux quantum logic," IEEE Trans. Appl. Supercond., vol. 1, pp. 157-163, 1991.
- [48]   N. Mohyuddin, E. Pakbaznia and M. Pedram, "Probabilistic error propagation in a logic circuit using the Boolean difference calculus," in Proc. Intl. Conf. Computer Design , 2008.
- [49]   R. S. Bakolo, R. Van Staden, P. Febvre and C. J. Fourie, "Modelling magnetic fields and shielding efficiency in superconductive integrated circuits," J. Supercond. Nov. Magn., vol. 30, pp. 1649-1653, 2017.
- [50]   R. S. Bakolo, J. A. Delport, P. Febvre and C. J. Fourie, "Anallysis of a shielding approach for magnetic field

- tolerant SFQ circuits," IEEE Trans. Appl. Supercond., vol. 27, p. 1301305, 2017.
- [51]   R. Collot and P. Febvre, "Operation of low-Tc circuits in a magnetic environment," IEEE Trans. Appl. Supercond., vol. 23, p. 1700404, 2013.
- [52]   R. Collot, P. Febvre, J. Kunert, H.-G. Meyer, R. Stolz and J. L. Issler, "Characterization of an on-chip magnetic shielding technique for improving SFQ circuit performance," IEEE Trans. Appl. Supercond., vol. 26, p. 1300605, 2016.
- [53]   S. Nazar Shahsavani, B. Zhang and M. Pedram, "Accurate margin calculation for Single Flux Quantum logic cells," in Design, Automation &amp; Test in Europe Conference &amp; Exhibition (DATE) , 2018.
- [54]   J. A. Sethian, Level set methods and fast marching methods, New York: Cambridge University Press, 1999.
- [55]   K. Maki, "Thermal conductivity of pure Type-II superconductors in high magnetic fields," Phys. Rev., vol. 158, pp. 397-399, 1967.
- [56]   L. Schindler, P. Le Roux and C. J. Fourie, "Optimization of Passive Transmission Lines to minimize reflections between RSFQ logic cells," IEEE Trans. Appl. Supercond., submitted for publication.
- [57]   P. Le Roux, J. A. Delport, K. Jackman and C. J. Fourie, "Time domain modeling of superconducting circuit interconnects," IEEE Trans. Appl. Supercond., submitted for publication.
- [58]   P. Febvre, C. Boutez, S. George and G. Beaudin, "Models of superconducting microstrip and coplanar elements for submillimeter applications," Proc. SPIE, vol. 2558, pp. 136-147, 1995.
- [59]   N. Takeuchi, Y. Yamanashi and N. Yoshikawa, "Adiabatic quantum-flux-parametron cell library adopting minimalist design," J. Appl. Phys., vol. 117, p. 173912, 2015.
- [60]   N. Takeuchi, S. Nagasawa, F. China, T. Ando, M. Hidaka, Y. Yamanashi and N. Yoshikawa, "Adiabatic quantum-flux-parametron cell library designed using a 10 kA cm-2 niobium fabrication process," Supercond. Sci. Technol., vol. 30, p. 035002, 2017.
- [61]   K. Jackman and C. J. Fourie, "Impedance extraction of superconducting structures," IEEE Trans. Appl. Supercond., submitted for publication.
- [62]   K. Jackman and C. J. Fourie, "Flux trapping analysis in superconducting circuits," IEEE Trans. Appl. Supercond., vol. 27, p. 1300105, 2017.
- [63]   M. Kamon, M. J. Tsuk and J. K. White, "Fasthenry: a multipole-accelerated 3-d inductance extraction program," IEEE Trans. Microw. Theory Tech., vol. 42, pp. 1750-1758, 1994.
- [64]   M. Bebendorf and S. Rjasanow, "Adaptive low-rank approximation of collocation matrices," Computing, vol. 70, pp. 1-24, 2003.
- [65]   L. Grasedyck, "Adaptive recompression of H-matrices for BEM," Computing, vol. 74, pp. 205-223, 2005.
- [66]   B. A. P. Nel and M. M. Botha, "Investigation of Multilevel Adaptive Cross Approximation (MLACA) acceleration for superconducting circuit analysis," in Proc. International Conference on Electromagnetics in Advanced Applications (ICEAA) , Cartagena, 2018.
- [67]   B. A. P. Nel and M. M. Botha, "An efficient MLACASVD solver for superconducting integrated circuit analysis," Supercond. Sci. Technol., submitted for publication.
- [68]   B. A. P. Nel and M. M. Botha, "MLACA with modified grouping strategy for efficient superconducting circuit analysis," IEEE Trans. Appl. Supercond., submitted for publication.
- [69]   R. M. C. Roberts and C. J. Fourie, "Layout-versusscematic verification for superconductive integrated circuits," IEEE Trans. Appl. Supercond., vol. 25, p. 1200105, 2015.
- [70]   J. Pearl, "Current distribution in superconducting films carrying quantized fluxoids," Appl. Phys. Lett., vol. 5, no. 4, pp. 65-66, 1964.
- [71]   S. Narayana, V. K. Semenov, Y. A. Polyakov, V. Dotsenko and S. K. Tolpygo, "Design and testing of high-speed interconnects for superconducting multi-chip modules," Supercond. Sci. Technol., vol. 25, p. 105012, 2012.
- [72]   V. K. Semenov and M. M. Khapaev, "How moats protect superconductor films from flux trapping," IEEE Trans. Appl. Supercond., vol. 26, p. 1300710, 2016.
- [73]   K. Jackman and C. J. Fourie, "Tetrahedral modeling method for inductance extraction of complex 3-D superconducting structures," IEEE Trans. Appl. Supercond., vol. 26, p. 0602305, 2016.