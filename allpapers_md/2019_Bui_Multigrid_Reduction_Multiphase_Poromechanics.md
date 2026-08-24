## A SCALABLE MULTIGRID REDUCTION FRAMEWORK FOR MULTIPHASE POROMECHANICS OF HETEROGENEOUS MEDIA ∗

QUAN M. BUI † , DANIEL OSEI-KUFFUOR ‡ , NICOLA CASTELLETTO § , AND JOSHUA A. WHITE §

Abstract. Simulation of multiphase poromechanics involves solving a multi-physics problem in which multiphase flow and transport are tightly coupled with the porous medium deformation. To capture this dynamic interplay, fully implicit methods, also known as monolithic approaches, are usually preferred. The main bottleneck of a monolithic approach is that it requires solution of large linear systems that result from the discretization and linearization of the governing balance equations. Because such systems are non-symmetric, indefinite, and highly ill-conditioned, preconditioning is critical for fast convergence. Recently, most efforts in designing efficient preconditioners for multiphase poromechanics have been dominated by physics-based strategies. Current state-ofthe-art 'black-box' solvers such as algebraic multigrid (AMG) are ineffective because they cannot effectively capture the strong coupling between the mechanics and the flow sub-problems, as well as the coupling inherent in the multiphase flow and transport process. In this work, we develop an algebraic framework based on multigrid reduction (MGR) that is suited for tightly coupled systems of PDEs. Using this framework, the decoupling between the equations is done algebraically through defining appropriate interpolation and restriction operators. One can then employ existing solvers for each of the decoupled blocks or design a new solver based on knowledge of the physics. We demonstrate the applicability of our framework when used as a 'black-box' solver for multiphase poromechanics. We show that the framework is flexible to accommodate a wide range of scenarios, as well as efficient and scalable for large problems.

1. Introduction. Modeling subsurface systems requires an understanding of many different physical processes, including multiphase fluid flow and transport, and geomechanical deformations. These processes are often tightly coupled in a 'two-way' fashion: for example, the flow process can have a large influence on the mechanical process and in turn can be affected by the feedback of the produced mechanical response. To simulate these processes, one needs to solve a set of coupled, nonlinear, time-dependent partial differential equations (PDEs) that govern the conservation of mass of the fluid phases and linear momentum of the solid-fluid mixture. For this system, fully-implicit time discretization is the widely preferred approach because it is unconditionally stable and allows for large time steps. However, using an implicit approach, one must solve a large, sparse, and ill-conditioned linear system at each nonlinear iteration. Robust and scalable solvers are therefore needed for large scale simulations on high performance computing platforms. This paper presents our efforts to design an efficient preconditioning strategy based on an algebraic framework that is flexible and capable of addressing the inherent ill-conditioning of a complicated multi-physics system.

In recent years, much of the work in developing preconditioning strategies for coupled problems has focused on so-called physics-based strategies. The key is to

∗ Submitted to the editors April 15, 2019.

Funding: This work was funded by LLNL through Laboratory Directed Research and Development (LDRD) Project 18-ERD-027. Portions of this work were performed under the auspices of the U.S. Department of Energy by Lawrence Livermore National Laboratory under Contract DE-AC5207-NA27344.

† Corresponding Author. Center for Applied Scientific Computing, Lawrence Livermore National Laboratory, United States (bui9@llnl.gov)

‡ Center for Applied Scientific Computing, Lawrence Livermore National Laboratory, United States (oseikuffuor1@llnl.gov).

§ Atmospheric, Earth and Energy Division, Lawrence Livermore National Laboratory, United States (castelletto1@llnl.gov, jawhite@llnl.gov).

use knowledge of the specific physical processes involved to break the tightly coupled systems into smaller sub-problems whose properties are well-studied. For example, these sub-problems could take the form of an elliptic, hyperbolic, or parabolic PDE, to which appropriate techniques can be applied. For fully implicit simulation of complex multiphase flow and transport without mechanics, one of the most popular methods is the Constrained Residual Pressure (CPR) multistage preconditioning technique [42, 43]. For single-phase flow poromechanics, many block preconditioners have been developed [1, 5, 6, 23, 28, 45, 47]. In the context of multiphase poromechanics, one recent strategy [46] uses the fixed-stress partitioning [25, 31, 37, 47] of the mechanics and the flow parts combined with a CPR approach [42] for the multiphase flow system. In general, these physics-based preconditioners are among the most effective techniques available. However, designing a good strategy is both time-consuming and challenging as it requires extensive knowledge of the particular continuous model of interest. One alternative is to use a 'black-box' approach, such as algebraic multigrid (AMG) [39, 41]. AMG techniques are among the most efficient and scalable methods for solving sparse linear systems. Unlike geometric multigrid , these methods do not need an explicit hierarchy of computational grids. However, they are originally designed for scalar elliptic PDEs, and their applicability is much more limited for strongly coupled systems of PDEs.

Recently, multigrid reduction (MGR) [33, 34], a variant of AMG, has been applied successfully to coupled systems of multiphase flow and transport with phase transitions [8, 44]. Drawing on this success, in this work we further develop MGR into a general multi-level framework for solving discrete systems coming from discretization of tightly coupled PDEs. We also introduce a new dropping strategy for computing the reduction onto the coarse-grid within the MGR V-cycle that effectively captures the coupling between mechanics and flow. The goal of this strategy is two-pronged: (1) to keep the coarse grid sparse during multi-level reduction, and (2) to make the coarse grid amenable to classical AMG. We show that with this new feature, MGR is effective as a general-purpose algebraic solver for multiphase poromechanics, and it also scales well with problem size. The rest of the paper is organized as follows. Section 2 and 3 introduce the governing equations of multiphase poromechanics and the discretization scheme. Section 4 describes the nonlinear solution algorithm. In section 5, we describe the MGR framework and how it is applied to solve the linear systems coming from the linearization. We show numerical results in section 6 to demonstrate the robustness and scability of the proposed preconditioner. We then end with some concluding remarks and directions for future work.

2. Problem Statement. We focus on a displacement-saturation-pressure formulation of immiscible two-phase flow through a deforming poroelastic medium [13]. We limit the discussion to quasi-static small-strain kinematics. Let the subscript w and nw denote the wetting and non-wetting fluid phase, respectively. Since the medium's pore space is always fluid-filled, the fluid phase saturations must always sum to unity, i.e. ( s w + s nw ) = 1. Here, the wetting fluid phase saturation, denoted from now on by lower case s without subscript, is used as a primary unknown. Capillary pressure, which is the difference between the phase pressure of the nonwetting phase and the wetting phase, is not considered-a frequent assumption in many practical engineering applications. Hence, we have p w = p nw = p .

