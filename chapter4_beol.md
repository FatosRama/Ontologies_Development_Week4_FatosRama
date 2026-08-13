# Chapter 4 – Backend / BEOL Integration

*HfO₂ FeRAM Production System — University of Pristina × Infineon*
*Ownership: Fatos Rama*

---

## 4.1 Module Purpose

The Backend-of-Line (BEOL) module receives the completed front-end stack — the CMOS access transistors and the ALD-deposited HfO₂/HZO ferroelectric capacitor module described in Chapters 2 and 3 — and builds the electrical wiring system that connects every memory cell and peripheral transistor to the chip's input/output pads. Conventional BEOL practice in copper-based logic and DRAM technology is to interconnect device terminals using a stack of tungsten contacts and copper dual-damascene metal levels separated by low-k interlayer dielectrics, planarized at every level by chemical mechanical polishing (CMP) and sealed at the top by a passivation stack [1, 2].

For an HfO₂/HZO-based FeRAM, the BEOL module additionally functions as a *thermal and chemical protection system* for the ferroelectric capacitor. The orthorhombic phase that gives HfO₂/HZO its ferroelectric response is metastable, and literature on BEOL-compatible ferroelectric capacitors consistently reports a maximum cumulative thermal budget on the order of 400–500 °C for the interconnect levels built above the capacitor, since higher post-capacitor anneal temperatures degrade remanent polarization and increase leakage [3, 4]. In addition, atomic hydrogen generated during dielectric deposition, plasma etching, and forming-gas anneal steps has been shown to diffuse into HfO₂/HZO films and passivate the oxygen vacancies that stabilize the ferroelectric phase, converting it toward the non-ferroelectric monoclinic phase and degrading polarization and endurance [5, 6]. The BEOL module purpose therefore combines two co-equal goals: (i) build a low-resistance, reliable multilevel wiring system, and (ii) enclose the ferroelectric capacitor in a hydrogen- and thermal-budget barrier from the first post-capacitor dielectric deposition through final passivation.

**Sources**
1. ScienceDirect Topics, *Dual Damascene* — https://www.sciencedirect.com/topics/engineering/dual-damascene
2. IMAPS 3D InCites, *Copper Dual Damascene for Wafer-Level Packaging* — https://www.3dincites.com/2025/08/copper-dual-damascene-for-wafer-level-packaging-enabling-reliable-high-density-interconnects/
3. Francois et al., *Demonstration of BEOL-compatible ferroelectric Hf0.5Zr0.5O2 scaled FeRAM co-integrated with 130 nm CMOS*, IEDM 2019 — https://www.researchgate.net/publication/339258516
4. *Zirconium-Rich Strategy in Ultrathin Hf0.5Zr0.5O2 toward BEOL-Compatible FeRAM* — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12622460/
5. *Effect of post-metallization anneal on monolithic co-integration of Hf0.5Zr0.5O2-based FeFET and CMOS*, Scientific Reports — https://www.nature.com/articles/s41598-025-02281-8
6. *HfO2-based ferroelectric thin film and memory device applications in the post-Moore era: A review*, PMC — https://pmc.ncbi.nlm.nih.gov/articles/PMC11197553/

> **Note on Nanya Technology as reference.** Nanya Technology's publicly disclosed process history is DRAM, not FeRAM. Nanya's disclosed BEOL practice is therefore cited in this chapter as an industry reference for *conventional copper/low-k interconnect processing* (Sections 4.3–4.4), not as a source for FeRAM-specific or thermal-budget-constrained BEOL claims. Nanya has publicly disclosed the adoption of copper metallization together with Applied Materials' Ultima HDP-CVD and Producer PECVD/SACVD systems for intermetal dielectric, STI, and passivation film deposition, and confirmed a copper-based interconnect scheme at the 42 nm DDR3 DRAM node [1, 2]. No Nanya publication identified in this research discloses layer-by-layer film thicknesses, CMP recipes, or via resistance targets; these remain general-industry values (Section 4.5) and are explicitly marked as such rather than attributed to Nanya.

