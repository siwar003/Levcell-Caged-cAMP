+# Levcell Caged cAMP Project Protocol (NOT final)

## Phase 0: Culture HEK Cells, Control Experiment, and Order Reagents

**Materials:** HEK293 (ATCC CRL-1573), DMEM high glucose, 10% FBS, 1% penicillin/streptomycin, 0.25% trypsin-EDTA, 60 mm plate, freezing medium (20% FBS, 70% DMEM, 10% DMSO).

**Protocol:**
1. Thaw one vial of HEK293 cells into a 60 mm culture dish; culture at 37 °C, 5% CO₂ in DMEM + 10% FBS + P/S.
2. Passage at 80–90% confluence (every 3–4 days) using standard trypsinization; split 1:10.
3. Once stable for ≥3 passages, freeze 15–20 vials at 1–2 × 10⁶ cells/vial in freezing medium for a consistent working bank across the project.
4. Maintain cells below passage 25–30 from thaw to minimize genetic drift.
5. Routinely check for mycoplasma (PCR test every ~2 months).

> **Note:** HEK293 grows adherent; all downstream droplet work requires trypsinization to single-cell suspension immediately before loading.

**Control experiment:** 3 samples, standard discovery proteomics.

---

## Phase 1: Pathway Validation, Dish-Based

**Goal:** Confirm forskolin (bypasses receptor, activates adenylate cyclase directly) drives the expected PKA/CREB response, and establish your Western blot readout before adding any platform variables.

**Materials:** forskolin (10 mM stock), HEK293 cells, RIPA buffer (10 mM sodium phosphate pH 7.5, 150 mM NaCl, 1% Nonidet P-40, 0.5% sodium deoxycholate, and 0.1% SDS + protease/phosphatase inhibitor cocktail)⁴, IBMX (250 mM stock), DMSO.

**Protocol:**
1. Plate HEK293 at ~2 × 10⁵ cells/well in 6-well plates; grow to ~70% confluence (~48 h).
2. After 70% confluency is reached, serum-starve 4–6 h in DMEM + 0.5% FBS (reduces basal PKA activity, improves signal-to-noise).
   1. Prepare: pre-warm DMEM media to 37 °C.
   2. Quickly and carefully remove the 10% FBS media from each well and add 1 mL of serum-low DMEM or PBS to wash away any remaining serum-high media, and aspirate immediately.
   3. Gently add 2 mL of the serum-low media to each side of the well, being careful not to detach any cells.
   4. Return plate to the 37 °C incubator and incubate for 4–6 hours before treatment.
3. Meanwhile: prepare stock solution of forskolin: dissolve 10 mg forskolin in 2.44 mL DMSO to get a 10 mM stock concentration; prepare 250 mM IBMX stock solution by reconstituting 50 mg in 899.7 µL of DMSO¹⁻³. Pre-mix IBMX and forskolin to add to 2 mL media, since volumes are small and to ensure proper mixing. Each well should receive 0.8 µL IBMX (final concentration 100 µM) and 2 µL forskolin (final concentration of 10 µM). For vehicle control samples, add 2.8 µL pure DMSO to each well. DMSO concentration in each well becomes 0.14%.
4. Treat with forskolin/IBMX for 0, 1, 2, 5, 15, 30, 60 min. DMSO as vehicle control for early (0 min) and late (60 min) time points.
   1. Do a staggered approach:
      1. Work backwards: add forskolin/IBMX to 60 min well, then 30 min well, then 15 min well, then 5 min well, then 2 min well, then 1 min well, and do not treat the last well (control).
      2. At end of the 60 min time point, move the plate on ice, remove media from all wells, and carefully wash once with ice-cold PBS. Add 200 µL of ice-cold lysis buffer to all wells at the same time.
      3. Scrape cells in lysis buffer and transfer to tubes for centrifugation. Spin at top speed for 20 min, and transfer lysate to tubes.