For a given closed domain Ω = Ω ∪ Γ ∈ R 3 , with Ω an open set and Γ its boundary, and time interval I = (0 , t max ], the strong form of the multiphase poromechanical initial/boundary value problem (IBVP) consists of finding the displacement vector

field u : Ω × I → R 3 , the wetting fluid phase saturation s : Ω × I → R 3 , and the pore pressure p : Ω × I → R such that [13]:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where

- σ = ( C : ∇ s u -bp 1 ) is the total Cauchy stress tensor, with C the rank-4 elasticity tensor, b the Biot coefficient, and 1 the rank-2 identity tensor;
- ρ g is a body force due to the self-weight of the multiphase mixture, with ρ = ((1 -φ ) ρ s + φρ w s + φρ nw (1 -s )) the density of the mixture, φ the porosity, ρ s , ρ w , ρ nw the density of the solid, the wetting, and the non-wetting fluid phase, respectively, and g the gravity vector;
- m w = ( φρ w s ) and m nw = ( φρ nw (1 -s )) denote wetting and non-wetting fluid phase mass per unit volume;
- w w = -( ρ w λ w κ ·∇ Φ w ) and w nw = -( ρ nw λ nw κ ·∇ Φ nw ) are wetting and nonwetting fluid phase mass fluxes [2], with λ glyph[lscript] = k rglyph[lscript] /µ glyph[lscript] the phase mobility, µ glyph[lscript] the phase viscosity, k rglyph[lscript] the phase relative permeability factor, κ the absolute permeability tensor, Φ glyph[lscript] = ( p -ρ glyph[lscript] g · x ) the phase potential, x the position vector in R 3 , glyph[lscript] = { w,nw } ;
- q w and q nw are mass source/sink per unit volume terms for the wetting and the non-wetting fluid phase, respectively;
- ∇ , ∇ s , and ∇· are the gradient, symmetric gradient, and divergence operator, respectively;
- the superposed dot, ˙ ( · ), indicates the derivative of quantity ( · ) with respect to time .

For the application of boundary conditions, let us introduce two disjoint partitions of the domain boundary such that Γ = Γ D u ∪ Γ N u = Γ D f ∪ Γ N f . Without loss of generality, consider homogeneous displacement boundary conditions u = 0 on Γ D u × I and homogeneous flux conditions w w · n = w nw · n = 0 on Γ N f × I , along with a prescribed total traction conditions σ · n = t N on Γ N u × I and pressure/saturation conditions p = p D and s = s D on Γ D f × I , where n denotes the outer normal vector for Γ. More complicated boundary conditions may be introduced as needed with modest changes to the discretization below. The formulation is completed by appropriate: (i) initial conditions for u , s , and p , and (ii) equations of state and constitutive equations to specify the following dependencies: φ = φ ( u , p ), ρ glyph[lscript] = ρ glyph[lscript] ( p ), µ glyph[lscript] = µ glyph[lscript] ( p ), and k rglyph[lscript] = k rglyph[lscript] ( s ), with glyph[lscript] = { w,nw } . For additional details on the adopted poromechanical model we refer the reader to [46].

3. Discretization. Several space discretization methods for the multiphase poromechanical IBVP have been proposed in the literature-see, e.g., [29, 22, 46, and references therein]. In this work, the discrete form of (2.1) is obtained by combining a finite element (FE) method for the mechanical subproblem with a finite volume (FV) approach for the multiphase flow and transport subproblem. This choice is quite common when modeling nonlinear hydromechanical processes in subsurface formations characterized by highly heterogeneous hydrogeological properties, e.g. highcontrast permeability fields typically encountered in practical reservoir simulation [37, 26, 32, 19, 38].

Let H 1 0 (Ω) denote the Sobolev space of vector functions satisfying displacement

homogeneous Dirichlet conditions over Γ D u and whose first derivatives belong to L 2 (Ω), with L 2 (Ω) the space of square integrable functions in Ω; let U h ⊂ H 1 0 (Ω), S h ⊂ L 2 (Ω), P h ⊂ L 2 (Ω) denote finite-dimensional subspaces associated with a conforming triangulation T h of the domain into nonoverlapping hexahedral cells; and let ̂ w ε glyph[lscript] denote a conservative numerical flux approximating the glyph[lscript] fluid phase mass flux across face ε in E h , namely the set of faces in T h , such that ̂ w ε glyph[lscript] ≈ -∫ ε w glyph[lscript] · n ε d A , with n ε a unit normal vector defining the global face orientation.

Precisely, our space discretization employs: (i) continuous piecewise trilinear finite elements for U h , (ii) piecewise constant functions for S h and P h , and (iii) a linear two-point flux approximation (TPFA) combined with a first-order upwinding strategy for the numerical flux ̂ w ε glyph[lscript] [2]. Using a fully-implicit time marching scheme, with the subscript n indicating the discrete time level, the fully discrete mixed FE/FV variational statement of (2.1) is: find { u h n , s h n , p h n } ∈ U h ×S h ×P h such that for all { η h , ψ h , χ h } ∈ U h ×S h ×P h

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where n ∈ { 1 , 2 , . . . } . The compact notation ( · , · ) denotes the L 2 -inner product of scalar, vector, or rank-2 tensor functions in L 2 (Ω), [ L 2 (Ω)] 3 , or [ L 2 (Ω)] 3 × 3 , as appropriate. In (3.1b)-(3.1c), ∆ t n = ( t n -t n -1 ) is the timestep size; E h,N f is the set of faces belonging to the boundary Γ N f ; and J · K ε indicates the jump of a quantity ( · ) across ε . For an internal face ε shared by cells K and L , n ε pointing from K to L , J · K ε = (( · ) | L -( · ) | K ), with ( · ) | K and ( · ) | L the restriction of ( · ) on K and L , respectively. For a boundary lying on Γ D f , n ε coincides with the outer normal to the domain boundary and the jump expression simply reads · ε = -( · ) | K .

J K Finally, introducing in (3.1) the expressions u h n = ∑ i u i,n η h i , s h n = ∑ j s j,n ψ h j , and p h n = ∑ k p k,n χ h k , with { η h i } , { ψ h j } , and { χ h k } bases for U h , S h , and P h , respectively, a standard Galerkin approach yields a system of nonlinear discrete equations

<!-- formula-not-decoded -->

Here, vector x n contains the nodal displacement ( u i,n ), cell-centered saturation s i,n and cell-centered pressure p i,n coefficients that are used to expand u h n , s h n , and p h n in terms of the respective basis functions at time level n .