**Sources**
1. Applied Materials, *Taiwan's Nanya Technology Chooses Applied Materials' Ultima and Producer CVD Systems for DRAM Production* — https://ir.appliedmaterials.com/news-releases/news-release-details/taiwans-nanya-technology-chooses-applied-materials-ultima-and
2. Micron Technology / Nanya Technology, *Micron and Nanya Unveil 42-Nanometer DRAM Process Technology* — https://investors.micron.com/news-releases/news-release-details/micron-nanya-unveil-42-nanometer-dram-process-technology-reduces

---

## 4.2 Input Condition

The BEOL module begins processing on a wafer that carries the completed front-end and high-k modules from Chapters 2–3: CMOS access transistors with silicided source/drain and gate contacts, and an array of TiN/HfO₂ (or HZO)/TiN metal-ferroelectric-metal (MFM) capacitors with their top and bottom electrodes exposed for contacting. Reported process flows for BEOL-integrated HfO₂-based capacitors define the capacitor module's own thermal budget ceiling (typically requiring crystallization anneals at or below approximately 500 °C for orthorhombic-phase stabilization) [1], which becomes the starting constraint that every subsequent BEOL step must respect. Publicly available sources reviewed for this chapter do not disclose the exact incoming topography, capacitor pitch, or electrode material stack used in the assigned FeRAM process; these parameters are treated as inherited from the Chapter 3 module and are not restated here.

**Sources**
1. Francois et al., IEDM 2019 (as above) — https://www.researchgate.net/publication/339258516

---

## 4.3 Step-by-Step Flow

### 4.3.1 Pre-Metal Dielectric and Planarization

A pre-metal dielectric (PMD) is deposited over the capacitor array and the peripheral CMOS transistors to electrically isolate the device layer from the first metal level. In FeRAM-specific integration schemes, an additional hydrogen-barrier encapsulation layer is deposited directly on the ferroelectric capacitor *before* the bulk PMD, since hydrogen released during subsequent dielectric depositions and anneals is a documented cause of ferroelectric degradation. A patent describing F-RAM encapsulation specifies an encapsulation layer (CVD/ALD/PVD AlOx or SiNx) followed by a distinct barrier layer of the same class of materials, each in the range of 50–1000 Å thick, deposited over the planarized ferroelectric oxide before the first metal (M1) layer is formed [1]. The PMD itself is then planarized by CMP to remove topography inherited from the capacitor array prior to contact patterning [1].

### 4.3.2 Contact Formation

Contact holes are patterned and etched through the PMD (and, where present, through the FEO barrier stack) down to the transistor source/drain, transistor gate, and capacitor top/bottom electrode nodes. Conventional practice fills these high-aspect-ratio contacts with CVD tungsten over a Ti/TiN liner, since tungsten offers strong resistance to electromigration, hillock formation, and humidity-induced corrosion, and can be deposited with good step coverage into narrow contact holes; its principal drawback is a comparatively high resistivity of roughly 6–15 µΩ·cm relative to copper [2]. Excess tungsten is removed by CMP, leaving planarized contact plugs level with the PMD surface.

### 4.3.3 Metal 1 Formation

The first copper wiring level is formed by damascene patterning: a dielectric layer is deposited over the contact level, trenches are lithographically defined and etched, a conformal diffusion-barrier/seed layer is deposited to line the trench, and copper is electroplated to fill it. Because copper is not self-passivating and diffuses readily through silicon dioxide, a continuous barrier liner is required around every copper feature to protect the underlying active devices from copper contamination [3]. Excess plated copper and barrier material are removed by CMP, leaving planarized M1 lines flush with the dielectric.

### 4.3.4 Via Formation

Interlevel vias connecting M1 to M2 (and each subsequent metal pair) are formed using the same dual-damascene principle as the trenches: via holes and the overlying trench are patterned into one or two dielectric layers (via-first or trench-first sequencing), lined with a diffusion barrier, and filled with copper in a single plating step, so that the via and the wiring line above it form one continuous copper body with no via/line interface [4, 5].

### 4.3.5 Repeated Interconnect Stack

