#maintenance
## Log

### 2026-07-03 — Remove duplicate va10 source

- Task: delete the duplicate `va10` source and retarget any surviving wiki references to `vj2`.
- Actions:
  - Deleted `PDFs/va10_raw.pdf`, `sources/va10.md`, and `wiki/summaries/va10-summary.md`.
  - Switched the surviving design and parameter pages created from the duplicate ingest to use `[[vj2]]`, `sources/vj2.md`, and existing `images/vj2-*` figures.
  - Removed duplicate source backlinks and source citations from concept and method pages, replacing them with `vj2` where the content was the same.
  - Removed the temporary `va10-summary` index entry and marked `sources/vj2.md` as processed.
- Decisions:
  - Kept the generic design and parameter pages because they remain useful and are not source-name-specific; only their canonical source was changed.
  - Left historical log entries intact even though they mention `va10`, because they record work that actually happened.
- Open:
  - None.

### 2026-07-03 — Ingest va10 hybrid CFD source

- Task: ingest `sources/va10.md` according to `schema/Ingest Source`.
- Actions:
  - Added `wiki/summaries/va10-summary.md` with source-grounded findings and figure links.
  - Added `wiki/designs/Savonius-Darrieus Hybrid Wind Turbine.md` as a single-source design page for the hybrid rotor studied in `va10`.
  - Added `wiki/parameters/Savonius Shaft Removal.md` and `wiki/parameters/Savonius Placement Outside Darrieus Rotor.md` for the two torque-improving geometry changes studied in the paper.
  - Updated `Hybrid VAWT`, `Savonius Turbine`, `Darrieus Turbine`, `CFD and Validation`, `CFD`, `Optimization`, and `Structures and Loads` with `va10` claims.
  - Updated `wiki/index.md` and marked `sources/va10.md` as processed.
- Decisions:
  - Ingested `va10` as an additional corroborating source for the same hybrid-CFD case already present as `vj2`, while still creating the required `va10` summary and single-source pages.
  - Kept the source-specific design page separate from the existing generic `Helical Hybrid` page because `schema/Ingest Source` requires single-source design pages when a source discusses a specific turbine design.
- Open:
  - `va10` and `vj2` appear to be duplicate copies of the same paper with different provenance and slightly different conversion details; the wiki currently keeps both as separate sources.

### 2026-07-03 — Convert va10 PDF source

- Task: convert `PDFs/va10_raw.pdf` into Markdown according to `schema/Convert PDF to MD`.
- Actions:
  - Created `sources/va10.md` with source front matter, full converted text, preserved section structure, figure captions, tables, acknowledgement, note, and references.
  - Extracted 8 figure images to `images/va10-fig1.jpg` through `images/va10-fig8.jpg`.
  - Converted Tables 1 and 2 to Markdown tables.
- Decisions:
  - Used `va10.md` because the PDF is a VAWT source and follows Anna's existing VAWT source numbering.
  - Used rendered visible figure regions for the paper figures because the page-layout figures are composite and crop more reliably than embedded object extraction.
- Open:
  - None.

### 2026-07-03 — Reconvert va6 source from PDF

- Task: replace the summarized `sources/va6.md` with a source-faithful conversion of `PDFs/va6_raw.pdf` according to `schema/Convert PDF to MD`.
- Actions:
  - Rebuilt `sources/va6.md` from the PDF text instead of keeping the prior summary-style content.
  - Preserved the article info, abstract, keywords, section headings, appendix, references, and biographies of authors.
  - Linked the paper figures in source order using the existing extracted `va6-fig*.jpg` files and added `images/va6-eq1-5.jpg` for the displayed equations in section 2.3.
  - Converted Tables 1, 2, and 3 to Markdown tables.
- Decisions:
  - Kept the source file name `va6.md` so it continues to match the existing Anna VAWT source numbering.
  - Used the existing split images for Figure 1(a) and Figure 1(b) rather than creating a new combined crop.
- Open:
  - None.

### 2026-07-03 — Reconvert va5 source from PDF

- Task: replace the summarized `sources/va5.md` with a source-faithful conversion of `PDFs/va5_raw.pdf` according to `schema/Convert PDF to MD`.
- Actions:
  - Rebuilt `sources/va5.md` from the PDF text instead of keeping the prior summary-style content.
  - Preserved the paper title, authors, abstract, nomenclature, section headings, references, and in-place figure/table captions.
  - Reused the existing extracted figure images for `va5` and added three equation crops as `images/va5-eq1.jpg`, `images/va5-eq2.jpg`, and `images/va5-eq3.jpg`.
  - Converted Tables 2 and 3 to Markdown tables and kept Table 1 as an image because the scanned table content was not reliable enough for exact text reconstruction.
- Decisions:
  - Kept the source file name `va5.md` so it continues to match the existing Anna VAWT source numbering.
  - Treated replacing the file contents as the deletion of the old summarized source, since the summary no longer exists at that path.
- Open:
  - Table 1 remains image-only unless a higher-quality OCR/transcription pass is needed later.

### 2026-07-02 — Rename raw PDFs to remove source-link ambiguity

