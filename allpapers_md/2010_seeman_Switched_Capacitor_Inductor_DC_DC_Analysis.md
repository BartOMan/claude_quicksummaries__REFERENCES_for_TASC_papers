## A Comparative Analysis of Switched-Capacitor and Inductor-Based DC-DC Conversion Technologies

Michael D. Seeman Solar Semiconductor Inc

1292 Kifer Road, Suite 808, Sunnyvale, CA 94086 USA

Abstract -This  paper  compares  the  performance  of  SwitchedCapacitor (SC) and inductor-based DC-DC conversion technologies.  A metric to compare between the two topologies is discussed, and is used to compare switch utilization. Fundamental limits on utilization of reactive elements developed in the literature for all DC-DC converters are also reviewed and discussed, and this analysis shows that popular SC and inductorbased  converters  achieve  the  limits  of  utilization  for  reactive components.    These  limits  are  stated  in  terms  of  the  ratio  of output power to required stored energy in reactive elements.  A detailed analysis of available surface mount discrete components and  on-die  devices  reveals  that  capacitors  have  substantially higher energy and power density than their magnetic counterparts.  The challenging regulation task for SC converters is  also  discussed,  with  a  promising  strategy  outlined.    The  SC converter  is  evidently  a  promising  candidate  for  future  high power density integrated DC-DC converters.

Keywords  -  switched  capacitor  dc-dc  converters,  high  power density, charge-pump.

## I. INTRODUCTION

The traditional inductor-based buck converter has been the default design for most switched-mode voltage regulators for decades,  as  it  has  dominated  the  moderate  to  high  power (&gt;100mW) applications. However, the buck converter requires a bulky inductor and transistors rated for the full input voltage and the full output current of the application.  At the high  power  densities  required  by  today's  silicon  chips,  lowloss  inductors  are  difficult  to  integrate  and  remain  discrete components  in  nearly  all  cases.    As  the  industry  pushes towards  system  on  a  chip  (SOC)  solutions,  many  different circuit  functions  have  already  been  integrated  onto  a  single die, and the power converters occupy an increasing proportion of  printed  circuit  board  (PCB)  area.    In  contrast  to  the  buck converter, a Switched Capacitor (SC) DC-DC  converter requires  only  capacitors,  which  have  a  significantly  higher power density and can be integrated more easily than inductors.    Historically,  SC  converters  have  been  used  in integrated circuits to provide programmable voltages to memories,  and have mostly been limited to  low  power (&lt;100mW) applications. However, SC converters theoretically have lower intrinsic conduction loss than inductor-based  converters  for  a  given  total  rating  (e.g.  V-A product) of switches for certain converters or applications [1]. This  advantage  is  exploited  in  Ng  [2]  and  Le  [3],  further

Vincent W Ng, Hanh-Phuc Le, Mervin John, Elad Alon, Seth R Sanders EECS Dept, University of California, Berkeley

341 Cory Hall, Berkeley, CA 94720, USA

demonstrating  that  SC  converters  can  achieve  high  power density  and  high  efficiency  in  moderate  power  applications (e.g. &gt;1W),  by using off-chip capacitors and integrated capacitors, respectively. This paper investigates the advantages  of  the  SC  converter  with  respect  to  the  buck converter, and shows that it has promise in high power density applications. The analysis and examples point to the conclusion  that  SC  converters  can  and  will  surpass  their magnetic counterparts in overall performance.

Reference  [1]  discusses  a  methodology  to  analyze  and optimize SC converters, and compares the SC converter with the  buck  converter  in  terms  of  switch  utilization.  This  paper expands  on  the  discussion  in  [1],  but  focuses  on  reactive elements instead.  Section II  first  gives a brief review of the results in [1], and introduces common metrics to compare both SC and inductor-based converters.  Section III shows that  SC converters  can  meet  the  fundamental  limit  on  component stress that applies to all  DC-DC converters.  Section IV then compares the reactive component stresses among SC converters and inductor-based converters.  Section V discusses implementations of fully integrated DC-DC converters. Section VI briefly discusses an example using discrete capacitors, and Section VII discusses regulation for  SC converters.

