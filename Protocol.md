# Levcell caged cAMP project protocol
## Phase 0: Culture HEK cells and control experiment (Weeks 1-2) + order reagents 
### Materials: HEK293 (ATCC CRL-1573), DMEM high glucose, 10% FBS, 1% penicillin/streptomycin, 0.25% trypsin-EDTA, 60 mm plate, DMSO, freezing medium (90% FBS/10% DMSO).
### Protocol: 
	Thaw one vial of HEK293 cells into a 60 mm culture dish; culture at 37 °C, 5% CO₂ in DMEM + 10% FBS + P/S.
	Passage at 80–90% confluence (every 4 days) using standard trypsinization; split 1:10.
	Once stable for ≥3 passages, freeze 15–20 vials at 1–2 × 10⁶ cells/vial in freezing medium for a consistent working bank across the project.
	Maintain cells below passage 25–30 from thaw to minimize genetic drift.
	Routinely check for mycoplasma (PCR test every ~2 months).
### Note: HEK293 grows adherent; all downstream droplet work requires trypsinization to single-cell suspension immediately before loading. 
## Control experiment: 
	Harvest cells into three pellets containing ~50,000 cells each (~15 ug). 
	Lyse cells using TNI buffer and sonication, spin down at top speed to pellet debris. 
	Transfer supernatant to three clean tubes.
	Precipitate protein via MeOH/CHCl3 precipitation, and dissolve pellet in 8M Urea.
	Dilute to 2 M Urea and measure protein concentration using BCA assay. 
	Reduce, alkylate, and digest pellets overnight with trypsin for LC-MS/MS analysis in DIA mode.
