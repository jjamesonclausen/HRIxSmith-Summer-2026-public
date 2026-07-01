## Log

### 2026-06-30 — Maintenance pass

- Task: run the wiki maintenance procedure from `schema/`.
- Actions:
  - Read `AGENTS.md` and the `schema/` procedures.
  - Checked the current source and wiki inventory.
  - Confirmed `20` source markdown files and `20` summary pages.
- Decisions:
  - No wiki content changes were needed because the summary inventory matches the source inventory.
  - `schema/Maintain Wiki` is empty, so there was no additional procedure to follow there.
- Open:
  - Re-run ingest if any new source files are added or updated.

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

### 2026-06-29 — Ingest vj6.md

Task: Convert the CFD review PDF into Markdown and ingest it.

Actions:
- Created `sources/vj6.md` from the rendered PDF/OCR text
- Extracted 21 figure crops to `images/vj6-fig*.jpg`
- Created `wiki/summaries/vj6-summary.md`
- Updated `wiki/methods/CFD.md`, `wiki/concepts/VAWT.md`, `wiki/concepts/Dynamic Stall.md`, and `wiki/concepts/Wind Turbine Parameters.md`
- Updated `wiki/index.md` and appended this log entry

Decisions:
- Kept the paper as `vj6.md` because it is a VAWT source added by Julie
- Treated the review as a source for reusable CFD-method and VAWT-concept updates rather than a new standalone concept page

Open:
- None

### 2026-06-29 — Clean vj6 OCR captions

Task: Clean the rough OCR output in `sources/vj6.md`.

Actions:
- Merged split figure captions into single lines
- Fixed obvious OCR artifacts in captions and figure alt text
- Removed dangling continuation fragments left by the initial OCR conversion

Decisions:
- Kept the source grounded in the OCR text rather than inventing missing figure content

Open:
- A few figure references still inherit minor OCR spelling issues from the PDF

### 2026-06-29 — Ingest vj7.md

Task: Convert the straight-bladed VAWT materials paper into Markdown and ingest it.

Actions:
- Created `sources/vj7.md` from the rendered PDF/OCR text
- Extracted `images/vj7-fig1.jpg`, `images/vj7-fig2.jpg`, and `images/vj7-fig3.jpg`
- Created `wiki/summaries/vj7-summary.md`
- Updated `wiki/concepts/VAWT.md` and `wiki/index.md`

Decisions:
- Kept the source as `vj7.md` because it is another Julie VAWT source
- Treated blade material and fatigue as a VAWT concept update rather than creating a separate page

Open:
- The OCR source is rough in places, but the main technical claims and figures are captured

### 2026-06-29 — Ingest vj8.md

Task: Convert the contra-rotating VAWT optimization paper into Markdown and ingest it.

Actions:
- Created `sources/vj8.md` from the rendered PDF/OCR text
- Extracted `images/vj8-fig1.jpg` through `images/vj8-fig20.jpg`
- Created `wiki/summaries/vj8-summary.md`
- Updated `wiki/methods/CFD.md`, `wiki/concepts/VAWT.md`, and `wiki/index.md`

Decisions:
- Kept the source as `vj8.md` because it is another Julie VAWT source
- Folded the optimization workflow into existing CFD and VAWT pages rather than creating a duplicate concept page

Open:
- The OCR source is usable but still rough in a few figure captions and section sentences

### 2026-06-29 — Rewrite vj8 source raw

Task: Replace the paraphrased `sources/vj8.md` with a raw OCR-backed source file.

Actions:
- Rewrote `sources/vj8.md` from the OCR transcript without paraphrasing the paper text
- Kept figure links only as inserted markdown references

Decisions:
- Followed the user's instruction to avoid editing source text when creating source markdown

Open:
- None

### 2026-06-29 — Clean vj8 formatting

Task: Remove header/footer noise and obvious OCR fragments from `sources/vj8.md` without changing the source content.

Actions:
- Removed repeated journal headers, page markers, and standalone numeric artifacts
- Dropped obvious short OCR noise lines from the intro figure block
- Kept the paper text and figure captions intact

Decisions:
- Applied formatting-only cleanup, no paraphrase or content rewrite

Open:
- A few OCR typos remain in the paper text because they are part of the source transcription

### 2026-06-29 — Fix vj8 title block

Task: Restore the paper title and clean the author block in `sources/vj8.md`.

