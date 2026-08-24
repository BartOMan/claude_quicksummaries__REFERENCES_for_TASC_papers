<!-- image -->

## A Prospective Approach to Energy Saving (Reversible) Computing

Vasili K. Semenov,

Department of Physics and Astronomy Stony Brook University (SBU)

D. V. Averin, Yu. A. Polyakov,  G. Danilov, J. Ren (all SBU)

and Jaw-Shen Tsai (NEC, Japan)

This work was supported in part by the NSF (grant EIA-0121428), by JST/CREST and by the National Security Agency (NSA)

under ARO contract number W911NF-06-1-217.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

1

•

- Highlights
- Key theoretical discoveries in the area of Reversible Computing (RC) have been made in sixties and seventies by Landauer and Bennett. We closely
- followed their theoretical recommendations. · Superconducting Josephson junction technology is the optimal choice for RC because allows to eliminate static energy losses. · Any prospective computing technology must satisfy a long list of requirements. Earlier suggestions for RC superconducting gates satisfied only a few of them.
- Our recent solution based on nSQUID gates is quite close to the requirement list. As a result, we experimentally approached to the thermodynamic
- threshold. · The most significant step was the elimination of multi-phase AC biasing

schemes that are quite common for RC.

The next important step could be a matching RC circuitry with a more conventional computing technology.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

2

Competition for a Lower Energy Dissipation

(It has been discovered long ago that logic reversibility and thermodynamics set limitations for energy dissipation)

Only erasure of the information costs energy [R. Landauer]. This conclusion leads to  the concept of logically reversible computation

which avoids erasure of the information [C. Bennett].

Our goal was to experimentally approach and even cross

- thermodynamic threshold for energy dissipation per logic operation: k T ln2 (~4 ⋅ 10 -23 J at T=4.2 K)
- R. Landauer, 'Irreversibility and heat generation in the computing process,' B

IBM J. of Res. and Devel., vol. 3, pp. 183-191, 1961.

C. Bennett, 'Logical reversibility of computation', vol. 17, p. 525, 1973

Annapolis, MD, March 15, 2012

IBM J. of Res. and Devel.

Vasili.Semenov@StonyBrook.edu

,

3

Impacts of Landauer Discoveries

The main paper

Title: Irreversibility and heat generation in the computing process

Author:

Landauer R

Source: IBM JOURNAL OF RESEARCH AND DEVELOPMENT

Volume: 5 Issue: 3 Pages: 183-191 Published: 1961 Times Cited: 687 With the so high number of citation it is possible to find papers of any kind, in particular those that give new proofs of Landauer principles and paper that explain why the principles are incorrect. However, about 2/3 of papers deal with reversible algorithms for Quantum Computing. This is because

almost any Quantum Computers could be also named as a Reversible Computer operating in a quantum mode. This is a quite strong observation because it immediately leads to a natural question: Why QC researchers bypass the more simple classical mode of operation? It is so usual to start any big project from execution simple tasks.

Probably we are the only group that tried to design and experimentally

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu demonstrate Classical Reversible Computing.

4

## Unprecedented Accuracy 1of

Unprecedented Accuracy of R. Landauer Forecast In 1982 Landauer collected available data that are reasonably fitted by a simple exponential 10 106 10° 10 10 10°

approximation. The fitting line hits kT threshold in 2014. We are still

in time to meet this forecast.

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

5

## Another Good Mlustration For Reversible Computing (Landauer 1991)

Another Good Illustration For Reversible Computing

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

6

## rconducting Circuits

First Potentially Reversible Superconducting Circuits

- -No energy dissipation in superconducting state;
- -Very convenient and accurate energy potential: E( ϕ )=I ( φ )· Φ ⋅ cos( ϕ );

-

C

cl

0

Developed technology: CAD tools, fabrication, measurement

.

consumption in computation,'

<!-- image -->

Int. J. Theor. Phys.,

Annapolis, MD, March 15, 2012

vol. 21, p. 311, 1982.

Vasili.Semenov@StonyBrook.edu

7

also Known as Quantum Flux Parame QUID, Flux and Ground-state Qubit

Parametric Quantron

E.Goto and others, 1986

also Known as Quantum Flux Parametron, Double SQUID, IN-SQUID, Flux and Ground-state Qubit