5. Western blot: total protein 15–20 µg/lane. Primary antibodies: phospho-CREB (Ser133), total CREB, phospho-PKA-substrate (RRXS/T motif, Cell Signaling #9624 or equivalent), GAPDH loading control.
6. Quantify band intensity (ImageJ), plot phospho/total CREB ratio vs. time.

**Expected result:** pCREB Ser133 rises within 1–5 min of forskolin, plateaus by ~15–30 min⁵. If this doesn't happen, do not proceed to caged compound; troubleshoot antibody/lysis/cell health first.

**Decision gate:** Clean, reproducible forskolin response (≥3 biological replicates) required before Phase 2.

---

## Phase 2: Caged cAMP Characterization, Dish-Based

**Goal:** Confirm that UV-uncaged cAMP reproduces the forskolin response and establish loading/uncaging parameters.

**Materials:** DMNB-caged cAMP or DEACM-caged cAMP. DMNB-caged cAMP was discontinued by Thermofisher and seems hard to source. DEACM-cAMP is a good alternative, as it is more available, has a much higher quantum yield, and requires near-visible light wavelengths to uncage (prevents any phototoxicity); UV light source (340–370 nm or 375-410 nm; a filtered xenon lamp, LED UV source, or the same laser/UV module planned for the levitator); HEPES-buffered saline for loading (avoid bicarbonate buffers to prevent pH drift under UV/handling).

**Protocol:**
1. Serum-starve HEK293 cells in 6-well plates 4–6 hours prior to treatment with caged cAMP. Each well should contain 2 mL of media.
2. Dissolve caged cAMP in DMSO buffer to create 10 mM stock. Perform all steps in dark conditions and cover in aluminum foil to store in a dark place.
3. Dilute the caged cAMP into pre-warmed (37 °C) HEPES-buffered saline loading buffer. Aim for a final concentration of 200 µM in each well if using DMNB-caged cAMP⁶,⁷. If using DEACM-cAMP, aim for 10–30 µM per well. Aliquot into 5–25 µL vials using PCR tubes and store to avoid repeated freeze-thaw cycles. Keep DMSO 0.1–1% to avoid toxicity; match vehicle controls to same DMSO concentration⁸.
4. Aspirate serum-low media from HEK cells and wash twice with warm, blank loading buffer (HEPES buffer). Pipette the loading buffer (with caged cAMP) gently against the walls of the plate as to not detach the cells.
5. Cover with foil to store in dark conditions. Incubate for 30 minutes at 37 °C.
6. Gently aspirate the loading buffer containing the extracellular, uncleaved DMNB-cAMP.
7. Wash cells once to remove residual extracellular cage molecules.
   - Note: DEACM-caged cAMP is highly lipophilic and can leave cells after entering. Control/account for that.
8. Keep in 2 mL of loading buffer containing IBMX solution to prevent rapid degradation of released cAMP (~0.8 µL per well from the 250 mM stock solution). Incubate for 10–30 minutes.⁹
9. Expose cells to brief flash of UV (340–370 nm, ~0.5 W/cm², 5 s; if using DEACM, 375–410 nm, 10–200 ms).
10. Lyse at defined time points post-flash: 0 (no UV, dark control), 15, 30, 60, 120, 300 s. To lyse and stop intracellular reactions at these time points, do a staggered approach. Take out 300 s plate first and place under UV, followed by 120 s, 60 s, 30 s, and 15 s, and add ice-cold lysis buffer to all wells at the same time. Collect lysate for sonication and centrifugation as above.
    - **Controls:** caged cAMP, IBMX, no UV (dark control); no caged cAMP, IBMX, vehicle control, UV (vehicle control). Controls only for the earliest, middle, and latest time point.
    - Each time point has its own well.
    - **Note:** because whole-dish UV exposure and manual lysis cannot resolve sub-minute kinetics precisely, this phase is about confirming the pathway responds to uncaging at all, not about establishing fine kinetics; that is the job of the levitator.
11. Western blot as in Phase 1 (pCREB S133, pan-PKA-substrate, total CREB, GAPDH).

**Expected result:** UV + caged-compound condition roughly reproduces the forskolin pCREB response; both controls are flat.

**Decision gate:** Clean caged-compound response, comparable in amplitude/timing to forskolin, required before moving to the levitator.

---

## Phase 3: Instrument Characterization on the Levcell

**Goal:** Characterize the platform independent of cell biology: how fast does the droplet mix, how fast does the quench actually stop a reaction, and how much jitter exists between trigger and quench.

### 3a. Mixing Time
Levitate a droplet, inject a second droplet containing fluorescent dye (e.g., fluorescein), and record homogenization by high-speed fluorescence imaging (≥200 fps). Report time to 95% homogeneity.

### 3b. Trigger-to-Quench Jitter
Fire the full trigger→delay→quench sequence 50–100 times against a high-speed camera timestamp. Report the mean ± SD of realized delay vs. programmed delay.

### 3c. Determining How Accurately the Levcell Can Reproduce a Known Biochemical Reaction
This directly benchmarks whether your denaturant quench (Section 5.6) actually stops phosphorylation on contact.

#### 3c(i). Enzyme Linearity Assay and Steady-State Kinetics

**Objective:** Reproduce a well-established phosphorylation reaction in the Levcell and compare directly to conventional tube-based methods. Phosphorylation of Kemptide by PKA will be monitored directly by LC-MS/MS.

**Optimizing reaction conditions:**

*Promega PKA catalytic subunit storage conditions:*
- 2,500 u × 1 (1 u = amount of enzyme required to incorporate 1 pmol of phosphate into casein in one minute at 30 °C).
- Stored in 350 mM potassium phosphate (pH 6.8) and 0.1 mM DTT.

*Assay buffer:*
- 40 mM Tris-HCl, pH 7.4
- 20 mM magnesium acetate
- 0.2 mM ATP

*Peptide substrate:*
- 50-130 µM Kemptide

*Quench buffer* 
- 4% SDC, 100 mM Tris pH 8.5 

**Step 2: Determine optimal reaction conditions**

In a tube, have 100 µL total reaction mixture volume (40 mM Tris-HCl, pH 7.4 + 20 mM magnesium acetate + 0.2 mM ATP + 50–130 µM Kemptide) + add 1 unit (volume depends on vial lot) of PKA catalytic subunit, then from 0–25 minutes, at 30 °C, aliquot 10 µL into 10 µL of quench buffer (SDC/Tris).

- Try Kemptide concentrations 50 µM and 130 µM. After plotting time course from the LC-MS/MS phosphorylated-Kemptide results, choose the concentration that is needed for a linear initial velocity within the testing period.
- Test 0, 1 min, 5 min, 10 min, 15 min, 20 min, 25 min.
- Controls: no kemptide control, no PKA control.

**LC-MS/MS quantification:** Generate an external calibration curve using known concentrations of synthetic phospho-Ser5 Kemptide. The calibration curve will relate the phospho-Kemptide/internal-standard peak-area ratio to phospho-Kemptide concentration.

#### 3c(ii). Determining the Precision and Effectiveness of Levcell Reaction Quenching, Compared to Tube Performance

**Objective:** Determine whether the Levcell quench terminates PKA-mediated phosphorylation rapidly and reproducibly, with minimal post-quench enzymatic activity.

**Prepare two solutions:**
- **Stock A:** optimized Kemptide concentration, 20 mM Mg-acetate, 0.2 mM ATP, 40 mM Tris-HCl (pH 7.4).
- **Stock B:** PKA catalytic subunit (1 unit).

Concentrate the components such that mixing 4 µL of Stock A with 1 µL of Stock B produces the desired final reaction concentrations.

**Levcell reaction and quench:**
1. Levitate six 4 µL droplets of Stock A, each representing a quench time point.
2. Initiate the reaction by adding 1 µL of Stock B to each droplet.
3. Allow the reaction to proceed for defined time intervals, before adding quench droplet:
   - 0 s
   - 1 min
   - 5 min
   - 15 min
   - 20 min
   - 25 min
4. At each time point, add 1 µL of 4% SDC/100 mM Tris as quench buffer.
5. Analyze phospho-Kemptide directly by LC-MS/MS without enzymatic digestion using the standard curve.

The primary measurement will be phospho-Kemptide concentration as a function of time.

**Immediate versus delayed processing**

Split quenched samples into two processing arms:
- **Arm 1 — Immediate processing:** Process samples immediately following quenching (i.e., transfer to equilibrated Evotips immediately after quenching).
- **Arm 2 — Delayed processing:** Hold samples for 30 min at room temperature following quenching before LC-MS/MS processing.

Compare phospho-Kemptide concentrations between the two arms at each reaction time point. If the quench is effective, the immediate and delayed samples should produce statistically indistinguishable phospho-Kemptide concentrations, indicating negligible post-quench phosphorylation.

**Containerless control:** In a 384-well plate, perform parallel well-based reactions using same volumes and automated addition using robotic arm. 

**Deliverable for this phase:** One figure with three panels (mixing time, quench progress curves, jitter histogram) — this is the platform-characterization core of the eventual paper and should be finalized before Phase 4 cell work begins.

---

## Phase 4: Bulk-Droplet Levitated Time Course

**Goal:** Establish a clean, well-powered PKA time course at a cell number large enough to be comfortably within standard phosphoproteomics sensitivity, and generate a spectral library for the harder Phase 5 experiment.

**Concerns**: Phase 3 successfully establishes whether quench reagent SDC/Tris is sufficient for immediate quench and characterizes the quench delay on purified protein. However, here there is the added variable of cell lysis in phases 4 and 5. How can we know if cell lysis AND quenching is performed sufficiently when working with intact cells as opposed to purified protein? 

**Cell preparation:**
- Trypsinize a confluent plate to single-cell suspension; count and resuspend in HEPES-buffered saline (no serum, no phenol red) loaded with caged cAMP and IBMX at a concentration allowing ~1,000–5,000 cells per ~2–5 µL droplet.

**Levitation run:**
1. Dispense a 3 µL cell-containing droplet onto the levitator; equilibrate at 37 °C, humidified, for 5 min.
2. Deliver UV flash (trigger, t = 0).
3. At each of 7 time points: 0 (no-flash control), 15 s, 30 s, 60 s, 120 s, 300 s, 600 s, merge in 1 µL 4% SDC/100mM Tris denaturant quench droplet. Note: refer to EasyPhos-style buffer to eliminate protein precipitation steps and maintain trypsin-suitable conditions. 
5. Add 1 µL of trypsin gold (+ CaCl2) to digest the droplet for 15 min at 37 °C.
6. Add 50-100% isopropanol to each sample to solubilize SDC.
7. Quench digestion by adding formic acid.
8. Transfer samples to low-bind tubes for TMT-labeling. 
9. Label digests with TMTpro (7 time points + 2 controls fits an 11- or 16-plex easily, leaving room for a pooled reference channel).
10. Combine samples (pooled sample), perform phosphopeptide enrichment on pooled sample following the uPhos workflow. 
11. Load samples into Evotips. 
12. LC-MS/MS, DIA; search against human proteome with phospho as a variable modification.
13. Run n = 4 biological replicate droplets per time point (independent thaws/passages on different days), plus the two Phase-2-style controls (UV-only, caged-compound-only) at the 60 s point.

**Analysis:** Plot phospho-CREB S133, phospho-VASP S157, and pan-RRXS/T-motif site abundance vs. time; fit a simple rise/plateau model; compare the fitted time constant to the Western blot (Phase 1/2). Agreement across all three readouts is the key validation claim.

---

## Phase 5: Cardiomyocyte-Protein-Matched Levitated Time Course (Weeks 10–13)

**Goal:** Repeat the Phase 4 experiment at ~15–20 cells/droplet (~3–6 ng protein — matched to one adult cardiomyocyte) using targeted MS, to directly support the R01's core feasibility claim.

**Differences from Phase 4:**
1. Dilute the single-cell suspension so that each ~2–5 µL droplet receives ~15–20 cells (Poisson-load and verify by imaging/counting each droplet before the run — record actual cell number per droplet as a covariate).
2. Reduce quench-denaturant volume proportionally (e.g., EasyPhos-style 4% sodium deoxycholate/100 mM Tris pH 8.5, merged at ~1:5–1:10 dilution into the working droplet) to keep total processed volume compatible with nanoPOTS-scale or low-bind-well digestion.
3. Go straight to targeted acquisition (PRM with heavy synthetic peptide standards) on a short pre-selected panel built from the Phase 4 discovery data: phospho-CREB S133, phospho-VASP S157, and 2–3 top RRXS/T-motif sites that showed the cleanest, most reproducible kinetics in Phase 4.
4. Time points: reduce to 5 (0, 30 s, 60 s, 120 s, 300 s) to conserve replicate budget; n = 5–6 droplets per time point given the expected higher variance at low input.
5. Include a dilution-series control run alongside this phase (bulk → 1,000 → 100 → 20 cells/droplet, single time point) so the paper can show explicitly where signal quality degrades.

**Analysis:** Overlay the targeted-panel kinetics from the 15–20 cell condition on the Phase 4 bulk curve (normalized). The claim to support is not "identical depth," but "the same kinetic trend is recoverable at cardiomyocyte-matched protein input."

---

## Section 5.7: Sample Processing (Shared Protocol for Phases 4–5)

1. **Quench:** Merge quench droplet (SDC/Tris-based lysis-denaturation buffer with TCEP/CAA for simultaneous reduction/alkylation) directly into the stimulated droplet at the programmed time. Refer to EasyPhos buffer. 
2. **Transfer:** Aspirate the merged droplet into a low-protein-binding tube or directly onto a nanoPOTS-type processing chip for phospho-peptide enrichment and TMT-labeling steps. Otherwise, transfer digests directly into pre-equilibrated Evotips.
3. To prevent SDC precipitation during digestion quenching (addition of formic acid), add 50-100% isopropanol to solubilize the SDC then quench; however, since the organic solvent concentration now is too high for efficient peptide binding to C18 in Evotips, dilute in water 0.1% FA (solvent A) and load onto evotips; run a quick control experiment to test different concentrations and compare protein yield.
4. **Digestion:** Trypsin, overnight, 37 °C, following standard SDC-compatible workflow. 
5. **Desalting:** Evotip loading.
6. **Phase 4 only — labeling and enrichment:** TMTpro labeling per manufacturer protocol scaled to peptide amount; Fe-IMAC or TiO₂ phosphopeptide enrichment on pooled multiplex.
7. **Phase 5 — no enrichment:** spike heavy PRM standards for the targeted peptide panel prior to LC-MS injection.
8. **LC-MS/MS:** nanoflow LC coupled to Orbitrap or equivalent; DIA for Phase 4, scheduled PRM for Phase 5.