## II. SC CONVERTER MODELING

Neglecting frequency dependent parasitic losses, the steady state behavior of a Switched Capacitor (SC) converter can be modeled as an ideal transformer with a series output impedance [1].

Figure 1: Model of a SC converter

<!-- image -->

In  this  model,  the  turns  ratio,  n,  represents  the  conversion ratio,  determined  by  the  converter  topology  and  switching pattern.  The output impedance represents the requisite output voltage drop used to move charge in the circuit.  The output impedance  is  a  function  of  converter  topology,  switching frequency and component sizes.

SC converters can operate in one of two unique operating conditions, or in the region between them.  At low switching frequencies,  the  converter  losses  and  output  impedance  are dominated by the amount of charge that can be transferred by capacitors.    This  regime  is  denoted  the  slow  switching  limit (SSL).    At  high  frequencies,  the  switch  on-state  resistance prevents  the  capacitors  from  completely  transferring  their charge each period, and thus, the switch resistance dominates the converter's loss.  This operating regime is denoted the fast switching limit (FSL).

This discussion assumes two-phase converters operating at 50%  duty  cycle.    The  SSL  (capacitor-dominated)  and  FSL (switch-dominated) output impedance are given by the following equations [1]:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

In (1), f sw represents the switching frequency, Ci is the value of  capacitor i ,  and ac,i is  the  charge  multiplier  of  capacitor i . The  charge  multiplier  is  defined  as  the  ratio  between  the charge  flowing  in  capacitor i during  a  single  period  to  the average output charge during that period.  Similarly, in (2), Ri and ar,i are  the  on-state  resistance  and  charge  multiplier  for switch i , respectively.

These expressions for an SC converter's output impedance explicitly  allow  for  its  optimization.    By  constraining  total switch V-A product (related to area for integrated implementations)  or  capacitor  energy  storage,  each  circuit element  can  be  sized  proportionally  to  its  charge  multiplier and inversely to its blocking voltage.  This optimization yields the smallest output impedance for a given allotment of switch V-A product or capacitor energy storage.

After  carrying  out  the  optimization  steps  above,  a  pair  of performance metrics can be developed from the output impedance expressions in (1) and (2) to express the ratio of the optimized performance of an SC converter to the cost of the components used.  In the case of the slow switching limit, the dimensionless metric in (3), below, is the ratio of the converter output GV 2 to  the  total  energy  storage  scaled  by  switching frequency.  In the case of the fast switching limit, the metric in (4), below, is the ratio of the converter output GV 2 to the value of the GV 2 ratings  of  the  switches,  totaled over the switches. Converter output GV 2 is  a  precise metric that allows an exact computation of a power versus loss relationship. These metrics assume  the  switches  and  capacitors  are  sized  optimally  as described  above  and  in  [1].    The  SSL  and  FSL  metrics  are given as follows:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

Notice that each of these metrics depends only on the squaredabsolute-sum  of  the  V-A  products  for  the  relevant  circuit elements  -  capacitors  or  switches  -  normalized  by  output power.    Thus,  the  performance  metrics  relate  directly  to  the fundamental operation of the underlying circuit. In the performance  metrics,  the  voltage  used  for  characterization  is the  component  voltage  rating,  since  this  sets  the  cost  of  the device.  In all cases, the maximum expected working voltage must be less than this rated voltage.

## III. FUNDAMENTAL LIMITS

Wolaver  [4]  has  developed  fundamental  limits  on  the component stresses in a DC-DC converter.  While these limits hold  for  all  DC-DC  converters,  they  can  be  specifically applied to switched capacitor converters to derive fundamental limits on the performance metrics stated earlier. This development  for  SC  converters  is given in this section. Section  IV-B  discusses  Wolaver's  limits  in  the  context  of inductor-based converters.

## A. SSL Analysis.

Based on the  reactive  elements  in  any  DC-DC  converter, Wolaver [4] states and proves the following relation:

