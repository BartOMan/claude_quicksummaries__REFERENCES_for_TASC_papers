## A Majority Logic Synthesis Framework For Single Flux Quantum Circuits

Junyao Zhang University of Southern California Los Angeles, CA junyaozh@usc.edu

Paul Bogdan University of Southern California Los Angeles, CA pbogdan@usc.edu

Abstract -Exascale computing and its associated applications have required increasing degrees of efficiency. SemiconductorTransistor-based Circuits (STbCs) have struggled with increasing the GHz frequency while dealing with power dissipation issues. Emerging as an alternative to STbC, single flux quantum (SFQ) logic in the superconducting electrons (SCE) technology promises higher-speed clock frequencies at ultra-low power consumption. However, its quantized pulse-based operation and high environmental requirements, process variations and other SFQ-specific non-idealities are the significant causes of logic error for SFQ circuits. A suitable method of minimizing the impact of the aforementioned error sources is to minimize the number of Josephson Junctions (JJs) in the circuits, hence an essential part of the design flow of large SFQ circuits. This paper presents a novel SFQ logic synthesis framework that given a netlist, offers an automated mapping solution including majority (MAJ) logic with the goal of minimizing the number of JJs, while catering to the unique characteristics and requirements of the design. Our experiments confirm that our synthesis framework significantly outperforms the state-of-the-art academic SFQ technology mapper, namely reducing the number of JJs on average by 35.0%.

## I. INTRODUCTION

As a solid competitor to the state-of-the-art semiconductor circuits in the field of super electronic products, SCE has shown great potential in ultra-high-speed clock frequency, and ultra-low power consumption [1]. The interest in SFQ has grown in communities that need higher performance and higher energy efficiency as the most touted candidate in SCE. However, the high sensitivity of SFQ circuits to the environmental factors has been problematic [1], [2]. There has been some research on hard faults in post-manufacturing testing [3], [4]. However, the SFQ technologies have much larger feature sizes compared to CMOS technologies [5]. E.g., a recent fabrication process of JJs is based on a 200nm production-level [6]. A large feature size results in low defect density, thereby stuck-at and other hard faults become less critical.

In contrast, other non-idealities such as process variations and other SFQ-specific issues (inductive coupling, bias current steering, flux trapping) have significant impacts on the operation of the fabricated chips [7]. These faults can cause the logic gates to produce erroneous outputs just as highlydistorted pulses can not be interpreted logically correctly by cells, or unexpected jitters can produce a logical HIGH [8]. A variation-focused ATPG paradigm is proposed to generate test patterns for these random faults [7]. However, these faults still can not be eliminated or minimized effectively. Therefore, it

Shahin Nazarian University of Southern California Los Angeles, CA

shahin.nazarian@usc.edu is critical to develop an effective approach that can mitigate the negative impact of these sporadic failures.

Logic synthesis is an essential step in the design flow of digital circuits because it enables the desired metrics to be minimized [9]. It is divided into two distinct phases: 1) technology-independent optimizations: Boolean optimizations such as restructuring, re-substitution, common subexpression extraction, and node minimization. 2) technology mapping: associating logic expressions with actual gates in the given cell library. According to the theoretical and experimental results [2], [7], the aforementioned faults can be effectively reduced by minimizing the number of Josephson Junctions (referred to as the #JJs) in the SFQ circuits. Thus, an effective method of mitigating the effects of non-idealities in SFQ circuits is to use a mapping algorithm that is oriented toward reducing #JJs.

Additionally, logic synthesis can be improved by incorporating majority logic (MAJ) gates into expressions rather than relying exclusively on the AND-OR-INV-based (AOI) representation [10]. Although MAJ circuit configuration is proposed in Dynamic Single Flux Quantum (DSFQ) [11], and MAJ logic synthesis works exist in both CMOS [12] and Adiabatic Quantum-Flux-Parametron (AQFP) [13]. MAJ circuit configuration in SFQ and a systematic synthesis framework capable of integrating MAJ in to the expression is still imminent.

In this paper, we propose a logic synthesis framework for generating MAJ included SFQ netlists from a given netlist. Mapped netlist minimizes the number of JJs and thus the risk of encountering non-idealities in SFQ circuits. The framework, as illustrated in Fig. 1, is divided into three distinct phases: 1) pre and post-process: both processes are related to the circuit modifications unique to SFQ, such as path-depth balancing, splitter binary trees insertion, and gate conversion. 2) mapping optimization: optimize the cut circuits for each node with a modified Quine-McCluskey algorithm, then greedily modify each node with its corresponding representative cut to reduce the product of total #JJs and the network depth of the netlist (denoted as PND). The main contributions can be summarised as follows:

- We propose a circuit configuration of MAJ gate in SFQ logic and apply it to our proposed logic synthesis framework.
- We develop a novel greedy mapping algorithm for SFQ logic, which can modify each node with its representative

Fig. 1: Overview of the proposed framework . 1) Pre-process: insert splitters into the input netlist; convert all of the cells in the netlist to the cells in the cell library. 2) Mapping optimization: find all the K -feasible cuts for each node; optimize the Boolean function of each cut circuit Cut n with the modified Quine-McCluskey algorithm; regenerate the cut circuit Cut n ∗ with its optimized Boolean function; modify this node by representative cut Cut rep which is the regenerated cut circuit with the most significant improvement in PND value). 3) Post-process: insert DFFs to balance the logic level of each node's fan-in; merge and replace the path-depth balancing DFFs to further minimize their overhead in the SFQ netlist.

<!-- image -->

cut to reduce PND value.

- We propose a logic synthesis framework for SFQ logic, which can process the netlist to an SFQ netlist, including catering to the unique characteristics of SFQ logic and mitigating the impact of non-idealities in SFQ circuits

The rest of the paper provides the preliminaries, related work, motivation, cell characterization under non-idealities, majority gates, synthesis framework for SFQ logic, evaluation, and conclusion in successive sections.

