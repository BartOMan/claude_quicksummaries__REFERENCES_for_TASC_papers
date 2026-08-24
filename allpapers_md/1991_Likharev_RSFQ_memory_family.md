## RSFQ Logic/Memory Family: A New Josephson-Junction Technology for Sub-Terahertz-Clock-Frequency Digital Systems

K. K. Likharev and V. K. Semenov

Invited Paper

Abstract-Recent developments of therapid single-flux-quantum (RSFQ)circuit family are reviewed. Elementary cells of the family can generate, pass, memorize, and reproduce picosecond voltage pulses V(t) withnominally quantized areav(t)dt=Φo，corresponding to transfer ofa singlemagneticfux quantum Φ=h/2eacross a Josephson junction. Functionally, each cell can be viewed as a combination of a which are physically similar to the signal pulses. Hand-shaking style of local exchange by the clock pulses enables onetoincrease complexity of the LSI RSFQ systems without loss of operating speed. The simplest componentsof theRSFQcircuitry havebeen experimentally tested at clock frequencies exceeding 100 GHz, and an increase of the speed beyond 300 GHz is expected as a result of using an up-to-date fabricationtechnology. Thereviewincludesadiscussionofpossiblefuture developments and applications of this novel, ultrafast digital technology.

ultrafast digital signals can bepassed along the chips ballistically that of light. (It is a pity that so many advertisers of the optoelectronics forget that one does not need tohavelight for havingthespeedoflight!)

## I. INTRODUCTION

QEMICONDUCTORmicroelectronics continuesitsvictorious Smarch, despite repeated claims of finding new physical principles that would allow one to process the digital information more effectively(faster, cheaper, etc.)than one could with the semiconductor-transistor-based integrated circuits. Most of these claims are justly criticized for their insufficient account of requirements imposed by the computer architectures andLSI fabricationtechnologies.

The basic commonfeatures of all Josephson-junction technologies, favorable for their digital applications, are as follows:

Eventhemost ardentproponents of the semiconductordigital technologies agree, however, that quite a serious challenge for them has come from the superconductor integrated circuitsbased on the Josephson effect.(For an excellent introduction to the effect, as well as to the superconductor electronics as a whole, see [1].)

i) Effective impedance Ref of a Josephson junction as a waveform generator canbereadily adjusted to that（p)of the superconducting microstrip line (typically p = 10 Ω). Such lines, with their verylow attenuation and dispersion, allow one to pass picosecond waveforms for distances well exceeding the typical chip size [2], with a low crosstalk. As a consequence,

Manuscript received August 31,1990; revised November 7,1990. This conductivityProblemunder Grant42.

IEEELog Number9042305.

The authors are with the Department of Physics, Moscow State University，Moscow,119899 GSP, USSR.

i) The signal voltage amplitude V in the Josephson junction circuitsdoesnotexceedthevalue2△(O)/eestablishedbythe energy gap △(T) and equals ～ 3 mV for the traditional low-T superconductors (we willdiscuss prospects arising from the a result, the power P = V²/Rep dissipated by a Josephson onemicrowatt. Hence theproblemof theheatremovalfrom VLSI circuits is either trivial or at least quite solvable. This fact leads to thepossibilityof the closepackaging of the superconductor-circuit chips，with the corresponding decrease of time delaysfortheinterchipcommunication.

iii)Intrinsic switching speed of the Josephson junction is also veryhigh, typicallyfewpicoseconds(switchingdelays aslow as 1.5 ps have been demonstrated recently [3]).

iv)Lastly, theJosephson junction fabrication technologies are considerablysimpler than those of thepresent-day semiconductor (both Si and GaAs) transistors with similar design rules. Physical limits of the junction size (a ≤ 0.1 μm) are also close tothose of the semiconductor transistors and can hardlybe regarded as a serious problem at the present-day patterning techniques.

Small wonder, then, that the famous project of the IBM Corporation aimed at creationof aprototypeJosephson-junction computer attracted somuchattentionin the1970's andearly 1980's(for adetaileddescriptionof theproject thereader is referred to the specialissue of IBMJ. Res. Devel.[4]; several important results have been reported later [5],[6]; see also [7]). When the attemptwas eventually droppedinlate1983, the news produced a major sensation in the electronics world.

Now, after a fewyears we believe to have abasically clear view of the mainreasons for this failure. Most important, a need in liquid-helium cooling of thewhole systemwasnot the main reason. Infact, modernrefrigerationtechniquesdojustifycommercial productioneven of instruments likeSQUID's[8]and reflectometers[9]whichuse verysimple superconductor IC chips with just a fewJosephson junctions. For possibleLSI/VLSI circuits the refrigeration costs would be far from being the major concern.

The first real drawback of the IBM project was utilization of

<!-- image -->

(d)

Fig.1. The simplest stage of the Josephson junction logics. (a) Equivalent circuit and schemes of its operation when using (b) an underdamped and (c), (d) overdamped junction. Plots in Fig.1(d) and all similar plots below were model (β。= 1) of the junctions [11] using the PSCAN program [34]. Inputs obtainedbynumerical simulation of the circuit dynamicswithin theRSJ and outputs of the circuits were supposed to be connected to the standard RSFQ buffer stages (see below).

""soft'' superconductors like lead alloys. The temperature recycling of the devicesbetween300K and 4.2K leads toagradual degradation ofultrathin (2-3nm)oxide layers usedas the tunnel barriers in the Josephson junctions (because of recrystallization of theelectrodefilms)andeventuallyto anunacceptablechange of their parameters. Despite a drastic improvement of such materials achieved in the course of theIBM project, they have