<!-- formula-not-decoded -->

where n is the current or voltage step-down ratio (whichever is greater  than  one)  and vk and i k are  the  instantaneous  voltage across and  current through  reactive element  k, with the overbar indicating a time-averaged quantity for periodic steady state operation.

The SSL output impedance assumes a low-load condition where  there  is  negligible  voltage  drop  across  switches  and small capacitor ripple.  The current through a capacitor can be represented in terms of its charge multiplier:

<!-- formula-not-decoded -->

Substituting (6) into (5) yields:

<!-- formula-not-decoded -->

The SSL metric in (3) can be used to put this limit in terms of the SC converter parameters developed earlier.  Manipulating equations (7) and (3) yields

<!-- formula-not-decoded -->

This fundamental limit sets the maximum performance for any  switched  capacitor  DC-DC  converter,  based  on  reactive energy  storage.    Since  the  series-parallel  converter  achieves the fundamental limit, it has the highest ideal performance of any capacitor-limited SC converter.

## B. FSL Analysis

A similar fundamental limit can be placed on the switches in a DC-DC converter.  In any converter, the switches can be divided  into  two  groups:  the  dc-active  set,  where  switches conduct current in the direction opposite the blocking voltage (e.g.  diodes),  and  the  ac-active  set,  where  switches  conduct current  in  the  same  direction  as  the  blocking  voltage  (e.g. MOSFETs, BJTs).

Wolaver  [4]  states  and  proves  the  following  relations  for the ac-active and dc-active switches in any DC-DC converter:

<!-- formula-not-decoded -->

<!-- formula-not-decoded -->

where n is  the  step-down  ratio  of  the  converter  (greater  than one)  and vk and i k are  the  instantaneous  current  and  voltage associated  with  switch k .    For  a  two-phase  SC  converter operating  at  50%  duty  cycle,  the  switches  are  on  during  one phase,  such  that vk is  zero  and i k equals  the  switch's  charge multiplier ar,k times the output current.  In the other phase, i k equals zero and vk equals the blocking voltage vr,k .

Since the average instantaneous power in an ideal switch is zero, the time-averaged power term in (10) can be eliminated. By observing that the product of average voltage and average current is  negative for dc-active devices, and positive for acactive  devices,  equations  (9)  and  (10)  can  be  simply  added together.  By substituting the definition for the switch charge multiplier, the following equation can be obtained:

<!-- formula-not-decoded -->

Substituting the FSL performance metric in (4) can be used to obtain this limit in terms of the fundamental parameters of a switched-capacitor converter, analogously to the steps described in section IIIA  The fundamental limit on the FSL converter metric is given as:

<!-- formula-not-decoded -->

This  fundamental  limit  establishes  the  maximum  switch utilization possible in an SC converter.  Since the ladder-type converters (including the Dickson topology) achieve this limit for  all  conversion  ratios,  they  will  out-perform  other  SC converters in switch-limited applications.

## IV. COMPARISON OF TOPOLOGIES

This  section  provides  a  comparative  analysis  of  the  SC  and inductor-based converters in terms of the metrics and fundamental  limits introduced above,  beginning with  SC converters in subsection IV-A and following with a comparison with inductor-based converters in  subsection IVB.

## A.  Switched Capacitor Converter Metrics &amp; Comparison

By comparing the SSL and FSL metrics for converters of interest (shown in Figs. 2 and 3), the best converter topology can  be  chosen  for  a  specific  application.    In  switch-limited applications,  where  the  switch  cost  dominates  the  capacitor cost in nominal operation (e.g., integrated switches and discrete  capacitors),  choosing  a  converter  with  a  high  FSL metric is optimal.  However, if the capacitor cost is dominant (e.g. in fully-integrated converters), choosing a topology with a  large  SSL  metric  is  best.    As  shown  in  Figs.  2  and  3,  the Series-Parallel topology has the best SSL metric but the worst FSL  metric  of  the  topologies  compared.    Conversely,  the Ladder and Dickson topologies have the best FSL metric and worst SSL metric.