The via/trench/barrier/plate/CMP sequence of Sections 4.3.3 and 4.3.4 is repeated to build up the required number of metal levels. Each dielectric level typically also carries a thin RIE-stop / copper-diffusion-barrier film (silicon dioxide, fluorinated oxide, or a SiCxHy(Nz) dielectric barrier) between metal levels to protect against barrier-scratch and copper-diffusion defects propagating into the next damascene level [6].

### 4.3.6 Upper-Level Global Routing

The uppermost one or two metal levels are generally drawn with wider line/space dimensions than the fine-pitch levels directly above the memory array, since their role is global signal routing, clock/power distribution, and connection to the bond-pad ring rather than dense local interconnect. Publicly available sources reviewed for this chapter do not disclose an FeRAM-specific global-routing rule set; the general practice of progressively coarsening pitch at upper metal levels, common to copper BEOL stacks, is stated here as general industry practice rather than a verified process-specific rule.

### 4.3.7 Passivation and Pad Opening

After the final copper level, a passivation stack — typically a combination of a hydrogen/moisture diffusion barrier (e.g. silicon nitride or oxynitride) and an overlying protective oxide/nitride — is deposited over the full wafer and then opened over the bond-pad locations to allow electrical probing and wire bonding. For FeRAM devices, this passivation step is also the final line of hydrogen-barrier defense for the ferroelectric capacitor beneath the interconnect stack, consistent with the documented sensitivity of HfO₂/HZO to hydrogen exposure throughout back-end processing [7].

### 4.3.8 Wafer Probe and Test Handoff

Following pad opening, the wafer is handed off to wafer-level electrical test (parametric test and initial functional/memory test), where contact, via, and line test structures placed in the scribe lines (Section 4.6) are measured before the wafer proceeds to dicing and packaging.

**Table 4.1 — Ordered Backend/BEOL process steps**

| Order | Process step | Purpose | Method type | Output / next input |
|---|---|---|---|---|
| 1 | Hydrogen-barrier encapsulation & PMD deposition | Isolate capacitor & transistors; block H diffusion | ALD/CVD dielectric deposition, CMP | Planarized PMD surface |
| 2 | Contact formation | Connect S/D, gate, and capacitor electrodes to M1 | Litho/etch, Ti/TiN liner, CVD-W fill, CMP | Planarized W contact plugs |
| 3 | Metal 1 formation | First wiring level | Damascene litho/etch, barrier/seed, Cu electroplating, CMP | Planarized M1 lines |
| 4 | Via formation | Connect Mn to Mn+1 | Dual-damascene litho/etch, barrier/seed, Cu plating, CMP | Cu via + line (single fill) |
| 5 | Repeated interconnect stack | Build required metal-level count | Repeat of steps 3–4 with inter-level barrier dielectric | Multilevel Cu stack |
| 6 | Upper-level global routing | Power/clock/global signal distribution | Coarser-pitch damascene levels | Routed top metal |
| 7 | Passivation & pad opening | Seal stack; expose bond pads | PECVD nitride/oxide, litho/etch | Passivated die with open pads |
| 8 | Wafer probe & test handoff | Verify contact/via/line integrity | Wafer-level parametric/functional test | Tested wafer to dicing |

**Sources**
1. *Enhanced hydrogen barrier encapsulation method for the control of hydrogen induced degradation of ferroelectric capacitors in an F-RAM process*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8916434
2. *Dual damascene interconnect* (tungsten resistivity/electromigration), US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6724089
3. *Microelectronics BEOL reliability basics and evolution*, ResearchGate — https://www.researchgate.net/publication/261343507
4. *Method of low-K/copper dual damascene*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6309957
5. ScienceDirect Topics, *Dual Damascene* — https://www.sciencedirect.com/topics/engineering/dual-damascene
6. *Dual damascene copper interconnect to a damascene tungsten wiring level*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6566242
7. *HfO2-based ferroelectric thin film and memory device applications in the post-Moore era: A review*, PMC — https://pmc.ncbi.nlm.nih.gov/articles/PMC11197553/

---

## 4.4 Key Materials and Equipment

**Table 4.2 — Backend/BEOL materials and equipment**

