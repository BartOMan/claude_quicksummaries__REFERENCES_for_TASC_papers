COURSE 1

## SUPERCONDUCTING QUBITS AND THE PHYSICS OF JOSEPHSON JUNCTIONS

JOHN M. MARTINIS

National Institute of Standards and Technology, 325 Broadway, Boulder, CO 80305-3328, USA

PHOTO: height 7.5cm, width 11cm

## Contents

|   1 | Introduction                                                  |   3 |
|-----|---------------------------------------------------------------|-----|
|   2 | The Nonlinear Josephson Inductance                            |   4 |
|   3 | Phase, Flux, and Charge Qubits                                |   6 |
|   4 | BCS Theory and the Superconducting State                      |   9 |
|   5 | The Josephson Effect, Derived from Perturbation Theory        |  14 |
|   6 | The Josephson Effect, Derived from Quasiparticle Bound States |  20 |
|   7 | Generation of Quasiparticles from Nonadiabatic Transitions    |  25 |
|   8 | Quasiparticle Bound States and Qubit Coherence                |  29 |
|   9 | Summary                                                       |  30 |
|  10 | Acknowledgements                                              |  30 |

## SUPERCONDUCTING QUBITS AND THE PHYSICS OF JOSEPHSON JUNCTIONS

John M. Martinis 1 , Kevin Osborne 1

## 1 Introduction

Josephson junctions are good candidates for the construction of quantum bits (qubits) for a quantum computer [1]. This system is attractive because the low dissipation inherent to superconductors make possible, in principle, long coherence times. In addition, because complex superconducting circuits can be microfabricated using integrated-circuit processing techniques, scaling to a large number of qubits should be relatively straightforward. Given the initial success of several types of Josephson qubits [2-10], a question naturally arises: what are the essential components that must be tested, understood, and improved for eventual construction of a Josephson quantum computer?

In this paper we focus on the physics of the Josephson junction because, being nonlinear, it is the fundamental circuit element that is needed for the appearance of usable qubit states. In contrast, linear circuit elements such as capacitors and inductors can form low-dissipation superconducting resonators, but are unusable for qubits because the energy-level spacings are degenerate. The nonlinearity of the Josephson inductance breaks the degeneracy of the energy level spacings, allowing dynamics of the system to be restricted to only the two qubit states. The Josephson junction is a remarkable nonlinear element because it combines negligible dissipation with extremely large nonlinearity - the change of the qubit state by only one photon in energy can modify the junction inductance by order unity!

Most theoretical and experimental investigations with Josephson qubits assume perfect junction behavior. Is such an assumption valid? Recent experiments by our group indicate that coherence is limited by microwavefrequency fluctuations in the critical current of the junction [10]. A deeper

1 National Institute of Standards and Technology, 325 Broadway, Boulder, CO 803053328, USA

understanding of the junction physics is thus needed so that nonideal behavior can be more readily identified, understood, and eliminated. Although we will not discuss specific imperfections of junctions in this paper, we want to describe a clear and precise model of the Josephson junction that can give an intuitive understanding of the Josephson effect. This is especially needed since textbooks do not typically derive the Josephson effect from a microscopic viewpoint. As standard calculations use only perturbation theory, we will also need to introduce an exact description of the Josephson effect via the mesoscopic theory of quasiparticle bound-states.

The outline of the paper is as follows. We first describe in Sec. 2 the nonlinear Josephson inductance. In Sec. 3 we discuss the three types of qubit circuits, and show how these circuits use this nonlinearity in unique manners. We then give a brief derivation of the BCS theory in Sec. 4, highlighting the appearance of the macroscopic phase parameter. The Josephson equations are derived in Sec. 5 using standard first and second order perturbation theory that describe quasiparticle and Cooper-pair tunneling. An exact calculation of the Josephson effect then follows in Sec. 6 using the quasiparticle bound-state theory. Section 7 expands upon this theory and describes quasiparticle excitations as transitions from the ground to excited bound states from nonadiabatic changes in the bias. Although quasiparticle current is typically calculated only for a constant DC voltage, the advantage to this approach is seen in Sec. 8, where we qualitatively describe quasiparticle tunneling with AC voltage excitations, as appropriate for the qubit state. This section describes how the Josephson qubit is typically insensitive to quasiparticle damping, even to the extent that a phase qubit can be constructed from microbridge junctions.

## 2 The Nonlinear Josephson Inductance

A Josephson tunnel junction is formed by separating two superconducting electrodes with an insulator thin enough so that electrons can quantummechanically tunnel through the barrier, as illustrated in Fig. 1 . The Josephson effect describes the supercurrent I J that flows through the junction according to the classical equations

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- image -->

where Φ 0 = h/ 2 e is the superconducting flux quantum, I 0 is the criticalcurrent parameter of the junction, and δ = φ L -φ R and V are respectively the superconducting phase difference and voltage across the junction. The

Fig. 1. Schematic diagram of a Josephson junction connected to a bias voltage V . The Josephson current is given by I J = I 0 sin δ , where δ = φ L -φ R is the difference in the superconducting phase across the junction.

dynamical behavior of these two equations can be understood by first differentiating Eq. 2.1a and replacing dδ/dt with V according to Eq. 2.1b

<!-- formula-not-decoded -->

With dI J /dt proportional to V , this equation describes an inductor. By defining a Josephson inductance L J according to the conventional definition V = L J dI J /dt , one finds

<!-- formula-not-decoded -->

The 1 / cos δ term reveals that this inductance is nonlinear. It becomes large as δ → π/ 2, and is negative for π/ 2 &lt; δ &lt; 3 π/ 2. The inductance at zero bias is L J 0 = Φ 0 / 2 πI 0 .

An inductance describes an energy-conserving circuit element. The energy stored in the junction is given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

This calculation of energy can be generalized for other nondissipative circuit elements. For example, a similar calculation for a current bias gives U bias = -( I Φ 0 / 2 π ) δ . Conversely, if a circuit element has an energy U ( δ ), then the current-phase relationship of the element, analogous to Eq. 2.1a, is

<!-- formula-not-decoded -->

<!-- image -->

<!-- image -->

The classical and quantum behavior of a particular circuit is described by a Hamiltonian, which of course depends on the exact circuit configuration. The procedure for writing down a Hamiltonian for an arbitrary circuit has been described in detail in a prior publication [11]. The general form of the Hamiltonian for the Josephson effect is H J = U J .