Figure 2: SSL Metric for various topologies and conversion ratios

<!-- image -->

Figure 3: FSL Metric for various topologies and conversion ratios

<!-- image -->

Table  1:  Sample  of  commercially-available  PCB-level  capacitors  and  inductors  suitable  for  DC-DC  converters.    For  each device, the volumetric energy storage density is computed.  This energy density represents a cost metric that can be used in reactive component comparison.  However, in many converters, the power density is of larger concern than the energy density. Thus, the power density of these components is also calculated considering a 20 °C rise at 1 MHz.  Capacitors have a greater energy and power density compared with inductors, but for larger devices, this relation may not hold true.

| Capacitor       | Capacitance   | Vmax       | Imax   | Size            | Energy Density   | Power Density   |
|-----------------|---------------|------------|--------|-----------------|------------------|-----------------|
|                 | µF            | V          | A      | mm              | µJ/mm 2          | W/mm 3 @1MHz    |
| T-Y Ceramic     | 1             | 35         | 2.8    | 1.6 x 0.8 x 0.8 | 149.536          | 95.703          |
| Vishay Tantalum | 100           | 6.3        | 0.8    | 3.2 x 1.6 x 1.6 | 242.249          | 0.615           |
| Kemet Elect.    | 22            | 16         | 3.1    | 7.3 x 4.3 x 1.9 | 47.216           | 0.832           |
| Inductor        | Inductance    | Imax (sat) |        | Size            | Energy Density   | Power Density   |
|                 | µH            | A          |        | mm              | µJ/mm 2          | W/mm 3 @1MHz    |
| Coilcraft SMT   | 10            | 0.21A      |        | 2.6 x 2.1 x 1.8 | 0.0224           | 0.0224          |

## B   Buck converter metrics &amp; comparison

The limits on converter performance developed in section III  utilize  properties  that  apply  to  all  DC-DC  converters. Thus, it  would  be  highly  informative  to  use  these  metrics  to compare  switched-capacitor  and  traditional  buck  converters. Using the concepts in sections II and III, the FSL metric for a traditional buck converter can be derived, and is given by:

<!-- formula-not-decoded -->

When  finding  this  metric,  the  converter's  total  switch GV 2 rating  is  constrained,  and  the  two  switches  are  optimized  to minimize conduction loss for each specific conversion ratio to develop this expression.

Similarly,  when  the  reactance-based  performance  limit  is found, the buck converter meets the Wolaver limit in (5) when considering only the power inductor. It is somewhat reasonable to focus only on the inductor, since the input and output  capacitance  can  be  made  arbitrarily  small  in  principle by using a sufficiently large  number of interleaved converter phases. We  note  that inductor peak energy storage is minimized with a design choice that corresponds to operation at the edge of discontinuous conduction mode (DCM), though this choice may not correspond to minimal inductor size given a loss constraint.

In  any  case,  for  the  component  range  of  interest  for integrated or board-mounted applications, inductors are much bulkier than capacitors for the same  energy and  power handling  capability,  as  shown  in  Table  1.  Thus,  the  buck converter  can  be  significantly  larger  than  a  comparable  SC converter.

When  comparing  reactive  element  usage,  we  see  that switched-capacitor  converters  are  similar  to  inductor-based converters  in  terms  of  required  V-A  product  for  the  best topologies in each class.  However, the electrical utilization of the reactive elements differs significantly. Inductor-based converters,  such  as  the  buck  and  boost  topologies,  can,  in principle, fully magnetize and de-magnetize a lossless inductor every period in the case of discontinuous conduction without incurring  loss.  This  is  not  usually  the  case  in  practice  since depending upon design, there are significant losses associated with  ripple  current  and  ripple  flux.    SC  converters,  on  the other  hand,  only  utilize  a  small  fractional  ripple  voltage  on their  capacitors,  since  this  ripple  corresponds  to  loss  in  the slow-switching limit, also known  as  charge-sharing loss. Despite  the need  to store additional  energy in  switched capacitor  converters, 1 the  substantially  superior  energy  and power  density  of  capacitors  with  respect  to  inductors  for practical frequencies of interest allow  switched  capacitor circuits to provide higher power density at equal efficiency, or higher efficiency at equal power density.

