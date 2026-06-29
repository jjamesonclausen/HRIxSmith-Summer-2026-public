## Log

### 2026-06-24

- Ingested sources/n1.md and sources/va1.md
- Created summary pages for each source
- Extracted key concepts into separate wiki pages
- Updated wiki/index.md with new pages
- Added research Q&A page on lift vs drag VAWTs
- Reorganized concept pages under concepts/ namespace in index (logical grouping; files not yet moved)
- Moved concept pages into wiki/concepts/ directory to match schema
- Created methods/ namespace and moved CFD page (analysis method)
- Extracted AEO calculation and Bin Method from sources/va1.md into methods/
- Updated index to include methods pages and fixed question namespace link
- Anna added summaries folder in wiki and moved va1 and n1 summaries to it

Open questions:
- Need deeper breakdown of aerodynamic concepts (stall, TSR)
- Potential contradictions between efficiency claims across sources
- Should physically move concept files into a concepts/ folder for consistency
- Decide boundary between concepts/ and methods/ for borderline pages (e.g., AEO)
### 2026-06-25 — Ingest HRI2526.md

Task: Ingest new source and create structured wiki pages.

Actions:
- Read and summarized `sources/HRI2526.md`
- Created core concept pages: VAWT, HAWT vs VAWT, Darrieus, Savonius, Hybrid, Parameters
- Created project summary page for HRI Phase 1 work
- Updated `wiki/index.md`

Decisions:
- Split content into concept-level pages for reuse across future sources
- Kept pages concise and source-grounded per wiki rules

Open:
- CFD section, economic analysis, and scaling not yet broken into dedicated pages
- Potential future page: "Urban Wind Conditions"

### 2026-06-25 — Refactor per AGENTS.md

Task: Remove redundant pages and align with schema rules.

Actions:
- Merged new Darrieus and Savonius information into existing concept pages
- Deleted duplicate concept pages in root wiki directory
- Created `summaries/HRI2526-summary.md`
- Updated index to reflect folder structure

Decisions:
- Enforced single source of truth for each concept page
- Separated summaries from concepts per schema

Open:
- VAWT concept page in /concepts may still need enrichment from this source
- Additional concepts (hybrid VAWT, parameters) not yet merged into existing pages

### 2026-06-25 — Complete HRI2526 ingestion

Task: Extract all remaining concepts and methods from HRI2526.md.

Actions:
- Added concept pages: Urban Wind Conditions, Scaling Effects, Economic Viability of VAWTs
- Added method page: Wind Tunnel Testing
- Created Hybrid VAWT and Wind Turbine Parameters concept pages
- Added cross-links across all related pages
- Updated index to include all new concepts

Decisions:
- Treated scaling and economics as first-class concepts due to decision relevance
- Kept CFD in existing methods/CFD.md (not duplicated)

Open:
- CFD validation details could be expanded in methods/CFD.md with explicit links to scaling + wind tunnel
- Consider adding "Power Curve" as its own concept if reused

### 2026-06-25 — Ingest n2.md

Task: Integrate supplementary notes without creating duplicate concepts.

Actions:
- Created `summaries/n2-summary.md`
- Enriched Savonius Turbine with optimization parameters
- Added inefficiency mechanisms and deployment context to VAWT
- Added quantitative economic examples to Economic Viability
- Added hybrid interference note to Hybrid VAWT
- Updated index with new summary

Decisions:
- Treated n2 as corroborating + detail source; merged into existing concept pages

Open:
- Consider a dedicated "Inefficiency Mechanisms" concept if reused across turbines

### 2026-06-25 — Ingest vj1.md

Task: Integrate academic comparative study without duplicating concepts.

Actions:
- Created `summaries/vj1-summary.md`
- Enriched VAWT concept with structural, maintenance, and noise advantages
- Added Betz limit and solidity to Wind Turbine Parameters
- Created `concepts/HAWT vs VAWT.md` for consolidated comparison
- Updated index and cross-links

Decisions:
- Centralized comparison content into a single HAWT vs VAWT concept page
- Treated historical and commercialization notes as context, not standalone concepts

Open:
- Consider adding a dedicated "Torque Ripple" concept if reused