The second, and probably the main, reason for the IBM The superconducting technologies still lack a practical transistor, and should use active two-terminal devices instead. Fig. 1(a) shows a simplifiedbutconceptually correctversion of the simplest logic gate, the buffer stage, used in the IBM-type logics. It damped and thus exhibits a hysteretic dc I-V curve (Fig.1(b), biased by a dc current I, slightly less than its critical value I. Initially the junction is in its superconducting state (V= O, point "0"' in Fig. 1(b)). An arriving signal current In drives the total junction current beyond Ie, and induces its switching to its resistive state "1' with V # 0, so that a considerable part Iout of the current is steered into the load R，(typically, through the microstripline with the wave resistance p=R);thelatter currentservesasanoutputsignal.(Inmostimplementedversions of this logic[22], the current In is also used to suppress I. simultaneously, but this fact changes nothing essential in our cess, which can be very fast (few picoseconds).

- i）The necessary supply of power per gate is well beyond that of the signal which can be produced by a similar gate. Thus the clock signals should be generated externally, so that the latching circuits are restricted to external global timing. As aresult, their flexibility for system design is rather limited (see, e. g., [10]).
- ii）A close limitation of the clock frequency of a latching logic comes from another source, an undesirable effect of the junctionswitching to the oppositeresistivebranchof its symmetrical I-V curve (Fig.1(b)) during the decrease of the supply current. This so-called punch-through effect becomes noticeable at RFsupplyfrequencies of the order of 1GHzfor typical Josephson-junction parameters (for details, see, e. g., sec. 5.3 of the monograph [11]).
- i)Apracticalgeneration of thenecessaryrf supplypresents rather a problem. In fact, its current amplitude per gate should be of the order of the criticalcurrent Ic, whichcannot be made less than～100μAin order toensure operation stability with respect to the thermal fluctuations[1],[11](see also Appendix 3). Thus, for a chip containing, say 10° gates, one would need therf currentwith the amplitude～100A and sourceresistance ~ 10-4 Ω. The only apparent way to induce RF currents so high is their on-chip or on-board transformation using special superconducting thin-film structures;the upper frequency of such transformers canbe hardlyraisedbeyond afewgigahertz because of their intrinsicresonance problems [12].

Thus there have been no prospects found to increase clock frequencies of thelatching-logiccircuits beyond afewgigahertz. This speed is higher but comparable to those of the fastest GaAs digitalcircuits whichdonotrequire thehelium refrigeration (see, e. g.,[13]). This marginal advantage was found insufficient for a massive transfer to a completely new technology, and this was presumably the major reason to discontinue thelarge-scale IBM effort (the latchinglogics are also responsible for other technical problems, like a poor isolation of the logic gates).

This discouraging decision, however, has not terminated work on the Josephson-junction computing in other laboratories, and wecanclaimthatsince1983bothmajorproblemsoutlined abovehavebeensolvedinprinciple.

ThefirstcontributionhascomefromJapan. Severallaboratories including those of Fujitsu, Hitachi, NEC, and ETL united improvetheJosephson-junctionfabricationtechnologyusing niobiumrather thantheleadalloys as the superconductors, and aluminumoxideinsteadoftheindiumoxideasthetunnelbarrier material. As the result of utilization of these"rigid"materials, the thermal recycling has virtually ceased to be a problem [15]. perfection and make it feasible to fabricate theLSI circuits, in particular digital ones. For example, a 4-bit microprocessor developed by Hitachi [16] is a 2.5-μm design rule 5× 5 mm² chip that contains 8454 Josephson junctions and 9027 resistors. Microprocessors of an almost similar complexityhave alsobeen developed by Fujitsu [17] and ETL [18];moreover, Fujitsu recently announced[19] an 8-bit microprocessor containing about 22 000 Josephson junctions. Memory chips of nearly the same integrationscalehavebeendemonstratedbyNEC[20]andETL [21].

All these circuits, however, are based on the latching logics very similar to thoseemployedin theIBMproject(with some modifications, for a review see[22]). As a result, their operation speed remains low(on the Josephson junction time scale);for example, themaximumclockfrequenciesofallthemicroprocessorsreferredtoabovewerecloseto1GHz. Suchaspeedcan

Note, however, that the reset (the "1"'-→"O"' switching) cannot be achieved by merely turning the signalIinoff;the circuit remains in its "1"' state.(Due to this property, such logicshavebeen nicknamedlatching.）The onlypracticalway to reset the gate to its"O"state is to switch off the bias current I,. In the latching logics, this periodic reset of all gates is achieved by using RF rather than dc current supply of all the gates;this waveform performs also a global synchronization of thewholedevice. Unfortunately，thisoperationmodehassevere drawbacks:

hardly give superconductor digital electronics a decisive advantage over semiconductor technologies.

The purpose of this paper is to review a step toward a drastic increase of theoperation speed of theJosephson junction digital circuits, developed since 1985 in Moscow by a joint team of the MoscowStateUniversity (MSU)and theInstitute ofRadioengeneering and Electronics (IRE). In 1985, Likharev, Mukhanov, and Semenov of MsU suggested [23] an entirely new approach to Josephson junction computing. In this approach, the binary information is presented not by the dc voltage (as in all semiconductor transistor logics, as well as in the superconductor latching logics), but by very short (picosecond)voltage pulses V(t) of a quantized area:

<!-- formula-not-decoded -->

Anessenceof thisideaisthatthesesingle-flux-quantum (SFQ) pulses (1) can be quite naturally generated, reproduced, amplified, memorized，and processed by elementary circuits comprising overdampedJosephson junctions. This unique ability，fully appreciated in some analog devices based on the Josephson effect [11](see also Appendix II), was virtually neglected in the latching logics; moreover, in the latching logic circuits the SFQpulse generation is aninternal reason for the above-mentioned punch-through effect, which limits the operation speed.

By that time it was recognized that the first(`resistive") versionoftheRSFQcircuitrysufferedrathernarrowparameter margins. The second version[25], which used additionalJosephson junctions (rather than the resistors) for the connections, allowed not only a drastic broadening of the margins but also a further increase of operating speed. It was called the rapid single-flux-quantumlogic(tosome extent, in order to save the original abbreviationRSFQ). Since then three test circuits containing the basic components of the new version have demonstrated their workability at clock frequencies in excess of 100 GHz with quite decent parameter margins [26]-[28], despite of a relatively primitive 5-pm(all-Nb) technology used for their fabrication. Numerical simulations show that transfer to a 1-pm technology can increase the speeds beyond the 300-GHz level. Even more important, a self-timing scheme for the RSFQ circuitry，which was suggested simultaneously [29], promises to ofvirtually arbitrarycomplexity.

The first version of the new logic/memory family relied heavily on ohmic resistors for interconnection of the Josephson junctions, and thus was nicknamed the resistive single-fluxquantum (RSFQ) logic [23]. During 1985-1986, the MSU team designedthefirst experimentalchip containing thekeyelements of this version. By summer of 1986, the IRE group fabricated and tested the first samples. Somewhat unexpectedly for the 30 GHz [24], a factor of ～ 30 faster than any latching logic device and afactor of~2faster that anyother digitaldevice of asimilarcomplexitytestedtothatdate.

These developmentsreceivedconsiderablepublicityin the SovietUnionbuthardly any outside of that country. Nevertheless, we believe that a major success in such a big enterprise as bringingpracticalcomputer speeds closetotheterahertzlevel can hardlybe achievedwithout anextended international cooperation/competition. This review paper can be considered as our sincere attempt to attract attention of the international electronic engineering communitytotheseremarkableprospects.

TABLEI THE RSFQ TIME UNIT To (EQUATION (2))ASA FUNCTION OF THE LINEAR SIZE Q OF THE JOSEPHSON JUNCTION FOR THE Nb/AlOXIDE/Nb TECHNOLOGY (FORI。=100 μA)

| Junction size a,μm   |    |   2.5 |   1.250.7 |     |
|----------------------|----|-------|-----------|-----|
| Time unit To, ps      |  4 |     2 |         1 | 0.5 |

The paper is organized to be ready for a piecemeal consumption. To those interested in the basic ideas alone, we recommend reading Section II, which describes the backgrounds of the RSFQ operation, a fewinitial sections of both Sections III (elementary RSFQ cells)and IV(examples of the RSFQ arithmetic), and then Section V (describing the self-timing concept), Section VI (prospects for system development), and concluding Section Vll completely, skipping the Appendixes. On the other hand, the reader who studies thepaper thoroughly will reallybe updated on the problem. In order tokeep the basic narrative uninterrupted, a descriptionof theRSFQcircuit layout, abrief pre-history of the digital single-flux-quantum digital devices, and a discussion of prospects for the high-T。superconductivity are included in the Appendixes.

## I1. ABC's OF THE RSFQ

## A. HandlingtheSFQPulses

Let us repeat that in the RSFQ logic circuits the signals are passed in the form of very short pulses V(t), nominally with the area expressed by (1). In order to fully appreciate this choice, consider again the most elementary circuit shown in Fig.1(a), but now with an overdamped Josephson junction. Fig.1(c) shows the dcI-Vcurve of the junction;in contrast to the underdamped case, the curve is single-valued. It implies that after a current pulse Iin(t)the junction is self-reset again to its original superconducting state.

This is a truth, but not all the truth. Elementary calculations using theJosephson dynamics equations show(see, e. g.,[11]ch. 5) that if the pulse Iin(t) is short enough, there exists a broad range of its amplitude within which the pulse induces a quantized leap of the Josephson phase Φ of the junction: △Φ = 2π; see Fig. 1(d).

This fact can be readily understood starting from the wellknown analogy between the Josephson junction and the pendulum. In this analogy, biasing of the junction with the dc current I, 之 I. corresponds to applying a nearly critical torque to the pendulum, driving it to a position close to the critical angle Φ。= π/2. The short input current pulse is equivalent to a kick that drives the pendulum beyond Φe. If the pendulum is overdamped, the kick results in just one 2π-rotation of the pendulum with its return to the subcritical state.

According to the fundamental phase-to-voltage relation

<!-- formula-not-decoded -->

such a"2π-leap''ofΦ(in the literature, one can also find the corresponds to the SFQ voltage pulse (1) across the junction. Duration of thepulseis close to the characteristictime unit

<!-- formula-not-decoded -->

whereR, istheeffectivenormalresistanceofthejunctionat voltage of the order of Ve, and Ris the active impedance of theelectrodynamicenvironmentasseenbythejunction. TableI

Fig.2. Two overdamped junctions connected by a matched microstrip line. (a)Equivalent circuit and (b) simulation of the circuit dynamics (for I1= Ic2=I, Ref1=Ref2=R, p/R=1, Ib/I=0.8).

<!-- image -->

<!-- image -->

10

Fig.3. SFQ transmission/amplification line. (a) Equivalent circuit and (b) results of the dynamics simulation (for Ibi=0.75Ic, LIei =0.5Φ。）.

<!-- image -->

shows that for decent present-day fabrication technologies (a ~ 1-2 μm) the unit is close to one picosecond, so that the pulse amplitude Vmax = 2V is of the order of 1 mV. (The energy E =IΦ。dissipated during the pulse is independent of a erations; see Appendix 3. The energy is of the order of 2 × 10-19 J for the value Ic= 100 μA typical for the helium-temperature operation.)

Calculations [31] show that if the dc bias current I, is close enough to the criticalvalue Ic, this SFQpulse canbe triggered, in particular, by a similar pulse, with either the nominal or a somewhat smaller amplitude. It means that the circuit shown in Fig 1(a) can reproduce the SFQ pulses, bringing their area to the nominal value (1), i. e., providing voltage gain if necessary. On the other hand, if the input pulse is too weak (say, presents a "noise'' due to parasitic crosstalk between the signal transfer lines)it is not reproduced by the circuit, so that it also serves as anoisediscriminator.

In order to develop a convenient way to look at this process let us recall that according to the Faraday induction law Φ=V, the development of the SFQpulse(1)acrossa two-terminal circuit element can always be considered as aresult(or the ：reason) of it being crossed by a bunch of magnetic field lines carrying\_exactly one magnetic flux quantumΦ。=h/2e=2.07 across an edge junction, it has no other choice than to leave it by crossing all the junctions in turn(flux crossing of the superconductingleads connecting the junctions is forbiddenby theMeissner effect, and small inductances L of the leads make it impossible for the flux to be trapped in the loops of the array). Below, language is more natural than that of the voltage pulses.

Fig.3(a)showsanother keycircuitcomprisingseveral Josephson junctions connected in parallel by superconducting strips of a relativelylowinductance L～Φo/Ic, and dccurrent-biased to their precritical state(Ip&lt;I). Let the 2π-leap of the Josephson phase in theleft junction J1 of this array be inducedby the input pulse. Calculations show that theresulting

<!-- image -->

10

Fig.4. The SFQ pulse splitter. (a) equivalent circuit.(b)Results of the dynamics simulation (for I2=I3=I，I=1.41, Ibi=0.751c, L2= L3= 0.6Φ。/I), and (c) notation [30].

SFQ pulse developed across J1 will necessarily trigger the 2 π-leap in J2, and this process will continue until the pulse is reproduced at the right edge of the array (Fig.3(b)).

Coming back to the circuit shown in Fig.3(a), we have seen that it is capable of transferringtheSFQpulses witha small time delay of order of to(Fig.3(b)). The circuit can also amplify the pulses (more exactly, provide their current and Two important remarks should be made here. First, the load power gain). For that, critical currents of the junctions (and the (R, in Fig.1(a) should not necessarily be an ohmic resistor; correspondingdcbias currents)shouldgrowin thedirection of moretypically，anothersimilarjunctionservesasaloadin the the pulse propagation (Ic1 &lt; I2 &lt;···), with the proportional RSFQ circuits (Fig. 2(a). Second, these junctions need not decrease of the inductances (L1 &gt; L2 &gt; ·.·). For example, necessarily be close to each other; they can be connected by a an exponential growth of I. by a factor of √2 per stage provides quite a high current gain together with large (±30%) ate wave impedance p = R,(Fig.2(b)). cient.

An evident generalization of the circuit(Fig.4(a))provides splitting of the pulse, i. e., reproduction of the input pulse A at eachofitstwooutputsBandC, withoutadecreaseofthepulse voltageamplitude.

These simplest circuits are, however, not always practical:in

Fig. 5. The simplest RSFQ buffer stage. (a) Equivalent circuit and (b), (c) its dynamics (for I = 1.4Ic2, I, = 0.71c2, and (d) notation [25].

<!-- image -->

particular, inputs andoutputsinFigs.1-3arereciprocal, sothat the circuits cannot be used for isolation. Nevertheless, a slight modification yields a decent buffer stage (Fig.5(a)). In this circuit, critical current of thejunction J2 is somewhat smaller than that of the junction J1. Now, if the initial pulse arrives from the circuit input A, it is applied to J1 alone, and induces the 2 π-leap of the Josephson phase in J1, leaving the phase across J2 virtually undisturbed (Fig. 5(b)). As a consequence, the SFQ pulse is reproduced and passed to the output terminal B.

On the contrary, if a pulse arrives from the latter terminal, it induces a current pulse in both J1 and J2. As I2 &lt; Ic, the junction J2 reaches its resistive state earlier, and performs the 2 π-leap of its phase, preventing J1 from the similar leap. Hence voltage across J1 remains close to zero, which means that the SFQ pulse does not reach the input terminal A (Fig.5(c)). Fig.6 shows a generalization of this circuit—-the"confluence buffer'that permits channeling of the SFQpulses passing from auxiliary junctions J3 and J4 protect the inputs from penetration both its inputs A and B to the single output C. Here, the of the SFQpulse from outputC or anotherinput. Anegative feature of this simple circuitis thatit can provide only one output pulse if the input pulses arrive too close in time.

## B. SFQFlip-Flops:StoringtheSingleFluxQuanta

Fig.7 shows another key component of virtually all RSFQ circuits. It is essentially the celebrated superconducting quantum interferometer (sometimes called the dc SQUID）using two similar Josephson junctions (I3 = Ic4 = I). If the inductance L of theinterferometeris chosen tomake itsbasicparameter

<!-- image -->

Fig. 6. Confluence buffer. (a) Equivalent circuit.(b) Its dynamics simula(c) tion(forl3=I4=les=1，I=I2=1.41c, Ib=1.41，Ib2= 0.71, L=0.5Φ。/1), and (c) notation.

<!-- image -->

Fig. 7. SFQ RS flip-fop (used typically as the DRO register cell). (a) The equivalent circuit. (b)Dynamics (for 1=I2=I,13=I4=1.41I I=I, L =1.25Φ。/I)）.(c) The Moore (state-transition)diagram.(d) Notation of the circuit[25]. Josephson junctions that perform the 2π-leaps of their phase during particular state transitions are indicated in parentheses in the Moore diagram. Point denotes the initial state which is established after turning on the dcbias.

<!-- image -->

Fig.8. SFQ T flip-flop.(a) Equivalent circuit. (b)Dynamics (for parameters similar to those in Fig. 7).(c) The Moore diagram. (d) Notation [27].

<!-- image -->

Fig.9. An elementary cell of the RSFQ circuits.(a) The general scheme. (b) Signal consequence.

<!-- image -->

pulses from its single input A. Each pulse is split (c. f., Fig. 4(a)) and injected to both arms of the interferometer, so that it always triggers thecircuit switching to the opposite state. An important auxiliary component of the circuit is the resistor R between the middle point of the interferometer inductance and the ground. It somewhat prolongs the switching process and substantiallywidensthe parameter margins. Experimentally measured margins for the dc bias current I, were as wide as ±30% [26] for this circuit, in a good agreement with numerical simulations.

## C. RSFQBasicConvention:PresentationofBits

The above physical background enables one to describe the general idea of storing, passing, and processing the binary informationin theRSFQ circuitry. AnyRSFQ circuit consists of elementary (logic/memory） cells, operating as Fig.9 shows. The cell isfed by the SFQpulses that can arrive from one or several signal lines, S,···, Sn, and the clock (timing）line T. (For the beginning, it is easier to think about the T pulses as arrivingperiodicallyin time, althoughwewillseelater that their periodicityis anexceptionrather than a rule in practicalRSFQ circuits.)

Generally, each cell can have two or more stable states (cf., the flip-flop states described above)and hence presents a finitestate machine from the point of view of general computer science[32]. Eachclockpulsemarks aboundarybetween two adjacent clock periods by setting the cell intoits"o"'state. During the new period, an SFQ pulse can arrive (or not arrive) at each of the cell inputs S; (Fig. 9(b)), changing the cell state. Thisistherightmomentfor formulation of theRSFQBasic Convention:

ArrivaloftheSFQpulsetoaterminalS;duringthe currentclockperiodhasameaningofthebinary"1'value ofthesignalS，whileabsenceofthepulseduringthisperiod isunderstoodasthebinary"O'valueofthissignal.

One can see that for theSFQpulses the circuitworks exactly as a standard RS fip-flop (trigger). The SFQ pulses can be trapped by this circuit, so that the information about their arrival there can be conveniently stored there, and released when necessaryin the similarphysicalform.

Note that the conventiondoesnotrequire an exacttime coincidence of theSFQpulses (itwouldbe impracticalbecause of their picosecond duration). Moreover, neither a certain time sequence of the various input signals is needed;the only requirement of the Basic Convention is that each pulse denoting the binary"1"'arrives some time during the clock period. Each pulseeitherchanigesordoesnotchangetheinternalstateofthe cell, but it does not produce anyimmediate reaction at its output terminal(s) Sou. Only the clock pulse T is allowed to develop the output pulse(s) Sout corresponding to the internal state of the cell, predetermined by the input signal pulses which arrived during this period. The same clock pulse terminates the clockperiod by resetting the cell. Thus an elementary cell of the RSFQfamilyis equivalent to a usual asynchronous logic circuit coupled with a register (flip-flop) storing its output bit(s) until ttheendoftheclockperiod.

(d)

close to 10, and the dc bias current I, is close to 0.8 Ic, the circuit has two symmetric stable stationary states that differ by the directionof thepersistent currentI,±Φo/2Lcirculating in the loop. In the ·'magnetic' language, one of these states superconducting loop of the interferometer. Let us suppose that the persistent current is circulating counterclockwise (binary 1 ~d1 + 7/91 =1 :u 91 m dn suns  eos .0, now the SFQ pulse(possibly, with a somewhat decreased amplitude) arrives at the input S, it induces the 2π-leap in J3, but not in J2, which carried a lower dc current. As a result of the leap, the cell is switched to its opposite"1"' state with the clockwise circulation of the persistent current. It is evident that now the reset (the "1"'→"O"' switching) can be triggered by the SFQ pulse arriving at the R terminal. Simultaneously, an SFQ pulse V(t)is developed across J4, which can serve as an output signal F. The auxiliary junctions J1 and J2 defend the SFQ pulse sourcesfromthebackreactionof theinterferometerin thecase of a "wrong"' signal, for example, of the S pulse arriving during the "1"' state. In this case, junction J2 (rather than J3) switches; in the "magnetic'' language, the incoming single flux ter loop is unable to accept it.

Fig.8 shows the SFQ analog of the T flip-flop (i. e., a single bit stage of the binary counter). This circuit isfed by the input

III. BASICELEMENTARY CELLS

<!-- image -->

## A. ORCell

In order tounderstand why the combinedlogic/memory circuits are used as the elementary cells of the RSFQ family, let us have alook at how simply these cells canbe composedfrom the basic components considered in Section II-A and -B.

One can be readily convinced that within theRSFQBasic Convention, the circuit does perform the ""timed'' oR function, with the output delayed until the end of the clock period. It is also useful now to have one more glance of Fig. 9 and the accompanyingdescription of operationof thearbitraryRSFQ cell. The reader will probably agree that this type of operation is not something artificial butrather the mostnatural utilization of the unique dynamics of the Josephson junction circuits.

For example, in order to get the 2-input OR cell (Fig. 10(a) it is enough to unite the confluence buffer (Fig.6(a))with the RS flip-flop (Fig. 7(a)). When the SFQ pulse arrives at one of the signal inputs （A, B)it is reproduced (normalized) by the buffer stage and then is fed into the input of the flip-flop, either inducing its "O"→"1"' switching (if it is the first signal pulse during the given clock period) or having no effect on its internal state.(If the switching has been already triggered by the preceding signal pulse, the signal pulse induces the 2π-leap of the phase in the junction J5.)Even if the signal pulses (occasionally) coincide in time, theirfinaleffect on the circuit is similar tothat of a single pulse. Note also that noSFQpulse appears at the circuit output during the clock period; the output can appear (if at least one signal has arrived during the period) only as a result of the circuit being reset by the clock pulse arriving to the T input and thus terminating the clock period.

## B. DROandNDRO/DRORegisterCells

It is evident that the RS flip-flop (Fig.7) itself presents a latch, i. e., asingle-bitcellof a"Dregister'withdestructive

Fig. 11. NDRO/DRO register cell.(a) The equivalent circuit. (b) Dynamics.(c)Moore diagram.(d)Notation of the cell[29]. TheleftpartofFig. 11(b)illustrates the WRITEoperation，while itsmiddlepart, the NDRO operation, and right part, the DRO operation of the cell.

<!-- image -->

read-out (DRO), if its S input is fed with the signal pulses, while the R input is fed with the clock pulses. A ready modification (Fig. 11) turns this circuit into a cell of an"N register" permitting the nondestructive read-out (NDRO) as well.

The main new feature here is the addition of a new pair of JosephsonjunctionsJ2, J4connectedinseriestoamiddlepoint of the two-junction interferometer (J1, J3, L2, L3). Critical current of the additional junctionJ2is relativelylow, sothat the addition does notinfluence statics and dynamics of the interferometerqualitatively. Thisis whythe celloperates as the simple DRO register, when its inputs A and T are fed by the signal and clock SFQ pulses, respectively (in this mode the output bit appears at the terminal F).

The effect of the cell state on the junction pair J2, J4is, on the contrary, quite considerable. In the"1''state, with its clockwise circulationofthepersistentcurrent, thenetphasedropacross each junction of the pair is close to π/2, so that junctionJ4 is in a precritical state (Φ;≥ π /2, I; = Ic). In this case, arrival of anSFQpulse from the terminalBinduces two successive 2π-leaps (first in J4 and then J2 junctions), and the SFQ pulse is reproduced at theNDROoutput terminalP. It is important that this switching does not change the internal state of the cell (Fig. 11(b)). In the opposite ""0"' state, the junctions J2, J4 are far from their critical state, and the NDRO-initiating pulse B induces the 2π-leap in the junction J6rather than in any of J2, J4.

Fig.12. RSFQ inverter. (a) The equivalent circuit.(b) Dynamics for A = 1 and A = 0. (c) Moore diagram.

<!-- image -->

As a result, the zero output P again mirrors the contents of the register.

Note that if thepulseBis considered as a signal rather than the NDRO clock, the same circuit performs the asynchronous single-bit multiplication (in other words, the AND function)provided that theBpulse arrives later thanA.

## C. Inverter

Fig. 12 shows another modification of the basic flip-flop, which leads to a cell performing the signal inversion (NOT function), one of the most difficult tasks in any Josephson junction digital technology(cf.,[4],[6], and[22]). Here，the additional JosephsonjunctionJ5is insertedin series into the mainquantizingloop(J3, J4, J5, L5)ofthecell. Criticalcurrent of this additional junction is relatively large, so that the SFQ signalpulseAinducesa2π-leapinJ4rather thaninJ5. Asa consequence, the resulting "o"→"1"' switching of the cell produces no considerable signal across the output terminal F. The clock pulse T induces the 2-leap in J2 (but not in J5, because of its larger I), and there is no output pulse again. However, the same clock pulse, after a small time delay by the circuit L3, R, L2, arrives at the terminal B and resets the cell to its"0'state by inducing the2π-leap in J3.

On the other hand, if there were no signal pulse during the operation period, and the cell remains in its"O''state until the clock pulse T, the latter pulse finds the persistent currentflowing counterclockwise, and the junction J5，in its subcritical state. Hence the 2π-leap is induced in this junction rather than J2, and an SFQpulseis formed at the output terminalF.

Fig. 13. Exclusive oR cell. (a) The equivalent circuit.(b) Dynamics for {A =1, B=1} and {A =1，B=0}.(c)The Moore diagram.(d) Notation[30].

<!-- image -->

## D. XORCell

One morefruitfulway to modify the basic SFQflip-flop is to split one of its arms. In particular, such a splitting allows one to perform the two-input exclusive or (xor) function (Fig. 13). Due to the splitting of the basic interferometer, the cell can be consideredasconsistingoftwoquantizingloops (J1, J3, L1, J5, J7, and J2, J4, L2, J5, J7). As a consequence, the cell has three stable static states. One of them ("oo") can be interpreted as that without trapped flux quanta, and two others the loops containing junction J1 or J2, respectively. (Simultaneous trapping of two flux quanta, i. e.，the "11''state, is unstableduetotheinteractionof thecellsvia thecommon junction J5.)Dynamics of the cell are very similar to that of the elementary flip-flop (see Fig.13(b)and (c)).

## E. OR-ANDCell

We have seen that the cell shown in Fig.11(a) can be used as the AND cell only under certain conditions. In order to get rid of this limitation, another AND cell would be quite useful. As an exception, this circuit does not require its own quantizing interferometer but can use those of the input cells, so that it is convenient to combine those to form one circuit performing a more generalfunction.

Fig.14(a) shows an example [34] of such a combined cell that performstheoR-ANDfunction. Heretheelements J5, J6, L1, L2, J7canbe considered asforming theANDcircuit

Fig. 14. Single-bit cell performing the generalized function F = (A + B) · (C + D). (a) Equivalent circuit. (b) Dynamics for {A = B = 1, C = D =0} and {A=C=1, B=D=0}.(c) Notation [34].

<!-- image -->

(cf., Fig. 6(a)), and the remainder as a couple of or cells similar to that shown in Fig.10(a). If both these oR cells are in their "0" state by the end of the clock period (which is possible only if A = B = C = D = O), the clock pulse T switches junctions J1 and J2, with no appreciable effect on the output F. If one of the oR cells (say, that with junction J3)is in its "1"' state, then J3 (rather than J1) is switched by T, so that the SFQ pulse is applied to junctionsJ5and J7connected in series. Theformer of these junctions has a smaller critical current than the latter one, so that J5 is switched, and there is no output pulse again. The only case when J7 switches and produces the SFQ pulse at the output F is when both oR cells are in their'1""state, so that bothJ3andJ4are switchedsimultaneouslyby theclockpulse T.(In this case the pulse currents, injected into J7 through L1 and L2, sum up and exceed the critical current of this junction.)

Note that in contrast to other RSFQ cells, an exact time coincidence of the current pulses in L1 and L2is essential in this circuit. However, this does not violate the RSFQ Basic Convention because these pulses are confinedinside the cell; the input pulses A, B, C, D are free of this requirement. Numerical simulations show that thenecessary coincidence is achieved inside a wide parameter window (the critical current margins can be in excess of±30%).

Itis straightforwardtomodifythiscircuit by changingeither one oR cellorboth of themfor cellsperformingotherfunctions F and F2; in this case the combined cell will perform the function F·F2. As the simplest extreme, a "bare"AND cell is

Fig.15. Single-bit full adder.(a) The equivalent circuit.(b) Dynamics for {A =B=1, C=0} and{A=B=C=1}.(c) Notation[25].

<!-- image -->

readily possible (with the DRO register cells in the both inputs), buttoohardware-consuming.

## F. Single-BitFullAdder

Thelast elementary circuit we will need for our further discussion is the single-bit full adder (FA). Generally speaking, it can be readily composed in the usual way (see, e. g.,[74]) from two xOR cells, two AND cells and an OR cell. Fig. 15(a)

Thereis another example ofmodificationof anelement withrestrictions convention. The asynchronous confluence buffer, as mentioned above, can generateone ortwo outputpulses dependingon the time shiftbetweenits twoinput pulses, thusviolating theRSFQbasic convention. Moreover, there is a nonvanishing transition range of these shifts where confluence buffer operates improperly. To eliminate time shifts of this range one can use an element that consists of twoclockedflip-flopsfollowedby the confluence buffer. Similar to the OR-AND cell, the same clock pulse is used for reading out both theflip-flops, ensuring the fixed delaybetween output pulses and hence the correct operation of the confluence buffer. This does not mean that one has to add newflip-flops to all confluence buffers. Usually it is sufficient

TABLE II PARAMETERS OF THE BASIC ELEMENTARY CELLS AND SOME AUXILIARY CIRCUITS OF THERSFQFAMILY

| Circuit                                   | Time delay, 8/T0      | Number of JJ          | Area, A/a²            | Margins, ±%           |
|-------------------------------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| 1. Elementary cells                        | 1. Elementary cells    | 1. Elementary cells    | 1. Elementary cells    | 1. Elementary cells    |
| DRO register                              | 2                     | 4                     | 500                   | 30                    |
| OR cell                                   | 3                     | 9                     | 006                   | 30                    |
| AND cell                                  | 1                     | 3                     | 400                   | 30                    |
| NDRO/DRO register                         | 2                     | 6                     | 700                   | 20                    |
| Inverter                                  | 3                     | 5                     | 580                   | 25                    |
| XOR cell                                  | 3                     | 7                     | 800                   |                       |
| 1-bit full adder                          | 8                     | 22                    | 2500                  | 20                    |
| 1-bit stage of the serial memory Register | 1                     | 2                     | 250                   | 30                    |
| I1. Auxiliary circuits                     | I1. Auxiliary circuits | I1. Auxiliary circuits | I1. Auxiliary circuits | I1. Auxiliary circuits |
| Buffer stage                              | 1                     | 2                     | 200                   | 50                    |
| Split buffer                              | 1                     | 1                     | 210                   | 50                    |
| Confluence buffer                         | 2                     | 5                     | 570                   | 30                    |
| Coincidence junction                      | 2                     | 3                     | 50                    | 35                    |
| DC/SFQ converter                          | 2                     | 2                     | 200                   | 40                    |
| SFQ/dcconverter                           | a                     | 6                     | 680                   | 30                    |
| 1-bit multiplexer                         | 1                     | 10                    | 1100                  |                       |
| 1-bit demultiplexer                       | 1                     | 14                    | 1300                  | b                     |

shows the result of our first attempt [25] to develop a simpler adder, while Fig.15(b) shows results of numerical simulation of its operation for two and three input pulses.

(J17, L2, J18, J19), with two stable states each. The former interferometer is fed by the signal pulses A, B, and C through 8). As a result, a correct sum bit pulse S is formed across junction J16 under the action of the clock pulse T (Fig.15(b)). It is easy to check that a correct carry bit pulse is being formed in the point G. One cannot use it, however, because the sum bit pulse also penetrates there. The remaining part of the adder serves to cut off this parasitic sum signal. If S = O and C' = 1, the genuine carry bit pulse switches the persistent currentintheloopL2tofiowcounterclockwise, andisthus correctly read out to the output C'by the clock pulse T. On the contrary，if S =1 and C'=1，the clock signal, after some delay, also arrives at the opposite arm of the interferometer through the buffer circuit J4, J20, L5. By switching the junction J19 this delayed pulse resets theinterferometer to its proper state (Fig.15(b)). As a reward for these complications, the correct carrybit pulse is formed at the terminalC'witha considerable delay after the clock pulse T. We will see that this delay enables one to use this cell as avery simple serial adder.

The cell has two quantizing loops (J13, L1, J15, J16) and the confluence buffers, and operates as a T flip-flop (cf., Fig.

We are not, however, quite happy with this circuit. Firstly，it does not tolerate an occasional coincidence of the input pulses (cf., Fig. 6 and its discussion). Secondly, its parameter margins are rather narrow. A better design is in progress presently.

## G. ParametersoftheElementaryCells

The very concept of the elementary cells(see Fig.9 and its discussion) supposes that the time delay between an input and output of thecellcannot exceed theclockperiodr. For a particular cell there is of course a minimum value 8 of the periodfor which the celloperates correctly. TableIIshows thisvalue for theelementarycellsconsideredabove;8is expressed in the natural units To;for the standard "niobium'

TABLE III ESTIMATES OF BASIC PARAMETERS OF 32 × 32-BIT FIXED-POINT MULTIPLIERSBASED ONVARIOUSDIGITALCIRCUITTECHNOLOGIES[29]

| Circuit type; fabrication technology (design rules)   | Integrationscale (Josephson/p-n junctions per chip)   |   Productivity (billion operations per second) |   Time delay (ns) |
|-------------------------------------------------------|-------------------------------------------------------|------------------------------------------------|-------------------|
| Parallel pipelined; Si-MOS (1.0μm)                    | 200000                                                |                                           0.2  |               150 |
| Parallel; GaAs (0.5 μm)                               | 100000                                                |                                           0.15 |                 6 |
| Parallel; JJ latching (2.5 μm)                        | 70000                                                 |                                           0.5  |                 2 |
| Serial; JJRSFQ (2.5 μm)                               | 1 500                                                 |                                           0.5  |                 2 |
| Parallel- pipelined; JJRSFQ (2.5 μm)                  | 40000                                                 |                                          30    |                 2 |

technology this unit is directlydetermined by thelinear sizea of thejunction(whichpracticallycoincideswithminimumfeature size); see Table I.

Table II also gives an estimate of the cell areaA in units of a² and shows the total number of the Josephson junctions in the cell (these numbers can serve as a measure of the cell complexity).

Several auxiliary circuits(both considered above and to be discussed in Sec. V) are also listed in Table II. For them,0 shouldbe understoodasanexplicit time delaybetween theinput andoutputSFQpulses.

The same table shows parameter margins. They were calculated usingthe operationalrangeoptionof thePSCANprogram [34]as a maximumrelativevariation of thejunction area, which does not lead to misfunctioning of the circuit.(Other possible definitions of themarginslead tonearly similar values.) One can see that the RSFQ circuit margins are not less than those of the modern latching gates (see, e. g., [22]).

## IV. SOMELOGICANDARITHMETICBLOCKS

## A. TheSimplestSerialBlocks

Now it is straightforward to use the single-bit cells described in Sec. Ill for building logic and arithmetic blocks performing either serial or parallel processing of multibit data, so that we will consider only a few examples of these.(For the sake of convenience we will leave discussion of the key problem of timing until the next section;here we will imagine that the necessary clock pulses arrive in due time from the environment of the block.)

First of all, some logic/arithmetic operations with multibit numbers can be performed using just one single-bit cell. For example, consider an operation where anybit of theresult is a function of the corresponding bits of the input numbers (say，the n-bit or function). One can perform this operation in series by consequently feeding the input bits into the proper single-bit cell and picking up one single bit of the result F after each clock pulse (Fig. 16(a)).

Thenextexampleistheserialadditionoftwomultibit

Fig. 16. The simplest serial blocks for (a) elementary logic operations, and (b)summation of the multibit numbers.

<!-- image -->

numbers A and B, where each single-bit addition requires not only current signal bits A; and B, but also the carry bit C; = C'-1 produced during the preceding clock period. This problem is, however, readily solved by the circuit shown in Fig. 16(b). (One does not need to insert any time delay into the carry bit line, because the Ci-1 pulse is generated with some delay after the clock pulse T, i. e., arrives to the input terminal C safely after thebeginning of thenextclockperiod.)

## B. SerialALU

The same approach can be applied to the design of more complex serialdevices, in particular, arithmetic/logic units (ALU). Most instructions of a typical ALU can be fulfilled in a serialway, startingfromtheleastsignificantbits.(Animportant exception arerotate-typeinstructions;inRSFQcircuits they can be readily fulfilled using ring registers; see Section V.)

This is why the serial ALU can be designed in away similar to the serial adder (Fig.16(b))with the exception that the single-bit cell shouldperform afunction controlledby the instruction code. Such a cell can be composed of the elementary cells discussed in Sec. IⅢI (see, e. g.,[22]), supplemented by switching(multiplexer/demultiplexer) circuits. Such switching can be performed by a combination of the cells N (Fig.11) and split/confluence buffers (Figs. 4 and 6). The special multiplexer and demultiplexer circuits, shown in Fig. 17, are, however, more convenient. Each of these very similar circuits is controlled by S/Rpulses of the instruction code, which can switch the state of the symmetric interferometer J7, J3, L, J4, J8 and thus establish what arm of it (right or left)becomes transparent for the signal SFQ pulses. In the multiplexer (Fig.17(a)) the signal pulses A and B are independent, and are channeled to the general outputF through the confluencebuffer J11-J14. In the demultiplexer (Fig. 17(c)) the single input pulse A is passed tooneoftheoutputsF1, F2.

## C. SerialMultiplier

Multiplication of n-bit numbers requires more complex circuits with the number of the elementary cells scalingeither as n, or even as n². Fig. 18(a) shows a possible structure of the block SM performing the serial multiplication of numbers A and B. The block uses three types of the single-bit elementary cells: DRO sells D (i. e., RS flip-flops, Fig. 7), DRO/NDRO sells N (Fig.11), and full adders FA·(Fig. 15) operating as the serial adders (cf., Fig. 16(b)). Operation of the block is controlled by two sequences ("trains")of the clock pulses, TA and TB(Fig. 18(b)).

The operation is started by a train of n clock pulses TB arriving to all cells N. The train induces sequential loading of the B bits into the shift register formed by these cells. Then the train TA starts, which induces a similar loading of the bits of A intothe shift register formedby theDcells. The latter train induces alsoa simultaneousbackwardmotionof thebitsalong the string of the full adders FA.

One can be readily convinced that in the end of each operation

Fig.17. RSFQ pulse switches.(a) Multiplexer. (b) Demultiplexer. (c), (d) Theirfunctional schemes[34].

<!-- image -->

SM

Fig. 18. Serial RSFQ multiplier.(a) The block circuit and (b) pulse

<!-- image -->

correct consequent bit of the 2n-bit productA·B at its output terminal P.(In fact, all the partial single-bit multiplications are performed by the N cells, while the serial adders FA merely sum up all the partial products.)

Note that the whole multiplication takes 2n clock periods (loading of the next B can be fulflled during last n periods of the previous multiplication cycle; see Fig. 18(b)). A numerical estimate of the time necessary for the operation will be presented below (Table IⅢI).

## D. SerialDivider

Fig. 19(b) shows an arithmetic block D; for serial calculation of the n-bit reciprocal F = 1/M (1/2&lt; M&lt; 1) via k =

Fig.19. Serial divider. (a) The block circuit.(b) Structure of the block D) [28].

<!-- image -->

log2 n iterations using the well-known recipe:

<!-- formula-not-decoded -->

starting with F。= 2 -M (each iteration doubles the number of correct bits). The block consists of two serial multipliers SM (Fig.16(a)) and a simple device "2-"calculating the difference between 2 and the input number.(The latter device consists of two single-bit cells, the inverter and the full adder.） The"pipeline''structure of theblock allows the cycletime of oneiteration tobesomewhatlessthanthatrequiredfortwomultiplications.

The complete divider canbe arranged intwodifferentways; the simplest one is to link the Fj-1 and F; terminals of a single while the other one is to use a pipeline structure (Fig.19(a) composed of log2 n blocks D; with increasing bit lengths (n; = 2j). The total division time for these two cases is ~ 2n· log2 n and 4n clock periods, respectively.

## E. ParallelMultiplier

Productivity ofcalculations canbeincreased drasticallyusing parallel-pipeline single-bit units. Fig. 20 shows an example of such a device, a multiplier of two n-bit numbers A and B(in our example, n = 4). It presents a two-dimensional array (Fig. 20(a) of single-bit multiplication units M shown in Fig.20(b). (Most of the units do not get a complete set of input signals and can be internally simplified accordingly;in Fig.20(a) one can seetwotypesofthesimplifiedunits, thehalf-adderHand the DRO register cellsD.)Note that the unit M is a copy of a single column of the serial multiplier (Fig.18(a);the only difference is a way of connection of the units and their timing.

Fig. 20. Parallel RSFQ multiplier.(a) General structure. (b) That of its single cell. (c) Notation of the cell [28].

<!-- image -->

the other hand, a parallel block requires N x n² cells and produces M X n bits per period.

Nevertheless, one may need some blocks that escape from this classification. Forexample，onecanincreasethespeedof the multiplier similar to that shown in Fig. 18(a) by using parallel m-bit multipliers shown in Fig. 20(a) (with m &lt; n) instead of the single-bit multipliers. (Of course, the register cells D and fulladdersFAshouldberedesignedcorrespondingly.)Sucha 1device would require a factor of m more junctions, but would operate~m times faster.

## V. SELF-TIMING

## A. ElementaryCell Timing

Timing (synchronization) of the digital systems has always been a special computer science discipline (see, e. g.,[10]). This disciplinebecomesofevenlarger importanceforthesystems being designed to operate at ultrahigh clock frequencies (say, beyond 100 GHz). The RSFQ logic is apparently the pioneer at this frontier, so that its timing deserves special attention.

The first fact to be fully appreciated is that the external (global)synchronizationofanLSIcircuitatsuchfrequencies is impractical. In fact, it is hardly possible to debug the globalsynchronizationcircuitlayoutofminorimperfections

If the clock pulses are fed into the vertical columns of the structure consequently，fromright to theleft(forimplementation of that, see the next section), the signal bit front is moving from left to the right, being processed simultaneously. If fed in parallel by all 2n bits of new operands （A, B) each clock product P = A·B during one period, although a full processing of each specific pair of the operands takes 2n + 1 clock periods.

## F. Parallel-SerialBlocks

Theabove examples demonstrate thatthe serial blocks have the following common features: they consist of N× n elementary cells andproduce M outputbits during each clock period, independent ofn andgenerallynot muchlarger than unity. On

Fig.21. The simplest clock distribution systems for (a) counterflow and (b) concurrent flow of the clock and signalwaves ina one-dimensionalRSFQ circuit. 7. is the clock pulse delay, while  is the cell delay.

<!-- image -->

producing pulse delays of the order of 1 ps. But at, say,300 GHz clock frequency, such delays of the global clock signal are as a rule unpermissible!This is why theRSFQ-type superfast devices should rely on the self-timing of one or another type. The preferable type of timing is dependent on the size of the circuitfragment.

Hence most elementary cells can be controlled in a"lumped' wayby clock pulsesgenerated somewhere outside the cell.

Let us start from smallest fragments, the elementary cells (Section II). Tables I and II show that for the present-day fabrication technologies (a =1-2 μm), the delay  of a typical cell is of the order of 5 ps, while its linear size is of the order of 30 μm. The SFQ pulse propagating along the typical superconducting microstrip line with velocity = c/√e = 1010 cm/s passes the latter distance in less than 1 ps, i. e., much faster than 8. This means that even considerable (say, fewer than 10%) changes or imperfections of the clock pulse propagation circuit layout cannot affect the circuit operation.

## B. SignalandClockPulseWaves

The last conclusion is valid also for some other RSFQ circuits，for example for the simplest arithmeticblocks, especially with a small wordlength (say, n = 8). For larger circuits, other approaches become necessary.

Let us consider them using a simple shift-register-type structure (Fig.21)as an example.(Here and below the data transfer will be denoted by double lines and the clock, by single lines.) Before passing the data from the previous (sending) cell to the following (receiving) one, we should first complete the clock period of the receiver by resetting it with the clock pulse. The most evidentway to ensure this consequenceis to send the clock pulse train in the direction opposite to the desired signal propagation direction, with an appropriate time delay . per gate (Fig. 21(a)). This"wave counterfiow'timing scheme generally requires that

<!-- formula-not-decoded -->

where 7 is again the clock period, and 8 is the maximum time delay of the cell. Under this condition, eachclockpulse induces a shift of all contents of theregister byoneposition.

In ordertoseewhether another wayof the simple timingis possible, consider an alternativescheme, shown inFig.21(b). Thisschemecanworkcorrectlyonlyif(6)issatisfiedand the whole register is initially empty. In this case a single clock pulse will induce a motion of the single input bit along whole the register.

Fig.22. A simple RSFQ shift register. (a) Equivalent circuit. (b) Dynamics for two cases described in the text [34].

<!-- image -->

Thus the simple timing circuits shown in Fig. -21 allow one to fulfill any of the basic tasks:either provide a one-step shift of contents of a register full with the data, or induce a rapid load of the data to an initially empty system. Their design should only satisfy thelocal condition (6)in order·toensure a correct operation of the system as a whole. Thus the natural intrinsic memory of the RSFQ cells enables one to avoid more complex two-phase timing schemes typical for the semiconductor circuits (see, e. g., [32]).

On the other hand, if the states differ (say, L6 does not carry wise current denoting '1"), the persistent currents sum up in the lower junction (J4), driving it close to its critical state. In thiscasetheclockpulseswitchesthelowerjunctionratherthe upper one. This event shifts the fux quantum (i. e., binary "1') from cell L4 to cell L6, and also somewhat influences the clock pulse dynamics, but does not change the very fact of the further propagationoftheclockpulse(becauseswitchingofeitherJ3or J4producestheSFQpulseV(t)inthepointD). Onecancheck that all "1"'\_"0"'and "0"'\_"1"'boundaries, and hence the whole the data string, will be shifted to the right after propagation of the single clock pulse along all the register, in accordance with the general "counterflow'' scheme (Fig. 21(a)). The same circuit can also operate in the load mode (Fig. 21(b)).

Note that Fig. 21 assumes that the data do not influence the clock pulse dynamics. In some specific circuits this rule can be somewhat violated, permittingvery efficient'designs. For example, Fig. 22(a) shows a shift register which can be used in very compact cash memories (only two Josephson junctions per bit) [33],[34]. The lower interferometers (J2, L4, J4, etc.) are quantizing and contain the data bits. The clock pulses T are propagating along nonquantizing loops of the upper row (cf., Fig. 3 and its discussion). If the pulse arrives to' a junction column (say, J3, J4) which separates interferometers with similar states, it circulating in the interferometers cancel in the lower junction (J4) and it is far from its critical state.

Fig. 23. Clock distribution systems for a quasi-uniform two-dimensional circuit.(a) The simplest system.(b)A possible system with the clock skew correction.

<!-- image -->

## C.2-DWavesandClockSkewCorrection

The similar timing schemes can be also used for quasi-uniform two-dimensional RSFQ structures. For example, let us come back to the parallel multiplier shown in Fig. 20(a). We have seen that itsoperationrequiresanearlysimultaneous pulses, witheachcolumnbeingfedsomewhat later thanitsright neighbor.

Fig.23(a) shows the simplest way for the appropriate timing of a general 2-D structure of this kind (with quasi-local signal connections). This counterflowscheme organizesaleftward motion of a clock wave, which induces a rightward motion of the signal waves. For operation with arbitrary elementary cells, not only (6)but also the condition

<!-- formula-not-decoded -->

(where 8r' is an average irregularity of the traversal delay T′) should be satisfied. For long operands, this condition can limit the clock frequency significantly.

Forsuchstructures, therearebetterwaystoensuretheclock wave front linearity (in other words, to correct the"clock skew"). One of the ways is shown in Fig.23(b). Here C denotesacoincidencejunction. WithintheRSFQconvention this is a circuit that provides its output SFQpulse as soon as both its inputs have been fed by such pulses.(Note that by definition this circuit isnot the elementaryRSFQ cell, because itisnottimedfromacertainterminal. Ifonelikesitanother way，itistheDROregistercellforitsinputarrivingearlier,

<!-- image -->

(e)

Fig.24. Coincidence junction. (a)A possible equivalent circuit with the initial "0o"" state.(b)Its version with the initial "01"' state.(c),(d) Corresponding Moore diagrams. (e) Dynamics of the circuit.(f) Its notation [29], [34].

which is clocked by the input arriving later.) Fig. 24(a) and (c) showapossible structure of the coincidencejunction andresults of its numerical simulation;for basic characteristics of this circuit, see Table II. Note that the circuit is designed in a way that insures its self-reset to the"oo'state (with both interferometers reset to their"o''state)right after turning on the dc supply.

Coming back to Fig. 23(b), one can see that the coincidence junctions compensate possible parasitic delays of the clock pulses in the horizontal lines (due to, say, imperfections of the layout) and thus cancel the limitation expressed by (7).

## D. HandShaking

Allpreviousdiscussionof theRSFQcircuittimingassumed that the clock pulses are generated by some circuit external to those under consideration. This way is possible for relatively small circuits where all time delays of the pulse propagation from aclockgenerator canbeprovidedwith anaccuracybetter than the clock period . For most circuits, however, another approach turns out to be preferable. In this approach, each fragment(cellorblock)ofthesystemiscomplementedbya special circuit that generates the clock pulses for its signal correspondents.

Fig.25(a)shows such a circuit for a shift-register type structure. Let the register be filled up by a string of data and all the coincidencejunctionshavereceived theiracknowledgment (ACK)pulses. In the following schemes the correspondent inputs of the coincidence junctions will be marked by 1.(If one needs to ensure the correct operation of the circuit immediately after the first turning on of the whole device, he should use the conjugate junction version which is shown in Fig. 24(b). This circuit self-resets to its"10'state with the flux quantum trapped in the L1 loop.)

The celliswaitingfor the arrival of theSENDpulse signaling that the receiver cellis reset and henceready to accept the new data. This pulse triggers the coincidence junction, which first

Fig. 25. Hand-shaking approach to the clock pulse distribution. (a) Timing ofanelementarycell[28].(b)Theelasticpipelinemodeofoperation.(c) The fixed-period-delay (or Z-) register using the latter mode. D and 0 denote cellswith andwithout data, respectively.

<!-- image -->

<!-- image -->

produces the clock pulse T for its native cell and thus forces it to send its output signal to the receiver. Simultaneously, this pulse is duplicated as the ACK signal necessary to set up the coincidencejunction of thereceiver and(after an appropriate delay T)as the SEND'signal for the next (sending) cell. As a consequence, the whole data string will be eventually shifted by onestep totheright. This counterflowoperationmode can be used, for example, for timing the shift registers formed by N and FA cells of the serial multiplier (Fig. 18(a)) and vertical columns of the parallel multiplier (Fig. 20(a)).

Even more interesting is a combination of these two operation modes when the data string is shorter than the register and thus occupies its right section of some length.(The coincidence junctions are to be set up correspondingly, with the boundary junction in its "00"" state; see Fig.25(b).) Now each SEND pulsefedinto theright end of the structureinduces a shiftof the data string by one step to the right, decreasing the data string length. On the contrary, an ACK' pulse fed into the left end (together with the data bit)inducesa rapidloading of the bit to the rightmost empty cell of the register, joining it to the data string, which is not shifted during this operation.

The same clock distribution system can operate in the"load' mode similar to that of the circuit shown in Fig.21(b). Let the shift-register-structure be initially empty, and let all the coincidence junctions have been sent their SENDpulses. Now if a signal and the accompanying ACK' pulse are fed into the left end of the whole structure, the arising clock wave pushes the data bit through all the structure. This mode can be employed, for example, for timing the-shift register formed by cells R of the serial multiplier (Fig. 18(a)).

nientfor design ofvery natural superfastblocks. As the simplest

<!-- image -->

N- 1

Fig. 26. A simple RSFQ clock controller providing a single train of N clock pulses.

example, if the elementary blocks in Fig.25(b) are merely the single-bit register sells D (Fig. 7), this circuit can serve as the first in-first out (FIFO) shift register. Its total length (including forward andreversebranches)shouldbesomewhatlargerthan circuit of the similar single-bit register cells. One cani be conthe data stringlength. Fig.25(c)shows a slightly more complex vinced that this block, the Z-1 register, provides the data delay by a fixed number of clock pulses. Despite a possibly very large length of theblock, thereis nochance thatparasitiedelays of the clock pulses can disturb its operation (of course, if (6) is fulfilled for all local delays).

If one closes the Z-l register input and output through a simple multiplexer/demultiplexer circuit, he gets a circular register that can also serve as the serial access memory.

## E. ClockControllers

All theRSFQ structures wehave discussed up tonow including the most "closed'one, shown in Fig. 25(c)) are still to be fed by ultrafast trains of the picosecond clock pulses. One could imagine that these trains shouldbegeneratedbysomeclock generator, which in particular determines their period  that should satisfy(6)for all the cells of the timed circuit.

As a simple example, Fig. 26 shows a possible controller for an RSFQ circuit that needs a single train of N clock pulses. Its operation is started by an external signal INIT, which is passed tothecontrolledcircuitasthefirstSENDpulse. Afterthe termination of the first operation period, the circuit sends the acknowledgementACK to thecontroller whichusesit togenerate the second SEND pulse, etc., until all N necessary pulses have been produced (the last pulse triggers the READY bit signaling that the whole operation hasbeen completed). Note that the structure of this controller enables it to provide a very fast (few-picosecond) SEND response to each ACK input, independent of N (i. e., of the length of the structure).

This conclusion is only correct for the simplest clock distribution systems (Figs. 21 and 23), and this is one of the reasons eliminates this need and allows one to use clock controllers rather thangenerators:the former devicepredetermines only thenumber andsequence of thepulses rather than theirperiod.

One can see that the period  between the pulses is determined by time delays in both the controlled and controlling circuits, and thus is automatically adjusted to the shortest value that is acceptable for the correct operation of the whole device. Hence the hand-shaking approach allows one to omit  from (6) and take care exclusively of the correctrelationbetween (local) values of&amp;andt. during theRSFQcircuit design.

Concluding the discussion of the hand-shaking approach, it is necessary to note that it is in fact quite common for communications in modern asynchronous computer circuits (see, e. g.,

Fig.27. Asynchronous dc/SFQ converter. (a) Equivalent circuit.(b) Dynamics.(c) Notation [26].

<!-- image -->

[10]), and even the structure of our basic timing circuit (Fig. 25(a))is formally similar to that usedin the semiconductor electronics; see, e. g., fig. 2 of [35]. Thus one can borrow quite afewrecipes suggestedby semiconductor self-timingdiscipline for a design of more complex RSFQ circuits.

Fig. 28. Timed dc/SFQ converter.(a) Equivalent circuit.(b) Notation.

<!-- image -->

Fig.29. SFQ/dc converter.(a)Equivalent circuit.(b)Notation.

<!-- image -->

stage (Fig.5)but operates as a balanced Josephson-junction comparator[1i],[37], theinput dccurrentdetermines whether the clock pulseT triggers the 2π-leapin the junction J1 and hencewhether an output pulse is developed across this junction just after arrival of T, ornot.

Thereallynewfeature that theRSFQcircuitrybrings into this discipline is a common use of the hand-shaking approach on the lowest (single-bit) level because of enormous operation speed of these circuits andhence theirhighrequirementsimposed on the clock delays (note recent attempts to apply this approach at an almost similarlylow-scalelevelin thehigh-speedsemiconductor circuits[35]). On the other hand, the natural internal memory of the RSFQ cells (including the coincidence junctions) makes the single-bit hand-shaking not excessively hardware-consuming.

## VI. POSSIBLERSFQSYSTEMSANDTHEIRPERFORMANCE

## A. dc/SFQandSFQ/dcConversion

Proceeding toa discussion ofpossibledigital andanalog/digital systems that could use the RSFQ technology, one should takeinto account the following grave fact: the picosecond SFQ pulsescanhardlybepassedbetweentheICchips, atleast using the present-day packaging techniques (see. e. g.,[36]). Hencetheinformationshouldbetransferredfrom theSFQform into the usual dc-voltage form before being passed between the chips, and then convertedback into the SFQ.

Fig.29(a) shows a possible structure of the SFQ/dc converter. Itsheart is theRSflip-flop formed byinterferometer (J1, J3, L), connected to an additional pair of the Josephson junctions (J5, J6), quite similarly to the N cell (Fig.11(a). Thereare, however, minordifferencesbetweenthetwocircuits: in theSFQ/dcconverter thejunctionpairisexternallyshunted by an additional resistor R, and the bias current I, is considerably larger than that in the cell N. Due to these differences, switchingofthebasicinterferometer toits'1"stateleads to the resistive state of the junctions J5 and J6(accompaniedby continuous Josephson oscillations), i. e.，to the appearance of a nonvanishing dcvoltageV at the converter output. Animportant advantage of this converter is its self-resetting feature: switching the basicinterferometer to its'o''state by a resetting(typically, clock) pulse R leads to a rapid decay of the output dc voltage. Internal time delay of the converterisrelativelylong on theT。 scale, butconsiderably shorter than that of anyfeasible circuit accepting the developed dcsignal.

Fig.27(a) shows a simple asynchronous dc/SFQ converter based on the two-junction interferometer. If its input current Iin is increased beyond a certain threshold value Ion, the critical state of the junction J1is achieved, and the standard SFQpulse isgenerated(Fig.27(b)). Inorder torestoretheinitialstateof theinterferometer, Iin should be nowdecreasedbelowa value Ioff. The reset of the circuit is accompanied by generation of the SFQ pulse across another junction (J2), which does not penetrate tothecircuitoutput.

The major disadvantage of the converter is that its output pulseis not synchronizedwith the clock periodof thefollowing RSFQcircuitry. Fig.28shows how this drawback can be Onemighthavenoticed that the outputvoltageof theSFQ/dc avoided. In this circuit, which is similar in structure to the bufferconverter is still low, which makes high-speed testing even more

Thedc/SFQ andSFQ/dcconvertershavebeen testedexperiGHz, despitetheirimplementation with a relatively primitive 5-um technology. In these experiments, the asynchronous dc/SFQconverter was connectedby theSFQtransmissionline (Fig. 3) to the SFQ/dc converter combined with the T flip-flop, i. e., the single-bit section of the binary counter (Fig.30). As a result，when thecircuitwasfedbyatrianglewaveform(top trace in Fig.31), a square waveform was developed at its output (the middle trace in Fig.31)although no detectable waveform appeared across the transmission line (the bottom trace), because the experimental setup could notregister thepicosecond SFQ pulses carrying the signals between the converters. These experimentshaveshownthatthedc/SFQandSFQ/dcconverterscan operate with more than ±30% parameter margins, in good agreement with the simulation results (Table II).

Fig. 30. SFQ/dc converter combined with the T flip-flop (c. f. Figs. 8, 29).(a) Equivalent circuit. (b) Dynamics. (c) Notation [26].

<!-- image -->

Fig. 31. Experimental oscillograms of operation of a test circuit containing the dc/SFQ and SFQ/dc converters connected by the SFQ transmission line [27].

<!-- image -->

difficult than thatinlatching logic. This drawback can be easily removed at the price of decreasing the upper frequency of the conversion. In this case one can use as an output stage of the converter a well-known unlatched dc biased fip-flop (or huffle) based on underdampedJosephson junctions[76]. The operation of thehufflehasbeendemonstatedwith the outputvoltageas using 5-um design rules Pb-alloy technology[77]. The design of the SFQ/dc converter based on this idea is nowin progress.

In order to do that, the RSFQ binary counter, consisting of a B. A/DConverters series of T flip-fiops (Fig.8), is connected to the direct output of the comparator and anRSFQ transmission line (Fig.3) to its A/D converters seem to be the simplest and hence the most reverseoutput. TheSFQsplitters(Fig.4)andconfluencebuffers immediate application of the RSFQ technology. The reasons for [(Fig.6) feed the reverse-output pulses into each T flip-flop. As this are similar tothose listedin theSectionI:theextremely aresult, each direct-output count increases the counter contents high switching speed of the Josephson junctions determines a a by 1 ("0..·01"' in binary code), while each reverse-output very short (picosecond-scale) aperture time Ta of the converters using them. By a proper design of the converter, this short timesubtraction is achieved, so that the contents of the binary counter can be traded for either a better accuracy e or a larger signal 1representabinarycodeofΦ/Φo. Thecodecouldbereadouit frequency Fmax, according to the general relation [38]

<!-- formula-not-decoded -->

where n = log2(1/e) is the number of correct bits. Another important advantage of the Josephson junctions, which allows hardware-saving designs of the converters, is the natural 2πquantization of the Josephson phase Φ (equivalent to the Φoquantization of the magnetic flux).

Two types of the Josephson-junction A/D converters have been developed during the last decade:parallel and serial (or counter-type)ones;for a recent review, see[38].(Compensation-type versions of the serial A/D converters are usually referred to as the digital SQUID's; we will discuss them in the next section.）The former converters are usuallybelieved to provide the highest Fmax. However, they need a simultaneous delivery of ultrafast sampling waveforms to each of their n samplers, and an extremely high (~e)precision of their comparators and analog input signal dividers. Both factors do limit theeffective aperture time, so that the experimentallydemonstrated performance of the converters (say, Fmax =100 MHz for n=6bits)areworse than that evaluated by numeric simulation without taking into account mentioned above parasitic factors (say Fmax = 5 GHz for n = 5 bits) or achieved at their semiconductor commercially available counterparts (say Fmax = 1 GHz for n = 5.2 bits) [38]. Despite some recent reasonable suggestions[39]that canhelptoimprove theperformance, webelieve that much better prospects exist for the serial or parallel-serial converters.

A possible core of the latter devices, the so-calledripple counter based on overdamped Josephson junctions, was proposed more than a decade ago[40](see also[41]). Its practical application was, however, pendinguntil a way could befound to digital output of the device. The RSFQ circuits open such a way. In order to demonstrate that, a test RSFQ circuit picking up informationfrom amodifiedversionoftheripple counter has been tested recently [28].

The quantizing part (comparator) of this A/D converter is the usual two-junction interferometer (J1, L, J2 in Fig. 32(a)). The input analog signal currentIinduces aproportionalmagnetic fluxΦ=MI applied to the interferometer. If the flux is constant, no SFQ pulses appear at the outputs. If the fux is increased in time, and crosses a level Φon+ kΦ。(with an integer k)thejunctionJ1reaches its critical state and theSFQ pulse (a"ripple")is triggered in this junction. Thus. the SFQ pulse rate at the direct output of the counter equals|Φ丨/Φ。 at Φ &gt; 0. At Φ &lt; 0, this junction is silent, but junction J2 develops a similar amount of pulses at the reverse output of the converter. So the comparator produces 1-bit numbers (pulses), which are a differentialcode of the analog signalΦ. Toget the usual binaryform of the signal, these numbers should be counted (integrated) as positive ones for direct output and as negative for reverse output.

Fig.32. Test RSFQ circuit with an asynchronous serial A/D converter and a 8-stage reversible binary counter with SFQ/dc converters for each bit.(a) General structure.(b)Microphotograph of the circuit.(c)Oscillograms of operation of the first two stages.(Photo presented by courtesy of Dr. V. Koshelets.)

<!-- image -->

continuously using the SFQ/dc converters combined with each T flip-flop (Fig. 30). Fig. 32(b) shows the whole circuit implemented using a 5-um all-Nb technology and containing 169 Josephson junctions and 300 resistors, while Fig.32(c)illustrates operation of its first two stages(for more details, see [28]).

Amore complex processingof the outputsignalof this converter is, however, impeded by a major disadvantage of the ripple counter:its output pulses are not synchronized with the clock pulses of the followingRSFQ logic stages. As a result, the clock periods, and thus either abandon counting or be counted twice.

This problem can be solved[33] using the timed A/D converter (Fig.33). In its essence the comparator (Fig.33(b)) is the

<!-- image -->

(d)

Fig.33. SerialtimedA/Dconverter.(a)General structure.(b)Equivalent circuits of the comparator and corrector blocks.(c) Equivalent circuit of the block TO.(d)Its notation[33].

two-junction interferometer (J1, J2, L), formed by lower junctions of two clocked comparators (c. f. Fig.28). Its operation is similar to that of the ripple counter, with the exception that all the SFQ pulses are triggered by the clock pulses T and thus are tightlybound in time to the clock pulse arrival moments.

A minor remaining problem is that sometimes both direct-output and reverse-outputpulses canbe generated during one clock cycle. This is why the digital part of the device should start with the corrector (Fig. 33(b)) containing an AND gate combined with twoDRO register cells D, and two xoR cells. It is straightforward to check that if the SFQ pulse arrives from one channel alone, it is passed by the corrector to the corresponding output, but arrival of the counts from both channels result in no output at all. The latter outcome alsoleads to the correctresulteventually, because the number of pulses coming from the direct and reverse channels should be later subtracted anyway.

Fig.33(a)shows thedigitalpart of thesimplestversion of the converter. The circuit is timed by a continuous train of the SFQ pulses (it can be generated by just a single overdamped Josephson junction, dc biased slightly above its critical current). The

Clock output Digitol output Fig.34. Serial A/D converter with digital low-pass filtering (for the particularcase of two stages).

<!-- image -->

output pulses from the directandreverse channels of the comparator-corrector unit arrive at the corresponding inputs of an n-bit reversible counter generally similar to that discussed earlier (Fig. 32). Its contents could be read out continuously (as Fig.32(a) shows), but if this operation is slow (i. e., limited by a relativelylarge timeofthedcsignal transferfrom theconverter chip), then several least significant bits could be already wrong because of simultaneous change of the signal. Fig.33(a) shows how this drawback can be avoided. The asynchronous T cells are replaced here by clocked TO cells (Fig.33(c)). This cell is a T fip-flopwith an additional DRO circuit for the complementary-code readout S (Fig. 34(b)), so that the register as a whole is justabinary counter with theparallel destructivereadout in the complementary code. The readout clock pulse train is running along the counter with the same speed as the data, and destructively reads out the counter contents, corresponding to the input signalvalue at a certain instant, to the output register of theSFQ/dcconverters. So thecounterstores thevariation of its inputs during the readout period 7′ = 2N. Its output dc signals canbereadoutrelatively slowly(withafrequency of the order of Fmax). The clock pulse arriving along the RESET line clears the output register just before reading in the next data from the counter.

These contentsaresentintothesimilar but 6-bitbinary counter, again with signal averagingby additional D cells. After every four clock periods, similar operation isfulfilled with the contents of these latter counters, etc.(Note T flip-flops in the clock distribution line, providing division of the clock pulse frequency by two on each stage.)

(c. f., Figs. 32(a) and 33(a)). Averaging of two consequent countsis achievedby a delay ofeach countfor one clockperiod in a simple register cell D(Fig.7), and by addition of its contents to the next count. Decimation of the redundant counts is achievedsimplyby the(destructive)reading outof the contents of the counter only oncefor two clock periods.

One can be readily convinced that each binary counter. provides the correctdifferentialdigitalcode of theinput signal (exceptall odd stagesyield thisinformation in the complementary code). The further right is the counter, the larger is the number of output bits (by two bits per stage) and the lower is the the device operation shows[33]thatN/2leastsignificantbits of its output (where N is the number of stages)present the quantization noise and should be neglected, while the remaining half of the additional Nbits are correct and present the accuracy gained due to the signal averaging at the same output code frequency Fmax. This means that = 15 bits rather than = 10 bits would be correct in the example discussed above (Fmax = 100 MHz).

Note that the parallel implementation of the decimationfilter discussed above works well for severalfirst stageswhere clock frequency is high enough. For the next stages the serial way of digital processing is less hardware consuming [33].

Formal substitution of the resulting accuracy and frequency to (9)(which does not take the averaging feature into account) yields the effective aperture time Tain a 0.1-ps range. To the best of our knowledge, this unique performance cannot be jected. Its origin is the ultrahigh sampling/processing frequency availablein theRSFQcircuits.

The second way to improve the accuracy is as follows. Recall that both the comparators (Fig. 33(b)) that feed the decimation filter canbeconsidered as1-bitA/D converterswith differential coding. Each of these comparators could be replaced with a parallel A/D converter (comprising 2P comparators), which producesp-bitdifferentialcodeoftheanalogsignal[33]. Itis evident that this wayincreases the total conversion accuracyby pbits. Computer simulation of thedevice employing sucha techniqueproved its steady operation at leastforp=2with the clock frequency no less than that of the clocked comparators shown on Fig.33(b)[33]. The two additional bits lead to the total accuracy of = 17 bit for Fmax = 100 MHz (or = 12 bit for Fmax = 1 GHz).

The first one is using a well-known oversampling technique based on sampling of a signal at a ratewell above theNyquist frequency (see, for example, [75]). The error introduced by the quantizeris spreadoutthe entirefrequencybandfromzeroto the sampling frequency 1/r. Quantization noise above the signal band is then removed with a digital decimationfilter wherein the signal is resampled at the rate 2Fmax A possible algorithm of this filtering is just a successive replacement of even counts by mean values of the even and the neighboring odd counts. Then odd counts are dropped (decimated) from further processing.

## C. DigitalSQUID's

The effective digitalfiltering described above can alsobe used for developmentofdigitalSQUID'sthatwouldcombinehigh sensitivityof their analogversion[8]withamuchhigher slew rate and avirtually unlimited dynamic range[33].

Consider an example shown in Fig.35. The usual analog dc SQUID (J1, J2, L1) senses the current flowing in the input coil L2 of its dc transformer, and produces proportional changes of the its output dc voltage V. After a moderate low-pass filtering, this signal controls theSFQ-clock drivencomparatorformedby junctions J3-J5 (c. f., Fig.28). If the dc signal I is above a

To get an idea of a possible accuracy of such a converter, let us note that its output bit number can be restricted to N= log2 (Fmax7), and that the clock period 7 is limited from below by the operating speed of the slowest RSFQ stage. For example, for a feasible value T = 10 ps (c. f., Tables I and II) one can get N = 10 correct bits of a signal with the upper frequency Fmax = 100 MHz (or N = 6.5 bits with Fmax = 1 GHz). These figures (reasonably good) do not, however, approach the ultimate performance limits of the RSFQ circuitry. There are two ways toimprove the accuracyofconversion.

Fig.34(a) shows a possible RSFQ circuit performing such a filtering. Here the output signals of the comparator-corrector unit feed the register of four TO cells (Fig.33(c)). The subtraction of the direct andreverse counts is achieved again byfeeding allstages of the counter inparallelby thereverse-outputpulses

Fig.35. Apossible structure of the compensation-typelow-frequencyA/D

<!-- image -->

certain threshold, the clock pulse T induces the 2π-leap in junctionJ4, which is then applied to the clockedinverter and the register cell D. As a result, an SFQ pulse appears at the direct digitaloutput, anditisalsoinjectedtothepositive(bottom)arm of the feedback loop. After passing the Josephson transmission line (J7, J9, J11; c. f. Fig.3), the single flux quantum is injected tothepick-upcoilof theSQUID. Thepolarityof theinjection ensuresreductionof theinputflux applied to the dcSQUIDby βΦ。，where β《1is the transfer factor. This injection of a singleflux quantawould continueeachclockperioduntil the analog outputVof the dcSQUIDreduces theinputcurrentI of the comparator below its threshold. As a result, the junction J5 rather thanJ4 would be switched each clock period, leading to supply of the SFQ pulse to the reverse digital output and insertion of the single flux quantum to the negative (top) arm of the feedbackloop. Hence the threshold will be approached from theeitherside.

Thison-chipnegativefeedbackisgenerallysimilar to that described by the Fujitsu group[73]with an important exception that in theRSFQversion the clockfrequencyf canbe extremely fast(well beyond 100 GHz, the figure tobe compared with 0.5 MHz) in [73]. As a result, the slew rate s =βΦ。f can be as large as ~ 109 Φ。/s (we have used a realistic value β = 10-2 whichwouldmakethe additionalquantizationfuxnoise6Φ= βΦ。/f1/2 = 3 × 10-8Φo/Hz1/2 of the device less than the intrinsic noise of the best practical dc SQUID's).

Note that thedevice shown inFig.35has a virtuallyunlimited dynamic range, and that the staticinput inductance of the device is infinite, thus allowing large and/or remote pickup coils. The SFQdigitaloutputof thedevicepresents thetimederivative of the signal, just as in the A/D converters considered above, so thatitscounting/filtering canbefulfilled just asFig.34shows. The number M of the consequent sections of the filter should be sufficient to reduce the output signal frequency fout = f /2 M to a valuepermittingitspickup thesemiconductorelectronicsfor a further processing. we would needM=14 stages andhence some～4000Josephson junctions on the chip. This number maybereducedbya factorof twoor treewiththehelpofserialrather thanparallel processing at the last (longest and slowest) stages. The remainingcomplexitycanbereadilytradedoffforperformanceby reduction of f and s; ultimately, one can use external clock and no SFQ counting/filtering at all, thus reducing the number of junction to 15 or so. We believe, however, that there are good prospects for the full-scale full-performance device as well.

<!-- image -->

(a)

Fig.36. Serial RSFQ chip with the serial data bus. (a) General structure. (b)Its dc/SFQ interface.(c)Its SFQ/dc interface.

<!-- image -->

(b)

## D. DigitalSignalProcessing

Fig.36 shows a possible general structure of an RSFQ digital chip. Because of theinterchipcommunication problem discussed in the beginning of this section, the chip should be equipped by thedc/SFQandSFQ/dcconverter interfaces. Duetoarelatively slow dc exchange rate (之 1 GHz), theinterface should be parallel from outside, but canbe serial inside where the RSFQ 100 GHz. Such an input parallel/serial interface (Fig.36(b)) can beorganizedasashiftregisterconsistingoftheoRcells(Fig. 10)fedbythetimed single-bitdc/SFQconverters(Fig.28). The output serial/parallel interface(Fig.36(c))canbe organized as the register of the N cells (Fig.10) with their NDRO outputs feeding the single-bit SFQ/dc converters (Fig.29).

The other key components of the chip are the digital device itself and a clock controller. Let us consider the operation cycle of the device as a whole, supposing that the hand-shaking approach (Fig.25(a)) is applied for the clock distribution to all the cells, and that all the coincidence junctions are initially set for thecounterflow(shift)mode. Atfirst, thedcinputsshouldbe supplied with the data to be processed. Then the clock signal INIT，which confirms relevance of the data, arrives. Itis converted to the INIT SFQ pulse, which triggers the clock controller. The first clock pulse generated by the controller (see Fig.26forthe simplestexampleof thisblock)arrives at thefirst stage of the SFQ/dc interface as a SEND signal. Passing the coincidence junction of the stage, this signal is duplicated as the SEND'signalfor the next cell and the ACK signal comingback to the controller. The latter pulse starts a new similar clock

Fig. 37. Canonic second-order section IR digital filter.

<!-- image -->

pulse, etc., so that a clock wave starts to propagate towards the signal wave. It is evident that the clock period is established at a valueTcwhichis slightlyinexcessof the timedelayof a single stage of the register (typically，a few picoseconds, see Tables I and II). Note that when/if the clock wave meets slower cell(s), this local timing scheme automatically slows its pace accordingly.

When theclockwavereaches thefarend of the circuitry(the upper edge of the dc/SFQ interface in Fig. 36(a)) it is closed by a simple loop; the SEND pulse developed by the last register cell is used just as the ACK pulse fed back to the same cell after a provides the continuous clock wave flow regardless of the total length of the clockpath. The operation of thedevice is terminated by the clock controller after it counts the proper number of clock periods. As a result, the controller stops pushing the clock wave (and hence pulling the signal wave) and sends the READY signaloutside(througha single-bitSFQ/dc converter).

Note that Fig.35(a) shows just the simplest pipeline structure (such devices are most promising forutilization of the enormous speed of the RSFQ circuitry). More complex circuits may require multiple joints of the signal and accompanying clock lines with a more complex hand-shaking protocol in the joints in order toensurethe correctsignalexchange.

Nowlet us consider several concreteRSFQdigitalchips of this type and their discuss possible performance. The simplest example is the serial multiplier (Fig. '18). Table Il shows estimated performance of such a device in comparison with those for other digital technologies. One can see that the serial RSFQdevice can combine arecord speedwith an exceptional simplicity. Even implemented with a present-day(few-um-destandard chip area. This is why more complex devices can be evenmoreattractiveforimplementation.

Fig. 37 shows a core component of another very useful device, the digital filter with avirtually arbitrarytransfer function, processing a regular inflow of n-bit numbers X. Such a filter can be composed[42]of the second-order sections (Fig. 36). The section calculates first thelinear combination

<!-- formula-not-decoded -->

of the current number with two preceding numbers (so that d; is dependent implicitly on all the former data), and then the output numbers

<!-- formula-not-decoded -->

In the frequency domain,(10) and (11) correspond to the function

<!-- formula-not-decoded -->

Suchsectionscanbecombinedtoperformarbitrarylinear transforms of the input data, including time-dependent transforms(provided that the numbers A;and B; are changed from onecycletoanother).

In the RSFQ technology, the second-order section can be composed of our familiar blocks: two digital delays (Z-1 registers), four single-bit full adders, and four serial multipliers (Fig. 37). The last components are most complex and slow, and thus determine both the operation speed and integration scale of the section. According toTablesI and II, the sectionhandling 32-bit numbers (andrequiring only as few as some 12 000Josephson junctions)，being implemented with 2.5-um technology, could process up to 5 × 108 numbers/s. This is why it would enable one to extend elaborate methods of the digital signal processing, developed for"acoustic''-frequencies(several-ten-kHz)[43], to

Of course, this is just one example, because similarly fast RSFQ circuits can be designed for other types of digital signal processing. Nevertheless, we believe that the example shows clearly that this new technology opens unique opportunities for several areas of the applied electronics, particularly for radars and communications.

## E. Computing

In contrast to digital signal processing, a universal von-Neumann-type computer isprobablythe worst deviceforimplementation using the RSFQ(or any other superfast) technology. The reason is that such a device relies on frequent data exchange between the processor andmemory，with the exchange rate distance). One can see that if the processor and the bulk of the memory are located on different chips (as they typically are), it processor).

Let us, nevertheless, estimate a possible performance of the RSFQ-based circuits of this type. A simpleRSFQmicroprocessor can be designed in the serial fashion (Fig. 36); it would require a serial ALU with only~100 elementary cells with 4 to 15 Josephson junctions each, one serial multiplier, some 64 memory registers with 3 to 4 Josephson junctions per bit, and ers and demultiplexers (with7 to8Josephson junctions each). It leaves us with less than5000 junctions altogether. On the other hand, an elementary analysis (using Tables I and I) shows that even with an existing fabrication technology (say, a = 2.5 μm) thenet logic delay of the device canbe as small as~20 ps/bit.

True, such a formal analysis neglects the interblock propagation delays. Nevertheless, thanks to unique properties of superconducting microstrip lines (see Introduction） and the serial mode ofoperation of the devicesunder consideration, the delays can be minimized.

Infact, if the distancebetween the communicatingblocks is not very large, one can connect them by a uniformly distributed shift register with single-bit hand-shaking, operating in the elastic pipeline mode (see Fig. 25(b) and its discussion). This approachallows thereceiving block to use firstbits of the data before the last ones are sent. Its disadvantage is arelatively complex structure, andhence a considerable physicalwidth, of the communication channel. As a reward, the signalpropagation hereproducesnoadditional logicdelayatall, providedis not very large:Q≤nc8～1 cm.

In the case of short numbers or instructions (or very far blocks)thecommunicationchannelcanbesimplifiedtoconsist

of just two bare microstrip lines for the data and the clock. If one provides the data line with fast (and simple) buffer registers on both its ends, one can use the hand-shaking approach on the single-word (rather than single-bit) level. It would reduce the operation. Comparison with the figures in Tables I and II shows that this delayis almost negligible even for distances aslong as 1 cm.

These estimates show that the RSFQ technology allows one to implement, for example, an 8-bit microprocessor performing 5-10 billion register/register operations/s (including cash memory operations), or alternatively a 32-bit microprocessor performing 1-2 billion operations/s. These figures are considerably betterthanthoseachievablewithotherexistingtechnologies using either semiconductors or superconductors (see, e. g.,[22]). Note that a similar speed is attainable in more complex RSFQ processors as well, via usage of parallel blocks (e. g., multipliers; see Table I1) for broadening the critical path bottlenecks; of course, this measure can cost a considerable increase of the integration scale.

i) The superfast microprocessors with an on-chip cash memory using, e. g., very compact registers shown in Fig. 22, can be extremely useful for controlling the real-time signalprocessors (see theprevious section).

One can justly argue that this increase of speed is virtually uselessdue to themuch smaller speed of theintrachip communications between the microprocessor and the main memoryin a standard general-purpose computer. Nevertheless, two comments can be made on this point:

i)Theproblemof the standardvon-Neumann-type computer being too slow is not specific for the RSFQ digital technology, but will be met by any technology approaching the 100-GHzclock-frequency frontier; the RSFQ circuits have just come there first. Solutions of this problem should be apparently looked for in development of new computer architectures that would make full use of the unique operation speed of the novel logic/memory circuits, and also take into account the final speed of the signal propagation on both the intrachip and interchiplevels.

Another prospective direction of research and development is packaging. If a way could be found to allow the SFQ-pulse communicationbetween chips, one could place a computer as a whole on the resulting"superchip.'Here one could make full use of thefabulous speed of the parallelRSFQ circuitry (please have onemorelook on theestimatedperformance of theparallel-type RSFQ multiplier in Table III), and ten-GOPS computing speeds of single processor units would become a reality.

Specialattentionshouldbeattractedtocellularautomata structures with local interconnections of the cells (see, e. g., [44]). Note that most of the RSFQ blocks are just the cellular automata, either one-dimensional (see, e. g., Fig.18) or two-dimensional (Fig.20). Presently，most attention in this field is attracted to transputer-type systems where each cell is a complete microcomputer. Possibly，more elementary units like the RSFQ blocks could be more practical cells for operating with ultrafast hardware.

## VII. CONCLUSION RSFQ:ADVANTAGESANDPROBLEMS

The Josephson-junctionRSFQ circuits canperform thelogic and arithmeticfunctions at extremelyhigh(sub-terahertz)clock frequencies, just a fewtimes lower than theintrinsic reciprocal time of the junctions employed. These circuits seem to represent themostfast digital technology availablenowadays.

Fig.38. Layout of a typical RSFQ elementary cell (the T flip-flop with dc converter). (a) Top view and (b) cross section of its part.

<!-- image -->

(b)

A list of other advantages of this technology includes:

- ducting layers (including the ground plane;see Fig.38);
- ii)small power consumption virtually eliminating the selfheating problems up to the VLSI level, at least for the low-Tc materials;
- iv)natural self-timing, which enables one to save the ultrahigh operation speed in important LSI circuits, notably the digitalsignalprocessors.

Anotherproblemislowoutputvoltageof theSFQ/dcconverters，which urges one todevelopspecial superconductor and/orsemiconductoramplifiersofthevoltageandthe helium/room temperature interfaces.

This impressive list does not mean that the RSFQ circuits are free of problems. For one, all Josephson junction technologies (RSFQincluding) sufferfrom theparasitic trapping the magnetic flux quanta(in the form of the Abrikosov vortices) in superconducting thin films, especially that of the ground plane. Despite some recipes developed, including circuit cooling ina low-field environment, and a special ground plane patterning, the struggle againsttrappedfluxisstillmoreanartthanthescience. Our feeling is that some important reserves remain unused in this struggle, and that the problem can be solved in a radical way.

There is also an important difficultywhich haslittle to dowith either physics or technology:the RSFQ idea has not yet married

an advanced Josephson junction fabrication technology, due to with their very small power dissipation (typically, less than 10-7 financial, political, bureaucratic, and apparently psychological obstacles.

The authors would be happy if this paper could help to overcome these problems.

## APPENDIXI

## RSFQCIRCUITLAYOUTPECULIARITIES

Layout of the RSFQ circuits is generally similar to that of the latching circuits (see, e. g., [4]-[7], [15]-[22]). Few substantial peculiarities can be traced in Fig. 38, which shows a typical RSFQ elementary cell, the T flip-flop (c. f., Fig.8(a)). The main newfeature is the external shunting of all Josephson junctions by metallic resistors Rs, necessary in order to make them overdamped, i. e., to make their McCumber-Stewart parameter[1], [11]

βc=(h/2e)1cR²fC (13) Almost simultaneously, several other SFQ devices were proposed. In particular, the simplest single-junction interferometers close to1(afurther decrease of R, would cause an undesirable ("rf SQUID's")have been suggested as the SFQ memory cells increase of the time constant To; note that values of 。listed in with destructive readout [52]-[56]. The major problem here was Table I were calculated for βc = 1). In any case, typical values that of readout of the cell contents. Now we know that one can of Rer are in the few-ohm range. readilyperform the destructivereadoutbypicking up and proAnother important requirement to the shunt is its low induccessing the SFQ pulse arising across the junction during the tance L. Calculations show that the corresponding parameterβ, switching, but some 15years ago this fact was not so evident. defined by (4), should be preferably less than 0.3 and by no ）This is why more complex cells(with typically multiquantum means exceed O.8, in order to avoid undesirable dynamic effects. trapped flux) and additional NDRO circuits (converting. the SFQ In the layout, the shunt is a normal-metal thin-film stripwith the information to the dc form) [57] were preferred for cash memolength/width ratio typically close to 1. In order to reduce its sries of the latchinglogics[4],[22]. SimilarSFQmemory cells inductance, the strip should pass under a part of the supercon-1 usingtwo-junctioninterferometers allow the destructive dcreadductingcounter-electrode. out [58] and are used in the main memories in the latching-logic projects [4],[21].

1W/junction for 300-GHz clock frequency at helium temperatures). For example, vertical stacking of just two Josephson junctions would allow one toreduce area of thesingle-bit cell of the register memory (Fig.22) to some 10 junction areas.

## APPENDIXII BRIEFPREHISTORY OF THESFQ DIGITALDEVICES

Theidea touse single flux quanta for coding the digital bits has emerged at the very early stages of studies of the Josephson effect. Probablythemostinfluentialoftheseearlyworkswas that by Anderson, Dynes, and Fulton [50] where the 'Flux Shuttle'was proposed. This device (later implemented experimentally; see e. g.,[51]) was essentially an SFQ shift register, similar in structure to the lower row of that shown inFig.22(a). In contrast to theRSFQ circuits, however, the shift was induced by an external rf drive (one position per one period).

In orderto avoidthetransferofinformationfromtheSFQto the latching circuits), so that the layout is restricted to only threethe dc form, several circuits capable ofperforminglogic funcsuperconducting layers including the ground plane. As a result, tions with the SFQ bits have been suggested [59]-[66]. Of those, notable is the parametric quantron(reinvented several times [59],[62],[64]), which can perform reversible processing of digital information and as a consequence approach the ultimate minimum of energy consumption [60],[65].

Otherfactorswhichincrease thepotential integration scale of theRSFQcircuitsinclude absence of theRF power supply transformers and most latches, required by latching logics. The present-dayRSFQcircuit layoutis quite convenient forimplegies(Nb/Al2O/Nb), firstintroduced by Gurvitch et al.[45] and then perfected considerably, mostlybyJapanese laboratories (see, e. g.,[15]). The MSU/IRE collaboration used several simplifiedversions of this technology[24],[26]-[28],[46](with [47]), can become a necessity.

The second important feature of the RSFQ circuits is that they the chip area A occupied by a typical RSFQ cell (expressed in the minimum feature squares a²)is either close to, or even less than that of the corresponding gate of a latching logic; see Table I1.(The experimental circuits designed and fabricated by the MSU/IRE collaborationwere somewhat larger than these estimates show, because two insulating layers had to be used because of a poor quality of the insulation.)

TheRSFQidea was approached closelybyArnold Silver and cuits, but for forthcoming implementation of the VLSI circuits acounter that was successfully tested later to operate at frequenuse of recent improvements, including planarization (see, e. g., cies in excess of 100 GHz [67]. An elementary cell of this counter was identicalin function to ourTflip-flop shown in Fig.8(a)(although the original designyielded rather narrow fabricate very small Josephson junctions (S  0.1 μm²）reproducibly，a further substantialincrease of the relative density oped by Nakajima and coauthors[68],[69]whogave examples (i. e., the a²/A ratio) of the RSFQ circuits can be achieved, of how ballistically moving Josephson vortices (i. e., single flux because a junctions of such area(with thefixed R, of few quanta) can be trapped by interferometer loops. ohms) become overdamped [48] without external shunting.

Common drawbacks of all these devices include a needin an external(typicallymultiphase)rfdrive anda limiteddistance range of the data transfer during one clock period.(This range is determined bya specificinductance of the transmissionlines and is·typically of the order of the single cell size.)The reader has ealreadyseenthatthelatterdrawbackcanbeavoidedbythe ballistic transfer along superconducting microstrip lines. Historically, the first suggestion [66] was to use long Josephson junctions capable of combining ballistic transfer of the SFQ pulses with their processing, but the logic cells proposed in these works were very complex, large, and slow.

Nevertheless, to our knowledge the key idea of special clock One more potential reserve is the vertical integration of thepulses that would enable one to make a strict definition of the junctions[49], which is quite acceptablefor theRSFQcircuitsSFQinformation(c. f., theRSFQBasic Convention)and hence

to design a complete setof theSFQlogicfunctions hadnotbeen suggesteduntilourfirstwork[23].

## APPENDIXIII

## PROSPECTSFOR THEHIGH-T. SUPERCONDUCTIVITY

Therecent advent of the high-T. oxide superconductors is doubtless a great scientific event that should have a significant impact on several areas of science and technology, including superconductor electronics [70], [71]. In order to use these new materials in Josephson-junction devices, however, one should solve several problems[71].

Thefirst problemis that ofreproducibleJosephson junctions with suitable parameters including the I. Rn product, normal resistance Rn, andMcCumber-Stewart parameterβ. The junctions available presently (for a recent review see[72])are mostly overdamped(β.&lt;1)，andhavearathermoderatevalueof IR,(typically, several hundred microvolts at 77K) and low Rn (typically, below 1 Ω). Their major drawback, however, is their irreproducibility, presently excluding any chance for their use in LSI circuits.

Nevertheless, due to the amount of attention attracted by this problem, progress has been quite fast, and some way(s) to fabricate decent junctions reproducibly can be found (possibly even before this paper is published). At this stage, several fundamental problems will arise, notably that of the thermal noise stability[71]. In order tokeep the probability of thermalnoise-induced errors low enough, the ratio of the Josephson coupling energy E,=hlc/2e to the fuctuation energy scale k pT should be large enough (typically, of the order of 500). For helium temperatures the resulting condition（I. ≥ 100 μA) can be readily fulfilled. For a stable nitrogen-temperature operation, however, the critical current should be rather high(I.≥ 2mA).

Currentssolargecausetwoundesirableeffects:junction self-heating and a necd for very low inductances. It is easy to be convinced (see, e. g.，Likharev et al. in [7o]) that the former effect makes thelatchinglogic circuits impractical atnitrogen temperatures. For the RSFQ circuits the energy dissipation also grows, but to a lesser extent, leading to figures close to 3 × 10-18 J/bit. For a VLSI circuit with, say, 3 × 10^ Josephson junctions operating witha clock frequency of 300GHz, one estimates a power dissipation of ~0.1 W. Dissipation in the bias resistors increases this figure to ~ 3 W. Such a power still can be removed from a 1-cm² chip by liquid nitrogen without forbidding overheating[70].

Thus one comes to thepreliminary conclusion that an acceptable solution of the Josephson junction fabrication problem could make thenitrogen-temperature-operatedRSFQcircuitsfeasible. One can argue [71], however, that in devices so complex and so

The latter problem of low inductances is more severe. We have already mentioned thatloopsin theRSFQcircuitstypically shouldhaveinductancesβ, from3to10. Fortheabovevalueof Ione gets theLfrom 0.5 to1.5 pH. For the smallest penetration depth入=0.2 μm available for the high-T。superconductors at 77K, this fact means that the smallest loop should have notmore than~3lithographic squares connected in series (aninsulation thicker than~入wouldfurtherreduce thisfigure). As one can see in Fig.38, this limitation makes the layout design very hard. Cooling to intermediate temperatures (say, ~30K)wouldrelax thislimitation signifcantly. Note that this evaluationiscorrectonlyfortheunshuntednonhysteresis Josephsonjunction. Alternativesituationsofusingshuntedhys teresisjunctionsislessrealisticbecauseofsimilarproblemwith shunt inductances (see Appendix I).

uniqueintheir performanceastheVLSIRSFQcircuits, the coolingisfarfrombeingthemainconcern. Theauthorsbelieve thatwhensuchdigitaldevicesareimplemented，theywould readilyfind several applicationniches even if theyrequired the helium cooling. Transfer to the the high-T. materials would apparentlyrequire a muchlonger period.

## ACKNOWLEDGMENT

Joint work and numerous fruitful discussions with all members of the MSU/IRE collaboration are gratefully acknowledged. We are especiallygrateful to O. Mukhanov and S. Rylov for their kindpermission to use some of their new results and ideas prior topublication. We would alsolike to thank other colleagues, notably D. Feld, C. Heiden, S. Hasuo, M. Gurvitch, V. Koshelets, M. Muck, A. Rakhimov, N. Roi, T. Van Duzer, andS. Vyshenskii forusefuldiscussions, and toV. Polonskii and S. Zimacheva for their help in numerical simulations. Special thanks are to A. Braginski and the anonymous referee fortheirattentivereadingof thedraftmanuscript, andvaluable remarks.

## REFERENCES

- [1]T. Van Duzer and C. W. Turner, Principles of Superconducting Circuits. New York:Elsevier,1981.
- R. L. Kautz,"Miniaturization of normal-state and superconducting microstriplines,"'J. Res. NBS, vol.84, pp.247-259, Feb. 1979.
- [3] S. Kotani, T. Imamura, and S. Hasuo,"A 1.5-ps Josephson OR gate,"Tech. Digest IEDM'88, pp.884-885,1988.
- [5] M. B. Ketchen et al., A Josephson technology system level experiment,'IEEE Electron Device Lett., vol. EDL-2, pp. 262-265，Feb.1981.
- [4] "Josephson computer technology:An IBM research project, IBM J. Res. Develop., vol.24, Mar.1980.
- [6] H. Hayakawa,"Josephson junction technology for high speed computer systems, IEEE Trans. Magnetics, vol. MAG-19, Pp. 845-852, Mar.1983.
- [8] T. Ryhaenen et al., SQUID magnetometers for lowfrequency applications,"'J. Low Temp. Phys., vol.76, Pp. 287- 386. June 1989.
- [7] T. Gheewala,"The Josephson technology,'"Proc. IEEE, vol. 70, pp.26-34, Jan.1982.
- [9] G. K. G. Hohenwarter, J. A. Grange, and S. R. Whiteley，"A fast open-cycle cryocooler for cryogenic high-speed signal processing circuits, IEEE Trans. Magnetics, vol. MAG-23，pp. 775-776, Mar.1987.
- [11] K. K. Likharev, Dynamics of Josephson Junctions and Circuits. New York:Gordon and Breach,1986.
- [o1] C. Seitz，System timing,'in C. Mead and L. Conway, Introduction toVLSI Systems. Reading, MA:Addison-Wesley, 1980, ch.7.
- [12] P. C. Arnett and D. J. Herrell,"Power design for gigabit Josephsonlogic\_systems, IEEE Trans. MicrowaveTheory Tech., vol. MTT-28, pp.500-508, Oct.1980.
- [13] T. Enoki, S. Sugitani, and Y. Yamane,"0.15 μm GaAs MESFETs applied toultrahigh-speed frequency divider,'Electron. Lett., vol.25, Pp.512-513, Apr.1989;L. Waller, Hughes breaks speedrecord for digital gallium arsenide,''Electronics, Pp. 31-31, Dec.1986.
- [14] H. Kroger,"Josephson devices and technology, in Japanese Assessment. Park Ridge, NJ: Noyes Data Corporation,1986, pp.250-306.
- [16]Yu Hatano, S. Yano, H. Mory, H. Yamada, M. Hirano, and U. Kavabe, A 4-bit Josephson data processor\_with dc output buffer,'in Extended Abstracts of ISEC"89, Tokyo,1989, pp. 375-380.
- [15] Y. Tarutani, M. Hirado, and U. Kawabe, "Niobium-based integrated circuit technologies," Proc. IEEE, vol. 77, pp. 1164-1176, Aug. 1989.
- [17] S. Kotani, T. Imamura, and S. Hasuo,"A subnanosecond clock Josephson 4-bit processor,"'IEEE J. Solid-State Circuits, vol. 25, pp. 117-124, Feb. 1990.

- [18] H. Nakagawa, S. Kosaka, I. Kurosawa, M. Aoyagi, Y. Hamazaki, [40] J. P. Hurrell and A. H. Silver, "SQUID digital electronics,' in Y. Okada, and S. Takada,"A Josephson 4-bit processor for a FutureTrendsin SuperconductiveElectronics, B. S. Deaver, prototype computer,"inExtended AbstractsofISEC'89, Jr. et al., Eds. New York: AIP, Conf. Proc. #44, 1978, pp. Tokyo,1989，pp.387-390. 437-447.
2. [20]1. Kurosawa, H. Nakagawa, S. Kosaka, M. Aoyagi, and S.[42] Takada,"A1-kbitvariable thresholdJosephsonRAMchip,''in Extended Abstracts ofISEC89, Tokyo,1989, pp.395-400.
- [19] S. Kotani, A. Inoue, T. Imamura, and S. Hasuo,"A 1-GOPS 8-bit Josephson digital signal processor,，' presented at ISSCC '90, San Francisco, CA, Feb. i990.
4. S[41]J. P. Hurrell, D. C. Pridemore-Brown, andA. H. Silver, A/D conversion with unlatched SQUID's,"IEEE Trans. Electron Devices, vol. ED-27, pp.1887-1896, Oct.1980.
- [21] S. Nagasawa, Y. Wada, H. Tsuge, M. Hidaka, I. Ishida, and S. Extended Abstracts ofISEC'89, Tokyo,1989, pp.401-406.
- [23] K. K. Likharev, O. A. Mukhanov, and V. K. Semenov, "Resistive singlefluxquantumlogicfor theJosephson-junction technology,'in SQUID '85. Berlin, Germany:W. de Gruyter,1985, pp. 1103-1108.
7. [22]S. Hasuo and T. Imamura,"Digital logic circuits,'Proc. IEEE, vol.77, Pp.1177-1193, Aug.1989.
8. VLSI and Modern Signal Processing, S. Y. Kung, H. J. Whitehouse, and T. Kailath, Eds. Englewood Cliffs, NJ:Prentice-Hall,1985.
9. P. Denyer and D. Renshaw, VLSI Signal Processing:A Bit-
- [44] "Cellular-automata,"Proc. Interdisciplinary Workshop, Los Alamos, NM, Mar.1983, Physica D, vol.10D, Jan.1984.
- [46] V. P. Koshelets, G. A. Ovsyannikov,1. L. Serpuchenko, and A. N. Vystavkin，"Frequency conversion with quasiparticle nonlinearity ofNb-AlOx-Nb tunnel junctions,'Pis'ma Zh. Tekhn. Fiz.(Soviet Tech. Phys. Lett.), vol. 11, Ppp. 290-295, Mar. 1985.
- [25] K. K. Likharev, O. A. Mukhanov, and V. K. Semenov, "Ultinetics, vol.23, pp.759-762, Mar.1987.
- [24] V. P. Koshelets, K. K. Likharev, V. V. Migulin, O. A. Mukhanov, G. A. Ovsyannikov, V. K. Semenov,1. L. Serpuchenko, and A. N. Vystavkin,"Experimentalrealization of a resistive single flux quantum logic circuit,'IEEE Trans. Magnetics, vol. MAG-23, Pp.755-758, March1987.
- [43] SerialApproach. Wokingham:Addison-Wesley，1985.
- [45] M. Gurwitch, M. A. Washington, and H. A. Huggins, "High refractory Josephson tunnel junctionsutilizing thin aluminum layers,"Appl. Phys. Lett., vol.42, pp.472-475, Mar.1983.
16. -[47]S. Nagasawa, H. Tsuge, and Y. Wada,"Planarization technology for Josephsonintegration circuits,'IEEE Electron Device Lett., vol.25, pp. 414-416, Aug.1989.
- [26] V. K. Kaplunenko, M. 1. Khabipov, V. P. Koshelets, K. K. Likharev, O. A. Mukhanov, V. K. Semenov, I. L. Serpuchenko, and A. N. Vystavkin，"Experimental study of theRSFQ logic elements,"'IEEE Trans. Magnetics, vol.25, pp.861-864, Mar. 1989.
- [49] T. Imamura, H. Hoko, and S. Hasuo,"Integration process for JosephsonLSIbasedonNb/Al2O/Al junctions,'inExtended Abstracts ISEC '87, Tokyo, 1987, pp. 57-62.
19. [28]] L. V. Fillipenko, V. K. Kaplunenko, M. 1. Khabipov, V. P. Koshelets, K. K. Likharev, O. A. Mukhanov, S. V. Rylov, V. K. Semenov, and A. N. Vystavkin,"Experimental implementation ofanalog-to-digitalconverterbasedon thereversibleripple counter,'submitted to 1990 Applied Superconductivity Conf. Snowmass, CO, Sep.1990.
20. L. D. Jackel, E. L. Hu, R. E. Howard, L. A. Fetter, and D. M. Tennant,"Ultrasmall superconducting tunnel junctions,"IEEE Trans. Electron Devices, vol. ED-27，Pp. 2030-2031, Oct. 1980.
- [50] P. W. Anderson, R. C. Dynes, and T. A. Fulton,"Josephson fux quantum shuttles,''Bull. Am. Phys. Soc., vol.16, p.399, Mar. 1971.
- [27] ]V. K. Kaplunenko, M.1. Khabipov, V. P. Koshelets, I. L. Serpuchenko, and A. N. Vystavkin, Experimental study of the singleflux quantum devices, in ExtendedAbstractsISEC89, Tokyo, 1989, pp. 411-414.
- [52] T. D. Clark and J. P. Baldwin,"Superconducting memory device using Josephson junctions,"Electron. Lett., vol. 3, pp. 178-179, Feb.1967.
- [29] O. A. Mukhanov, S. V. Rylov, V. K. Semenov, and S. V. Vyshenskii,"RSFQlogic arithmetic，IEEE Trans. Magnetics, vol.25, Pp.857-860, Mar.1989.
- [51] T. A. Fulton and L. N. Dunkleberger,"Experimental fux shuttle," Appl. Phys. Lett., vol. 22, pp. 232-233, Jan. 1973.
- [53] W. Anacker and H. H. Zappe, "Superconducting memory array using weak links,"U. S. Patent 3 705 393, Dec. 5,1972.
- [30] ditical devices,""in Extended Abstracts ISEC'89，Tokyo, 1989, Pp.557-560.
- [54] K. K. Likharev，"Properties of a weak-link-closed superconductingloopas amulti-state device,'RadiotekhnikaiElektronika, vol.19, pp.1494-1502, June 1974.
- [31] K. K. Likharev, O. A. Mukhanov, and V. K. Semenov,"Quantum pulse reproduction in Josephson junction system, Mikroelektronika (Soviet Microelectronics), vol.17, pp. 155-161, Feb.1988;pp.147-154, Mar.1988.
- [55] W. Y. Lum and T. Van Duzer,'Switching measurements on semiconductor-barrierJosephson junctions, isolated andinmemory loops,''J. Appl. Phys., vol. 48, Pp.1693-1696, Apr. 1977.
- [32] C. Mead and L. Conway, Introduction to VLSI Systems. Reading, MA:Addison-Wesley,1980, ch.6.
32. converters using RSFQ logic/memory elements,'Rep. PRP-1, 1990 Applied Superconductivity Conf., Snowmass, CO, Sept. 1990;IEEETrans. Magnetics, tobe published.
- [35] S. Komori, H. Takata, T. Tamura, F. Asai, T. Ohno, O. Tomisawa, T. Yamasaki, K. Shima, K. Asada, and H. Terada, "Elastic pipeline mechanism by self-timed circuits, IEEE J. Solid-State Circuits, vol.23, pp.111-117, Feb.1988.
34. [56]W. J. Lum, H. W. K. Chan, and T. Van Duzer,"Memory and logic\_circuits using semiconductor-barrier Josephson junctions," IEEE Trans. Magnetics, vol. MAG-13, pp.48-51, Jan.1977.
- [58] "A single fux quantum Josephson junction memory cell, Appl. Phys. Lett., vol.25, Pp.424-426, July 1974.
- [57] H. H. Zappe,"A subnanosecond Josephson tunneling memory cellwithnondestructive readout, IEEEJ. Solid-State Circuits, vol. SSC-10, pp.12-19, Feb.1975.
- [34] O. A. Mukhanov, S. V. Polonskii, and V. K. Semenov,"New elements of theRSFQlogic family,'Rep. PRP-2，1990Applied Superconductivity Conf.，Snowmass, CO, Sept.1990;IEEE Trans. onMagnetics., to be published.
- [09] ，Classical and quantum limitations on energy consumption in computation,"Int. J. Theor. Phys., vol.21, pp.311-326, July 1982.
39. [36]C. J. Anderson, M. Klein, and M. B. Ketchen,"Transmission of high speed electrical signals in a Josephson package,' IEEE Trans. Magnetics, vol. MAG-19, pp. 1182-1i85, Mar.1983.
- [38] G. S. Lee and D. A. Peterson, Superconductive A/D converters,"Proc. IEEE, vol. 77, pp.1164-1176, Aug.1989.
- [59] K. K. Likharev,"Dynamics of some single fux quantum devices, I—Parametric quantron,'IEEE Trans. Magnetics, vol. 13, Pp.242-244, Jan.1977.
- [61] K. Nakajima, G. Oya, and Y. Sawada,"Fluxoid motion in phase mode Josephson switching system,'IEEE Trans. Magnetics, vol. MAG-19, pp.1201-1204, Mar.1983.
43. [37]V. K. Kornev andV. K. Semenov, TheJosephson Gotopair as a basic element of high sensitive samplers,'in Extended Ab-[63] A. H. Silver, R. P. Phillips, and R. D. Sandell, "High speed stracts ISEC87, Tokyo,1987, pp.131-134.
- [39] S. V. Rylov and V. K. Semenov,"A wide-margin JosephsonjunctionA/Dconverter using theredundantcoding,'Electron. Lett., vol.21, pp.829-830, Sept.1985.
- [62] Y. Okabe, A. Inoue, and T. Sugano,"Self-biasing logic-memory cellwithwide margins,'in Proc.17th Conf. LowTemp. Phys., U. Eckern et al., Eds. Amsterdam:Elsevier,1974, pp. 445-446.
46. nonlatching SQUID binaryripple counter, IEEETrans. Magnetics, vol. MAG-21, pp.204-207, Jan.1985.
47. [65]K. K. Likharev, S. V. Rylov, and V. K. Semenov,“Reversible
- [64] K. F. Loe and E. Goto,"Analysis of fux input and output Josephson pair device,"IEEE Trans. Magnetics, vol. MAG-21, pp.884-887, Mar.1985.

Trans. Magnetics, vol. MAG-21, pp.947-950, Jan.1985.

- [67] C. A. Hamilton and F. L. Lloyd,"100 GHz binary counter based on dc SQUID's,''IEEE Electron Device Lett., vol.3, pp.335-338, Nov.1982.
- [66] K. Nakajima, Y. Onodera, and Y. Ogawa,"Logic design of Josephson network,''J. Appl. Phys.，vol.47, pp.1620-1627, Apr.1976;vol.49, pp.2958-2963, May 1978.
- [68] G. Oya, M. Yamashita, and Y. Sawada,"Single fux quantum 4JL-interferometer operated in the phase mode,'IEEETrans. Magnetics, vol. MAG-21, pp.880-883, Mar.1985.
- [70] Superconducting Devices, S. T. Ruggiero and D. A. Rudman, Eds. Boston: Academic Press, 1990.
- [69] K. Nakajima, H. Sugahara, A. Fujimaki, and Y. Sawada,"Experimental analysis of phase-mode Josephson digital circuits, J. Appl. Phys., vol. 66, pp. 949-955, July 1989.
- [71] K. K. Likharev，"Progress and prospects of superconductor electronics,"'Supercond. Sci. Tech., vol.3, pp.325-337, July 1990.
- [73] N. Fujimaki, H. Tamura, T. Imamura, and S. Hasuo,"SinglechipSQUIDmagnetometer,'IEEE Trans. Electron Devices, vol.35, pp.2412-2418, Dec.1988.
- [72] M. Yu Kupriyanov and K. K. Likharev,"Josephson effect in high-T。 superconductors and structures,'Usp. Fiz. Nauk, vol. 160, pp.49-88, May 1990.
- [74] C. G. Bell andA. Newel, Computer Structures:Reading and Examples. NewYork:McGraw-Hill,1971.
10. [76]A. F. Hebard, S. S. Pei, L. N. Dunkleberger, and T. A. Fulton, "A dc-powered Josephson flip-flop,"IEEE Trans. Magnetics, vol. MAG-15, Pp.408-411, Jan. 1979.
- [75] R. W. Adams,"Design and implementation of an audio 18-bit analog-to-digital converter using oversampling techniques,'J. AudioEng. Soc., vol.34, pp.153-166, Mar.1986.
12. [77]N. Kotera, A. Asano, Y. Harada，and U. Kawabe，"Ring oscillator experiment usinga huffle circuit,，IEEE Trans. Magnetics, vol. MAG-19, pp.1174-1177, May 1983.

<!-- image -->

<!-- image -->

Konstantin K. Likharevgraduated from MoscowStateUniversity in 1966，received the Candidate of Sciences(Ph. D.)degree from the same university in1969, and in 1979 received hisDoctorofSciencedegreefromtheHigher AttestationCommitteeoftheU. S. S. R.

Since1969hehasbeenwith theDepartment of Physics，Moscow State University，working onvariousproblems oflow temperaturephysics and electronics, and leading the Laboratory of Cryoelectronics.

Vasili K. SemenovgraduatedfromMoscow StateUniversityin1971andreceivedhisCandidate of Sciences (Ph. D.)from the same university in 1975.

From 1974 to 1979 hewas working in appliedsuperconductingelectronicsat theInstitute of Physical Problems, Moscow. Since 1979 he has been with the Laboratory for Cryoelectronics, Physics Department, Moscow State University，where he heads the Superconducting Digital Circuits Group.