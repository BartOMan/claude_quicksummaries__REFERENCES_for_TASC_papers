# Papers Published in IEEE Transactions on Applied Superconductivity (TASC)

Identified by rendering/inspecting the source PDFs in `~/cc_projects/fable5_engineering_summarizer/references/cleaned_files/pdf/` — checking embedded PDF `Subject` metadata (IEEE Xplore stamps this as `IEEE Transactions on Applied Superconductivity;year;vol;issue;DOI`), the paper's own printed DOI/copyright line on page 1 (`10.1109/TASC....` or `1051-8223/YY` ISSN), and cross-checking with web search where the PDF was an author-uploaded preprint lacking publisher metadata. Plain title/reference-list keyword matches were explicitly ruled out as unreliable (many non-TASC papers merely *cite* TASC articles).

| Filename | How identified as a TASC paper |
|---|---|
| 1991_Likharev_RSFQ_memory_family.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;1991;1;1;10.1109/77.80745` |
| 1999_polonsky_Delay_Insensitive_RSFQ_Zero_Static_Power.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;1999;9;2;10.1109/77.783793` |
| 2001_silver_New_Concept_Ultra-Low_Power_Ultra-High_Clock_Rate.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2001;11;1;10.1109/77.919350` |
| 2007_yamanashi_Study_of_LR_Loading_Technique_for_LowPower_SFQ.md | Paper's own printed DOI in the text: `Digital Object Identifier 10.1109/TASC.2007.898608` |
| 2009_filippov_Serially_Biased_Components_Digital_RF_Receiver.md | Paper's own printed DOI in the text: `Digital Object Identifier 10.1109/TASC.2009.2018426` |
| 2011_Kirichenko_Zero_Static_Power_Dissipation_Biasing_of_RSFQ_Circuits.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2011;21;3;10.1109/TASC.2010.2098432` |
| 2011_mukhanov_Energy-Efficient_SFQ_Technology.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2011;21;3;10.1109/TASC.2010.2096792` |
| 2015_Semenov_IEEE_New_AC-Powered_SFQ_Digital_Circuits.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2015;25;3;10.1109/TASC.2014.2382665` |
| 2017_semenov_AC_Biased_Shift_Registers.md | Paper's own printed DOI on page 1 of the PDF: `10.1109/TASC.2017.2669585` |
| 2019_fourie_ColdFlux_Superconducting_EDA_TCAD_Tools.md | Self-archived HAL record on page 1 explicitly states: "IEEE Transactions on Applied Superconductivity, 2019, 29 (5), pp.1300407... 10.1109/TASC.2019.2892115" |
| 2021_jabbari_Splitter_Trees_SFQ.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2021;31;5;10.1109/TASC.2021.3070802` |
| 2021_Semenov_SFQ_bias_for_SFQ_digital_circuits.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2021;31;5;10.1109/TASC.2021.3067231` |
| 2022_schindler_Phase_Based_Circuit_RSFQ.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2022;32;3;10.1109/TASC.2022.3142278` |
| 2023_cong_Supercond_All_JJ_Inductor_Free.md | PDF is the arXiv preprint (no publisher metadata), but the arXiv-hosted PDF displays the printed banner "IEEE TRANSACTIONS ON APPLIED SUPERCONDUCTIVITY, VOL. 33, NO. 5, AUGUST 2023"; confirmed by web search (published version, vol. 34, no. 9, Dec. 2024 issue) |
| 2023_tolpygo_Scalability_Limits_AC_Clock_Flux_Bias.md | PDF `Subject` metadata: `IEEE Transactions on Applied Superconductivity;2023;33;2;10.1109/TASC.2022.3230373` |
| 2023_Volk_Low-Cost_SC_Fan-Out_with_Cell_Ic_Ranking.md | PDF is the arXiv preprint (no publisher metadata); confirmed via web search — published in IEEE Trans. Appl. Supercond., March 2023 (also received the ASC Best Student Paper Runner-Up award) |

## Targeted check: Tolpygo, Semenov, A./Q. Herr, Coenrad Fourie, Krylov, Kirichenko, Volk, Mukhanov

Every file in this folder with one of these names in its author block (not just the reference list) was re-inspected, including preprint/arXiv copies, since a prepub PDF is fine as long as the paper ultimately ran in TASC. Result: all TASC papers by these authors are already in the table above:

- **Tolpygo** — sole/lead author on 2023_tolpygo; co-author on 2015_Semenov, 2017_semenov, 2021_Semenov (all above).
- **Semenov** — 2015_Semenov, 2017_semenov, 2021_Semenov (above); also a co-author on the 1991 Likharev paper (above).
- **Herr (Quentin & Anna)** — Quentin Herr is a co-author on 2001_silver (above). Both Anna and Quentin Herr also co-authored *"Ultra-Low-Power Superconductor Logic"* (2011_Herr_Ultra-Low-Power_Superconductor_Logic.md) — verified via web search this ran in **Journal of Applied Physics** (vol. 109, 103903, 2011), not TASC, so it's correctly left out.
- **Coenrad Fourie** — 2019_fourie (above); also a co-author on 2022_schindler (above). Also co-authored 2013_Volkmann_eSFQ_Digital_Circuits_sub_aJ_bit.md, verified via web search as published in **Superconductor Science and Technology** (IOP), not TASC — correctly excluded.
- **Krylov** — co-author on 2021_jabbari (above). Also authored 2020_krylov_Bias_Distribution_ERSFQ.md (verified: IEEE ISCAS 2020 conference proceedings, not TASC) and 2021_krylov_Design_Methodologies_SFQ_VLSI.md (a University of Rochester PhD dissertation, not TASC) — both correctly excluded.
- **Kirichenko** — sole/lead author on 2011_Kirichenko (above). Also a co-author on 2023_high_density_fabrication_process_for_single_flux_quantum_circuits.md, verified via web search as published in **Applied Physics Letters**, not TASC — correctly excluded.
- **Volk** — 2023_Volk (above); no other Volk-authored files in this folder.
- **Mukhanov** — 2011_mukhanov (above); also a co-author on 2013_Volkmann (SUST, see Fourie note) and 2023_high_density (APL, see Kirichenko note) — both correctly excluded.