## 3 Phase, Flux, and Charge Qubits

A Josephson qubit can be understood as a nonlinear resonator formed from the Josephson inductance and its junction capacitance. nonlinearity is crucial because the system has many energy levels, but the operating space of the qubit must be restricted to only the two lowest states. The system is effectively a two-state system [12] only if the frequency ω 10 that drives transitions between the qubit states 0 ←→ 1 is different from the frequency ω 21 for transitions 1 ←→ 2.

We review here three different ways that these nonlinear resonators can be made, and which are named as phase, flux, or charge qubits.

The circuit for the phase-qubit circuit is drawn in Fig. 2(a). Its Hamiltonian is where C is the capacitance of the tunnel junction. A similar circuit is drawn for the flux-qubit circuit in Fig. 2(b), and its Hamiltonian is

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The charge qubit has a Hamiltonian similar to that in Eq. 3.1, and is described elsewhere in this publication. Here we have explicitly used notation appropriate for a quantum description, with operators charge ̂ Q and phase difference ̂ δ that obey a commutation relationship [ ̂ δ, ̂ Q ] = 2 ei . Note that the phase and flux qubit Hamiltonians are equivalent for L →∞ and I = Φ /L , which corresponds to a current bias created from an inductor with infinite impedance.

The commutation relationship between ̂ δ and ̂ Q imply that these quantities must be described by a wavefunction. The characteristic widths of this wavefunction are controlled by the energy scales of the system, the charging energy of the junction E C = e 2 / 2 C and the Josephson energy E J = I 0 Φ 0 / 2 π . When the energy of the junction dominates, E J /greatermuch E C ,

Fig. 2. Comparison of the phase (a), flux (b), and charge (c) qubits. Top row illustrates the circuits, with each 'X' symbol representing a Josephson juncton. Middle row has a plot of the Hamiltonian potential (thick line), showing qualitatively different shapes for three qubit types. Ground-state wavefunction is also indicated (thin line). Key circuit parameters are listed in next row. Lowest row indicates variations on the basic circuit, as discussed in text. The lowest three energy levels are illustrated for the phase qubit (dotted lines).

then ̂ δ can almost be described classically and the width of its wavefunction is small 〈 ̂ δ 2 - 〈 ̂ δ 〉 2 〉 /lessmuch 1. In contrast, the uncertainty in charge is large 〈 Q 2 -〈 Q 〉 2 〉 /greatermuch (2 e ) 2 .

̂ ̂ If the Josephson inductance is constant over the width of the ̂ δ wavefunction, then a circuit is well described as a L J -C harmonic oscillator, and the qubit states are degenerate and not usable. Usable states are created only when the Josephson inductance changes over the δ -wavefunction.

The most straightforward way for the wavefunction to be affected by the Josephson nonlinearity is for ̂ δ to have a large width , which occurs when E J ∼ E C . A practical implementation of this circuit is illustrated in Fig 2(c), where a double-junction Coulomb blockade device is used instead of a single junction to isolate dissipation from the leads [2, 4]. Because the wavefunction extends over most of the -cos ̂ δ Hamiltonian, the transition frequency ω 10 can differ from ω 21 by more than 10 %, creating usable qubit states [13].

Josephson qubits are possible even when E J /greatermuch E C , provided that the junction is biased to take advantage of its strong nonlinearity. A good example is the phase qubit [6], where typically E J ∼ 10 4 E C , but which is biased near δ /lessorapproxeql π/ 2 so that the inductance changes rapidly with δ (see Eq.2.3a). Under these conditions the potential can be accurately described

by a cubic potential, with the barrier height ∆ U → 0 as I → I 0 . Typically the bias current is adjusted so that the number of energy levels in the well is ∼ 3 -5, which causes ω 10 to differ from ω 21 by an acceptably large amount ∼ 5 %.

Implementing the phase qubit is challenging because a current bias is required with large impedance. This impedance requirement can be met by biasing the junction with flux through a superconducting loop with a large loop inductance L , as discussed previously and drawn in Fig. 2(a). To form multiple stable flux states and a cubic potential, the loop inductance L must be chosen such that L /greaterorsimilar 2 L J 0 . We have found that a design with L /similarequal 4 . 5 L J 0 is a good choice since the potential well then contains the desired cubic potential and only one flux state into which the system can tunnel, simplifying operation.

The flux qubit is designed with L /lessorapproxeql L J 0 and biased in flux so that 〈 ̂ δ 〉 = π . Under these conditions the Josephson inductance is negative and is almost canceled out by L . The small net negative inductance near ̂ δ = π turns positive away from this value because of the 1 / cos δ nonlinearity, so that the final potential shape is quartic, as shown in Fig. 2(b). An advantage of the flux qubit is a large net nonlinearity, so that ω 10 can differ from ω 21 by over 100 %.

The need to closely tune L with L J 0 has inspired the invention of several variations to the simple flux-qubit circuit, as illustrated in Fig. 2(b). One method is to use small area junctions [7] with E J ∼ 10 E C , producing a large width in the ̂ δ wavefunction and relaxing the requirement of close tuning of L with L J 0 . Another method is to make the qubit junction a two-junction SQUID, whose critical current can then be tuned via a second flux-bias circuit [14, 15]. Larger junctions are then permissible, with E J ∼ 10 2 E C to 10 3 E C . A third method is to fabricate the loop inductance from two or more larger critical-current junctions [16]. These junctions are biased with phase less than π/ 2, and thus act as positive inductors. The advantage to this approach is that junction inductors are smaller than physical inductors, and fabrication imperfections in the critical currents of the junctions tend to cancel out and make the tuning of L with L J 0 easier.

In summary, the major difference between the phase, flux, and charge qubits is the shape of their nonlinear potentials, which are respectively cubic, quartic, and cosine. It is impossible at this time to predict which qubit type is best because their limitations are not precisely known, especially concerning decoherence mechanisms and their scaling. However, some general observations can be made.

First, the flux qubit has the largest nonlinearity. This implies faster logic gates since suppressing transitions from the qubit states 0 and 1 to state 2 requires long pulses whose time duration scales as 1 / | ω 10 -ω 21 | [12]. The flux qubit allows operation times less than ∼ 1 ns, whereas for the

phase qubit 10 ns is more typical. We note, however, that this increase in speed may not be usable. Generating precise shaped pulses is much more difficult on a 1 ns time scale, and transmitting these short pulses to the qubit with high fidelity will be more problematic due to reflections or other imperfections in the microwave lines.