## II. PRELIMINARIES

## A. SFQ Logic

Overdamped Josephson Junctions in SFQ use resistive current bias, which means that the binary information is present in a picosecond duration of voltage pulses V ( t ) , rather than voltage levels in semiconductor technologies. Due to the voltage pulse is equivalent to a quantum of flux φ o = 2 . 07 × 10 -15 V · s , it is also referred to as single flux quantum pulse (SFQ pulses) These unique properties fundamentally alter the conventional understanding of the representation of bits. The basic convention is that the arrival of an SFQ pulse during the current clock period represents a logic ' 1 ' whereas the absence of any pulse during this period is understood as logic ' 0 '. Additionally, there are several SFQ circuit-specific properties that need to be discussed below.

- 1) Fan-out: Given the quantum communication nature of SFQ logic, the fan-out of cells strictly equals to one. A special asynchronous SFQ gate (splitter cell) is used to achieve higher fan-out [1]. A splitter can generate only two output pulses after accepting an SFQ pulse. Additional splitters can be applied to a binary tree structure to allow for additional fan-outs. It needs n -1 splitters to accommodate n fan-outs. Fig. 2 is an example of the splitter binary tree when fan-outs equal 4.
- 2) Gate-level Pipeline: Almost all SFQ gates (except for some asynchronous gates like splitter or Josephson Transmission Line) are clock-synchronized, so an SFQ gate can be

thought of as a CMOS gate with an edge-triggered flip-flop at its output. The outputs only respond to their respective inputs when the clock pulse arrives. This work [14] outlines the design of a clock distribution network, and its take-away is that the SFQ circuit must be completely gate-level pipelined.

- 3) Path-depth Balancing: Due to the gate-level pipeline prerequisite, all inputs of an SFQ gate must have the same logic level for correct operation. Some D flip-flops (DFFs) should be inserted into the path to balance the logic level of inputs if there is a difference among logic levels of fanins. Assume that the fan-in depths of a OR gate are different: in 1 = 1 , in 2 = 2 . The correct pulse as in 1 will be consumed 1 clock earlier than in 2 without the path-depth balancing DFF. Thus, path-depth balancing DFFs are needed to ensure the correct logic values.

## B. Logic Synthesis

There are two phases in logic synthesis: the technologyindependent and the technology-dependent phase [9]. Several optimizations are performed in the first stage to reduce the total number of literals in the given network. Some functional operations include common subexpression extraction, decomposition, and resubstitution [15]. The second phase is referred to as technology mapping, in which appropriate gates from a given library are allocated to nodes in the given network in order to satisfy certain constraints, such as minimizing certain cost functions [9]. The provided netlist needs to be transformed into a Boolean network prior to technology mapping. Boolean

Fig. 2: A splitter binary tree (Fan-outs = 4)

<!-- image -->

networks are directed acyclic graphs (DAG) [9], in which nodes represent logic gates and directed edges correspond to the wires that link the gates. The terms network and circuit are used interchangeably in this paper. Primary inputs (PIs)/primary outputs (POs) are nodes without fan-ins/fan-outs in the current network [16]. A cut of node n is specified as follows: n is the root node (the output of this cut), l n is a set of nodes in the network referred to as leaf nodes (inputs of this cut) [16]. Each path from a PI to n passes through at least one leaf. A cut is K -feasible if it contains no more than K leaf nodes [17]. The logic level of a node is the length of the longest path from any PI to the node. The logical depth is the largest level of an internal node in the network.

## III. RELATED WORK

In the literature of the logic synthesis for SFQ circuits, a few papers have presented the technology-independent and technology mapping problems [18]-[21]. In [18], a framework is developed by constructing a virtual cell named '2AND/XOR', which enables the use of the CMOS logic synthesis tools for SFQ circuits. In [21], it added path-depth balancing DFFs and the splitters to the netlist followed by applying the standard retiming algorithm [22] to reduce the required number of path-depth balancing DFFs. In [20], a technology mapping tool for SFQ logic circuits (called SFQmap) is presented, with an emphasis on minimizing logical depth and product of the worst-case stage delay and the logical depth (PSD). [19] is the similar work to SFQmap, which can generate mapping solutions with balanced structures. Mapping algorithms in [19], [20] are implemented by applying Cutenumeration-based technology, which is close to the work in [17]. The above SCE domain papers [19]-[21] are all developed on an AND-INV graph (AIG) based logic synthesis and verification tool, ABC [23].

Furthermore, there are several applications beyond CMOS technologies like nanotechnologies that have benefited from MAJ logic synthesis, such as quantum cellular automata (QCA) [24] and single electron tunnelling (SET) [25]. In SCE domain, there are few papers that mention majority logic. One of them proposed the majority logic synthesis framework for AQFP [13], another proposed an asynchronous Dynamic SFQ Majority Gates design [11].

## IV. MOTIVATION

Despite significant research advances that leverage logic synthesis in a different domain, the state-of-the-art synthesis tool in SFQ logic still has a substantial improvement space. In [19], [20], their mapping algorithm is developed on Cutenumeration-based technology. This technology aims to map the cut circuit with the supergate by look-up table (LUT). Specifically, the mapping algorithm establishes a massive supergate library and searches it for each cut circuit. If a supergate has the same LUT as the cut circuit, then this supergate can be used to map the cut circuit. The drawbacks of this technology are the limited K value and the memory overhead associated with the supergate library, which grows exponentially with the logical depth and basic cell library size. For instance, by having 20 gates in the original library and using up to level 3 supergates, there will be around 4000 supergates. Despite a large-scale supergate library is established, it is still hard to find a mapped supergate capable of implementing the function of a cut as K value increases [19]. Also, the aforementioned technology primarily focused on the optimization of the depth and path-depth balancing overhead. Apart from these optimizations, we wish to integrate majority logic into the mapping algorithm in order to decrease the #JJs and thus mitigate the effects of random faults.