- Task: rename all files in `PDFs/` to `*_raw.pdf` so bare source wikilinks like `[[va9]]` resolve cleanly to the Markdown source notes in Obsidian.
- Actions:
  - Renamed every current file in `PDFs/` from `name.pdf` to `name_raw.pdf`.
  - Updated live filename references in repo text, including `sources/va4.md` and matching `wiki/log.md` entries for `va4`, `va8`, `va9`, `vj1`, and `vj12`.
  - Corrected one verification-time edge case so `va1_raw_raw.pdf` now correctly reads `va1_raw.pdf`.
  - Removed the current basename collision between `sources/*.md` and the raw PDF filenames in `PDFs/`.
- Decisions:
  - Kept the Markdown source-note names unchanged so the wiki can continue using bare wikilinks like `[[va9]]`.
  - Used `_raw.pdf` only for the original-file layer in `PDFs/`.
- Open:
  - None.

### 2026-07-02 — Audit concept and method page links

- Task: make sure all links on `wiki/concepts/` and `wiki/methods/` pages work in Obsidian.
- Actions:
  - Audited all Obsidian wikilinks, Markdown note links, and Markdown image links on concept and method pages.
  - Verified no broken wikilink targets remain on those pages.
  - Verified no broken Markdown file links or image links remain on those pages.
- Decisions:
  - Left source backlinks such as `[[va9]]` unchanged because that is the requested bare wikilink format and it matches the current schema examples.
  - Confirmed the links themselves were not broken; the only issue was a basename collision that was later removed by renaming the raw PDFs to `*_raw.pdf`.
- Open:
  - None.

### 2026-07-02 — Fix remaining wiki backlink formatting

- Task: fix remaining wiki pages that still lacked Obsidian-friendly wikilink backlinks.
- Actions:
  - Added missing summary-page frontmatter backlinks so older source summaries now include `Sources: [[...]]` metadata.
  - Converted remaining wiki-to-wiki Markdown links in `wiki/index.md` and `wiki/learning-log.md` to Obsidian wikilinks.
  - Left single-source `Source: [[...]]` properties, claim citations like `sources/va9.md`, and non-wiki Markdown links unchanged because those already match the schema or serve a different purpose.
- Decisions:
  - Followed `schema/Ingest Source`, which uses inline `Sources: [[va1]]` for general wiki pages and singular `Source: [[va1]]` for single-source design and parameter pages.
  - Added minimal frontmatter to older summary pages rather than rewriting their body text, since the missing source backlinks were the navigation issue.
- Open:
  - None.

### 2026-07-02 — Add va3 design and parameter pages

- Task: revisit `sources/va3.md` under the updated ingest procedure and create design/parameter pages as appropriate.
- Actions:
  - Added single-source design pages for `Ropatec WRE.060 WindRotor`, `Solwind Vertical Axis Wind Turbine`, `Eurowind VAWT`, `Venturi Wind Turbine`, `Turby Wind Turbine`, `Windside Helical Wind Turbine`, `QuietRevolution QR5`, `Aerogenerator Offshore VAWT`, `Windspire Gyromill`, and `Counter-rotating VAWT Array`.
  - Added single-source parameter pages for `Tip Speed Ratio Classification`, `Blade Count for VAWT Startup and Pulsation`, and `Counter-rotating Array Spacing`.
  - Updated `wiki/index.md`, `va3-summary`, and related VAWT/Darrieus/Savonius/Helical pages with links to the new pages.
  - Added current summary front matter to `wiki/summaries/va3-summary.md`.
  - Verified bare backlinks and image links for the new design/parameter layer.
- Decisions:
  - Created pages only for `va3` designs with enough source detail to describe geometry, design choices, and/or performance.
  - Left unavailable metadata fields blank rather than inferring values.
  - Marked the Venturi 85% efficiency statement as a source claim that should be checked before being used as a design rule because it exceeds the Betz limit framing elsewhere in the same source.
- Open:
  - Some `va3` design pages may need later consolidation if the wiki decides to separate commercial product pages from generic VAWT type pages.

### 2026-07-02 — Add va9 design and parameter pages

- Task: revisit `va9` after the ingest procedure was updated to require design and parameter pages.
- Actions:
  - Added `wiki/designs/EN0005 Self-start Darrieus VAWT.md` as a single-source design page for the prototype described in `sources/va9.md`.
  - Added `wiki/parameters/EN0005 Blade Profile.md` as a single-source parameter page for the EN0005 profile change and self-start outcome.
  - Added `Designs` and `Parameters` sections to `wiki/index.md` and linked the new pages.
  - Updated related links from `va9-summary`, `Darrieus Turbine`, and `Aerodynamic Design Parameters`.
  - Corrected `Sources` metadata on existing pages that cite `sources/va9.md` so they include `[[va9]]`.
- Decisions:
  - Used the reported field-test self-start at 1.25 m/s as the design page cut-in/self-start value, while leaving rated speed, rated power, efficiency, TSR, and swept area blank because the source does not provide those as explicit design metadata.
  - Classified the EN0005 blade-profile outcome as a significant positive effect because the source reports improved self-start behavior, favorable lift/drag/moment comparisons, and successful prototype self-start.