4. Newton-Krylov Solver. The nonlinear system (3.2) is solved by means of Newton's method, with a backtracking strategy added for robustness. The solution at time t n is computed as follows. Given an initial guess x 0 n , for k = 0 , 1 , . . . , until convergence

<!-- formula-not-decoded -->

where A ( x ( k ) n ) = ( ∂F/∂ x n )( x ( k ) n ) is the Jacobian matrix associated with the nonlinear residual function F , and λ ∈ (0 , 1] is an appropriately chosen line-search parameter. For convenience of notation, we omit from now on to specify that A is evaluated at x ( k ) n . Clearly, at each nonlinear iteration k , the solution of a linear system with A is required.

The linearization of (3.2) produces a Jacobian system with an inherent 3 × 3 block structure

<!-- formula-not-decoded -->

This system has size proportional to the number of vertices (three displacement degrees of freedom per vertex) and cells (one saturation and one pressure degree of freedom per cell) in the computational mesh. For detailed expressions of the subblocks in A , we refer the reader to [46]. Briefly, we emphasize the properties of the three diagonal blocks that motivate choices in designing the preconditioning operator described in section 5. Specifically:

- A uu is the elasticity block and has the structure of a discrete elliptic operator;
- A ss is the saturation block that, in the abscence of capillarity effects, has the structure of a discrete time-dependent hyperbolic problem;
- A pp is the pressure block that, similar to the elastic block, has the structure of a discrete elliptic operator.

In this work, the linear system with matrix A is solved iteratively with generalized minimal residual (GMRES) [35], a Krylov subspace method designed for nonsymmetric systems. Since Krylov methods' practical convergence depends on the availability of an effective preconditioner, we introduce the preconditioning operator M and replace the linear system in (4.1) with the right preconditioned system,

<!-- formula-not-decoded -->

where ∆ x = M -1 ∆ y . In the following section, we describe an algebraic method to construct M given a matrix A with the structure specified in (4.2).

5. Multigrid Reduction. The idea of MGR has been around for a long time, tracing back to the work of Ries and Trottenberg [33, 34]. Recently, it has gained more attention through the work on multigrid reduction in time by Falgout et al. [15, 16]. MGR has also been applied successfully for problems in reservoir simulation and multiphase flow in porous media with phase transitions [8, 44]. A major advantage of the MGR approach is that it is an algebraic method and unlike geometric multigrid, it can be applied to general geometries and grid types. In this section, we first summarize the approach for the case of two-level reduction and then present the general multilevel reduction algorithm.
2. 5.1. Two-grid Reduction Scheme. For a matrix A of size N × N , we define a partition of the row indices of the matrix into C-points and F-points. The C-points play a role analogous to the points on a coarse grid, and the F-points belong to the set that is the complement of the C-points. It is important to note that this partitioning is different from the one normally used in standard multigrid methods, in which the F-points correspond to all points on the fine grid, i.e. the set of F-points contains the set of C-points. In multigrid reduction, the C-points and F-points belong to

non-overlapping sets. Following [15], using such CF-splitting we have

<!-- formula-not-decoded -->

where I CC and I FF are identity matrices and S = A CC -A CF A -1 FF A FC is the Schur complement. We can define the ideal interpolation and restriction operators by

<!-- formula-not-decoded -->

Additionally, define the injection operator as Q = ( I FF 0 ) . Then since A FF = Q T AQ and S = RAP , it is simple to derive that

<!-- formula-not-decoded -->

and

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where the equivalence occurs since RAQ = Q T AP = 0. This identity defines the twolevel multigrid method with the ideal Petrov-Galerkin coarse-grid correction ( RAP ) -1 and the F-relaxation Q ( Q T AQ ) -1 Q T : (i) Equation (5.4) is the additive MGR identity and (ii) (5.5) and (5.6) are multiplicative identities with pre-smoothing and postsmoothing F-relaxation, respectively. However, constructing ideal interpolation and restriction operators is impractical. Similarly, computing the coarse-grid correction exactly is expensive, so we need to approximate these operators. In practice, MGR methods use a scalable solver such as AMG for the coarse-grid solve, and replace the ideal restriction and prolongation R and P with

<!-- formula-not-decoded -->

where

<!-- formula-not-decoded -->

There are many ways to construct these approximations. One simple choice is to use an injection operator for restriction and a Jacobi approach for interpolation

<!-- formula-not-decoded -->

where D FF = diag( A FF ). Then the coarse grid operator A h = ˜ RA ˜ P can also be considered as an approximation to the Schur complement S . Besides the choices in (5.9), one can also choose to use Jacobi approach for restriction, that is W r = -A CF D -1 FF . Another option is to construct A -1 FF using incomplete factorizations (ILU) or sparse approximate inverse techniques, such as sparse approximate inverse (SPAI) [21], factored sparse approximate inverse (FSAI) [18], or minimal residual (MR) [11]. Although these methods could provide a better approximation to A -1 FF , and therefore

better approximations for the restriction and interpolation operators, they tend to make these operators dense. The resulting coarse grid also becomes dense and unamenable to AMG. One can certainly apply a dropping strategy to keep such ˜ P and ˜ R sparse, but in practice, the potential improvement in performance using approximate inverse methods is usually offset by the cost to construct the approximation, which makes simple methods like Jacobi more appealing.

In general, we define the MGR operator with either pre-smoothing or postsmoothing F-relaxation by

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where M CC = ( ˜ RA ˜ P ) is the coarse-grid correction and M -1 FF is the F-relaxation smoother. Additionally, similar to AMG methods, one can also apply a global smoothing step that extends to all the unknowns, not just the F-points. For the global smoother M -1 glo , various methods including (block) Jacobi, (block) Gauss-Seidel, or ILU, can be used. The inclusion of this step can help eliminate error modes that both the F-relaxation and coarse-grid correction may have missed. The application of the twogrid MGR scheme consisting of a global smoother and an F-relaxation followed by a coarse-grid correction can be summarized as shown in Algorithm 5.1.

| Algorithm 5.1 Two-grid MGR preconditioner with presmoothing, z = M - 1 MGR v .   | Algorithm 5.1 Two-grid MGR preconditioner with presmoothing, z = M - 1 MGR v .   | Algorithm 5.1 Two-grid MGR preconditioner with presmoothing, z = M - 1 MGR v .   |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| 1:                                                                               | function MGR ( A,v )                                                             | function MGR ( A,v )                                                             |
| 2:                                                                               | z = M - 1 glo v                                                                  | glyph[triangleright] Global Relaxation                                           |
| 3:                                                                               | z ← z + QM - 1 FF Q T ( v - Az )                                                 | glyph[triangleright] F-Relaxation                                                |
| 4:                                                                               | r C = ˜ R ( v - Az )                                                             | glyph[triangleright] Restrict residual                                           |
| 5:                                                                               | M CC e C = r C                                                                   | glyph[triangleright] Solve coarse-grid error problem with AMG                    |
| 6:                                                                               | e = ˜ Pe C                                                                       | glyph[triangleright] Interpolate coarse error approximation                      |
| 7:                                                                               | z ← z + e                                                                        | glyph[triangleright] Apply correction                                            |
| 8:                                                                               | return z                                                                         | return z                                                                         |
| 9:                                                                               | end function                                                                     | end function                                                                     |