'Parametric Quantron', K.K. Likharev, and others 1985.

<!-- image -->

""IN-SQUID'', J. Clarke and others, 2

<!-- image -->

<!-- image -->

"Ground State Qubit'', M. W. Johnson, and others, 2011.

<!-- image -->

We mentioned only most common names given to almost identical devices that could be described as a superconducting inductance shortened by an externally controlled two-junction SQUID.

Vasili.Semenov@StonyBrook.edu

8

Annapolis, MD, March 15, 2012

## Externally JID Properti

<!-- image -->

⎛

-

ϕ

ϕ

ϕ

(

)

(

2

⎜ ⎝ l The effective critical current and therefore the energy profile of the device is controlled by external current. This (AC) current delivers and takes energy to and from the cell. In other words, it serves as a bias current. At the same time it

+

⎜

-

ϕ

Σ

+

serves as a clock signal. In general, this is not good because several clock signal could be required to control complex logic circuits.

As a example, the circuits developed in Goto

Annapolis, MD, March 15, 2012

group use 3-phase clocking scheme.

Vasili.Semenov@StonyBrook.edu

⎟

⎞

⎟

)

2

e

<!-- image -->

9

c

-

ϕ

ϕ

2cos cos

+

## Double SQUI

<!-- formula-not-decoded -->

U

(

Φ

+

ϕ

/ 2

)

π

ϕ

0

-

I

,

C

<!-- image -->

<!-- image -->

<!-- formula-not-decoded -->

π

=

φ

±=(

φ

1±

φ

2)/2

Annapolis, MD, March 15, 2012

⎛

⎜

⎜

⎝