We propose a novel SFQ logic synthesis framework that favors generating mapping solutions with lower impact SFQ based non-idealities by reducing JJ numbers. Several closedform formulae are developed for: cut selection, modified Quine-McCluskey algorithm, and netlist processing algorithms with SFQ-specific properties. To the best of our knowledge, this is the first paper that presents a logic synthesis framework in SFQ logic: 1) involving majority gates, and 2) mitigating the effect of non-idealities in SFQ circuits.

## V. CELL CHARACTERIZATION UNDER NON-IDEALITIES

SFQ circuits achieve fast operating speeds and low power consumption by using unique characteristics of JJs and superconducting operations. However, JJs are highly sensitive to environmental conditions. Some SFQ-specific issues like inductive coupling, bias current steering, flux trapping can significantly impair their operation [1], [2]. In [7], Monte Carlo simulations are used to characterize the behaviors of SFQ logic cells in non-idealities, and the average value is normalized using Gaussian distributions when circuit parameters change. The simulation results demonstrate that the error rates are relatively higher when a cell contains more Josephson Junctions. As a consequence, SFQ circuits with a large number of JJs are more likely to encounter errors due to non-idealities. As illustrated in Section II-A2, the latency of an SFQ circuit is primarily determined by its logical depth. While a netlist can mitigate the effects of non-idealities by minimizing the #JJs, it does not expect to achieve this objective at the expense of other critical circuit properties, such as logical depth. Therefore, we introduce a new metric, PND, to evaluate latency and reliability combinational performance of a mapping solution. For a network C with node set N , PND is defined as the product of the total #JJs and its logical depth d C .

<!-- formula-not-decoded -->

where P() is the PND value, and J n is the #JJs for node n . The cell library used in this paper consists of the following cells, and each cell is listed in this format: cell name (#JJs) .

Cell library: DFF ( 8 ), AND2 ( 9 ), AND3 ( 12 ), AND4 ( 15 ), OR2 ( 9 ), OR3 ( 11 ), OR4 ( 13 ), INV/inverter ( 5 ), XOR ( 7 ), SP/splitter ( 3 ), and the proposed MAJ ( 12 ).

## VI. MAJORITY GATE MODEL

The majority gates are discussed in this section, along with an example circuit configuration of a gate suitable for use in large-scale SFQ circuits. The n-input (n being odd) majority function M returns the logic value assumed by more than half of the inputs [26]. The principle of Josephson

Fig. 3: Circuit configuration for majority gate

<!-- image -->

Junction is that when the value of its bias current approaches its critical current, it can induce a 2 π leap at the voltage phase, and then trigger an SFQ pulse. A proposed three-input SFQ majority gate is shown in Fig. 3 The gate consists of three parallel superconducting quantum interferometer loops (SQUID) [1], S 1 : { J 1 , L 4 , J 4 , J 11 } , S 2 : { J 2 , L 5 , J 5 , J 11 } and S 3 : { J 3 , L 6 , J 6 , J 11 } . These loops terminate on a grounded junction J11 that drives the output port OUT.

The proposed 3-input MAJ gate operates in a similar manner to the SFQ 3-input AND gate [27]. However, compared with AND3, the dc-bias I b 1 in majority gate provides a comparatively large current. When input pulses are fed in a single clock cycle, the associated loops leap to the '1' state, and the total bias current at J11 equals I b 1 plus currents in leaped loops. In the initial state, all loops are initialized to '0'. In case, there is only one input pulse or no pulse in a single clock cycle, the bias current in J11 does not reach its critical current. Therefore, the clock pulse is incapable of inducing a 2 π leap at J11. When the cell is supplied with two or more input pulses, the total bias current approaches or exceeds to its critical value as the dc-bias I b 1 provides a larger current. In this situation, the clock pulse will induce an SFQ pulse at J11, resulting in a '1' at OUT . The simulation of the proposed gate is depicted in Fig. 4, and its operation is represented as

<!-- formula-not-decoded -->

Fig. 4: Operation of the proposed 3-inputs majority gate, A , B and C are the inputs, CLK is the clock input, and OUT is the output

<!-- image -->

## VII. SYNTHESIS FRAMEWORK FOR SFQ LOGIC

For a given Boolean expression: S = ( ab + bc + ac ) d . We hope to map it into an SFQ circuit. As illustrated in Fig. 5, cutting-edge mapper (SFQmap [20]) generate the left circuit, which has a PND value of 201 and a logical depth of 3. However, it is possible to have a better mapping solution

Fig. 5: Two mapping solutions for S = ( ab + bc + ac ) d . The one on left is generated by SFQmap [20], which PND value is 201, maximum logic level is 3, and requires 1 path-depth balancing DFF; the one on right can reduce the above 3 metrics to 52, 2, 0 separately.

<!-- image -->

with a lower PND value and improved logic optimization, as shown in the right graph in Fig. 5. The reason for this is that no algorithm is currently implemented in state-of-the-art technology mappers for minimizing #JJs and encompassing MAJ gates, let alone optimize such a multi-objective value as PND. Our framework can generate novel mapping solutions with minimal PND values and path-depth balancing overhead. Suppose for a network C with node set N , K n is the set of all K -feasible cuts of node n ∈ N , and c j ∗ n is the regenerated cut circuit of cut c j n ∈ K n , then we formalize the objective for network C with node set N as:

<!-- formula-not-decoded -->

where P () is the PND value function in Eq. (1). In the following section, we will first elaborate on the greedy mapping algorithm for the proposed PND value minimization problem, followed by theoretical analysis for the mapping algorithm, and processes of SFQ unique characteristics modifications in our framework.

## A. Mapping Optimization