Balancing the quality of the approximation to the Schur-complement and the convergence of the coarse-grid solve is key to the success of MGR. One extreme is to design a coarse grid that is perfectly suitable for AMG. Assuming, for example, that the block A CC comes from a scalar elliptic PDE and A CC is SPD, then one can choose W p = W r = 0 and the coarse grid becomes RAP = A CC . In this case, the convergence of the coarse grid solve is optimal, but the approximation of the Schur-complement far from ideal, since the coarse grid neither takes into account any information from the F-points nor the coupling between the C and F points. At the other extreme, one can use the exact Schur-complement as the coarse grid by choosing W r = -A CF A -1 FF and W p = 0. However, because of the exact inversion of A -1 FF , the coarse grid is dense. Furthermore, since the F-points and C-points actually represent equations obtained from the discretization of different continuous physical models, capturing the coupling between them on the coarse grid can lead to loss of ellipticity, which can make the coarse-grid solve with AMG ineffective. Thus, finding a good approximation of the Schur-complement that is still amenable to AMG methods is essential.

Remark 5.1. The appeal of the MGR approach is that it provides a general framework for choosing the coarse/fine grids, the interpolation and restriction operators,

and the solvers for the F-relaxation and coarse-grid correction. As an example, it was shown in [8, 44] that one can recast any CPR-AMG strategy [9, 20, 27, 30, 36, 40, 48] or block preconditioner [7] used in reservoir simulation as a particular variant of the two-grid MGR reduction scheme by appropriately defining the different components of the algorithm, namely prolongation, restriction and smoothing operators.

5.2. A general multi-level MGR algorithm. One can replace the coarse grid solve in Algorithm 5.1 with a two-level MGR scheme and apply the method recursively to obtain a multi-level MGR algorithm. The general application of the MGR V-cycle with global smoothing is summarized in Algorithm 5.2, where the hierarchy of coarse grid operators, i.e. A l +1 = ˜ R l A l ˜ P l , is assumed to be computed for each level l .

```
Algorithm 5.2 General multi-level MGR preconditioner, z = M l,MGR v . 1: function MGR ( A l , v l ) 2: if l is the coarsest level then 3: A l z l = v l glyph[triangleright] Solve coarse-grid error problem with AMG 4: else 5: z l = M -1 l,glo v l glyph[triangleright] Global Relaxation 6: z l ← z l + Q l M -1 l,FF Q T l ( v l -Az l ) glyph[triangleright] F-Relaxation 7: r l +1 = ˜ R l ( v l -A l z l ) glyph[triangleright] Restrict residual 8: e l +1 = MGR ( A l +1 , r l +1 ) glyph[triangleright] Recursion 9: e l = ˜ P l e l +1 glyph[triangleright] Interpolate coarse error approximation 10: z l ← z l + e l glyph[triangleright] Apply correction 11: end if 12: return z l 13: end function
```

-1

Based on Algorithm 5.2, W- and F-cycle versions of the MGR algorithm can also be defined [34]. Note that the Schur-complement S is approximated by the triple product RAP = A CC -A CF D -1 FF A FC in the classical two-grid reduction scheme in Algorithm 5.1. Even though we have introduced a sparse approximation to S by replacing A FF with its diagonal D FF , i.e. A -1 FF ≈ D -1 FF , in a multi-level reduction scheme, the coarse grid can still become dense or unsuitable for standard AMG because the correction term A cor = A CF D -1 FF A FC involves a matrix-matrix product.

In this work, we develop a dropping strategy for A cor to keep the coarse grid sparse as well as suitable for AMG. One approach is to drop all entries of A cor that are smaller than a prescribed tolerance. Here, we use a different strategy based on a maximum number of non-zero values per row. Specifically, we choose to keep only N max entries with largest absolute values on each row. To preserve at least some information of the first level of reduction, however, we always keep the diagonals of the sub-blocks in A cor . For instance, in a three-level reduction scheme, in the firstlevel reduction, A cor has 2 × 2 block structure, and applying maximum dropping (i.e. using an extremely large tolerance or N max = 0), A cor is still a 2 × 2 block matrix, whose sub-blocks are diagonal matrices. Using this dropping strategy results in a non-Galerkin coarse grid

<!-- formula-not-decoded -->

where G is a sparsifying operator that performs one of the aforementioned dropping strategies. So far we only assume that a CF-splitting of the rows is given. How to

choose such a splitting is dependent on the problem and it is up to the user to make the decision. However, as a general principle, it is usually a good idea to choose a CF-splitting so that the final coarse grid corresponds to the variable associated with an elliptic equation, e.g. pressure, since we want to solve the coarse grid using an efficient method such as standard AMG. In the next section, we show how to choose an appropriate CF-splitting at each level of reduction for our multiphase poromechanical problem.

- 5.3. MGR for Multiphase Poromechanics. We propose a three-level MGR reduction scheme to precondition the Jacobian matrix (4.2). For the first level of reduction, we aim at decoupling the mechanics sub-problem from the flow. Therefore, we assign all the displacement unknowns as F-points while both saturation and pressure unknowns are labeled as C-points. This leads to the following partitioning

<!-- formula-not-decoded -->

Then A FF ≡ A uu and the coarse grid A CC , which corresponds to the flow subproblem, has the 2 × 2 block structure

<!-- formula-not-decoded -->

For the F-relaxation step, we need to solve the elasticity problem involving the elliptic operator A uu . Here, we use one AMG V-cycle. Because of the vectorial nature of the elasticity operator, this is the most expensive part of the setup phase. Also, given the global system size, we ignore the first-level global relaxation step. Using the interpolation and restriction operators specified in (5.9) combined with the dropping strategy defined in Equation (5.12) yields the following first level coarse grid

<!-- formula-not-decoded -->

For our multiphase poromechanics problem, we use N max = 4 for G . Again, we emphasize the flexibility of our framework as it allows for experimenting with different choices of G . For example, choosing an appropriate G , we can mimic the fixed-stress preconditioner developed in [46].

The second reduction step is essentially a CPR approach that is embedded within a multigrid reduction framework. Hence, we label saturation unknowns as F-points and pressure unknowns as C-points in S 1 :