Actions:
- Restored the title as a top-level Markdown heading
- Kept a single formatted author block under it

Decisions:
- Formatting only; no content rewrite

Open:
- None

### 2026-06-29 — Remove vj7 figure links

Task: Make the new `sources/vj7.md` ignore images.

Actions:
- Removed the three embedded Markdown image links from `sources/vj7.md`
- Left the figure caption text in place so the paper structure stays readable

Decisions:
- Kept the change limited to the source markdown file, per request

Open:
- The extracted `images/vj7-fig*.jpg` files remain on disk but are no longer referenced from the source markdown

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

### 2026-06-29 — HRI2526 summary cleanup

Task: Finish the HRI2526 ingest by tightening the summary and figure links.

Actions:
- Added the remaining HRI report figures to `summaries/HRI2526-summary.md`
- Added the rooftop wind-data figure to `concepts/Urban Wind Conditions.md`
- Added the 10 kWh/year and >5,000 year breakeven result to `concepts/Economic Viability of VAWTs.md`
- Strengthened `concepts/Hybrid VAWT.md` with the report's selected-design context

Decisions:
- Kept the update focused on reusable wiki pages rather than creating new report-specific pages

Open:
- None

### 2026-06-29 — Ingest torque_from_wind

Task: Convert the new VAWT dynamic-stall PDF into a source markdown file and extract its figures.

Actions:
- Created `sources/vj5.md` from `sources/torque_from_wind.pdf`
- Rendered the PDF figures into `images/vj5-fig*.jpg`
- Created `summaries/vj5-summary.md`
- Added `concepts/Dynamic Stall.md`
- Updated `concepts/VAWT.md`, `concepts/Darrieus Turbine.md`, `methods/CFD.md`, and `wiki/index.md`

Decisions:
- Used the Julie `vj` naming sequence because the source was added by Julie
- Kept dynamic stall as a new reusable concept instead of burying it inside VAWT or CFD
- Folded the CFD/PIV comparison into the existing CFD method page

Open:
- None

### 2026-06-29 — Reorganize wiki index

Task: Clean up `wiki/index.md` so pages are grouped by folder instead of listed together.

Actions:
- Moved all summary pages into a dedicated `Source summaries` section
- Kept concept pages under `Concepts`
- Added a dedicated `Methods` section for technique pages
- Removed the old mixed `Pages` list
- Fixed the broken research-question link to use the actual `concepts/` path

Decisions:
- Kept the index alphabetical within each folder section for easier scanning

Open:
- None

### 2026-06-29 — Ingest va4.md

Task: Convert the helical VAWT CFD paper into Markdown and ingest it.

Actions:
- Created `sources/va4.md`
- Created `wiki/summaries/va4-summary.md`
- Added `wiki/concepts/Helical VAWT.md`
- Updated `wiki/concepts/VAWT.md`, `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/methods/CFD.md`, and `wiki/index.md`

Decisions:
- Kept the helical rotor as its own concept because it is distinct from the existing H-VAWT page
- Folded the solver and flow-mechanism details into the existing CFD method page instead of creating new method pages

Open:
- Figure images were not extracted in this workspace, so the source file contains figure captions without image links

### 2026-06-29 — Ingest va5.md

Task: Convert the rooftop J-type VAWT design paper into Markdown and ingest it.

Actions:
- Created `sources/va5.md`
- Created `wiki/summaries/va5-summary.md`
- Added `wiki/concepts/J-Type VAWT.md`
- Updated `wiki/concepts/VAWT.md`, `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md`

Decisions:
- Kept the J-type rotor as its own concept because it is a distinct low-cost drag design
- Merged the design targets into the Wind Turbine Parameters page as a concrete example

Open:
- Figure images were not extracted in this workspace

### 2026-06-29 — Ingest va6.md

Task: Convert the HAWT/VAWT comparison paper into Markdown and ingest it.

Actions:
- Created `sources/va6.md`
- Created `wiki/summaries/va6-summary.md`
- Updated `wiki/concepts/HAWT vs VAWT.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md`

Decisions:
- Kept the comparison content in the existing HAWT vs VAWT page instead of creating a new comparison page
- Folded the paper's example performance numbers into Wind Turbine Parameters as reference values

Open:
- Figure images were not extracted in this workspace

### 2026-06-29 — Extract va4 va5 va6 figures

