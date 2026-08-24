## Time-dependent Ginzburg-Landau treatment of rf magnetic vortices in superconductors: Vortex semiloops in a spatially nonuniform magnetic field

Bakhrom Oripov * and Steven M. Anlage

Quantum Materials Center and Department of Physics, University of Maryland, College Park, Maryland 20742-4111, USA

<!-- image -->

(Received 4 September 2019; accepted 24 February 2020; published 19 March 2020)

We apply time-dependent Ginzburg-Landau (TDGL) numerical simulations to study the finite frequency electrodynamics of superconductors subjected to an intense rf magnetic field. Much recent TDGL work has focused on spatially uniform external magnetic fields and largely ignores the Meissner state screening response of the superconductor. In this paper, we solve the TGDL equations for a spatially nonuniform magnetic field created by a point magnetic dipole in the vicinity of a semi-infinite superconductor. A two-domain simulation is performed to accurately capture the effect of the inhomogeneous applied fields and the resulting screening currents. The creation and dynamics of vortex semiloops penetrating deep into the superconductor domain are observed and studied, and the resulting third-harmonic nonlinear response of the sample is calculated. The effect of pointlike defects on vortex semi-loop behavior is also studied. This simulation method will assist our understanding of the limits of superconducting response to intense rf magnetic fields.

DOI: 10.1103/PhysRevE.101.033306

## I. INTRODUCTION

Superconductor technology is widely used in industrial applications where high current and low loss are required. With technological advancements in the fabrication of high quality superconducting materials and significant reduction in cryocooler prices, superconductor-enabled devices like magnetic resonance imaging, high performance microwave and rf filters, low-noise and quantum-limited amplifiers, and fast digital circuits based on rapid single flux quantum logic devices became feasible [1,2].

The superconducting radio frequency (SRF) cavity [3,4] used in new generation high energy particle accelerators is an example of the large scale usage of superconductor technology. Nb is the most dominant material used in SRF applications because it has the highest superconducting critical temperature ( Tc = 9 . 3 K) and superheating field ( B SH ≈ 240 mT) among the elemental superconductors at ambient pressure while being a good heat conductor at typical SRF operating temperatures [5]. During normal operation an SRF cavity is subjected to a high rf magnetic field parallel to the internal superconducting surface. One of the key objectives in SRF cavity operation is to maximize the accelerating gradient of the machine while minimizing the dissipated power in the cavities. However, these cavities remain susceptible to a number of issues including enhanced losses due to trapped magnetic flux [6] and the existence of pointlike surface defects [7,8]. The maximum gradient operating conditions are often limited by extrinsic problems. One limiting scenario is that a surface defect can facilitate the entrance of vortex semiloops which can later be trapped due to the impurities within the bulk of the cavity [9]. The energy dissipated due to the dynamics of these vortex semiloops under the influence of rf currents

* Corresponding author: bakhromtjk@gmail.com

could be the limiting factor on the ultimate performance of the SRF cavity. This phenomenon cannot be simulated unless the effects of the screening currents and fields on the superconducting order parameter are included self-consistently.

This paper is motivated by results for third-harmonic generation from a near-field microwave microscope utilized on Nb surfaces [10-16]. In this experiment, a magnetic writer probe from a conventional magnetic recording hard-disk drive is used to create a high-intensity, localized, and inhomogeneous rf magnetic field on the surface of a Nb superconducting sample. This probe applies a localized field oscillating at microwave frequency, and measures the sample's fundamental [17] and harmonic rf response. In the experiment, the third-harmonic response and its dependence on the applied rf magnetic field amplitude and the temperature of the sample were studied. Preliminary results of TDGL modeling and comparison to experimental data were published in Ref. [16].

In this paper, numerical solutions of the time-dependent Ginzburg-Landau (TDGL) equations are obtained for a superconductor subjected to a spatially nonuniform applied rf magnetic field, and the effect of boundary conditions on the accuracy of the results is investigated. First, the GinzburgLandau (GL) theory and its range of validity are discussed in Sec. II. Second, the TDGL equations and the normalization used in this paper are presented in detail in Sec. III. Then, the implementation of the TDGL simulation in COMSOL MULTIPHYSICS simulation software with all appropriate boundary conditions is summarized in Sec. IV. In Sec. IV A a twodomain simulation capable of correctly modeling spatially nonuniform magnetic fields and the response screening currents of the superconductor is described, and simple examples are presented to demonstrate the validity of the two-domain model. Next, in Sec. V, an application of the two-domain simulation is presented, where vortex semiloops created by a strongly inhomogeneous field distribution are simulated. The time evolution of the vortex semiloops, their dependence on

the magnitude of the rf magnetic field, and their interaction with a localized defect are studied. Finally, in Sec. V D, a more general case where the vortex semiloops are created in a superconductor surface when a uniform rf magnetic field is applied parallel to the surface of the superconductor is presented, and the results are discussed. We then discuss future work in Sec. VI and conclude the paper.

## II. GINZBURG-LANDAU THEORY

The GL theory is a generic macroscopic model appropriate for understanding the electrodynamic response of superconductors subjected to static magnetic fields and currents in the limit of weak superconductivity [18]. GL generalizes the theory of superconductivity beyond BCS by explicitly considering inhomogeneous materials, including surfaces, interfaces, defects, vortices, etc.

The GL equations are differential equations which relate the spatial variation of the order parameter /Psi1 ( /vector r ) to the magnetic vector potential /vector A ( /vector r ) and the current /vector J ( /vector r ) in a superconductor. GL starts with an expression for the free energy density of a superconductor in terms of the position-dependent order parameter and vector potential [19]:

<!-- formula-not-decoded -->

Here, α ( /vector r , T ) and β ( /vector r , T ) are the temperature and positiondependent phenomenological expansion parameters, m ∗ = 2 me is the mass of the Cooper pair, e ∗ = 2 e is the charge of the Cooper pair, /vector Ba = /vector Ba ( /vector r , t ) is the amplitude of the externally applied magnetic field, and i = √ -1.

Taking variational derivatives and minimizing the free energy with respect to /Psi1 and /vector A leads to the coupled GinzburgLandau equations [20,21]:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Apart from the TDGL model, the Bogoliubov-de Gennes equations [22-25], Gorkov's Green's-function method [26-28], the Matsubara formalism [29,30], or Usadel's equations [31] can be used to study inhomogeneous superconductors [32]. We shall utilize TDGL because of its relative simplicity and the physical insights it offers compared to these other more microscopic approaches.

## III. TIME-DEPENDENT GINZBURG-LANDAU EQUATIONS AND NORMALIZATION

The GL equations are static, and thus cannot be used to study the temporal evolution of the order parameter and the screening currents. In 1966, Schmid proposed a timedependent generalization of the GL equations that could be utilized to study the dynamics of the order parameter [33]. Gor'kov and Eliashberg derived a similar equation [34], but noted that for the case of a gapped superconductor there exists a singularity in the density of states vs energy spectrum which prohibits expanding various quantities in powers of the gap /Delta1 .

Gor'kov limited the use of TDGL to gapless superconductors, or to materials with magnetic impurities or other pairbreaking mechanisms that would round off the singularity in the BCS density of states [21]. Proximity to a boundary with a normal metal, along with strong external magnetic fields and currents, can also lead to gapless superconductivity before completely destroying it. Of relevance to the case of SRF cavities, numerous researchers have noted a substantial reduction in the singularity, and broadening of the density of states spectrum, under SRF operating conditions [35,36] or with various types of impurities and imperfections at the surface [37-41]. Such conditions would also justify the use and relevance of the TDGL equations under these circumstances.

In order to extend the validity of the TDGL formalism to gapped superconductors, a generalized version of TDGL (gTDGL) was proposed [42,43]. In gTDGL, the effects of a finite inelastic electron scattering time are considered. gTDGL is valid for a superconductor in the dirty limit, but does not require strong limitations such as a large concentration of magnetic impurities and/or gapless superconductivity [27]. Nevertheless, both TDGL and gTDGL are not microscopic theories, thus some of the parameters of the model are difficult to determine precisely for a given material of interest. For this reason we focus on semiquantitative results and use the phenomenological TDGL equations mainly to give insight into the signals created by our near-field microwave microscope [16]. Future work will explore the order parameter dynamics under gTDGL. In addition, questions of validity and relevance of the solution to the TDGL equations outside of the range in which they are derived remain.

TDGL numerical simulations have been employed on a broad variety of problems [20,44,45]. We note that TDGL was previously used to study vortex dynamics and V-I characteristics of two-dimensional (2D) rectangular thin films [46], vortex entry in the presence of twin boundaries [47], and the vortex dynamics under an ac magnetic field in mesoscopic superconductors [48]. TDGL was also used to study the dynamics of vortex loops created by a static magnetic dipole [49] which is similar to the results discussed in this paper. More recently, the TDGL formalism was used to estimate the strength of the Kerr effect in a superconductor when a short light pulse is applied [50].