<!-- formula-not-decoded -->

Again, using interpolation and restriction operators in (5.9), we obtain the secondlevel Schur-complement

<!-- formula-not-decoded -->

where D ss = diag( ˜ A ss ). In other physics-based approaches commonly used in reservoir simulation, one can seek to further sparsify the Schur-complement. For example, in a Quasi-IMPES reduction scheme, the block ˜ A ps is also replaced by its diagonal D ps = diag( ˜ A ps ). This approximation ensures that the matrix sparsity pattern of A pp coming from the original finite volume stencil is preserved and the resulting Schur-complement is near elliptic. In the MGR approach, however, no further sparse approximation is needed for this level since the flow part is relatively small compared to the elasticity block and the coarse grid generated in (5.17) is still well-suited for AMG. At the second level, the F-relaxation involving the ˜ A ss block is done using a simple Jacobi relaxation. However, the second-level global smoothing step is required to reduce the error associated with the hyperbolic component of the flow subproblem. Indeed, the global smoothing plays a key role particularly in the later stage of the simulation when the pressure field approaches steady-state conditions and the multiphase flow and transport process transitions to an advection dominated regime. The need for a robust global smoother will become clear through numerical results presented in the next section.

Remark 5.2. Even though we formally present the multigrid reduction framework for the 3 × 3 system in field-ordered form, in our implementation, the input matrix has interleaved ordering for saturation and pressure. This choice produces a sparsity pattern in which dense 2 × 2 blocks appear for the first-level coarse grid in (5.15). Block versions of relaxation or incomplete factorization preconditioners are therefore appealing, as dense multiplication and inversion operations can be applied to the small blocks.

Remark 5.3. Common strategies for the second-level global smoothing step include block relaxation methods (e.g. Jacobi, Gauss-Seidel) or incomplete factorizations (e.g. ILU(k), ILUT). In this work, we explore two options. The first option uses several sweeps of hybrid block Gauss-Seidel (HBGS). The second option uses one sweep of processor-local, pointwise ILU(k) [10].

6. Numerical Results. We perform numerical experiments to test the performance of the MGR preconditioner on two problems: (1) a weak scaling study for a simple synthetic configuration; and (2) a strong scaling study using a realistic, highly heterogeneous reservoir based on the SPE10 [12] example. Both examples have been designed as community benchmark problems and exhibit tight-coupling between displacement, pressure, and saturation fields. Problem specifications are described in detail in [46] and so are only briefly reported below.

In this study, the simulator is provided by Geocentric , which utilizes the deal.ii Finite Element Library [4] for discretization functionality. It also provides a direct interface with MGR, which is implemented as a separate solver in hypre [17]. All the numerical experiments were run on Quartz , a cluster at the Lawrence Livermore Computing Center with 1344 nodes containing two Intel Xeon E5-2695 18-core processors sharing 128 GiB of memory on each node with Intel Omni-Path interconnects between nodes. We use pure MPI-based parallelism.

For the elastic block A uu , we use one V-cycle of BoomerAMG [24], with an unknown approach for a system of three PDEs, with one level of aggressive coarsening, one sweep of hybrid forward l 1 -Gauss-Seidel [3] for the down cycle and one sweep of hybrid backward l 1 -Gauss-Seidel for the up cycle. The coarsest grid is solved directly with Gaussian elimination. The MGR coarse-solve in (5.17) also uses BoomerAMG with the same smoother configuration, but for a scalar problem and a Hybrid Modified

Fig. 1: Staircase benchmark, showing basic geometry and resulting saturation field within the high-permeability channel at t = 92 days.

<!-- image -->

Table 1: Weak scaling performance for the staircase example.

| Cores   | DoFs       | Iterations                | Iterations             | SetupPhase[s]SolvePhase[s]Iter.IncreaseTimeIncrease   |        |      |      |
|---------|------------|---------------------------|------------------------|-------------------------------------------------------|--------|------|------|
|         |            | Newtonper Timestep (avg.) | GMRESper Newton (avg.) | (avg.)                                                | (avg.) |      |      |
| 2       | 88,307     | 3.3                       | 9.5                    | 0.50                                                  | 0.46   | 1.00 | 1.00 |
| 16      | 680,419    | 4.0                       | 10.8                   | 0.89                                                  | 0.88   | 1.14 | 1.85 |
| 128     | 5,342,147  | 5.0                       | 13.1                   | 1.30                                                  | 1.81   | 1.38 | 3.24 |
| 1024    | 42,338,179 | 6.6                       | 17.3                   | 2.35                                                  | 2.79   | 1.82 | 5.35 |

Independent Set (HMIS) coarsening strategy [14]. For the global smoother, we use one step of processor-local, pointwise ILU(1).

- 6.1. Staircase Benchmark. The configuration of the first test problem is illustrated in Figure 1. A highly-permeable channel winds its way in a 'staircase' fashion through a lower-permeability host rock. A denser, wetting phase is injected through a well at the top corner, leading to a saturation plume driven by gravity and pressure that migrates towards a production well in the lower corner. The whole system is deformable and exhibits significant poromechanical coupling. Visualizations of the resulting pressure and deformation fields have been omitted for brevity. A detailed specification of mesh geometry, material properties, and boundary conditions can be found in [46].

Table 1 shows the results for a weak scaling study using the staircase example. We keep the number of degrees of freedom per core constant at 44k and increase the number of cores from 2 to 1024. The global problem size grows 8 3 times from 88k to 42M. Due to the inherent nonlinearity, we observe an increase in the number of Newton iterations per time step as the mesh is refined. The average number of GMRES iterations per Newton step, however, only experiences a modest growth as desired. Even though we can use a more complex smoother in place of the hybrid l 1 -

Fig. 2: SPE10-based benchmark: The original SPE-10 reservoir is embedded in a larger poromechanical domain to provide realistic mechanical boundary conditions.

<!-- image -->

Table 2: Strong scaling performance for the SPE10-based problem.

| Cores   | DoFs/Core   | Iterations                | Iterations             |        | SetupPhase[s]SolvePhase[s]Overall[s]   |        | Efficiency   |
|---------|-------------|---------------------------|------------------------|--------|----------------------------------------|--------|--------------|
|         |             | Newtonper Timestep (avg.) | GMRESper Newton (avg.) | (avg.) | (avg.)                                 |        |              |
| 36      | 464,738     | 6.5                       | 21.0                   | 15.60  | 44.2                                   | 20,290 | 1.00         |
| 72      | 232,369     | 6.5                       | 21.5                   | 7.29   | 22.7                                   | 10,160 | 1.00         |
| 144     | 116,184     | 6.5                       | 22.5                   | 4.40   | 11.7                                   | 5,470  | 0.93         |
| 288     | 58,092      | 6.5                       | 23.2                   | 2.48   | 6.2                                    | 2,941  | 0.86         |
| 576     | 29,046      | 6.5                       | 24.3                   | 2.58   | 3.2                                    | 1,955  | 0.65         |