Task: Extract the figure images for `va4.md`, `va5.md`, and `va6.md` and wire them into the source markdowns.

Actions:
- Used the existing temp `pdfextract` tool to render image crops from the three PDFs
- Copied the extracted crops into `images/` as `va4-fig*.jpg`, `va5-fig*.jpg`, and `va6-fig*.jpg`
- Updated `sources/va4.md`, `sources/va5.md`, and `sources/va6.md` to reference the extracted images

Decisions:
- Kept the sequential numbering from extraction order for the saved image files
- Left a short note in each source file for additional composite-panel crops

Open:
- None

### 2026-06-29 — Link va4 va5 va6 figures in wiki

Task: Link the extracted `va4`, `va5`, and `va6` figures into the relevant wiki pages.

Actions:
- Added figure sections to `wiki/summaries/va4-summary.md`, `wiki/summaries/va5-summary.md`, and `wiki/summaries/va6-summary.md`
- Added figure sections to `wiki/concepts/Helical VAWT.md`, `wiki/concepts/J-Type VAWT.md`, and `wiki/concepts/HAWT vs VAWT.md`

Decisions:
- Linked representative figures on the summary and concept pages rather than duplicating every crop across the wiki

Open:
- None

### 2026-06-29 — Expand figure links

Task: Add figure links to the broader wiki pages where the captions and content are directly useful, while keeping the source markdown figure blocks intact.

Actions:
- Added `va4`, `va5`, and `va6` figures to `wiki/concepts/VAWT.md`
- Added `va4`, `va5`, and `va6` figures to `wiki/concepts/Wind Turbine Parameters.md`
- Added `va4` figures to `wiki/methods/CFD.md`
- Added more `va5` and `va6` figures to `wiki/concepts/J-Type VAWT.md` and `wiki/concepts/HAWT vs VAWT.md`

Decisions:
- Preferred pages where the figure captions clarify the written claims instead of duplicating every figure everywhere

Open:
- The source markdown still includes a note for extra composite crops that do not have clean standalone captions

### 2026-06-29 — Fix wiki image paths

Task: Fix broken image links in wiki notes where Obsidian was resolving `../images/...` against `wiki/` instead of the repo root `images/` folder.

Actions:
- Updated image links in `wiki/concepts/`, `wiki/summaries/`, and `wiki/methods/` from `../images/...` to `../../images/...`
- Confirmed `sources/*.md` image links were already correct and left them unchanged

Decisions:
- Kept the source markdown relative paths as-is because they already point correctly from `sources/` to the root `images/` directory

Open:
- None

### 2026-06-29 — Tighten AGENTS figure-path rule

Task: Update `AGENTS.md` so future wiki figure links use the correct relative path from the file location.

Actions:
- Added an explicit rule for `sources/*.md` vs `wiki/*/*.md` image paths
- Added a requirement to verify image paths from the file’s own folder before adding links

Decisions:
- Kept the rule minimal and specific to the path-depth bug that caused the broken Obsidian links

Open:
- None

### 2026-06-29 — Rework va4 image extraction

Task: Re-do the `va4.md` image extraction so the source file explicitly links every extracted crop.

Actions:
- Replaced the vague `va4-fig20.jpg` through `va4-fig42.jpg` note in `sources/va4.md`
- Added explicit Markdown image links for every extracted crop currently present, `va4-fig20.jpg` through `va4-fig41.jpg`
- Marked `va4-fig41.jpg` as preview-unverified because the in-tool image preview could not render it cleanly

Decisions:
- Kept the existing figure captions intact and only changed the extraction block below Figure 19
- Used a generic crop label for the extra assets because their one-to-one figure mapping is not cleanly recoverable from the cropped files alone

Open:
- Verify whether `va4-fig41.jpg` should be renamed or re-extracted if the original PDF becomes available again

### 2026-06-30 — Review schema instructions

Task: Review `AGENTS.md` and the files under `schema/` for clarity and usefulness.

Actions:
- Read `AGENTS.md` and the available schema files in `schema/`
- Noted that `wiki/schema` does not exist in the repository; the procedures live in top-level `schema/`

Decisions:
- Treated the instruction set as mostly clear and actionable, but flagged a few conflicts and ambiguities for follow-up