Often a three-dimensional (3D) problem is simplified by assuming that the sample is infinite in the direction parallel to the externally applied magnetic field, thus reducing the 3D problem to a 2D one [47,51,52]. Moreover, much published work done using numerical solutions to the TDGL equations involves problems with a spatially uniform external magnetic field and uses a single (entirely superconducting) domain for the simulation. However, this assumption ignores the effect that the screening currents would have at the surface, which is one of the most important aspects of the problem that we investigate.

Here we give a brief motivation for the origins of the TDGL equations. Once the GL free energy is known in its functional

form [Eq. (1)], the relaxation dynamical equation can be written by considering how the order parameter evolves after being slightly disturbed from its equilibrium value [27,53]:

<!-- formula-not-decoded -->

where γ plays the role of a friction coefficient. Here, the scalar electric potential /Phi1 is included to make the equation describing the dynamics of the superconducting order parameter gauge invariant. The TDGL equations are then derived through the variational derivatives of the GL free energy equation [Eq. (1)] with respect to /Psi1 ∗ and A and are given as follows [33,52,54]:

<!-- formula-not-decoded -->

where /Psi1 = /Psi1 ( /vector r , T , t ) is the time-dependent order parameter, /vector A = /vector A ( /vector r , t ) is the magnetic vector potential, /vector Ba = /vector Ba ( /vector r , t ) is the externally applied magnetic field, /Phi1 = /Phi1 ( /vector r , t ) is the scalar electric potential, D is the phenomenological electron diffusion coefficient given by D = v F l 3 [20] with v F being the Fermi velocity and l being the quasiparticle mean free path [55], and σ is the electric conductivity of the normal (nonsuperconducting) state. It is evident from Eq. (5) that γ = ¯ h 2 2 m ∗ D and can also be written as γ = | α ( T ) | τ/Psi1 ( T ), where τ/Psi1 ( T ) = ξ ( T ) 2 D = π ¯ h 8 kB ( Tc -T ) is a characteristic time for the relaxation of the GL order parameter [54]. Here, α ( T ) = α (0)(1 -T Tc ) and ξ 2 = ξ 2 0 (1 -T Tc ) , where ξ 0 is the zero temperature GL coherence length.

Equation (5) was first proposed by Schmid [33], following the derivation of the GL equation from BCS [56,57] by Gor'kov and Eliashberg [34]. Equation (6) is Ampere's law /vector ∇ × /vector B ( /vector r ) = µ 0 ( /vector Js ( /vector r ) + /vector Jn ( /vector r )), where /vector Jn ( /vector r ) = -σ ∂ /vector A ( /vector r ) ∂ t is the normal current and the supercurrent is defined in Eq. (7).

The superconducting current can be obtained from the expectation value of the momentum operator for a charged particle in a magnetic field:

<!-- formula-not-decoded -->

The TDGL equations are invariant under the following change of gauge [52]:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where χ ( /vector r , t ) is any (sufficiently smooth) real-valued scalar function of position and time. One can fix the gauge as ∂χ ( /vector r , t ) ∂ t = e ∗ ¯ h /Phi1 ( /vector r , t ) in order to effectively eliminate the electric potential at all times [50,52].

It is useful to introduce dimensionless variables (denoted by the tilde) to simplify the simulation and normalize Eqs. (5) and (6): The order parameter is scaled according to /Psi1 ∞ , /Psi1 → /Psi1 ∞ ˜ /Psi1 where | /Psi1 ∞ ( /vector r ) | 2 = -α 0 β 0 is the bulk superfluid density at zero temperature in the absence of an external magnetic field, α 0 ≡ α ( T = 0), and β 0 ≡ β ( T = 0). The spatial coordinates are scaled according to the zero temperature GL penetration depth λ 0 ≡ √ m µ 0 nse ∗ 2 , so that ( x , y , z ) → ( λ 0 ˜ x , λ 0 ˜ y , λ 0 ˜ z ), thus /vector

/vector ∇ → 1 λ 0 ˜ ∇ [58]. Time is scaled according to the characteristic time for the relaxation of the vector potential τ 0 , t → τ 0 ˜ t where τ 0 ≡ µ 0 λ 2 0 σ n [59] and σ n is the normal state conductivity at 0 K [as opposed to the conductivity of nonsuperconducting current at any temperature denoted as σ ( T )]. The temperature is scaled according to the critical temperature of the superconductor Tc , T → Tc ˜ T . The vector potential /vector A → /Phi1 0 ξ 0 /vector ˜ A where /Phi1 0 = h 2 e is the magnetic flux quantum. The superconductor current is scaled in terms of Jc , /vector J → Jc κ /vector ˜ J , where Jc = /Phi1 0 2 πµ 0 λ 0 ξ 2 0 = Bc 2 µ 0 λ 0 is the critical current density at T = 0 and B = 0, and κ is the GL parameter and is defined as the ratio of two characteristic length scales κ ≡ λ 0 ξ 0 . The normal state conductivity is scaled with its zero temperature value σ → σ n ˜ σ and, since it is nearly constant in the temperature range of interest for Nb, it is set to ˜ σ = 1. The 'normalized friction coefficient' is defined as the ratio between the two characteristic time scales τ/Psi1 and τ 0 , η ≡ τ/Psi1 τ 0 [54,60] and is proportional to γ defined in Eq. (4) ( η = γ | α | τ 0 ). For cases when the source of an externally applied magnetic field is outside of the superconducting domain, the /vector Ba term in Eq. (6) should be dropped because /vector ∇ × /vector Ba = 0 everywhere within the superconducting domain.

Rewriting Eqs. (5) and (6) using the newly introduced dimensionless quantities and dropping the tilde, we have

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Defects (such as pinning sites) can be introduced into the model via spatial variation of the GL coefficient α ( /vector r , T ). Such defects could be due to spatial variation of temperature T , critical temperature Tc ( /vector r ), and/or spatial variation of the mean free path l ( /vector r ). One can calculate the vortex pinning potential created by these kinds of disorder using the method outlined in Ref. [44]. The pinning coefficient /epsilon1 ( /vector r , T ) = α ( /vector r , T ) α ( T = 0) = ξ 2 ( T = 0) ξ 2 ( /vector r , T ) = 1 -T Tc ( /vector r ) dictates the maximum possible value for the superfluid density ns ( /vector r , T ) at a given location and temperature in the absence of an external magnetic field.

In this paper we are interested in studying the effects of some common SRF surface defects, such as lossy Nb oxides and metallic Nb hydrides near the surface of Nb [61]. These types of defects either are nonsuperconducting or have lower critical temperature than Nb. Such metallic inclusions, or the effect of nonzero temperature, can be specified through /epsilon1 ( /vector r , T ) [48,62-65], which can range from /epsilon1 ( /vector r , T ) = 0 (strong order parameter suppression) to /epsilon1 ( /vector r , T ) = 1 (full superconductivity).

To numerically simulate the superconducting domain, we must specify the boundary conditions for the order parameter, current density, and vector potential. In this paper only the superconductor-insulator boundary is considered. Any current passing through the boundary between a superconducting domain and vacuum or insulator would be nonphysical, and thus on the boundary ∂/Omega1 of the superconducting domain /Omega1 we expect

<!-- formula-not-decoded -->

Here ˆ n is the unit vector normal to the boundary, and since we expect Eq. (13) to be true even when /vector A = 0 and /Psi1 /negationslash= 0 the first boundary condition is [25,52,54,60]

<!-- formula-not-decoded -->

Likewise when both /vector A /negationslash= 0 and /Psi1 /negationslash= 0, to satisfy Eq. (14),

<!-- formula-not-decoded -->

leading to

<!-- formula-not-decoded -->

The third condition generally used is the continuity of the magnetic field across an interface:

<!-- formula-not-decoded -->

where /vector B external is the externally applied magnetic field.

## IV. TDGL IN COMSOL

COMSOL MULTIPHYSICS simulation software [66] can be used to solve the TDGL equations in both 2D and 3D domains [52,67]. The main advantage of COMSOL is the intuitive interface of the software and automatic algorithm optimization. A critical comparison of COMSOL and ANSYS simulation software was previously performed [68], where the authors showed that COMSOL can complete the simulation ten times faster while reaching similar results. The accuracy of the software has been validated by other researchers as well [69,70]. COMSOL has an easy learning curve enabling researchers to use the TDGL model as a tool without spending too much effort on algorithm development [71].

The general form partial differential equation is one of the equations best suited to be solved by COMSOL MULTIPHYSICS simulation software and is given as

<!-- formula-not-decoded -->

Here /vector F is the driving term vector, d is the inertia tensor, /vector u is a column vector of all unknowns, and /vector /Gamma1 is a column vector function of /vector u . We can rewrite Eqs. (11) and (12) to be in this form. Redefine /Psi1 and /vector A as

<!-- formula-not-decoded -->

where v 1 and v 2 are real functions of position and time:

<!-- formula-not-decoded -->