| Step | Material or chemical | Equipment or capability | Role in the module |
|---|---|---|---|
| Hydrogen barrier | AlOx / SiNx / SiONx | ALD, CVD, or PVD dielectric deposition tool | Blocks hydrogen diffusion into the ferroelectric capacitor [4] |
| PMD/ILD | Silicon dioxide, low-k dielectric | PECVD, HDP-CVD (e.g. Ultima-class HDP tool used industry-wide, including at Nanya [1]) | Interlevel electrical isolation; parasitic capacitance reduction |
| Contacts | Ti/TiN liner + CVD tungsten | CVD tungsten deposition, CMP tool | Low-electromigration vertical connection to device terminals [2] |
| Metal lines/vias | Cu (barrier/seed + electroplate) | PVD barrier/seed, electroplating tool, CMP tool | Low-resistance multilevel wiring [3] |
| Diffusion barrier film | SiCxHy(Nz) or fluorinated oxide | PECVD | RIE-stop and copper-diffusion barrier between metal levels [5] |
| Passivation | Silicon nitride / oxynitride stack | PECVD | Moisture/hydrogen barrier and mechanical protection |

**Figure 4.1 — Backend/BEOL module process flow**

![Figure 4.1: Backend/BEOL module process flow, showing steps 1-8 from hydrogen-barrier encapsulation through wafer probe/test handoff, with the hydrogen and thermal-budget guard band spanning steps 1-7](figure4_1_beol_process_flow.png)

*Based on sources [1], [2], and [3] below. The dashed guard band indicates the hydrogen- and thermal-budget protection requirement that spans the module (Sections 4.1, 4.3.1, 4.5.5); no authoritative Nanya-specific or FeRAM-specific process-flow figure was located in the sources reviewed, so this schematic is an original construction from the step sequence in Table 4.1.*

**Sources**
1. Applied Materials, Nanya Ultima/Producer CVD systems — https://ir.appliedmaterials.com/news-releases/news-release-details/taiwans-nanya-technology-chooses-applied-materials-ultima-and
2. *Dual damascene interconnect*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6724089
3. ScienceDirect Topics, *Dual Damascene* — https://www.sciencedirect.com/topics/engineering/dual-damascene
4. *Enhanced hydrogen barrier encapsulation method for the control of hydrogen induced degradation of ferroelectric capacitors in an F-RAM process*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8916434
5. *Dual damascene copper interconnect to a damascene tungsten wiring level*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6566242

> *Note: sources 4 and 5 above (the hydrogen-barrier encapsulation patent and the tungsten wiring-level patent) support the "Hydrogen barrier" and "Diffusion barrier film" table rows respectively; they were added here to keep every table citation traceable to a listed source, consistent with the chapter's citation requirements.*

---

## 4.5 Critical Parameters

### 4.5.1 Contact and Via Resistance

Tungsten's bulk resistivity is reported at approximately 6–15 µΩ·cm, materially higher than copper, which is why contacts use tungsten (for electromigration and fill robustness into high-aspect-ratio holes) while wiring and vias use copper [1]. Publicly available sources reviewed here do not disclose a numeric per-contact or per-via resistance target for any specific Nanya or FeRAM process node; such targets are process-node-specific and are not publicly disclosed / not verified in the sources reviewed.

### 4.5.2 Line Resistance and Capacitance

BEOL RC delay — the combination of copper line resistance and interlevel dielectric capacitance — is widely reported as a dominant performance limiter as interconnect critical dimensions shrink, motivating the industry shift to copper and low-k dielectrics in place of aluminum and SiO₂ [4, 6]. Exact resistance-per-length or capacitance-per-length values are technology-node- and layer-specific and are not disclosed in the sources reviewed for this chapter.

### 4.5.3 Overlay and Critical Dimensions

As interconnect pitch shrinks, via-to-trench overlay control becomes increasingly critical; at advanced nodes, industry sources report that tight-pitch metal patterning required multi-patterning techniques to hold overlay and CD control, e.g. imec's demonstration of 12 nm trench CD at 16 nm half-pitch [4]. No process-specific overlay/CD specification for the assigned FeRAM process was located.