- Open:
  - The EN0005 results remain source-specific and should not be generalized without corroborating sources.

### 2026-07-02 — Normalize wiki backlinks

- Task: make wiki backlinks functional using bare file-name syntax such as `[[va1]]`.
- Actions:
  - Normalized path-style wikilinks across `wiki/`, including metadata `Sources`, from `sources/va1.md`, `../../sources/va9`, and `concepts/Darrieus Turbine` forms to bare file-name links.
  - Fixed broken `Lift vs Drag` links to point to `Lift vs Drag VAWT – Research Question`.
  - Verified no path-style or `.md` wikilinks remain in `wiki/`.
  - Verified all wiki wikilink targets resolve to existing Markdown file basenames with no duplicate basename targets.
- Decisions:
  - Left standard Markdown links and image links unchanged because those use path syntax intentionally.
- Open:
  - None.

### 2026-07-02 — Ingest va9 self-start Darrieus source

- Task: ingest `sources/va9.md` according to `schema/Ingest Source`.
- Actions:
  - Created `wiki/summaries/va9-summary.md` with source-grounded key points and selected figure links.
  - Added `wiki/methods/Double-Multiple Streamtube Model.md` for the DMS method and the sliced DMS extension from `va9`.
  - Updated `Darrieus Turbine`, `Straight-bladed Darrieus`, `H-VAWT`, `Aerodynamic Design Parameters`, `VAWT`, `Urban Wind Conditions`, `Materials and Manufacturing`, `CFD and Validation`, `Blade Element-Momentum Model`, and `Wind Tunnel Testing` with `va9` claims.
  - Added `va9-summary` and `Double-Multiple Streamtube Model` to `wiki/index.md` and marked `sources/va9.md` as processed.
- Decisions:
  - Created a new DMS method page because no existing streamtube-specific method page covered the single/multiple/double-multiple streamtube comparison or the sliced DMS extension.
  - Treated the reported 1.25 m/s self-start and 25 m/s stability results as source-specific field-test outcomes, not universal Darrieus design rules.
- Open:
  - The EN0005 profile and field-test outcomes should be compared with independent studies before being generalized to other rotor scales or urban sites.

### 2026-07-02 — Convert va9 PDF source

- Task: convert `PDFs/va9_raw.pdf` into Markdown according to `schema/Convert PDF to MD`.
- Actions:
  - Created `sources/va9.md` with source front matter, full converted text, preserved section structure, references, figure captions, and converted Markdown tables.
  - Extracted 29 figure images to `images/va9-fig*.jpg`.
  - Rendered 8 grouped equation images covering equations (1) through (41) to `images/va9-eq*.jpg`.
  - Verified all 37 Markdown image links in `sources/va9.md` resolve from the source file location.
- Decisions:
  - Used `va9.md` because the PDF is a VAWT source and follows Anna's existing VAWT source numbering.
  - Used grouped equation images where the paper had dense equation blocks, because reconstructing the equations from PDF text would be less reliable than rendering the source equations.
- Open:
  - Source has not yet been ingested into wiki concept pages.

### 2026-07-02 — Ingest va8 patent source

- Task: ingest `sources/va8.md` according to `schema/Ingest Source`.
- Actions:
  - Created `wiki/summaries/va8-summary.md` with source-supported key points and figure links.
  - Updated `Hybrid VAWT`, `Aerodynamic Design Parameters`, `Structures and Loads`, `Materials and Manufacturing`, `Urban Wind Conditions`, `Darrieus Turbine`, `Savonius Turbine`, `VAWT`, `VAWT Types`, and `Wind Tunnel Testing` with `va8` claims.
  - Added `va8-summary` to `wiki/index.md` and marked `sources/va8.md` as processed.
- Decisions:
  - Treated the patent as a useful design concept source, but flagged its performance comparisons as single-source patent claims rather than broadly validated trends.
  - Updated existing pages instead of creating a new concept page because the source fits under the current hybrid VAWT, aerodynamic design, structure, and wind-tunnel pages.
- Open:
  - The patent's claimed 2.5x circumferential-force improvement and 54% lighter blade profile should be checked against independent aerodynamic or experimental sources before being used as design rules.

### 2026-07-02 — Convert va8 PDF source

- Task: convert `PDFs/va8_raw.pdf` into Markdown according to `schema/Convert PDF to MD`.
- Actions:
  - Read the PDF conversion, figure extraction, and repo organization procedures.
  - Created `sources/va8.md` with source front matter, patent metadata, full converted text, preserved headings, claims, figure captions, and `Processed: false`.
  - Extracted 13 figure images to `images/va8-fig*.jpg` and one displayed-equation image to `images/va8-eq1.jpg`.
  - Verified all 14 Markdown image links in `sources/va8.md` resolve from the source file location.
- Decisions:
  - Used `va8.md` because the PDF is a VAWT source and follows the existing Anna source numbering.
  - Used the clean patent drawing sheets for figures instead of the title-page duplicate image.