where A 1 , A 2, and A 3 are real functions of position and time representing the magnitudes of the components of /vector A in the ˆ x , ˆ y , and ˆ z directions.

We thus have five independent unknown variables and five equations [two from Eq. (11), real and imaginary, and three vector components from Eq. (12)]. After some simple mathematical rearrangement we get an equation of the form of Eq. (19):

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Here v 1 x stands for ∂ v 1 ∂ x , A 2 z stands for ∂ A 2 ∂ z , and so on. These equations indicate that the change in /vector A ( /vector r , t ) is driven by the total current, while the change in /Psi1 ( /vector r , t ) is driven by both /Psi1 ( /vector r , t ) and its interaction with /vector A ( /vector r , t ).

FIG. 1. Schematic view of the superconductor and vacuum domains and boundary conditions in our TDGL simulations.

<!-- image -->

The boundary conditions at the superconductor-vacuum interface are as follows:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

## A. Two-domain TDGL and inclusion of superconducting screening

After reviewing some previously published TDGL simulations [47,52,64], we noticed that usually Eq. (18) or Eq. (26) is enforced on the boundary of the superconductor. However, this implies that the superconducting screening current has no effect on the magnetic field at the boundary and beyond the superconducting domain. This is physically incorrect for the situation of interest to us. The effect of screening currents is crucial when one is trying to simulate a spatially nonuniform external magnetic field (like that arising from a nearby magnetic dipole) and the resulting nonlinear response of the superconductor.

To include the important physics of screening, our simulation is divided into two domains: superconductor and vacuum (Fig. 1). The full coupled TDGL equations are solved in the superconductor domain, while only Maxwell's equations are solved in the vacuum domain, with appropriate boundary conditions at the interface. Any finite value of /vector A · /vector n or /vector ∇ /Psi1 · /vector n would lead to a finite current passing through the superconductor-vacuum boundary (red box in Fig. 1), which is nonphysical, hence Eqs. (24) and (25) are enforced at the superconductor-vacuum interface. Any externally applied magnetic field is introduced by placing a boundary condition on the outer boundary of vacuum domain [Eq. (26)]. The vacuum domain is assumed to be large enough that at the external boundary (blue box in Fig. 1) the magnetic field generated by the superconductor is negligible. Figure 1 schematically summarizes this scenario.

We now examine several key examples where it is crucial to include the screening response of the superconductor to capture the interesting physics. Through these two examples we validate our approach to solving the TDGL equations.

FIG. 2. Plot of the TDGL two-domain solution for the z component of the magnetic field in a plane through the center of the sphere in and around a superconducting sphere in the Meissner state subjected to a uniform static external magnetic field in the z direction. The dashed lines show the boundaries of the spheres, with the smaller sphere being the superconducting sphere with diameter 10 λ 0 and the larger sphere being the vacuum domain with diameter 40 λ 0. The solution is obtained for temperature T = 0, GL parameter κ = 1, and external magnetic field /vector B applied = 10 × 10 -3 Bc 2 ˆ z . Black lines show the streamline plot of the magnetic field, while the color represents the value of magnetic field component Bz . The white line indicates the equator, and the magnetic field along the white line is shown in Fig. 3.

<!-- image -->

## B. Superconducting sphere in a uniform magnetic field

First consider the classic problem of a superconducting sphere immersed in a uniform magnetic field. Assume that the superconductor remains in the Meissner state. It is known from the exact solution to this problem that there will be an enhancement of the magnetic field at the equatorial surface of the superconducting sphere due to the magnetic flux that is expelled from the interior of the sphere. To test this approach to solving the TDGL equations we created a model of this situation in COMSOL [72]. We simulated the response using the two-domain method, and the conventional single-domain method used in many other contexts, and then compared both results with the exact analytical solution for the magnetic field profile [73].

Figure 2 shows the TDGL simulation of a superconducting sphere subjected to a uniform static external magnetic field. The boundaries of the spheres are shown with the dashed lines, where the smaller sphere is the superconducting sphere, and the larger sphere is the vacuum domain. The colors represent the amplitude of the ˆ z component of the applied magnetic field in the y -z plane passing through the common center of the spheres. Black lines show the streamline plot of the magnetic field in the same y -z plane. The streamline plot is defined as a collection of lines that are tangent everywhere to the instantaneous vector field, in this case to the direction of the magnetic field. The simulation was initialized in a field free configuration and the external magnetic field was applied at t = 0. The simulation was iterated for t = 1000 τ 0 time steps after which the changes in | /Psi1 | 2 were &lt; 0 . 1% per iteration.

FIG. 3. Top: Magnetic field ˆ z -component ( Bz ) profile through the center of the sphere (white line in Fig. 2). The results of a singledomain TDGL model are shown in red, those of a two-domain TDGL model are shown in green, and the analytic solution is shown as a blue solid line. Bottom: The difference between a two-domain TDGL model and the analytic solution is shown in green and the difference between the single-domain TDGL model and the analytic solution is shown in red. The biggest difference is observed at the surface.

<!-- image -->

To test the reproducibility of the result, the simulation was later repeated, but this time the external magnetic field was increased linearly in time from zero to 0 . 01 Bc 2 between time zero and 500 τ 0. After this, the simulation was again iterated for t = 1000 τ 0 time steps. The results of these two simulations were identical.

Equations (24) and (25) were enforced on the spherical superconductor-vacuum boundary ( r = 5 λ 0 ) in both cases. When the two-domain method was used, the TDGL equations were solved in the inner sphere ( r &lt; 5 λ 0 ) and only Maxwell's equations were solved in the vacuum domain (5 λ 0 &lt; r &lt; 20 λ 0 ). Equation (26) was enforced at the outer boundary of the simulation ( r = 20 λ 0). When the single-domain simulation method was used, Eq. (26) was enforced at the inner boundary of the simulation ( r = 5 λ 0 ) and the vacuum domain was not utilized.

The top plot in Fig. 3 shows the profile of the z component of magnetic field ( Bz ) along a line through the center of the sphere, in a plane perpendicular to the externally applied magnetic field (white line in Fig. 2) calculated from the single-domain simulation, the two-domain simulation, and the analytic result. Inside the sphere, the magnetic field profile calculated from the single-domain simulation and the twodomain simulation are very similar although not identical. The bottom plot in Fig. 3 shows the difference between the TDGL simulation results and the analytic solution. The field deep inside the sphere is strongly suppressed by the screening currents. This can also be seen from the color map in Fig. 2. The blue region inside the sphere corresponds to the fully shielded portion of the sphere. However, there is a region outside the sphere around the equator where the magnetic field is enhanced (red color in Fig. 2).

At the surface of the sphere the magnetic field calculated from the two-domain model reproduces the exact analytic solution, while the single-domain model fails to account for the enhancement of the magnetic field on the equator of the sphere. This disparity between the single-domain model and analytic solution is caused by the treatment of the boundary conditions. In the single-domain model, Eq. (26) is enforced at the superconductor-vacuum interface, which completely ignores the effect of screening currents. Thus a two-domain model should be used for any problem where screening and the magnetic field profile at the surface of the superconductor are important.

## C. Point magnetic dipole above a semi-infinite superconductor

To ensure that we can accurately simulate the screening currents produced by a spatially nonuniform magnetic field, we numerically simulated the case of a static point magnetic dipole placed at a height of h DP = 1 λ 0 above the surface of a semi-infinite superconductor. The superconducting domain and vacuum domain are simulated inside two coaxial cylinders with equal radius R = 8 λ 0 with a common axis along the ˆ z direction of the Cartesian coordinate system. The origin of this coordinate system is located on the superconductor surface immediately below the dipole. The thickness of the superconducting domain is h SC = 10 λ 0 and the height of the vacuum domain is h vac = 5 λ 0 . The normalized friction coefficient η and the GL parameter κ are set to 1.

The surface magnetic fields produced by the dipole are assumed to be below the lower critical field Hc 1, so that the superconductor remains in the Meissner state. The simulation was started with a superconductor in the uniform Meissner state and the dipole field equal to zero. Then, at time t = 0, the dipole magnetic field is turned on, and the simulation is iterated in time until the relative tolerance of ∂ u u &lt; 0 . 001 is achieved for all the variables in the column vector of all unknowns u [Eq. (19)]. At this point the static solution to the problem is obtained. Later the simulation was repeated with the external magnetic field linearly increasing with time over a t = 0-500 τ 0 time interval before reaching a set constant value. The results of these two simulations were identical.

We compared our TDGL results for the distribution of the surface screening current density /vector J screening ( x , y ) to numerical results obtained by Mel'nikov [74] for the case of a perpendicular magnetic dipole. Figure 4 shows a comparison of the calculated screening current profiles. Both results show that there is a circulating screening current centered directly below the dipole. Also note that the screening current reaches zero at the outer boundary of the simulation. This indicates that a sufficiently large domain was chosen for simulation and no finite size effects are expected. We have very good agreement between the two-domain TDGL simulation result and numerical results obtained by Mel'nikov, in the low magnetic field limit where there are no vortices (Fig. 4). This and the previous result serve to validate our two-domain approach to properly capturing the screening response of the superconductor in TDGL.