### 2026-06-25 — Merge Lift vs Drag pages

Task: Remove redundant Lift vs Drag concept and merge into VAWT-focused page.

Actions:
- Merged `concepts/Lift vs Drag.md` into `concepts/Lift vs Drag VAWT – Research Question.md`
- Added links to Darrieus, Savonius, and Hybrid VAWT
- Deleted redundant concept file

Decisions:
- Kept a single page combining definition + research question to avoid duplication

Open:
- Consider renaming file to `Lift vs Drag (VAWT).md` for clarity and consistency

### 2026-06-26 — Rename source references

Task: Update wiki references after the source files were renamed to `va1.md` and `vj1.md`.

Actions:
- Updated all wiki citations to use `sources/va1.md`
- Updated all wiki citations to use `sources/vj1.md`
- Renamed source summary pages to `va1-summary.md` and `vj1-summary.md`
- Updated `wiki/index.md` links to the renamed summary pages

Decisions:
- Kept the content changes limited to wiki references and did not touch `sources/`
- Normalized summary-page titles to match the new source IDs

Open:
- None

### 2026-06-26 — Ingest vj2.md

Task: Convert the Savonius-Darrieus hybrid PDF into Markdown and ingest it.

Actions:
- Created `sources/vj2.md` from the PDF in Downloads
- Created `wiki/summaries/vj2-summary.md`
- Updated `wiki/concepts/Hybrid VAWT.md` with the paper's CFD torque results
- Updated `wiki/index.md` to link the new summary

Decisions:
- Kept the source conversion as a standalone markdown file under `sources/`
- Merged the paper's key result into the existing Hybrid VAWT concept instead of creating a duplicate concept page

Open:
- None

### 2026-06-26 — Ingest va2.md

Task: Convert and ingest the new VAWT airfoil optimization PDF.

Actions:
- Converted the PDF into `sources/va2.md`
- Deleted the original PDF after conversion
- Created `summaries/va2-summary.md`
- Added concept pages for H-VAWT and the optimization methods it uses
- Updated `VAWT` and `wiki/index.md` with links to the new pages

Decisions:
- Kept the paper content in the source markdown and the synthesis in wiki pages
- Split reusable techniques into method pages rather than a single umbrella page

Open:
- Figure assets were preserved as placeholders in the markdown source

### 2026-06-26 — Link H-VAWT to Darrieus

Task: Clarify that H-VAWT is a subtype of lift-based Darrieus turbines.

Actions:
- Added a `[[Darrieus Turbine]]` link to `concepts/H-VAWT.md`
- Added a `[[H-VAWT]]` link to `concepts/Darrieus Turbine.md`

Decisions:
- Kept the change to cross-links only

Open:
- None

### 2026-06-26 — Figure audit

Task: Ensure source markdown files retain figure captions and link extracted images where available.

Actions:
- Confirmed `sources/va2.md` and `sources/vj3.md` already link extracted images in `images/`
- Added explicit missing-figure notes to `sources/vj2.md` and `sources/HRI2526.md`
- Added helpful figure links from `va2` into `H-VAWT`, `Kriging Surrogate Model`, `CST Parameterization`, and `Multi-Island Genetic Algorithm`

Decisions:
- Kept missing figures as `> Unverified:` placeholders instead of inventing image files
- Prioritized the most reusable figures for wiki pages

Open:
- `sources/vj2.md` and `sources/HRI2526.md` still need PDFs if you want extracted figure images

### 2026-06-26 — Extract vj2 and HRI figures

Task: Rename existing `va2` figure files to the AGENTS naming scheme and extract figures from the new `vj2` and `HRI2526` PDFs.

Actions:
- Renamed all `va2` image files to `va2-fig*.jpg`
- Extracted hybrid turbine figures to `images/vj2-fig*.jpg`
- Extracted report figures to `images/hri2526-fig*.jpg`
- Updated `sources/va2.md`, `sources/vj2.md`, and `sources/HRI2526.md` to point at the extracted images
- Updated wiki figure links that referenced `va2`

Decisions:
- Used cropped figure blocks from the PDFs rather than leaving placeholder file names
- Kept the HRI report captions in place and linked representative extracted figures near the top