### 4.5.4 CMP Planarity

CMP is used at every damascene level to remove excess metal and produce a flat, coplanar surface required for reliable multilevel stacking [7]. For hydrogen-barrier-encapsulated ferroelectric oxide layers specifically, CMP planarization of the ferroelectric oxide is performed before the encapsulation and barrier layers are deposited, so that the M1 layer sits on a planar surface [5].

### 4.5.5 Thermal Budget

This is the parameter most specific to FeRAM BEOL integration. Reported BEOL-compatible HfO₂/HZO ferroelectric capacitor demonstrations specify a maximum thermal budget below approximately 500 °C for the full back-end stack built above the capacitor [2]. Separately, HZO integration work has demonstrated ferroelectric-phase stabilization at processing temperatures as low as 300 °C using oxygen-vacancy engineering, illustrating that the achievable thermal budget is strongly dependent on the specific capacitor engineering used rather than being a single fixed industry number [3]. No Nanya-specific or FeRAM-assigned-process thermal budget figure was located in the sources reviewed.

**Table 4.3 — Backend/BEOL critical parameters**

| Step | Parameter | Unit | Value or range | Evidence status / source |
|---|---|---|---|---|
| Contact | Tungsten resistivity | µΩ·cm | ~6–15 | General industry value [1] |
| Post-capacitor BEOL | Cumulative thermal budget | °C | ≲500 (BEOL-compatible HZO demo) | General industry / research demo, not Nanya-specific [2] |
| Post-capacitor BEOL | Reduced-thermal-budget HZO demo | °C | ~300 (with O-vacancy engineering) | General research demo, not Nanya-specific [3] |
| Metal pitch (advanced node ref.) | Trench CD at 16 nm half-pitch | nm | 12 | General industry (imec), not Nanya/FeRAM-specific [4] |
| Encapsulation/barrier layer | FEO encapsulation & barrier thickness | Å | 50–1000 | General industry (F-RAM patent), not Nanya-specific [5] |
| Nanya-specific contact/via resistance | — | — | Not publicly disclosed | Not verified in sources reviewed |

**Sources**
1. *Dual damascene interconnect*, US Patent (tungsten resistivity) — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/6724089
2. Francois et al., IEDM 2019 — https://www.researchgate.net/publication/339258516
3. *Region-Selective Oxygen Vacancy Engineering for Ferroelectric Hf0.5Zr0.5O2 Thin Films Processed at 300 °C*, ACS Appl. Mater. Interfaces — https://pubs.acs.org/doi/10.1021/acsami.5c08743
4. imec, *How to solve the BEOL RC delay problem?* — https://sst.semiconductor-digest.com/2017/11/how-to-solve-the-beol-rc-delay-problem/
5. *Enhanced hydrogen barrier encapsulation method...*, US Patent — https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8916434
6. *Copper interconnect electromigration behaviors...*, ScienceDirect — https://www.sciencedirect.com/science/article/abs/pii/S0026271404005074
7. IMAPS 3D InCites, *Copper Dual Damascene for Wafer-Level Packaging* — https://www.3dincites.com/2025/08/copper-dual-damascene-for-wafer-level-packaging-enabling-reliable-high-density-interconnects/

> *Note: source 7 above (IMAPS 3D InCites) supports the CMP Planarity claim in 4.5.4; it was added here to keep that citation traceable to a listed source.*

---

## 4.6 Metrology and Electrical Tests

### 4.6.1 Contact and Via-Chain Tests

Contact and via integrity is commonly verified using daisy-chain and four-point Kelvin structures placed in scribe-line test macros; daisy chains give a cumulative resistance measurement across many contacts/vias in series, while Kelvin structures isolate the resistance of a single contact/via for more precise per-feature characterization [1].

### 4.6.2 Line-Resistance and Defect Inspection

Sheet and line resistance are measured on dedicated test structures, complemented by optical/SEM defect inspection of the copper lines; interface and line-edge-roughness effects on line resistance have been reported as a significant contributor to BEOL reliability variation as CDs shrink [2].

### 4.6.3 CMP Thickness and Planarity Mapping