## V. APPLICATION: NONLINEAR NEAR-FIELD MAGNETIC MICROWAVE MICROSCOPY OF A SUPERCONDUCTOR

The dominant material used in SRF cavities is Nb, which is a type-II superconductor and can host vortices. Vortices

FIG. 4. The magnitude of the superconducting screening current density at the surface J screening as a result of a perpendicular magnetic dipole placed h DP = 1 λ 0 above the superconductor vs the horizontal distance from the dipole location obtained from TDGL simulation (blue × ) and numerical solution for the same scenario obtained from Ref. [74] (red solid line). The left inset shows a schematic of the dipole over the superconductor, while the right inset shows the top view of the surface current distribution calculated by TDGL, which is azimuthally symmetric. The parameters of the simulation are listed in Table I.

<!-- image -->

can be created by high rf magnetic fields used in SRF cavity operation and pointlike surface defects [7,8]. V ortices can also form due to flux trapped during the cool down procedure. Recent studies showed that the trapped magnetic flux amount depends on the rate at which the cavity is cooled down through the critical temperature and the level of the ambient magnetic field [75]. Decreasing the trapped magnetic flux amount leads to better cavity performance.

The type of vortices inside an SRF cavity and the dynamics of those vortices were theoretically studied by Gurevich and Ciovati [9]. For large parallel surface rf magnetic fields and a pointlike surface defect, a vortex first enters the superconductor as a vortex semiloop. To study the dynamics of these vortex semiloops a near-field magnetic microwave microscope was successfully built using a magnetic writer from a conventional magnetic recording hard-disk drive [10-16]. A magnetic write head can produce a B rf ≈ 600-mT rf magnetic field localized to a ≈ 100-nm length scale [76]. In the experiment, a Seagate perpendicular magnetic writer head is attached to a cryogenic XYZ positioner and used in a scanning probe fashion. Probe characterization results and other details can be found in [12-16]. The probe produces an rf magnetic field perpendicular to the sample surface. The sample is in the superconducting state, so to maintain the Meissner state a screening current is induced on the surface. This current generates a response magnetic field which is coupled back to the same probe, creates a propagating signal on the attached transmission line structure, and is measured with a spectrum analyzer at room temperature. Since superconductors are intrinsically nonlinear [77], both linear and nonlinear responses to an applied rf magnetic field are expected. In said experiment, mainly the third-harmonic response to the inhomogeneous driving field is measured.

FIG. 5. TDGL simulation setup for an oscillating horizontal magnetic dipole /vector M DP at height h DP above the superconductor surface. The magnetic probe is approximated as an oscillating point magnetic dipole parallel to the surface. Red arrows: Surface currents on the horizontal ( xy ) superconductor/vacuum interface as calculated from the self-consistent TDGL equations. Black arrows: Externally applied magnetic field on a vertical plane ( xz ) perpendicular to the superconductor surface and including the dipole.

<!-- image -->

The rf magnetic field produced by the magnetic writer probe sitting on top of a sample is very similar to the magnetic field produced by a horizontal point magnetic dipole with normalized magnetic moment M DP( t ) || ˆ x placed at a height h DP above the sample. The normalized vector potential produced by such a dipole in free space is given by [78]

<!-- formula-not-decoded -->

where the origin of the coordinate system is on the superconductor surface immediately below the dipole. While this is very different from a uniform and parallel magnetic field inside an actual SRF cavity, the dynamics of the vortex semiloops created by this field should be very similar.

The superconducting domain and vacuum domain are simulated inside two coaxial cylinders with equal radius R (see Fig. 5) with a common axis along the ˆ z direction of the Cartesian coordinate system. The thickness of the superconducting domain is h SC and the height of the vacuum domain is h vac in normalized units.

The boundary condition Eq. (26) is enforced at the top of the vacuum domain, whereas a /vector B = 0 boundary condition is enforced at the bottom and the sides of the superconducting domain, since it is expected that the superconducting currents due to the Meissner state will fully shield the externally applied magnetic field before it reaches the outer boundary of the superconductor.

The interaction between the probe and the sample was modeled by solving the TDGL equations. In the simulation, we specify M DP( t ) indirectly through the the magnetic field experienced at the origin (on the superconductor surface immediately below the dipole) /vector B 0 ( t ) = /vector ∇ × /vector A DP(0 , 0 , 0 , t ) = -M DP( t ) h 3 DP ˆ x , where M DP( t ) = M DP(0)sin( ω t ). The driving rf magnetic field profile is specified through the analytic equation for the magnetic vector potential of a point dipole [Eq. (27)], therefore the dipole itself can be placed either

inside the vacuum domain h vac &gt; h DP or beyond it h vac &lt; h DP without affecting the accuracy of the simulation. h vac is chosen to be large enough to be consistent with Eq. (26) at the top of the vacuum domain.

The main objective of this paper is to simulate the response of the SRF grade Nb, thus the parameters are chosen accordingly. For Nb, σ n ranges from 2 × 10 8 to 2 × 10 9 S/m depending on the residual resistivity ratio (RRR) value of the material, and λ 0 = 40 nm [79,80]. The characteristic time for the relaxation of /vector A is τ 0 = µ 0 λ 2 0 σ n = 4 × 10 -12 s for Nb bulk samples in the clean limit (RRR ≈ 300). Consequently, the 100-2000 τ 0 range for the period of the magnetic dipole corresponds to a frequency range of 125 MHz to 2 . 5 GHz. Hence, the period of the dipole rf magnetic field was chosen to be 2 π ω = 200 τ 0. The GL parameter κ = 1 [5], and η is on the order of unity (parameters are summarized in Table I ). It should be noted that the relaxation time τ 0 ∼ ps with η = τψ τ 0 ∼ 1 is 'fast' in the sense that the order parameter will quickly follow any variations in rf field or current.

The spatial distribution of the magnetic field at the surface of the superconductor is set through the value for the dipole height h DP. While the driving rf magnetic field is specified through the analytic equation Eq. (27), the goal is to reproduce the actual spatial distribution produced by the magnetic writer head at the surface of the superconductor, which was provided by the manufacturer [76]. To produce similar spatial distribution of the magnetic field, we set the dipole height to the 300-500-nm range which corresponds to h DP of 8-12 λ 0 in normalized units.

## A. The evolution of vortex semiloops with time

We consider a dipole that oscillates sinusoidally in time with frequency ω , and calculate the response of the superconductor to this external inhomogeneous and time-dependent magnetic field. Our objective is to describe a spatially inhomogeneous microwave frequency stimulus of the superconducting surface. In this section a uniform superconductor domain with no defects is considered. The simulation is started with the order parameter having a uniform value of | /Psi1 | 2 = /epsilon1 ( T ) everywhere. At time t = 0 the externally applied magnetic field is turned on. Then the simulation is run for several rf cycles to reach the steady state solution.

FIG. 6. Snapshot of three vortex semiloops at time t = 73 τ 0 during the rf cycle of period 200 τ 0 . In this view, one is looking from inside the superconducting domain into the vacuum domain. Plots of | /Psi1 | 2 are evaluated at the superconductor surface for an oscillating parallel magnetic dipole above the superconductor. The three-dimensional silver surfaces (corresponding to | /Psi1 | 2 = 0 . 005) show the emergence of vortex semiloops. The simulation parameters are given in Table I.

<!-- image -->

Figure 6 shows the results for such a simulation, and the parameters are given in Table I. The simulation was run for three driving periods to stabilize and the results shown in Fig. 6 are from the fourth driving period. Three well-defined vortex semiloops are illustrated by the three-dimensional silver surface corresponding to | /Psi1 | 2 = 0 . 005.

Figure 7 shows results for a similar simulation, illustrating the order parameter space and time dependence, and the parameters are given in Table I. The simulation was run for five driving periods to stabilize, and the results shown in Fig. 7 are from the sixth driving period. We see that as /vector B 0 ( t ) increases a suppressed | /Psi1 | 2 domain (red region) forms at the superconductor surface immediately below the dipole. At t = 50 τ 0 the magnetic field reaches its peak value and the suppressed superconducting region reaches its deepest point inside the superconducting domain illustrated by the silver surface in Fig. 7(c). Later ( t &gt; 50 τ 0 ), the amplitude of the external driving magnetic field decreases, the suppressed | /Psi1 | 2 domain rapidly diminishes, and vortex semiloops spontaneously emerge, become well defined [Figs. 7(d) and 7(e)], then move back towards the surface and vanish there before the end of the

TABLE I. Values of parameters used for TDGL simulations of the oscillating magnetic dipole above the superconductor.