The subsequent  section provides a  more detailed analysis of  on-die  reactive  elements  in  the  context  of  fully  integrated DC-DC converter applications.

## V. FULLY INTEGRATED IMPLEMENTATIONS

With increasing levels of integration of digital processing cores and functional blocks in system-on-a-chip (SOCs), it is clear  that  multiple  independent  power  supplies  need  to  be implemented  on-die  to  actively  optimize  the  whole  system's power and circuit performance. Simply adding off-chip supplies  will  not  only  incur  serious  degradations  of  supply impedance  due  to split package  power  planes, but also additional cost due to increased motherboard size and package complexity.  Therefore,  there  is  a  strong  motivation  to  fully integrate voltage conversion on the silicon chip using a pointof-load strategy as shown in Fig. 5. With an on-die approach, the  density  metric  is  defined  using  the  total  implementation area, rather than the total implementation volume.

In  order  to  make  the  optimal  choice  of  DC-DC converter implementation in a fully integrated context, a fair comparison

1 In practice, buck converters will also require significant additional energy storage in the form  of input and/or output  decoupling capacitors in order to achieve good transient response.

between integrated inductors and integrated capacitors requires  a  consideration  of  the  technology  used  in  the  two relative  converter  types.  With  an  initial  implementation  goal to ensure no additional cost for special process steps, the most desirable  method  is  to  use  the  gate  oxide  to  implement capacitors.  Similarly the top metal layer is used to implement inductors. Given an area of 1mm 2 in today's  CMOS technology,  a  capacitance  of  about  10nF  can  be  obtained  to achieve an energy density of 5nJ at 1V  of operation. Meanwhile, for  a  planar  spiral  inductor  implementation  with 1mm  diameter,  3  turns,  100 µ m  line  width 2 and  50 µ m  line spacing, approximately 12nH can be achieved to obtain 6nJ at 1A  operation.    However,  this  inductor,  implemented  in  a common  3 µ m-thick  top  metal  layer,  has  a  DC  resistance  of 600m Ω , equivalent to 37.5% efficiency degradation for a 1V1A or 1W/mm 2 output.  This 62.5% efficiency critical limit is calculated  without  other  losses  of  the  inductor  coming  from AC  resistance,  substrate  loss,  and  inductive  switching  loss. Significantly, integrated capacitors do not suffer from any of these loss mechanisms.

Figure 5: On-die point-of-load power distribution

<!-- image -->

Le in [3] reports  a preliminary implementation of a fully integrated SC DC-DC converter that achieves efficiency above 80% at 0.55W/mm 2 of output power density with no additional fabrication steps in a commercial 32nm CMOS process.  The work  also  illustrates  methodologies  to  address  several  wellknown issues associated with SC converters, including limited output  voltage  range,  voltage  ripple,  output  power  density, interconnect for many  capacitors, and voltage rating of devices.

If  additional  process  steps  are  considered,  both  inductor and  capacitor  technologies  can  be  improved.    A  comparison can  be  made  between  an  inductor  implemented  with  a  thick electroplated top metal (usually Aluminum) layer and capacitors utilizing widely available deep-trench or 3D DRAM capacitor technologies.

For example, if fabricated on a 30 μ m-thick top metal layer, the DC resistance ܥܦܴ of the inductor can be reduced to 60m Ω . However,  increasing  the  thickness  does  not  reduce  the  AC resistance ܥܣܴ significantly. At a nominal switching frequency of 100MHz (which would maintain reasonably low switching

2 In practice, certain process rules usually limit a single line width to a smaller number, leading to a higher DC resistance.

losses with modern CMOS transistors), the metal skin depth is only  approximately  8.2 μ m  Ignoring  the  proximity  effect,  a naïve analysis estimates the AC resistance factor =ܥܣܴ/ܥܦܴ=ݎܨ 1.61 ,  or ܥܣܴ =  97  m Ω .    Assuming  that  the converter  is  operating  at  the  edge  of  continuous  conduction mode (CCM) and discontinuous conduction  mode (DCM) to best  take  advantage  of  the  available  inductor  energy  density, the loss due to ܥܣܴ and ܥܦܴ are  130mW  and  60mW, respectively. These losses alone limit the achievable efficiency to 84% for a 1W/mm 2 implementation.  Thus, even with  thick  metals,  the  performance  of  the  inductor-based converter is only comparable to an SC converter implemented in completely standard CMOS technology.