## Phase 1: Pathway validation, dish-based 
### Goal: Confirm forskolin (bypasses receptor, activates adenylate cyclase directly) drives the expected PKA/CREB response, and establish your Western blot readout before adding any platform variables.
### Materials: forskolin, HEK293 cells, RIPA buffer, IBMX, DMSO
### Protocol:
	Plate HEK293 at ~2 × 10⁵ cells/well in 6-well plates; grow to ~70% confluence (~48 h)
	After 70% confluency is reached, serum-starve 2–4 h in DMEM + 0.5% FBS (reduces basal PKA activity, improves signal-to-noise). 
	Prepare: pre-warm DMEM media to 37 C. 
	Quickly and carefully remove the 10% FBS media from each well and add 1 mL of serum-low DMEM or PBS to wash away any remaining serum-high media, and aspirate immediately. 
	Gently add 2 mL of the serum-low media to each side of the well, being careful not to detach any cells. 
	Return plate to the 37 C incubator and incubate for 4-6 hours before treatment.
	Meanwhile: prepare stock solution of forskolin: dissolve 10 mg forskolin in 2.44 mL DMSO to get a 10 mM stock concentration; prepare 250 mM IBMX stock solution by reconstituting 50 mg in 899.7 uL of DMSO1–3. Pre-mix IBMX and forskolin to add to 2 mL media, since volumes are small and to ensure proper mixing. Each well should receive 0.8 uL IBMX (final concentration 100 uM) and 2 uL forskolin (final concentration of 10 uM). For vehicle control samples, add 2.8 uL pure DMSO to each well. DMSO concentration in each well becomes 0.14%. 
	Treat with forskolin/IBMX for 0, 1, 2, 5, 15, 30, 60 min. DMSO as vehicle control for early (0 min) and late (60 min) time points. 
	Do a staggered approach (n=3): 
	Work backwards: add forskolin/IBMX to 60 min well, then 30 min well, then 15 min well, then 5 min well, then 2 min well, then 1 min well, and do not treat the last well (control). Remove media and add lysis buffer to all wells at the same time after the 60 minutes have passed. Ensure proper mixing of forskolin/IBMX in each well. 
	At the end of each point, immediately move the plate on ice, aspirate the media carefully, wash with ice-cold PBS, and add 200 ul of ice-cold lysis buffer directly. For earlier time points (0, 1, 2 min), can skip on PBS step and add lysis buffer (RIPA buffer: 10 mM sodium phosphate pH 7.5, 150 mM NaCl, 1% Nonidet P-40 0.5% sodium deoxycholate, and 0.1% SDS + protease/phosphotase inhibitor cocktail)4
	Western blot: total protein 15–20 µg/lane. Primary antibodies: phospho-CREB (Ser133), total CREB, phospho-PKA-substrate (RRXS/T motif, Cell Signaling #9624 or equivalent), GAPDH loading control. 
	Quantify band intensity (ImageJ), plot phospho/total CREB ratio vs. time.
Expected result: pCREB Ser133 rises within 1–5 min of forskolin, plateaus by ~15–30 min 5. If this doesn't happen, do not proceed to caged compound — troubleshoot antibody/lysis/cell health first.
Decision gate: Clean, reproducible forskolin response (≥3 biological replicates) required before Phase 2.
## 5.3 Phase 2: Caged cAMP characterization, dish-based (Weeks 4–6)
### Goal: Confirm that UV-uncaged cAMP reproduces the forskolin response and establish loading/uncaging parameters.
### Materials: DMNB-caged cAMP (4,5-dimethoxy-2-nitrobenzyl adenosine 3′,5′-cyclic monophosphate; Biolog or equivalent supplier), UV light source (340–370 nm; a filtered xenon lamp, LED UV source, or the same laser/UV module planned for the levitator), HEPES-buffered saline for loading (avoid bicarbonate buffers to prevent pH drift under UV/handling).
### Protocol:
	Serum-starved HEK293 cells in 6 well plates 2-4 hours prior to treatment with DMNB-cAMP. Each well should contain 2 mL of media.
	Dissolve DMNB-cAMP in DMSO buffer to create 10 mM stock. Perform all steps in dark conditions and cover in aluminum foil to store in a dark place. 
	Dilute the DMNB-cAMP into pre-warmed (37 C) HEPES Buffered Saline loading buffer. Aim for a final concentration of 200 uM in each well6,7. Aliquot into 5-25 uL vials using PCR tubes and store to avoid repeated freeze-thaw cycles. Keep DMSO 0.5-1% to avoid toxicity; match vehicle controls to same DMSO concentration8. 
	Aspirate serum-low growth medium from HEK cells and wash twice with warm, blank loading buffer (HEPES buffer). Pipette the loading buffer gently against the walls of the plate as to not detach the cells. 
	Add the DMNB-cAMP working solution to cells (diluted in HEPES loading buffer), and cover with foil to store in dark conditions. Incubate for 30 minutes at 37 C. 
	Gently aspirate the loading buffer containing the extracellular, uncleaved DMNB-cAMP.
	Wash cells once to remove residual extracellular cage molecules. 
	Add 0.8 uL of IBMX stock solution to each well (100 µM final concentration), to prevent rapid degradation of the released cAMP; incubate for 10-30 minutes.9 
	Expose cells to brief flash of UV (340–370 nm, ~0.5 W/cm², 5 s); this should uncage >90% of intracellular DMNB-cAMP per literature precedent.
	Lyse at defined time points post-flash: 0 (no UV, dark control), 15, 30, 60, 120, 300 s. To lyse and stop intracellular reactions at these time points, immediately place the plate on ice, aspirate media, and add 200 uL of ice-cold lysis buffer with protease/phosphate inhibitors. Collect lysate for sonication and centrifugation as above. Controls: caged cAMP, IBMX, no UV; no caged cAMP, IBMX, vehicle control, UV; no caged cAMP, no IBMX, only vehicle control, UV. Controls only for the earliest and latest time points. 
	Each time point has its own well. 
	Note: because whole-dish UV exposure and manual lysis cannot resolve sub-minute kinetics precisely, this phase is about confirming the pathway responds to uncaging at all, not about establishing fine kinetics — that is the job of the levitator.
	Western blot as in Phase 1 (pCREB S133, pan-PKA-substrate, total CREB, GAPDH). 
	Include two controls: (a) UV flash with no caged compound loaded (rules out UV phototoxicity/stress response), (b) caged compound loaded, no UV (rules out spontaneous hydrolysis/leak).
Expected result: UV+caged-compound condition reproduces the forskolin pCREB response; both controls are flat.
Decision gate: Clean caged-compound response, comparable in amplitude/timing to forskolin, required before moving to the levitator.
## 5.4 Phase 3: Instrument characterization on the levitator (Weeks 5–7, parallel to Phase 2)
### Goal: Characterize the platform independent of cell biology: how fast does the droplet mix, how fast does the quench actually stop a reaction, and how much jitter exists between trigger and quench.
3a. Mixing time. Levitate a droplet, inject a second droplet containing fluorescent dye (e.g., fluorescein), and record homogenization by high-speed fluorescence imaging (≥200 fps). Report time to 95% homogeneity.
3b. Trigger-to-quench jitter: Fire the full trigger→delay→quench sequence 50–100 times against a high-speed camera timestamp. Report the mean ± SD of realized delay vs. programmed delay. 
3c. Determining how accurately the levcell can reproduce a known biochemical reaction. This directly benchmarks whether your denaturant quench (Section 5.6) actually stops phosphorylation on contact.
3c(i). Enzyme linearity assay and steady-state kinetics
### Objective: Establish a well-characterized biochemical PKA phosphorylation reaction that can be used to compare conventional solution-phase reactions with reactions performed in the LevCell. Phosphorylation of Kemptide will be monitored directly by LC-MS/MS rather than by the radiometric assay used in the Promega protocol.
Initial reaction conditions: Use the Promega PKA catalytic-subunit assay as the starting condition:
	40 mM Tris-HCl, pH 7.4
	20 mM magnesium acetate
	0.2 mM ATP
	130 µM Kemptide
	variable PKA catalytic-subunit concentration
	30°C
Use a single well-mixed reaction vessel for each condition. Initiate the reaction by addition of ATP and remove aliquots at defined time points. Immediately quench each aliquot in pre-aliquoted acidic organic solvent or validated acidic quench to terminate PKA activity.
### Step 1: Determine an appropriate PKA concentration
At a fixed Kemptide concentration of 130 µM, test several PKA concentrations, initially:
	1 nM
	5 nM
	10 nM
For each PKA concentration, collect a short time course, for example:
PKA concentration	Time points
1 nM	0, 5, 10, 30, 60 s
5 nM	0, 5, 10, 30, 60 s
10 nM	0, 5, 10, 30, 60 s
Quantify phospho-Kemptide by LC-MS/MS. Plot phospho-Kemptide concentration versus time and calculate the initial reaction velocity (v_0) from the slope of the initial linear region.
Select a PKA concentration that produces a readily measurable linear product-formation rate while maintaining low substrate conversion during the initial-rate measurement. Ideally, the region used for calculating v_0should correspond to <10–20% Kemptide conversion.
### Step 2: Determine Kemptide steady-state kinetics
Using the selected PKA concentration, vary Kemptide concentration while keeping PKA, ATP, Mg²⁺, buffer, temperature, and reaction volume constant.
Initial Kemptide concentrations may include:
	5 µM
	10 µM
	25 µM
	50 µM
	100 µM
	200 µM
	500 µM
For each Kemptide concentration, collect multiple early time points appropriate to the observed reaction rate. For example:
Kemptide	Example time points
5 µM	0, 30, 60, 120, 240 s
25 µM	0, 15, 30, 60, 120 s
100 µM	0, 15, 30, 60, 120 s
500 µM	0, 15, 30, 60, 120 s
The exact time points should be adjusted after the PKA concentration pilot to ensure that the initial linear region is adequately sampled.
For each Kemptide concentration:
	Quantify phospho-Kemptide concentration by LC-MS/MS.
	Plot phospho-Kemptide concentration versus reaction time.
	Fit the initial linear region by linear regression.
	Use the slope as the initial velocity, v_0.
	Plot v_0versus Kemptide concentration.
	Fit the data to the Michaelis-Menten equation:
v_0=(V_max [S])/(K_M+[S] )
Determine V_maxand K_M, then calculate:
k_cat=V_max/[E]_T 
where [E]_Tis the molar concentration of PKA catalytic subunit in the reaction.
The PKA concentration should be determined from the lot-specific protein concentration provided by the manufacturer or independently quantified. The catalytic subunit has a molecular mass of approximately 40 kDa.
LC-MS/MS quantification: Generate an external calibration curve using known concentrations of synthetic phospho-Kemptide. A stable-isotope-labeled phospho-Kemptide internal standard should be added after reaction quenching to improve quantitative reproducibility. The calibration curve will relate the phospho-Kemptide/internal-standard peak-area ratio to phospho-Kemptide concentration.
Negative control: For each PKA concentration, include a no-Kemptide control containing PKA, ATP, Mg²⁺, and reaction buffer but no Kemptide. This control will identify background LC-MS/MS signals and potential interfering species.
1. Benchmark: conventional solution-phase reaction
Repeat the optimized PKA and Kemptide conditions in conventional reaction tubes and compare the resulting kinetics with the Levcell.
Use identical:
	PKA concentration
	Kemptide concentration
	ATP concentration
	Mg²⁺ concentration
	buffer composition
	reaction volume
	temperature
	reaction time points
	quenching procedure
	LC-MS/MS analysis
For direct comparison, calculate v_0, K_M, V_max, and k_catfor the conventional and Levcell conditions.

3c(ii). Determining the precision and effectiveness of LevCell reaction quenching
Objective: Determine whether the LevCell quench terminates PKA-mediated phosphorylation rapidly and reproducibly, with minimal post-quench enzymatic activity.
Prepare two solutions:
Stock A: PKA catalytic subunit, ATP, Mg²⁺, and reaction buffer.
Stock B: Kemptide.
Concentrate the components such that mixing 4 µL of Stock A with 1 µL of Stock B produces the desired final reaction concentrations.
The reaction composition should match the optimized conditions established in 3c(i), including PKA, ATP, Mg²⁺, Kemptide, and buffer concentrations.
LevCell reaction and quench
	Levitate a 4 µL droplet of Stock A.
	Initiate the reaction by adding 1 µL of Stock B.
	Allow the reaction to proceed for defined time intervals, initially:
	0 s
	5 s
	10 s
	30 s
	60 s
	At each time point, rapidly transfer/quench the reaction using the validated acidic quench.
	Analyze phospho-Kemptide directly by LC-MS/MS without enzymatic digestion.
The primary measurement will be phospho-Kemptide concentration as a function of time.
Immediate versus delayed processing
Split quenched samples into two processing arms:
Arm 1 — Immediate processing: Process samples immediately following quenching.
Arm 2 — Delayed processing: Hold samples for 30 min at room temperature following quenching before LC-MS/MS processing.
Compare phospho-Kemptide concentrations between the two arms at each reaction time point.
If the quench is effective, the immediate and delayed samples should produce statistically indistinguishable phospho-Kemptide concentrations, indicating negligible post-quench phosphorylation.
No-substrate control
For each experiment, include a no-Kemptide control containing PKA, ATP, Mg²⁺, and reaction buffer but no Kemptide. This control will establish background LC-MS/MS signal and identify any interfering phosphopeptide-like signals.
Quench reproducibility
Repeat the LevCell reaction/quench sequence across multiple independent replicates to determine the reproducibility of the measured phospho-Kemptide concentration at each time point. Report the mean, standard deviation, and coefficient of variation for each condition.
Orthogonal dephosphorylation control
To independently assess whether the quench prevents enzymatic activity after the intended reaction endpoint, perform a complementary experiment using pre-phosphorylated Kemptide and λ-phosphatase. Compare immediately processed and 30-min post-quench samples to determine whether phospho-Kemptide loss occurs after quenching.
Deliverable for this phase: One figure with three panels (mixing time, quench progress curves, jitter histogram) — this is the platform-characterization core of the eventual paper and should be finalized before Phase 4 cell work begins.
## 5.5 Phase 4: Bulk-droplet levitated time course (Weeks 7–10)
Goal: Establish a clean, well-powered PKA time course at a cell number large enough to be comfortably within standard phosphoproteomics sensitivity, and generate a spectral library for the harder Phase 5 experiment.
Cell preparation:
	Trypsinize a confluent flask to single-cell suspension; count and resuspend in HEPES-buffered saline (no serum, no phenol red) at a concentration allowing ~1,000–5,000 cells per ~2–5 µL droplet.
	Load DMNB-cAMP as in Phase 2 (50–200 µM, 20–30 min, dark, room temperature); wash.
Levitation run:
	Dispense a cell-containing droplet onto the levitator; equilibrate at 37 °C, humidified, for 5 min.
	Deliver UV flash (trigger, t = 0).
	At each of 7 time points — 0 (no-flash control), 15 s, 30 s, 60 s, 120 s, 300 s, 600 s — merge in the SDC/Tris denaturant quench droplet (Section 5.6) and collect.
	Run n = 4 biological replicate droplets per time point (independent thaws/passages on different days), plus the two Phase-2-style controls (UV-only, caged-compound-only) at the 60 s point to confirm no confound.
Sample processing and MS (Section 5.6 for full detail):
	Digest each quenched droplet sample.
	Label with TMTpro (7 time points + 2 controls fits an 11- or 16-plex easily, leaving room for a pooled reference channel).
	Phosphopeptide enrichment (Fe-IMAC or TiO₂) on the pooled/combined sample — at this protein mass, standard low-input IMAC protocols apply directly.
	LC-MS/MS, DDA or DIA depending on instrument availability; search against human proteome with phospho as a variable modification.
Analysis: Plot phospho-CREB S133, phospho-VASP S157, and pan-RRXS/T-motif site abundance vs. time; fit a simple rise/plateau model; compare the fitted time constant to the Western blot (Phase 1/2) and, if available, the AKAR4 FRET curve. Agreement across all three readouts is the key validation claim.
## 5.6 Phase 5: Cardiomyocyte-protein-matched levitated time course (Weeks 10–13)
Goal: Repeat the Phase 4 experiment at ~15–20 cells/droplet (~3–6 ng protein — matched to one adult cardiomyocyte) using targeted MS, to directly support the R01's core feasibility claim.
Differences from Phase 4:
	Dilute the single-cell suspension so that each ~1–2 µL droplet receives ~15–20 cells (Poisson-load and verify by imaging/counting each droplet before the run — record actual cell number per droplet as a covariate).
	Reduce quench-denaturant volume proportionally (e.g., EasyPhos-style 4% sodium deoxycholate/100 mM Tris pH 8.5, merged at ~1:5–1:10 dilution into the working droplet) to keep total processed volume compatible with nanoPOTS-scale or low-bind-well digestion.
	Do not attempt broad phospho-enrichment at this scale. Go straight to targeted acquisition (PRM or parallel-reaction monitoring with heavy synthetic peptide standards) on a short pre-selected panel built from the Phase 4 discovery data: phospho-CREB S133, phospho-VASP S157, and 2–3 top RRXS/T-motif sites that showed the cleanest, most reproducible kinetics in Phase 4.
	Time points: reduce to 5 (0, 30 s, 60 s, 120 s, 300 s) to conserve replicate budget; n = 5–6 droplets per time point given the expected higher variance at low input.
	Include a dilution-series control run alongside this phase (bulk → 1,000 → 100 → 20 cells/droplet, single time point) so the paper can show explicitly where signal quality degrades — this is valuable, honest data even if the lowest point is noisy.
Analysis: Overlay the targeted-panel kinetics from the 15–20 cell condition on the Phase 4 bulk curve (normalized). The claim to support is not "identical depth," but "the same kinetic trend is recoverable at cardiomyocyte-matched protein input."
## 5.7 Sample processing (shared protocol for Phases 4–5)
	Quench: Merge quench droplet (SDC/Tris-based lysis-denaturation buffer with TCEP/CAA for simultaneous reduction/alkylation) directly into the stimulated droplet at the programmed time.
	Transfer: Aspirate the merged droplet into a low-protein-binding tube or directly onto a nanoPOTS-type processing chip.
	Digestion: Trypsin/LysC, overnight, 37 °C, following standard SDC-compatible workflow (acid precipitation of SDC before or after digestion per your chosen protocol variant).
	Desalting: StageTip or equivalent micro-scale cleanup.
	Phase 4 only — labeling and enrichment: TMTpro labeling per manufacturer protocol scaled to peptide amount; Fe-IMAC or TiO₂ phosphopeptide enrichment on pooled multiplex.
	Phase 5 — no enrichment; spike heavy PRM standards for the targeted peptide panel prior to LC-MS injection.
	LC-MS/MS: nanoflow LC coupled to Orbitrap or equivalent; DDA/DIA for Phase 4, scheduled PRM for Phase 5.