| Parameter name                       | Symbol   | Scale            | Fig. 4     | Fig. 6    | Fig. 7    | Fig. 8    | Fig. 9              | Fig. 10   | Fig. 11   |
|--------------------------------------|----------|------------------|------------|-----------|-----------|-----------|---------------------|-----------|-----------|
| Temperature                          | T        | T c              | 0          | 0         | 0.6       | 0.9       | 0.6                 | 0.85      | 0.7       |
| Applied rf field amplitude           | B 0      | B c 2 µ 0 H SH † | 0.01 0.009 | 0.75 0.69 | 0.55 0.49 | 0.3 0.268 | 0.46-0.84 0.41-0.75 | 0.3 0.268 | 0.3 0.268 |
| Period of applied rf field           | 2 π ω    | τ 0              | Static     | 200       | 200       | 200       | 200                 | 200       | 1000      |
| Dipole height                        | h DP     | λ 0              | 1          | 8         | 8         | 12        | 8                   | 12        |           |
| Radius of the simulation domain      | R        | λ 0              | 8          | 12        | 35        | 60        | 20                  | 40        | 80 × 60   |
| Height of the superconducting domain | µ 0 h SC | λ 0              | 10         | 6         | 20        | 50        | 8                   | 25        | 20        |
| Height of the vacuum domain          | h vac    | λ 0              | 5          | 3         | 20        | 25        | 4                   | 15        | 10        |
| Ginzburg-Landau parameter            | κ        |                  | 1          | 1         | 1         | 1         | 1                   | 1         | 1         |
| Ratio of characteristic time scales  | η        |                  | 1          | 1.675     | 1         | 0.2       | 1                   | 0.5       | 1         |

FIG. 7. Summary of the TDGL solution for an oscillating parallel magnetic dipole above a superconducting surface. (a)-(f) Plots of | /Psi1 | 2 evaluated at the superconductor surface at different times for an oscillating parallel magnetic dipole above the superconductor. In the top part of each panel, one is looking from inside the superconducting domain into the vacuum domain, whereas in the bottom part of each panel one is looking at the x -z cross-section plane towards the + y axis. /vector M DP( t ) is chosen such that /vector B 0 ( t ) = 0 . 55sin( ω t )ˆ x . The three-dimensional silver surfaces (corresponding to | /Psi1 | 2 = 0 . 005) show the emergence of vortex semiloops. (g) | /vector B 0 | at the surface vs time during the first half of the rf cycle. Red crosses correspond to field values for snapshots (a)-(f).

<!-- image -->

first half of the rf cycle. In the second part of the rf cycle, the same process is repeated but now antivortex semiloops enter the superconducting domain. The full solution animated over time is available in the Supplemental Material [81]. In this particular scenario vortices and antivortices never meet, unlike the situation discussed in Ref. [82].

Figure 8 shows another simulation result with a different set of parameters (listed in Table I). Here the dipole is further away from the surface, at h DP = 12 and the temperature is set to T = 0 . 9 Tc . Three-dimensional silver contour surfaces correspond to | /Psi1 | 2 = 0 . 005. The two-dimensional screening currents (white arrows) and two-dimensional order parameter (colors) are plotted in the yz plane. Three vortex semiloops are clearly visible in this x = 0 cross-section cut. We see that the vortex semiloops penetrated somewhat deeper into the superconductor than the suppressed order parameter domain.

## B. The evolution of vortex semiloops with rf field amplitude

One can also study the effect of the applied rf field amplitude, defined through | /vector B 0 | , on the number and the dynamics of vortex semiloops. Figure 9 shows the bottom view of the order parameter on the surface of the superconducting domain for different values of the applied rf magnetic field amplitude, all

FIG. 8. Plots of | /Psi1 | 2 (color) and /vector J surf (arrows) evaluated at the two-dimensional x = 0 plane inside the superconductor at t = 50 τ 0 for an oscillating parallel magnetic dipole above the superconductor. White arrows indicate the currents induced inside the superconducting domain. The three-dimensional silver surfaces (corresponding to | /Psi1 | 2 = 0 . 005) show the emergence of vortex semiloops and the suppressed superconducting domain. All model parameters are listed in Table I.

<!-- image -->

at the same point in the rf cycle [ t = 50 τ 0 and /vector B 0 ( t ) at its peak value]. As expected, the number of vortex semiloops increases with increasing | /vector B 0 | . Once | /vector B 0 | = 0 . 6 is reached, a normal state | /Psi1 | 2 = 0 domain emerges at the origin, as opposed to a suppressed | /Psi1 | 2 domain observed at lower rf field amplitudes. The full solution as a function of peak applied magnetic field amplitude is available in the Supplemental Material [81].

## C. The effect of localized defects on rf vortex semiloops

In the past GL has been used to estimate the surface superheating field of superconductors [83] and TDGL was used to study rf vortex nucleation in mesoscopic superconductors [48]. Here we wish to examine the effect of a single pointlike defect on rf vortex nucleation in a bul sample.

FIG. 9. (a)-(h) Plots of | /Psi1 | 2 evaluated at the superconductor surface at t = 50 τ 0 for an oscillating parallel magnetic dipole above the superconductor as a function of dipole strength. In this view, one is looking from inside the superconducting domain into the vacuum domain. The maximum amplitude of the applied rf field is shown as | /vector B 0 | . The silver three-dimensional surfaces correspond to | /Psi1 | 2 = 0 . 005 and show the suppressed order-parameter domain and the vortex semiloops. The parameters of the simulation are listed in Table I.

<!-- image -->

FIG. 10. Summary of TDGL solutions for an oscillating parallel magnetic dipole above a superconducting surface in the presence of a localized defect at /vector rd = 0ˆ x + yd ˆ y -12ˆ z , where yd is varied from zero to 16 λ 0. (a)-(e) Plots of vortex semiloops in the y -z cross-section plane below the dipole illustrated with a three-dimensional silver surface (corresponding to | /Psi1 | 2 = 0 . 003) at time t = 150 τ 0, when the applied magnetic field reaches its peak amplitude. (f)-(j) Plots of vortex semiloops at time t = 180 τ 0. The defect is denoted by the red dot to the right of the center. /vector M DP( t ) is chosen such that /vector B 0 ( t ) = 0 . 30sin( ω t )ˆ x . The full list of simulation parameters is given in Table I.

<!-- image -->

The effect of a localized defect can be specified through the function /epsilon1 ( /vector r , T ) = α ( /vector r , T ) α ( T = 0) in Eqs. (11) and (23), which can range from /epsilon1 ( /vector r , T ) = 0 (strong suppression of superconductivity) to /epsilon1 ( /vector r , T ) = 1 (fully superconducting). Here, α ( /vector r , T ) dictates the maximum possible value for the superfluid density ns ( /vector r , T ) in the absence of an external magnetic field. A simple defect can be created, for example, by defining a Gaussian-in-space domain with suppressed superconducting critical temperature T cd, where 0 &lt; T cd &lt; 1:

<!-- formula-not-decoded -->

where ( xd , yd , zd ) are the central coordinates of the defect and σ x , σ y , and σ z are the standard deviations in the three coordinate directions, all expressed in normalized values. Figure 10 shows a simulation which was done with parameters given in Table I. A localized defect with σ x = σ y = σ z = √ 2

and T cd = 0 . 2 is located at /vector rd = 0ˆ x + yd ˆ y -12ˆ z , where yd is varied from zero to 16 λ 0, to represent a localized defect that is centered 12 penetration depths ( λ 0) below the surface and offset various distances from the oscillating dipole. We observed very similar vortex semiloops in the time domain evolution as those shown above. However, one of the vortex semiloops is now attracted towards the defect location (shown as a red dot in Fig. 10) and is distorted in shape. Furthermore, the vortex attracted by the defect remains inside the superconductor longer compared to the other vortex semiloops. Note that the semiloop disappears at the end of each half of the rf cycle, hence the pinning potential of this defect is not strong enough to trap the vortex semiloop, only to modify the rf behavior.

## D. Surface Defect in a Parallel rf magnetic field

In previous sections, we examined the dynamics of vortex semiloops created by a point magnetic dipole, as it is relevant to the magnetic microscopy experiment [16]. In this section we will briefly address the more general case which is appropriate for SRF applications, a uniform parallel rf magnetic field [ /vector B ( t ) = B 0sin( ω t )ˆ x ] above the superconductor in the presence of a single defect on the surface. In order to have a truly uniform field, the boundary between superconductor and vacuum should be simulated as an infinite plane. To accurately simulate the screening currents on the surface of the cavity, the two-domain simulation method described in Sec. IV A is used. The superconducting domain and vacuum domain are simulated inside two rectangular blocks instead of the cylindrical domain used in previous sections. The block dimensions are L = 80 λ 0 (along the field direction) and width W = 60 λ 0 . The height of the superconducting domain is h SC = 20 λ 0 , and the height of the vacuum domain is h vac = 10 λ 0. The vacuum domain is placed on the top of the superconducting domain. To mimic the infinite domain, periodic boundary conditions are applied in the ± ˆ x and ± ˆ y directions both for /Psi1 and /vector A .