In our framework, we perform the following heuristic greedy approach to reduce the PND value of the network. The optimal result for mapping a network is defined as the result that iterates through all the nodes in the network and modifies each node with its representative cut circuit. The representative cut c rep n is the one that has the greatest decrease in PND value after regeneration from the optimal Boolean function compared with original cut c j n . The approach is broken down into the following sub-tasks.

(1) Find K n : We explain K -feasible cut in Section II-B. Algorithm 1 performs a Breath-First search for the upstream nodes of root nodes n and collects all the possible cut circuits under the K boundary, specifically, leaf nodes number of each cut c j n is in range [2 , K ] . Suppose I j n denotes the set of leaf nodes for cut c j n ∈ K n . In general, the searching terminates at the PI nodes, splitter nodes or when the number of leaf nodes exceeds K (size ( I j n ) &gt; K ), since the regenerated cut circuit c j ∗ n retains only the same leaf nodes and root node as its preceding cut circuit c j n . If c j n contains a splitter node inside, and some branches of this splitter are omitted. The latter regeneration process has an effect on the logic values in non-included branches, as this node can be removed or reconnected. Our algorithm is heuristic that can detect possible cuts even behind splitters. Cut c 5 H in Fig. 6 is an example.

Fig. 6: 3-feasible cuts for node H, c 1 H : { F, G } , c 2 H : { A, D, G } , c 3 h : { D, E, F } , c 4 h : { A, D, E } , c 5 H : { A, B, E }

<!-- image -->

## Algorithm 1: Find all K -feasible cuts

```
Input: root node n , cut parameter K Output: set S of all leaf nodes sets for each cut c j U : fan-in set; N : node set; g(): gate type set curPI = { n } , idx = 0 while size ( curPI ) > idx do n c = curPI[idx] s = size(curPI) + size( U nc ) - 1 add all U nx to N in , ( n x ∈ curPI ) for each i ∈ N in do if ∃ j = i ; j ∈ N in , U a ; i ∈ U b ; a, b ∈ curPI then add U a , U b -i to N x and add a , b to N d remove i, j from N in end if curPIN d + N x ≤ k then curPI = curPI N d + N x add curPI to S else if g ( n c ) / ∈ { PI/Splitter } and s < K then add U nc to curPI, remove n c from curPI add curPI to S else idx++
```

```
end
```

(2) Find optimal Boolean function for each cut c j n ∈ K n : In Section IV, we discuss the defects of the state-of-the-art mapping algorithm. We present a novel Boolean function minimization algorithm based on the Quine-McCluskey algorithm [28] to overcome their defects. Our optimization algorithm is superior since it incorporates XOR and MAJ logic into the Boolean Algebra. In addition, in a number of majoritylogic-based works [10], [12], [13], all the AND/OR gates are substituted by with MAJ gates. Although these majority logic based mapping algorithms have demonstrated significant performance gain, and Section VI proves our proposed MAJ gate has the same overhead as the 3-input AND gate. They can not imply that the MAJ is the panacea for all logic optimizations. For example, 3 MAJs and 2 INVs are needed to represent an XOR function. If we insert the splitters and do the path-depth balancing, the overhead will further surge. We only involve the cuts with MAJ gates in the certain best situations in our framework.

To begin the logic optimization, we simulate the cut c j n to determine all of its prime implicants. Assume that the cut c j n has three leaf nodes: { a, b, c } and each bit is represented by 0 or 1 . We present the logic with the standard representation, sum of product (SOP) [29]. Assume the implicant set is as follow:

<!-- formula-not-decoded -->

Implicant { 110 } represents c j n = 1 , when a = 1, b = 1, and c = 0. The number and order of bits in each implicant are immutable. Then, our algorithm evaluates the relationship between each prime implicant and combines them to generate the essential prime implicants. The final set of the essential prime implicants is the optimal Boolean function of cut in the form of SOP. The following relationships in Algorithm 2 are used to validate the implicants: grey code pair, XOR/XNOR logic and MAJ logic. Grey code pair check examines whether there is exactly one different bit between two implicants, and replaces this complement bit with don't care '-' sign. MAJ logic check compares three implicants simultaneously to replace the bits in these implicants that can perform majority logic with ' glyph[star] '. XOR/XNOR logic check is similar to MAJ logic check with two implicants each time. ' ⊕ ' denotes the bits that have an XOR relationship, while ' glyph[circleminus] ' denotes XNOR. The combination begins with grey code pair check until all the implicants are essential prime implicants in this checking stage, then the output implicants are then subjected to other two logic checks (MAJ and XOR/XNOR). These two checks are mutually exclusive, in that if an implicant is modified by one check while the other ignores this implicant. Our algorithm reduces the preceding implicant set to the following essential prime implicants.

<!-- formula-not-decoded -->

These implicants represent the optimal Boolean function as:

<!-- formula-not-decoded -->

## Algorithm 2: Implicant checks

glyph[negationslash]

```
Input: implicant string s1, s2, s3 Function Greycode check( s 1 , s 2 ) : flag = 0 , idx = 0 for each bit i ∈ s 1 do if s 1[ i ] = s 2[ i ] then flag ++, idx = i if flag == 1 then return merge s2 to s1 and s1[ idx ] →-Function XOR/XNOR logic check( s 1 , s 2 ) : f1 = 0, f2 = 0, s = {} for each bit i ∈ s 1 do if ( s 1[ i ] , s 2[ i ]) == (0 , 1) then f 1 ++, add i into s if ( s 1[ i ] , s 2[ i ]) == (1 , 0) then f 2 ++, add i into s if f 2 == 2 or f 2 == 2 then return merge s2 to s1 and for j ∈ s s1[j] →glyph[circleminus] if f 1 == 1 and f 2 == 1 then return merge s2 to s1 and for j ∈ s s1[j] →⊕ Function MAJ logic check( s 1 , s 2 , s 3 ) : f 1 = 0 , f 2 = 0 , f 3 = 0 , s = {} for each bit i ∈ s 1 do if ( s 1[ i ] , s 2[ i ] , s 3[ i ]) == (1 , 1 , -) then f 1 ++, add i into s if ( s 1[ i ] , s 2[ i ] , s 3[ i ]) == (1 , -, 1) then f 2 ++, add i into s if ( s 1[ i ] , s 2[ i ] , s 3[ i ]) == ( -, 1 , 1) then f 3 ++, add i into s if f 1 == 1 and f 2 == 1 and f 3 == 1 then return merge s2,s3 to s1 and for j ∈ s s1[j] → glyph[star]
```

