## The physics of Superconducting Quantum Interference Devices (SQUIDs) Joey Lambert December 8, 2008

Josephson  junctions  are  interesting  devices  that  provide  a  great  deal  of  physics  to research, both experimental and theoretical.  The device was first proposed by Brian Josephson in  short  concise  paper  in  1962  [1],  which  predicts  a  resistance-less  supercurrent  that  passes through  the  very  thin  insulating  layer  in  between  two  macroscopic  size  superconductors. Depending on the circuit configuration and biasing methods, many useful devices can be made for  use  in  research  and  industry,  the  most  widely  used  being  the  Superconducting  Quantum Interference Device (SQUID).  In this report, I present the underlying physics of these devices.

## What is a SQUID?

Making a SQUID is fairly simple: it is a superconducting ring interrupted by one or more Josephson junctions.   An example is shown in figure 1.

<!-- image -->

Based on this description, we can foresee some of the physics governing this device.  First, we have the Josephson effect.  Due to the ring geometry and the possibility of multiple junctions, we  should  encounter  interference  effects.    Second,  there  is  a  loop  containing  electric supercurrent which will result in effects due magnetic flux.   We will start simple and look at the flux due to currents in a superconducting ring.  We will follow this with the basic concepts of a Josephson junction alone, and then add them to the superconducting ring.

## Magnetic flux in a superconducting ring

To start we need some equations describing the superconducting state.  As shown by the BCS theory of superconductivity, the electrons in the superconducting state form correlated pairs of electrons with opposite spin and momentum called cooper pairs [2].  The coherence length of these pairs is sufficiently large that they overlap and the relative phase factors of the wavefuntions of each pair match. This results in a coherent  phase  throughout the superconductor.  We will then assume, a la Feynman, that we can take the ensemble average of the cooper pair wavefunctions and desecibe all cooper pairs with a macroscopic wavefunction of the form [3][4]

<!-- formula-not-decoded -->

Where 𝑲 is the net wave vector of all cooper pairs and Ψ 𝒓 is the ensemble-average function when 𝐾 = 0 .    The  quantity 𝑲∙ 𝒓 is  the  position  dependent  phase  of  our  macroscopic wavefunction, so we will write this as 𝑲∙ 𝒓 = 𝜃 𝒓 .  We can normalize this wavefuction so that

Ψ ∗ Ψ𝑑𝐫 V = 𝑁 , the total number of electron pairs in the superconductor.  This means we can write our wavefunction as

<!-- formula-not-decoded -->

Where 𝑛 𝒓 is  the  local  cooper  pair  density.    From  here  on  we  will  take  the  density  to  be spatially invariant, which is approximately true in weak fields.

The classical canonical momentum of a particle of charge q and mass m in a magnetic field of vector potentional A is 𝒑 = 𝑚𝒗 + 𝑞𝑨 .  For a pair of mass m* and charge e*, we have

<!-- formula-not-decoded -->

We can find the momentum density by multiplying equation (3) by the local density 𝑛 𝒓  = 𝑛 . Quantum  mechanically, 𝑛𝒑 is  the  expectation  value  of  the  canonical-momentum  operator -𝑖ℏ𝛁 , so we have

<!-- formula-not-decoded -->

The pair current density is given by 𝑱 = 𝑛𝑒 ∗ 𝒗 , so we can write momentum as

<!-- formula-not-decoded -->

where Λ = 𝑚 ∗ 𝑛𝑒 ∗2 [3] .

Now we can look at a superconducting ring.  We will consider a closed contour within a superconductor that surrounds a hole.  Then integrate equation (5) around this contour:

<!-- formula-not-decoded -->

The phase must be coherent around the contour, so the right-hand-side integral must come in integer multiples of 2𝜋 .  If  the  contour  is  chosen  deep  inside  the  superconductor, 𝑱 ≈ 0 ,  and using Stokes' theorem, the left-hand-side integral becomes

<!-- formula-not-decoded -->

Where Φs is the flux penetrating our loop.  The integral on the left we found to be quantized, so the flux must be quantized as

<!-- formula-not-decoded -->

Since each pair consists of two electron charges, we can define the flux quantum as Φ0 = h 2e [3].

The quantization of magnetic flux was actually first discovered experimentally.  The experiment was  done  in  1961  by  two  groups:  Doll  and  Näbauer  in  Munich  and  Deaver  and  Fairbank  in Stanford [6] In summary, because the phase in a superconductor is coherent, the flux in a ring must be quantized in units of the flux quantum.

## The Josephson Junction

We  model  a  Josephson  junction as a thin insulator  sandwiched  between  two

Figure 2 - Simple schematic of a Josephson Junction.

<!-- image -->

superconductors, as shown in figure 2.

Under much skepticism, Brian Josephson was able to predict in a short paper in 1962 that under zero applied voltage cooper pairs between the two superconductors should tunnel through the insulation barrier resulting in a resistance-less supercurrent [1].  His paper is very often cited, but his derivations are very rarely used possibly in part because it has errors to be corrected and gaps to be filled.   Instead the Feynman approach has been used widely [4], as we will here.