Figure 11 shows the solution for the order parameter in the case of an externally applied rf magnetic field parallel to the surface of the superconductor along the ˆ x axis direction. A localized defect [modeled with Eq. (28)] is placed at the origin ( /vector rd = 0ˆ x + 0ˆ y + 0ˆ z ) with σ x = 6 and σ y = σ z = 1 and T cd = 0 . 1. A transient solution starting from the zero field Meissner state is studied in this case. A vortex semiloop penetrates into the superconducting domain at the site of the defect as the rf field amplitude increases [84]. We consider vortex semiloops as a unique type of vortex, distinctly different from parallel line vortices [85]. When the amplitude of the magnetic field is increased beyond that used in Fig. 11, we observe that arrays of parallel line vortices nucleate into the superconductor. While no defect was required to create vortex semiloops with the magnetic dipole source, a surface defect is required to create such a vortex when a parallel field is applied.

The solution shown in Fig. 11 is an initial transient solution, i.e., the simulation is not run for several cycles to reach the steady state condition. When the vortex semiloop reaches the boundary of the simulation in the field direction the results become nonphysical due to artificial pinning of the vortex

FIG. 11. (a)-(h) Plots of vortex semiloops illustrated with a silver surface (corresponding to | /Psi1 | 2 = 0 . 005) at different times for a parallel rf magnetic field in the ˆ x direction above the superconductor. A localized defect is placed at the origin ( /vector rd = 0ˆ x + 0ˆ y + 0ˆ z ) with σ x = 6 and σ y = σ z = 1 and T cd = 0 . 1. The color shows the orderparameter magnitude | /Psi1 | 2 on the superconducting surface. (i) | /vector B 0 | at the surface vs time during the first half of the rf cycle. Red crosses correspond to field values for snapshots (a)-(h). The full list of simulation parameters is given in Table I. Note that this is a transient solution rather than a steady-state solution.

<!-- image -->

semiloop by the boundaries. This finite size effect is currently limiting our ability to perform full rf parallel field simulation. Nevertheless, the transient solution shown in Fig. 11 may give some insight into the development of vortex semiloops in SRF cavities [9], and will be pursued in future work.

## VI. DISCUSSION

These simulations have proven very useful in understanding the measured third-harmonic response of Nb materials, subjected to intense localized rf magnetic fields [16]. In all the cases described in the previous section, the order parameter | /Psi1 | 2 and the vector potential /vector A are first retrieved from the simulation. Using Eq. (13) the screening supercurrent is calculated for each point in space and time. The response magnetic field generated by said currents at the location of the dipole is calculated using the Biot-Savart law. The third-harmonic response recovered at the location of the dipole is obtained through Fourier transformation of the calculated response magnetic field. Later the TDGL-derived third-harmonic voltage V 3 ω was compared with the third-harmonic response mea- sured from experiment. The comparison is discussed in detail in Ref. [16].

While most of the work was done for an oscillating parallel magnetic dipole, we also showed that vortex semiloops are created when a localized defect is introduced in the internal surface of an SRF cavity. It is plausible that vortex semiloops are one of the key sources of dissipation inside an SRF cavity at high operating power. The losses associated with such a vortex can be studied by combining the TDGL numerical technique with the experimental work published in Ref. [16].

While recent advances in SRF cavity fabrication, especially the technique of nitrogen doping and nitrogen infusion [86-88], have significantly improved the properties of SRF cavities, the microscopic mechanism responsible for this improvement is yet unknown. Nitrogen infused cavity surfaces can perhaps be thought of as a layered superconductor, with a dirty superconductor on top acting like a 'slow' superconductor and suppressing vortex nucleation [79,89,90]. The characteristic time scale governing the dynamic behavior of the superconductor was calculated by Gor'kov and Eliashberg to be τ GL = π ¯ h 8 kB ( Tc -T ) [34]. Superconductors in the dirty limit, with a finite inelastic electron-phonon scattering time τ E subject to √ D τ E /lessmuch ξ , can be better studied using gTDGL, where the effect of a finite inelastic electron scattering time is considered [42]. However, Tinkham has argued that the characteristic time for the relaxation of the order parameter in a gapped superconductor in the clean limit should be much longer than the characteristic GL time τ GL, instead on the order of τ E [21,27,91] ( τ E ≈ 1 . 5 × 10 -10 s for Nb [92]). It has been argued that a TDGL-like equation that incorporates these long relaxation times, a so called slow-GL model, can be used in such circumstances [21]. Perhaps the effects of nitrogen doping and nitrogen infusion on Nb cavities can be better understood by considering the effects of this different time scale on vortex semiloop formation. This can be accomplished with a sequence of TDGL, gTDGL, and slow-GL model simulations.

There is also a proposal to create superconductor-insulator multilayer thin-film coatings with enhanced rf critical fields [93]. TDGL simulations can be used to guide the design process for these multilayers. Although TDGL is not a microscopic theory, and it is sometimes difficult to link the parameters of the model to observable experimental quantities, the general behavior of the superconductor response to microwave magnetic fields and the development of vortex semiloops still provide much insight.

## VII. CONCLUSION

In this paper we present a way to perform TDGL simulations in three dimensions for spatially nonuniform magnetic fields applied to a superconducting surface. Proof of principle results are presented to show the validity of the proposed twodomain simulation method. The vortex semiloops created by a point magnetic dipole above the surface and the rf dynamics of such vortices are studied. The effect of temperature, rf field amplitude, and the surface defects on the vortex semiloops are studied and presented. The resulting third-harmonic nonlinear response can be calculated and compared with the

experimental data (a comparison is published in Ref. [16]). Finally, we demonstrate the creation of such rf vortex semiloops in the case of a uniform rf magnetic field parallel to a superconducting surface with a single defect.

- [1] Applied Superconductivity: Handbook on Devices and Applications , edited by Paul Seidel (Wiley, New York, 2015), Vol. 2.
- [2] Technological applications of superconductivity. in McGraw-Hill Concise Encyclopedia of Physics , 2002, https://encyclopedia2.thefreedictionary.com/Technological+ applications+of+superconductivity, accessed 10 Aug. 2019.
- [3] B. Aune, R. Bandelmann, D. Bloess, B. Bonin, A. Bosotti, M. Champion, C. Crawford, G. Deppe, B. Dwersteg, D. A. Edwards, H. T. Edwards, M. Ferrario, M. Fouaidy, P.-D. Gall, A. Gamp, A. Gössel, J. Graber, D. Hubert, M. Hüning, M. Juillard, T. Junquera, H. Kaiser, G. Kreps, M. Kuchnir, R. Lange, M. Leenen, M. Liepe, L. Lilje, A. Matheisen, W.-D. Möller, A. Mosnier, H. Padamsee, C. Pagani, M. Pekeler, H.-B. Peters, O. Peters, D. Proch, K. Rehlich, D. Reschke, H. Safa, T. Schilcher, P. Schmüser, J. Sekutowicz, S. Simrock, W. Singer, M. Tigner, D. Trines, K. Twarowski, G. Weichert, J. Weisend, J. Wojtkiewicz, S. Wolff, and K. Zapfe, Superconducting TESLA cavities, Phys. Rev. Special Topics: Accelerators Beams 3 , 092001 (2000).
- [4] H. Padamsee, J. Knobloch, and T. Hays, rf Superconductivity for Accelerators , 2nd ed. (Wiley, New York, 2008).
- [5] W. Singer, SRF cavity fabrication and materials, in CAS CERN Accelerator School: Course on Superconductivity for Accelerators , CERN Yellow Reports No. CERN-2014-005 and No. 171-207, 2015, doi: 10.5170/CERN-2014-005.171.
- [6] M. Martinello, M. Checchin, A. Grassellino, O. Melnychuk, S. Posen, A. Romanenko, D. Sergatskov, and J. F. Zasadzinski, Trapped flux surface resistance analysis for different surface treatments, in Proceedings, 17th International Conference on RF Superconductivity (SRF2015) (JACoW, Whistler, 2015), p. 115.
- [7] M. Ge, G. Wu, D. Burk, J. Ozelis, E. Harms, D. Sergatskov, D. Hicks, and L. D. Cooley, Routine characterization of 3D profiles of SRF cavity defects using replica techniques, Supercond. Sci. Technol. 24 , 035002 (2010).
- [8] Y. Iwashita, Y. Tajima, and H. Hayano, Development of high resolution camera for observations of superconducting cavities, Phys. Rev. ST Accel. Beams 11 , 93501 (2008).
- [9] A. Gurevich and G. Ciovati, Dynamics of vortex penetration, jumpwise instabilities, and nonlinear surface resistance of typeII superconductors in strong rf fields, Phys. Rev. B 77 , 104501 (2008).
- [10] S.-C. Lee, S.-Y. Lee, and S. M. Anlage, Microwave nonlinearities of an isolated long YBa2Cu3O7 -δ bicrystal grain boundary, Phys. Rev. B 72 , 024527 (2005).
- [11] D. I. Mircea, H. Xu, and S. M. Anlage, Phase-sensitive harmonic measurements of microwave nonlinearities in cuprate thin films, Phys. Rev. B 80 , 144505 (2009).
- [12] T. Tai, X X Xi, C. G. Zhuang, D. I. Mircea, and S. M. Anlage, Nonlinear Near-Field Microwave Microscope for rf Defect Lo-