Open:
- Resolve the folder-path mismatch in the wording (`wiki/schema` vs `schema/`)
- Reconcile the conflicting figure-handling instructions between `Convert PDF to MD` and `Extract Figure`
- Clarify the empty `Maintain Wiki` procedure or remove it if intentional

### 2026-06-30 — Re-review updated schema

Task: Check whether the small schema edits improved clarity.

Actions:
- Re-read the updated `AGENTS.md` and schema files
- Verified that the repo-path wording now points at `schema/` instead of `wiki/schema`
- Checked for remaining instruction conflicts and lingering examples that could mislead execution

Decisions:
- Considered the instruction set noticeably better than before, with the main remaining rough edge being a few inconsistent path/examples rather than structural confusion

Open:
- Confirm the `../images/...` example in `schema/Ingest Source` if the intended wiki image path is `../../images/...`
- Decide whether `schema/Maintain Wiki` should stay as an empty placeholder

### 2026-06-30 — Duplicate PDF check

Task: Ingest the newly added PDF in `PDFs/`.

Actions:
- Verified the new PDF is a duplicate copy of the already ingested contra-rotating VAWT paper
- Confirmed the paper is already represented by `sources/vj8.md` and `wiki/summaries/vj8-summary.md`
- No source, wiki, or figure updates were needed

Decisions:
- Avoided creating a duplicate source entry for the same paper

Open:
- None

### 2026-06-30 — Record torque ripple explanation

Task: Add the user's torque-ripple understanding to the learning log.

Actions:
- Added a new `Torque ripple` entry to `wiki/learning-log.md`
- Captured the explanation that torque ripple is uneven torque during rotation and can lower efficiency

Decisions:
- Kept the learning-log entry in the user's own wording style rather than expanding it

Open:
- None

### 2026-06-30 — Add vj9 summary page

Task: Create a summary page for `sources/vj9.md` and link it from the wiki index.

Actions:
- Read the rebuilt `sources/vj9.md` and existing summary-page style
- Created `wiki/summaries/vj9-summary.md`
- Added source-grounded bullets covering the scooplet design, CFD workflow, 39% power-coefficient improvement, and 3D validation results
- Added representative figure links to the summary page
- Updated `wiki/index.md` to link `vj9-summary`

Decisions:
- Kept the summary concise and source-cited, matching the existing wiki summary style

Open:
- None

### 2026-06-30 — Re-ingest vj9 source Markdown

Task: Rebuild `sources/vj9.md` from the matching PDF while keeping the existing extracted images.

Actions:
- Followed `schema/Convert PDF to MD` and `schema/Extract Figure`
- Re-read `PDFs/1-s2.0-S0959652620313573-main.pdf`
- Regenerated `sources/vj9.md` with frontmatter, title, article info, abstract, section headings, subsections, references, and glossary headings
- Kept existing `images/vj9-fig1.jpg` through `images/vj9-fig24.jpg` unchanged
- Reinserted all 24 figure captions with Markdown links to the existing image files
- Cleaned obvious page-header/footer clutter and repaired the page-1 introduction flow where the previous extraction mixed columns
- Verified 24 links, 24 existing image files, no broken relative paths from `sources/`, frontmatter, title heading, and 21 Markdown headings

Decisions:
- Did not re-extract image files because the user asked to keep the images
- Preserved PDF-derived text rather than summarizing or paraphrasing the source

Open:
- Some equations remain rough because the source PDF text extraction represents equations poorly

### 2026-06-30 — Replace vj9 typed equations with images

Task: Replace rough OCR/PDF-extracted equations in `sources/vj9.md` with equation image crops.

Actions:
- Located the rough equation text in section `2. Savonius-style wind turbine modeling`
- Cropped equations (1) through (5) from `PDFs/1-s2.0-S0959652620313573-main.pdf`
- Added `images/vj9-eq1.jpg` through `images/vj9-eq5.jpg`
- Replaced the typed equation fragments in `sources/vj9.md` with Markdown image links
- Verified five equation links, five image files, and no broken relative paths from `sources/`

Decisions:
- Used equation-specific filenames instead of figure filenames because these are not numbered figures in the paper
- Kept surrounding explanatory text unchanged

Open:
- None

### 2026-06-30 — Recommend schema figure-extraction update

Task: Explain what to add to the schema so figure extraction happens consistently in future sessions.