Gauss-Seidel solves for the elasticity block and drive down the number of iterations, that will come at the expense of run-time performance. In general, we find that the l 1 -Gauss-Seidel smoother strikes a good balance between iteration counts and run time. Similar to the number of iterations, the total run time, including both the setup and solve phases, also exhibits some growth, but again, the result is quite satisfactory even for large core counts. The increase in the run time can be attributed to communication costs in the MGR setup and solve phases, since the actual number of degrees of freedom per core is fairly small. Overall, however, the MGR framework provides a good platform for scalable performance.

Fig. 3: Effects of the global smoother at different time steps for the hybrid block Gauss-Seidel and processor-local ILU(1).

<!-- image -->

6.2. SPE10-based Benchmark. We also perform a strong scaling study on a more realistic benchmark problem derived from the second model of the SPE10 Comparative Solution Project (Figure 2) [12]. The original SPE10 permeability and porosity fields are now treated as a poromechanical medium. These geostatistically generated fields exhibit both severe heterogeneity and anisotropy. In the current poromechanical benchmark, the reservoir itself is also embedded in a larger domainwith caprock and underburden-to provide more realistic boundary conditions. Water is injected through a central well, while fluids are produced from four wells at the corners of the domain. Mesh, material property, and boundary condition specifications are reported in [46]. Note that the well control conditions differ from the original SPE10 model to avoid well impacts on the linear solver. The treatment of well degreesof-freedom within the linear solver is a critical issue, but is deliberately left out-ofscope for the current contribution. We remark, however, that the MGR approach provides a flexible framework to treat this additional complexity.

The resulting discrete problem has 16.7M degrees-of-freedom. We keep the problem size fixed and divide the work across an increasing number of compute cores. The results are shown in Table 2. Again, we observe only minor growth in the number of GMRES iterations with larger core counts. Similar to the weak scaling case, the reason for this growth is the use a hybrid l 1 -Gauss-Seidel smoother in AMG solves for the elasticity block and the coarse grid. Good overall timing efficiency is also achieved up to 288 cores. For 576 cores, even though we still get good efficiency for the solve phase, there is a noticeable increase in the setup time because the problem size on each core becomes very small, i.e. about 17k total and less than 6k degrees of freedom for the elastic block and the coarse grid, respectively. Consequently, the majority of the time is spent in communication while not much computation is performed. However, the results still indicate that one can use the proposed framework with a large number of processors to efficiently reduce the long simulation time for challenging problems with highly heterogeneous media.

6.3. Effect of global smoother. As we have mentioned earlier, the performance of MGR is dependent on the effectiveness of the solvers for each component of the algorithm. In general, changing the configuration for one component, e.g. smoother choices for the F-relaxation or coarsening strategies for the coarse-grid AMG solve, would result in a different number of GMRES iterations. However, the effect

could also be quite subtle and not manifest itself until the underlying property of the problem changes. For multiphase poromechanics simulations, early times are typically dominated by elliptic effects associated with the pressure and displacement fields, while at late times the hyperbolic effects associated with the saturation field become significant.

Here we explore the effectiveness of different global smoothers on the multiphase flow system as the simulation progresses. The first option uses three sweeps of HBGS, and the second option uses a single sweep of processor-local ILU(1). As one can see from Figure 3a, there is no apparent difference between the two smoothers until about 45 days of injection, when the number of iterations for the HBGS method increases sharply and continues to stay high. In contrast, ILU(1) is less sensitive. Even though the number of iterations also rises slightly around 85 days, it starts to decrease for the last period at the end of the simulation. We also plot the total time of HBGS(3) against ILU(1) in Figure 3b. It is clear that even though ILU(1) takes slightly more time in the beginning (mainly due to higher setup cost), the trade off is worthwhile thanks to its robustness, which leads to a modest reduction in total time for the whole simulation. This observation is confirmed by the widespread use of incomplete factorization smoothers in the reservoir simulation community.

7. Conclusion. In this work, we have presented an algebraic framework based on multigrid reduction for solving the linear system that comes from discretizing and linearizing the conservation equations governing multiphase flow coupled with poromechanics. This framework is flexible and allows us to construct different preconditioners based on different choices for CF-splitting strategies, interpolation and restriction operators, as well as solvers and smoothers. We have also developed a dropping strategy for computing the reduction onto the coarse-grid within the MGR V-cycle that captures the coupling between mechanics and flow and reduces the operator complexity at the same time. This results in an algebraic preconditioner that is robust and scalable for realistic and large-scale simulation of multiphase poromechanics.

Regarding future work, a number of improvements to the MGR framework could be explored. For example, constructing good approximations to the ideal interpolation and restriction operators that have low complexity remains a significant challenge. Also, it is unclear how one can choose an optimal coarse grid that is representative of the fine-grid system and at the same time still amenable to AMG in a multi-level reduction setting. Thus, better strategies for computing the non-Galerkin coarse grid introduced in this work are needed to improve robustness of the framework. Lastly, since MGR is designed to accommodate a wide range of coupled systems, we are looking into extending the approach to solve problems with non-isothermal flow and fractured media.

## REFERENCES

- [1] F. J. Adler, J. H. Gaspar, X. Hu, C. Rodrigo, and L. T. Zikatanov , Robust block preconditioners for biot's model , in Domain Decomposition Methods in Science and Engineering XXIV, P. E. Bjørstad, S. C. Brenner, L. Halpern, H. H. Kim, R. Kornhuber, T. Rahman, and O. B. Widlund, eds., Springer International Publishing, 2018, https://doi.org/10.1007/978-3-319-93873-8, https://doi.org/10.1007/978-3-319-93873-8.
- [2] K. Aziz and A. Settari , Petroleum Reservoir Simulation , Applied Science Publishers, 1979.
- [3] A. H. Baker, R. D. Falgout, T. V. Kolev, and U. M. Yang , Multigrid smoothers for ultraparallel computing , SIAM Journal on Scientific Computing, 33 (2011), pp. 2864-2887, https://doi.org/10.1137/100798806, https://doi.org/10.1137/100798806.