- Open:
  - Source has not yet been ingested into wiki concept pages.

### 2026-07-02 — Add vj11 findings to concept pages

- Task: add the new `vj11` review findings to the relevant wiki concept pages.
- Actions:
  - Expanded `VAWT`, `Darrieus Turbine`, `Savonius Turbine`, `Hybrid VAWT`, `Helical VAWT`, `CFD and Validation`, `Urban Wind Conditions`, `Scaling Effects`, `Optimization`, `Wind Turbine Parameters`, `Dynamic Stall`, `Atmospheric Turbulence`, and `Aerodynamic Design Parameters` with new source-grounded bullets from `sources/vj11.md`.
  - Added a few cross-links so the new review findings are reachable from the main concept hubs.
- Decisions:
  - Kept the additions targeted to the specific design ranges, CFD guidance, and performance tradeoffs that `vj11` contributes.
  - Left the existing earlier-source material in place and layered the new review points on top.
- Open:
  - None.

### 2026-07-02 — Add vj11 summary page

- Task: create the summary page for `sources/vj11.md`.
- Actions:
  - Added `wiki/summaries/vj11-summary.md` with a source-grounded overview, key findings, figures, and related links.
  - Updated `wiki/index.md` to include the new summary page.
- Decisions:
  - Kept the summary concise and tied every claim to `sources/vj11.md`.
  - Included the five extracted figures so the summary page mirrors the paper structure.
- Open:
  - None.

### 2026-07-02 — Fix vj11 Table 1 formatting

- Task: repair the malformed table in section 2.3 of `sources/vj11.md`.
- Actions:
  - Replaced the collapsed Table 1 text block with a proper Markdown table.
  - Verified the table now renders with distinct parameter and configuration columns.
- Decisions:
  - Kept the surrounding prose unchanged because the issue was isolated to the table block.
- Open:
  - None.

### 2026-07-01 — Add geometry/performance/tradeoffs to VAWT type pages

- Task: make the VAWT type pages more useful for design by adding geometry, performance, and tradeoff information.
- Actions:
  - Expanded `Classical Savonius`, `Helical Savonius`, `Eggbeater Darrieus`, `Straight-bladed Darrieus`, `Troposkien Darrieus`, `Helical Darrieus`, `Outer Darrieus with Inner Savonius`, `Helical Hybrid`, `Darrieus above Savonius`, `Multi-stage Savonius within H-rotor Darrieus`, `Double Darrieus with Inner H-rotor and Outer Eggbeater`, and `Contra-rotating VAWT` with geometry/performance/tradeoff sections.
  - Added the same structure to the parent pages `Savonius Turbine`, `Darrieus Turbine`, `Hybrid VAWT`, `Helical VAWT`, `J-Type VAWT`, and `H-VAWT`.
- Decisions:
  - Kept the information source-grounded and marked any unsupported detail as inference.
  - Preserved the existing hub pages while making the leaf pages more design-oriented.
- Open:
  - None.

### 2026-07-01 — Add VAWT variant concept pages

- Task: create a concept page for each VAWT type represented in the hub.
- Actions:
  - Added pages for `Classical Savonius`, `Helical Savonius`, `Eggbeater Darrieus`, `Straight-bladed Darrieus`, `Troposkien Darrieus`, `Helical Darrieus`, `Outer Darrieus with Inner Savonius`, `Helical Hybrid`, `Darrieus above Savonius`, `Multi-stage Savonius within H-rotor Darrieus`, `Double Darrieus with Inner H-rotor and Outer Eggbeater`, and `Contra-rotating VAWT`.
  - Updated `VAWT Types`, `Savonius Turbine`, `Darrieus Turbine`, `Hybrid VAWT`, `Helical VAWT`, `H-VAWT`, and `wiki/index.md` to link the new pages.
- Decisions:
  - Used short, source-grounded pages for each variant rather than repeating the full report text.
  - Kept `H-VAWT`, `Helical VAWT`, and `Hybrid VAWT` as parent pages while adding the more specific variant pages beneath them.
- Open:
  - None.

### 2026-07-01 — Expand VAWT types hub from HRI2526

- Task: add the VAWT families and variants named in `sources/HRI2526.md` into `wiki/concepts/VAWT Types.md`.
- Actions:
  - Expanded the hub to include classical, helical, straight-bladed, troposkien, and eggbeater Darrieus variants.
  - Added the hybrid configurations named in the report, including helical hybrid, outer Darrieus with inner Savonius, Darrieus above Savonius, multi-stage Savonius within H-rotor Darrieus, and double Darrieus with inner H-rotor and outer eggbeater.
- Decisions:
  - Kept the structure grouped by drag-based, lift-based, and hybrid/combined families.
  - Left contra-rotating as an inference because the wiki does not yet have a dedicated concept page for it.
- Open:
  - None.

### 2026-07-01 — Add VAWT types hub

- Task: create a hub-style concept page for VAWT families grouped by broader categories.
- Actions:
  - Added `wiki/concepts/VAWT Types.md` with drag-based, lift-based, and hybrid/combined sections.
  - Linked the page from `wiki/index.md` and `concepts/VAWT.md`.