Second, the choice between large and small junctions involve tradeoffs. Large junctions ( E J /greatermuch E C ) require precise tuning of parameters ( L/L J 0 for the flux qubit) or biases ( I/I 0 for the phase qubit) to produce the required nonlinearity. Small junctions ( E J ∼ E C ) do not require such careful tuning, but become sensitve to 1 /f charge fluctuations because E C has relatively larger magnitude.

Along these lines, the coherence of qubits have been compared considering the effect of low-frequency 1 /f fluctuations of the critical current [17]. These calculations include the known scaling of the fluctuations with junction size and the sensitivity to parameter fluctuations. It is interesting that the calculated coherence times for the flux and phase qubits are similar. With parameters choosen to give an oscillation frequency of ∼ 1 GHz for the flux qubit and ∼ 10 GHz for the phase qubit, the number of coherent logic-gate operations is even approximately the same.

## 4 BCS Theory and the Superconducting State

A more complete understanding of the Josephson effect will require a derivation of Eqs. 2.1a and 2.1b. In order to calculate this microscopically, we will first review the BCS theory of superconductivity [18] using a 'pair spin' derivation that we believe is more physically clear than the standard energy-variational method. Although the calculation follows closely that of Anderson [19] and Kittel [20], we have expanded it slightly to describe the physics of the superconducting phase, as appropriate for understanding Josephson qubits.

In a conventional superconductor, the attractive interaction that produces superconductivity comes from the scattering of electrons and phonons. As illustrated in Fig. 3(a), to first order the phonon interaction scatters an electron from one momentum state to another. When taken to second order (Fig. 3(b)), the scattering of a virtual phonon produces a net attractive interaction between two pairs of electrons. The first-order phonon scattering rates are generally small, not because of the phonon matrix element, but because phase space is small for the final electron state. This implies that the energy of the second order interaction can be significant if there are large phase-space factors.

The electron pairs have the largest net interaction if every pair is allowed by phase space factors to interact with every other pair. This is explicitly

Fig. 3. Feynman diagram of electron-phonon interaction showing (a) first- and (b) second-order processes.

created in the BCS wavefunction by including only pair states (Cooper pairs) with zero net momentum. Under this assumption and using a second quantized notation where c † k is the usual creation operator for an electron state of wavevector k , the most general form for the electronic wavefunction is

<!-- formula-not-decoded -->

where u k and v k are real and correspond respectively to the probability amplitude for a pair state to be empty or filled, and are normalized by u 2 k + v 2 k = 1. For generality we have included a separate phase factor φ k for each pair. Because each pair state is described as a two state system, the wavefunction may also be described equivalently with a 'pair-spin' tensor product

<!-- formula-not-decoded -->

and the Hamiltonian given with Pauli matrices σ xk , σ yk , and σ zk .

The kinetic part of the Hamiltonian must give Ψ in the ground state with pairs occupied only for | k | &lt; k f , where k f is the Fermi momentum. If we define the kinetic energy of a single electron, relative to the Fermi energy, as ξ k , then the kinetic Hamiltonian for the pair state is

<!-- formula-not-decoded -->

The solution of H K Ψ = E k ± Ψ gives for the lowest energy, E k -, the values v k = 1 for | k | &lt; k f , and v k = 0 for | k | &gt; k f , as required. An energy E k + -E k -= 2 | ξ k | is needed for the excitation of pairs above the Fermi energy or the excitation of holes (removal of pairs) below the Fermi energy.

The potential part of the pair-spin Hamiltonian comes from the secondorder phonon interaction that both creates and destroys a pair, as illustrated

in Fig. 3(b). The Hamiltonian for this interaction is given by

<!-- formula-not-decoded -->

and can be checked to correspond to the second-quantization Hamiltonian H ∆ = -V ∑ c † k c † -k c k c -k by using the translation σ xk → c k c -k + c † k c † -k and σ yk → i ( c k c -k -c † k c † -k ).

We will first understand the solution to the Hamiltonian H K + H ∆ for the phase variables φ k . This Hamiltonian describes a bath of spins that are all coupled to each other in the x-y plane ( H ∆ ) and have a distribution of magnetic fields in the z-direction ( H K ). Because H ∆ is negative, each pair of spins becomes aligned with each other in the x-y plane, which implies that every spin in the bath has the same phase φ k . This condition explains why the BCS wavefunction has only one phase φ = φ k for all Cooper pairs [21]. Because there is no preferred direction in the x-y plane, the solution to the Hamiltonian is degenerate with respect to φ and the wavefunction for φ is separable from the rest of the wavefunction. Normally, this means that φ can be treated as a classical variable, as is done for the conventional understanding of superconductivity and the Josephson effects. For Josephson qubits, where φ must be treated quantum mechanically, then the behavior of φ is described by an external-circuit Hamiltonian, as was done in Sec. 3.

For a superconducting circuit, where one electrode is biased with a voltage V , the voltage can be accounted for with a gauge transformation on each electron state c † k → e i ( e/ /planckover2pi1 ) ∫ V dt c † k . The change in the superconducting state is thus given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The change in φ can be written equivalently as

<!-- formula-not-decoded -->

which leads to the AC Josephson effect.

The solution for u k and v k proceeds using the standard method of mean-

Fig. 4. Bloch sphere solution of the Hamiltonian ( σ x , σ y , σ z ) · ( B x , B y , B z ). The vector - → B gives the direction of the positive energy eigenstate.

field theory, with

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Using the standard definition of the gap potential, one finds

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

This Hamiltonian is equivalent to a spin 1/2 particle in a magnetic field, and its solution is well known. The energy eigenvalues of H Ψ = E k ± Ψ are given by the total length of the field vector,

<!-- formula-not-decoded -->

and the directions of the Bloch vectors describing the E k + and E k -eigenstates are respectively parallel and antiparallel to the direction of the field

vector, as illustrated in Fig. 4. The ground state solution Ψ k -is given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

with the last equation required for consistency. The excited state Ψ k + is similarly described, but with u k and v k interchanged and φ → φ + π .

At temperature T = 0 the energy gap ∆ may be solved by inserting the solutions for u k and v k into Eq. 4.12a

<!-- formula-not-decoded -->

Converting to an integral by defining a density of states N 0 at the Fermi energy, and introducing a cutoff of the interaction V at the Debye energy θ D , one finds the standard BCS result,