Open:
- The HRI report contains many figures; the extracted images are saved in `images/hri2526-fig*.jpg` for reference

### 2026-06-26 — Add inline figure links

Task: Add helpful inline figure links to wiki pages using the newly extracted HRI and hybrid-turbine images.

Actions:
- Added representative extracted figures to `summaries/HRI2526-summary.md`
- Added inline figures to `concepts/Hybrid VAWT.md`, `concepts/Darrieus Turbine.md`, and `concepts/Savonius Turbine.md`
- Verified the linked image files exist in `images/`

Decisions:
- Kept image links on the pages that gain the most explanatory value from them

Open:
- None

### 2026-06-26 — Ingest vj3 turbulence article

Task: Convert and ingest the new wind-turbulence PDF.

Actions:
- Converted the PDF into `sources/vj3.md`
- Extracted the two embedded figures into `images/vj3-fig1.jpg` and `images/vj3-fig2.jpg`
- Created `summaries/vj3-summary.md`
- Created `concepts/Atmospheric Turbulence.md`
- Updated `wiki/index.md` with the new summary and concept
- Deleted the original PDF after conversion

Decisions:
- Treated atmospheric turbulence as its own reusable concept instead of folding it into urban wind conditions
- Kept the source summary separate from the concept synthesis

Open:
- Could add a narrower `Turbulence Intensity` concept later if another source uses it heavily

### 2026-06-26 — Ingest HRI2526 source update

Task: Fold the latest HRI rooftop VAWT report details into the wiki.

Actions:
- Expanded `summaries/HRI2526-summary.md` with the report structure, rooftop wind data, CFD results, wake comparison, scaling, and economic conclusions
- Added report-specific detail and figure links to `concepts/Hybrid VAWT.md`, `concepts/Urban Wind Conditions.md`, `concepts/Scaling Effects.md`, `concepts/Economic Viability of VAWTs.md`, and `concepts/Darrieus Turbine.md`
- Added report-specific detail and figure links to `methods/Wind Tunnel Testing.md` and `methods/CFD.md`

Decisions:
- Kept the existing concept pages and enriched them instead of creating duplicate report-only pages
- Used the report figures that most directly support the summarized claims

Open:
- The report still contains many additional figures and appendices that could be linked later if they become relevant to a specific question

### 2026-06-26 — Convert Blade Architectures PDF

Task: Convert `sources/Blade Architectures.pdf` into Markdown using the source naming rules.

Actions:
- Created `sources/vj4.md` with the paper title, authors, abstract, section structure, tables, symbols, and references
- Removed the original PDF from `sources/`

Decisions:
- Used the next available `vj` sequence number for the new source file
- Kept the paper as a source document only for now; wiki ingestion can be done next if needed

Open:
- The PDF figure images were not separately extracted in this workspace, so the Markdown preserves figure captions but not embedded image files

### 2026-06-26 — Ingest Blade Architectures source

Task: Add the new small-VAWT blade architecture paper to the wiki.

Actions:
- Created `summaries/vj4-summary.md`
- Created `methods/Blade Element-Momentum Model.md`
- Updated `concepts/Darrieus Turbine.md` and `concepts/H-VAWT.md` with the paper's findings
- Updated `wiki/index.md` with the new summary and method pages

Decisions:
- Reused existing Darrieus and H-VAWT pages rather than creating duplicate blade-architecture concept pages
- Put the predictor under methods because the paper uses it as an analysis workflow rather than a standalone concept

Open:
- The source PDF did not yield separate extracted figure files in this workspace

### 2026-06-26 — Extract Blade Architectures figures

Task: Extract figures from `sources/Blade Architectures.pdf` and save them using the `vj4-fig*.jpg` naming scheme.

Actions:
- Rendered the PDF pages with a local Node/pdfjs pipeline
- Cropped figures 1 through 12 into `images/vj4-fig1.jpg` through `images/vj4-fig12.jpg`
- Linked the new images from `sources/vj4.md`, `summaries/vj4-summary.md`, and `methods/Blade Element-Momentum Model.md`

Decisions:
- Used page-render crops because no direct PDF image extractor was installed in the workspace
- Kept the crop regions broad enough to preserve figure captions where possible

Open:
- None