- Decisions:
  - Kept the page limited to families currently represented in the wiki and marked contra-rotating as an inference where no separate concept page exists yet.
- Open:
  - None.

### 2026-07-01 — Add VAWT design hub pages

- Task: reorganize the concepts area around VAWT design, especially the rules-of-thumb idea.
- Actions:
  - Added new concept hub pages for `VAWT Design Overview`, `VAWT Design Comparisons`, `Turbine Concept Selection`, `Aerodynamic Design Parameters`, `Structures and Loads`, `Materials and Manufacturing`, `CFD and Validation`, `Optimization`, `Design Checklist`, and `Rules of Thumb`.
  - Updated `wiki/index.md` so the new pages are visible from the main concepts list.
  - Added links from `concepts/VAWT.md` to the new design pages.
- Decisions:
  - Kept the new pages as source-grounded hubs that point to the existing detailed pages instead of duplicating the underlying paper content.
  - Made `Rules of Thumb` a dedicated page because it is the most useful quick-reference layer for a design workflow.
- Open:
  - None.

### 2026-07-01 — Fill source publication dates

- Task: populate `Published` in `sources/vj1.md` through `sources/vj7.md` with the best supported date information.
- Actions:
  - Set `vj1` to `2007` from the Elsevier copyright/front-matter year.
  - Set `vj2` to `2020` from the paper's own 2020 symposium reference in the source text.
  - Set `vj3` to `2012-09` from the visible source line `North American Windpower, September 2012`.
  - Set `vj4` to `2016-05` from Crossref metadata for the paper.
  - Set `vj5` to `2009-05` from Crossref metadata for the paper.
  - Left `vj7` blank because no exact Crossref/DOI match or source year could be confirmed.
- Decisions:
  - Used partial dates when only month/year were supported.
  - Avoided inventing a year for `vj7`.
- Open:
  - None.

### 2026-07-01 — Add vj8 properties block

- Task: add schema frontmatter to `sources/vj8.md` and confirm `sources/vj9.md` status.
- Actions:
  - Added `Title`, `Author`, `Published`, `Created`, `Processed`, and `tags` frontmatter to `sources/vj8.md`.
  - Verified `sources/vj9.md` already had a complete properties block and left it unchanged.
- Decisions:
  - Used `Published: 2023-12-30` for `vj8` because the source explicitly says “Available online 30 December 2023.”
  - Left `Created` blank because the source did not provide a creation date.
- Open:
  - None.

### 2026-07-01 — Clean vj8 abstract header

- Task: remove the stray journal header/footer spill from the start of `sources/vj8.md` and label the abstract.
- Actions:
  - Replaced the `A B S T R A C T` marker with `## Abstract`.
  - Removed the `E-mail address` / ScienceDirect / journal footer lines that had spilled into the introduction block.
- Decisions:
  - Kept the rest of the source unchanged because the issue was limited to the top-of-file spill.
- Open:
  - None.

### 2026-07-01 — Rebuild vj8

- Task: check `vj8` for summarization, missing text, and image quality.
- Actions:
  - Rebuilt `sources/vj8.md` from the PDF text layer instead of the prior summary.
  - Re-extracted the `vj8-fig*.jpg` figures from embedded PDF images.
  - Fixed one duplicate figure-caption insertion near Fig. 18.
- Decisions:
  - Treated the existing `vj8.md` as summary/OCR drift and replaced it with a raw transcript-style source.
- Open:
  - None.

### 2026-07-01 — Rebuild vj7

- Task: check `vj7` for summarization, missing text, and figure quality.
- Actions:
  - Rewrote `sources/vj7.md` from the PDF text layer instead of the prior summary.
  - Replaced `vj7-fig1.jpg`, `vj7-fig2.jpg`, and `vj7-fig3.jpg` with embedded PDF image extractions.
  - Kept the source anchored to the PDF sections and references.
- Decisions:
  - Treated the old `vj7.md` as a summary that needed a full source rebuild.
- Open:
  - None.

### 2026-07-01 — Fix vj6 Table 1

- Task: repair the broken Table 1 block in `sources/vj6.md`.
- Actions:
  - Replaced the flattened OCR table with a clean Markdown table.
  - Kept the wording aligned with the PDF’s Table 1 content for sliding, overset, and morphing mesh.
- Decisions:
  - Left the rest of the document unchanged in this pass.
- Open:
  - Broader paragraph cleanup is still separate from this table fix.

### 2026-07-01 — vj6 follow-up cleanup

- Task: address the reviewer notes on `sources/vj6.md`.
- Actions:
  - Regenerated all `vj6-fig*.jpg` files as tight PDF crops.
  - Replaced displayed equations 1 through 11 with cropped equation images.
  - Verified the source still references the figure assets and the new equation images.
- Decisions:
  - Kept the source text otherwise unchanged after a failed broad reflow attempt, because the safe text cleanup path needs a narrower pass.
- Open:
  - Paragraph reflow remains to be decided: conservative spot fixes vs. a full verbatim reflow pass.