<!-- formula-not-decoded -->

Two eigenstates E k -and E k + have been determined for the pair Hamiltonian. Two additional 'quasiparticle' eigenstates must exist, which clearly have to be single-particle states. These states may be solved for using diagonalization techniques, giving

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Fortunately, these states may be easily checked by inspection. The kinetic part of the Hamiltonian gives H K Ψ k 0 , 1 = 0 since Ψ k 0 , 1 corresponds to the creation of an electron and a hole, and the electron-pair and hole-pair states have opposite kinetic energy. The potential part of the energy also gives 〈 H ∆ 〉 Ψ k 0 , 1 = 0 since the interaction Hamiltonian scatters pair states. Thus the eigenenergies of Ψ k 0 , 1 are zero, and these states have an energy E k = | E k -| above the ground state.

The quasiparticle operators that take the ground-state wavefunction to the excited states are

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Fig. 5. Energy-level diagram for the ground-pair state (solid line), two quasiparticle states (dashed lines), and the excited-pair state (short dashed line).

which can be easily checked to give

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

A summary of these results is illustrated in Fig. 5, where we show the energy levels, wavefunctions, and operators for transitions between the four states. The quasiparticle raising and lowering operators γ † k 0 , γ † k 1 , γ k 0 , and γ k 1 produce transitions between the states and have orthogonality relationships similar to those of the electron operators.

It is interesting to note that the ground and excited pair states are connected by the two quasiparticle operators e -iφ γ † k 1 γ † k 0 Ψ k -= Ψ k + . Because the value u l v l changes sign between Ψ k -and Ψ k + , and is zero for Ψ k 0 , 1 , the gap equation 4.12a including the effect of quasiparticles is proportional to 〈 1 -γ † k 0 γ k 0 -γ † k 1 γ k 1 〉 . Along with the energy levels, these results imply that the two types of quasiparticles are independent excitations.

## 5 The Josephson Effect, Derived from Perturbation Theory

We will now calculate the quasiparticle and Josephson current for a tunnel junction using first and second order perturbation theory, respectively. We note that our prior calculations have not been concerned with electrical transport. In fact, the electron operators describing the superconducting state have not been influenced by charge, and thus they correspond to the occupation of an effectively neutral state. Because a tunneling event involves a real transfer of an electron, charge must now be accounted for

properly. We will continue to use electron operators for describing the states, but will keep track of the charge transfer separately.

When an electron tunnels through the barrier, an electron and hole state is created on the opposite (left and right) side of the barrier. The tunneling Hamiltonian for this process can be written as

<!-- formula-not-decoded -->

where t LR is the tunneling matrix element, and the L and R indices refer respectively to momentum states k on the left and right superconductor. The first two terms - → H T + and - → H T -correspond to the tunneling of one electron from left to the right, whereas ← -H T + and ← -H T -are for tunneling to the left. The Hamiltonian is explicitly broken up into - → H T + and - → H T -to account for the different electron operators c † k and c † -k for positive and negative momentum.

The electron operators must first be expressed in terms of the quasiparticle operators γ because these produce transitions between eigenstates of the superconducting Hamiltonian. Equations 4.20, 4.21, and their adjoints are used to solve for the four electron operators

<!-- formula-not-decoded -->

Substituting Eqs. 5.2 into 5.1b, one sees that all four terms of the Hamiltonian have operators γ † that produce quasiparticles. We calculate here to first order the quasiparticle current from L to R given by - → H T + + - → H T -. The Feynman diagrams (a) and (b) in Fig. 6 respectively describe the tunneling Hamiltonian for the - → H T + and - → H T -terms. In this diagram a solid line represents a Cooper pair state in the ground state, whereas a quasiparticle state is given by a dashed line. Only one pair participates in the tunneling interaction, so only one of the three solid lines is converted to a dashed line. The line of triangles represents the tunneling event and is labeled with its corresponding H T Hamiltonian, with the direction of the triangles indicating the direction of the electron tunneling. The c † k operators, acting on the L or R lead, is rewritten in terms of the γ operators and placed above or below the vertices. Since only γ † operators give a nonzero term when acting on the ground state, the effect of the interaction is to produce final states Ψ L,R f with total energy E R + E L , and with amplitudes given at the right of the figure.

The two final states in Fig 6(a) and (b) are orthogonal, as well as states involving different values of L and R . The total current is calculated as

Fig. 6. First-order Feynmann diagrams for interaction - → H T + (a) and - → H T -(b). Solid lines are Cooper-pair states, dashed lines are quasiparticle excitations, and arrow-lines represents tunneling interaction. Electron operators arising from interaction are displayed next to vertices.

an incoherent sum over all possible final quasiparticle states, under the condition that the total quasiparticle energy for the final state is equal to the energy gained by the tunneling of the electron

<!-- formula-not-decoded -->

The total current from L to R is given by e multiplied by the transition rate

<!-- formula-not-decoded -->

where in the last equation we have expressed the conservation of energy with a Dirac δ -function, and have assumed matrix elements | t | 2 of constant strength. Because E ( ξ k ) = E ( -ξ k ) and u k ( ξ k ) = v k ( -ξ k ), one finds

<!-- formula-not-decoded -->

This result is equivalent to the standard 'semiconductor model' of the quasiparticle current, which predicts no current for V &lt; 2∆ /e , a rapid rise of current at 2∆ /e , and then a current proportional to V at large voltages. Note that Eq. 5.4c has a sum over the occupation probability v 2 L of the pair state and the occupation probability u 2 R of a hole-pair state, as is expected given the operators c L c † R in the tunneling Hamiltonian. The final result of Eq. 5.5a does not have these factors because the occupation probability is unity when summed over the ± ξ k states.

It is convenient to express the tunneling matrix element in terms of the normal-state resistance of the junction, obtained by setting ∆ = 0 , with the equation

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

We now calculate the tunneling current with second-order perturbation theory. The tunneling Hamiltonian, taken to second order, gives

<!-- formula-not-decoded -->

where /epsilon1 i is the energy of the intermediate state i . Because the terms in H T have both γ † and γ operators, the second-order Hamiltonian gives a nonzero expectation value for the ground state. This is unlike the first-order theory, which produces current only through the real creation of quasiparticles.

Because H T has terms that transfer charge in both directions, H T H T will produce terms which transfer two electrons to the right, two to the left, and with no net transfer. With no transfer, a calculation of the secondorder energy gives a constant value, which has no physical effect. We first