The  work  reported  in  [12]  also  concludes  that  significant improvements  are  still  needed  for  integrated  inductor-based converters to reach 80% efficiency over a high power density range. A successful implementation with magnetic material on silicon  from  Enpirion  [14]  achieves  efficiency  of  80%  at 0.4W/mm 2 . As reported in [13], substantial effort was put into improving the integrated inductor by utilizing magnetic materials as well as thick metals  to  achieve  76%  peak efficiency at a power density of ~10W/mm 2 with a roughly 2to-1 conversion ratio.

While these works certainly demonstrate significant progress in integrated inductor technology, these solutions are not yet widely available at low cost.  In contrast, deep trench or 3D capacitors with densities on the order of 200400nF/mm 2 are  ubiquitously  utilized  in  stand-alone  DRAMs and are gaining traction in embedded DRAM applications as well.  The ~20-40x increase in energy density offered by these capacitors over CMOS gate oxide translates into significantly improved  efficiency  and  power  density  for  SC  converters. Specifically,  the  work  reported  in  [11]  demonstrated  a  fully integrated 2-to-1 SC converter implemented with ~200fF/ μ m 2 deep  trench  capacitors  and  achieved  efficiency  of  90%  at  a power  density  of  2W/mm 2 . An  analysis  similar  to  that described  in  [3]  predicts  that  with  200fF/ μ m 2 deep  trench capacitors  and  modern  CMOS  switches,  an  optimized  SC design can achieve above 88% efficiency for power densities up  to  10W/mm 2 -  i.e.,  notably  higher  than  the  design  from [13] while utilizing only relatively standard processing techniques.

## VI. DISCRETE CAPACITOR IMPLEMENTATION

SC  converters  may  offer  compelling  advantages  in  more traditional applications with external energy storage elements as  well.    Ng  [2]  reports  on  a  12V-to-1.5V  Dickson  SC converter  using  off-chip  ceramic  capacitors  and  integrated switches.  Unlike most SC converters that are designed for low conversion ratio (&lt;4:1) and low power (&lt;100mW) applications, this converter operates with moderate conversion ratio (8:1) and moderate power level (1.5W).  As discussed in [2], the converter achieves a higher efficiency (93% vs. 89%) and  smaller  component  PCB  footprint  (13mm 2 vs.  34mm 2 ) when compared to commercially available buck and SC DCDC converters, and highlights the fact that SC converters can attain high efficiency in high conversion ratio applications as well. The improvement in volumetric density for this design is largely  due  to  the  high  energy  density  of  capacitors  when compared to inductors, as reported in Table 1.

## VII. REGULATION OF SC CONVERTERS

One of the main drawbacks of SC converters is that they do not  nominally  provide  an  efficient  means  to  regulate  over  a wide range of output voltages, and therefore in this section we will briefly discuss techniques that address this issue.

Regulation  of  an  SC  converter  can  be  achieved  through modulating either the output referred resistance, ROUT ,  of  the converter, or changing the unloaded conversion ratio, n .  Since the  maximum  achievable  efficiency  of  an  SC  converter  is limited by the voltage drop across ROUT , changing n is desired when  the  ratio VIN/VOUT varies  substantially.    However,  the complexity  of  the  converter  and  the  number  of  components increase  with  the  number  of  possible  conversion  ratios  [5]. Thus, as a practical SC converter may not offer extremely fine resolution of n ,  modulating ROUT is  also  necessary in order to maintain  tight  regulation.  However,  as  long  as  sufficient choices of n are available to limit the voltage range over which linear  regulation  through  modulating ROUT is  necessary,  the efficiency of the SC converter can remain high across a broad range of VOUT .