Post-CMP film thickness and planarity are mapped across the wafer (e.g. by optical or profilometric metrology) to detect dishing, erosion, or incomplete clearing of the polished metal/dielectric surface before the next damascene level is built [3].

### 4.6.4 RC and Signal-Integrity Tests

Comb/serpentine RC test structures are used to extract line resistance and interlevel/intralevel capacitance, tracking the RC-delay trends that motivate copper/low-k adoption and multi-patterning at advanced nodes [4].

### 4.6.5 Electromigration and Dielectric Reliability

Electromigration lifetime is evaluated with wafer-level isothermal or accelerated stress tests on daisy-chain/Kelvin structures, extracting current acceleration factors and activation energy for lifetime extrapolation [1]. Time-dependent dielectric breakdown (TDDB) of the interlevel dielectric is tracked alongside electromigration as a co-equal BEOL reliability failure mechanism at advanced nodes [5].

### 4.6.6 Final Wafer Test

After passivation and pad opening, the wafer proceeds to parametric and functional probe test, verifying interconnect continuity/resistance specifications and initial memory-cell functionality before dicing. Publicly available sources reviewed for this chapter do not disclose a Nanya-specific or FeRAM-assigned-process final-test specification.

**Table 4.4 — Backend/BEOL metrology and electrical tests**

| Step or checkpoint | Measurement or test | Acceptance measure | Decision or process response |
|---|---|---|---|
| Contact/via level | Daisy-chain / Kelvin resistance | Within target resistance window (process-specific; not publicly disclosed) | Rework or scrap lot if out of window |
| Metal line level | Sheet/line resistance + defect inspection | Line resistance and defect density within spec | Flag lot for inspection or rework |
| CMP level | Thickness / planarity mapping | No dishing/erosion beyond process limit | Re-polish or scrap if out of spec |
| Multilevel stack | RC comb/serpentine structures | RC delay within design target | Feed back to process/design co-optimization |
| Reliability qualification | EM stress test, TDDB test | Lifetime projection meets qualification target | Gate process release |
| Final wafer test | Parametric + functional probe | Interconnect continuity and memory functionality pass | Bin wafer for dicing/packaging |

**Sources**
1. *TSI test structures* (Kelvin/daisy-chain BEOL characterization), ResearchGate — https://www.researchgate.net/figure/TSI-test-structures-a-meander-fork-structure-b-four-port-Kelvin-structure-for_fig21_282600116
2. *Exploration of baking temperature effects on 28 nm BEOL reliability*, ScienceDirect — https://www.sciencedirect.com/science/article/abs/pii/S002627141730063X
3. IMAPS 3D InCites, *Copper Dual Damascene for Wafer-Level Packaging* — https://www.3dincites.com/2025/08/copper-dual-damascene-for-wafer-level-packaging-enabling-reliable-high-density-interconnects/
4. imec, *How to solve the BEOL RC delay problem?* — https://sst.semiconductor-digest.com/2017/11/how-to-solve-the-beol-rc-delay-problem/
5. *Microelectronics BEOL reliability basics and evolution*, ResearchGate — https://www.researchgate.net/publication/261343507

---

## 4.7 Ontology Model and Communication

### 4.7.1 Protégé Ontology Design
### 4.7.2 Classes and Properties
### 4.7.3 Individuals and Example Records
### 4.7.4 Digital Reference Mapping
### 4.7.5 Reasoner and Validation Results
### 4.7.6 Ontology Limitations

**[NOT COMPLETED — REQUIRES YOUR OWL/Protégé FILE]** This subsection set (4.7.1–4.7.6, matching the template's numbering) cannot be research-filled from public web sources: it documents *your own* Protégé ontology of the BEOL module (classes, object/data properties, individuals, Digital Reference IRI mappings, and reasoner output). Inventing class names, IRIs, or reasoner results here would violate the no-fabrication requirement, since these are artifacts of your own modelling work, not externally verifiable facts. Once you export your ontology (classes list, individuals, and any competency-question / reasoner log), I can help you turn that directly into Tables 4.5–4.7 and the accompanying text and figures (4.2–4.3) in the same format as this chapter.