Fig. 7. Second-order Feynman diagrams for the transfer of two electrons across the junction. Only nonzero operators are displayed next to vertices.

calculate terms for transfer to the right from ( - → H T + + - → H T -)( - → H T + + - → H T -), which gives nonzero expectation values only for - → H T + - → H T -+ - → H T -- → H T + . The Feynman diagrams for these two terms are given in Fig. 7(a) and (b), where we have displayed only the amplitudes from the nonzero operators. The expectation value of these two Hamiltonian terms is given by

<!-- formula-not-decoded -->

where we have used t ∗ LR = t -L -R and assumed the same gap ∆ for both superconductors. A similar calculation for transfer to the left gives the complex conjugate of Eq. 5.8e. The sum of these two energies gives the Josephson energy U J , and using Eq. 2.5, the Josephson current I J ,

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where R K = h/e 2 is the resistance quantum. Equation 5.10 is the standard Ambegaokar-Baratoff formula [22] for the Josephson current at zero temperature.

The Josephson current is a dissipationless current because it arises from a new ground state of the two superconductors produced by the tunneling interaction. This behavior is in contrast with quasiparticle tunneling, which is dissipative because it produces excitations. It is perhaps surprising that a new ground state can produce charge transfer through the junction. This is possible only because the virtual quasiparticle excitations are both electrons and holes: the electron-part tunnels first through the junction, then the hole-part tunnels back. Only states of energy ∆ around the Fermi energy are both electron- and hole-like, as weighted by the ( v R u R )( u L v L ) term in the integral.

The form of the Josephson Hamiltonian can be understood readily by noting that the second-order Hamiltonian,

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

corresponds to the pair-scattering Hamiltonian of Eq. 4.4. Comparing with the gap-equation solution, one expects U J ∼ | t | 2 ∆cos δ , where the cos δ term arises from the spin-spin interaction in the x-y plane.

We would like to make a final comment on a similarity between the BCS theory and the Josephson effect. In both of these derivations we see that a dissipative process that is described in first-order perturbation theory, such as phonon scattering or quasiparticle tunneling, produces in second order a new collective superfluid behavior. This collective behavior emerges from a virtual excitation of the dissipative process. Dissipation is normally considered undesirable, but by designing systems to maximize dissipation, it may be possible to discover new quantum collective behavior.

With this understanding of the Josephson effect and quasiparticle tunneling, how accurate is the description of the Josephson junction with the

Hamiltonian corresponding to Eq. 5.9? There are several issues that need to be considered.

First, quasiparticle tunneling is a dissipative mechanism that produces decoherence. Although it is predicted to be absent for V &lt; 2∆ /e , measurements of real junctions show a small subgap current. This current is understood to arise from multiple Andreev reflections, which are described as higher-order tunneling processes. We thus need a description of the tunnel junction that easily predicts these processes for arbitrary tunneling matrix elements. This is especially needed as real tunnel junctions do not have constant matrix elements, as assumed above. Additionally, we would like to know whether a small number of major imperfections, such as 'pinhole' defects, will strongly degrade the coherence of the qubit.

Second, quasiparticle tunneling has been predicted for an arbitrary DC voltage across the junction. However, the qubit state has 〈 V 〉 = 0, but may excite quasiparticles with AC voltage fluctuations. This situation is difficult to calculate with perturbation theory. In addition, is it valid to estimate decoherence from quasiparticles at zero voltage simply from the junction resistance at subgap voltages?

Third, how will the Josephson effect and the qubit Hamiltonian be modified under this more realistic description of the tunnel junction?

All of these questions and difficulties arise because perturbation theory has been used to describe the ground state of the Josephson junction. The BCS theory gives basis states that best describe quasiparticle tunneling for large voltages, not for V → 0. A theory is needed that solves for the Josephson effect exactly , with this solution then providing the basis states for understanding quasiparticle tunneling around V = 0. This goal is fulfilled by the theory of quasiparticle bound states, which we will describe next.

## 6 The Josephson Effect, Derived from Quasiparticle Bound States

We begin our derivation of an exact solution for the Josephson effect with an extremely powerful idea from mesoscopic physics: electrical transport can be calculated under very general conditions by summing the current from a number of independent 'conduction channels', with the transport physics of each conduction channel determined only by its channel transmission probability τ i [23,24]. For a Josephson junction, the total junction current I j can be written as a sum over all channels i

<!-- formula-not-decoded -->

where I j ( τ ) is the current for a single channel of transmission τ , which may be solved for theoretically. For a tunnel junction, the number of channels is estimated as the junction area divided by the channel area ( λ f / 2) 2 ,

Fig. 8. Plot of potential vs. coordinate x with a positive delta-function tunnel barrier V 0 δ ( x ). Scattering of plane wave states is shown in (a), whereas (b) is a plot of the bound-state wavefunction. The delta-function barrier is negative in (b), as required for producing a bound state.

where λ f is the Fermi wavelength of the electrons. Of course, the difficulty of determining the distribution of the channel transmissions still remains. This often may be estimated from transport properties, and under some situations can be predicted from theory [25-27].

Because transport physics is determined only by scattering parameterized by τ , we may make two simplifying assumptions: the transport can be solved for using plane waves, and the scattering from the tunnel junction can be described by a delta function. The general theory has thus been transformed into the problem of one-dimensional scattering from a delta function, and an exact solution can be found by using a simple and clear physical picture.

Central to understanding the Josephson effect will be the quasiparticle bound state. To understand how to calculate a bound state [28,29], we will first consider a normal-metal tunnel junction and with a δ -function barrier V 0 δ ( x ), as illustrated in Fig. 8. For an electron of mass m and wavevector k , the wavefunctions on the left and right side of the barrier are

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where A , B , and C are respectively the incident, reflected, and transmitted electron amplitudes. From the continuity equations

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

evaluated at x = 0, the amplitudes are related by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Fig. 9. Plot of quasiparticle energies E κ verses momentum κ near the ± k f Fermi surfaces. The two-component eigenfunctions are also displayed for each of the four energy bands. Also indicated are the quasiparticle states A-E used for the bound-state calculation.

The transmission amplitude and the probability are

<!-- formula-not-decoded -->