### 2026-07-01 — Finish vj6 rebuild

- Task: replace the paraphrased `sources/vj6.md` with the rebuilt PDF-derived draft.
- Actions:
  - Copied the verified `vj6-rebuild.md` draft into `sources/vj6.md`.
  - Confirmed the source hash matches the draft hash exactly.
  - Verified all 21 `vj6-fig*.jpg` assets exist and are linked from the source.
- Decisions:
  - Kept the draft as-is because it was a full rebuild with the references section intact and no content drift from the temp draft.
- Open:
  - None.

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

### 2026-07-02 — Normalize source metadata

Task: Add convention-style frontmatter metadata to all `sources/*.md` pages.

Actions:
- Added frontmatter to the five source pages that were still missing it: `HRI2526.md`, `n1.md`, `n2.md`, `va5.md`, and `va6.md`
- Kept the existing source frontmatter on the already-tagged pages unchanged
- Verified that all 23 source markdown files now start with frontmatter

Decisions:
- Used best-effort titles and author fields where the source note clearly provided them
- Left `Published` blank where the source did not provide a clear publication date

Open:
- None

### 2026-07-02 — Normalize concept and method metadata

Task: Add convention-style frontmatter metadata to the concept and methods wiki pages.

Actions:
- Added frontmatter to concept pages that were missing it
- Added frontmatter to methods pages that were missing it
- Populated each new frontmatter block with `Updated: 2026-07-02`, the page's cited source backlinks, source count, and folder tag
- Left the one preexisting metadata page (`concepts/Wind Shear.md`) untouched because it already matched the convention

Decisions:
- Kept the existing page bodies and links intact
- Used blank `Created:` values where the original creation date was unavailable

Open:
- None

### 2026-07-02 — Add vj12 concepts and methods notes

Task: Fold the new `vj12` review into the existing concept and method pages.

Actions:
- Updated `concepts/Contra-rotating VAWT.md` with the stacked-rotor layout, opposite-rotation requirement, and spacing result
- Updated `concepts/Savonius Turbine.md` with overlap, inner-blade, blade-count, and endplate notes from the review
- Updated `concepts/Helical Savonius.md` with twist-angle performance notes
- Updated `concepts/Optimization.md` with the review's active/passive optimization split and representative gains
- Updated `concepts/Urban Wind Conditions.md` with siting, obstacle-clearance, and wind-farm layout notes
- Updated `concepts/Wind Turbine Parameters.md` with the review's main geometry/performance knobs
- Updated `methods/CFD.md` with the review's CFD usage and URANS/k-omega note

Decisions:
- Kept the edits limited to pages that already covered the same concepts or methods
- Added representative figure links where they reinforced the new notes

Open:
- None

### 2026-07-02 — Ingest vj12 review

Task: Ingest `PDFs/vj12_raw.pdf` and add its source summary to the wiki.

Actions:
- Converted `vj12_raw.pdf` into `sources/vj12.md` with frontmatter, extracted text, and figure links
- Extracted and named 28 figure files in `images/vj12-fig*.jpg`
- Added `wiki/summaries/vj12-summary.md` with source-grounded bullets and representative figure links
- Updated `wiki/index.md` to include `vj12-summary`

Decisions:
- Kept the ingest focused on the new source summary rather than creating new concept pages, since the paper mainly synthesizes existing VAWT topics
- Used a representative crop for the final multi-panel wind-farm figure because the PDF splits that figure across the closing pages

Open:
- The source conversion still contains some OCR clutter from the PDF text extraction, but the structure and figure links are in place

### 2026-07-02 — Repair vj12 figure set

Task: Fix the broken `vj12` image set after the initial ingest.

Actions:
- Rebuilt the `vj12` figure crops from `PDFs/vj12_raw.pdf` into the repo `images/` folder
- Restored the full 28-file figure set after an earlier rename pass had clobbered most of the generated files
- Corrected `vj12-fig1.jpg` so it now matches the Figure 1 image used by the source markdown

Decisions:
- Kept the existing source and summary links, since the image filenames now match them again

Open:
- None

### 2026-06-30 — VAWT types learning quiz

Task: Quiz Anna on different types of VAWTs and their pros and cons.

Actions:
- Started with broad mechanism categories: Darrieus, Savonius, and hybrid VAWTs.
- Asked Anna to identify how each type works, one advantage, and one downside.
- Followed with straight-bladed H-type versus helical VAWTs to test understanding of torque ripple, cyclic loading, and the smoothness/performance tradeoff.
- Asked a site-selection question for low-speed, turbulent, changing-direction urban wind to make Anna apply the design tradeoffs rather than recite definitions.
- Introduced `vj9` Savonius variants only after the foundational questions: classical Savonius, modified Bach-type Savonius, and scooplet-based Savonius.
- Shifted from quiz mode to explanation when Anna said she had not read `vj9`, then pointed her to the relevant figure numbers: Fig. 1, Fig. 11b, and Fig. 16b.