- (3) Regenerate c j ∗ n from the optimal Boolean function of c j n : K value only limits the number of leaf nodes in the K -feasible cut searching, which means that each leaf node can exist at a variety of logic levels. Considering c 2 H in Fig. 6, the regenerated cut circuit c 2 ∗ H is a 3-input AND gate from H = ADF , the optimal Boolean function of c 2 H . It seems to

make a dramatic improvement in PND value by lowering it to 12. Nevertheless, c 2 ∗ H increases the overhead in Josephson Junctions as 2 DFFs are required to balance the path-depth of nodes A and D. The PND value surges to 56 which is even higher than c 2 H (42). Therefore, it is essential to regenerate c j ∗ n by taking into account the logic levels of leaf nodes in c j n .

(4) Compare the PND value of c j ∗ n with c j n , update c rep n , and modify the node n with its representative cut c rep n : The regenerate cut c j ∗ n and cut c j n signify the a cut pair. The improvement in each pair is calculated using the following equation.

<!-- formula-not-decoded -->

where d j n is the improvement value of PND value between c j n and c j ∗ n , and P() is the PND values computed by Eq. (1). If d j n in has the largest value among all cut pairs ( c i n , c i ∗ n ), c i n ∈ K n , which indicates c j ∗ n has the greatest positive improvement in PND value compared with c j n , and then c j ∗ n is updated to the representative cut c rep n . If none of the c j ∗ n can improve the PND value for node n , the c rep n is set to null. The node n is modified with its representative cut c rep n to minimize the PND value of network C after all its cuts c j n ∈ K n has been traversed. If none of the nodes in the network are modified, this indicates that the network is already the optimal mapping solution after the pre-process stage.

## B. Theoretical Analysis

The optimal solution for mapping the network C is formalized with the following equations:

1) Compute the representative cut c rep n of node n :

<!-- formula-not-decoded -->

2) Update each node with its representative cut:

<!-- formula-not-decoded -->

## Theorem 1. The objective function Eq. (2) is submodular.

proof. For a given network C with node set N , we define two sets of nodes can generate representative cuts by our framework, α ⊆ { a 1 , . . . , a n } , β ⊆ { b 1 , . . . , b n } where both sets α, β ⊆ Ω and Ω is the solution space of the problem, and we define f ( x ) as the objective function in Eq. (2). If α ∩ β = glyph[epsilon1] , there exists glyph[epsilon1] = ∅ .

<!-- formula-not-decoded -->

On the basis of the preceding equation, we can deduce that the objective function is submodular. Due to for any two sets α, β ⊆ Ω , f ( α ) + f ( β ) = f ( α ∩ β ) + f ( α ∪ β ) .

Theorem 2. The objective function Eq. (2) is monotonic.

proof. For a network C with node set N , we define an arbitrary node set can generate representative cuts by our framework α ′ = α ∪ τ , we can get f ( α ∪ τ ) -f ( α ) ≥ 0 .

<!-- formula-not-decoded -->

## C. Pre-Process

We introduce our mapping algorithm in the previous section. However, the framework needs to pre-process the netlist before the mapping optimization by interpreting the netlist to an SFQ circuit-based network whose nodes represent the logic gates in the netlist. These two steps are needed in the pre-process stage of this representation scheme: 1) Gate conversion: convert all the gates in the netlist to the existing cells in the cell library. Assume the input netlist contains NAND gates that are not included in our cell library. Therefore, each NAND gate is converted to an AND gate and a new INV node is concatenated. In a similar fashion, the conversion function modifies XNOR and NOR gates. In addition, due to the cell library's constraint, the AND/OR gate's fan-ins can not exceed four. The higher fan-in gates are transformed into gate trees by their lower fan-in counterparts; 2) Splitter insertion: Section II-A1 presents the fan-out characteristic of the SFQ circuits. A splitter binary tree must be inserted into each node with a fan-out greater than two. Algorithm 3 includes extensive descriptions of the gate conversion and splitter insertion.

Algorithm 3: SFQ circuit unique characteristics modifications

glyph[negationslash]

<!-- image -->

glyph[negationslash]

## D. Post-Process

In the post-process, the framework needs to modify the network with property in Section II-A3: all fan-ins of each gate should have the same delay (clock phases). This modification is delegated to the process behind the optimization in order to prevent duplicate cut searching and computation. As a result of path-depth balancing, DFFs have the same cuts as their fan-in nodes by considering the nodes I and H in Fig. 6. The pseudocode of path-depth balancing is also listed in Algorithm 3.

Fig. 7: Merging &amp; replacing example, fan-ins of target gate has 2, 3, 3 DFFs, respectively. This process can reduce #(DFFs+INVs) amount by 50% in this specific case.

<!-- image -->

Additionally, since DFF consumes more #JJs than INV, a merging &amp; replacing process is used to further minimize path-depth balancing DFFs consumption. The framework only processes the DFFs inserted by the path-depth balancing algorithm in this stage, the DFFs that are contained in the input netlist are not changed to retain the correct logic function of the network. For each cell, if all of its fan-ins have at least y DFFs inserted, y is the shared number of DFFs for this gate. So all its fan-ins can remove y DFFs, and then insert y DFFs to its fan-outs without logic change. In the meantime, for each path, if there are x path-depth balancing DFFs inserted ( x &gt; 2 ), the x -( x %2) DFFs is replaced with INVs. As shown in Fig. 7, three fan-ins to the target gate have 2, 3, and 3 DFFs, respectively. This structure can be simplified by relocating two DFFs to the target gate's fan-out path, reducing the number of DFFs (#DFFs) at the fan-ins to 0, 1, and 1, respectively, and then replacing the DFFs at the fan-out path with INVs. This step ensures that the total number of path-depth balancing DFF is as low as possible while also mitigating the effects of non-idealities in the circuit.