We  can  represent  each  superconductor  of  the  junction  with  their  own  macroscopic wavefunctions, equation (2).  One way to interpret the Josephson effect in superconductors is these two wavefunctions, which describe cooper pairs and not individual electrons, penetrate into the insulator.  If the insulator is sufficiently thin, these wavefunctions will have an overlap which  means  there  is  a  probability  that  cooper  pairs  will  tunnel  through  the  barrier. Representing this wavefunction overlap as a coupling constant, one can derive this cooper pair current  [4].    The  result  is  the  current  depends  on  the  difference  in  the  phases  of  the  two superconductors at the insulator boundary, which is written as

<!-- formula-not-decoded -->

In  the  presence  of  a  magnetic  field  the  current  will  be  altered,  so  the  phase  is  not  gauge invariant.  In terms of the vector potential 𝑨 , the gauge invariant phase difference is [5]

<!-- formula-not-decoded -->

where the integration is taken across the insulating layer.  If we replace the phase difference in equation (9) with equation (10), we get the true Josephson current relation in a magnetic field.

## The dc-SQUID

Now we will put two Josephson junction in a superconducting loop, such as in figure 1, which is called a dc-SQUID.    To compute the line integral of the vector potential around the loop to calculate the magnetic flux, we have to separate the integral for the superconducting electrodes and the Josephson junctions, which will be referred as links [5].  If the electrodes are thicker  than  the  London  penetration  depth,  then  we  can  choose  a  contour  deep  inside  the electrodes where the supercurrent velocity, 𝒗 ,  introduced in equation (3), is zero.  Therefore, from  equation  (5),  the  vector  potential  along  the  contour  inside  the  electrodes  is 𝑨 = Φ0/2π 𝛁𝜑 .  The flux looping the dc-SQUID is [5],

<!-- formula-not-decoded -->

The phase around the loop must be single valued, so the integral in the first term in the right side of equation (11) plus the phase differences across the links must be an integer multiple of 2𝜋 .    Combining  equation  (11)  with  equation  (10)  for  both  links,  difference  in  the  gaugeinvariant phase differences is [5]

<!-- formula-not-decoded -->

For  a  single  Josephson  junction,  the  maximum  current  is  when  the  gauge-invariant  phase difference is 𝛾 = 𝜋/2 .    When two are coupled in a loop, there is an interference effect which restricts  the  possible  values  for  the  phases.    Unless  the  total  magnetic  flux  is  an  integral multiple of the flux quantum, the max current passing through the SQUID must be less than the sum  of  the  critical  currents  of  each  of  the  junctions.    If  each  junction  has  identical  crictical currents, 𝐼 𝑐 , it can be shown that the maximum supercurrent is [5]

<!-- formula-not-decoded -->

The plot of the max current against the flux looks an awful lot like the interference pattern from Young's Double slit experiment.  So SQUIDs exhibit the analogous superconducting experiment. This derivation treated the junctions as point contacts, so variation along the boundary was not considered.    If  we  extend  the  size  of  a  rectangular  junction,  we  find  that  the  current  varies sinusiodally with position.   The maximum current as a function of the flux becomes [5]

<!-- formula-not-decoded -->

This  is  the  Fraunhofer  diffraction  pattern,  just  like  when  light  passes  through  a  narrow rectangular slit.  If the junction is circular, we get an airy diffraction pattern [5].

Other typers of SQUID devices can be made by using different numbers of Josephson junctions.    A  superconducting  loop  with  one  Junction  is  called  an  rf-SQUID.    These  are  fairly similar in function to dc-SQUIDs, but dc-SQUIDS are used more often because they were the first to be built [3].  BY using three junctions, one can make a flux qubit or  persistent current qubit.  These qubits use the clockwise and counterclockwise directed currents as basis states which can create superposition states.

## Applications of the SQUIDs

SQUIDs  have  found  their  way  into  many  facets  of  research  and  industry.    They  are widely used at highly sensitive magnetometers.  Looking at equations (13) and (14), we can see that we can measure changes in current due to changes in flux on the order of a flux quantum, which is Φ0 = 2.07 × 10 -7  G ∙ cm 2 ; compare this to the earth's magnetic field which ~1 𝐺 .  In current research, they are used to read out the states of superconducting qubits. With a SQUID located in close proximity to either a phase or flux qubit. The flux induced by changing currents can be detected.  They are also used to measure the magnetic susceptibility of materials and measure faint signals of biological systems suchas the human hear t and brain [3].

References [1] B. D. Josephson, Physics Letters 1 , 251 (1962). [2] J. Bardeen, L. N. Cooper, and J. R. Schrieffer, Phys. Rev. 108 ,1175 (1957). [3] T. Van Duzer and C. W. Turner, Principles of Superconductive Devices and Circuits, 2 nd Ed. (Prentice Hall PTR, Upper Saddle River NJ, 1999). [4]  R.  P.  Feynman,  R.  B.  Leighton,  M.  Sands, The  Feynman  Lectures  on  Physics (AddisonWesley, Reading MA, 1965). [5]  M.  Tinkham, Introduction  to  Superconductivity (Dover  Publications,  Inc.,  Mineola  NY, 2004). [6] W. Buckel and R. Kleiner, Superconductivity: Fundamentals and Applications (Wiley-VCH Verlag GmbH &amp; Co. KGaA, Wienheim, 2004).