With  the  large  number  of  switches  in  an  SC  converter, there are numerous ways to modulate ROUT [6-9]. All of these methods can be categorized as either modulating RSSL or RFSL . Bayer  [6]  proposes  skipping  clock  pulses,  and  Seeman  [7] proposes  controlling  the  clock  hysteretically,  with  both  of these approaches effectively adjusting switching frequency to modulate ROUT via RSSL .  Gregoire [8] proposes varying switch conductance and Zhu [9] proposes varying switch duty ratios, with  both  schemes  effectively  varying  switch  resistances  to modulate ROUT via RFSL .

Varying ROUT through RSSL means the converter is operating  in  the  SSL  regime.  This  scheme  leads  to  lower switching  frequency  for  a  given ROUT ,  and  thus  potentially lower switching loss and higher efficiency.  However, output current is impulsive in  the  SSL, and this scheme can lead to higher  output  voltage  ripple.    A  larger  output  capacitor  or multi-phase interleaving may be necessary in order to reduce the  output  ripple  down  to  reasonable  values.    On  the  other hand,  by  actively  modulating  the  switch  conductance  of  the 'output'  switch  of  a  converter,  the  output  current  can  be maintained at a near constant value [8], and the output ripple minimized.  'Output' switches here are the last switches that separate the flying capacitor(s) from the output terminal.

A regulated SC converter based on combined output switch conductance modulation and variable ratio can be modeled as shown in Fig. 7.  The controller can be divided into 2 loops. The inner loop modifies ROUT for tight regulation, and can be modeled as a series transistor controlled by an error amplifier. The outer loop chooses the best conversion ratio such that both regulation and high efficiency is maintained.

Figure 7: Model of a regulated SC converter

<!-- image -->

A  current  ramp  simulation  of  an  SC  converter  using  this control  scheme  is shown  in  Fig. 8. The  SC  regulator modulates the conductance of the output switches for regulation.  In order to reduce switching losses, the switching frequency  is  set  proportionally  to  the  conductance  of  the output switches.  As shown in the figure, when output current increases, VOUT droops  and  switching  frequency  increases. This  corresponds  to  an  increase  in  switch  conductance,  as modeled  in  Fig. 7. As  switch  conductance  reaches its maximum,  the  conversion  ratio n is  reduced  to  maintain regulation. After n reduces, voltage drop across transistor M1 increases, and thus switch conductance is reduced, accompanied by a reduction in switching frequency. After the second  reduction  in n , VOUT surges  temporarily,  as  shown  in Fig. 8. This is due to the residual charge stored on the flying capacitor from when  it was  configured in the previous conversion ratio.

Figure 8: Simulation of a regulated SC converter

<!-- image -->

## VIII. CONCLUSION

This paper presents analysis and practical data highlighting that the SC  converter  can  be  superior  to  the traditional inductor-based  buck  converter  in  terms  of  switch  utilization, reactive  element  utilization,  and  integration.    In  terms  of switches, the ladder-type SC converter has lower switch V-A stress  than  the  buck  converter,  and  meets  the  fundamental limit for minimum switch V-A stress applicable to all DC-DC converters [4].  In terms of reactive elements, while both the series-parallel  SC  converter  and  the  buck  converter  meet  the fundamental  limit  on  reactive  element  V-A  stress,  the  SC converter  benefits  from  the  significantly  higher  energy  and power  densities  of  capacitors  over  inductors.    In  terms  of integration, a fully integrated SC  converter can already achieve  respectable  performance  without  extra  process  steps [3],  whereas  a  fully  integrated  buck  converter  will  likely require  both  thick  metals  and  magnetic  materials  to  achieve acceptably high efficiency and high power density. Regulation for the SC converters can be achieved by regulating  the  output  resistance  and  conversion  ratio.    With these  considerations,  this  work  comes  to  the  conclusion  that the  SC  converter  has  a  bright  future  for  high  power  density integrated DC-DC converters.