Actions:
- Recommended adding a Python/PyMuPDF implementation note to `schema/Extract Figure`
- Recommended requiring source/PDF matching, rendered fallback extraction, Markdown linking, and verification checks
- Added a learning-log prompt for the human to capture the schema-design idea in their own words

Decisions:
- Did not edit the schema file directly because the user asked what to add rather than asking for the edit to be made

Open:
- User can approve applying the schema update directly

### 2026-06-30 — Fix vj10 figure crops

Task: Fix the figure images for `sources/vj10.md` using the schema extraction rules.

Actions:
- Compared `sources/vj10.md`, `images/vj10-fig*.jpg`, and `PDFs/1-s2.0-S0959652619304585-main.pdf`
- Found that the existing figure crops included too much surrounding page text and table content
- Re-rendered tighter visible figure regions for `images/vj10-fig1.jpg` through `images/vj10-fig11.jpg`
- Moved figure links out of generated `Figures extracted from this page` blocks and placed them next to the original captions
- Preserved the Figure 2 caption from the PDF while relocating its image link
- Verified 11 links, 11 image files, no broken relative paths from `sources/`, no leftover generated figure blocks, and reviewed an after-fix contact sheet

Decisions:
- Used rendered visible regions because several `vj10` figures are vector/text drawings rather than clean embedded image assets
- Kept existing file names so wiki references to `vj10-fig*.jpg` remain valid

Open:
- None

### 2026-06-30 — Ingest vj10.md

Task: Ingest the newest PDF in `PDFs/`.

Actions:
- Identified `PDFs/1-s2.0-S0959652619304585-main.pdf` as the newest PDF by filesystem timestamp
- Converted it into `sources/vj10.md`
- Extracted 11 rendered figure crops to `images/vj10-fig1.jpg` through `images/vj10-fig11.jpg`
- Created `wiki/summaries/vj10-summary.md`
- Created `wiki/concepts/Wind Shear.md`
- Updated `wiki/methods/Blade Element-Momentum Model.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Atmospheric Turbulence.md`, and `wiki/concepts/Urban Wind Conditions.md`
- Updated `wiki/index.md`

Decisions:
- Used `vj10.md` as the next Julie wind-turbine source ID because the new PDF is part of the same current PDF batch and `vj9.md` already exists
- Treated wind shear as a reusable concept because it is central to the paper and connects BEM, turbine parameters, atmospheric turbulence, and urban wind conditions
- Used rendered page crops for figures because standalone PDF image-extraction tooling was not available in the workspace

Open:
- The converted source text is usable but retains some PDF text-extraction artifacts such as split words and rough equations

### 2026-06-30 — Check Python and extensions

Task: Check whether the newly installed Python and image-extraction-related extension are visible from this workspace.

Actions:
- Confirmed `python --version` reports Python 3.14.6
- Listed VS Code extensions available through `code --list-extensions`
- Found Python-related extensions and `tomoki1207.pdf`, which may be the PDF/image extraction-related extension

Decisions:
- Did not modify project source or wiki content beyond this log entry

Open:
- Confirm the exact extension name if `tomoki1207.pdf` is not the one the user meant

### 2026-06-30 — Extract vj9 figures

Task: Use the schema figure-extraction procedure with the available Python tooling.

Actions:
- Read `schema/Extract Figure` and confirmed the required naming/linking rules
- Confirmed Python has `PyMuPDF` installed for PDF image extraction/rendering
- Matched `sources/vj9.md` to `PDFs/1-s2.0-S0959652620313573-main.pdf`
- Rendered 24 visible figure regions into `images/vj9-fig1.jpg` through `images/vj9-fig24.jpg`
- Added Markdown image links near the corresponding original captions in `sources/vj9.md`
- Verified there are 24 links, 24 image files, no broken relative paths from `sources/`, and reviewed a contact sheet for figure order

Decisions:
- Used Python/PyMuPDF rather than the VS Code PDF extension because the extension is visible only as an editor extension and does not expose a reliable CLI extractor here
- Rendered visible figure regions from the PDF so masks, page placement, and composite figures were preserved

Open:
- None

### 2026-06-30 — Check Python and PyMuPDF access

Task: Confirm whether Python and the PyMuPDF library are available from this workspace.

Actions:
- Ran `python --version` and confirmed Python 3.14.6 is available
- Imported `fitz` and confirmed PyMuPDF 1.28.0 is available

Decisions:
- No project content was changed beyond this log entry

Open:
- None