(

+

ϕ

/ 2

λ

+ -+ -⎟ ⎟ ⎠ ⎞ ⎜ ⎜ ⎝ ⎛ -+ + -= ϕ ϕ λ ϕ ϕ λ ϕ ϕ cos 2cos ) ( / 2) / 2 ( ) ( 2 2 e c L

In particular, they are described by similar equations. Advantages of one or another geometry partly depend on personal preferences.

This is because until now we assume that the compared devices are weakly coupled with  other devices. In plain words, standalone double and nSQUIDs are quite

similar.

<!-- formula-not-decoded -->

-

+

(

ϕ

L

Vasili.Semenov@StonyBrook.edu

)

2

(

ϕ

-

-

ϕ

)

2

⎞

⎟

ϕ

ϕ

<!-- image -->

-

cos

+

10

## The First

<!-- image -->

J 1 J 2 The circuit fabricated at HYPRES, Inc. Target Ic = 0.015 mA.

Dark areas are the ground plane holes. The left and right holes are used for magnetic coupling with other nSQUIDs

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

11

## Schematics and I alvanic Cou pling

Schematics and Layouts of nSQUIDs (type c) with

Galvanic Coupling

0.01 mA

<!-- image -->

<!-- image -->

Year 2004

<!-- image -->

<!-- image -->

Year 2007-08

Vasili.Semenov@StonyBrook.edu

Annapolis, MD, March 15, 2012

12

## nSQUIDs as Building Blocks for L:

<!-- image -->

<!-- image -->

<!-- image -->

Annapolis, MD, March 15, 2012

energy profile from mono-stable at φ cl =0 to bi-stable at φ cl= π Fluxons or Josephson vortices can freely move along long Josephson junctions with arbitrary Fluxons or Josephson along long Josephson speed V that depends

speed

V

that depends only on initial and boundary conditions. (Properties of long JJs are discussed by A. Ustinov.) A long Josephson junction could be made of nSQUIDs. The SQUIDs located near the center of a moving or resting vortex have

bistable energy profile and they should randomly 'fall' into one of two energy

minimums.

Vasili.Semenov@StonyBrook.edu

13

## String of nSQUID is sone ofthe

String of nSQUID is one of the Simplest Digital Circuits Let us magnetically couple of neighbor nSQUIDs. Such mutual biasing should force all nSQUIDs belonging to one Josephson vortex to select the same energy minimum.

<!-- image -->

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

14

## nSQUIDEnergy ProfilesatDifferent t (increasing) Couplings

nSQUID Energy Profiles at Different (increasing) Couplings Error rates and error correction are among the first technical question to any new technology. Any bi-stable (especially symmetric) potential is naturally vulnerable for spontaneous state change. However a relatively strong magnetic bias created by neighbor devices is able to 'bend' the bi-stable potential to a mono-stable one. Error rates and error correction are among the first technical

<!-- image -->

<!-- image -->

The only lost group of people are theoreticians. This is because there is no chance to analytically analyze any circuits built of many strongly coupled nSQUIDs. Fortunately

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu numerical simulation are able to close this technical problem.

15

## a Linear nSQUD Array nerical simulations)

Dynamics of a Linear nSQUD Array

(numerical simulations)

There is a strong overlapping of bi-stable states of adjacent cells. At the selected 8-phase timing all cells are organized into bi-stable domains consisting of 3 to 4 cells

and isolated by 5 to 4

mono-stable cells.

Pictures  illustrate  the  evolution  of  differential  phase  with  time.  The  upper  plot shows  that  domains  occupy  about  4  cells  and  move  along  the  array

with  a constant speed (strictly proportional to the applied DC voltage). The lower plot

shows evolutions of differential phases in 4 different nSQUIDs.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

<!-- image -->

16

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

17

## Comparison of Reversible and IrreversiblenSQUiD Circuits

<!-- image -->

Reversible XOR circuit (above) is larger than its irreversible counterpart (on the right). Each of four sketches corresponds different sets of input data. However, the reversible solution will be correct even at fluctuating direction of data propagation. Orange and blur arrows show propagation of logic 'ones' and

'zeros'. Both gates are suggested of Sergey Rylov master and PhD project. (Currently S. Rylov is with

IBM Yorktown Heights.)

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

<!-- image -->

18

## What Could be Made of Simple nSQ

What Could be Made of Simple nSQUID Strings? The shown circuit is two shift registers that share the common clock line. Two vortices are injected into the clock line. Vortices circulate along the line with the speed that completely defined by an external voltage source. The circuit has been fabricated at HYPRES, Data Out 工 工 Circulating Clock Vortices Vcl I 工 工 工 Data In

Inc. Direct measurements showed the specific energy

dissipation about 3

k

B

T

per

8 nSQUID shift register!

Vasili.Semenov@StonyBrook.edu

19

<!-- image -->

Annapolis, MD, March 15, 2012

## Measurements of Energy Dissipation

Due to DC biasing it is possible to reduce energy

measurements to much more simple current measurements

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

I E ⋅ =Φ 0

Jie Ren will give more details about design and measurement procedures.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

=

(1/

Φ

0

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

At

Temp

=4.2 K

I

th

=0.02

μ

)

⋅

V

20

A

Measurement of the Energy Dissipation

## Digitization of analog input magnetic flux and transfer it on about 2 mm

distance, where the digitized signal is measured by a dc SQUID.

Legends show clock frequencies in GHz.

Measurement of the energy dissipation (in fact, dc current flowing

<!-- image -->

via the circuit.): Minimal current is around 2 times of the thermodynamic

Vasili.Semenov@StonyBrook.edu threshold value(0.04

μ

A).

21

<!-- image -->

2 vortices in the clock loop. Frequency

Annapolis, MD, March 15, 2012

range 0.05 GHz to 7.1 GHz

## Measurement Current II. as

Measurement of Bias Current II.

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

22

## Timing B lockScmeile

Architecture and System Issues:

Timing Belt Clock Scheme

<!-- image -->

Two functionally similar 'timing belts'. One is composed of long

Josephson  junctions  and  nSQUID strings.  (both  are  shown  as  a belt used in cars.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

23

## Experimental Made of One Long Jo

Experimental Investigation of Time Belt Made of One Long Josephson Junction with 77 Junctions Shown IV curves correspond to 3 different numbers of vortices in the belt. At 11 injected vertices one vortex occupies 7 6 5

junctions; at 10 and 9 injected vertices one

<!-- image -->

vortex occupies accordingly about 7.7 and 8.6 junctions. In nSQUID strings the vortices serve as multi-phase clocking devices. All vortices are identical and we may hope that they will be able to provide ideally accurate timing sequences. Moreover, simple numerical analysis showed that circuits with fractional (not integer) number of junctions or nSQUIDs per vortex dissipate dramatically lower power. It would be impossible to implement such sophisticated explicit clocking schemes. Ultimate simplicity and accuracy of the timing belt solution is probably the most fundamental advantage of our approach. Closed long Josephson junction is a well investigated device but it was important for us to check that we are not affected neither design nor fabrication errors. A.

Ustinov provided us educational support, while J. Ren designed and measured the

Annapolis, MD, March 15, 2012

circuit.

Vasili.Semenov@StonyBrook.edu

24

## Timing Belt Serving Reversible XOR Gate Composed of Majority, OR RandAND gates

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

25

## lmportant Primitives

## longJJ nSQUID Interface

## onal SQUID readout

Important nSQUID Primitives

Optional SQUID readout

<!-- image -->

<!-- image -->

<!-- image -->

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

26

## sibleErasure of Data Copying and reve

Copying and reversible Erasure of Data

<!-- image -->

## Possible implementation

<!-- image -->

Explanations taken from an old

Landauer paper

===

Annapolis, MD, March 15, 2012

Î

<!-- image -->

Vasili.Semenov@StonyBrook.edu

27

## ProspectivenSQUID with π Junction as a Basis for Lumped Reversible Circuitry

<!-- image -->

nSQUID current returns to the ground via other nSQUIDs. It means that nSQUID devices are inherently distributed. There is at leat one option to make lumped nSQUID circuits. It is known that π -junction is similar to conventional Josephson junctions but it generates current with opposite direction. nSQUID composed of conventional and π junctions would have similar a similar dependence of the energy profile on the clock phase but it

will generate much lower current. This is because most of 'conventional'

Annapolis, MD, March 15, 2012

current is compensated by

π

Vasili.Semenov@StonyBrook.edu current.

28

## General Structure of a Composite Reversible(SFL)and eRSFQDigital Circuitr

<!-- image -->

Currently reversible circuits look quite exotic. We suggest that the first reversible circuits  should be delivered with the 'mandatory' RSFQ or

eRSFQ interface. As a result, reversible components will be invisible for high-

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu level engineering and architectural errorts.

29

## fnSQUID circuitry Synchroniz

Synchronization of nSQUID circuitry

<!-- image -->

In fact, we need only a low-pass filter to smooth SFQ pulses. Numerical

simulations are made by J. Ren.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

<!-- image -->

30

## RSFQ Read Out of nSQUIDData

<!-- image -->

Details for clocked or digital SQUID (lower part in the sketch) could be

50, 2003

Vasili.Semenov@StonyBrook.edu

Annapolis, MD, March 15, 2012

31

- Conclusion
- It looks that we are able to provide experimental support for the
- theory of reversible computing developed by R. Landauer and C. Bennett. · Experimentation with reversible circuits could bring several benefits. · The technology could be practical if, indeed, the energy dissipation will be a really critical issue. Two evident examples are: small digital
- circuits operating at sub Kelvin temperatures and really huge digital systems, where fore some reason the cost is less significant factor than the energy dissipation. · Many features of nSQUIDs are quite similar to those of qubits. From academic point of view it would be exiting to run a competition for the lowest possible energy dissipation. Quantum effects will play important

role when/if the energy dissipation is 10 -4 of k

B T. In this case a few nSQUIDs could be renamed into qubits and there is a chance that such

circuits could be reconstructed into a quantum computer.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

32

•

- Acknowledgements
- Our projects were relatively small. For example, our last year budget related  with reversible computing was $47 K. In fact, we were much richer because of many different kinds of support. · First, we like to mention unique but inexpensive or occasionally free
- fabrication of superconducting circuits at HYPRES, Inc. We received also a lot of help from Oleg Mukhanov, S. Tolpygo, A. Kirichenko, T. Filippov and D. Gupta. · Second, we thank for ONR support (Deborah VanVechten). In particular
- we have been funded for the development of an advanced  (active) magnetic shielding. The advance shielding is vitally important for
- experimentation with reversible circuits. · I wish to mentioned help from IBM Yorktown Heights people. In
- particular,  frequent discussions with S. Rylov and A. Rylyakov. · We got important pieces of advice from Erik DeBenedictis (Sandia) and

Alexey Usinov (Karlsrue University).

But of course nothing could be possible unless ARO contract number

W911NF-06-1-217 opened 'Pandora box' of reversible computing.

Annapolis, MD, March 15, 2012

Vasili.Semenov@StonyBrook.edu

33