## ACKNOWLEDGEMENTS

The authors would like to acknowledge  grants from National  Semiconductor,  Freescale  Semiconductor  and  Intel. H.-P. Le and E. Alon would like to acknowledge the support of  C2S2  and  IFC  (2  of  5  research  centers  funded  under  the Focus  Center  Research  Program,  a  Semiconductor  Research Corporation program), an IBM Faculty Award, NSF, and the sponsors, students, faculty, and staff of BWRC.  M. John and S. Sanders would like to acknowledge the support of GRC, a Semiconductor Research Corporation program.

## REFERENCES

- [1] M.  Seeman  and  S.  Sanders,  'Analysis  and  Optimization  of  SwitchedCapacitor DC-DC Converters', IEEE Trans. on Power Electronics, vol. 23, no. 2, Mar., 2008
- [2] V. Ng, M Seeman, S. Sanders, 'Minimum PCB Footprint Point-of-Load DC-DC  Converter  Realized  with  Switched-Capacitor  Architecture', Proc. IEEE Energy Conversion Congress and Exposition (ECCE), 2009
- [3] H.-P.  Le  et.  al,  "A  32nm  Fully  Integrated  Reconfigurable  SwitchedCapacitor DC-DC Converter Delivering 0.55W/mm2 at 81% Efficiency",  ISSCC Dig. Tech. Papers, pp. 210-211, 2010
- [4] D. Wolaver, 'Fundamental study of DC-DC conversion systems," Ph.D. dissertation, M.I.T., February 1969.
- [5] S.  Ben-Yaakov  and  A.  Kushnerov,  'Algebraic  Foundation  of  SelfAdjusting  Switched  Capacitors  Converters'  IEEE  Energy  Conversion Congress and Expo (ECCE), pp. 1582-1589, September 2009.
- [6] E. Bayer and H. Schmeller, 'Charge Pump  with Active Cycle Regulation - Closing the Gap between Linear- and Skip Modes' IEEE Power Electronics Specialists Conference (PESC), vol 3, pp. 1497-1502, August 2000.
- [7] M.D.  Seeman,  S.R.  Sanders  and  J.M.  Rabaey,  "An  Ultra-Low-Power Power  Management  IC  for  Wireless  Sensor  Nodes",  IEEE  Custom Integrated Circuits Conference (CICC), pp. 567-570, September 2007.
- [8] B. Gregoire, 'A Compact Switched-Capacitor Regulated Charge Pump Power Supply' IEEE J. Solid-States Circuits, vol 41, August 2006.
- [9] G.  Zhu  and  A.  Ioinovici,  'Switched-Capacitor  Power  Supplies:  DC Voltage Ratio, Efficiency, Ripple, Regulation' IEEE Symp. Circuits and Systems, vol 1, pp. 553-556, August 2002.
- [10] G. Rincon-Mora and P. Allen, 'A Low-Voltage, Low Quiescent Current, Low Drop-Out Regulator' IEEE J. Solid-State Circuits, vol 33, January 1998
- [11] L.  Chang,  et  al.,'A  Fully-Integrated  Switched-Capacitor  2:1  Voltage Converter with Regulation Capability and 90% Efficiency at 2.3A/mm 2 ,' IEEE Symp. VLSI Circuits , June, 2010
- [12] Jaeseo Lee, et al., 'Evaluation of Fully-Integrated Switching Regulators for CMOS Process Technologies,' IEEE Trans. VLSI , pp. 1017 - 1117, 2007
- [13] J.  Ted  Dibene,  et  al.,  'A  400  Amp  Fully  Integrated  Silicon  Voltage Regulator with In-die Magnetic Coupled Embedded Inductors', Special Presentation, APEC, Feb. 2010.
- [14] A. Lotfi,  T.  Liakopoulos,  M.  Wilkowski,  'Integrated  Inductors  in PwrSoC: Today &amp; Tomorrow', Special Presentation, APEC, Feb. 2010.