- [4] W. Bangerth, R. Hartmann, and G. Kanschat , deal.II-a general-purpose object-oriented finite element library , ACM Transactions on Mathematical Software, 33 (2007), pp. 24-es, https://doi.org/10.1145/1268776.1268779, https://doi.org/10.1145/1268776.1268779.
- [5] L. Bergamaschi, M. Ferronato, and G. Gambolati , Novel preconditioners for the iterative solution to FE-discretized coupled consolidation equations , Computer Methods in Applied Mechanics and Engineering, 196 (2007), pp. 2647-2656, https://doi.org/10.1016/j.cma. 2007.01.013, https://doi.org/10.1016/j.cma.2007.01.013.
- [6] L. Bergamaschi and ´ A. Mart´ ınez , RMCP: Relaxed mixed constraint preconditioners for saddle point linear systems arising in geomechanics , Computer Methods in Applied Mechanics and Engineering, 221-222 (2012), pp. 54-62, https://doi.org/10.1016/j.cma.2012.02.004, https://doi.org/10.1016/j.cma.2012.02.004.
- [7] Q. M. Bui, H. C. Elman, and J. D. Moulton , Algebraic multigrid preconditioners for multiphase flow in porous media , SIAM Journal on Scientific Computing, 39 (2017), pp. S662-S680, https://doi.org/10.1137/16M1082652, http://dx.doi.org/10.1137/ 16M1082652, https://arxiv.org/abs/http://dx.doi.org/10.1137/16M1082652.
- [8] Q. M. Bui, L. Wang, and D. Osei-Kuffuor , Algebraic multigrid preconditioners for twophase flow in porous media with phase transitions , Advances in Water Resources, 114 (2018), pp. 19-28, https://doi.org/10.1016/j.advwatres.2018.01.027.
- [9] H. Cao, H. A. Tchelepi, J. H. Wallis, and H. E. Yardumian , Parallel scalable unstructured CPR-type linear solver for reservoir simulation , in SPE Annual Technical Conference and Exhibition, Society of Petroleum Engineers (SPE), 2005, https://doi.org/10.2118/ 96809-ms, http://dx.doi.org/10.2118/96809-MS.
- [10] E. Chow and A. Patel , Fine-grained parallel incomplete LU factorization , SIAM Journal on Scientific Computing, 37 (2015), pp. C169-C193, https://doi.org/10.1137/140968896, https://doi.org/10.1137/140968896.
- [11] E. Chow and Y. Saad , Approximate inverse preconditioners via sparse-sparse iterations , SIAM Journal on Scientific Computing, 19 (1998), pp. 995-1023, https://doi.org/10.1137/ s1064827594270415, https://doi.org/10.1137/s1064827594270415.
- [12] M. A. Christie and M. J. Blunt , Tenth SPE comparative solution project: A comparison of upscaling techniques , in SPE Reservoir Simulation Symposium, Society of Petroleum Engineers (SPE), 2001, https://doi.org/10.2118/66599-ms, http://dx.doi.org/ 10.2118/66599-MS.
- [13] O. Coussy , Poromechanics , Wiley, Chichester, UK, 2004.
- [14] H. De Sterck, U. M. Yang, and J. J. Heys , Reducing complexity in parallel algebraic multigrid preconditioners , SIAM Journal on Matrix Analysis and Applications, 27 (2006), pp. 1019-1039, https://doi.org/10.1137/040615729, https://doi.org/10.1137/040615729.
- [15] R. D. Falgout, S. Friedhoff, T. V. Kolev, S. P. MacLachlan, and J. B. Schroder , Parallel time integration with multigrid , SIAM Journal on Scientific Computing, 36 (2014), pp. C635-C661, https://doi.org/10.1137/130944230, http://dx.doi.org/10.1137/ 130944230, https://arxiv.org/abs/http://dx.doi.org/10.1137/130944230.
- [16] R. D. Falgout, T. A. Manteuffel, B. O'Neill, and J. B. Schroder , Multigrid reduction in time for nonlinear parabolic problems , tech. report, Lawrence Livermore National Laboratory, jan 2016, https://doi.org/10.2172/1236132, https://doi.org/10.2172/1236132.
- [17] R. D. Falgout and U. Yang , HYPRE: a library of high performance preconditioners , in Preconditioners, Lecture Notes in Computer Science, 2002, pp. 632-641.
- [18] M. Ferronato, C. Janna, and G. Pini , A generalized block FSAI preconditioner for nonsymmetric linear systems , Journal of Computational and Applied Mathematics, 256 (2014), pp. 230 - 241, https://doi.org/10.1016/j.cam.2013.07.049, http://www.sciencedirect.com/ science/article/pii/S0377042713003944.
- [19] T. A. Garipov, M. Karimi-Fard, and H. A. Tchelepi , Discrete fracture model for coupled flow and geomechanics , Comput. Geosci., 20 (2016), pp. 149-160, https://doi.org/10.1007/ s10596-015-9554-z.
- [20] S. Gries, K. St¨ uben, G. L. Brown, D. Chen, and D. A. Collins , Preconditioning for efficiently applying algebraic multigrid in fully implicit reservoir simulations , SPE Journal, 19 (2014), pp. 726-736, https://doi.org/10.2118/163608-pa, https://doi.org/10.2118/ 163608-pa.
- [21] M. J. Grote and T. Huckle , Parallel preconditioning with sparse approximate inverses , SIAM Journal on Scientific Computing, 18 (1997), pp. 838-853, https://doi.org/10.1137/ s1064827594276552, https://doi.org/10.1137/s1064827594276552.
- [22] J. B. Haga, H. Osnes, and H. P. Langtangen , On the causes of pressure oscillations in lowpermeable and low-compressible porous media , Int. J. Numer. Anal. Methods Geomech., 36 (2012), pp. 1507-1522, https://doi.org/10.1002/nag.1062.