Decisions:
- Used one-question-at-a-time teaching mode because it forced retrieval and reasoning while avoiding the redundancy Anna previously disliked.
- Ordered questions from broad categories, to subtype tradeoffs, to design recommendation, to paper-specific variants because that moved from familiar concepts toward less familiar source-specific details.
- Treated Anna's uncertainty as useful signal: when she could reason from existing knowledge, I graded and tightened; when she lacked source exposure, I stopped quizzing and explained.

Open:
- Anna found the session helpful. Future VAWT quizzes should keep this pattern: ask applied comparison questions, grade directly, correct only the weakest claim, and switch to explanation when the missing piece is source exposure rather than reasoning.

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

### 2026-07-01 — Clean vj1 source header

Task: Remove PDF header boilerplate from `sources/vj1.md`.

Actions:
- Removed the stray source marker, journal header line, and Elsevier URL from the top of the file
- Kept the paper title, authors, and abstract intact

Decisions:
- Limited the cleanup to the obvious header noise at the top of the source markdown

Open:
- None

### 2026-07-01 — Clean vj1 page breaks

Task: Remove repeated page-header interruptions from `sources/vj1.md`.

Actions:
- Removed the repeated running journal header from the middle of paragraphs
- Removed standalone page numbers inserted at page breaks
- Cleaned the references section where the header text had been injected inline

Decisions:
- Kept the paper text, figure captions, and references intact
- Treated this as formatting cleanup only, not content rewriting

Open:
- None

### 2026-07-01 — Add vj1 figures

Task: Restore the extracted figures for `sources/vj1.md`.

Actions:
- Extracted two figure images from `PDFs/vj1_raw.pdf` into `images/vj1-fig1.jpg` and `images/vj1-fig2.jpg`
- Added Markdown image links for both figures at their caption locations in `sources/vj1.md`
- Verified both image files exist and the source links resolve relative to `sources/`

Decisions:
- Used rendered figure regions instead of partial embedded assets so the composite first figure stayed intact

Open:
- None

### 2026-07-01 — Clean vj1 placeholder blocks

Task: Remove leftover OCR picture placeholder blocks from `sources/vj1.md`.

Actions:
- Removed the omitted picture markers around the equation sections
- Removed the embedded graph-text placeholder block near Fig. 2
- Kept the surrounding prose, table, and figure links intact

Decisions:
- Treated the placeholders as OCR artifacts, not source content

Open:
- None

### 2026-07-01 — Fix vj1 figure crops

Task: Correct the figure images linked from `sources/vj1.md`.

Actions:
- Replaced `images/vj1-fig1.jpg` with a crop from the actual figure on PDF page 3
- Replaced `images/vj1-fig2.jpg` with a render of the actual chart on PDF page 9
- Kept the existing figure links in `sources/vj1.md`

Decisions:
- Used the visible figure regions from the PDF rather than the journal masthead crop and OCR placeholder text

Open:
- None

### 2026-07-01 — Check vj2 figures

Task: Verify `sources/vj2.md` for the same figure issues seen in `vj1`.

Actions:
- Checked the extracted figure files for `vj2` and confirmed the expected image set is present
- Compared the source figure links against the PDF figure order and found them aligned
- Removed the stale note claiming the figure images were missing from `images/`

Decisions:
- Left the existing `vj2` figure crops and links in place because they match the PDF layout

Open:
- None

### 2026-07-01 — Check vj4 figures

Task: Verify `sources/vj4.md` for figure-link and crop issues.

Actions:
- Read the figure sections in `sources/vj4.md`
- Visually checked the extracted `vj4-fig*.jpg` images against their captions
- Confirmed the figure sequence and filenames are aligned

Decisions:
- No edits were needed; the source links and extracted images match the paper layout

Open:
- None

### 2026-07-01 — Re-export vj4 figures

Task: Fix `vj4` figure crops to follow the extraction protocol.

Actions:
- Re-exported `vj4-fig2.jpg` through `vj4-fig12.jpg` from the PDF's actual figure bounding boxes
- Removed caption bleed and surrounding page text from the figure images
- Kept `vj4-fig1.jpg` and the source links unchanged

Decisions:
- Used the visible figure regions from the PDF as the source of truth for composite/vector figures

Open:
- None

### 2026-07-01 — Fix vj5 figures

Task: Re-export the `vj5` figures using the extraction protocol.

Actions:
- Replaced embedded-image figures with direct xref extractions for the clean figure assets
- Re-rendered the vector-only force-history figures so they exclude captions and surrounding text
- Verified all 22 `vj5-fig*.jpg` files exist and remain linked from `sources/vj5.md`

Decisions:
- Followed the protocol's preference for embedded image extraction first, then page rendering for vector-only plots

Open:
- None

### 2026-07-01 — Restore vj5 source text

Task: Remove summary-style rewrites from `sources/vj5.md` and restore the paper wording.

Actions:
- Replaced the abstract and section lead-ins with the paper's original language
- Restored the model, flow-condition, validation, and grid-sensitivity sections from the PDF text
- Fixed a few clipped OCR/transcription fragments that remained after the rewrite

Decisions:
- Kept the figure links and cleaned figure assets in place
- Left minor OCR quirks that are transcription artifacts rather than summaries

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