## VIII. EVALUATION

In this section, we provide two experiment setups and experimental results to validate the effectiveness of our proposed framework, several ISCAS arithmetic benchmark circuits [30] for testing our developed framework The pseudo-code of our proposed framework is shown in Algorithm.4. First, we present

TABLE I: Experimental Results for proposed framework in different K values. 3 -denotes K = 3 and the merging &amp; replacing process is disabled.

| K       |   Logical Depth |   #JJs |   PND( × 10 5 ) |   #(DFFs+INVs) |
|---------|-----------------|--------|-----------------|----------------|
| K = 3 - |            46.7 | 108662 |           63.48 |          11247 |
| K = 4 - |            44.8 | 106253 |           62.42 |          10943 |
| K = 3   |            46.1 |  81401 |           45.71 |          11032 |
| K = 4   |            44.8 |  80038 |           45    |          10733 |

## Algorithm 4: Mapping optimization

glyph[negationslash]

<!-- image -->

different K value experiments, where we compare the performance of different K values, as well as corresponding results without merging &amp; replacing processes. Then we compare our proposed framework and the state-of-the-art technology mapper.

1) K values test: In Section VII-A, we present the K -feasible cut finding algorithm and mapping optimization algorithm. We are now conducting an empirical evaluation of the proposed framework's output over a range of K values and the effects of the merging &amp; replacing process. The K value indicates the maximum fan-ins of the cut circuits; hence, the maximum K value is set to 4, which corresponds to the maximum fan-ins of the cells in our cell library. Table I shows the average results for 15 benchmark circuits listed in Table II, when the framework sets K value to 3 or 4, as well as their corresponding result without merging &amp; replacing process. As discussed in SectionVII, our developed technology mapper focuses on improving four critical parameters in SFQ circuits including logical depth, #JJs, PND and #(DFF+INV). In general, #DFFs metric is used to determine the overhead in the path-depth balancing. Due to the fact that our post-process algorithm substitutes the DFF for INV to achieve path-depth balancing under the permissible conditions. #(DFF+INV) substitutes #DFFs as a metric in our evaluation. The framework with K = 4 improves all the metrics compared with K = 3 . This is the reason that the result set from the cut searching algorithm with a larger K value is the super-set of the lower K value cut circuit sets. Specifically, it is capable of discovering additional cut circuits for the root node and regenerating a representative cut circuit with a lower PND value. The merging &amp; replacing process achieves comparable performance under the same logic result condition since DFFs with higher #JJs are replaced with INVs that require less #JJs, and the DFFs and INVs in the branches are merged to the root. This operation, on average, reduces #JJs by 24.88%.

2) Comparison with the state-of-the-art technology mapper: Table II shows the experimental results for our framework and two baseline mappers. The first baseline mapper is the input netlist B 1 applying our proposed SFQ unique characteristics modifications in Algorithm 3 to insert the DFFs and

TABLE II: Experimental Results for proposed framework F ( K = 4 ) and baselines ( B 1 : Input netlists, B 2 : SFQmap [20])

|          | Logical Depth   | Logical Depth   | Logical Depth   | #JJs    | #JJs    | #JJs   | PND( × 10 5 )   | PND( × 10 5 )   | PND( × 10 5 )   | #(DFFs+INVs)   | #(DFFs+INVs)   | #(DFFs+INVs)   |
|----------|-----------------|-----------------|-----------------|---------|---------|--------|-----------------|-----------------|-----------------|----------------|----------------|----------------|
| Circuits | B 1             | B 2             | F               | B 1     | B 2     | F      | B 1             | B 2 :           | F               | B 1            | B 2 :          | F              |
| b04      | 51              | 40              | 33              | 35297   | 30141   | 18532  | 18.0            | 12.1            | 6.12            | 3855           | 3294           | 2332           |
| b11      | 61              | 35              | 36              | 48190   | 31251   | 22636  | 29.4            | 10.9            | 8.15            | 5480           | 3267           | 3137           |
| c880     | 42              | 35              | 23              | 19764   | 14551   | 8380   | 8.3             | 5.1             | 1.93            | 2172           | 1566           | 1096           |
| c1355    | 44              | 14              | 12              | 33995   | 10915   | 7587   | 15.0            | 1.53            | 0.91            | 3792           | 1024           | 896            |
| c1908    | 68              | 52              | 50              | 70512   | 58294   | 25983  | 47.9            | 30.3            | 13.0            | 8436           | 6773           | 3963           |
| c2670    | 42              | 38              | 33              | 30768   | 29475   | 21998  | 12.9            | 11.2            | 7.3             | 3205           | 2970           | 2601           |
| c3540    | 75              | 64              | 58              | 65143   | 58443   | 39179  | 48.9            | 37.4            | 22.7            | 7215           | 6357           | 5320           |
| c5315    | 73              | 53              | 52              | 114273  | 91323   | 66002  | 83.4            | 48.4            | 34.3            | 12783          | 9784           | 9257           |
| c6288    | 246             | 168             | 168             | 402824  | 248038  | 166283 | 991             | 416.7           | 279.4           | 47935          | 28874          | 28159          |
| c7552    | 68              | 49              | 48              | 127514  | 106264  | 79554  | 86.7            | 52.7            | 38.2            | 13998          | 10981          | 10209          |
| s1423    | 67              | 59              | 57              | 82400   | 55746   | 30214  | 55.2            | 32.9            | 17.2            | 9723           | 6518           | 5174           |
| s1494    | 18              | 16              | 15              | 19328   | 20447   | 14721  | 3.48            | 3.27            | 2.21            | 1722           | 1774           | 1569           |
| s5378    | 33              | 30              | 26              | 58191   | 55137   | 37101  | 19.2            | 16.5            | 9.65            | 6490           | 6097           | 4354           |
| s35932   | 42              | 16              | 13              | 1121734 | 310597  | 239681 | 471.1           | 49.7            | 31.2            | 126866         | 26715          | 24724          |
| s38584   | 70              | 63              | 48              | 815009  | 727571  | 422713 | 570.5           | 458.3           | 202.9           | 89538          | 79792          | 58209          |
| Avg      | 66.7            | 48.8            | 44.8            | 202996  | 12312   | 80037  | 164.1           | 79.1            | 45.0            | 22881          | 13017          | 10773          |
| Imp(Avg) | ↑ 32.8%         | ↑ 8.2%          |                 | ↑ 60.5% | ↑ 35.0% |        | ↑ 72.5%         | ↑ 43.1%         |                 | ↑ 53.1%        | ↑ 17.5%        |                |

