## Delay insensitive RSFQ circuits with zero static power dissipation

Stas  Polonsky

Physics Department, SUNY Stony Brook, Stony Brook, NY 11794 USA

Abstract -Total power dissipation in RSFQ  circuits consists of two parts, dynamic and static. Dynamic power is dissipated  in Josephson  junctions performing  useful logical and data transmission operations. This  dissipation is  fundamental  and proportional  to the data rate (at 4 K, of the order of lo-''  Joule per bit). Static power is dissipated in  resistors used by  RSFQ circuits to distribute  dc bias current between Josephson junctions.  This  part  of  dissipation is  not  intrinsic  to  RSFQ circuits  and  in principle can be eliminated.  The goal of this work is to show that Delay Insensitive (DO  RsFQ primitives can be modified so that resistors are no longer required  in the dc power supply distribution network, so that  the  on-chip static  power dissipation is absent. In this report we present the schematics for such primitives, define the class of  circuits that allow resistorfree current distribution network, and formulate the requirements  to the design of this network.

## I. INTRODUCTION

Low  power  dissipation  of  logic circuits is  vital  for  the Petaflops project [l].  RSFQ circuits  are considered as the best candidate  for this  project  since  they offer  lower  power dissipation  at very high  speed.  The power  dissipation  Pt in RSFQ  circuits  is the sum  of the dynamic  dissipation Pd=I,.Q,,=2. Joule  per Josephson  junction switching, which  is associated with  performing  logical operations, and static  dissipation P, of the  resistive  power distribution network.  In typical  large  scale  (few  thousand  Josephson junctions) RSFQ circuits P, dominates the total power budget, for  example  the  efficiency  E=Pd/Pt of the  RSFQ  digital autocorrelator [2]  was  about  2.  lo-'. For  relatively  simple circuits the contribution of P,  can be decreased at the expense of relative bias voltage margin degradation [2] (see Fig. 1).

-.--

Figure 1 : Efficiency of RSFQ circuit as a function of bias margin degradation

<!-- image -->

Manuscript received September 15,1998.

This work was supported in part by DARF'A, NSA, and NASA via JPL, and by NSF under grant No. ECS-9700313.

10.51-8223/99$10.00 0 1999 IEEE

In  particular,  the experiment [2] has shown that an  RSFQ XOR gate can operate at a frequency of  15 GHz with e 0 . 2 5 for  an  input  sequence  101=0 and  bias  margin  degradation from  60%  to  20%. For  practical  circuits with  typical  bias margins around 30%,  margin degradation by more than  10% is  hardly  desirable. As  a  result  one  could  expect E-0.125 assuming that  the  circuit operates  100% of  the  time. For  a general purpose processor  this  estimate may be significantly lower  since  the  workload  cannot  be  distributed so  that  all subsystems operate 100% of the time.

A universal  set  of  asynchronous  Delay  Insensitive (DI) RSFQ primitives, suggested in  1997 by  the researchers from Intel, SUNY-Stony Brook, and University of Texas in Austin [3], was initially  addressing such issues as implementation of asynchronous logic gates in RSFQ technology, their complexity and speed. It was shown that DI RSFQ primitives are at least comparable in area, speed, and parameter margins to existing implementations of  Boolean primitives  in RSFQ, in  sharp  contrast  to  the  situation  in  CMOS. As a  building block of asynchronous  circuits,  they  have  an important advantage  over existing clocked RSFQ logic elements on that they  require no  minimum  separation  in  the  arrival  times  of input events to work correctly.

We have found that  the static power  dissipation  P,  of  DI RSFQ gates can be completely eliminated by means of  a nonresistive,  purely superconductive  power distribution  network. and Josephson-junction-based phase-compensating bias current injectors.  For these gates P,S,  at the expense of  some increase  of Pa  associated  with switching of the  phasecompensating Josephson junctions. In a sense, this fact brings an  analogy  with  CMOS  with  its  negligible  static  power dissipation. From  the Petatlops project  point of  view,  zero static power  dissipation might be the most important feature of  DI  RSFQ  gates.  This  fact,  combined  with  advantages arising from the asynchronous nature of DI RSFQ (modularity, average  speed of operation as compared with the worst case  speed  of clocked  circuits)  might  become  an important contribution to the Petaflops project.

The objective  of  this report is  twofold.  In  Section  I 1   we present  arguments  why  it  is impossible for  classical RSFQ circuits to avoid using resistive  bias distribution networks  and give estimates on  the efficiency of  complex parallel circuits. In  section  I 1 1   we  show  how  DI  RSFQ  primitives  can  be modified to allow purely inductive  power distribution network and formulate design requirements for circuits with zero static  power dissipation.

## 11. BIAS NETWORK IN CLASSICAL RSFQ CIRCUITS

## A. Resistive  bias network.

Classical RSFQ data representation  assumes that a logical '1'  corresponds to an SFQ pulse in a 'clock window', and a logical '0' to an absence of  such a pulse. Fig. 2 a  presents a two parallel segments of  a classical Josephson  Transmission Line (JTL). The upper J T L (input a) transmits  logical ' U ' s , the lower SIZ (input b) 'transmits'  logical '1's.

*

Figure 2:  Bias of classical RSFQ JTL: (a) resistive (b) inductive

<!-- image -->

For the resistively  biased JTL, the circuit bias current Zb is divided equally  between  both  junctions J l ,  J2 so  that  the junction bias current Z=Ib.Rz/R where R is the value of bias resistor, and, in our example, Rz=W2. The current I is usually selected  as I=0.7,Zc, where Z , is  the  critical  current  of a Josephson junction. In  addition  to  current Z , there  exists  a 'redistribution'  current Zr=V/2R flowing into '0' transmitting JTL, which is caused by a voltage drop across the switching junction J l :  V=fQo, where f is the fkequency of pulses at Jl, and Q0=2.07~10~15 Wb, the  magnetic  flux  quantum.  For N parallel JTLs each transmitting '1's except one, the redistribution  current  into the later JTL is

<!-- formula-not-decoded -->

assuming N&gt;&gt;1, for  example N&gt;lO. To  ensure the correct circuit operation for any input d a t a , one should select such a value of R that Z, &lt; &lt; Z . Introducing the ratio x=ZJZ, and using expressions  for dynamic  and static  power dissipation

<!-- formula-not-decoded -->

one gets the following estimate  on efficiency

<!-- formula-not-decoded -->

For  typical -RSFQ circuits, the margin  on  bias  current Z is about  L-30%, so  that  the  value ~ 5 1 0 % seems  like  a reasonable  compromise. If the  estimate ( 3 ) is  valid for arbitrary complex RSFQ 'circuits,  one might expect the best case efficiency of these circuits  in the  4.8-9%  range.

## B. Inductive bias network

A natural question  arises if  relatively low  efficiency of resistively biased classical  RSFQ circuits can be overcome b y using  inductive  power  distribution  of she  sort  depicted  in Fig. 2b. Here, the bias resistors are replaced with corresponding inductors L, so that the bias current l b is split equally between junctions JI,  J2: I=IbLz/L (for this particular example, Lz=U2). Now, unlike the  resistive bias, the redistribution current Z,=(ql-(p2)/2L depends on  the difference of phases q ~ , @ across junctions Jl, J2 respectively. If  lower J T L transmits  '1'  and  the  upper  one -'0's  then after approximately M=2.L.(Ic-Z)/Qo pulses  the  current Z , will  be large enough to cause switching of J2, which is an error, and cannot be tolerated.

As one can see, the reason why inductive  biasing cannot be used in classical  RSFQ is the data-dependent  phax accumulation at different current injection points of a circuit. In  other words,  classical RSFQ  data representation excludes inductive  biasing schemes.

## 11 1 .   I N D U C T I V E BIAS NETWORK IN DI RSFQ CIRCUITS

## A. Data transmission

Figure 3: Inductive bias of dual-rail JTL

<!-- image -->

Dualrail da t a encoding enables clock free data transfer [ ' I ] , [5]. For this type of  encoding, a pair of  (true-and false3 d a l a lines  carry  lbit binary  information. The  propagation of  a pulse on  the trueline or the falseline represents logical 'I' or '0' respectively. From  the  'inductive biasing'  point  of

view, the  most  important feature  of the dual-rail da t a encoding is  that  both  logical '0' and  '1' are  transmitted using  SFQ pulses. This fact  can  be  used  to  equalize phase accumulation at different points of  the circuit, which, in turn, opens the way for using the inductive  biasing.

Fig. 3 introduces an inductive biasing  scheme for dual-rail data  transmission.  The  circuit  depicted serves  the  same purpose  as  those from  Fig.  2 -it  propagates  2-bit  digital signals a and b. Each signal is represented by  two JTLs. For example, the '0's of  signal b (the lower part of  the  circuit) propagate  through junction J4, '1's  propagate through junction JZ. The critical currents of  the junctions J2, J3 are somewhat smaller then  those  of JZ, J4. As a  consequence, whenever J1 switches, J 3 switches  too,  compensating  the phase  difference in  the loop J1, J2,  J3,  J4. Similarly,  the switching of J4 leads to the switching of J2. Later on  we  will refer to  the junctions, serving the function  similar to that  o f J2, J3, as phase-compensating junctions. The described dualrail  circuit  (which  is,  by  the  way,  similar to  a  confluence buffer [7]) ensures that the phase at the current injection point B increases by  2n  everytime signal b arrives,  disregarding whether it is '0' o r '1'. In  what  follows,  we  will refer  to circuits of  that type as phase-compensating circuits.

If the signals a and b have the  same rate,  the maximum phase difference between  current injection points A and  B will not exceed 2n, so that  the resulting redistribution current Z,&lt;W2L. Its value can be made arbitrary small by increasing the bias inductance L.

## B. Data storage and processing

For dualrail circuits, efficient delay insensitive primitives have been proposed [3] (see also report [6] at this conference). A lx23oin  serves  as  a  destructive  readout register with a dualrail  data input/output and a request input. Note  that the  order  of  a da t a pulse  and  a  request pulse  is arbitrary. Another primitive,  the  2x23oin  serves as  a  logic gate. It has two dualrail  inputs and four outputs one of  which produces  a pulse in response to four possible input patterns operation by merging its outputs with confluence  buffers [6]. ( U , , , '01' , &lt;&lt; lo', '1  1').  It can implement any 2input binary

a

Figure 5: 2x2-Join: (a) with resistive  bias (output JTL not shown), (b) phase-compensating

<!-- image -->

Both  circuits can  be  made  phase-compensating. Fig.  4a presents the original schematic of  a  1x2-Join (for details see

Figure 4: 1x2-Join: (a) with resistive  bias, (b) phase-compeusating

<!-- image -->

[3] or [6]), given for the sake of comparison, and Fig. 4b its phase-compensated  analog. The part of the circuit, irrelevant for the further discussion, is enclosed into a box  titled  '1x2Join core'. The proper bias to the circuits is provided by  an inductive tree L1, L2. The dual-rail data input b is  phasecompensated  by  adding junctions JI, J2 and  injecting  bias current distributed  by inductance LI in point B.

Please  note  that  there  is  no  need  to  phase-compensate single-rail read-out input a, since the phase accumulation at point A has the same  rate as that at point B.

Fig. 5  presents a  phase-compensating  version  of  a  2x2Join. The bias current II, is injected  into points A, B, and C using  inductive tree L1, L2, W. Dual-rail inputs a and b are phase compensated in a way similar to the data input of  the 1x2-Join.  The four-rail output c is phase-compensated by the Josephson junction  tree JI, J2, .  .  . , J6. The example below illustrates the operation  of  this tree. Let  us  assume that the input to the circuit  is a=b=O. As soon as a0 and b O pulses are present,  the  output COO produces  a  pulse,  which causes junction J3 to  switch, which,  in  turn,  causes junction J5 to switch. As a result,  the phase at the point C increases  by 2n, i.e. this current injection point is phase-compensated. Similarly, the input a=I, b=O, produces a pulse at the output cl 0 and causes switching of junctions J1 and 56.

## C. Requirements on inductively biased circuits.

For complex circuits consisting of many cells the following requirements  should  be  met  to  allow  inductive  dc  power distribution network:

1. All  cells  must  be  phase-compensating,  i.e.  for  one single operation the phase increment at the cell's bias current injection point  is 2nn, where n is  constant throughout the circuit. Typically, n would be equal to one.
2. For  any  single input  operand  or  a  set  of  operands, every cell in a circuit must perform the same number of  operations. Typically, this number would be equal to one.

In  the case of  DI  RSFQ primitives, all primitives can be made  phase-compensating  (the  trivial  cases  of 1x1-Join, Merger, and Fork are not  considered in  this paper). The DI RSFQ primitives form a universal set  of  circuit primitives such  that  any  circuit  is  realizable  as  a  network  of the primitives [8],  which  means the fist requirement does  not impose serious  restrictions.

The second requirement does not impose serious restrictions either. In fact, all synchronous circuits operating at a single clock rate (single-rate circuits) or their asynchronous counterparts  satisfy this requirement. Multiplerate  circuits  can be  designed  using several  independent inductive power  distribution  networks (one for  every clock rate) if the number of different  clock rates is not too large.

## D. EfJiciency

There is no static power  dissipation  in  inductively biased circuits based on  DI RSFQ primitives. Nevertheless, about a. half of Josephson  junctions  in these circuits  are  phasecompensating,  and  do  not  perform  'useful'  computations. Thus,  the  circuit  efficiency  can  be  crudely  estimated  as E=50%.

## IV. CONCLUSION

We presented arguments why it is impossible for classical RSFQ  circuits  to  avoid  using resistive  bias distribution networks  and  gave  estimates on  values of  bias resistor  for complex  parallel  circuits.  We  also  demonstrated how  DI RSFQ primitives can be modified to allow purely inductive power distribution networks with zero static power dissipation, and  formulated  design  requirements  for  such circuits.

## ACKNOWLEDGMENT

The author thanks Kostya Likharev and Vassily Semenov for fiuitful  discussions.

## REFERENCES

- [l]  K.  Likharev, 'Recent progress and prospects  of  superconductor digital technology', FED report, January 1997.
- [2] A.V. Rylyakov, 'Ultra-low-power RSFQ Devices and Digitd Autocorrelation of Broadband Signals', Ph.D. thesis, Physics Department,  SUNY-Stony  Brook, May 1997.
- [3]  P. Patra, S. Polonsky, D. Fussel, 'Delay Insensitive Logic fix Superconductor Technology', Extended Ab.ytracts of ISEC'97, Eindhoven, The Netherlands,  pp. 42-53, April 1997.
- [4] J.Z. Deng, S.R.  Whiteley, and T. Van Duzer, 'Data-driven self-timing #of RSFQ  digital  integrated  circuits', Extended  Abstract.r  of  ISEC'95, Nagoya, Japan, p. 189,1995.
- [SI A.V. Rylyakov,  S.V. Polonsky  'All-Digital 1  -bit  RSFQ  Autocorrelator for  Radioastronomy  Applications:  Design  and  Experimental  Results', IEEE Transactions on  Appl. Supercond., vol. 8, no.1, p. 14-19,1998.
- [6]  Y. Kameda, S . Polonsky, M. Maezawa,  T. Nanya,  'Self-timed parallel adders based on DI RSFQ primitives', report EOD-04 at this conferencs.
- [7] K.K. Likharev and V. K. Semenov, 'RSFQ logic/memory family: A new Josephsonjunction technology  for  subterahertzclock  frequency digital systems,' IEEE Trans. Appl.  Supercond., vol. 1, no. 1, pp.  3--2.8, Mar. 1991.
- [8] P.Patra, 'Approaches to Design of Circuits for Low-Power Computation', Ph.D. thesis, The University of Texas at Austin, 1995.