- [23] J. B. Haga, H. Osnes, and H. P. Langtangen , A parallel block preconditioner for large-scale poroelasticity with highly heterogeneous material parameters , Computational Geosciences, 16 (2012), pp. 723-734, https://doi.org/10.1007/s10596-012-9284-4, https://doi.org/10. 1007/s10596-012-9284-4.
- [24] V. E. Henson and U. M. Yang , BoomerAMG: a parallel algebraic multigrid solver and preconditioner , Applied Numerical Mathematics, 41 (2000), pp. 155-177.
- [25] J. Kim, H. A. Tchelepi, and R. Juanes , Stability, accuracy, and efficiency of sequential methods for coupled flow and geomechanics , SPE Journal, 16 (2011), pp. 249-262, https: //doi.org/10.2118/119084-pa, https://doi.org/10.2118/119084-pa.
- [26] J. Kim, H. A. Tchelepi, and R. Juanes , Rigorous Coupling of Geomechanics and Multiphase Flow with Strong Capillarity , SPE J., 18 (2013), pp. 1123-1139, https://doi.org/10.2118/ 141268-PA.
- [27] S. Lacroix, Y. Vassilevski, J. Wheeler, and M. F. Wheeler , Iterative solution methods for modeling multiphase flow in porous media fully implicitly , SIAM Journal on Scientific Computing, 25 (2003), pp. 905-926, https://doi.org/10.1137/s106482750240443x, http:// dx.doi.org/10.1137/S106482750240443X.
- [28] J. J. Lee, K.-A. Mardal, and R. Winther , Parameter-robust discretization and preconditioning of biot's consolidation model , SIAM Journal on Scientific Computing, 39 (2017), pp. A1-A24, https://doi.org/10.1137/15m1029473, https://doi.org/10.1137/15m1029473.
- [29] R. W. Lewis and B. A. Schrefler , The Finite Element Method in the Static and Dynamic Deformation and Consolidation of Porous Media , Wiley, Chichester, UK, 2nd ed., 1998.
- [30] H. Liu, K. Wang, and Z. Chen , A family of constrained pressure residual preconditioners for parallel reservoir simulations , Numerical Linear Algebra with Applications, 23 (2015), pp. 120-146, https://doi.org/10.1002/nla.2017, https://doi.org/10.1002/nla.2017.
- [31] A. Mikeli´ c and M. F. Wheeler , Convergence of iterative coupling for coupled flow and geomechanics , Computational Geosciences, 17 (2012), pp. 455-461, https://doi.org/10. 1007/s10596-012-9318-y, https://doi.org/10.1007/s10596-012-9318-y.
- [32] J. H. Prevost , Two-way coupling in reservoir-geomechanical models: vertex-centered Galerkin geomechanical model cell-centered and vertex-centered finite volume reservoir models , Int. J. Numer. Meth. Eng., 98 (2014), pp. 612-624, https://doi.org/10.1002/nme.4657.
- [33] M. Ries and U. Trottenberg , MGR-Ein blitzschneller elliptischer L¨ oser , Preprint 277SBF 72, Universit¨ at Bonn, (1979).
- [34] M. Ries, U. Trottenberg, and G. Winter , A note on MGR methods , Linear Algebra and its Applications, 49 (1983), pp. 1 - 26, https://doi.org/10.1016/0024-3795(83)90091-5, http://www.sciencedirect.com/science/article/pii/0024379583900915.
- [35] Y. Saad and M. H. Schultz , GMRES: A generalized minimal residual algorithm for solving nonsymmetric linear systems , SIAM Journal on Scientific and Statistical Computing, 7 (1986), pp. 856-869, https://doi.org/10.1137/0907058, http://dx.doi.org/10.1137/ 0907058.
- [36] R. Scheichl, R. Masson, and J. Wendebourg , Decoupling and block preconditioning for sedimentary basin simulations , Computational Geosciences, 7 (2003), pp. 295-318, https://doi.org/10.1023/b:comg.0000005244.61636.4e, https://doi.org/10. 1023/b:comg.0000005244.61636.4e.
- [37] A. Settari and F. Mourits , A coupled reservoir and geomechanical simulation system , SPE Journal, 3 (1998), pp. 219-226, https://doi.org/10.2118/50939-pa, https://doi.org/ 10.2118/50939-pa.
- [38] R. R. Settgast, P. Fu, S. D. C. Walsh, J. A. White, C. Annavarapu, and F. J. Ryerson , A fully coupled method for massively parallel simulation of hydraulically driven fractures in 3dimensions , International Journal for Numerical and Analytical Methods in Geomechanics, 41 (2017), pp. 627-653, https://doi.org/10.1002/nag.2557.
- [39] K. St¨ uben , A review of algebraic multigrid , Journal of Computational and Applied Mathematics, 128 (2001), pp. 281 - 309, https://doi.org/10.1016/S0377-0427(00)00516-1, http: //www.sciencedirect.com/science/article/pii/S0377042700005161.
- [40] K. St¨ uben, T. Clees, H. Klie, B. Lu, and M. F. Wheeler , Algebraic multigrid methods (AMG) for the efficient solution of fully implicit formulations in reservoir simulation , in SPE Reservoir Simulation Symposium, Society of Petroleum Engineers (SPE), 2007, https://doi.org/10.2118/105832-ms, http://dx.doi.org/10.2118/105832-MS.
- [41] U. Trottenberg, C. W. Oosterlee, and A. Schuller , Multigrid , Academic Press, Inc., Orlando, FL, USA, 2001.
- [42] J. R. Wallis , Incomplete gaussian elimination as a preconditioning for generalized conjugate gradient acceleration , in SPE Reservoir Simulation Symposium, Society of Petroleum Engineers, 1983, https://doi.org/10.2118/12265-ms, https://doi.org/10.2118/12265-ms.

- [43] J. R. Wallis, R. P. Kendall, and L. E. Little , Constrained residual acceleration of conjugate residual methods , in SPE Reservoir Simulation Symposium, Society of Petroleum Engineers (SPE), 1985.
- [44] L. Wang, D. Osei-Kuffuor, R. D. Falgout, I. D. Mishev, and J. Li , Multigrid reduction for coupled flow problems with application to reservoir simulation , in SPE Reservoir Simulation Conference, Society of Petroleum Engineers (SPE), SPE-182723-MS, 2017.
- [45] J. A. White and R. I. Borja , Block-preconditioned Newton-Krylov solvers for fully coupled flow and geomechanics , Computational Geosciences, 15 (2011), pp. 647-659, https://doi. org/10.1007/s10596-011-9233-7, http://dx.doi.org/10.1007/s10596-011-9233-7.
- [46] J. A. White, N. Castelletto, S. Klevtsov, Q. M. Bui, D. Osei-Kuffuor, and H. A. Tchelepi , A Two-Stage Preconditioner for Multiphase Poromechanics in Reservoir Simulation , arXiv e-prints, (2018), arXiv:1812.05540, p. arXiv:1812.05540, https://arxiv.org/ abs/1812.05540.
- [47] J. A. White, N. Castelletto, and H. A. Tchelepi , Block-partitioned solvers for coupled poromechanics: A unified framework , Computer Methods in Applied Mechanics and Engineering, 303 (2016), pp. 55-74, https://doi.org/10.1016/j.cma.2016.01.008, https: //doi.org/10.1016/j.cma.2016.01.008.
- [48] Y. Zhou, Y. J., and H. A. Tchelepi , A scalable multistage linear solver for reservoir models with multisegment wells , Computational Geosciences, 17 (2012), pp. 197-216, https://doi. org/10.1007/s10596-012-9324-0, https://doi.org/10.1007/s10596-012-9324-0.