∣ ∣ where η = mV 0 / /planckover2pi1 2 k . The bound state can be determined by finding the pole in the transmission amplitude. A pole describes how a state of finite amplitude may be formed around the scattering site with zero amplitude of the incident wavefunction, which is the definition of a bound state. The pole at η = i gives k b = -imV 0 / /planckover2pi1 2 , and a wavefunction around the scattering site Ψ R = Ce ( mV 0 / /planckover2pi1 2 ) x . This describes a bound state only when V 0 is negative, as expected.

<!-- formula-not-decoded -->

A superconducting tunnel junction will also have bound states of quasiparticles excitations. These bound states describe the Josephson effect since virtual quasiparticle tunneling was necessary for the perturbation calculation in the last section. The Bogoliubov-deGennes equations describe the spatial wavefunctions, whose eigenstates are given by the solution of the Hamiltonian

<!-- formula-not-decoded -->

where ϕ ± e iκx are the slowly varying spatial amplitudes of the exact wavefunction ϕ ± e iκx e ± ik f x . As illustrated in Fig. 9, the ± k f κ term corresponds to the kinetic energy at the ± k f Fermi surfaces using the approximation

( k f + κ ) 2 / 2 /similarequal const . + k f κ . As expected for a spin-type Hamiltonian, the two eigenvalues are

<!-- formula-not-decoded -->

where ξ κ = /planckover2pi1 2 k f κ/m is the kinetic energy of the quasiparticle referred to the Fermi energy. The eigenvectors are also displayed in Fig. 9, where u κ and v κ are given by Eqs. 4.14 and 4.15. Because the two energy bands represent quasiparticle excitations, the lower band is normally filled and its excitations correspond to the creation of hole states.

We can solve for the quasiparticle bound states by first writing down the scattering wavefunctions in the left and right superconducting electrodes. An incoming quasiparticle state, point A in Fig. 9, is reflected off the tunnel barrier to states B and C and is transmitted to states D and E [30]. The wavefunctions are then given by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where we have used the relations v ≡ v κ = u -κ and u ≡ u κ = v -κ , and we have included the phases φ L and φ R of the two states. The continuity conditions Eqs. 6.4 and 6.5, solved for both the components of the spin wavefunction, gives the matrix equation

<!-- formula-not-decoded -->

The scattering amplitudes for B -E have poles given by the solution of

<!-- formula-not-decoded -->

Using the relations u 2 + v 2 = 1, E J = E k = ∆ / 2 uv , and τ = 1 / (1 + η 2 ), the energies of the quasiparticle bound states are

<!-- formula-not-decoded -->

Because these two states have energies less than the gap energy ∆, they are energetically 'bound' to the junction and thus have wavefunctions that are localized around the junction.

The dependence of the quasiparticle bound-state energies on junction phase is plotted in Fig. 10 for several values of τ . The ground state is normally filled, similar to the filling of quasiparticle states of negative energy.

Fig. 10. Plot of quasiparticle bound-state energies E J -and E J + vs. the phase difference δ across the junction, for three values of tunneling transmission τ . Quasiparticles are produced by vertical transitions from the E J -to E J + band. As indicated by the arrow, the energy gap E J + -E J -is always greater than √ 2∆ at δ = π/ 2.

The energy E J -corresponds to the Josephson energy, as can be checked in the limit τ → 0 to give

<!-- formula-not-decoded -->

This result is equivalent to Eq. 5.9 after noting that the normal-state conductance of a single channel is 1 /R N = 2 τ/R K .

The current of each bound state is given by the derivative of its energy

<!-- formula-not-decoded -->

in accord with Eq. 2.5. Since the curvature of the upper band is opposite to that of the lower band, the currents of the two bands have opposite sign I J + = -I J -. For level populations of the two states given by f ± , the average Josephson current is 〈 I J 〉 = I J -( f --f + ). For a thermal population, f ± are given by Fermi distributions, and the Josephson current in the tunnel junction limit gives the expected Ambegaokar-Baratoff result

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Fig. 11. Plot of semiclassical solutions for the tunneling through a barrier (a) and tunneling through an energy gap (b). Imaginary solutions to k and δ are used to calculate the tunneling rates.

## 7 Generation of Quasiparticles from Nonadiabatic Transitions

In this description of the Josephson junction, the Josephson effect arises from a quasiparticle bound state at the junction. Two bound states exist and have energies E J + and E J -, with the Josephson current from the excited state being of opposite sign from that of the ground state. We will discuss here the small-voltage limit [31, 32], which can be fully understood within a semiclassical picture by considering that a linear increase in δ produces nonadiabatic transitions between the two states.

The junction creates 'free quasiparticles', those with E ≥ ∆, via a twostep process. First, a transition is made from the ground to the excited bound state. This typically occurs because a voltage is placed across the junction, and the linear change of δ causes the ground state not to adiabatically stay in that state. For a high-transmission channel, the transition is usually made around δ ≈ π , where the energy difference between the states is the lowest and the band bending is the highest. Because this excited state initially has energy less than ∆, the state remains bound until the phase changes to 2 π and the energy of the quasiparticle is large enough to become unbound and diffuse away from the junction. The quasiparticle generation rate is thus governed by dδ/dt and will increase as V increases.

The quasiparticle transition rate can be predicted using a simple semiclassical method. We will first review WKB tunneling in order to later generalize this calculation to energy tunnelling. In Fig. 11(a), we plot a cubic potential V ( x ) versus x and its solution k 2 = 2 m [ E -V ( x )] / /planckover2pi1 2 . The solution for k is real or imaginary depending on whether E is greater or less than V ( x ). A semi-classical description of the system is the particle oscillating in the well, as described by the loop in the solution of Re { k } . A solution in the imaginary part of k connects a turning point on this loop, labeled A, with the turning point of the free-running solution, labeled B.

The probability of tunneling each time the trajectory passes point A is given by the standard WKB integral of the imaginary action

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

The transition rate for a nonadiabatic change in a state may be calculated in a similar fashion. In Fig. 11(b) we plot the solution of Eq. 6.16 for δ versus E . In the 'forbidden' region of energy | E | &lt; ∆ √ 1 -τ , the solution of δ has an imaginary component. As the bias of the system changes and the system trajectory moves past point A, then this state can tunnel to point B via the connecting path in the imaginary part of δ . The probability for this event is given by Eq. 7.1 with S given by the integral of the imaginary action

<!-- formula-not-decoded -->

where we define an imaginary time by

<!-- formula-not-decoded -->

