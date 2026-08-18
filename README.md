# Awesome Semiconductor Industry Topics [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

> A curated map of the modern semiconductor industry, with a deliberate bias toward the two places
> where the hardest engineering now happens: **logic below 10 nm** and **inside the package**.

Most "awesome semiconductor" lists are really awesome-RTL lists — they stop at the GDSII handoff.
This one starts there and keeps going: how the pattern actually gets onto silicon, how atoms get
added and removed, how the die gets measured, thinned, bonded, stacked, and cooled, and how the
factory that does all of it is scheduled and financed.

Everything here is a link to something you can read, run, download, or attend. Where a topic is
dominated by proprietary tools, the list says so rather than pretending an open-source equivalent
exists.

**Scope**

- ✅ Advanced logic scaling (FinFET → GAA nanosheet → forksheet → CFET), lithography, process
  modules, metrology, memory, **advanced packaging and chiplets**, TCAD, EDA for 3D, fab
  operations, test, reliability, and the economics/policy layer around all of it.
- ✅ Open-source tools, public datasets, benchmark suites, standards, roadmaps, and papers.
- ⚠️ Not a startup database — for that see [awesome-semiconductor-startups](https://github.com/aolofsson/awesome-semiconductor-startups).
- ⚠️ Not an RTL/HDL list — for that see [awesome-opensource-hardware](https://github.com/aolofsson/awesome-opensource-hardware).

**A note on node names.** "3 nm", "2 nm", "A16", "18A" are marketing names, not physical
dimensions. Nothing in a modern logic node measures the number in its name. When precision matters
this list uses the physical parameters that actually scale: contacted poly pitch (CPP), metal pitch
(MP), cell height in tracks, and fin/sheet count.

---

## Contents

- [1. Start Here](#1-start-here)
- [2. Roadmaps and Standards Bodies](#2-roadmaps-and-standards-bodies)
- [3. Advanced Logic Scaling](#3-advanced-logic-scaling)
  - [Node Roadmaps by Foundry](#node-roadmaps-by-foundry)
  - [Transistor Architectures](#transistor-architectures)
  - [Backside Power Delivery](#backside-power-delivery)
  - [Interconnect and BEOL Scaling](#interconnect-and-beol-scaling)
  - [DTCO, STCO and Standard Cells](#dtco-stco-and-standard-cells)
  - [Beyond-CMOS Channels and 2D Materials](#beyond-cmos-channels-and-2d-materials)
- [4. Lithography and Patterning](#4-lithography-and-patterning)
  - [EUV Fundamentals](#euv-fundamentals)
  - [High-NA and Hyper-NA](#high-na-and-hyper-na)
  - [Sources, Optics, Masks and Pellicles](#sources-optics-masks-and-pellicles)
  - [Photoresists and Stochastics](#photoresists-and-stochastics)
  - [Multi-Patterning, DSA and Nanoimprint](#multi-patterning-dsa-and-nanoimprint)
  - [Computational Lithography](#computational-lithography)
  - [Open-Source Lithography Code](#open-source-lithography-code)
- [5. Process Modules, Materials and Equipment](#5-process-modules-materials-and-equipment)
  - [Deposition](#deposition)
  - [Etch](#etch)
  - [CMP, Cleans, Implant, Anneal and Epitaxy](#cmp-cleans-implant-anneal-and-epitaxy)
  - [Materials, Precursors and Gases](#materials-precursors-and-gases)
  - [Wafer Fab Equipment Landscape](#wafer-fab-equipment-landscape)
- [6. Metrology, Inspection and Yield](#6-metrology-inspection-and-yield)
  - [Dimensional and Compositional Metrology](#dimensional-and-compositional-metrology)
  - [Defect Inspection and Review](#defect-inspection-and-review)
  - [Yield Modeling and Process Control](#yield-modeling-and-process-control)
- [7. Memory Technology](#7-memory-technology)
- [8. Advanced Packaging](#8-advanced-packaging)
  - [Primers and Taxonomy](#primers-and-taxonomy)
  - [2.5D Interposers and Bridges](#25d-interposers-and-bridges)
  - [3D Stacking and Hybrid Bonding](#3d-stacking-and-hybrid-bonding)
  - [Fan-Out and Panel-Level Packaging](#fan-out-and-panel-level-packaging)
  - [Substrates, Glass and RDL](#substrates-glass-and-rdl)
  - [TSVs, Bumps and Bonding Equipment](#tsvs-bumps-and-bonding-equipment)
  - [Thermal, Power and Mechanical Integrity](#thermal-power-and-mechanical-integrity)
  - [Co-Packaged Optics](#co-packaged-optics)
  - [Packaging Supply Chain and OSATs](#packaging-supply-chain-and-osats)
- [9. Chiplets and Die-to-Die Interfaces](#9-chiplets-and-die-to-die-interfaces)
  - [Interface Standards](#interface-standards)
  - [Open-Source Chiplet IP](#open-source-chiplet-ip)
  - [Chiplet Economics and Cost Models](#chiplet-economics-and-cost-models)
  - [Architecture Exploration Tools](#architecture-exploration-tools)
- [10. Design and EDA for Advanced Nodes and 3D](#10-design-and-eda-for-advanced-nodes-and-3d)
  - [Commercial 3D-IC and Packaging Flows](#commercial-3d-ic-and-packaging-flows)
  - [Open-Source RTL-to-GDS](#open-source-rtl-to-gds)
  - [Open-Source PDKs and Shuttles](#open-source-pdks-and-shuttles)
  - [3D Floorplanning and Physical Design Research](#3d-floorplanning-and-physical-design-research)
  - [Layout, Extraction and Signoff Utilities](#layout-extraction-and-signoff-utilities)
- [11. TCAD and Physical Simulation](#11-tcad-and-physical-simulation)
  - [Commercial TCAD](#commercial-tcad)
  - [Open-Source TCAD and Process Emulation](#open-source-tcad-and-process-emulation)
  - [Atomistic and First-Principles](#atomistic-and-first-principles)
  - [Electromagnetics and Photonics](#electromagnetics-and-photonics)
- [12. AI and Machine Learning for Semiconductors](#12-ai-and-machine-learning-for-semiconductors)
  - [ML for EDA](#ml-for-eda)
  - [ML for Lithography and Masks](#ml-for-lithography-and-masks)
  - [ML for Fab, Metrology and Yield](#ml-for-fab-metrology-and-yield)
  - [LLMs for Chip Design](#llms-for-chip-design)
  - [Datasets and Benchmarks](#datasets-and-benchmarks)
- [13. Fab Operations and Manufacturing Science](#13-fab-operations-and-manufacturing-science)
  - [Factory Physics and Cycle Time](#factory-physics-and-cycle-time)
  - [Scheduling, Dispatching and Simulators](#scheduling-dispatching-and-simulators)
  - [SEMI Standards and Equipment Integration](#semi-standards-and-equipment-integration)
  - [Cleanroom, Facilities and Sustainability](#cleanroom-facilities-and-sustainability)
- [14. Test, Reliability and Hardware Security](#14-test-reliability-and-hardware-security)
  - [Test and DFT](#test-and-dft)
  - [Reliability Physics](#reliability-physics)
  - [Hardware Security and Supply Chain Trust](#hardware-security-and-supply-chain-trust)
- [15. Economics, Markets and Policy](#15-economics-markets-and-policy)
- [16. Learning Resources](#16-learning-resources)
  - [Books](#books)
  - [Courses and Lecture Series](#courses-and-lecture-series)
  - [Video and Podcasts](#video-and-podcasts)
  - [Newsletters and Analysis](#newsletters-and-analysis)
- [17. Conferences, Journals and Communities](#17-conferences-journals-and-communities)
- [18. Research Institutes and Consortia](#18-research-institutes-and-consortia)
- [19. Industry Map](#19-industry-map)
- [20. DIY and Garage Fab](#20-diy-and-garage-fab)
- [21. Related Awesome Lists](#21-related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

---

## 1. Start Here

If you are new to the field, read in this order. Each of these is free and gives you the vocabulary
for everything below.

- [IRDS — International Roadmap for Devices and Systems](https://irds.ieee.org/editions) — The
  successor to the ITRS. Free PDF chapters covering More Moore, Beyond CMOS, Lithography,
  Metrology, Packaging Integration, and Systems and Architectures. The single best free orientation
  to where the industry thinks it is going.
- [Heterogeneous Integration Roadmap (HIR)](https://eps.ieee.org/technology/heterogeneous-integration-roadmap/) —
  IEEE EPS 20+ chapter roadmap dedicated entirely to packaging and integration. Free download,
  updated on a rolling basis.
- [Semiconductor Engineering Knowledge Center](https://semiengineering.com/knowledge-center/) —
  Encyclopedia-style entries for essentially every term in this list, each linked to the news
  articles that use it.
- [imec Technology Articles](https://www.imec-int.com/en/expertise) — The research institute that
  most of the industry co-funds, explaining its own results in plain language. Best free source on
  CFET, backside power, semi-damascene, and 2D materials.
- [Asianometry — Semiconductor playlist](https://www.youtube.com/@Asianometry) — Long-form video
  explainers on fab history, equipment, and geopolitics. Unusually well-sourced.
- [Construction Physics — Semiconductor fab reading list](https://www.construction-physics.com/p/semiconductor-fab-reading-list) —
  An annotated reading list for understanding fabs as physical, capital-intensive factories.
- [Chips and Cheese](https://chipsandcheese.com/) — Independent microarchitecture and silicon
  analysis. The best free source on what shipping chips actually do, as opposed to what their
  datasheets claim.
- [TechInsights](https://www.techinsights.com/) — Reverse-engineering firm whose
  public blog posts frequently reveal actual as-built dimensions of shipping nodes.

**How to read a node.** The parameters that matter, in rough order of importance: contacted poly
pitch (CPP / gate pitch), minimum metal pitch (MMP / M0 pitch), standard cell height in metal
tracks, number of fins or sheets per device, SRAM bit-cell area, and whether power is delivered
front-side or backside. Everything else is marketing.

---

## 2. Roadmaps and Standards Bodies

### Roadmaps

- [IRDS 2023/2025 Editions](https://irds.ieee.org/editions) — Free, chapter-by-chapter. Start with
  *More Moore* and *Lithography*.
- [Heterogeneous Integration Roadmap](https://eps.ieee.org/technology/heterogeneous-integration-roadmap/) —
  Chapters on Single-Chip and Multi-Chip Integration, 2.5D/3D, Interconnects for 2D/3D, Thermal,
  Test, Reliability, Co-Design, and Photonics.
- [SEMI — Heterogeneous Integration Roadmap community](https://www.semi.org/en/communities/heterogeneous_integration_roadmap) —
  SEMI's landing page for HIR participation.
- [ITRS Archive (2.0, 2015)](https://www.semiconductors.org/resources/2015-international-technology-roadmap-for-semiconductors-itrs/) — The historical roadmap. Still worth reading
  for how the industry framed scaling before the "equivalent scaling" era.
- [OCP Open Domain-Specific Architecture (ODSA)](https://www.opencompute.org/wiki/Server/ODSA) — Open
  Compute Project workstream that produced Bunch of Wires and much of the early open chiplet
  ecosystem work.

### Standards Bodies

- [SEMI Standards](https://www.semi.org/en/products-services/standards) — The ~1,000-document body
  governing wafer dimensions, equipment communication (E30/E37/E5), carrier and FOUP interfaces
  (E47), facilities, safety (S2/S8), and traceability. Individual standards are paid; the index and
  scope statements are free.
- [JEDEC](https://www.jedec.org/standards-documents) — Memory and packaging standards: DDR5, LPDDR6,
  HBM (JESD270 series), package outlines (JEP/MO), and reliability test methods (JESD22, JESD47,
  JEP122 for failure mechanisms). Free registration to download.
- [IPC](https://www.ipc.org/ipc-standards) — Substrate, board, and assembly standards; increasingly
  relevant as packaging substrates become the bottleneck.
- [IEEE Standards Association — Electronics Packaging](https://standards.ieee.org/) — Home of IEEE
  1838 (3D test access), 1687 (IJTAG), 1149.1 (JTAG), 2851, and the P3405 chiplet family.
- [Open Compute Project](https://www.opencompute.org/) — Where hyperscaler-driven packaging,
  chiplet, and co-packaged-optics requirements get published before they become products.
- [UCIe Consortium](https://www.uciexpress.org/) — Universal Chiplet Interconnect Express
  specification and compliance program.
- [Optical Internetworking Forum (OIF)](https://www.oiforum.com/) — Electrical and optical
  interface implementation agreements (CEI-112G/224G, co-packaged optics frameworks).
- [Si2 (Silicon Integration Initiative)](https://si2.org/) — OpenAccess, OpenPDK, and the
  Compact Model Coalition (BSIM-CMG for FinFET/GAA).
- [Compact Model Coalition — BSIM Group](https://bsim.berkeley.edu/) — BSIM-CMG is the industry
  standard compact model for FinFET and gate-all-around devices. Source code is downloadable.

---

## 3. Advanced Logic Scaling

Everything in this section is about the front end of line and middle of line at pitches where
single-exposure patterning has run out and electrostatics no longer come for free.

### Node Roadmaps by Foundry

- [TSMC Technology Roadmap](https://www.tsmc.com/english/dedicatedFoundry/technology/logic) —
  Official N7 / N5 / N3 / N2 / A16 / A14 descriptions. A16 introduces Super Power Rail (TSMC's
  backside power delivery); A14 is the first TSMC node targeted at High-NA.
- [Intel Foundry Process Technology](https://www.intel.com/content/www/us/en/foundry/process.html) —
  Intel 7 / 4 / 3 / 18A / 14A. Intel 18A pairs RibbonFET (GAA) with PowerVia (backside power) and
  was the first node to ship with backside power delivery in volume.
- [Samsung Foundry Process](https://semiconductor.samsung.com/foundry/process-technology/) —
  SF4 / SF3 / SF2 / SF1.4. Samsung was first to production with GAA (MBCFET) at 3 nm.
- [Rapidus](https://www.rapidus.inc/en/) — Japan's 2 nm greenfield effort with IBM and imec;
  notable for a single-wafer, no-batch, fully-AI-scheduled fab concept.
- [Wikipedia — 2 nm and 3 nm process](https://en.wikipedia.org/wiki/2_nm_process) — Unglamorous but
  well-sourced cross-foundry tables of announced CPP, metal pitch, and density, with citations back
  to the original IEDM and press disclosures.
- [SemiAnalysis — foundry process deep dives](https://semianalysis.com/) — Paid, but the free posts
  are the most detailed public accounting of node economics and wafer pricing.

### Transistor Architectures

- [imec — CFET (complementary FET)](https://www.imec-int.com/en/articles/imec-puts-complementary-fet-cfet-logic-technology-roadmap) —
  The architecture that stacks an nFET directly on a pFET. imec targets monolithic CFET around the
  A7 node, with monolithic and sequential integration flows differing sharply in thermal budget.
- [imec — Outer wall forksheet](https://www.imec-int.com/en/articles/outer-wall-forksheet-bridge-nanosheet-and-cfet-device-architectures-logic-technology) —
  The bridge device between nanosheet and CFET, intended to extend the nanosheet roadmap to roughly
  the A10 node with easier fabrication than the inner-wall forksheet.
- [imec — Scaling monolithic CFET across multiple nodes](https://www.imec-int.com/en/articles/performance-boosters-scale-monolithic-cfet-across-multiple-logic-technology-nodes) —
  What has to be true (channel stress, contact resistance, middle dielectric isolation) for CFET to
  scale rather than merely exist.
- [Intel RibbonFET](https://www.intel.com/content/www/us/en/newsroom/news/intel-unveils-ribbonfet-powervia.html) —
  Intel's gate-all-around implementation.
- [Samsung MBCFET](https://semiconductor.samsung.com/foundry/process-technology/) —
  Multi-Bridge Channel FET, the first GAA device in high-volume manufacturing.
- [EE Times — VLSI 2025: Outer Wall Forksheet](https://www.eetimes.com/vlsi-2025-outer-wall-forksheet-bridges-nanosheet-and-cfet-architectures/) —
  Readable conference coverage of the forksheet/CFET transition.
- [Semiconductor Digest — Performance boosters for monolithic CFET](https://www.semiconductor-digest.com/performance-boosters-to-scale-monolithic-cfet-across-multiple-logic-technology-nodes/) —
  Companion write-up with the device-level numbers.
- [Nanosheet vs FinFET — Semiconductor Engineering](https://semiengineering.com/knowledge_centers/integrated-circuit/transistors/3d/gate-all-around-fet/) —
  Knowledge-center entry with links to a decade of GAA coverage.

**Key primary sources.** The device papers themselves land at three venues every year:
[IEDM](https://www.ieee-iedm.org/) (December), the
[VLSI Symposium](https://www.vlsisymposium.org/) (June), and
[ECS/ECS Transactions](https://www.electrochem.org/) for the materials and process chemistry side.
IEDM short courses are the single densest tutorial material in the industry.

### Backside Power Delivery

Moving the power distribution network to the wafer backside frees front-side routing tracks for
signals, cuts IR drop, and decouples power and signal RC. It also requires extreme wafer thinning,
carrier bonding, and nano-TSVs in every standard cell — which is why it arrived with 18A/A16 and
not earlier.

- [imec — How to power chips from the backside](https://www.imec-int.com/en/articles/how-power-chips-backside) —
  The clearest free explanation of nano-TSV and buried power rail (BPR) flows.
- [imec — DTCO study of backside power delivery options](https://www.imec-int.com/en/articles/backside-power-delivery-options-dtco-study) —
  imec/Arm co-optimization comparing BPR-based and nTSV-only implementations.
- [Intel — PowerVia](https://www.intel.com/content/www/us/en/newsroom/news/intel-unveils-ribbonfet-powervia.html) —
  Intel reports 5–10% standard cell utilization improvement and up to ~4% ISO-power performance
  gain from decoupling power and signal routing.
- [TrendForce — Clearwater Forest 18A backside power at Hot Chips](https://www.trendforce.com/news/2025/08/27/news-intels-clearwater-forest-unveils-18a-backside-power-at-hot-chips-tsmcs-super-power-rail-to-follow/) —
  Where PowerVia and TSMC Super Power Rail stand relative to each other.
- [Tom's Hardware — PowerVia technical detail](https://www.tomshardware.com/news/intel-details-powervia-backside-power-delivery-network) —
  Good coverage of the test-vehicle results Intel published before productizing.
- [Semiconductor Engineering — Big changes in power delivery, materials, and interconnects](https://semiengineering.com/big-changes-ahead-in-power-delivery-materials-and-interconnects/) —
  Ties backside power to the interconnect metallization change happening at the same time.

### Interconnect and BEOL Scaling

Below roughly 20 nm metal pitch, copper's effective resistivity blows up because barrier and liner
thickness stop scaling and surface/grain-boundary scattering dominates. The industry's answers are
barrier-less metals (Ru, Mo), subtractive patterning, and airgaps.

- [imec — 16 nm pitch Ru lines by semi-damascene](https://www.imec-int.com/en/press/imec-demonstrates-16nm-pitch-ru-lines-record-low-resistance-obtained-using-semi-damascene) —
  Record-low line resistance at 16 nm pitch using a subtractive/semi-damascene flow.
- [imec — Semi-damascene with fully self-aligned vias at 18 nm metal pitch](https://www.imec-int.com/en/articles/imec-demonstrates-semi-damascene-interconnects-fully-self-aligned-vias-18nm-metal-pitch) —
  Fully self-aligned vias are what makes semi-damascene manufacturable.
- [Subtractive Ruthenium Interconnects with Airgap (IEEE)](https://ieeexplore.ieee.org/document/10873431) —
  The airgap integration that turns Ru's resistance advantage into an actual capacitance win.
- [IITC — International Interconnect Technology Conference](https://iitc-conference.org/) —
  The interconnect venue. Past programs are public and are the best index of what is being tried:
  [2025 program](https://iitc-conference.org/2025-iitc-program/),
  [2024 program](https://iitc-conference.org/2024-iitc-program/).
- [Semiconductor Engineering — Interconnects approach tipping point](https://semiengineering.com/interconnects-approach-tipping-point/) —
  Survey of the Cu → Ru/Mo transition and why it is happening now.
- [Spatially resolved conductivity of rectangular interconnects (arXiv)](https://arxiv.org/abs/2401.14366) —
  Physical modeling of surface scattering; useful if you want to compute rather than cite.

### DTCO, STCO and Standard Cells

Design-technology co-optimization is now where most of the "node" improvement comes from. Cell
height reduction, fin/sheet depopulation, buried rails, and via-pillar schemes deliver density that
lithography alone no longer does.

- [imec — Design-technology co-optimization](https://www.imec-int.com/en/expertise) —
  imec's DTCO program pages, including the standard-cell architectures used in their public studies.
- [Si2 OpenPDK / OpenAccess](https://si2.org/openaccess/) — Database standard underneath most
  commercial physical design tools.
- [ASAP7 Predictive PDK](https://asap.asu.edu/) — Arizona State / ARM 7 nm predictive PDK
  built on realistic EUV-era ground rules. The standard academic vehicle for sub-10 nm physical
  design research.
- [ASAP7 on GitHub](https://github.com/The-OpenROAD-Project/asap7) — Packaged for use with
  open-source flows.
- [FreePDK15](https://eda.ncsu.edu/freepdk/freepdk15/) — NCSU's 15 nm FinFET predictive kit.
- [BSIM-CMG](https://bsim.berkeley.edu/models/bsimcmg/) — Berkeley's common multi-gate compact
  model, the industry standard for FinFET and nanosheet SPICE models. Source available.
- [Semiconductor Engineering — System-technology co-optimization (STCO)](https://semiengineering.com/tag/dtco/) —
  Where DTCO stops and packaging-aware STCO begins.

### Beyond-CMOS Channels and 2D Materials

- [imec/ASML/TSMC — 300 mm 2D-material CMOS at 50 nm CPP](https://www.imec-int.com/en/press/asml-tsmc-and-imec-bring-industry-ready-2d-material-transistors-closer-breakthrough-300mm) —
  MoS₂ nFETs and WS₂/WSe₂ pFETs on the same 300 mm wafer at 50 nm contacted poly pitch, with 94% of
  transistors operational. The most significant lab-to-fab step 2D materials have taken.
- [imec — 2D-material devices in the logic scaling roadmap](https://www.imec-int.com/en/articles/introducing-2d-material-based-devices-logic-scaling-roadmap) —
  Where 2D channels plausibly enter: ultra-scaled logic, but also backend and wafer-backside
  devices.
- [Semiconductor Today — 300 mm integration route for 2D FETs](https://www.semiconductor-today.com/news_items/2026/jun/imec-asml-tsmc-220626.shtml) —
  Process-flow-level summary.
- [IRDS Beyond CMOS chapter](https://irds.ieee.org/editions) — Systematic comparison of tunnel
  FETs, spin devices, ferroelectric logic, and 2D materials against CMOS baselines.
- [Nature Electronics — 2D semiconductors collection](https://www.nature.com/subjects/two-dimensional-materials) —
  Primary literature aggregation.
- [Stanford SystemX / N3XT](https://systemx.stanford.edu/) — Carbon nanotube FETs, RRAM, and
  monolithic 3D as a system-level alternative to conventional scaling.

---

## 4. Lithography and Patterning

### EUV Fundamentals

- [ASML — EUV lithography systems](https://www.asml.com/en/products/euv-lithography-systems) —
  Product pages for the NXE 0.33 NA platform, including throughput and overlay specifications.
- [ASML — Technology explained](https://www.asml.com/en/technology) — Vendor-authored but
  genuinely good tutorials on how the source, optics, reticle stage, and wafer stage work together.
- [IRDS Lithography chapter](https://irds.ieee.org/editions) — Vendor-neutral resolution,
  overlay, and CD-uniformity requirements per node, with the multi-patterning decision tree.
- [SPIE Advanced Lithography + Patterning](https://spie.org/conferences-and-exhibitions/advanced-lithography-and-patterning) —
  The conference where every EUV result is first published. Proceedings are paywalled; abstracts
  and program are free and are a useful index.
- [Chris Mack — Lithography resources](https://www.lithoguru.com/) — Decades of free lecture notes,
  the *Field Guide to Optical Lithography*, and the definitive plain-English writing on resolution,
  DOF, and stochastic effects.
- [Lithography basics — Semiconductor Engineering](https://semiengineering.com/knowledge_centers/manufacturing/lithography/) —
  Aggregated coverage with the EUV/DUV/multi-patterning terminology defined.

### High-NA and Hyper-NA

0.55 NA anamorphic optics buy roughly 8 nm single-exposure resolution — a step that avoids EUV
double patterning at the tightest pitches — at the cost of a half-field (26 × 16.5 mm) exposure,
which forces field stitching for large dies.

- [ASML — EXE:5000 / High-NA EUV](https://www.asml.com/en/products/euv-lithography-systems) —
  Specifications for the first-generation High-NA platform.
- [Intel — High-NA EUV in the foundry](https://newsroom.intel.com/intel-foundry/intel-foundry-opens-new-frontier-chipmaking) —
  Intel's account of installing and qualifying the first commercial High-NA tools.
- [Tom's Hardware — First commercial EXE:5200B installation](https://www.tomshardware.com/tech-industry/semiconductors/intel-installs-industrys-first-commercial-high-na-euv-lithography-tool-asml-twinscan-exe-5200b-sets-the-stage-for-14a) —
  Where High-NA sits relative to Intel 14A.
- [Tom's Hardware — ASML lithography roadmap from DUV to Hyper-NA](https://www.tomshardware.com/tech-industry/semiconductors/asml-lithograpy-roadmap-examined-from-duv-to-hyper-na) —
  The full scanner roadmap in one place, including what Hyper-NA (>0.55) would require.
- [Anamorphic imaging and field stitching](https://www.lithoguru.com/scientist/essays/) — Mack's
  essays on why anamorphic optics halve the field and what that costs designers.

**Design consequence worth internalizing:** a half-field High-NA reticle means reticle-limited die
area drops to roughly 429 mm². This is one of the strongest structural forces pushing large designs
toward chiplets — see [section 9](#9-chiplets-and-die-to-die-interfaces).

### Sources, Optics, Masks and Pellicles

- [EUV source technology — laser-produced plasma](https://www.asml.com/en/technology/lithography-principles) —
  Tin droplets, pre-pulse/main-pulse CO₂ lasers, collector mirror lifetime, and why source power is
  the throughput limiter.
- [Photomask technology at SPIE](https://spie.org/conferences-and-exhibitions/photomask-technology-and-euv-lithography) —
  Mask blanks, absorber materials, defect repair, and curvilinear mask writing.
- [Low-n and high-k EUV absorbers](https://semiengineering.com/tag/euv-masks/) —
  Replacing TaBN absorbers to reduce mask-3D effects at High-NA.
- [Multi-beam mask writers](https://www.ims.co.at/) — IMS Nanofabrication; curvilinear ILT masks
  are only writable because multi-beam writers decoupled write time from shot count.
- [EUV pellicles](https://semiengineering.com/euv-pellicles-finally-ready/) — Transmission,
  thermal load, and why pellicles were the long pole for EUV defectivity.
- [Mask 3D effects](https://www.lithoguru.com/scientist/essays/) — Why a reticle at 6× magnification
  and 6° chief-ray angle is not a thin mask, and what that does to imaging.

### Photoresists and Stochastics

- [Stochastics in EUV lithography](https://www.lithoguru.com/scientist/essays/) — The photon
  shot-noise argument: EUV photons are ~14× more energetic than 193 nm photons, so a given dose
  contains far fewer of them, and randomness becomes a yield-limiting defect mechanism
  (microbridges, broken lines, missing contacts).
- [Metal-oxide resists — Lam / Inpria dry resist](https://www.lamresearch.com/products/) —
  Dry deposition and dry development of metal-oxide resist; higher EUV absorption at lower dose.
- [Applied Materials / TEL resist processing](https://www.tel.com/product/) —
  Track systems and the coat/develop side of the resist story.
- [Journal of Micro/Nanopatterning, Materials, and Metrology (JM3)](https://www.spiedigitallibrary.org/journals/journal-of-micro-nanopatterning-materials-and-metrology) —
  Where resist and stochastics papers live outside conference proceedings.
- [ALE and selective deposition for EUV resist improvement (patent)](https://patents.google.com/patent/WO2020223011A1/en) —
  Illustrative of the "fix the resist with a process module" strategy: selective caps, scum
  removal, divot fill.

### Multi-Patterning, DSA and Nanoimprint

- [SADP / SAQP explained](https://semiengineering.com/tag/multi-patterning/) —
  Self-aligned double and quadruple patterning, spacer deposition, mandrel pull, and the pitch
  walking that results.
- [Litho-etch-litho-etch and cut masks](https://semiengineering.com/tag/multi-patterning/) —
  The overlay budget arithmetic that made EUV economically inevitable.
- [Directed self-assembly (DSA)](https://spie.org/conferences-and-exhibitions/advanced-lithography-and-patterning) —
  Block copolymers for pitch multiplication and via rectification; a perennial "five years away"
  technology that keeps finding niche uses.
- [Canon nanoimprint lithography](https://global.canon/en/news/2023/20231013.html) — NIL as a
  low-cost, low-throughput alternative for specific layers and for memory.
- [Semiconductor Engineering — Nanoimprint's second act](https://semiengineering.com/tag/nanoimprint-lithography/) —
  Realistic assessment of where NIL actually competes.

### Computational Lithography

The mask is no longer a picture of the design. Between the two sits OPC, sub-resolution assist
features, source-mask optimization, and increasingly full inverse lithography — a nonconvex
optimization run over petabytes of layout, now routinely GPU-accelerated.

- [Inverse lithography technology overview](https://semiengineering.com/tag/inverse-lithography-technology/) —
  What ILT changes versus rule- and model-based OPC.
- [NVIDIA cuLitho](https://developer.nvidia.com/culitho) — GPU-accelerated computational
  lithography library, adopted by TSMC and Synopsys; the reason full-chip curvilinear ILT became
  tractable.
- [Siemens Calibre](https://eda.sw.siemens.com/en-US/ic/calibre-design/) — The dominant production
  OPC/verification platform.
- [Synopsys Proteus / S-Litho](https://www.synopsys.com/manufacturing.html) — OPC, lithography
  simulation, and mask synthesis.
- [ASML Brion](https://www.asml.com/en/products/computational-lithography) — Tachyon
  source-mask optimization and LMC, coupled to ASML scanner models.
- [ICCAD CAD Contest benchmarks](https://iccad-contest.org/) — The annual contest problems (mask
  optimization, hotspot detection, layout) are the standard public benchmarks in this field.
- [Mask optimization literature index — CUHK](https://www.cse.cuhk.edu.hk/~byu/) — Bei Yu's group
  page; the most complete public bibliography of learning-based OPC/ILT.

### Open-Source Lithography Code

Computational lithography is, unexpectedly, one of the healthiest open-source niches in fab-side
software — largely because the ICCAD 2013 mask-optimization benchmark gave academia a shared target.

**ILT and mask optimization**

- [OpenILT](https://github.com/OpenOPC/OpenILT) — PyTorch-based open platform for inverse
  lithography research, implementing the ICCAD 2013 benchmark lithography model with GPU
  acceleration. It decomposes the ILT flow into simulation, initialization, optimization, and
  evaluation, so you can replace one stage without rewriting the rest. The natural starting point.
- [OpenFuILT](https://github.com/OpenOPC/OpenFuILT) — ISPD 2024 full-chip ILT system with boundary
  healing, addressing the tile-stitching artifacts that appear when ILT is scaled past a clip.
  Paired with [OpenFuILT-Eval](https://github.com/OpenOPC/OpenFuILT-Eval) for full-chip scoring.
- [TorchLitho](https://github.com/TorchOPC/TorchLitho) — Differentiable computational lithography
  framework; the imaging model is a differentiable module you can drop into a training loop.
- [TorchLitho 2.0](https://github.com/OpenOPC/TorchLitho-2.0) — ASICON 2025 rewrite aimed at
  full-chip-scale mask optimization with a friendlier API.
- [Neural-ILT](https://github.com/cuhk-eda/neural-ilt) — CUHK's end-to-end learning-based mask
  optimizer; the reference implementation of the learned-ILT lineage.
- [LithoNet](https://github.com/xinming-wei/LithoNet) — Learning-based lithography simulator and
  mask optimizer, useful as a compact baseline.
- [DimmiLitho](https://github.com/vincentlv/DimmiLitho) — Pixel-based mask synthesis plus a partially
  coherent imaging model, in readable Python.
- [lithosim](https://github.com/VLSIDA/lithosim) — Deliberately minimal lithography simulation and
  pixel-based OPC tool from the OpenRAM group; good for teaching.
- [Neural Lithography](https://github.com/Neural-Litho/Neural-Lithography) — SIGGRAPH Asia 2023
  real-to-simulation closed loop, calibrating a learned litho model against measured hardware.
- [Neural-ILT / DAMO / GAN-OPC family](https://www.cse.cuhk.edu.hk/~byu/) — The broader
  learning-based ILT lineage, with code links from the authors' page.
- [ILILT — implicit learning of ILT (arXiv)](https://arxiv.org/abs/2405.03574) — Recent approach
  that avoids explicit iterative optimization at inference time.
- [Open-source differentiable lithography imaging framework (arXiv)](https://arxiv.org/abs/2409.15306) —
  End-to-end differentiable Abbe/Hopkins imaging, so lithography models can sit inside a training
  loop.

**Benchmarks**

- [LithoBench](https://github.com/shelljane/lithobench) — 120k+ layout tiles cropped from real
  designs or synthesized to spec, with reference implementations of mask-optimization baselines.
  The closest thing the field has to ImageNet.

**Imaging and resist simulators**

- [K-Litho](https://github.com/LithoSimulator/K-Litho) — TCC/SOCS-based aerial and resist image
  calculation, including source-mask optimization primitives.
- [LithographySimulator](https://github.com/quarterwave0/LithographySimulator) — Actively maintained
  Python tool modeling optical photolithography from first principles.
- [Lithography-Simulation](https://github.com/pierremifasol/Lithography-Simulation) — Notebook-style
  introduction to Hopkins imaging; the gentlest on-ramp to the mathematics.
  [Computational-lithography](https://github.com/lani5677/Computational-lithography) extends it to 2D.
- [Optolithium](https://github.com/xthebat/optolithium) — Full optical lithography simulator with a
  GUI covering illumination, mask, projection, and resist development. Archived, still instructive.
- [microlith](https://github.com/mehta-lab/microlith) — Partially coherent image simulation shared
  between microscopy and lithography optics.

**E-beam and maskless**

- [pecebl](https://github.com/looninho/pecebl) — E-beam lithography simulation with proximity effect
  correction; [CUDAEBL](https://github.com/looninho/CUDAEBL) is the GPU-accelerated variant.
- [Raith_GDSII](https://github.com/ahryciw/Raith_GDSII) — MATLAB toolkit for driving Raith EBL and
  FIB systems, maintained by NRC Canada.
- [LTK](https://github.com/UUhy/LTK) — Lithography toolkit for KLayout, aimed at direct-write jobs.
- [ASML_JobCreator](https://github.com/demisjohn/ASML_JobCreator) — Programmatically generate job
  files for an ASML PAS 5500 stepper; from the UCSB nanofabrication facility.
- [Hacker Fab stepper](https://github.com/hacker-fab/stepper) — Control software for a DLP-based
  maskless photolithography stepper you can actually build. See [DIY and Garage Fab](#20-diy-and-garage-fab).

**Layout I/O for mask work**

- [KLayout](https://www.klayout.de/) — Not a lithography simulator, but the open-source layout
  viewer/editor with a Python/Ruby API that most open lithography work uses for GDS/OASIS I/O and
  DRC-style geometry processing.
- [gdstk](https://github.com/heitzmann/gdstk) — Fast C++/Python GDSII and OASIS library; useful for
  generating test patterns and mask decks programmatically.
- [gdsCAD](https://github.com/hohlraum/gdsCAD) — Python package specifically oriented toward
  building photolithography mask sets.

---

## 5. Process Modules, Materials and Equipment

### Deposition

- [Atomic layer deposition — BALD Engineering](https://www.blog.baldengineering.com/) — Long-running
  ALD blog covering precursors, conferences, and industrial adoption; unusually deep archive.
- [Area-selective deposition (ASD)](https://link.springer.com/article/10.1007/s12541-025-01337-z) —
  Review covering ASD, atomic layer annealing, and ALE together. ASD is how the industry hopes to
  get self-aligned structures without extra masks.
- [ASD Workshop](https://asd2026.avs.org/) — The dedicated annual workshop; abstracts are the
  best index of what selectivity is achievable on which material pairs.
- [ALD conference (AVS)](https://ald2026.avs.org/) — Primary venue for ALD/ALE
  process chemistry.
- [Area-selective ALD of Ru — defect formation mechanisms (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11280396/) —
  Concrete example of why selectivity degrades and how it is measured.
- [Applied Materials — deposition products](https://www.appliedmaterials.com/us/en/semiconductor/products.html) —
  PVD, CVD, ALD, and epi product families; useful for mapping process steps to actual toolsets.

### Etch

- [Lam Research — cryogenic etching](https://www.lamresearch.com/products/our-solutions/cryogenic-etching/) —
  Cryo 3.0 combines cryogenic wafer temperature with pulsed plasma ALE for high-aspect-ratio
  features; the enabling technology for 3D NAND beyond ~300 layers.
- [Atomic layer etching for extreme manufacturing (Springer)](https://link.springer.com/article/10.1007/s41871-026-00297-w) —
  Review of ALE mechanisms and where atomic-scale precision is actually required.
- [Cryo-ALE and HAR etch physics](https://drmanager.github.io/2026/02/06/ale-high-aspect-ratio-etching-semiconductor/) —
  Why sub −100 °C substrate temperature suppresses lateral etch and stabilizes sidewall passivation.
- [TEL etch systems](https://www.tel.com/product/etch.html) — Tokyo Electron's plasma etch
  portfolio, including their cryogenic HAR approach.
- [AVS Plasma Science and Technology](https://www.avs.org/) — The academic community behind plasma
  etch modeling; also home to the *Journal of Vacuum Science & Technology*.
- [High-aspect-ratio etch challenges](https://semiengineering.com/tag/high-aspect-ratio-etch/) —
  Bowing, twisting, tilting, and aspect-ratio-dependent etch, explained without a paywall.

### CMP, Cleans, Implant, Anneal and Epitaxy

- [CMP fundamentals](https://semiengineering.com/tag/chemical-mechanical-polishing/) —
  Slurry chemistry, pad conditioning, dishing/erosion, and why CMP dominates defectivity budgets.
- [Wafer cleaning and surface preparation](https://semiengineering.com/tag/wafer-cleaning/) —
  RCA cleans, dilute chemistries, cryo-aerosol, and the pattern-collapse problem at high aspect
  ratios.
- [Ion implantation](https://semiengineering.com/tag/ion-implantation/) —
  Beamline vs. plasma doping, and the shift toward conformal doping for 3D structures.
- [Millisecond and laser annealing](https://www.appliedmaterials.com/us/en/semiconductor/products.html) —
  Thermal budget is the binding constraint for sequential 3D integration; anneal technology is how
  you buy activation without diffusion.
- [Selective epitaxial growth for source/drain](https://semiengineering.com/knowledge_centers/manufacturing/process/epitaxy/) —
  Strain engineering via SiGe/SiP source-drain, still the main mobility booster.
- [Advanced Semiconductor Manufacturing Conference (ASMC)](https://www.semi.org/en/connect/events) —
  The manufacturing-focused IEEE/SEMI conference; process module papers with actual fab data.

### Materials, Precursors and Gases

- [SEMI — Materials market data](https://www.semi.org/en/products-services/market-data/materials) —
  Wafer, gas, chemical, photoresist, and substrate market sizing.
- [Electronic Materials — Merck/EMD, JSR, Shin-Etsu, TOK, Sumitomo](https://www.emdgroup.com/en/expertise/electronics.html) —
  The materials supply chain is more concentrated than the equipment supply chain; resist and mask
  blank supply are effectively duopolies.
- [Ultra-high-purity gases and precursors](https://www.linde.com/) — Bulk and
  specialty gas supply, including the fluorinated-gas emissions problem.
- [Critical minerals and semiconductor materials](https://www.csis.org/programs/economics-program-and-scholl-chair-international-business) —
  CSIS's economics program tracks gallium, germanium, neon, and rare-earth supply risk.
- [Materials Project](https://next-gen.materialsproject.org/) — Open computed-materials database;
  the practical starting point for screening dielectric, barrier, and channel candidates.

### Wafer Fab Equipment Landscape

| Segment | Principal suppliers |
|---|---|
| Lithography scanners | [ASML](https://www.asml.com/), [Canon](https://global.canon/en/product/), [Nikon](https://www.nikon.com/products/semi/) |
| Deposition (CVD/PVD/ALD/epi) | [Applied Materials](https://www.appliedmaterials.com/), [Lam Research](https://www.lamresearch.com/), [TEL](https://www.tel.com/), [ASM International](https://www.asm.com/), [Kokusai Electric](https://www.kokusai-electric.com/) |
| Etch | [Lam Research](https://www.lamresearch.com/), [TEL](https://www.tel.com/), [Applied Materials](https://www.appliedmaterials.com/), [Hitachi High-Tech](https://www.hitachi-hightech.com/) |
| CMP | [Applied Materials](https://www.appliedmaterials.com/), [Ebara](https://www.ebara.co.jp/en/), [TEL](https://www.tel.com/) |
| Cleans / track | [SCREEN](https://www.screen.co.jp/spe/en), [TEL](https://www.tel.com/), [Lam](https://www.lamresearch.com/) |
| Process control / metrology | [KLA](https://www.kla.com/), [Onto Innovation](https://ontoinnovation.com/), [Nova](https://www.novami.com/), [Hitachi High-Tech](https://www.hitachi-hightech.com/), [Bruker](https://www.bruker.com/), [Park Systems](https://www.parksystems.com/) |
| Ion implant | [Applied Materials](https://www.appliedmaterials.com/), [Axcelis](https://www.axcelis.com/), [SMIT/Sumitomo](https://www.shi.co.jp/english/) |
| Bonding / packaging | [BESI](https://www.besi.com/), [ASMPT](https://www.asmpt.com/), [EV Group](https://www.evgroup.com/), [SUSS MicroTec](https://www.suss.com/), [Kulicke & Soffa](https://www.kns.com/) |
| Test / ATE | [Advantest](https://www.advantest.com/), [Teradyne](https://www.teradyne.com/), [Cohu](https://www.cohu.com/) |

- [SEMI — Equipment market data (Worldwide Fab Forecast)](https://www.semi.org/en/products-services/market-data) —
  Fab-by-fab capacity, equipment spending, and construction tracking. The industry's standard
  planning dataset.
- [VLSI Research / TechInsights equipment rankings](https://www.techinsights.com/) — Annual
  market-share tables by segment.

---

## 6. Metrology, Inspection and Yield

At sub-2 nm, a measurement that perturbs the structure or cannot see past the top few nanometers is
not a measurement. This section is why metrology capex has grown faster than litho capex.

### Dimensional and Compositional Metrology

- [CD-SAXS at NIST](https://www.nist.gov/programs-projects/metrology-nanolithography) — Critical-
  dimension small-angle X-ray scattering is currently the only non-destructive technique that
  resolves sub-nanometer sidewall angle, pitch walking, inner-spacer geometry, and channel-hole
  tilt through multi-micron-deep structures.
- [Metrology challenges in sub-5 nm nodes](https://appliedphysicsusa.com/blogs/metrology-sub-5nm-challenges/) —
  Why optical scatterometry hits opacity and multi-reflection limits and CD-SEM cannot penetrate
  deep structures without damage.
- [X-ray metrology market and technology](https://www.exponentialindustry.com/blog/2026-07-30-x-ray-semiconductor-metrology-market/) —
  XRF, XRD, XPS, and CD-SAXS mapped to the process steps that need them.
- [Metrology for next-generation 3D NAND](https://semiengineering.com/metrology-digs-deep-to-produce-next-generation-3d-nand/) —
  High-aspect-ratio measurement, which is now a packaging problem too (TSVs, deep vias).
- [SPIE Metrology, Inspection, and Process Control](https://spie.org/conferences-and-exhibitions/advanced-lithography-and-patterning) —
  The primary conference; proceedings volumes are the reference literature.
- [Atom probe tomography and TEM for devices](https://www.bruker.com/en/products-and-solutions/microscopes.html) —
  Destructive but atomically resolved; how dopant profiles in nanosheets are actually confirmed.
- [Hybrid metrology](https://semiengineering.com/tag/hybrid-metrology/) — Combining
  optical, AFM, and X-ray data into one regression; the practical answer to any single technique
  being insufficient.

### Defect Inspection and Review

- [KLA — inspection and review](https://www.kla.com/products) — Brightfield, darkfield, and e-beam
  inspection; the reference implementations for the whole category.
- [E-beam inspection throughput problem](https://semiengineering.com/tag/e-beam-inspection/) —
  Why multi-beam e-beam inspection is the most-attempted, least-delivered idea in metrology.
- [Voltage contrast and physical failure analysis](https://semiengineering.com/knowledge_centers/manufacturing/process/failure-analysis/) —
  How buried opens and shorts are localized before anyone cross-sections a wafer.
- [Automated defect classification (ADC)](https://semiengineering.com/tag/defect-classification/) —
  The first production ML application in fabs, predating the current wave by two decades.

### Yield Modeling and Process Control

- [Yield models — Poisson, Murphy, negative binomial](https://en.wikipedia.org/wiki/Semiconductor_device_fabrication) —
  D0 and clustering factor; the arithmetic behind every chiplet-vs-monolithic argument.
- [Statistical process control in semiconductor manufacturing](https://www.semi.org/en/connect/events) —
  ASMC is where the practical SPC/APC work is published.
- [Run-to-run control and virtual metrology](https://semiengineering.com/tag/virtual-metrology/) —
  Predicting a measurement instead of taking it; the highest-value ML deployment in most fabs.
- [Yield learning and defect Pareto methodology](https://semiengineering.com/knowledge_centers/manufacturing/process/yield/) —
  How a fab actually decides what to fix next.
- [SEMI E10 / OEE definitions](https://www.semi.org/en/products-services/standards) — The standard
  equipment-state model underneath every fab productivity metric.

---

## 7. Memory Technology

Memory drives more wafer starts than logic and more advanced-packaging demand than anything except
AI accelerators. It also pioneers processes — hybrid bonding shipped in NAND before it shipped in
logic.

### DRAM

- [SK hynix DRAM roadmap — 4F2 VG and 3D DRAM](https://www.tweaktown.com/news/105694/sk-hynix-unveils-dram-memory-chip-roadmap-for-the-next-30-years-4f2vg-tech-3d-and-more/index.html) —
  The long-range plan: 6F2 → 4F2 with vertical-channel/vertical-gate transistors, then 3D DRAM.
- [Samsung — 3D DRAM on the roadmap](https://www.tomshardware.com/pc-components/dram/samsung-outlines-plans-for-3d-dram-which-will-come-in-the-second-half-of-the-decade) —
  Timing and architecture direction.
- [Baby steps toward 3D DRAM](https://semiengineering.com/baby-steps-towards-3d-dram/) — Honest
  assessment of what stacking DRAM actually requires (capacitor-less cells, IGZO channels, or
  wafer-bonded arrays).
- [Lam — learning from NAND for the 3D DRAM transition](https://newsroom.lamresearch.com/learning-from-nand-3d-dram-transition-ai-era) —
  Equipment-vendor perspective on which NAND lessons transfer.
- [4F2 DRAM with vertical thin-film transistor (patent)](https://patents.google.com/?q=4F2+DRAM+vertical+channel+transistor) —
  Patent literature is the best public source on cell architecture specifics.

### 3D NAND

- [NAND flash targets 1000 layers](https://semiengineering.com/nand-flash-targets-1000-layers/) —
  String stacking, CMOS-under-array vs. CMOS-bonded-array, and the etch/metrology limits.
- [Kioxia/SanDisk CBA and YMTC Xtacking](https://semiengineering.com/knowledge_centers/memory/non-volatile-memory/3d-nand/) —
  Wafer-bonded periphery is the architecture that made hybrid bonding a volume technology.
- [TEL cryogenic etch for 400-layer NAND](https://www.tel.com/) — Ultra-fast deep etch with
  substantially lower global-warming-potential emissions.

### High Bandwidth Memory

- [JEDEC JESD270-4 — HBM4](https://www.jedec.org/standards-documents/docs/jesd270-4a) — The
  standard itself: 2048-bit interface per stack, with data rates specified up to 8 GT/s and beyond
  in the amended revision.
- [JEDEC — HBM4 press release](https://www.jedec.org/news/pressreleases/jedec%C2%AE-and-industry-leaders-collaborate-release-jesd270-4-hbm4-standard-advancing) —
  Official summary of bandwidth, efficiency, and capacity targets.
- [JEDEC — SPHBM4](https://www.jedec.org/news/pressreleases/jedec%C2%AE-prepares-sphbm4-standard-deliver-hbm4-level-throughput-reduced-pin-count) —
  HBM4-level throughput at reduced pin count, aimed at cost-sensitive and mobile-adjacent uses.
- [Siemens — HBM3E and HBM4 IC design guide](https://blogs.sw.siemens.com/semiconductor-packaging/2026/04/24/hbm3e-hbm4-ic-design-guide/) —
  Design-side treatment: base-die logic process, channel count, and signal integrity.
- [EE Times — the push toward custom memory](https://www.eetimes.com/beyond-bandwidth-the-industry-is-striving-for-custom-memory-part-1/) —
  Custom HBM base dies with embedded logic, and what standardization gives up.
- [EE Times — Rambus HBM4E controller and C-HBM4E](https://www.eetimes.com/rambus-unveils-hbm4e-controller-16-gt-s-2048-bit-interface-enabling-c-hbm4e/) —
  The controller side of custom HBM, including UCIe-interfaced variants.

### Emerging Non-Volatile Memory

- [MRAM, RRAM, PCM and FeFET status](https://semiengineering.com/knowledge_centers/memory/non-volatile-memory/) —
  Where each has actually shipped: embedded MRAM in foundry MCU nodes, PCM in storage-class memory,
  FeFET still mostly in research.
- [Hafnium-oxide ferroelectrics](https://www.nature.com/subjects/ferroelectrics-and-multiferroics) —
  The CMOS-compatible ferroelectric that made FeFET and FeRAM interesting again.
- [Compute-in-memory surveys](https://arxiv.org/list/cs.AR/recent) — The main application driver
  for emerging NVM; search arXiv cs.AR and cs.ET for current surveys.
- [Stanford N3XT / monolithic 3D memory-logic](https://systemx.stanford.edu/) — RRAM plus CNFET
  logic in a monolithic stack.

---

## 8. Advanced Packaging

The longest section, deliberately. Packaging moved from cost-down back-end work to the primary
lever on system performance, and it is currently the binding capacity constraint on AI hardware.

### Primers and Taxonomy

- [A comprehensive primer on advanced semiconductor packaging](https://www.viksnewsletter.com/p/a-comprehensive-primer-on-advanced-packaging) —
  The best single free explainer: wire bond → flip chip → fan-out → 2.5D → 3D, with the reasoning
  for each transition.
- [Heterogeneous Integration Roadmap chapters](https://eps.ieee.org/technology/heterogeneous-integration-roadmap/) —
  Free, authoritative, and organized exactly the way this section is.
- [3D InCites](https://www.3dincites.com/) — The trade publication dedicated to advanced packaging.
  Phil Garrou's *IFTLE* column is the closest thing the field has to a running technical journal.
- [Semiconductor Engineering — Advanced Packaging knowledge center](https://semiengineering.com/knowledge_centers/packaging/) —
  Terminology plus a decade of linked coverage.
- [TechInsights — Advanced packaging and chiplets](https://www.techinsights.com/chiplets/advanced-packaging-and-chiplets-unleashing-semiconductor-innovation) —
  Teardown-grounded overview of what is actually inside shipping packages.
- [Semiconductor Packaging workshop (open course material)](https://github.com/Lakshana3/Semiconductor_Packaging) —
  Workshop repository bridging chip design and packaging, from wire bonding through 2.5D/3D
  chiplet assembly.
- [Semiconductor Packaging fundamentals notes](https://github.com/arunkpv/Semiconductor-Packaging) —
  Course-style notes covering packaging fundamentals.
- [Chiplet Marketplace wiki — advanced packaging](https://chiplet-marketplace.com/library/wiki/advanced-packaging) —
  Vendor-neutral wiki with a usable taxonomy of package types.

**Taxonomy cheat sheet**

| Family | Vertical? | Interconnect | Typical pitch | Examples |
|---|---|---|---|---|
| Flip-chip BGA | No | C4 solder bumps | 100–150 µm | Conventional SoC packages |
| Fan-out WLP | No | RDL in mold compound | 5–40 µm | TSMC InFO, ASE FOCoS |
| 2.5D interposer | Side-by-side | Si interposer + µbump | 40–55 µm | TSMC CoWoS-S, Amkor S-SWIFT |
| 2.5D bridge | Side-by-side | Embedded Si bridge | 45–55 µm | Intel EMIB, TSMC CoWoS-L |
| 3D µbump stack | Yes | TSV + µbump | 25–40 µm | HBM stacks, Foveros |
| 3D hybrid bond | Yes | Direct Cu–Cu + oxide | 1–10 µm | TSMC SoIC, Intel Foveros Direct, AMD 3D V-Cache |
| Panel-level | No | RDL on large panel | 5–20 µm | FOPLP, TSMC CoPoS |

### 2.5D Interposers and Bridges

- [TSMC 3DFabric / CoWoS](https://3dfabric.tsmc.com/english/dedicatedFoundry/technology/3DFabric.htm) —
  Official landing page for CoWoS-S (silicon interposer), CoWoS-R (RDL interposer), CoWoS-L
  (interposer with embedded local silicon interconnect bridges), InFO, and SoIC.
- [Intel EMIB](https://www.intel.com/content/www/us/en/foundry/advanced-packaging.html) — Embedded
  Multi-die Interconnect Bridge: a small silicon bridge embedded in organic substrate, avoiding a
  full-reticle interposer and its TSVs.
- [Intel EMIB with glass core (NEPCON 2026)](https://insights.trendforce.com/p/glass-substrate-development) —
  Bridge plus glass core in one package; a preview of where 2.5D substrates are heading.
- [Amkor S-SWIFT and S-Connect](https://amkor.com/packaging/) — OSAT
  alternatives to foundry-owned 2.5D flows.
- [Samsung I-Cube / H-Cube](https://semiconductor.samsung.com/foundry/advanced-package/) — Samsung's
  2.5D families.
- [SemiAnalysis — packaging developments from ECTC](https://semianalysis.substack.com/p/packaging-developments-from-ectc) —
  Conference readout on where interposer and bridge technology actually is.
- [Interposer design considerations](https://semiengineering.com/knowledge_centers/packaging/2-5d-ic/) —
  Micro-bump pitch, RDL line/space, and reticle-stitching limits for large interposers.

### 3D Stacking and Hybrid Bonding

Hybrid bonding replaces solder microbumps with direct copper-to-copper bonds surrounded by
dielectric-to-dielectric bonds. That removes the underfill, removes the bump height, and lets
interconnect pitch scale below 10 µm — into a regime where vertical wires start to look like on-die
wires.

- [Intel — Foveros Direct 3D technical brief (PDF)](https://www.intel.com/content/dam/www/central-libraries/us/en/documents/2025-11/foveros-direct-3d-tech-brief.pdf) —
  Vendor technical brief on bumpless Cu–Cu bonding, sub-10 µm pitch, and the design rules that
  follow.
- [TSMC SoIC](https://3dfabric.tsmc.com/english/dedicatedFoundry/technology/3DFabric.htm) —
  System on Integrated Chips: bumpless front-end 3D stacking, currently around 9 µm pitch in
  production and used together with CoWoS-L in flagship AI parts.
- [Semiconductor Engineering — Making hybrid bonding better](https://semiengineering.com/making-hybrid-bonding-better/) —
  The practical problems: dishing control, surface activation, particle sensitivity, and D2W
  placement accuracy.
- [TechInsights — Hybrid bonding, tomorrow's interconnect](https://library.techinsights.com/hg-asset/10147ff7-c189-4040-871f-a113cae34dc0) —
  Cross-sections of shipping hybrid-bonded devices.
- [Adeia (Xperi) DBI / DBI Ultra](https://www.adeia.com/) — The licensed
  direct bond interconnect technology underneath much of the industry's W2W and D2W capability.
- [Yole — hybrid bonding interview with Adeia](https://www.yolegroup.com/player-interviews/hybrid-bonding-latest-advancements-2-5d-3d-packaging-industry-an-interview-with-adeia/) —
  Market and roadmap framing.
- [IBM — D2W and W2W hybrid bonding below 25 µm pitch](https://research.ibm.com/publications/d2w-and-w2w-hybrid-bonding-system-with-below-25-micron-pitch-for-3d-chiplet-ai-applications) —
  Research-lab account of building the bonding system, not just using one.
- [AMD 3D V-Cache](https://www.amd.com/en/technologies/3d-v-cache) — The first high-volume consumer
  product built on hybrid-bonded logic-on-logic stacking; a useful concrete reference design.
- [ECTC — Electronic Components and Technology Conference](https://www.ectc.net/) — The packaging
  field's IEDM. Every bonding, pitch, and reliability record is announced here first.

**Pitch scaling, roughly.** Microbump flip-chip bottoms out near 25–40 µm because solder needs
volume and standoff. Hybrid bonding starts around 10 µm and has demonstrated 2 µm and below in
research. Intel has publicly described Foveros pitch progressing from ~50 µm (2020) to ~9 µm, with
~3 µm as a stated goal. Each halving of pitch is a 4× increase in vertical bandwidth density.

### Fan-Out and Panel-Level Packaging

- [TSMC InFO](https://3dfabric.tsmc.com/english/dedicatedFoundry/technology/3DFabric.htm) —
  Integrated Fan-Out; the technology that put TSMC in packaging and shipped in mobile APs before
  anything else.
- [Fan-out wafer-level packaging overview](https://semiengineering.com/tag/fan-out-wafer-level-packaging/) —
  Chip-first vs. chip-last, die shift, and warpage — the three problems FOWLP always has.
- [TSMC CoPoS — chip-on-panel-on-substrate](https://www.trendforce.com/news/2026/04/13/news-tsmc-advances-panel-level-packaging-copos-pilot-line-reportedly-set-for-june-completion-2028-29-ramp-eyed/) —
  Panel-level packaging as the escape from round-wafer area inefficiency for very large packages.
- [Panel size standardization](https://www.trendforce.com/news/2026/05/19/news-equipment-maker-schmid-flags-tsmc-panel-level-packaging-push-310x310mm-progress-glass-integration-under-review/) —
  310 × 310 mm, 510 × 515 mm, and 600 × 600 mm are converging as the industry panel formats.
- [FOPLP economics](https://www.yolegroup.com/) — Yole's packaging reports are the standard source
  for panel-vs-wafer cost crossover analysis.

### Substrates, Glass and RDL

- [Glass core substrates — the new race](https://www.yolegroup.com/strategy-insights/glass-core-substrates-the-new-race-for-advanced-packaging-giants/) —
  Why glass: better dimensional stability and flatness than ABF organic cores, enabling finer RDL
  and larger bodies.
- [Absolics (SKC) glass substrate production](https://www.trendforce.com/news/2026/03/03/news-skc-reportedly-channels-over-half-of-%E2%82%A91t-capital-increase-into-absolics-to-fast-track-glass-substrates/) —
  The first dedicated glass-substrate mass-production line, in Georgia.
- [MIT Technology Review — future AI chips on glass](https://www.technologyreview.com/2026/03/13/1134230/future-ai-chips-could-be-built-on-glass/) —
  Accessible framing of the transition and its remaining obstacles (brittleness, via formation,
  handling).
- [IDTechEx — glass interposers and substrates](https://www.idtechex.com/en/research-article/glass-interposers-and-substrates-in-advanced-packaging/33856) —
  Comparison against silicon interposer and organic RDL on cost, loss, and thermal expansion.
- [ABF substrate supply](https://semiengineering.com/tag/ic-substrates/) — Ajinomoto
  build-up film and the substrate-supply bottleneck that has repeatedly gated GPU shipments.
- [RDL scaling — line/space roadmap](https://eps.ieee.org/technology/heterogeneous-integration-roadmap/) —
  HIR's interconnect chapter has the authoritative RDL dimension roadmap.

### TSVs, Bumps and Bonding Equipment

- [Through-silicon via fundamentals](https://semiengineering.com/knowledge_centers/packaging/3d-ic/through-silicon-via/) —
  Via-middle vs. via-last, Cu pumping, keep-out zones, and the stress effects TSVs impose on nearby
  devices.
- [Wafer thinning and temporary bonding](https://www.evgroup.com/technologies/) —
  Backside power and 3D stacking both require thinning to single-digit micrometers on a carrier.
- [Thermocompression bonding and fluxless TCB](https://tspasemiconductor.substack.com/p/the-packaging-evolution-trilogy-hybrid) —
  Where TCB still wins over hybrid bonding, and the fluxless transition.
- [BESI hybrid bonding platforms](https://www.besi.com/products-technology/) — Die-to-wafer hybrid
  bonders and their placement-accuracy specifications.
- [EV Group bonding technology](https://www.evgroup.com/technologies/) — Wafer-to-wafer fusion and
  hybrid bonding, plus the metrology to verify alignment.
- [ASMPT advanced packaging](https://www.asmpt.com/en/) —
  High-throughput die attach and TCB.
- [2 µm pitch D2W hybrid bonding (ECTC 2025)](https://www.ectc.net/) — Surface protection during
  thinning and singulation is the enabling trick; see the ECTC 2025 program.

### Thermal, Power and Mechanical Integrity

Stacking dies multiplies power density and buries the hot layer under silicon. Thermal is now a
first-order architectural constraint, not a mechanical afterthought.

- [3D-ICE](https://github.com/esl-epfl/3d-ice) — EPFL's transient thermal simulator for stacked 3D
  ICs, including inter-tier microchannel liquid cooling. Widely used in research.
- [PACT — Parallel Compact Thermal Simulator](https://github.com/peaclab/PACT) — SPICE-based
  parallel thermal simulation from standard-cell to architecture level, extensible to 3D stacking
  and liquid cooling by editing the thermal netlist.
- [HotSpot](https://github.com/uvahotspot/HotSpot) — The long-standing architecture-level compact
  thermal model; still the baseline everything else is compared against.
- [MFIT — multi-fidelity thermal modeling for 2.5D/3D chiplets (arXiv)](https://arxiv.org/abs/2410.09188) —
  Trading accuracy for speed in chiplet thermal exploration.
- [Cool-3D — thermal-aware early design space exploration](https://arxiv.org/abs/2503.07297) —
  End-to-end framework for microfluidic-cooled 3D ICs.
- [Open-source thermal modeling tools (DAC BoF slides, PDF)](https://open-source-eda-birds-of-a-feather.github.io/doc/slides_2024/DAC24_BoF_Coskun.pdf) —
  A guided tour of the open thermal tool landscape by one of its main authors.
- [Vertical power delivery for HPC packages (arXiv)](https://arxiv.org/abs/2606.28837) — Design
  framework for delivering hundreds of amps vertically through a package.
- [Warpage and thermomechanical stress](https://semiengineering.com/tag/warpage/) —
  CTE mismatch across die, underfill, mold compound, and substrate; the reason large packages fail
  assembly before they fail electrically.
- [Direct-to-chip liquid cooling and immersion](https://www.opencompute.org/projects/cooling-environments) —
  OCP's cooling workstream; where package-level thermal meets datacenter facilities.

### Co-Packaged Optics

- [TSMC COUPE](https://finance.biggo.com/news/d980R50ByH9TLH69RcD5) — Compact Universal Photonic
  Engine: an electronic IC stacked on a photonic IC using SoIC bumpless bonding, then integrated
  with CoWoS. Roadmapped from ~0.5 Tb/s/mm toward ~4 Tb/s/mm.
- [Tom's Hardware — CPO foundry roadmaps compared](https://www.tomshardware.com/tech-industry/artificial-intelligence/co-packaged-optics-cpo-foundry-roadmaps-breaking-down-tsmc-intel-samsung-and-globalfoundries-approach-to-next-generation-scale-up-connectivity) —
  TSMC, Intel, Samsung, and GlobalFoundries approaches side by side.
- [EDN — where CPO stands in 2026](https://www.edn.com/where-co-packaged-optics-cpo-technology-stands-in-2026/) —
  Realistic status check on deployment.
- [SemiAnalysis — Co-Packaged Optics: scaling with light](https://newsletter.semianalysis.com/p/co-packaged-optics-cpo-book-scaling) —
  Long-form economic and technical analysis of the CPO transition.
- [IFTLE — TSMC integrated CoWoS and COUPE](https://www.3dincites.com/2025/10/iftle-642-tsmc-advanced-co-packaged-optics-integrated-cowos-and-coupe/) —
  Packaging-community perspective with cross-sections.
- [OIF — co-packaged optics frameworks](https://www.oiforum.com/technical-work/) —
  Where the electrical-optical interface agreements are written.
- [gdsfactory](https://github.com/gdsfactory/gdsfactory) — Open-source Python framework for
  photonic and analog layout; the practical entry point for building a PIC layout you can actually
  tape out.
- [gplugins — DEVSIM, Meep, and TCAD plugins for gdsfactory](https://gdsfactory.github.io/gplugins/) —
  Ties photonic layout to device and EM simulation.

### Packaging Supply Chain and OSATs

- [TSMC advanced packaging capacity tracking](https://www.digitimes.com/news/a20260514PD237/tsmc-cowos-soic-capacity-packaging.html) —
  CoWoS and SoIC capacity expansion reporting; capacity numbers here move markets and change
  quarterly, so treat any single figure as a snapshot.
- [ASE Group](https://www.aseglobal.com/) — Largest OSAT; FOCoS, VIPack, and fan-out capacity.
- [Amkor Technology](https://amkor.com/) — Second-largest OSAT, with US advanced packaging
  investment.
- [JCET](https://www.jcetglobal.com/), [Powertech (PTI)](https://www.pti.com.tw/en/),
  [SPIL](https://www.spil.com.tw/en/), [Tongfu Microelectronics](https://www.tfme.com/en/) —
  The rest of the top-tier OSAT landscape.
- [SEMI Packaging market data](https://www.semi.org/en/products-services/market-data) — Capacity
  and materials consumption by package family.
- [IMAPS](https://www.imaps.org/) — The microelectronics packaging professional society; its
  Device Packaging Conference is the applied counterpart to ECTC.

---

## 9. Chiplets and Die-to-Die Interfaces

Chiplets are an economic response to three facts: yield falls superlinearly with die area, SRAM and
analog stopped scaling with logic, and High-NA halves the reticle field. Splitting a design only
pays if the die-to-die interface is cheap enough in power, area, and latency — which is what all
these standards are about.

### Interface Standards

- [UCIe — Universal Chiplet Interconnect Express](https://www.uciexpress.org/) — The de facto
  standard: standard package and advanced package variants, PHY/adapter/protocol layer stack,
  streaming and PCIe/CXL protocol mappings, and a compliance program.
- [UCIe on Wikipedia](https://en.wikipedia.org/wiki/UCIe) — Concise, accurate summary of the layer
  stack and bump-pitch tiers if you do not want to read the specification.
- [Bunch of Wires (BoW) — OCP ODSA](https://www.opencompute.org/wiki/Server/ODSA) — The open,
  royalty-free alternative optimized for organic substrates; simpler PHY, no advanced package
  required.
- [Intel AIB / AIB 2.0](https://github.com/intel/aib-phy-hardware) — Advanced Interface Bus; the
  open-sourced DARPA CHIPS-era die-to-die PHY. Historically important and still a usable reference.
- [OpenHBI](https://www.opencompute.org/wiki/Server/ODSA) — HBM-derived open die-to-die interface for
  short-reach, high-density links.
- [OIF CEI-112G / CEI-224G](https://www.oiforum.com/technical-work/) — The long-reach SerDes
  agreements that chiplet XSR and USR links are derived from.
- [IEEE P3405 chiplet standards](https://standards.ieee.org/) — Emerging IEEE work on chiplet
  interface and interoperability specifications.
- [OIF/MSA short-reach optical chiplet interface](https://www.oiforum.com/) — WDM-based optical
  chiplet interconnect for scale-up CPO, backed by the major hyperscalers and accelerator vendors.

### Open-Source Chiplet IP

- [ucb-bar/ucie](https://github.com/ucb-bar/ucie) — Open-source digital implementation of the UCIe
  1.1 specification from UC Berkeley.
- [ucb-ucie/ucieanalog](https://github.com/ucb-ucie/ucieanalog) — The analog/mixed-signal companion
  to the digital UCIe implementation.
- [google/open-chiplet](https://github.com/google/open-chiplet) — Components for building an
  interoperable chiplet using open and industry-standard interfaces.
- [tenstorrent/aou-rtl](https://github.com/tenstorrent/aou-rtl) — AXI-over-UCIe bridge RTL,
  targeting the UCIe 3.0 Flit-Die Interface. A rare open, production-oriented D2D bridge.
- [Zero ASIC — lowering the barrier to chiplets](https://www.zeroasic.com/blog/ucie-open-source-design) —
  Write-up of an open UCIe-lite D2D generator, simulated with Verilator, Icarus, Xyce, and
  Switchboard.
- [Switchboard](https://github.com/zeroasiccorp/switchboard) — High-performance open co-simulation
  library for stitching RTL, C++, and Python models across chiplet boundaries.
- [Intel AIB PHY hardware](https://github.com/intel/aib-phy-hardware) — Open RTL and documentation
  for the AIB generation of die-to-die interfaces. The CHIPS Alliance fork at
  [chipsalliance/aib-phy-hardware](https://github.com/chipsalliance/aib-phy-hardware) is the one
  under active stewardship.
- [OpenHBM](https://github.com/Netie-AI/OpenHBM) — Open-source HBM4 memory subsystem targeting JEDEC
  JESD270-4A: controller, PHY shim, DFT, RAS, and security. A rare open implementation of a
  bandwidth-class memory interface rather than a toy.
- [UMI — Universal Memory Interface](https://github.com/zeroasiccorp/umi) — Transaction-level
  interface standard for composing chiplets and accelerators, designed to sit above a D2D PHY.
- [EBRICK demo](https://github.com/zeroasiccorp/ebrick-demo) — Worked example of packaging a design
  as a reusable chiplet "brick" with a standard interface and footprint.
- [logikbench](https://github.com/zeroasiccorp/logikbench) — Digital logic benchmark suite for
  comparing synthesis and place-and-route across tools and technologies.
- [Chipyard](https://github.com/ucb-bar/chipyard) — Berkeley's SoC framework; the usual host
  environment for integrating open D2D IP into a real design.

### Chiplet Economics and Cost Models

- [Chiplet Actuary](https://github.com/Yinxiao-Feng/chiplet-actuary) — Quantitative cost model for
  multi-chiplet systems, the first to model die-to-die overhead and NRE cost explicitly. Paper:
  [arXiv:2203.12268](https://arxiv.org/abs/2203.12268).
- [Gemini — mapping and architecture co-exploration](https://github.com/SET-Scheduling-Project/GEMINI-HPCA2024) —
  HPCA 2024 framework co-exploring architecture and mapping for large DNN chiplet accelerators
  under monetary-cost, performance, and energy objectives. Uses Chiplet Actuary for package cost.
- [Gemini paper (PDF)](http://people.iiis.tsinghua.edu.cn/~gaomy/pubs/gemini.hpca24.pdf) — Full
  method description.
- [CATCH](https://github.com/nanocad-lab/CATCH) — Cost Analysis Tool for Co-optimization of
  Chiplet-based Heterogeneous systems (UCLA NanoCAD). Models wafer cost, yield, known-good-die test,
  assembly, and packaging together, so you can see where disaggregation stops paying.
  Paper: [arXiv:2503.15753](https://arxiv.org/abs/2503.15753).
- [ChipletPart](https://github.com/ABKGroup/ChipletPart) — Cost-aware partitioner for 2.5D systems:
  multi-way partitioning, heterogeneous technology assignment, and IO-reach-aware floorplanning in
  one loop. Paper: [arXiv:2507.19819](https://arxiv.org/abs/2507.19819).
- [OCP chiplet cost model](https://www.opencompute.org/chiplets/66/cost-modeling-analysis-for-heterogeneous-integration-of-chiplets) —
  Industry-consensus cost model covering materials, test, known-good-die, and operations, published
  for supply-chain and engineering trade-offs.
- [Yield and cost arithmetic for disaggregation](https://semiengineering.com/tag/chiplets/) —
  When splitting a die actually saves money once packaging, test, and KGD costs are included.
- [Die-per-wafer and yield calculators](https://anysilicon.com/die-per-wafer-formula-free-calculators/) —
  The arithmetic behind every chiplet business case: gross die, edge loss, and defect-density yield
  models (Poisson, Murphy, negative binomial).
- [Design approach for energy-efficient D2D interfaces (ISLPED)](https://dl.acm.org/doi/abs/10.1145/3665314.3680473) —
  pJ/bit budgets across interface choices.

### Architecture Exploration Tools

- [Open3DFlow](https://github.com/RIOSLaboratory/Open3DFlow) — Open-source 3D IC design platform
  built on existing open EDA tools, with TSV modeling, thermal analysis, and signal-integrity
  assessment for chiplet designs. A [second implementation](https://github.com/Lcrypto/Open3DFlow)
  adds abstractions for simulating hybrid-bonded 3D structures on an OpenROAD 2D backend.
- [TAP-2.5D](https://github.com/bu-icsg/TAP-2.5D) — Thermally-aware chiplet placement for homogeneous
  and heterogeneous 2.5D systems, using simulated annealing to trade inter-chiplet wirelength
  against peak temperature. One of the few tools that treats thermal as a placement objective rather
  than a post-hoc check.
- [BookSim2](https://github.com/booksim/booksim2) — Cycle-accurate interconnection network
  simulator; the standard tool for modeling chiplet NoC/NoP topologies.
- [gem5](https://github.com/gem5/gem5) — Full-system architecture simulator, commonly extended for
  chiplet and disaggregated-memory studies.
- [Timeloop / Accelergy](https://github.com/NVlabs/timeloop) — Mapping and energy estimation for
  accelerator architectures; pairs naturally with chiplet partitioning studies.
- [SIAM and chiplet accelerator simulators](https://arxiv.org/list/cs.AR/recent) — Chiplet-based
  in-memory-computing accelerator simulation; search arXiv cs.AR for the current generation.
- [AuthenTree — distributed trust for chiplet SiPs (arXiv)](https://arxiv.org/abs/2508.13033) —
  Architecture work on authenticating chiplets from multiple vendors.

---

## 10. Design and EDA for Advanced Nodes and 3D

### Commercial 3D-IC and Packaging Flows

No open-source flow currently signs off a 3D stack. These are the tools that do.

- [Synopsys 3DIC Compiler](https://www.synopsys.com/implementation-and-signoff/3dic-design.html) —
  Unified multi-die planning, implementation, and analysis in one database.
- [Cadence Integrity 3D-IC](https://www.cadence.com/en_US/home/tools/ic-package-design-and-analysis.html) —
  3D-IC planning platform with integrated thermal and early feasibility analysis.
- [Siemens Innovator3D IC](https://eda.sw.siemens.com/en-US/ic/) — Multi-die
  planning, substrate/interposer co-design, and package-aware signoff.
- [Siemens Calibre 3DSTACK](https://eda.sw.siemens.com/en-US/ic/calibre-design/physical-verification/3dstack/) —
  Physical verification across die boundaries, including bonded-interface checks.
- [Ansys RedHawk-SC and Icepak](https://www.ansys.com/products/semiconductors) — Multiphysics:
  power integrity, electromigration, thermal, and warpage for stacked assemblies.
- [Keysight ADS / EMPro](https://www.keysight.com/us/en/products/software/pathwave-design-software.html) —
  Package and interposer electromagnetic modeling.
- [Siemens Tessent Multi-die](https://blogs.sw.siemens.com/semiconductor-packaging/2024/09/24/enabling-comprehensive-dft-for-chiplets-and-3dics-using-tessent-multi-die/) —
  IEEE 1838-based DFT across a stack, including pre-bond, mid-bond, and post-bond test.
- [Semiwiki — DFT moves up to 2.5D and 3D IC](https://semiwiki.com/eda/319014-dft-moves-up-to-2-5d-and-3d-ic/) —
  What changes in the DFT flow when the design spans dies.

### Open-Source RTL-to-GDS

- [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD) — The open RTL-to-GDSII physical
  design engine: floorplanning, placement, CTS, routing, and timing. The centerpiece of the open
  flow.
- [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) — Reference
  flow with working designs on multiple open PDKs; the fastest way to get an end-to-end run.
- [LibreLane](https://github.com/librelane/librelane) — The community-maintained successor to
  OpenLane 2, an RTL-to-GDSII flow built around OpenROAD with Nix-based reproducibility.
- [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) — The original OpenLane flow; still
  the reference for many published tapeouts.
- [Yosys](https://github.com/YosysHQ/yosys) — Open synthesis framework; the front end of nearly
  every open flow.
- [SiliconCompiler](https://github.com/siliconcompiler/siliconcompiler) — Build-system-style
  hardware compilation framework that abstracts over multiple tools, flows, and PDKs.
- [Magic VLSI](https://github.com/RTimothyEdwards/magic) — Layout editor with built-in extraction
  and DRC; the workhorse of open analog and custom layout.
- [Netgen](https://github.com/RTimothyEdwards/netgen) — LVS for open flows.
- [KLayout](https://github.com/KLayout/klayout) — Layout viewer, editor, and scriptable DRC engine;
  the format Swiss army knife of the field.
- [OpenRAM](https://github.com/VLSIDA/OpenRAM) — Open memory compiler; SRAM generation for open
  PDKs.
- [Verilator](https://github.com/verilator/verilator) — The fastest open Verilog/SystemVerilog
  simulator, and the standard for chiplet co-simulation harnesses.
- [cocotb](https://github.com/cocotb/cocotb) — Python coroutine-based verification, widely used for
  D2D protocol testing.
- [ngspice](https://ngspice.sourceforge.io/) — Open SPICE simulator with BSIM-CMG support.
- [Xyce](https://github.com/Xyce/Xyce) — Sandia's parallel SPICE-class simulator, built for very
  large circuits including package/PDN networks.
- [Coriolis](https://github.com/lip6/coriolis) — LIP6's complete open physical design toolchain,
  an independent alternative to OpenROAD.
- [Awesome open source hardware tools](https://github.com/TM90/awesome-hwd-tools) — A broader index
  if you need the front-end tooling this list skips.

**Timing and signoff**

- [OpenSTA](https://github.com/parallaxsw/OpenSTA) — The static timing analysis engine used inside
  OpenROAD; also usable standalone. The [OpenROAD fork](https://github.com/The-OpenROAD-Project/OpenSTA)
  tracks flow-specific changes.
- [OpenTimer](https://github.com/OpenTimer/OpenTimer) — High-performance parallel timing analyzer,
  and the reference implementation for several TAU contest problems.
- [Parser-SPEF](https://github.com/OpenTimer/Parser-SPEF) — Fast header-only SPEF parser, for when
  you need to consume extracted parasitics yourself.
- [Tatum](https://github.com/verilog-to-routing/tatum) — Flexible STA engine from the VTR project.

**Analog and mixed-signal**

- [Xschem](https://github.com/StefanSchippers/xschem) — Schematic capture for custom analog design
  with SPICE, Verilog, and VHDL netlisting. The front end of the open analog flow.
- [OpenFASOC](https://github.com/idea-fasoc/OpenFASOC) — Automated analog generation: describe a
  temperature sensor or LDO by specification and get a placed-and-routed layout.
- [ALIGN](https://github.com/ALIGN-analoglayout/ALIGN-public) — Analog layout automation from
  netlist to GDS, from the DARPA IDEA program.
- [MAGICAL](https://github.com/magical-eda/MAGICAL) — Machine-generated analog IC layout; the
  academic counterpart to ALIGN.
- [VA-Models](https://github.com/dwarning/VA-Models) — Collection of Verilog-A device models that
  work with OpenVAF and ngspice; the practical starting point for custom compact models.
- [qflow](https://github.com/RTimothyEdwards/qflow) — Complete end-to-end digital synthesis flow;
  the lightweight predecessor to OpenLane, still useful for small designs.

### Open-Source PDKs and Shuttles

- [SkyWater SKY130 PDK](https://github.com/google/skywater-pdk) — The first fully open,
  manufacturable PDK; 130 nm, with a large body of taped-out designs.
- [GlobalFoundries GF180MCU PDK](https://github.com/google/gf180mcu-pdk) — Open 180 nm PDK.
- [IHP Open PDK (SG13G2)](https://github.com/IHP-GmbH/IHP-Open-PDK) — Open 130 nm BiCMOS PDK with
  SiGe HBTs — notable because it includes usable RF devices, which SKY130 does not.
- [open_pdks](https://github.com/fossi-foundation/open-pdks) — The installer that assembles open
  PDKs into forms the open tools actually consume.
- [Tiny Tapeout](https://tinytapeout.com/) — Multi-project shuttle that puts small open designs on
  real silicon for a few hundred dollars. Recent shuttles have used IHP SG13G2 and SkyWater 130,
  with GF180 under evaluation.
- [Tiny Tapeout news and shuttle status](https://tinytapeout.com/news/) — Where to check which
  shuttles are open and which PDKs are supported right now.
- [ChipFoundry](https://chipfoundry.io/) — Shuttle operator that took over open-silicon shuttle
  service after Efabless wound down. Worth reading the current terms before planning a tapeout.
- [ASAP7](https://github.com/The-OpenROAD-Project/asap7) — 7 nm predictive PDK; the standard
  academic vehicle for sub-10 nm physical design experiments (not manufacturable). The
  [r1p7 release](https://github.com/The-OpenROAD-Project/asap7_pdk_r1p7) is the version most
  published results are built on, and
  [ASAP7_for_KLayout](https://github.com/laurentc2/ASAP7_for_KLayout) adds the technology files
  needed to view and edit it.
- [FreePDK45 / FreePDK15](https://eda.ncsu.edu/freepdk/) — Older predictive kits, still widely used
  in teaching and in reproducing published results.
  [FreePDK45_for_KLayout](https://github.com/laurentc2/FreePDK45_for_KLayout) and
  [SKY130_for_KLayout](https://github.com/laurentc2/SKY130_for_KLayout) provide matching KLayout
  technology setups.
- [OpenRPDK28](https://github.com/RIOSLaboratory/OpenRPDK28) — Open process design kit for a 28 nm
  process; one of the few open kits below 45 nm.
- [ICS55 open PDK](https://github.com/openecos-projects/icsprout55-pdk) — 55 nm CMOS open-source PDK
  released by ICsprout, with a stated path to manufacturing. The most advanced node with an openly
  published, foundry-backed kit.
- [lambdapdk](https://github.com/siliconcompiler/lambdapdk) — A library of open PDK packages wrapped
  in a uniform interface, so a design can move between processes without rewriting the flow.
- [volare](https://github.com/chipfoundry/volare) — Version manager and builder for the SKY130 and
  GF180MCU PDKs. Pin your PDK version the way you would pin a compiler.
- [IIC-OSIC-TOOLS](https://github.com/iic-jku/IIC-OSIC-TOOLS) — All-in-one Docker image with the open
  analog and digital flows preinstalled and SKY130, GF180, IHP SG13G2 and SG13C5 PDKs bundled. The
  single fastest way to get a working environment, and the one most tutorials assume.
- [ihp-sg13g2 AMS chip template](https://github.com/iic-jku/ihp-sg13g2-ams-chip-template) —
  End-to-end analog/mixed-signal tutorial and project skeleton for the IHP open PDK, from schematic
  to submitted GDS.
- [IHP Open PDK documentation](https://github.com/IHP-GmbH/IHP-Open-PDK-docs) and
  [FMD-QNC tapeouts](https://github.com/IHP-GmbH/IHP-Open-FMD_QNC-Tapeouts) — Reference designs
  actually fabricated on the IHP open process.
- [Caravel](https://github.com/chipfoundry/caravel) — The SoC harness that open MPW submissions are
  wrapped in, providing the padframe, management core, and test infrastructure around your design.
  The [original Efabless repository](https://github.com/efabless/caravel) is the historical
  reference; ChipFoundry maintains the active fork.
- [SSCS Chipathon](https://github.com/sscs-ose/sscs-chipathon-2026) — IEEE Solid-State Circuits
  Society open-source design program: design, tape out, test, publish. Includes full course
  material.
- [Tiny Tapeout support tools](https://github.com/TinyTapeout/tt-support-tools) and the
  [IHP submission template](https://github.com/TinyTapeout/ttihp-verilog-template) — The build
  infrastructure and project skeleton behind the shuttle.
- [pavona](https://github.com/pavona/pavona) — Library of modular, tapeout-proven, secure-by-default
  open silicon blocks; useful when you need IP you can trust in a shuttle submission.

### 3D Floorplanning and Physical Design Research

- [Open3DFlow](https://github.com/RIOSLaboratory/Open3DFlow) — Open 3D IC platform with TSV
  modeling, thermal, and SI analysis layered onto open EDA tools.
- [Cool-3D](https://github.com/iCAS-SJTU/Cool-3D) — Thermal-aware early-phase design space
  exploration for microfluidic-cooled 3D ICs.
- [Compact-2D / Pin3D / Cascade2D](https://arxiv.org/list/cs.AR/recent) — The Georgia Tech lineage
  of pseudo-3D physical design methods that fold a 2D placement into two tiers; search for the
  authors' releases, which appear intermittently.
- [MFIT — multi-fidelity chiplet thermal modeling](https://arxiv.org/abs/2410.09188) — Practical if
  you need thermal inside an optimization loop rather than as a signoff check.
- [OpenROAD 3D and multi-die research branches](https://github.com/The-OpenROAD-Project) — Watch the
  org rather than any single repository; 3D support arrives as separate projects.
- [Open Source EDA Birds of a Feather](https://open-source-eda-birds-of-a-feather.github.io/) —
  Annual DAC session; the slide archive is the best single map of what open EDA can and cannot do
  each year.

**Placement, partitioning and routing research**

The tools below are 2D, but they are the substrate every 3D and chiplet method builds on, and most
published 3D results are reported against them.

- [DREAMPlace](https://github.com/limbo018/DREAMPlace) — GPU-accelerated analytical placement that
  reframed placement as a deep-learning training problem. Orders of magnitude faster than the
  CPU placers it replaced, and the baseline nearly every placement paper now compares against.
- [Xplace](https://github.com/cuhk-eda/Xplace) — Fast, deterministic GPU placement framework with
  detailed-routability and timing optimization.
- [DG-RePlAce](https://github.com/ABKGroup/DG-RePlAce) — GPU-accelerated version of RePlAce, the
  global placer inside OpenROAD.
- [TritonPart](https://github.com/ABKGroup/TritonPart) — Open hypergraph partitioner; the front end
  to most partition-driven 3D and chiplet flows.
- [CU-GR](https://github.com/cuhk-eda/cu-gr) — Global routing tool from CUHK, a common research
  baseline.
- [PROBE3.0](https://github.com/ABKGroup/PROBE3.0) — Methodology for measuring the true quality gap
  between design tools and achievable results, by generating designs with known optimal solutions.
  The honest answer to "how good is my placer really?"
- [RosettaStone](https://github.com/ABKGroup/RosettaStone) — Translations between the enablements and
  formats that make cross-tool comparison possible.
- [FakeRAM2.0](https://github.com/ABKGroup/FakeRAM2.0) — Generates plausible memory macro
  abstracts (LEF/Liberty) when you have no memory compiler, which is the normal situation in
  academic flows.
- [NanGate45](https://github.com/ABKGroup/NanGate45-Synopsys-Enablement) and
  [ASAP7](https://github.com/ABKGroup/ASAP7-Synopsys-Enablement) Synopsys enablements — Reference
  setups for reproducing published commercial-tool results.
- [PlacementEssentialReadings](https://github.com/ABKGroup/PlacementEssentialReadings) — Curated
  reading list for physical design placement; a good syllabus if you are entering the field.
- [ORFS-Agent](https://github.com/ABKGroup/ORFS-Agent) — LLM-driven autotuning of OpenROAD flow
  parameters, an early example of agents doing PPA search.
- [ISPD 2026 contest](https://github.com/ABKGroup/ISPD26-Contest) — Post-placement buffering and
  sizing. The ISPD/ICCAD contest problems are how this field distributes benchmarks.
- [iEDA](https://github.com/OSCC-Project/iEDA) — Independent open EDA infrastructure covering
  netlist to GDS, from the Chinese open-source EDA community.
- [mflowgen](https://github.com/mflowgen/mflowgen) — Modular ASIC/FPGA flow generator; builds
  reproducible tool flows out of composable node graphs.
- [Hammer](https://github.com/ucb-bar/hammer) — Berkeley's physical design flow abstraction, letting
  one RTL design target multiple technologies and tool vendors.

### Layout, Extraction and Signoff Utilities

- [gdstk](https://github.com/heitzmann/gdstk) — Fast GDSII/OASIS manipulation in C++/Python.
- [gdspy](https://github.com/heitzmann/gdspy) — The predecessor; still common in older scripts.
- [gdsfactory](https://github.com/gdsfactory/gdsfactory) — Layout-as-code framework with a strong
  photonics and packaging component library.
- [OpenVAF](https://github.com/pascalkuthe/OpenVAF) — Open Verilog-A compiler, enabling open
  compact-model development.
- [Hdl21](https://github.com/dan-fritchman/Hdl21) — Python-embedded hardware description for analog
  and mixed-signal generators.
- [FastCap / FastHenry (via FastFieldSolvers)](https://www.fastfieldsolvers.com/) — Classic
  capacitance and inductance extraction; still useful for interposer and package parasitics.
- [OpenEMS](https://github.com/thliebig/openEMS-Project) — Open FDTD electromagnetic solver,
  usable for package and interposer structures.
- [Pyaedt](https://github.com/ansys/pyaedt) — Python API to Ansys Electronics Desktop, if you have
  the commercial license and want scripted package analysis.
- [KLayout-PEX](https://github.com/iic-jku/klayout-pex) — Parasitic extraction inside KLayout,
  filling one of the larger gaps in the open signoff flow.
- [gdscheck](https://github.com/aesc-silicon/gdscheck) — Fast standalone DRC engine for GDSII
  layouts, written in Rust.
- [gds2Para](https://github.com/purdue-onchip/gds2Para) — Layout parsing and parameter extraction
  from GDSII, aimed at parasitic and interconnect analysis.
- [xsection](https://github.com/klayoutmatthias/xsection) — Generates process cross-sections from a
  layout and a process description; the fastest way to sanity-check a stack-up.
  [klayout_pyxs](https://github.com/gdsfactory/klayout_pyxs) is the Python port.
- [GDS3D](https://github.com/trilomix/GDS3D) — Renders GDSII layouts as 3D structures using a
  process stack description. Genuinely useful for explaining a BEOL stack to anyone.
- [gdsjam](https://github.com/jwt625/gdsjam) — Web-based collaborative GDSII viewer, for reviewing
  layout without everyone installing a toolchain.
- [phidl](https://github.com/amccaugh/phidl) — Python GDS layout and CAD geometry creation with an
  unusually friendly API; the basis of several hobby and research mask flows.
- [gdshelpers](https://github.com/HelgeGehring/gdshelpers) — Pattern generation for nanostructuring
  and integrated optics.
- [kfactory](https://github.com/gdsfactory/kfactory) — gdsfactory-style layout-as-code on a KLayout
  backend, for large hierarchical layouts.

---

## 11. TCAD and Physical Simulation

### Commercial TCAD

- [Synopsys Sentaurus](https://www.synopsys.com/silicon/tcad.html) — The industry-standard process
  and device TCAD suite; effectively required for advanced-node device development.
- [Silvaco Victory](https://silvaco.com/tcad/) — The main alternative, with process, device, and
  atomistic modules.
- [Cogenda Genius / Visual TCAD](https://www.cogenda.com/) — Lower-cost commercial TCAD, common in
  academia.
- [Global TCAD Solutions (GTS)](https://www.globaltcad.com/) — Specializes in variability,
  reliability, and nano-device simulation.
- [Synopsys QuantumATK](https://www.synopsys.com/manufacturing/quantumatk.html) — Atomistic
  simulation for materials, interfaces, and 2D-material devices.
- [Applied Materials Ginestra](https://www.appliedmaterials.com/us/en/semiconductor/solutions/ginestra.html) —
  Multiscale materials-to-device simulation, strong on reliability and emerging memory.
- [Lam SEMulator3D](https://www.lamresearch.com/products/semulator3d/) — Virtual fabrication:
  predictive 3D process modeling used to debug integration schemes before running wafers. The most
  directly "fab" of the commercial simulators.
- [TCAD Central — software index](https://tcadcentral.com/Software.html) — Community-maintained
  index of TCAD tools, commercial and free.

### Open-Source TCAD and Process Emulation

- [DEVSIM](https://github.com/devsim/devsim) — Finite-volume TCAD device simulator, Apache 2.0
  licensed, scriptable from Python. The most practical open device simulator.
- [Charon](https://charon.sandia.gov/) — Sandia's open-sourced TCAD device code, built on Trilinos
  with finite-element and finite-volume discretizations and parallel nonlinear solvers.
- [ViennaPS](https://github.com/ViennaTools/ViennaPS) — Process and topography simulation library
  modeling 2D/3D surface evolution during etching, deposition, and oxidation, combining level-set
  surface evolution with Monte Carlo ray tracing for flux. Python bindings included.
- [ViennaLS](https://github.com/ViennaTools/ViennaLS) — The sparse-field level-set engine
  underneath ViennaPS, using hierarchical run-length encoding for memory efficiency.
- [ViennaRay](https://github.com/ViennaTools/ViennaRay) — The Monte Carlo ray tracer that computes
  particle flux to the evolving surface; what makes ViennaPS etch models directional.
- [ViennaCS](https://github.com/ViennaTools/ViennaCS) — Volumetric cell-set representation layered on
  the level-set surfaces, for models that need material composition below the surface (implant,
  diffusion, mixed-material etch).
- [ViennaEMC](https://github.com/ViennaTools/ViennaEMC) — Ensemble Monte Carlo carrier transport for
  semiconductors and metals; the transport counterpart to the topography stack.
- [ViennaChem](https://github.com/ViennaTools/ViennaChem) — Derives surface-kinetics models from
  chemical reaction equations, so etch chemistry can be specified declaratively.
- [ViennaFit](https://github.com/ViennaTools/ViennaFit) — Fits ViennaPS process models to
  experimental cross-sections. Calibration is the step that decides whether process simulation is
  useful or decorative.
- [DRIESequences](https://github.com/ViennaTools/DRIESequences) — Emulation models for the DEM, DREM,
  and DREAM deep reactive-ion etch sequences.
- [ViennaHRLE](https://github.com/ViennaTools/ViennaHRLE) — The hierarchical run-length encoded data
  structure underpinning the level-set memory efficiency.
- [ViennaTools organization](https://github.com/ViennaTools) — The full process-simulation stack in
  one place.
- [ViennaPS paper (SoftwareX)](https://www.sciencedirect.com/science/article/pii/S2352711025004194) —
  Describes the architecture and validation cases.
- [pytaurus](https://github.com/thomashirtz/pytaurus) — Python wrapper around Synopsys Sentaurus,
  for scripting commercial TCAD sweeps from a normal toolchain. Requires a Sentaurus license.
- [NanoTCAD ViDES](http://vides.nanotcad.com/vides/) — Open NEGF-based simulator for nanoscale and
  2D-material devices.
- [Kwant](https://kwant-project.org/) — Quantum transport in tight-binding systems; useful for
  nanowire and 2D-channel studies.
- [NEMO5](https://engineering.purdue.edu/gekcogrp/software-projects/nemo5/) — Purdue's multiscale
  nanoelectronics modeling tool.
- [gplugins DEVSIM notebook](https://gdsfactory.github.io/gplugins/) —
  Worked example of driving DEVSIM from a layout-first workflow.

### Atomistic and First-Principles

- [LAMMPS](https://github.com/lammps/lammps) — Molecular dynamics; used for etch/deposition surface
  chemistry, thermal transport, and thin-film mechanics.
- [Quantum ESPRESSO](https://gitlab.com/QEF/q-e) — Plane-wave DFT; the workhorse for band
  structures of candidate channel and barrier materials.
- [VASP](https://www.vasp.at/) — Commercial DFT, the de facto standard in industrial materials
  groups.
- [GPAW](https://gitlab.com/gpaw/gpaw) and [ASE](https://gitlab.com/ase/ase) — Python-native DFT and
  atomistic simulation environment; the easiest on-ramp for scripted materials screening.
- [pymatgen](https://github.com/materialsproject/pymatgen) — Materials analysis library behind the
  Materials Project.
- [Materials Project](https://next-gen.materialsproject.org/) — Open computed database of
  ~150k+ inorganic materials with band gaps, elastic constants, and phase diagrams.
- [NOMAD](https://nomad-lab.eu/) and [AFLOW](http://aflowlib.org/) — Alternative materials data
  repositories, useful for cross-checking.
- [Exploring transport in APAM-enabled pn junctions (arXiv)](https://arxiv.org/abs/2410.17408) —
  Example of atom-precision device modeling connecting DFT to TCAD.

### Electromagnetics and Photonics

- [Meep](https://github.com/NanoComp/meep) — Open FDTD solver from MIT; the standard free tool for
  photonic component simulation.
- [MPB](https://github.com/NanoComp/mpb) — Photonic band structure computation.
- [openEMS](https://github.com/thliebig/openEMS-Project) — Open FDTD for RF, package, and
  interconnect structures.
- [scikit-rf](https://github.com/scikit-rf/scikit-rf) — RF/microwave network analysis in Python;
  practical for de-embedding package S-parameters.
- [Ansys Lumerical](https://www.ansys.com/products/optics) — The commercial photonic simulation
  standard, relevant for co-packaged optics work.

---

## 12. AI and Machine Learning for Semiconductors

### ML for EDA

- [awesome-ai4eda](https://github.com/Thinklab-SJTU/awesome-ai4eda) — Curated bibliography of AI
  for EDA papers; the best entry point to the literature.
- [CircuitNet](https://circuitnet.github.io/) — Open dataset for ML in EDA: 10k+ samples from
  commercial tool runs on open RISC-V designs, with labels for routability, IR drop, and timing.
- [CircuitNet 2.0 (ICLR 2024)](https://openreview.net/forum?id=nMFSUjxMIl) — Extended to CPU, GPU,
  and AI-chip designs in a 14 nm FinFET flow.
- [CircuitNet paper (arXiv)](https://arxiv.org/abs/2208.01040) — Original dataset description.
- [Circuit Training (Google)](https://github.com/google-research/circuit_training) — Open
  reinforcement-learning framework for chip floorplanning, released alongside the Nature placement
  paper.
- [OpenABC-D](https://github.com/NYU-MLDA/OpenABC) — Large-scale dataset for learning logic
  synthesis; pairs AIG designs with synthesis recipes and QoR labels.
- [EDALearn — RTL-to-signoff ML benchmark (arXiv)](https://arxiv.org/abs/2312.01674) — Benchmark
  aimed at reproducibility across the whole flow.
- [MLCAD symposium](https://mlcad.org/) — The dedicated ML-for-CAD venue, with annual contests.
- [ICCAD CAD Contest](https://iccad-contest.org/) — Long-running contest whose problem sets became
  the field's standard benchmarks.
- [EPFL logic synthesis benchmarks](https://github.com/lsils/benchmarks) — The reference
  combinational benchmark suite.
- [awesome-AIEDA-works](https://github.com/OSCC-Project/awesome-AIEDA-works) — A second AI4EDA
  bibliography, organized by flow stage rather than by method.
- [CircuitOps](https://github.com/NVlabs/CircuitOps) — Turns EDA design data into labeled property
  graphs, so ML pipelines can consume netlists, placement, and timing without bespoke parsers.
  The unglamorous piece that makes the rest reproducible.
- [TimingPredict](https://github.com/TimingPredict/TimingPredict) — Graph neural network for
  pre-routing timing prediction, structured after a real timing engine rather than treating the
  netlist as a generic graph.
- [GNN4REL](https://github.com/lilasrahis/GNN4REL) — Graph neural networks predicting circuit
  reliability degradation from process variation and aging (TCAD 2022).

### ML for Lithography and Masks

- [OpenILT](https://github.com/OpenOPC/OpenILT) — PyTorch platform for ILT research with GPU
  acceleration and ICCAD13 benchmark models.
- [LithoBench](https://github.com/shelljane/lithobench) — Benchmark suite for AI computational
  lithography with 100k+ clips.
- [Generic lithography modeling with optics-inspired neural networks (arXiv)](https://arxiv.org/abs/2203.08616) —
  Physics-informed architecture that generalizes across process conditions.
- [ILILT (arXiv)](https://arxiv.org/abs/2405.03574) — Implicit learning of ILT.
- [Differentiable lithography imaging framework (arXiv)](https://arxiv.org/abs/2409.15306) —
  Makes the imaging model itself trainable.
- [NVIDIA cuLitho](https://developer.nvidia.com/culitho) — Production GPU acceleration for
  computational lithography.
- [Hotspot detection benchmarks — ICCAD 2012/2016](https://iccad-contest.org/) — The canonical
  layout-hotspot datasets.

### ML for Fab, Metrology and Yield

- [Virtual metrology](https://semiengineering.com/tag/virtual-metrology/) — Predicting
  wafer measurements from equipment sensor traces; the highest-ROI fab ML application.
- [Automated defect classification with ML](https://semiengineering.com/tag/defect-classification/) —
  Modern deep-learning ADC versus the rule-based systems it replaces.
- [WM-811K wafer map dataset](https://www.kaggle.com/datasets/qingyi/wm811k-wafer-map) — 811,457
  wafer maps from a real 300 mm line across 46,293 lots, with eight labeled defect patterns. The
  canonical public dataset in this area.
- [WM-811K benchmark implementations](https://github.com/xalzh/WM-811k) — Integrated framework
  comparing CNN, DenseNet, MobileNet, and ResNet variants on the dataset.
- [Wafer defect classification reference repo](https://github.com/iamxichen/Semiconductor-Wafer-Defect-Classification) —
  Clean baseline implementation.
- [Defect_KAN](https://github.com/judahobi/Defect_KAN) — EfficientNet + spatial pyramid pooling +
  Kolmogorov-Arnold network on WM-811K, with Grad-CAM interpretability.
- [Wafer map defect classification with tiny vision transformers (arXiv)](https://arxiv.org/abs/2504.02494) —
  Recent architecture comparison on the same benchmark.
- [Autoencoder augmentation for wafer maps (arXiv)](https://arxiv.org/abs/2411.11029) — Addresses
  the severe class imbalance that dominates this dataset.
- [Domain adaptation with minimal manufacturing data (arXiv)](https://arxiv.org/abs/2306.00202) —
  The realistic fab problem: very few labeled examples of the defect you care about.
- [DAGM 2007 defect dataset](https://hci.iwr.uni-heidelberg.de/content/weakly-supervised-learning-industrial-optical-inspection) —
  Classic optical surface inspection benchmark, still used for pretraining.
- [WaPIRL](https://github.com/hgkahng/WaPIRL) — Self-supervised pretraining for wafer bin map defect
  classification. The right approach when unlabeled maps are abundant and labels are not, which is
  every real fab.
- [WaferDC](https://github.com/SpatialAILab/WaferDC) — Long-tailed detection and classification of
  wafer defects from SEM images, robust to varying image backgrounds (EAAI 2025).
- [MixedWM38 vision transformer baseline](https://github.com/PanithanS/Wafers-Defect-Recognition-using-Visual-Transformer) —
  Worked example on the mixed-type defect dataset, where a single wafer carries superimposed
  patterns — the realistic case that WM-811K's eight clean classes understate.
- [WaferMap](https://github.com/Junliangwangdhu/WaferMap) — Additional wafer map defect dataset and
  models.
- [Semiconductor-Fault-Detection](https://github.com/markditsworth/Semiconductor-Fault-Detection) —
  Classifier built on real foundry process data rather than images; a useful counterpoint to the
  vision-heavy literature.
- [`wafermap` topic on GitHub](https://github.com/topics/wafermap) — Live index of wafer-map
  tooling and models.

**Wafer map and defect file tooling**

- [klarfkit](https://github.com/MichaelHotaling/klarfkit) — Read, plot, and edit KLARF files, the
  KLA-defined format that inspection tools emit. If you work with real inspection output rather than
  Kaggle exports, you need this.
- [wafermap](https://github.com/cap1tan/wafermap) — Python package for plotting wafer maps with
  correct notch, edge exclusion, and die grid handling.
- [wfmap](https://github.com/xlhaw/wfmap) — Wafer map visualization built on pandas and bokeh.
- [uia-wafermap](https://github.com/uia4w/uia-wafermap) — Shot map and wafer map rendering in
  JavaScript, for building web dashboards.
- [stdf2map](https://github.com/CozumelDiver/stdf2map) — Converts STDF test data into wafer bin
  maps, closing the loop between test and inspection views of the same wafer.

### LLMs for Chip Design

- [VerilogEval (NVIDIA)](https://github.com/NVlabs/verilog-eval) — The standard benchmark for
  LLM Verilog generation, from ICCAD 2023.
- [Revisiting VerilogEval (arXiv)](https://arxiv.org/abs/2408.11053) — Updated harness and results
  as models improved past the original benchmark.
- [RTLLM](https://github.com/hkust-zhiyao/RTLLM) — Open benchmark for RTL generation from natural
  language, with syntax, functionality, and quality metrics.
- [ChipBench (arXiv)](https://arxiv.org/abs/2601.21448) — Next-generation benchmark with realistic
  hierarchical modules, debugging cases, and reference-model tasks across Python, SystemC, and
  CXXRTL — built because earlier benchmarks saturated.
- [ChipVerilog (arXiv)](https://arxiv.org/abs/2607.13079) — Large OpenCores-derived benchmark for
  Verilog RTL generation.
- [LLM4ChipDesign](https://github.com/FCHXWH823/LLM4ChipDesign) — Curated collection of LLM-aided
  hardware design and verification work.
- [LLM4IC](https://github.com/DfX-NYUAD/LLM4IC) — NYU's work on LLMs in chip design with a security
  and trust focus.
- [Agentic hardware verification token allocation (arXiv)](https://arxiv.org/abs/2604.15657) —
  Empirical study of where inference compute actually helps in verification agents.
- [SemiKong](https://github.com/aitomatic/semikong) — Open domain-specific model trained on
  semiconductor process and equipment knowledge rather than RTL. Aimed at etch and deposition
  process engineering questions, which is a different problem from code generation.
- [LLM4Chip](https://github.com/renjieli08/LLM-4-Chip) — End-to-end chip design and generation with
  LLMs using reward-driven reinforcement learning.
- [ORFS-Agent](https://github.com/ABKGroup/ORFS-Agent) — Agent that tunes OpenROAD flow parameters,
  one of the more concrete demonstrations of agents doing real PPA optimization.
- [Generative AI for semiconductor design](https://github.com/aws-samples/generative-ai-for-semiconductor-design) —
  Reference engineering-assistant architecture over semiconductor documentation.

### Datasets and Benchmarks

| Dataset | Domain | Notes |
|---|---|---|
| [WM-811K](https://www.kaggle.com/datasets/qingyi/wm811k-wafer-map) | Wafer map defects | 811k maps, 8 defect classes, real 300 mm line |
| [MixedWM38](https://github.com/Junliangwangdhu/WaferMap) | Wafer map defects | 38 classes including mixed-type patterns |
| [CircuitNet / 2.0](https://circuitnet.github.io/) | ML for EDA | Routability, IR drop, timing labels; 14 nm flow |
| [OpenABC-D](https://github.com/NYU-MLDA/OpenABC) | Logic synthesis | Synthesis recipes + QoR |
| [LithoBench](https://github.com/shelljane/lithobench) | Computational litho | 100k+ mask-optimization clips |
| [ICCAD13 benchmark](https://github.com/OpenOPC/OpenILT) | ILT/OPC | The reference litho model for ILT research |
| [SMT2020](https://p2schedgen.fernuni-hagen.de/) | Fab scheduling | Full 300 mm fab models, HV/LM and LV/HM scenarios |
| [EPFL benchmarks](https://github.com/lsils/benchmarks) | Logic synthesis | Arithmetic and control combinational circuits |
| [VerilogEval](https://github.com/NVlabs/verilog-eval) | LLM RTL generation | Spec-to-RTL, standard reporting |
| [Trust-Hub](https://trust-hub.org/) | Hardware security | Trojan benchmarks, side-channel datasets |
| [Materials Project](https://next-gen.materialsproject.org/) | Materials | Computed properties for screening |

---

## 13. Fab Operations and Manufacturing Science

A leading-edge fab is a re-entrant flow shop with 1,000+ process steps, hundreds of tools,
lot-level priorities, and equipment that requires qualification after every maintenance event. The
scheduling problem is genuinely one of the hardest in industrial engineering.

### Factory Physics and Cycle Time

- [Factory Physics (Hopp & Spearman)](https://factoryphysics.com/) — Little's Law, the VUT
  equation, and the cycle-time/utilization tradeoff that governs every fab planning decision.
- [Cycle time and WIP management in wafer fabs](https://www.semi.org/en/connect/events) — ASMC
  proceedings are the applied literature here.
- [Winter Simulation Conference — semiconductor track](https://www.wintersim.org/) — The main venue
  for fab simulation and scheduling research; papers are open in the INFORMS/IEEE archives.
- [Re-entrant flow shop scheduling literature](https://arxiv.org/list/math.OC/recent) — The
  theoretical framing of the problem.
- [OEE and equipment productivity (SEMI E10/E79)](https://www.semi.org/en/products-services/standards) —
  Standard state model and productivity definitions.

### Scheduling, Dispatching and Simulators

- [SMT2020 — a semiconductor manufacturing testbed](https://p2schedgen.fernuni-hagen.de/) —
  The modern successor to the MIMAC datasets: full 300 mm fab models with 500+ operations and
  1,000+ machines, in high-volume/low-mix and low-volume/high-mix variants.
- [PySCFabSim](https://github.com/prosysscience/PySCFabSim-release) — Customizable open-source
  Python simulator for semiconductor fab scheduling research, compatible with SMT2020.
- [PySCFabSim overview (PDF)](https://prosysscience.github.io/PySCFabSim-release/assets/img/portfolio/asmc_presentation.pdf) —
  Design rationale and performance.
- [MiniFab model](https://p2schedgen.fernuni-hagen.de/) — The small Intel/ASU testbed: 6 steps,
  5 machines, batching. The standard sanity-check problem before scaling to SMT2020.
- [Scalability of RL for fab dispatching (arXiv)](https://arxiv.org/abs/2505.11135) — Compares
  open-source fab models against real industry datasets; a useful reality check on published RL
  results.
- [Semiconductor fab scheduling with self-supervised and RL (arXiv)](https://arxiv.org/abs/2302.07162) —
  Representative modern approach.
- [SimPy](https://gitlab.com/team-simpy/simpy) — Discrete-event simulation in Python; the usual
  substrate for custom fab models.
- [JobShopLib](https://github.com/Pabloo22/job_shop_lib) — Job-shop scheduling library with RL
  environments; a reasonable starting point before committing to a full fab model.
- [OR-Tools CP-SAT](https://github.com/google/or-tools) — The practical constraint solver for
  scheduling subproblems (batching, qual-state-aware assignment, maintenance windows).

### SEMI Standards and Equipment Integration

- [secsgem](https://github.com/bparzella/secsgem) — Pure-Python SECS/GEM implementation covering
  SEMI E5 (SECS-II), E30 (GEM), and E37 (HSMS), with no external dependencies. The only
  widely-used open implementation of fab equipment communication.
- [secsgem documentation](https://secsgem.readthedocs.io/en/latest/) — Includes a working
  host/equipment example, which is the fastest way to understand the protocol stack.
- [go-secs](https://github.com/arloliu/go-secs) — SECS-II, HSMS and SML implemented in Go, for
  building high-throughput equipment interfaces where a Python event loop would not keep up.
- [SECS/GEM overview](https://en.wikipedia.org/wiki/SECS/GEM) — Neutral explanation of the message
  layers and state machines.
- [SEMI EDA / Interface A](https://www.semi.org/en/products-services/standards) — The E120/E125/
  E132/E134 family for equipment data acquisition; how modern fabs get high-rate trace data out of
  tools for APC and virtual metrology.
- [OPC UA for machine-to-machine](https://opcfoundation.org/) — Increasingly the integration layer
  above SECS/GEM in newer facilities and in back-end assembly.
- [MST — open-source SECS/GEM driver commentary](https://mst-sg.com/how-msts-open-source-secs-gem-driver-is-changing-equipment-integration/) —
  Industry perspective on why open equipment integration matters.
- [Ignition SECS/GEM module docs](https://www.docs.inductiveautomation.com/docs/8.1/ignition-modules/secs-gem) —
  Well-written vendor documentation that doubles as a protocol tutorial.

### Cleanroom, Facilities and Sustainability

- [Cleanroom classification (ISO 14644)](https://www.iso.org/standard/53394.html) — Particle count
  classes; ISO 3–5 for lithography areas.
- [Airborne molecular contamination](https://semiengineering.com/tag/contamination/) —
  AMC control is a bigger practical constraint than particle count at advanced nodes.
- [Fab water and energy use](https://www.semi.org/en/industry-groups/semiconductor-climate-consortium) — SEMI's sustainability
  programme, including the Semiconductor Climate Consortium.
- [Fluorinated gas emissions and abatement](https://www.epa.gov/climate-hfcs-reduction) —
  EPA partnership data on process gas emissions; the reason cryo etch's lower GWP is a selling
  point.
- [Ultrapure water systems](https://www.semi.org/en/products-services/standards) — SEMI F63 and
  related standards.
- [Construction Physics — how fabs get built](https://www.construction-physics.com/p/semiconductor-fab-reading-list) —
  Vibration isolation, cleanroom construction sequencing, and why a fab shell costs what it does.

---

## 14. Test, Reliability and Hardware Security

### Test and DFT

Testing a chiplet stack is harder than testing a die: a bad die found after bonding destroys every
good die bonded to it, so known-good-die confidence has to come from pre-bond test that cannot
touch final-pitch bonding pads.

- [IEEE 1838-2019 — test access for 3D stacked ICs](https://standards.ieee.org/ieee/1838/6013/) —
  The primary TAP / secondary TAP / 3D configuration register architecture enabling pre-bond,
  mid-bond, and post-bond test.
- [An inside look at IEEE 1838](https://www.3dincites.com/2020/03/an-inside-look-at-3d-dft-standard-ieee-std-1838-2019/) —
  Readable walkthrough of the standard by people who wrote it.
- [IEEE 1838 explained for 2.5D/3D/3.5D](https://www.lovechip.com/blog/ieee-1838-explained-how-dft-evolves-for-2-5d-3d-and-3-5d-ics) —
  Practical framing with the other standards it composes with.
- [IEEE 1687 (IJTAG)](https://standards.ieee.org/ieee/1687/4460/) — Access and control of embedded
  instruments; the substrate for in-field monitoring in multi-die parts.
- [IEEE 1149.1 (JTAG)](https://standards.ieee.org/ieee/1149.1/4484/) — Boundary scan; still the
  foundation everything else hangs off.
- [Challenges in testing chiplets](https://www.eeworldonline.com/what-are-the-challenges-when-testing-chiplets/) —
  KGD, final test, and system-level test in a heterogeneous stack.
- [Testing the stack — DFT for 3D devices](https://semiengineering.com/can-you-afford-dft-for-3d-stacked-die/) —
  The cost argument, which is usually the deciding one.
- [International Test Conference (ITC)](https://www.itctestweek.org/) — The primary test venue.
- [Advantest and Teradyne ATE platforms](https://www.advantest.com/) — Where the economics of test
  time per device actually get set.
- [System-level test](https://semiengineering.com/tag/system-level-test/) — Increasingly
  mandatory for complex SoCs and stacks that structural test cannot fully cover.

**Working with test data**

STDF (Standard Test Data Format, SEMI E141) is what ATE actually writes. Nearly all published test
analytics work starts by parsing it.

- [STDF-Viewer](https://github.com/noonchen/STDF-Viewer) — Free GUI for exploring STDF files:
  parametric distributions, bin summaries, and wafer maps without writing code.
- [pystdf](https://github.com/cmars/pystdf) — Python STDF parser; the usual starting point for
  building a test-data pipeline.
- [LinqToStdf](https://github.com/marklio/LinqToStdf) — .NET STDF parsing library, for shops built
  on the Microsoft stack.
- [stdf2map](https://github.com/CozumelDiver/stdf2map) — Turns STDF records into wafer bin maps.

### Reliability Physics

- [JEDEC JEP122 — failure mechanisms and models](https://www.jedec.org/standards-documents) —
  The reference document for BTI, HCI, TDDB, electromigration, and stress migration models.
- [IEEE International Reliability Physics Symposium (IRPS)](https://irps.org/) — The venue; the
  tutorial notes are excellent and often circulated freely.
- [Electromigration in advanced interconnects](https://semiengineering.com/knowledge_centers/manufacturing/reliability/electromigration/) —
  Why Ru and Mo change the EM picture as much as the resistance picture.
- [Bias temperature instability and aging](https://semiengineering.com/tag/transistor-aging/) —
  Aging-aware timing signoff, now standard at advanced nodes.
- [Thermomechanical reliability of 3D stacks](https://www.ectc.net/) — ECTC's reliability sessions;
  TSV Cu pumping, underfill delamination, and bump/hybrid-bond fatigue.
- [Moisture, popcorning, and MSL classification (JEDEC J-STD-020)](https://www.jedec.org/standards-documents) —
  Assembly-side reliability that becomes harder as packages get larger and thinner.
- [Automotive-grade qualification (AEC-Q100)](http://www.aecouncil.com/) — The stricter regime, now
  pulling advanced packaging into its scope.

### Hardware Security and Supply Chain Trust

- [Trust-Hub](https://trust-hub.org/) — Benchmarks and datasets for hardware Trojan detection,
  logic locking, and IP protection. The standard evaluation set in the field.
- [CAD for Assurance](https://cadforassurance.org/) — Tool and dataset index for hardware assurance,
  including power/EM side-channel datasets for Trojan benchmarks.
- [AuthenTree — distributed trust for chiplet systems (arXiv)](https://arxiv.org/abs/2508.13033) —
  MPC-based authentication architecture for heterogeneous chiplet packages.
- [Enhancing DFT security in chiplet-based systems (PDF)](https://hal.science/hal-05185796v1/file/JETCAS_2025_final_upload.pdf) —
  The tension between test access and attack surface, which chiplets make worse.
- [Benchmarking at the frontier of hardware security — logic locking (arXiv)](https://arxiv.org/abs/2006.06806) —
  Sober assessment of what the benchmarks in this field do and do not prove.
- [Trojan Playground — RL for Trojan insertion and detection (arXiv)](https://arxiv.org/abs/2305.09592) —
  Adversarial framing of the detection problem.
- [Gate-level information flow tracking (PDF)](https://cseweb.ucsd.edu/~weh140/resource/IEEEComputer_16.pdf) —
  Formal approach to detecting information-flow violations from hardware Trojans.
- [Securing the silicon supply chain](https://techworks.org.uk/s2s26-siemens-blog-securing-the-silicon-supply-chain-why-hardware-trust-matters/) —
  Industry framing of counterfeit, overproduction, and cloning risk.
- [CHES — Cryptographic Hardware and Embedded Systems](https://ches.iacr.org/) — The venue for
  side-channel and fault-injection work.
- [HOST — Hardware Oriented Security and Trust](http://www.hostsymposium.org/) — The complementary
  venue focused on supply chain and assurance.

---

## 15. Economics, Markets and Policy

### Market Data and Analysis

- [SEMI](https://www.semi.org/en/products-services/market-data) — Equipment billings, Worldwide Fab
  Forecast, materials market data. The industry's own statistics body.
- [SIA — Semiconductor Industry Association](https://www.semiconductors.org/data/) — Monthly global
  billings, the *State of the Industry* report, and US-centric policy analysis.
- [WSTS](https://www.wsts.org/) — The forecast consortium whose numbers the whole industry plans
  against.
- [TechInsights](https://www.techinsights.com/) — Teardowns, process analysis, and market data
  (absorbed the former IC Insights and Strategy Analytics franchises).
- [Yole Group](https://www.yolegroup.com/) — The reference analyst for packaging, MEMS, imaging,
  and compound semiconductors. Packaging market splits in this list mostly trace back to Yole.
- [SemiAnalysis](https://semianalysis.com/) — Deep technical/financial analysis of fabs, packaging
  capacity, and AI hardware supply chains.
- [Counterpoint, TrendForce, Omdia](https://www.trendforce.com/) — Supply/demand and pricing
  tracking, especially for memory and foundry utilization.

### Policy and Export Controls

- [US BIS — export administration regulations and entity list](https://www.bis.gov/) — The primary
  source. Rules define advanced-node thresholds explicitly (logic at or below 16/14 nm, DRAM at or
  below 18 nm half-pitch, and NAND layer counts).
- [Congressional Research Service — US export controls and China: advanced semiconductors](https://www.congress.gov/crs-product/R48642) —
  The best neutral summary of a fast-moving control regime.
- [CSIS — semiconductor and AI export control analysis](https://www.csis.org/analysis/understanding-us-allies-current-legal-authority-implement-ai-and-semiconductor-export) —
  Focused on allied alignment, which is where the regime's effectiveness is actually determined.
- [European Chips Act](https://www.european-chips-act.com/) — Implementation tracking, plus the
  Chips Act 2.0 proposal adopted in June 2026.
- [SEMI Europe policy briefs](https://www.semi.org/eu) — Monthly EU policy summaries
  from the industry association's perspective.
- [CHIPS and Science Act — NIST program](https://www.nist.gov/chips) — US funding programme,
  including the National Semiconductor Technology Center and the National Advanced Packaging
  Manufacturing Program.
- [NAPMP — National Advanced Packaging Manufacturing Program](https://www.nist.gov/news-events/news/2025/01/us-department-commerce-announces-14-billion-final-awards-support-next) —
  Directly relevant if advanced packaging is your area: this is where US public funding is going.
- [Japan, Korea, India, and China programme trackers](https://www.csis.org/programs/scholl-chair-international-business) —
  CSIS and the OECD both maintain comparative subsidy analysis.

### Cost and Capacity Fundamentals

- [Wafer cost and cost-per-transistor curves](https://semiengineering.com/tag/cost/) —
  The claim that cost per transistor stopped falling is more nuanced than usually stated; this is
  where to check it.
- [Fab capex per 1,000 wafer starts](https://www.semi.org/en/products-services/market-data) —
  Roughly $2–3B per 10k wpm at leading edge, before packaging.
- [Mask set costs at advanced nodes](https://semiengineering.com/tag/photomask/) —
  The NRE that makes chiplet reuse economically compelling.
- [Chiplet economics](https://semiengineering.com/tag/chiplets/) — Where disaggregation pays
  and where it does not.

---

## 16. Learning Resources

### Books

**Process and fabrication**

- *Microchip Fabrication* — Peter Van Zant. The standard novice-to-practitioner guide to the whole
  process flow, deliberately light on mathematics.
- *Fundamentals of Semiconductor Fabrication* — Gary May and Simon Sze. Crystal growth, oxidation,
  lithography, etch, diffusion, implant, deposition, and integration.
- *Fundamentals of Semiconductor Manufacturing and Process Control* — Gary May and Costas Spanos.
  The statistics-and-control companion; the best treatment of SPC/APC in a textbook.
- *Silicon VLSI Technology* — Plummer, Deal, and Griffin. The rigorous process-physics text, with
  the modeling that underpins TCAD.
- *Handbook of Semiconductor Manufacturing Technology* — Doering and Nishi. Reference-grade
  coverage of every module.

**Devices and physics**

- *Physics of Semiconductor Devices* — Sze and Ng. The reference.
- *Fundamentals of Modern VLSI Devices* — Taur and Ning. The scaling-theory text; still the clearest
  derivation of short-channel effects.
- *Nanoscale Transistors* — Lundstrom and Guo. The ballistic-transport framing that matters below
  10 nm.

**Lithography**

- *Fundamental Principles of Optical Lithography* — Chris Mack. The definitive text.
- *Field Guide to Optical Lithography* — Chris Mack. The condensed version worth keeping on a desk.
- *EUV Lithography* — Vivek Bakshi (ed.). The reference volume on EUV sources, optics, masks, and
  resists.

**Packaging**

- *Semiconductor Advanced Packaging* — John H. Lau. SiP, fan-in and fan-out WLP/PLP, 2D through 3D
  integration, chiplet packaging, and bonding methods, with design/materials/process/reliability
  treated together. The most complete single volume.
- *Chiplet Design and Heterogeneous Integration Packaging* — John H. Lau. The chiplet-specific
  companion.
- *Semiconductor Packaging: Materials Interaction and Reliability* — Andrea Chen and Randy Lo. The
  materials-interaction view, which is where most packaging failures originate.
- *Heterogeneous Integration Roadmap* chapters — free, and more current than any book.

**Industry and history**

- *Chip War* — Chris Miller. The standard geopolitical history.
- *The Chip* — T.R. Reid. The invention of the integrated circuit.
- *Crystal Fire* — Riordan and Hoddeson. The transistor's origin, and the best account of what Bell
  Labs actually was.
- [BookAuthority — semiconductors reading lists](https://bookauthority.org/books/best-semiconductors-books) —
  If you want more.

### Courses and Lecture Series

- [nanoHUB](https://nanohub.org/) — Purdue-hosted platform with free courses *and* runnable
  simulation tools in the browser. Start with
  [Semiconductor Fundamentals](https://nanohub.org/courses/SFUN),
  [Fundamentals of Nanotransistors](https://nanohub.org/courses/NT), and
  [Fundamentals of Nanoelectronics](https://nanohub.org/courses/FON1).
- [MIT OpenCourseWare — Microelectronic Devices and Circuits](https://ocw.mit.edu/search/?q=microelectronics) —
  Full lecture notes and problem sets.
- [Berkeley EE 143 — Microfabrication Technology](https://inst.eecs.berkeley.edu/~ee143/) —
  Process-focused undergraduate course with public materials.
- [Georgia Tech 3D Systems Packaging Research Center](https://prc.gatech.edu/) — Short courses and
  research output specifically on packaging.
- [imec Academy](https://www.imec-int.com/en/academy) — Industry training from the research
  institute itself.
- [SEMI University](https://www.semi.org/en/semi-university) — Workforce-oriented courses on fab
  operations, equipment, and standards.
- [Class Central — semiconductors and microelectronics](https://www.classcentral.com/subject/semiconductors) —
  Aggregated index of ~300 free and paid courses.
- [Zero to ASIC Course](https://www.zerotoasiccourse.com/) — Practical, project-based path from RTL
  to a real tapeout using the open flow.
- [VLSI System Design (VSD)](https://www.vlsisystemdesign.com/) — Large catalogue of hands-on
  open-EDA and PDK courses.
- [Chris Mack's lithography lectures](https://www.lithoguru.com/scientist/tutor.html) — Free
  full-length lithography course.

### Video and Podcasts

- [Asianometry](https://www.youtube.com/@Asianometry) — The best free video explainers on fab
  technology, equipment history, and industry structure.
- [Applied Science](https://www.youtube.com/@AppliedScience) — Ben Krasnow builds semiconductor
  process equipment in a garage; unusually good intuition-builder.
- [Sam Zeloof](https://www.youtube.com/@SamZeloof) — Homemade integrated circuits, which teaches
  the process flow better than most courses.
- [Breaking Analysis / TechInsights webinars](https://www.techinsights.com/events) — Teardown-driven
  technical webinars, often free.
- [The Chip Letter podcast and newsletter](https://thechipletter.substack.com/) — History and
  architecture, well-researched.
- [Moore's Lobby / EE podcasts](https://www.allaboutcircuits.com/podcast/) — Interview-format
  coverage of design and manufacturing.

### Newsletters and Analysis

- [Semiconductor Engineering](https://semiengineering.com/) — Free, daily, and technically serious.
  The single most useful ongoing source for everything in this list.
- [SemiAnalysis](https://newsletter.semianalysis.com/) — Dylan Patel's analysis of fabs, packaging
  capacity, and AI hardware economics. Some free, most paid.
- [Fabricated Knowledge](https://www.fabricatedknowledge.com/) — Doug O'Laughlin on semiconductor
  companies and cycles from an investment perspective.
- [The Asianometry Newsletter](https://www.asianometry.com/) — Written companion to the video
  channel.
- [The Chip Letter](https://thechipletter.substack.com/) — Babbage on semiconductor history,
  architecture, and business strategy.
- [Vik's Newsletter](https://www.viksnewsletter.com/) — Vikram Sekar; strong on packaging and RF.
- [SemiWiki](https://semiwiki.com/) — Long-running community site with EDA and foundry coverage
  plus active forums.
- [3D InCites](https://www.3dincites.com/) — Advanced packaging community and the IFTLE column.
- [Semiconductor Digest](https://www.semiconductor-digest.com/) — Process and materials coverage.
- [EE Times](https://www.eetimes.com/) — Broad industry news with reliable conference reporting.
- [TrendForce Insights](https://insights.trendforce.com/) — Supply chain and capacity news, fast
  and frequently first.
- [Mark LaPedus on Substack](https://marklapedus.substack.com/) — Veteran process-technology
  journalist; excellent on device architecture transitions.

---

## 17. Conferences, Journals and Communities

### Conferences by Topic

| Conference | Focus | When |
|---|---|---|
| [IEDM](https://www.ieee-iedm.org/) | Devices, process, memory — the flagship | December |
| [VLSI Symposium](https://www.vlsisymposium.org/) | Technology + circuits, joint | June |
| [ISSCC](https://www.isscc.org/) | Solid-state circuits | February |
| [SPIE Advanced Lithography + Patterning](https://spie.org/conferences-and-exhibitions/advanced-lithography-and-patterning) | Lithography, masks, metrology, resists | February |
| [ECTC](https://www.ectc.net/) | Advanced packaging — the flagship | May/June |
| [IITC](https://iitc-conference.org/) | Interconnect technology | June |
| [ASMC](https://www.semi.org/en/connect/events) | Manufacturing science and fab data | May |
| [IRPS](https://irps.org/) | Reliability physics | March/April |
| [ITC](https://www.itctestweek.org/) | Test | Autumn |
| [DAC](https://www.dac.com/) | EDA and design | June/July |
| [ICCAD](https://iccad.com/) | CAD algorithms | Autumn |
| [DATE](https://www.date-conference.com/) | Design, automation and test in Europe | Spring |
| [ISPD](https://ispd.cc/) | Physical design | Spring |
| [MLCAD](https://mlcad.org/) | ML for CAD | Autumn |
| [Hot Chips](https://hotchips.org/) | Product architecture disclosures | August |
| [SEMICON West / Europa / Taiwan / Korea](https://www.semi.org/en/connect/events) | Industry + equipment | Various |
| [IMAPS Device Packaging](https://www.imaps.org/) | Applied packaging | March |
| [Winter Simulation Conference](https://www.wintersim.org/) | Fab simulation and scheduling | December |
| [AVS ALD/ALE](https://ald2026.avs.org/) | Atomic layer processes | Summer |
| [ASD Workshop](https://asd2026.avs.org/) | Area-selective deposition | Spring |

### Journals

- [IEEE Transactions on Electron Devices](https://eds.ieee.org/publications) — The device journal.
- [IEEE Electron Device Letters](https://eds.ieee.org/publications) — Short-form device results.
- [IEEE Transactions on Semiconductor Manufacturing](https://eds.ieee.org/publications) — Fab
  process control, yield, and metrology. Underused outside industry.
- [IEEE Transactions on Components, Packaging and Manufacturing Technology (T-CPMT)](https://eps.ieee.org/) —
  The packaging journal.
- [IEEE Transactions on CAD (TCAD)](https://ieee-ceda.org/) — EDA algorithms.
- [Journal of Micro/Nanopatterning, Materials, and Metrology (JM3)](https://www.spiedigitallibrary.org/journals/journal-of-micro-nanopatterning-materials-and-metrology) —
  Lithography and patterning.
- [Journal of Vacuum Science & Technology A/B](https://pubs.aip.org/avs/jva) — Deposition, etch, and
  surface science.
- [Nature Electronics](https://www.nature.com/natelectron/) — High-profile device and materials
  results.
- [ECS Journal of Solid State Science and Technology](https://iopscience.iop.org/journal/2162-8777) —
  Process chemistry.

### Communities

- [r/semiconductors](https://www.reddit.com/r/semiconductors/) and
  [r/chipdesign](https://www.reddit.com/r/chipdesign/) — Active practitioner communities.
- [SemiWiki forums](https://semiwiki.com/forum/) — Industry veterans, often with first-hand fab and
  EDA experience.
- [Open Source Silicon Slack / FOSSi Foundation](https://fossi-foundation.org/) — The hub for open
  hardware and open EDA, including the weekly *El Correo Libre* newsletter.
- [Zero to ASIC community](https://www.zerotoasiccourse.com/) — Practical open tapeout help.
- [imec technology forums](https://www.imec-int.com/en/events) — ITF conferences, often with public
  keynote material.

---

## 18. Research Institutes and Consortia

- [imec](https://www.imec-int.com/) — Leuven. The industry's shared R&D pipeline; every major
  foundry, equipment vendor, and materials supplier is a partner. Publishes more usable public
  material than any other institute.
- [CEA-Leti](https://www.leti-cea.com/) — Grenoble. Strong on 3D sequential integration, imaging,
  and photonics.
- [Fraunhofer IZM / IISB / IPMS](https://www.izm.fraunhofer.de/en.html) — Germany. IZM is one of
  the best public packaging research groups in the world.
- [IME A*STAR](https://www.a-star.edu.sg/ime) — Singapore. Advanced packaging, TSV, and hybrid
  bonding.
- [ITRI](https://www.itri.org.tw/english/) — Taiwan. The institute TSMC and UMC were spun out of.
- [AIST](https://www.aist.go.jp/index_en.html) — Japan's national institute of advanced industrial
  science and technology; its nanoelectronics programmes anchor much of the country's device
  research.
- [Georgia Tech PRC / 3D Systems Packaging](https://prc.gatech.edu/) — US academic packaging
  research with strong industry consortium participation.
- [SRC — Semiconductor Research Corporation](https://www.src.org/) — Consortium funding US academic
  research; the JUMP 2.0 centers are where a lot of pre-competitive work happens.
- [NSTC — National Semiconductor Technology Center](https://www.natcast.org/) — The CHIPS Act R&D
  entity, operated by Natcast.
- [Albany NanoTech / NY CREATES](https://ny-creates.org/) — 300 mm public research fab, IBM's
  research partner.
- [MIT.nano](https://mitnano.mit.edu/), [Stanford SNF](https://snfexfab.stanford.edu/), and the
  [NSF National Nanotechnology Coordinated Infrastructure](https://www.nnci.net/) — Open-access
  cleanrooms; the practical path to running your own process experiments.
- [Chalmers, KTH, EPFL, TU Delft, RWTH Aachen](https://www.epfl.ch/) — European academic groups with
  significant device and packaging programmes.

---

## 19. Industry Map

A compact orientation to who does what. Not exhaustive, and market positions change.

### Leading-Edge Logic Foundries and IDMs

| Company | Role | Leading-edge status |
|---|---|---|
| [TSMC](https://www.tsmc.com/) | Pure-play foundry | N3/N2 in production, A16 with Super Power Rail, A14 targeting High-NA |
| [Samsung Foundry](https://semiconductor.samsung.com/foundry/) | Foundry + IDM | First to GAA at 3 nm; SF2 and below |
| [Intel Foundry](https://www.intel.com/content/www/us/en/foundry/) | IDM + foundry | 18A with RibbonFET + PowerVia; 14A on High-NA |
| [Rapidus](https://www.rapidus.inc/en/) | Greenfield foundry | 2 nm with IBM/imec, single-wafer flow |
| [GlobalFoundries](https://gf.com/) | Foundry | Specialty and mature nodes; exited leading edge |
| [SMIC](https://www.smics.com/en/) | Foundry | Advanced-node capability constrained by export controls |
| [UMC](https://www.umc.com/en/), [Tower](https://towersemi.com/), [Vanguard](https://www.vis.com.tw/) | Foundry | Specialty and mature |

### Memory

[Samsung](https://semiconductor.samsung.com/), [SK hynix](https://www.skhynix.com/),
[Micron](https://www.micron.com/), [Kioxia](https://www.kioxia.com/),
[SanDisk](https://www.sandisk.com/), [YMTC](https://www.ymtc.com/),
[CXMT](https://www.cxmt.com/), [Nanya](https://www.nanya.com/), [Winbond](https://www.winbond.com/)

### EDA and IP

[Synopsys](https://www.synopsys.com/), [Cadence](https://www.cadence.com/),
[Siemens EDA](https://eda.sw.siemens.com/), [Ansys](https://www.ansys.com/) (now part of Synopsys),
[Keysight](https://www.keysight.com/), [Arm](https://www.arm.com/),
[SiFive](https://www.sifive.com/), [Rambus](https://www.rambus.com/),
[Alphawave Semi](https://awavesemi.com/), [Zero ASIC](https://www.zeroasic.com/)

### Standards and Roadmap Organizations

[SEMI](https://www.semi.org/), [JEDEC](https://www.jedec.org/), [IPC](https://www.ipc.org/),
[IEEE EPS](https://eps.ieee.org/), [IEEE EDS](https://ieee-eds.org/),
[UCIe Consortium](https://www.uciexpress.org/), [OCP](https://www.opencompute.org/),
[OIF](https://www.oiforum.com/), [Si2](https://si2.org/), [IRDS](https://irds.ieee.org/)

---

## 20. DIY and Garage Fab

A real fab costs twenty billion dollars. A working transistor costs rather less. This community has
demonstrated lithography, deposition, etch, and functional MOSFETs and small ICs on budgets in the
thousands — which makes it the only way most people will ever touch process engineering directly.
It is also the fastest way to develop intuition for why the real thing is hard.

**Hacker Fab** — a CMU-originated, multi-university effort to build an open, reproducible
"fab in a room" with published designs for every tool in the flow.

- [Hacker Fab documentation](https://github.com/hacker-fab/gitbook) — The project handbook: process
  flows, tool build guides, and results. Start here. Licensed CERN-OHL-S.
- [Stepper](https://github.com/hacker-fab/stepper) — Maskless DLP photolithography stepper software,
  the centerpiece tool. Patterns are projected rather than printed on a reticle, which removes the
  single most expensive item in a garage flow.
- [MicroManipulatorStepper](https://github.com/hacker-fab/MicroManipulatorStepper) — Sub-micrometer
  3D motion control platform; the stage that makes alignment and overlay possible.
- [Atomic layer deposition tool](https://github.com/hacker-fab/ald) — Open ALD reactor design.
- [Atomic force microscope](https://github.com/hacker-fab/afm) — Low-cost AFM hardware and firmware,
  for measuring what you just made.
- [RF impedance matcher](https://github.com/hacker-fab/impedance-matcher) — Automatic matching
  network for a sputtering chamber, from the CMU lab.
- [Layout tool](https://github.com/hacker-fab/Layout-tool-dev) — PHIDL-based layout generation sized
  for hobby-scale mask sets.

**People and channels**

- [Sam Zeloof](https://www.youtube.com/@SamZeloof) — Made the first homemade lithographically
  patterned integrated circuits in a garage lab; the [Z2 write-ups](http://sam.zeloof.xyz/) document
  the full process flow honestly, including the failures.
- [Breaking Taps](https://www.youtube.com/@BreakingTaps) — Electron microscopy, focused ion beam,
  and micro-fabrication experiments with unusually careful methodology.
- [Applied Science](https://www.youtube.com/@AppliedScience) — Ben Krasnow's builds include electron
  microscopes, vacuum systems, and thin-film deposition from scratch.
- [Zero to ASIC Course](https://www.zerotoasiccourse.com/) — The complementary path: rather than
  building the fab, use a shuttle. See [Getting Silicon Made](#open-source-pdks-and-shuttles).

**Reverse engineering**

- [SiliconRE](https://github.com/furrtek/SiliconRE) — Die traces, reconstructed schematics, and
  notes on custom chips reverse-engineered from decapped silicon.
- [Visual6502](http://visual6502.org/) — Polygon-level reconstruction of the 6502 from die photos,
  simulated transistor by transistor. The original proof that a chip can be fully recovered from its
  layout.
- [Ken Shirriff's blog](https://www.righto.com/) — Die-photo reverse engineering of analog and
  digital ICs, explained circuit by circuit.

---

## 21. Related Awesome Lists

- [awesome-semiconductor-startups](https://github.com/aolofsson/awesome-semiconductor-startups) —
  Database of semiconductor startups with technology category, founding year, country, and exits.
  The list this one is modeled on.
- [awesome-opensource-hardware](https://github.com/aolofsson/awesome-opensource-hardware) — 300+
  open-source hardware tools, generators, and reusable designs.
- [awesome-hwd-tools](https://github.com/TM90/awesome-hwd-tools) — Open-source hardware design tools
  with a chip-design focus.
- [awesome-ai4eda](https://github.com/Thinklab-SJTU/awesome-ai4eda) — AI for EDA paper collection.
- [awesome-electronics](https://github.com/kitspace/awesome-electronics) — Broader electronics
  engineering resources.
- [awesome-open-hardware](https://github.com/delftopenhardware/awesome-open-hardware) — Open source
  hardware project practice.
- [LLM4ChipDesign](https://github.com/FCHXWH823/LLM4ChipDesign) — LLM-aided hardware design and
  verification.
- [Semiconductor_Packaging](https://github.com/Lakshana3/Semiconductor_Packaging) — Packaging
  workshop material bridging design and assembly.
- [Semiconductor-Packaging](https://github.com/arunkpv/Semiconductor-Packaging) — Packaging
  fundamentals notes.
- [awesome](https://github.com/sindresorhus/awesome) — The root list, if you need something else
  entirely.

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guidelines; the short
version:

1. **One link, one line, one reason.** Every entry needs a description explaining what it is and why
   someone would open it. "Cool tool" is not a description.
2. **Prefer primary sources.** A vendor technical brief, a standards document, a paper, or a
   repository beats a news article summarizing one. News articles are fine when they are the only
   public account of something.
3. **No dead links, no link farms, no affiliate links, no SEO content pages.**
4. **Keep the sub-10 nm and packaging bias.** Excellent resources about 180 nm analog design belong
   in a different list.
5. **Say when something is paid or proprietary.** This list is not open-source-only, but readers
   should never be surprised by a paywall.

Open a pull request against `README.md`, or open an issue if you would rather just suggest
something.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors to this list have waived all copyright and
related or neighboring rights to this work. See [LICENSE](LICENSE).

Linked resources remain the property of their respective owners and are subject to their own
licenses and terms.