### 2026-07-02 — Reformat va3 source Markdown

Task: Fix `sources/va3.md` formatting after PDF conversion.

Actions:
- Removed page-section markers and the separate figure gallery.
- Promoted original PDF section headings, including `INTRODUCTION` and `DISCUSSION`, into Markdown headers.
- Moved all `va3-fig*.jpg` image links directly above their matching figure captions.
- Separated several captions from following body text where the conversion had merged them.
- Verified 39 figure captions, 48 linked `va3-fig*.jpg` image files, no broken relative paths, and no remaining page/gallery markers.

Decisions:
- Kept existing extracted figure files and file names because they already matched the source figure sequence.
- Treated the edit as formatting cleanup only and did not summarize or paraphrase source content.

Open:
- Some equations and technical tables in `sources/va3.md` remain rough from the original PDF text extraction.

### 2026-07-02 — Add va3 source metadata

Task: Add conversion-schema metadata to `sources/va3.md`.

Actions:
- Added YAML frontmatter with `Title`, `Author`, `Published`, `Created`, `Processed`, and `tags` fields following `schema/Convert PDF to MD`.
- Used the visible source date `3/21/2015` as `Published: 2015-03-21`.

Decisions:
- Set `Author` to `M. Ragheb` from the source header.
- Set `Processed: false` to match the conversion-schema template.

Open:
- None.

### 2026-07-02 — Retag parameters page

Task: Update the `wiki/parameters` page metadata so the page uses the `Parameters` tag.

Actions:
- Changed the `Tags` frontmatter on `wiki/parameters/Aerodynamic Design Parameters.md` from `concepts` to `Parameters`.

Decisions:
- Kept the change limited to the parameters folder page the user referenced.

Open:
- None.

### 2026-07-02 — Retag design pages

Task: Update the `wiki/designs` page metadata so design pages use the `Designs` tag like concept pages use `concepts`.

Actions:
- Changed the `Tags` frontmatter on all pages in `wiki/designs/` from `concepts` to `Designs`.

Decisions:
- Kept the rest of each page unchanged to avoid any content drift.

Open:
- None.

### 2026-07-02 — Clean va7 headings and page breaks

Task: Reformat `sources/va7.md` so paper sections are Markdown headings and page breaks are excluded.

Actions:
- Removed `<!-- Page N -->` page-break markers.
- Removed obvious page/footer artifacts from the first page break area, including the MDPI DOI/URL footer lines.
- Converted `Abstract`, `Keywords`, numbered sections, numbered subsections, author contribution/funding/acknowledgment/conflict sections, and `References` into Markdown headings.

Decisions:
- Kept the source text otherwise unchanged and did not summarize or paraphrase content.

Open:
- None.

### 2026-07-02 — Rebuild va4 source from PDF

Task: Replace the summarized `sources/va4.md` with a source-faithful PDF conversion.

Actions:
- Rebuilt `sources/va4.md` from `PDFs/va4_raw.pdf` using the PDF text layer instead of the prior summary-style source.
- Added conversion-schema frontmatter with title, authors, publication date, created date, processed status, and source tag.
- Preserved the paper structure: title, authors, abstract, keywords, numbered sections/subsections, tables, acknowledgments, author contributions, conflict statement, nomenclature, and references.
- Converted Tables 1 through 3 into Markdown tables.
- Removed page headers, page numbers, journal footers, summary bullets, and the artificial `Additional Extracted Crops` section.
- Added equation images `images/va4-eq1.jpg` through `images/va4-eq10.jpg` and linked them at the equation locations.
- Kept and linked the 19 actual paper figures as `images/va4-fig1.jpg` through `images/va4-fig19.jpg` at their caption locations.
- Removed PDF text-layer artifacts extracted from inside figures, such as plot ticks, legend labels, and axis labels.

Decisions:
- Set `Processed: true` because `va4` has already been ingested into the wiki.
- Did not link the old `va4-fig20.jpg` through `va4-fig41.jpg` duplicate crops in the source because they are not distinct original paper figures and the prior section was not source text.

Open:
- A few inline mathematical expressions remain as text where they are embedded in prose rather than displayed numbered equations.

### 2026-07-02 — Add va1 and va2 source metadata

Task: Add conversion-schema metadata to `sources/va1.md` and `sources/va2.md`.

Actions:
- Added YAML frontmatter with `Title`, `Author`, `Published`, `Created`, `Processed`, and `tags` fields to both source files.
- Used `Published: 2011` for `va1` from the journal volume/date visible in the source/PDF.
- Used `Published: 2025-06-03` for `va2` from the PDF publication line.

Decisions:
- Set `Processed: true` for both because `wiki/summaries/va1-summary.md` and `wiki/summaries/va2-summary.md` already exist.

Open:
- None.

### 2026-07-02 — Mark va3 processed

Task: Update `sources/va3.md` metadata after confirming it has already been ingested.

Actions:
- Changed `Processed` from `false` to `true` in the source frontmatter.

Decisions:
- Used `true` because `va3` already has an existing summary page and has been ingested into the wiki.

Open:
- None.