## ACKNOWLEDGMENT

This research was conducted with support from the U.S. Department of Energy Office of High Energy Physics through Grant No. DESC0017931.

- calization in Superconductors, IEEE Trans. Appl. Supercond. 21 , 2615 (2011).
- [13] T. Tai, B. G. Ghamsari, and S. M. Anlage, Nanoscale Electrodynamic Response of Nb Superconductors, IEEE Trans. Appl. Supercond. 23 , 7100104 (2013).
- [14] T. Tai, B. G. Ghamsari, T. R. Bieler, T. Tan, X. X. Xi, and S. M. Anlage, Near-field microwave magnetic nanoscopy of superconducting radio frequency cavity materials, Appl. Phys. Lett. 104 , 232603 (2014).
- [15] T. Tai, B. G. Ghamsari, T. R. Bieler, and S. M. Anlage, Nanoscale nonlinear radio frequency properties of bulk Nb: Origins of extrinsic nonlinear effects, Phys. Rev. B 92 , 134513 (2015).
- [16] B. Oripov, T. R. Bieler, G. Ciovati, S. Calatroni, P. Dhakal, T. Junginger, O. B. Malyshev, G. Terenziani, A.-M. Valente-Feliciano, R. Valizadeh, S. Wilde, and S. M. Anlage, High-Frequency Nonlinear Response of Superconducting Cavity-Grade Nb Surfaces, Phys. Rev. Appl. 11 , 64030 (2019).
- [17] T. Tai, B G Ghamsari, and S. M. Anlage, Modeling the nanoscale linear response of superconducting thin films measured by a scanning probe microwave microscope, J. Appl. Phys 115 , 203908 (2014).
- [18] L. D. Landau and V. L. Ginzburg, On the theory of superconductivity, Zh. Eksp. Teor. Fiz 20 , 1064 (1950).
- [19] V. L. Ginzburg and L. D. Landau, On the theory of superconductivity, in On Superconductivity and Superfluidity: A Scientific Autobiography (Springer-Verlag, Berlin, 2009), pp. 113-137.
- [20] M. Cyrot, Ginzburg-Landau theory for superconductors, Rep. Prog. Phys. 36 , 103 (1973).
- [21] M. Tinkham, Introduction to Superconductivity , 2nd ed. (Dover, New York, 2004).
- [22] N. N. Bogoliubov, A new method in the theory of superconductivity. I, Sov. Phys. JETP 34 , 58 (1958).
- [23] N. N. Bogoliubov, A new method in the theory of superconductivity. III, Sov. Phys. JETP 34 , 73 (1958).
- [24] P. G. De Gennes, Boundary effects in superconductors, Rev. Mod. Phys. 36 , 225 (1964).
- [25] P. G. De Gennes, Superconductivity of Metals and Alloys (Perseus, Boulder, CO, 1999).
- [26] A. A. Abrikosov, L. P. Gor'kov, and I. E. Dzyaloshinski, in MethodsofQuantumFieldTheoryinStatisticalPhysics , 2nd ed., edited by Richard A. Silverman, Dover Books on Physics (Dover, New York, 1975).
- [27] N. B. Kopnin, Theory of Nonequilibrium Superconductivity , International Series of Monographs on Physics (Oxford, New York, 2001).
- [28] L. P. Gor'kov, On the energy spectrum of superconductors, Sov. Phys. JETP 34 , 735 (1958).

- [29] G. Eilenberger, Transformation of Gorkov's equation for type II superconductors into transport-like equations, Z. Phys. 214 , 195 (1968).
- [30] H. Ehrenreich, F. Seitz, and D. Turnbull, Solid State Physics , 1st ed., Advances in Research and Applications Vol. 37 (Academic, New York, 1983).
- [31] K. D. Usadel, Generalized Diffusion Equation for Superconducting Alloys, Phys. Rev. Lett. 25 , 507 (1970).
- [32] M. G. Flokstra, Proximity effects in superconducting spin-valve structures, Ph.D. thesis, Leiden University, 2010.
- [33] A. A. Schmid, A time dependent Ginzburg-Landau equation and its application to the problem of resistivity in the mixed state, Physik der Kondensierten Materie 5 , 302 (1966).
- [34] L. P. Gor'kov and G. M. Eliashberg, Generalization of the Ginzburg-Landau equations for non-stationary problems in the case of alloys with paramagnetic impurities, Sov. Phys. JETP 27 , 328 (1968).
- [35] A. Gurevich and T. Kubo, Surface impedance and optimum surface resistance of a superconductor with an imperfect surface, Phys. Rev. B 96 , 184515 (2017).
- [36] T. Kubo and A. Gurevich, Field-dependent nonlinear surface resistance and its optimization by surface nanostructuring in superconductors, Phys. Rev. B 100 , 064522 (2019).
- [37] R. C. Dynes, V. Narayanamurti, and J. P. Garno, Direct Measurement of Quasiparticle-Lifetime Broadening in a Strong-Coupled Superconductor, Phys. Rev. Lett. 41 , 1509 (1978).
- [38] R. C. Dynes, J. P. Garno, G. B. Hertel, and T. P. Orlando, Tunneling Study of Superconductivity near the Metal-Insulator Transition, Phys. Rev. Lett. 53 , 2437 (1984).
- [39] J. F. Zasadzinski, Tunneling spectroscopy of conventional and unconventional superconductors, in The Physics of Superconductors , edited by K. H. Bennemann and J. B. Ketterson (Springer-Verlag, Berlin, 2003), Vol. 1, Chap. 8, p. 591.
- [40] A. V. Balatsky, I. Vekhter, and J.-X. Zhu, Impurity-induced states in conventional and unconventional superconductors, Rev. Mod. Phys. 78 , 373 (2006).
- [41] T. Proslier, J. F. Zasadzinski, L. D. Cooley, C. Z. Antoine, J. Moore, J. Norem, M. Pellin, and K. E. Gray, Tunneling study of cavity grade Nb: Possible magnetic scattering at the surface, Appl. Phys. Lett. 92 , 212505 (2008).
- [42] L. Kramer and R. J. Watts-Tobin, Theory of Dissipative Current-Carrying States in Superconducting Filaments, Phys. Rev. Lett. 40 , 1041 (1978).
- [43] D. Y. Vodolazov, F. M. Peeters, M. Morelle, and V. V. Moshchalkov, Masking effect of heat dissipation on the currentvoltage characteristics of a mesoscopic superconducting sample with leads, Phys. Rev. B 71 , 184502 (2005).
- [44] G. Blatter, M. V. Feigel'man, V. B. Geshkenbein, A. I. Larkin, and V. M. Vinokur, Vortices in high-temperature superconductors, Rev. Mod. Phys. 66 , 1125 (1994).
- [45] I. S. Aranson and L. Kramer, The world of the complex Ginzburg-Landau equation, Rev. Mod. Phys. 74 , 99 (2002).
- [46] M. Machida and H. Kaburaki, Direct Simulation of the TimeDependent Ginzburg-Landau Equation for Type-II Superconducting Thin Film: Vortex Dynamics and V-I Characteristics, Phys. Rev. Lett. 71 , 3206 (1993).
- [47] W. D. Gropp, H. G. Kaper, G. K. Leaf, D. M. Levine, M. Palumbo, and V. M. Vinokur, Numerical simulation of vortex
20. dynamics in type-II superconductors, J. Comput. Phys. 123 , 254 (1996).
- [48] A. D. Hernández and D. Domínguez, Dissipation spots generated by vortex nucleation points in mesoscopic superconductors driven by microwave magnetic fields, Phys. Rev. B 77 , 224505 (2008).
- [49] G. R. Berdiyorov, M. M. Doria, A. R. de C. Romaguera, M. V. M. Miloševi´ c, E. H. Brandt, and F. M. Peeters, Currentinduced cutting and recombination of magnetic superconducting vortex loops in mesoscopic superconductor-ferromagnet heterostructures, Phys. Rev. B 87 , 184508 (2013).
- [50] C. W. Robson, K. A. Fraser, and F. Biancalana, Giant ultrafast Kerr effect in superconductors, Phys. Rev. B 95 , 214504 (2017).
- [51] E. Sardella, A. L. Malvezzi, P. N. Lisboa-Filho, and W. A. Ortiz, Temperature-dependent vortex motion in a square mesoscopic superconducting cylinder: Ginzburg-Landau calculations, Phys. Rev. B 74 , 014512 (2006).
- [52] T. S. Alstrøm, M. P. Sørensen, N. F. Pedersen, and S. Madsen, Magnetic flux lines in complex geometry type-II superconductors studied by the time dependent GinzburgLandau equation, Acta Applicandae Mathematicae 115 , 63 (2011).
- [53] H. Rogalla, 100 Years of Superconductivity (Taylor &amp; Francis, London, 2011).
- [54] A. D. Hernández and D. Domínguez, Surface barrier in mesoscopic type-I and type-II superconductors, Phys. Rev. B 65 , 144529 (2002).
- [55] I. S. Aranson, N. B. Kopnin, and V. M. Vinokur, Dynamics of vortex nucleation by rapid thermal quench, Phys. Rev. B 63 , 184501 (2001).
- [56] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, Microscopic theory of superconductivity, Phys. Rev. 106 , 162 (1957).
- [57] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, Theory of superconductivity, Phys. Rev. 108 , 1175 (1957).
- [58] Note that the zero temperature GL coherence length ξ 0 can also be used as a normalization length scale (see Refs. [47,67]).
- [59] This time scale is also used in Refs. [47,52,54,60,94].
- [60] A. I. Blair and D. P. Hampshire, Time-dependent GinzburgLandau simulations of the critical current in superconducting films and junctions in magnetic fields, IEEE Trans. Appl. Supercond. 28 , 1 (2018).
- [61] A. Gurevich, Theory of rf superconductivity for resonant cavities, Supercond. Sci. Technol. 30 , 034004 (2017).
- [62] I. A. Sadovskyy, A. E. Koshelev, C. L. Phillips, D. A. Karpeyev, and A. Glatz, Stable large-scale solver for Ginzburg-Landau equations for superconductors, J. Comput. Phys. 294 , 639 (2015).
- [63] R. Geurts, M. V. Miloševi´ c, and F. M. Peeters, Second generation of vortex-antivortex states in mesoscopic superconductors: Stabilization by artificial pinning, Phys. Rev. B 79 , 174508 (2009).
- [64] S. Miyamoto and T. Hikihara, Dynamical behavior of fluxoid and arrangement of pinning center in superconductor based on TDGL equation, Physica C 417 , 7 (2004).
- [65] A. Aftalion, E. Sandier, and S. Serfaty, Pinning phenomena in the Ginzburg-Landau model of superconductivity, Journal des Mathematiques Pures et Appliquees 80 , 339 (2001).