splitters. The second baseline is SFQmap B 2 [20], whose K value is set to 3 to maintain consistency with original works. We unify cell library for all mappers with the cell library presented in Section V to ensure fairness. The same metrics in the K value test are evaluated in this experiment. Our framework provides considerable improvements on all these critical parameters in all the benchmark circuits compared with B 1 . The logical Depth, #JJs, PND value, and #(DFFs+INVs) are reduced 32.8%, 60.5%, 72.5% and 53.1% on average, respectively. It is mainly because B 1 does not provide an efficient mapping algorithm to reduce the overhead.

In general, our framework F outperforms baseline SFQmap B 2 in terms of #JJs, PND value, and the sum of #DFFs and #INVs. This verifies our expectation that the proposed framework can reduce the number of Josephson Junctions (#JJs) and the product of total #JJs with logical depth (PND). On average, F reduces the logical depth of all benchmark circuits by 8.3% as compared to B 2 , the DFFs number and logical depth oriented optimization mapping algorithm. This demonstrates the advantage of our algorithm, which incorporates MAJ gates and regenerates the cut circuits based on the logic level of leaf nodes in the original circuit rather than simply minimizing the critical paths of the cut circuits with supergates. In circuit b11, F produces a mapping result that has a slightly greater logical depth than B 2 . This indicates that F as a multiple objective oriented optimization mapper, which engages in finding the mapping result by considering overall metrics. Therefore, it can expense logical depth in exchange for a result with a lower PND value. While it produces a result with a higher logical depth value, the PND value and #JJs are reduced significantly in b11.

To analyze whether the observed improvements in the comparison with the state-of-the-art technology mapper are primarily contributed by our mapping algorithm, we disable the merging &amp; replacing in F and then compare it with

TABLE III: Experimental Results for proposed framework F ( K = 4 -) and baseline ( B 2 : SFQmap [20])

| mapper   | Logical Depth   | #JJs    | PND( × 10 5 )   | #(DFFs+INVs)   |
|----------|-----------------|---------|-----------------|----------------|
| F        | 44.8            | 106253  | 62.42           | 10943          |
| B 2 :    | 48.8            | 123212  | 79.10           | 13017          |
| Imp(Avg) | ↑ 8.2%          | ↑ 13.7% | ↑ 21.1%         | ↑ 15.9%        |

SFQmap B 2 again. Due to the merging &amp; replacing operation can also contribute to the improvement in terms of #JJs reduction, that is illustrated in the K values test. Table III summarizes experimental results by average over the preceding 15 benchmark circuits. Although the optimizations in #JJs are suppressed without the merging &amp; replacing process, all other critical metrics, such as logical depth, PND value and #(DFFs+INVs) continue to improve significantly.

## IX. CONCLUSION

In this paper, we proposed a comprehensive logic synthesis framework that is capable of mapping a netlist to an optimal netlist compatible with the SFQ technology, and also proposed MAJ gate circuit configuration in SFQ circuits and applied it into our framework. Our proposed mapping optimization algorithm has proved its superiority against the baseline approaches in terms of reducing the overhead associated with path-depth balancing and product of Josephson Junction number with logical depth (PND) for all the tested benchmark circuits, thereby mitigating the non-idealities in these SFQ circuits. Experimental results compared with the state-of-theart technology mapper indicates that our framework reduces the logical depth, #(DFFs+INVs), #JJs, and PND by an average of 8.2%, 17.5%, 35.0%, and 43.1%, respectively over 15 benchmark circuits.

## REFERENCES