Rewriting Eq. 6.16 as ( E/ ∆) 2 = 1 -τ (1 -cos δ ) / 2 and using dδ/dt = (2 e/ /planckover2pi1 ) V , one finds the action is given by the integral

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where the last interpolation formula approximates well a numerical solution of Eq. 7.6. The limiting expression for τ → 1 gives the standard LandauZener formula appropriate for a two-state system. In the tunnel-junction limit τ → 0 one finds

For the case of a constant DC bias voltage V , the total junction current 〈 I j 〉 may be calculated with this transition rate and an attempt rate Γ = (2 e/h ) V given by the frequency at which δ passes π/ 2. Using Eq. 7.6 and

Fig. 12. (a) Plot of average junction current 〈 I j 〉 versus inverse DC voltage V for transmission coefficients τ = 0 . 8, 0 . 5, 0 . 2, and 0 . 01 (from Ref. [32] ). Solid lines are from exact calculation, and dashed lines are from predictons of Eqs. 7.8 and 7.6. The time dependence of the Josephson current I J is plotted for the ground state (b) and for a transition (c), where the insets show the trajectory of the bound states as E J vs . δ .

setting the power of quasiparticle generation 2∆Γ W to the electrical power 〈 I j 〉 V , one finds

<!-- formula-not-decoded -->

This prediction is plotted in Fig. 12(a) and shows very good agreement with the results of exact calculations [32]. Only the steps in voltage are not reproduced, which are understood as arising from the quantization of energy eV from multiple Andreev reflection of the quasiparticles. The steps are not expected to be reproduced by the semiclassical theory since this theory is an expansion around small voltages, or equivalently, large quantization numbers.

The junction current may also be determined from the energies of the two bound states. For a constant voltage across the junction, we use Eq. 2.5 to calculate the charge transferred across the junction after a phase

change of 2 π

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

which gives the expected result that the change of energy equals Q j V . When the junction remains in the ground state, the energy is constant U J (2 π ) -U J (0) = 0 and no net charge flows through the junction. Net charge is transferred, however, after a transition. The charge transfer 2∆ /V multiplied by the transition rate gives an average current Q j Γ W that is equivalent to Eq. 7.8.

Equation 6.18 may be used to calculate the time dependence of the Josephson current, as illustrated in Fig. 12(b) and (c). When the system remains in the ground state (b), the junction current is sinusoidal and averages to zero. For the case of a transition (c), the current before the transition is the same, but the Josephson current remains positive after the transition (see Eq. 5.4 of Ref. [32]). The transition itself also produces charge transfer from multiple-Andreev reflections(MAR) [31,33]

<!-- formula-not-decoded -->

This result is perhaps surprising - the junction current at finite voltage arises from transfer of charge Q MAR and a change in the Josephson current. The relative contribution of these two currents is determined by the relative size of the gap in the bound states. For τ → 1 , all of the junction current is produced by Josephson current, whereas for τ → 0 (tunnel junctions) the current comes from Q MAR .

For small voltages, the transition event must transfer a large amount of charge Q MAR in order to overcome the energy gap. In comparing this semiclassical theory with the exact MAR theory, Q MAR /e has an integer value and represents the order of the MAR process and the number of electrons that are transferred in the transition. This description is consistent with Eq. 7.7 describing the transition probability for an n -th order MAR process, where n = 2∆ /eV , and τ/ 2 represents the matrix element for each order.

From this example it is clearly incorrect to picture the quasiparticle and Josephson current as separate entities, as suggested by the calculations of perturbation theory. To do so ignores the fact that quasiparticle tunneling, arising from a transition between the bound states, also changes the Josephson contribution to the current from δ = π to 2 π .

## 8 Quasiparticle Bound States and Qubit Coherence

The quasiparticle bound-state theory can be used to predict both the Josephson and quasiparticle current in the zero-voltage state, as appropriate for qubits. In this theory an excitation from the E J -bound state to the E J + state is clearly deleterious as it will change the Josephson current, fluctuating the qubit frequency and producing decoherence in the phase of the qubit state. For an excitation in one channel, the fractional change in the Josephson current is ∼ 1 /N ch , where N ch is the number of conduction channels. The subgap current-voltage characteristics can be used to estimate N ch , which gives an areal density of ∼ 10 4 /µ m 2 [10,34]. For a charge qubit with junction area 10 -2 µ m 2 , the qubit frequency changes fractionally by ∼ 1 /N ch ∼ 10 -2 for a single excitation, and gives strong decoherence. Although the phase qubit has a smaller change (1 /N ch ) I 0 / 4( I 0 -I ) ∼ 2 × 10 -5 , the excitation of even a single bound state is clearly unwanted.

Fortunately, these quasiparticle bound states should not be excited in tunnel junctions by the dynamical behavior of the qubit. The E J -to E J + transition is energetically forbidden because the energy of the qubit states are typically choosen to be much less than 2∆. Thus, the energy gap of the superconductor protects the qubit from quasiparticle decoherence.

If a junction has 'pinhole' defects, where a few channels have τ → 1, then the energy gap will shrink to zero at δ = π . However, only the flux qubit will be sensitive to quasiparticles produced at these defects since it operates near δ = π . In contrast, the phase qubit always retains an energy gap of at least √ 2∆ around its operating point δ = π/ 2 (see arrow in Fig. 10). We note this idea implies that a phase qubit can even be constructed from a microbridge junction, which has some channels [26] with τ = 1. Although the phase qubit is completely insensitive to pinhole defects, this advantage is probably unimportant because Al-based tunnel junctions have oxide barriers of good quality.

Pinhole defects also change the Josephson potential away from the -cos δ form. This modification is typically unimportant because the deviation is smooth and can be accounted for by a small effective change in the critical current.

The concept that the energy gap ∆ protects the junction from quasiparticle transitions suggests that superconductors with nonuniform gaps may not be suitable for qubits. Besides the obvious problem of conduction channels with zero gap, channels with a reduced gap may cause stray quasiparticles to be trapped at the junction. The highT c superconductors, with the gap suppressed to zero at certain crystal angles, are an obvious undesirable candidate. However, even Nb could be problematic since it has several oxides that have reduced or even zero gap. Nb based tri-layers may also be undesirable since the thin Al layer near the junction slightly reduces

the gap around the junction. In contrast, Al may not have this difficulty since its gap increases with the incorporation of oxygen or other scattering defects. It is possible that these ideas explain why Nb-based qubits do not have coherence times as long as Al qubits [6,10].

## 9 Summary