- [66] COMSOL multiphysics modeling software, https://www.comsol. com.
- [67] L. Peng and C. Cai, Finite element treatment of vortex states in 3D cubic superconductors in a tilted magnetic field, J. Low Temp. Phys. 188 , 39 (2017).
- [68] D. Salvi, D. Boldor, J. Ortego, G. M. Aita, and C. M. Sabliov, Numerical modeling of continuous flow microwave heating: A critical comparison of COMSOL and ANSYS, J. Microwave Power Electromagn. Energy 44 , 187 (2010).
- [69] G. Gomes, Comparison between COMSOL and RFSP-IST for a 2-D Benchmark Problem, in Proceedings of the COMSOL Conference , 2008, https://www.comsol.jp/paper/download/37875/ Gomes.pdf.
- [70] M. Cardiff and P. K. Kitanidis, Efficient solution of nonlinear, underdetermined inverse problems with a generalized PDE model, Comput. Geosci. 34 , 1480 (2008).
- [71] Q. Du, Finite element methods for the time-dependent Ginzburg-Landau model of superconductivity, Comput. Math. Appl. 27 , 119 (1994).
- [72] For all the simulations presented in this paper, the timedependent study in the COMSOL MULTIPHYSICS software was used. The Direct-MUMPS solver with the default parameters was used as the general solver and time stepping was performed using the Backward Differentiation Formula solver. The maximum time step was constrained to 1. The free tetrahedral mesh was used on the y &gt; 0 domain, and the same mesh was mirrored in the y &lt; 0 domain.
- [73] E. A. Matute, On the superconducting sphere in an external magnetic field, Am. J. Phys. 67 , 786 (1999).
- [74] A. S. Mel'nikov, Yu. N. Nozdrin, I. D. Tokman, and P. P. Vysheslavtsev, Experimental investigation of a local mixed state induced by a small ferromagnetic particle in YBaCuO films: Extremely low energy barrier for formation of vortexantivortex pairs, Phys. Rev. B 58 , 11672 (1998).
- [75] A. Romanenko, A. Grassellino, O. Melnychuk, and D. A. Sergatskov, Dependence of the residual surface resistance of superconducting radio frequency cavities on the cooling dynamics around T c , J. Appl. Phys 115 , 184903 (2014).
- [76] Michael J. Conover, principal engineer at Seagate Technology, modeled magnetic field contours (private communication, 2018).
- [77] D. Xu, S. K. Yip, and J. A. Sauls, Nonlinear Meissner effect in unconventional superconductors, Phys. Rev. B 51 , 16233 (1995).
- [78] T. Chow, Introduction to Electromagnetic Theory: A Modern Perspective , 1st ed. (Jones &amp; Bartlett, Boston, 2006), Chap. 4, p. 146.
- [79] D. B. Liarte, S. Posen, M. K. Transtrum, G. Catelani, M. Liepe, and J. P. Sethna, Theoretical estimates of maximum fields in superconducting resonant radio frequency cavities: Stability theory, disorder, and laminates, Supercond. Sci. Technol. 30 , 033002 (2017).
- [80] A. R. Jana, A. Kumar, V. Kumar, and S. B. Roy, Influence of material parameters on the performance of niobium based superconducting rf cavities, arXiv:1703.07985.
- [81] See Supplemental Material at http://link.aps.org/supplemental/ 10.1103/PhysRevE.101.033306 for the time loop of the solution to the TDGL equations illustrated in Fig. 7 and for the solution to the TDGL equations as a function of peak applied magnetic field as illustrated in Fig. 9.
- [82] T. Tai, Measuring electromagnetic properties of superconductors in high and localized rf magnetic field, Ph.D. thesis, University of Maryland, 2013.
- [83] M. K. Transtrum, G. Catelani, and J. P. Sethna, Superheating field of superconductors within Ginzburg-Landau theory, Phys. Rev. B 83 , 094505 (2011).
- [84] A. Gurevich, Maximum screening fields of superconducting multilayer structures, AIP Advances 5 , 017112 (2015).
- [85] C. Z. Antoine, M. Aburas, A. Four, F. Weiss, Y. Iwashita, H. Hayano, S. Kato, T. Kubo, and T. Saeki, Optimization of tailored multilayer superconductors for rf application and protection against premature vortex penetration, Supercond. Sci. Technol. 32 , 085005 (2019).
- [86] A. Grassellino, A. Romanenko, D. A. Sergatskov, O. Melnychuk, Y. Trenikhina, A. Crawford, A. Rowe, M. Wong, T. Khabiboulline, and F. Barkov, Nitrogen and argon doping of niobium for superconducting radio frequency cavities: A pathway to highly efficient accelerating structures, Supercond. Sci. Technol. 26 , 102001 (2013).
- [87] M. Martinello, A Grassellino, M. Checchin, A. Romanenko, O. Melnychuk, D. A. Sergatskov, S. Posen, and J. F. Zasadzinski, Effect of interstitial impurities on the field dependent microwave surface resistance of niobium, Appl. Phys. Lett 109 , 062601 (2016).
- [88] V. Ngampruetikorn and J. A. Sauls, Effect of inhomogeneous surface disorder on the superheating field of superconducting rf cavities, Phys. Rev. Res. 1 , 012015 (2019).
- [89] A. Romanenko, A. Grassellino, F. Barkov, A. Suter, Z. Salman, and T. Prokscha, Strong Meissner screening change in superconducting radio frequency cavities due to mild baking, Appl. Phys. Lett 104 , 072601 (2014).
- [90] A. Romanenko, Pathway to high gradients in superconducting rf cavities by avoiding flux dissipation, in Proceedings of the Ninth Annual International Particle Accelerator Conference, 2018 (unpublished), http://accelconf.web.cern.ch/AccelConf/ ipac2018/talks/weygbf2\_talk.pdf, 2018.
- [91] A. Schmid, The approach to equilibrium in a pure superconductor, the relaxation of the Cooper pair density, Physik der Kondensierten Materie 8 , 129 (1968).
- [92] S. B. Kaplan, C. C. Chi, D. N. Langenberg, J. J. Chang, S. Jafarey, and D. J. Scalapino, Quasiparticle and phonon lifetimes in superconductors, Phys. Rev. B 14 , 4854 (1976).
- [93] A. Gurevich, Enhancement of rf breakdown field of superconductors by multilayer coating, Appl. Phys. Lett. 88 , 012511 (2006).
- [94] A. D. Hernández, A. López, and D. Domínguez, Anisotropic ac dissipation at the surface of mesoscopic superconductors, Appl. Surf. Sci. 254 , 69 (2007).