- [1] K. K. Likharev and V. K. Semenov, 'Rsfq logic/memory family: A new josephson-junction technology for sub-terahertz-clock-frequency digital systems,' IEEE Transactions on Applied Superconductivity , vol. 1, no. 1, pp. 3-28, 1991.
- [2] P. Bunyk, K. Likharev, and D. Zinoviev, 'Rsfq technology: Physics and devices,' International journal of high speed electronics and systems , vol. 11, no. 01, pp. 257-305, 2001.
- [3] K. Gaj, Q. Herr, and M. Feldman, 'Parameter variations and synchronization of rsfq circuits,' in Conference Series-Institute of Physics , vol. 148. IOP PUBLISHING LTD, 1995, pp. 1733-1736.
- [4] I. V. Vernik, Q. P. Herr, K. Gaij, and M. J. Feldman, 'Experimental investigation of local timing parameter variations in rsfq circuits,' IEEE transactions on applied superconductivity , vol. 9, no. 2, pp. 4341-4344, 1999.
- [5] S. Narasimha, B. Jagannathan, A. Ogino, D. Jaeger, B. Greene, C. Sheraw, K. Zhao, B. Haran, U. Kwon, A. Mahalingam et al. , 'A 7nm cmos technology platform for mobile and high performance compute application,' in 2017 IEEE International Electron Devices Meeting (IEDM) . IEEE, 2017, pp. 29-5.
- [6] S. K. Tolpygo, V. Bolkhovsky, T. J. Weir, L. M. Johnson, M. A. Gouker, and W. D. Oliver, 'Fabrication process and properties of fully-planarized deep-submicron nb/al -alo x /nb josephson junctions for vlsi circuits,' IEEE transactions on Applied Superconductivity , vol. 25, no. 3, pp. 112, 2014.
- [7] F. Wang and S. Gupta, 'Automatic test pattern generation for timing verification and delay testing of rsfq circuits,' in 2019 IEEE 37th VLSI Test Symposium (VTS) . IEEE, 2019, pp. 1-6.
- [8] M. E. Celik and A. Bozbey, 'A statistical approach to delay, jitter and timing of signals of rsfq wiring cells and clocked gates,' IEEE transactions on applied superconductivity , vol. 23, no. 3, pp. 1 701 3051 701 305, 2012.
- [9] G. D. Hachtel and F. Somenzi, Logic synthesis and verification algorithms . Springer Science &amp; Business Media, 2007.
- [10] L. Amar´ u, P.-E. Gaillardon, and G. De Micheli, 'Majority-inverter graph: A novel data-structure and algorithms for efficient logic optimization,' in 2014 51st ACM/EDAC/IEEE Design Automation Conference (DAC) . IEEE, 2014, pp. 1-6.
- [11] G. Krylov and E. G. Friedman, 'Asynchronous dynamic single-flux quantum majority gates,' IEEE Transactions on Applied Superconductivity , vol. 30, no. 5, pp. 1-7, 2020.
- [12] L. Amaru, P.-E. Gaillardon, and G. De Micheli, 'Majority-inverter graph: A new paradigm for logic optimization,' IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems , vol. 35, no. 5, pp. 806-819, 2015.
- [13] R. Cai, O. Chen, A. Ren, N. Liu, C. Ding, N. Yoshikawa, and Y. Wang, 'A majority logic synthesis framework for adiabatic quantum-fluxparametron superconducting circuits,' in Proceedings of the 2019 on Great Lakes Symposium on VLSI , 2019, pp. 189-194.
- [14] E. G. Friedman, 'Clock distribution networks in synchronous digital integrated circuits,' Proceedings of the IEEE , vol. 89, no. 5, pp. 665692, 2001.
- [15] R. L. Rudell, 'Logic synthesis for vlsi design,' Ph.D. dissertation, University of California, Berkeley, 1989.
- [16] A. Mishchenko, S. Cho, S. Chatterjee, and R. Brayton, 'Combinational and sequential mapping with priority cuts,' in 2007 IEEE/ACM International Conference on Computer-Aided Design . IEEE, 2007, pp. 354361.
- [17] J. Cong and Y. Ding, 'Flowmap: An optimal technology mapping algorithm for delay optimization in lookup-table based fpga designs,' IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems , vol. 13, no. 1, pp. 1-12, 1994.
- [18] S. Yamashita, K. Tanaka, H. Takada, K. Obata, and K. Takagi, 'A transduction-based framework to synthesize rsfq circuits,' in Asia and South Pacific Conference on Design Automation, 2006. IEEE, 2006, pp. 7-pp.
- [19] G. Pasandi and M. Pedram, 'Pbmap: A path balancing technology mapping algorithm for single flux quantum logic circuits,' IEEE Transactions on Applied Superconductivity , vol. 29, no. 4, pp. 1-14, 2018.
- [20] G. Pasandi, A. Shafaei, and M. Pedram, 'Sfqmap: A technology mapping tool for single flux quantum logic circuits,' in 2018 IEEE International Symposium on Circuits and Systems (ISCAS) . IEEE, 2018, pp. 1-5.
- [21] N. Katam, A. Shafaei, and M. Pedram, 'Design of complex rapid singleflux-quantum cells with application to logic synthesis,' in 2017 16th

International Superconductive Electronics Conference (ISEC) . IEEE, 2017, pp. 1-3.

- [22] C. E. Leiserson and J. B. Saxe, 'Retiming synchronous circuitry,' Algorithmica , vol. 6, no. 1, pp. 5-35, 1991.
- [23] A. Mishchenko et al. , 'Abc: A system for sequential synthesis and verification,' URL http://www. eecs. berkeley. edu/alanmi/abc , vol. 17, 2007.
- [24] C. S. Lent and P. D. Tougaw, 'A device architecture for computing with quantum dots,' Proceedings of the IEEE , vol. 85, no. 4, pp. 541-557, 1997.
- [25] T. Oya, T. Asai, T. Fukui, and Y. Amemiya, 'A majority-logic nanodevice using a balanced pair of single-electron boxes,' Journal of nanoscience and nanotechnology , vol. 2, no. 3-4, pp. 333-342, 2002.
- [26] T. Sasao, Switching theory for logic synthesis . Springer Science &amp; Business Media, 2012.
- [27] N. K. Katam and M. Pedram, 'Logic optimization, complex cell design, and retiming of single flux quantum circuits,' IEEE Transactions on Applied Superconductivity , vol. 28, no. 7, pp. 1-9, 2018.
- [28] E. J. McCluskey, 'Minimization of boolean functions,' The Bell System Technical Journal , vol. 35, no. 6, pp. 1417-1444, 1956.
- [29] G. De Micheli, Synthesis and optimization of digital circuits . McGraw Hill, 1994, no. BOOK.
- [30] F. Brglez, D. Bryan, and K. Kozminski, 'Combinational profiles of sequential benchmark circuits,' in IEEE International Symposium on Circuits and Systems, . IEEE, 1989, pp. 1929-1934.