In summary, Josephson qubits are nonlinear resonators whose critical element is the nonlinear inductance of the Josephson junction. The three types of superconducting qubits, phase, flux, and charge, use this nonlinearity differently and produce qubit states from a cubic, quartic, and cosine potential, respectively.

To understand the origin and properties of the Josephson effect, we have first reviewed the BCS theory of superconductivity. The superconducting phase was explicitly shown to be a macroscopic property of the superconductor, whose classical and quantum behavior is determined by the external electrical circuit. After a review of quasiparticle and Josephson tunneling, we argued that a proper microscopic understanding of the junction could arise only from an exact solution of the Josephson effect.

This exact solution was derived by use of mesoscopic theory and quasiparticle bound states, where we showed that Josephson and quasiparticle tunneling can be understood from the energy of the bound states and their transitions, respectively. A semiclassical theory was used to calculate the transition rate for a finite DC voltage, with the predictions matching well that obtained from exact methods.

This picture of the Josephson junction allows a proper understanding of the Josephson qubit state. We argue that the gap of the superconductor strongly protects the junction from quasiparticle tunneling and its decoherence. We caution that an improper choice of materials might give decoherence from quasiparticles that are trapped at sites near the junction.

We believe a key to future success is understanding and improving this remarkable nonlinearity of the Josephson inductance. We hope that the picture given here of the Josephson effect will help researchers in their quest to make better superconducting qubits.

## 10 Acknowledgements

We thank C. Urbina, D. Esteve, M. Devoret, and V. Shumeiko for helpful discussions. This work is supported in part by the NSA under contract MOD709001.

## References

- [1] M. A. Nielsen and I. L. Chuang, Quantum Computation and Quantum Information (Cambridge University Press, Cambridge, 2000).
- [2] Y. Nakamura, C. D. Chen, and J. S. Tsai, Phys. Rev. Lett. 79 , 2328 (1997).
- [3] Y. Nakamura, Y. A. Pashkin, T. Yamamoto, and J. S. Tsai, Phys. Rev. Lett. 88 , 047901 (2002).
- [4] D. Vion, A. Aassime, A. Cottet, P. Joyez, H. Pothier, C. Urbina, D. Esteve, and M. H. Devoret, Science 296 , 886 (2002).
- [5] S. Han, Y. Yu, Xi Chu, S. Chu, and Z. Wang, Science 293 , 1457 (2001); Y. Yu, S. Han, X. Chu, S. Chu, and Z. Wang, Science 296 , 889 (2002).
- [6] J. M. Martinis, S. Nam, J. Aumentado, and C. Urbina, Phys. Rev. Lett. 89 , 117901 (2002).
- [7] I. Chiorescu, Y. Nakamura, C. J. P. M. Harmans, and J. E. Mooij, Science 299 , 1869 (2003).
- [8] A.J. Berkley, H. Xu, R.C. Ramos, M.A. Gubrud, F.W. Strauch, P.R. Johnson, J.R. Anderson, A.J. Dragt, C.J. Lobb, and F.C.Wellstood, Science 300 , 1548 (2003).
- [9] Yu. A. Pashkin, T. Yamamoto, O. Astafiev, Y. Nakamura, D. V. Averin, and J. S. Tsai, Nature 421 , 823 (2003).
- [10] R. W. Simmonds, K. M. Lang, D. A. Hite, D. P. Pappas, and J. M. Martinis, submitted to Phys. Rev. Lett.
- [11] M.H. Devoret, Quantum Fluctuations in Electrical Circuits , in 'Fluctuations Quantiques', Elsevier Science (1997).
- [12] M. Steffen, J. M. Martinis, and I. L. Chuang, Phys. Rev. B 68 , 2245xx (2003).
- [13] Audrey Cottet, Ph.D. thesis (2002).
- [14] R. Rouse, S. Han, J. Lukens, Phys. Rev. Lett. 75 , 1614 (1995).
- [15] R. Koch, private communication.
- [16] J. E. Mooij, T. P. Orlando, L. Levitov, L. Tian, C. H. van der Wal, S. Lloyd, Science 285 , 1036 (1999)
- [17] D. J. VanHarlingen, B. L. T. Plourde, T. L. Robertson, P. A Reichardt, and J. Clarke, Proceedings of the 3rd International Workshop on Quantum Computing, to be published.
- [18] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, Phys. Rev. 108 , 1175 (1957).
- [19] P. W. Anderson, Phys. Rev. 112 , 1900 (1958).
- [20] C. Kittel, Quantum Theory of Solids , John Wiley (1987).
- [21] U. Eckern, G. Schon, V. Ambegaokar, Phys. Rev. B 30 , 6419 (1984).
- [22] V. Ambegaokar and A. Baratoff, Phys. Rev. Lett. 11 , 104 (1963).
- [23] C. W. J. Beenakker, Phys. Rev. Lett. 67 ,3836 (1991).
- [24] C. W. J. Beenakker, Rev. Mod. Phys. 69 , 731 (1997)
- [25] Y. Naveh, Vijay Patel, D. V. Averin, K. K. Likharev, and J. E. Lukens, Phys. Rev. Lett. 85 , 5404 (2000).
- [26] O. N. Dorokhov, JETP Lett. 36 , 318 (1982).
- [27] K. M. Schep and G. E. W. Bauer, Phys. Rev. Lett. 78 , 3015 (1997).
- [28] A. Furusaki and M. Tsukada, Physica B 165-166 , 967 (1990).
- [29] S. V. Kuplevakhaskii and I. I. Fal'ko, Sov. J. Low Temp. Phys. 17 , 501 (1991).
- [30] Our notation for incoming and outgoing states is choosen to correspond to the boundry conditions for scatttering in Ref. [32].
- [31] D. Averin and A. Bardas, Phys. Rev. Lett. 75 , 1831 (1995).

- [32] E. N. Bratus', V. S. Shumeiko, E. V. Bezuglyi, and G. Wendin, Phys. Rev. B 55 , 12666 (1997).
- [33] E. N. Bratus, V. S. Shumeiko, and G. A. B. Wendin, Phys. Rev. Lett. 74 , 2110 (1995).
- [34] K.M. Lang, S. Nam, J. Aumentado, C. Urbina, J. M. Martinis, IEEE Trans. on Appl. Supercon. 13 , 989 (2003).

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- formula-not-decoded -->

<!-- image -->

<!-- image -->

-

+

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->