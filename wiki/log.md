#maintenance
## Log

### 2026-07-08 - Create five-week VAWT project plan note

- Task: create a five-week project plan for designing, modeling, testing, and reporting on a VAWT design.
- Actions:
  - Added `analysis/J_5_week_plan.md`.
  - Structured the note into weekly phases covering scope selection, first-pass geometry, modeling/analysis, prototyping/testing, and report writing.
  - Included a short list of deliverables, execution steps, and places where the agent can directly help.
- Decisions:
  - Kept the plan at the project-management level rather than filling it with detailed design targets, because the request was for a schedule rather than another technical recommendation note.
- Open:
  - The note assumes the user will have access to Zoo Keeper or another modeling tool plus some path to prototype or test a design within the five-week window.

### 2026-07-08 - Export focused 0-6 m/s wind-speed histogram

- Task: create a focused histogram of wind speeds from `wind data/all_wind_data.txt` for the `0-6 m/s` range.
- Actions:
  - Converted numeric `sknt` values to meters per second using `1 kt = 0.514444 m/s`.
  - Exported `wind data/all_wind_data_mps_histogram_0_to_6.svg` using `0.25 m/s` bins from `0` to `6 m/s`.
  - Used a percentage-based y-axis and verified the file was built from `4585` observations within the `0-6 m/s` range.
- Decisions:
  - Wrote this as a second focused histogram instead of overwriting the broader all-range histogram so both views remain available.
- Open:
  - If needed, the focused histogram could also be normalized against the full dataset rather than only the observations in the `0-6 m/s` range.

### 2026-07-08 - Export all_wind_data wind-speed histogram

- Task: create a histogram of wind speeds from `wind data/all_wind_data.txt`.
- Actions:
  - Converted numeric `sknt` values to meters per second using `1 kt = 0.514444 m/s`.
  - Exported a histogram as `wind data/all_wind_data_mps_histogram.svg`, then regenerated it with `0.5 m/s` bins from `0` to `18 m/s` and a percentage-based y-axis.
  - Verified the histogram file exists and that it was built from `6363` numeric wind-speed observations.
- Decisions:
  - Wrote the histogram as an `SVG` instead of a `PNG` because `matplotlib` was not available in the environment.
- Open:
  - If needed, the histogram could also be regenerated with different bin widths or for the Boston-only subset rather than the full `all_wind_data` file.

### 2026-07-08 - Convert and ingest vj28 small straight-bladed VAWT airfoil-guidance paper

- Task: convert `PDFs/vj28.pdf` into `sources/vj28.md`, extract its figures and displayed equations, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj28.md` with source frontmatter, cleaned section structure, linked figures `vj28-fig1` through `vj28-fig24`, and linked the two displayed equations as `vj28-eq1` and `vj28-eq2` images.
  - Added `wiki/summaries/vj28-summary.md`.
  - Added the concept page `wiki/concepts/Airfoil Selection for Small Straight-Bladed VAWTs.md`.
  - Added the method pages `wiki/methods/XFOIL.md` and `wiki/methods/NAFNoise.md`.
  - Added the source-specific parameter page `wiki/parameters/vj28 Blade Airfoil.md`.
  - Updated `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/H-VAWT.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Materials and Manufacturing.md`, `wiki/concepts/Rules of Thumb.md`, and `wiki/index.md` with `vj28`-supported claims and links.
  - Marked `sources/vj28.md` as processed.
- Decisions:
  - Did not create a design page because `vj28` is a guidance-and-screening paper about desirable airfoil features for small fixed-pitch SB-VAWTs, not a source with one fully specified turbine design and coherent whole-rotor performance dataset.
  - Created one source-specific parameter page for blade airfoil rather than splitting the paper into multiple small parameter notes, because the paper's main contribution is a coupled multi-criteria airfoil-selection framework.
  - Added `XFOIL` and `NAFNoise` method pages because both tools are used as named, reusable parts of the paper's analysis workflow.
- Open:
  - The `vj28` source conversion still reflects PDF block extraction, so some table formatting remains less clean than a hand-retyped transcription, especially for the dense rating-style tables.
  - The paper's airfoil comparison itself is partly based on `XFOIL` plus extrapolated post-stall data, so the ingest should be read as a source-backed design framework rather than proof of one universally best SB-VAWT airfoil.

### 2026-07-08 - Export all_wind_data m/s dataset as Markdown table

- Task: create a Markdown-table version of the `all_wind_data` dataset in meters per second.
- Actions:
  - Created `wind data/all_wind_data_mps.md`.
  - Exported the dataset as a Markdown table with columns `station`, `station_name`, `valid(UTC)`, `wind_speed_mps`, `drct`, `gust_drct`, and `gust_speed_mps`.
  - Preserved missing values as blank cells in the Markdown table.
  - Added the `#wind Data` tag at the top of the Markdown file for consistency with the existing wind-data Markdown export.
  - Verified the header row, separator row, and representative data rows in the output.
- Decisions:
  - Wrote the Markdown table next to the related text and JSON files in `wind data/` so the full set of exports stays grouped together.
- Open:
  - The table is large because it includes the full dataset; if needed, it could also be split by date range or summarized.

### 2026-07-08 - Convert all_wind_data speeds from knots to meters per second

- Task: create a meters-per-second JSON export for `wind data/all_wind_data.txt`.
- Actions:
  - Created `wind data/all_wind_data_mps.json` from the source text file.
  - Converted `sknt` to `wind_speed_mps` and `gust_sknt` to `gust_speed_mps` using `1 kt = 0.514444 m/s`, rounded to `6` decimal places.
  - Kept `drct` and `gust_drct` unchanged as direction values in degrees.
  - Preserved missing speed values as `null` and verified the file contains `6407` JSON objects with `44` null values in each converted speed field.
- Decisions:
  - Kept `wind data/all_wind_data.json` unchanged in knots and wrote a second file for the SI-unit version to preserve both unit systems.
- Open:
  - If needed, this dataset could also be exported as a Markdown table or with both knot and meter-per-second speed fields in the same rows.

### 2026-07-08 - Convert all_wind_data CSV text file to JSON

- Task: convert `wind data/all_wind_data.txt` into a JSON file for downstream use.
- Actions:
  - Read `wind data/all_wind_data.txt` and confirmed it is a comma-separated table with headers `station`, `station_name`, `valid(UTC)`, `sknt`, `drct`, `gust_drct`, and `gust_sknt`.
  - Created `wind data/all_wind_data.json` as a JSON array of row objects, preserving the original column names.
  - Normalized numeric values in `sknt`, `drct`, `gust_drct`, and `gust_sknt` to JSON numbers and converted `M` entries to `null`.
  - Verified the conversion by counting rows in both formats: `6407` CSV rows and `6407` JSON objects.
- Decisions:
  - Kept the derived JSON file next to the source text file inside `wind data/` so the wind-data files stay grouped together.
  - Kept `valid(UTC)` as the original string field rather than changing timestamp format during conversion.
- Open:
  - If needed, this dataset could also be re-exported in meters per second for `sknt` and `gust_sknt` while leaving direction columns unchanged.

### 2026-07-08 - Add wind-data tag to Markdown export

- Task: add the `#wind Data` tag to files in `wind data/` where it is safe to do so.
- Actions:
  - Inspected the folder contents: `bos_wind.txt`, `bos_wind.json`, `bos_wind_mps.json`, and `bos_wind_mps.md`.
  - Added `#wind Data` to the top of `wind data/bos_wind_mps.md`.
  - Verified the tag placement after correcting a leading-space formatting issue.
- Decisions:
  - Did not add the tag directly to the `.txt` or `.json` data files because prepending tag text would break the CSV and JSON file formats.
- Open:
  - If you want the non-Markdown files labeled too, the safe approach would be a separate README or sidecar metadata file in `wind data/`.

### 2026-07-08 - Export Boston wind dataset as Markdown table

- Task: create a Markdown-table version of the Boston wind dataset in meters per second.
- Actions:
  - Located the current data files in `wind data/` and created `wind data/bos_wind_mps.md`.
  - Exported the dataset as a Markdown table with columns `station`, `station_name`, `valid(UTC)`, and `wind_speed_mps`.
  - Kept the meter-per-second conversion consistent with the JSON export and preserved missing values as blank `null` cells rendered by PowerShell string conversion.
  - Verified the table structure by checking the header row, separator row, and the first data rows.
- Decisions:
  - Wrote the Markdown table next to the current wind-data files in `wind data/` so the related raw and derived files stay grouped together.
- Open:
  - The table is large because it includes the full dataset; if needed, it could also be split by date range or summarized.

### 2026-07-08 - Convert Boston wind JSON values from knots to meters per second

- Task: convert the Boston wind-speed dataset from knots to meters per second.
- Actions:
  - Created `bos_wind_mps.json` at the repo root from `sources/bos_wind.txt`.
  - Replaced the source `sknt` field with `wind_speed_mps` so the exported unit is explicit.
  - Converted knot values using `1 kt = 0.514444 m/s`, rounded to `6` decimal places, and preserved missing values as `null`.
  - Verified the converted file contains `13044` JSON objects and `86` null wind-speed entries.
- Decisions:
  - Kept `bos_wind.json` unchanged in knots and wrote a second file for the SI-unit version to avoid ambiguity and preserve the original derived export.
- Open:
  - If needed, the meter-per-second file could also be re-exported with fewer decimal places or with both units present in each row.

### 2026-07-08 - Convert Boston wind CSV text file to JSON

- Task: convert `sources/bos_wind.txt` into a JSON file for downstream use.
- Actions:
  - Read `sources/bos_wind.txt` and confirmed it is a comma-separated table with headers `station`, `station_name`, `valid(UTC)`, and `sknt`.
  - Created `bos_wind.json` at the repo root as a JSON array of row objects, preserving the original column names.
  - Normalized numeric `sknt` values to JSON numbers and converted missing `M` entries to `null`.
  - Verified the conversion by counting rows in both formats: `13044` CSV rows and `13044` JSON objects.
- Decisions:
  - Wrote the derived JSON file outside `sources/` to respect the repo rule that treats `sources/` as read-only input material.
  - Kept `valid(UTC)` as the original string field rather than changing timestamp format during conversion.
- Open:
  - If a different JSON shape would be more useful, the file could also be re-exported as newline-delimited JSON or with renamed keys.

### 2026-07-07 - Normalize existing wiki metadata to updated ingest schema

- Task: read the updated metadata instructions in `schema/Ingest Source` and update all existing wiki metadata to match the new schema format.
- Actions:
  - Audited metadata across `wiki/summaries/`, `wiki/concepts/`, `wiki/methods/`, `wiki/designs/`, and `wiki/parameters/` against the current `schema/Ingest Source` templates.
  - Normalized frontmatter in existing wiki content pages so summaries, concepts, and methods now use `Created`, `Updated`, `Sources`, `Source_count`, and single-line `Tags` fields in the new schema style.
  - Normalized design and parameter page frontmatter so `Tags` are single-line values and missing `Created` fields were populated.
  - Recomputed `Sources` backlinks and `Source_count` from the cited sources in each general wiki page, and repaired malformed metadata in pages such as `Discrete Vortex Method`, `Salp Swarm Algorithm`, and several older design notes with blank `Created` values.
  - Verified there are no blank required metadata fields, no old list-style `Tags` metadata blocks left in wiki content pages, and no Markdown `.md` links or unresolved wikilinks introduced by the maintenance pass.
- Decisions:
  - Used the current `schema/Ingest Source` text as authoritative and normalized all wiki metadata to one practical repo-wide rule: inline `Tags` values, explicit `Source_count`, and `Sources` backlinks collected from cited source notes.
  - Left `wiki/concepts/VAWT Design Comparisons.md` with empty `Sources` because it currently contains only wiki-link navigation and an `> Inference:` note, not direct source-backed claims.
- Open:
  - The schema is still somewhat ambiguous about whether multi-source `Sources` should be represented as inline strings or YAML lists; I normalized them as inline source-link strings to stay closest to the updated examples now written in `schema/Ingest Source`.

### 2026-07-07 - Convert and ingest vj27 wind-deflector review

- Task: convert `PDFs/vj27.pdf` into `sources/vj27.md`, extract its figures and equations, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj27.md` with source frontmatter, cleaned review structure, linked figures `vj27-fig1` through `vj27-fig12`, linked displayed equations `vj27-eq1` through `vj27-eq10`, and converted Tables 1-3 into Markdown tables.
  - Added `wiki/summaries/vj27-summary.md`.
  - Added the concept page `wiki/concepts/Wind Deflector.md`.
  - Added the source-specific parameter pages `wiki/parameters/vj27 Wind Deflector Shape.md` and `wiki/parameters/vj27 Wind Deflector Position and Orientation.md`.
  - Updated `wiki/concepts/Wind Flow Modifier.md`, `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/Optimization.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/methods/CFD.md`, `wiki/methods/Wind Tunnel Testing.md`, and `wiki/index.md` with `vj27`-supported claims and links.
  - Marked `sources/vj27.md` as processed.
- Decisions:
  - Treated `vj27` as a review ingest rather than creating design pages, because it synthesizes many deflector studies and turbine types instead of defining one source-specific turbine geometry with a coherent single performance dataset.
  - Added one reusable `Wind Deflector` concept page because the paper's main value is a cross-study framework for passive flow augmentation, broader than the existing `Wind Flow Modifier` note.
  - Added two parameter pages because the review explicitly centers its conclusions on deflector shape and on installation position/orientation as the key tuned variables affecting `Cp`.
- Open:
  - Most of the large performance gains in `vj27` are review-level summaries of cited papers, many of them CFD-heavy; cross-source experimental corroboration remains limited according to the review itself.

### 2026-07-07 - Convert and ingest vj26 VAWT rotor-design review

- Task: convert `PDFs/vj26.pdf` into `sources/vj26.md`, extract its figures, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj26.md` with source frontmatter, cleaned section structure, linked figures `vj26-fig1` through `vj26-fig9`, and preserved the review text and references.
  - Added `wiki/summaries/vj26-summary.md`.
  - Updated `wiki/concepts/VAWT.md`, `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/Hybrid VAWT.md`, `wiki/concepts/HAWT vs VAWT.md`, `wiki/concepts/Structures and Loads.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/Wind Tunnel Testing.md`, `wiki/methods/Wind Tunnel Blockage Correction.md`, and `wiki/index.md` with `vj26`-supported claims and links.
  - Marked `sources/vj26.md` as processed.
- Decisions:
  - Treated `vj26` as a review ingest rather than creating source-specific design pages, because the paper mainly surveys many cited third-party rotor concepts instead of defining one `vj26` turbine geometry with its own consolidated performance dataset.
  - Did not create source-specific parameter pages because the paper is structured as a broad literature review of many improvement strategies rather than a direct comparative study of one controlled parameter sweep under one source-specific experiment or model.
  - Folded the strongest actionable findings into existing concept and method pages, especially around self-starting, drag-rotor improvements, hybrid rationale, CFD limits, wind-tunnel blockage, and offshore structural issues.
- Open:
  - Several strong claims in `vj26` are themselves review-level summaries of cited studies, so they should be treated as source-grounded summaries of the reviewed literature rather than as direct experimental findings from the review authors' own single apparatus.

### 2026-07-07 - Convert and ingest vj25 aspect-ratio H-rotor design paper

- Task: convert `PDFs/vj25.pdf` into `sources/vj25.md`, extract its figures and equations, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj25.md` with source frontmatter, cleaned section structure, linked figures `vj25-fig1` through `vj25-fig8`, linked displayed equations `vj25-eq1` through `vj25-eq8`, and converted Tables 1-2 into Markdown.
  - Added `wiki/summaries/vj25-summary.md`.
  - Added the method page `wiki/methods/Multiple Stream Tube Model.md`.
  - Added the source-specific parameter page `wiki/parameters/vj25 Rotor Aspect Ratio.md`.
  - Added the source-specific design pages `wiki/designs/vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2).md` and `wiki/designs/vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4).md`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, and `wiki/index.md` with `vj25`-supported claims and links.
  - Marked `sources/vj25.md` as processed.
- Decisions:
  - Added a new `Multiple Stream Tube Model` method page because the paper's main reusable contribution is an MSTM-based sizing workflow rather than a new airfoil, CFD, or control technique.
  - Split the case study into two design pages because the paper reports two distinct converged rotors (`AR = 2` and `AR = 0.4`) with different final geometry and performance values.
  - Classified the aspect-ratio result as a `minimal positive effect` on the parameter page because the direction is clear but the explicit `Cp` gain in the `1 kW` comparison is modest (`0.464` to `0.475`).
- Open:
  - The paper's design recommendation is based on MSTM-generated characteristic curves and a numerical case study, not on experimental validation of the two final rotors.

### 2026-07-06 - Convert and ingest vj24 inverse-airfoil-design paper

- Task: convert `PDFs/vj24.pdf` into `sources/vj24.md`, extract its figures and displayed equation, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj24.md` with source frontmatter, cleaned section structure, linked figures `vj24-fig1` through `vj24-fig4`, linked the displayed approximation equation as an image, and converted Table 1 into Markdown.
  - Added `wiki/summaries/vj24-summary.md`.
  - Added the source-specific design page `wiki/designs/vj24 3-Bladed Straight-Bladed Darrieus VAWT.md`.
  - Added the source-specific parameter page `wiki/parameters/vj24 Blade Airfoil.md`.
  - Added the method page `wiki/methods/PROFOIL.md`.
  - Updated `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/methods/Double-Multiple Streamtube Model.md`, and `wiki/index.md` with `vj24`-supported claims and links.
  - Marked `sources/vj24.md` as processed.
- Decisions:
  - Added one design page because the paper evaluates one concrete `3`-bladed straight-bladed Darrieus example with full source-stated geometry and comparative whole-rotor output values.
  - Added one parameter page for blade airfoil because the central changed design variable is the inverse-tailored airfoil (`NACA 0018` to `NACA 0018-M`).
  - Added one method page for `PROFOIL` because the paper's main reusable contribution is the inverse-design workflow rather than CFD or a new whole-rotor control strategy.
- Open:
  - The paper explicitly says the reported gain should be treated as a relative qualitative improvement because low-Re, high-angle-of-attack post-stall prediction remains unreliable in the analysis chain.

### 2026-07-06 — Convert and ingest vj23 simple Darrieus VAWT design note

- Task: convert `PDFs/vj23.pdf` into `sources/vj23.md`, extract its figures and displayed equation, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj23.md` with source frontmatter, cleaned section structure, linked figures `vj23-fig1` through `vj23-fig5`, and linked the displayed wind-kinetic-energy equation as an image.
  - Added `wiki/summaries/vj23-summary.md`.
  - Added the source-specific design page `wiki/designs/vj23 3-Bladed Darrieus VAWT with Gearbox.md`.
  - Added the source-specific parameter pages `wiki/parameters/vj23 Blade Number.md` and `wiki/parameters/vj23 Gearbox Sizing.md`.
  - Updated `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/HAWT vs VAWT.md`, and `wiki/index.md` with `vj23`-supported claims and links.
  - Marked `sources/vj23.md` as processed.
- Decisions:
  - Added one design page because the paper includes one concrete three-bladed Darrieus concept with gearbox-chain drive.
  - Added one blade-number parameter page and one gearbox-sizing parameter page because those are the clearest changed design levers discussed in the source.
  - Did not create a separate gearbox concept page because the source's gearbox discussion is brief and design-specific rather than a strong standalone reusable method or concept note.
- Open:
  - The paper is brief and internally mixed about blade count: the abstract highlights a `3`-blade case, while the later text says `4` blades give greater and more stable torque.

### 2026-07-06 — Convert and ingest vj22 low-wind QBlade airfoil and blade-count study

- Task: convert `PDFs/vj22.pdf` into `sources/vj22.md`, extract its figures and equations, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj22.md` with source frontmatter, cleaned structure, linked figures `vj22-fig1` through `vj22-fig12`, linked the two displayed equations as images, and converted Tables 1-4 into Markdown tables.
  - Added `wiki/summaries/vj22-summary.md`.
  - Added the source-specific design page `wiki/designs/vj22 Simulated Small-Scale Straight-Bladed VAWT.md`.
  - Added the source-specific parameter pages `wiki/parameters/vj22 Blade Profile.md` and `wiki/parameters/vj22 Blade Number.md`.
  - Added the method page `wiki/methods/QBlade.md`.
  - Updated `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md` with `vj22`-supported claims and links.
  - Marked `sources/vj22.md` as processed.
- Decisions:
  - Added one simulated-design page because the paper defines a specific small rotor geometry that is then used for the airfoil and blade-count comparisons.
  - Added two parameter pages because the paper's clearest changed design variables are airfoil profile (`NACA 0012` vs `NACA 0015`) and blade number (`3`, `5`, `8`).
  - Added a `QBlade` method page because the source uses the software as the core analysis workflow and no such method note existed yet.
- Open:
  - The `vj22` conclusions are simulation-only and not experimentally validated in this paper, so its low-wind performance claims should be treated as source-specific until corroborated.

### 2026-07-06 — Convert and ingest vj21 fixed-pitch straight-bladed VAWT design-parameter paper

- Task: convert `PDFs/vj21.pdf` into `sources/vj21.md`, extract its figures, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj21.md` with source frontmatter, cleaned section structure, linked figures `vj21-fig1` through `vj21-fig7`, and converted the design-parameter table into Markdown.
  - Added `wiki/summaries/vj21-summary.md`.
  - Added four source-specific parameter pages: `vj21 Blade Airfoil`, `vj21 Blade Number`, `vj21 Supporting Strut Shape`, and `vj21 Blade Material`.
  - Updated `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Materials and Manufacturing.md`, `wiki/concepts/Design Checklist.md`, `wiki/concepts/Rules of Thumb.md`, and `wiki/index.md` with `vj21`-supported claims and links.
  - Marked `sources/vj21.md` as processed.
- Decisions:
  - Treated `vj21` as a design-guide/review ingest rather than a single turbine-design ingest, so I did not create a design page.
  - Added only the clearest source-specific parameter pages where the paper gives direct comparative or directional recommendations, instead of splitting every listed design consideration into its own weak page.
  - Folded broader guidance on solidity, aspect ratio, cut-out speed, and overall fixed-pitch SB-VAWT design practice into the existing concept pages rather than inventing new umbrella notes.
- Open:
  - The figures for winglets, endplates, and elliptical blades are concept illustrations tied to cited prior work, and the source explicitly says further aerodynamic and economic analysis is still required before concluding their practical value for SB-VAWT blades.

### 2026-07-06 — Convert and ingest vj20 proposed asymmetric-inner hybrid VAWT study

- Task: convert `PDFs/vj20.pdf` into `sources/vj20.md`, extract its figures and equations, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj20.md` with source frontmatter, cleaned section structure, figure links `vj20-fig1` through `vj20-fig18`, equation images `vj20-eq1` through `vj20-eq12`, and Markdown versions of Tables 1-5.
  - Added `wiki/summaries/vj20-summary.md`.
  - Added the single-source design page `wiki/designs/vj20 Proposed Hybrid VAWT.md`.
  - Added the source-specific parameter page `wiki/parameters/vj20 Blade Surface Roughness.md`.
  - Added the new method page `wiki/methods/Box-Behnken Design.md`.
  - Updated `wiki/concepts/Hybrid VAWT.md`, `wiki/concepts/Scaling Effects.md`, `wiki/concepts/Optimization.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/methods/CFD.md`, `wiki/methods/Wind Tunnel Testing.md`, and `wiki/index.md` with `vj20`-supported claims and links.
  - Marked `sources/vj20.md` as processed.
- Decisions:
  - Created one design page because the paper centers on one concrete proposed hybrid turbine with full-scale and scaled-model geometry.
  - Created one parameter page for blade surface roughness because that is the explicit source-specific performance sweep reported experimentally.
  - Added one new method page for Box-Behnken design because the source uses it as a reusable optimization workflow rather than only as background vocabulary.
  - Used the full-scale similarity-table values for the design-page cut-in and rated-speed fields, while noting that the paper also reports different scaled-model startup values elsewhere.
- Open:
  - `vj20` contains multiple context-dependent startup values (`1.72`, `1.54`, `1.405`, and `2.81 m/s` depending on section and scaling context), so cut-in comparisons to other sources should keep that discrepancy visible.

### 2026-07-06 — Convert and ingest vj19 Savonius design, modeling, and economics paper

- Task: convert `PDFs/vj19.pdf` into `sources/vj19.md`, extract its figures, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj19.md` with source frontmatter, cleaned paper structure, inline figure links, equation image links, and Markdown versions of the two paper tables.
  - Extracted `vj19-fig1a` through `vj19-fig7` and `vj19-eq1` through `vj19-eq6` into `images/`.
  - Added `wiki/summaries/vj19-summary.md`.
  - Added the single-source design page `wiki/designs/vj19 Curved-Blade Savonius VAWT.md`.
  - Added the source-specific parameter page `wiki/parameters/vj19 Savonius Blade Shape.md`.
  - Updated `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/Annual Energy Output.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Economic Viability of VAWTs.md`, `wiki/methods/AEO Calculation.md`, `wiki/methods/Payback Period Analysis.md`, and `wiki/index.md` with `vj19`-supported claims and links.
  - Marked `sources/vj19.md` as processed.
- Decisions:
  - Created one design page for the curved-blade Savonius turbine because that is the configuration the paper carries into the full modeling and economics workflow.
  - Created one parameter page for Savonius blade shape because the experimental comparison of curved, straight, aerofoil, and twisted blades is the source's main changed design variable.
  - Left rated power blank on the design page because the source says rated power is reached at `9 m/s`, but the paper's electrical-power table continues increasing above that point.
- Open:
  - The paper's Table 2 is internally awkward around rated-power reporting, so any use of its payback claim should stay source-specific until corroborated.

### 2026-07-06 — Tighten vj19 equation crops

- Task: check the crop quality of the `vj19` equation images and fix any bad crops.
- Actions:
  - Reviewed `images/vj19-eq1.png` through `images/vj19-eq6.png` against the source page.
  - Found that several crops included surrounding paragraph text or clipped parts of the formulas.
  - Re-rendered all six equation images as tighter formula-only crops from page 3 of `PDFs/vj19.pdf`.
- Decisions:
  - Overwrote the existing `vj19-eq*.png` files in place so `sources/vj19.md` did not need link changes.
  - Kept the equation numbering and placement unchanged because the source note structure was already correct.
- Open:
  - None.

### 2026-07-06 — Clean va27 source-note formatting and math rendering

- Task: improve `sources/va27.md` readability after conversion by fixing broken header formatting and replacing the roughest math/table OCR with direct source-page snapshots.
- Actions:
  - Cleaned the top of `sources/va27.md` so the title, affiliations, keywords, and abstract read in the correct order without duplicated header text.
  - Replaced the broken nomenclature block with a clean image from the source page.
  - Replaced the large literature-overview table with two source-page images instead of leaving the noisy OCR dump inline.
  - Replaced the roughest airfoil-shape equation block with equation images and removed the worst duplicated symbolic fragments.
  - Replaced the validation-summary and leading-edge-radius summary tables with source-page images instead of malformed OCR text.
- Decisions:
  - Preferred source-page images for the heavy tables and equations because they preserved the original notation more faithfully than the extracted text.
  - Left the rest of the paper in text form because most narrative sections were already readable enough and fully re-rendering the full methods section as images would make the note harder to search.
- Open:
  - `sources/va27.md` is substantially cleaner, but some long literature/reference formatting and a few figure-caption line breaks are still not perfectly normalized.

### 2026-07-06 — Convert and ingest va27 dynamic-stall airfoil-shape study

- Task: convert `PDFs/va27_raw.pdf` into `sources/va27.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va27.md` with source frontmatter and linked figure images `va27-fig1` through `va27-fig18`.
  - Added `wiki/summaries/va27-summary.md`.
  - Added the design page `wiki/designs/va27 Reference One-Bladed H-Type VAWT.md`.
  - Added three source-specific parameter pages: `wiki/parameters/va27 Airfoil Relative Maximum Thickness.md`, `wiki/parameters/va27 Airfoil Maximum-Thickness Position.md`, and `wiki/parameters/va27 Leading-Edge Radius Index.md`.
  - Added the concept page `wiki/concepts/Morphing Airfoil.md`.
  - Updated `wiki/concepts/Optimization.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, `wiki/concepts/H-VAWT.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md` with `va27`-supported claims and links.
  - Marked `sources/va27.md` as processed.
- Decisions:
  - Added three parameter pages because the paper explicitly studies three distinct airfoil-shape parameters: `t/c`, `xt/c`, and `I`.
  - Added one concept page for morphing airfoils because the paper frames the optimization results as a stepping stone toward adaptive airfoil geometry rather than just a one-off static optimization.
  - Added one design page for the reference one-bladed H-type rotor because the source defines a specific computational turbine geometry used across all shape comparisons.
- Open:
  - `sources/va27.md` is readable and figure-linked, but the long equation-heavy shape-generation section is still rough text extraction rather than clean mathematical notation.

### 2026-07-06 — Re-extract va26 figures for complete graph bounds

- Task: replace the `va26` figure images because several graph crops cut off important parts of the figure area, including axis labels or the intended plot region.
- Actions:
  - Audited the full `va26` figure sequence against `PDFs/va26_raw.pdf` and re-mapped `Fig. 1` through `Fig. 22` to the correct visible figure regions.
  - Rebuilt the full `images/va26-fig*.jpg` set from the PDF using corrected page coordinates.
  - Spot-checked the sensitivity, validation, static-airfoil, pitch-angle, and wake-generation plots to confirm that the graph bounds, axes, and labels are now visible.
- Decisions:
  - Rebuilt the whole set instead of patching only the obviously broken files because one earlier remap had also assigned a figure number to the wrong page region.
  - Kept `sources/va26.md` unchanged because its figure numbering and image links were already correct; only the underlying image files needed replacement.
- Open:
  - The figures are now correctly mapped and substantially cleaner, but they remain page renders from the PDF rather than original vector exports.

### 2026-07-06 — Re-extract va25 figures for correctness

- Task: replace the `va25` figure images because many of the first-pass crops included surrounding page text or missed the actual figure content.
- Actions:
  - Audited the PDF layout page by page and matched each `Fig. 1` through `Fig. 21` caption to the visible figure region in `PDFs/va25_raw.pdf`.
  - Replaced all `images/va25-fig*.jpg` files with tighter figure-only renders based on the visible figure regions rather than the earlier rough page crops.
  - Spot-checked the corrected set, with special attention to the symmetric-airfoil, cambered-in, cambered-out, and comparison plots that were previously wrong or incomplete.
- Decisions:
  - Preferred page-region renders over trying to recover every figure from embedded image objects because several plots are page-drawn/vector content rather than standalone embedded raster images.
  - Left `sources/va25.md` unchanged because its figure links were already correct; only the underlying image files needed replacement.
- Open:
  - A few figures are still close crops of page-rendered charts rather than original vector exports, but they now show the intended figures cleanly without the earlier page-fragment errors.

### 2026-07-06 — Convert and ingest va26 fixed-pitch H-rotor study

- Task: convert `PDFs/va26_raw.pdf` into `sources/va26.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va26.md` with source frontmatter and linked figure images `va26-fig1` through `va26-fig22`.
  - Added `wiki/summaries/va26-summary.md`.
  - Added the design page `wiki/designs/va26 3-Bladed H-Type VAWT.md`.
  - Added the source-specific parameter page `wiki/parameters/va26 Fixed Blade Pitch Angle.md`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, `wiki/methods/Double-Multiple Streamtube Model.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md` with `va26`-supported claims and figure links.
  - Marked `sources/va26.md` as processed.
- Decisions:
  - Added one parameter page because the paper's central design variable is the fixed blade pitch angle.
  - Added one design page because the study uses one specific 3-bladed H-type VAWT geometry as the basis for all comparisons.
  - Kept the source conversion text-heavy because the methodology and equation sections are long and symbol-dense, and a full equation-image cleanup would be a larger separate pass.
- Open:
  - `sources/va26.md` is figure-linked and source-usable, but several equations and some layout fragments remain rough text extraction rather than clean typeset math.

### 2026-07-06 — Convert and ingest va25 airfoil self-starting study

- Task: convert `PDFs/va25_raw.pdf` into `sources/va25.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va25.md` with source frontmatter and linked figure images `va25-fig1` through `va25-fig21`.
  - Added `wiki/summaries/va25-summary.md`.
  - Added the design page `wiki/designs/va25 Reference H-Rotor Darrieus VAWT.md`.
  - Added two source-specific parameter pages: `wiki/parameters/va25 Blade Airfoil Profile.md` and `wiki/parameters/va25 Cambered Airfoil Orientation.md`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, `wiki/methods/Double-Multiple Streamtube Model.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md` with `va25`-supported claims and links.
  - Marked `sources/va25.md` as processed.
- Decisions:
  - Added two parameter pages because the paper studies two distinct design levers: airfoil profile selection and camber orientation.
  - Added one reference-rotor design page because the study uses a specific H-rotor baseline geometry as the common platform for all comparisons.
  - Kept the source conversion text-heavy because the equation and table layout in the source PDF is difficult to normalize cleanly without a much larger cleanup pass.
- Open:
  - `sources/va25.md` is figure-linked and usable for ingestion, but some of the OCR-style line breaking and table/equation formatting remain rough compared with the source PDF.

### 2026-07-06 — Convert and ingest va24 DMST variable-pitch study

- Task: convert `PDFs/va24_raw.pdf` into `sources/va24.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va24.md` with source frontmatter, linked figure images `va24-fig1` through `va24-fig11`, and converted the validation-parameter table into Markdown.
  - Added `wiki/summaries/va24-summary.md`.
  - Added the design page `wiki/designs/va24 Variable-Pitch 3-Bladed NACA0015 Straight-Bladed VAWT.md`.
  - Added the source-specific parameter page `wiki/parameters/va24 Variable Blade Pitching Strategy.md`.
  - Updated `wiki/methods/Double-Multiple Streamtube Model.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Wind Turbine Parameters.md`, and `wiki/index.md` with `va24`-supported claims and figure links.
  - Marked `sources/va24.md` as processed.
- Decisions:
  - Added one parameter page because the paper's central changed design variable is the blade-pitching strategy and associated maximum local angle of attack target.
  - Added one design page because the paper repeatedly evaluates a specific straight-bladed NACA0015 rotor under fixed and active-pitch control, even though the paper is more about control strategy than hardware fabrication.
  - Kept the frontmatter fields mostly blank on the design page because the paper mixes a 2-blade validation table with 3-blade results, so several whole-turbine catalog fields are not source-clear enough to populate confidently.
- Open:
  - `sources/va24.md` is readable and figure-linked, but the equation-heavy methodology sections remain rough text extraction rather than clean equation-image renderings.

### 2026-07-06 — Convert and ingest vj18 variable-design review

- Task: convert `PDFs/vj18.pdf` into `sources/vj18.md`, extract and normalize its figures into `images/vj18-fig*.jpg`, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj18.md` with source frontmatter, section structure, and linked figure images `vj18-fig1` through `vj18-fig13`.
  - Rewrote `sources/vj18.md` as a page-faithful conversion so the paper text is kept in sequence and the figure images sit next to their captions instead of being grouped at the bottom.
  - Extracted the review figures into the repo image format, including a manual split for the page that contains two separate figures.
  - Added `wiki/summaries/vj18-summary.md`.
  - Added the new umbrella concept page `wiki/concepts/Variable VAWT Design.md`.
  - Updated `wiki/concepts/Optimization.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Materials and Manufacturing.md`, `wiki/concepts/Structures and Loads.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/VAWT Design Overview.md`, and `wiki/index.md` with `vj18`-supported claims and links.
- Decisions:
  - Treated `vj18` as a review-level ingest, so I created one umbrella concept page instead of splitting every variable mechanism into a separate standalone page.
  - Kept the wiki updates focused on the reusable design lessons the review actually supports: design taxonomy, performance ranges, complexity tradeoffs, and validation needs.
- Open:
  - The extracted figures are page-region crops from a review PDF with mixed text-and-figure layouts, so they are usable but not perfectly uniform.

### 2026-07-06 — Replace vj18 equation OCR

- Task: make sure the equations in `sources/vj18.md` render correctly.
- Actions:
  - Rendered cropped equation images from the source PDF and added `images/vj18-eq1-5.png`, `images/vj18-eq6-11.png`, `images/vj18-eq12.png`, `images/vj18-eq13-17.png`, `images/vj18-eq18.png`, and `images/vj18-eq19.png`.
  - Replaced the broken equation OCR blocks in `sources/vj18.md` with inline image embeds near the original locations.
  - Removed duplicated OCR fragments left behind by the source conversion.
- Decisions:
  - Used image fallbacks instead of retyping equations because the OCR text was not reliable enough to trust.
  - Kept the surrounding explanatory prose so the note still reads like a paper conversion.
- Open:
  - None.

### 2026-07-06 — Reformat vj18 source note

- Task: fix the formatting of `sources/vj18.md` so it reads as a paper conversion instead of a stream of wrapped OCR lines with page markers.
- Actions:
  - Removed page markers and footer noise from `sources/vj18.md`.
  - Reinserted the major section headings for the review and split the prose into readable sentence-level lines.
  - Kept the figure images inline where their captions appear in the paper.
- Decisions:
  - Preserved the source text rather than summarizing it, because the user wanted the conversion to stay source-faithful.
  - Left some OCR artifacts in place where they do not affect readability, instead of rewriting the paper content.
- Open:
  - None.

### 2026-07-06 — Tighten vj18 equation crops

- Task: remove surrounding paragraph text from the `vj18` equation images.
- Actions:
  - Re-rendered the equations as tighter per-formula crops from the PDF.
  - Split the multi-equation sections into individual equation images where that kept the crop clean.
  - Updated `sources/vj18.md` to point at the tighter equation images instead of the earlier broad crops.
- Decisions:
  - Kept image fallbacks instead of retyping the formulas.
  - Preferred narrow equation-only crops over larger stitched crops because the user explicitly wanted the surrounding text removed.
- Open:
  - None.

### 2026-07-06 — Backfill missing design metadata

- Task: audit the `wiki/designs/` section for the required design-page metadata block and fill in any missing fields.
- Actions:
  - Audited every design page against the schema-required frontmatter fields for design pages.
  - Found that `vj17 Airfoil-Based Savonius Wind Turbine` was missing the metadata block fields beyond `Created`, `Source`, and `Tags`.
  - Added the full design metadata block to `wiki/designs/vj17 Airfoil-Based Savonius Wind Turbine.md`, populating the supported `Cp` and `TSR` values from `sources/vj17.md` and leaving unsupported fields blank.
- Decisions:
  - Kept unsupported design metadata blank instead of inferring values not given by the source.
  - Left the other design pages unchanged because they already had the required metadata fields.
- Open:
  - None.

### 2026-07-06 — Convert and ingest va23 shifted-troposkien comparison paper

- Task: convert `PDFs/va23_raw.pdf` into `sources/va23.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va23.md` with source frontmatter, linked figure images `va23-fig1` through `va23-fig12`, and converted the turbine-specification table into Markdown.
  - Added `wiki/summaries/va23-summary.md`.
  - Added three single-source design pages: `va23 Conventional Troposkien VAWT`, `va23 50% STS-VAWT`, and `va23 100% STS-VAWT`.
  - Added the source-specific parameter page `va23 Shifted Troposkien Vertical Offset`.
  - Added the new concept page `wiki/concepts/Blade-Wake Interaction.md` and the new method page `wiki/methods/Wind Tunnel Blockage Correction.md`.
  - Updated `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/methods/Wind Tunnel Testing.md`, and `wiki/index.md` with `va23`-supported claims and links.
  - Marked `sources/va23.md` as processed.
- Decisions:
  - Split the paper into three design pages because it evaluates three explicit turbine configurations with distinct geometry and performance outcomes.
  - Added one parameter page for vertical shift amount because that is the central design variable the paper changes to influence blade-wake interaction and power coefficient.
  - Added a dedicated blockage-correction method page because the paper's modified Pope-and-Harper correction is a reusable workflow element, not just a one-off detail.
- Open:
  - `sources/va23.md` is usable and fully figure-linked, but the equation-heavy sections still contain rough text extraction artifacts rather than clean equation-image renderings.

### 2026-07-06 — Convert and ingest va22 low-TSR helical VAWT design paper

- Task: convert `PDFs/va22_raw.pdf` into `sources/va22.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va22.md` with source frontmatter, cleaned paper structure, linked figure images `va22-fig1` through `va22-fig9`, and converted Tables 1-7 into Markdown tables.
  - Built a composite image for the multi-page Figure 4 and tightened the figure crops for the remaining figures so the source note links match the paper's visible figures.
  - Added `wiki/summaries/va22-summary.md`.
  - Added the single-source design page `wiki/designs/va22 100-W Helical-Blade Vertical-Axis Wind Turbine.md`.
  - Updated `wiki/concepts/Helical VAWT.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/methods/Double-Multiple Streamtube Model.md`, `wiki/methods/Wind Tunnel Testing.md`, `wiki/methods/CFD.md`, and `wiki/index.md` with `va22`-supported claims and figure links.
  - Marked `sources/va22.md` as processed.
- Decisions:
  - Added a design page because the paper defines one concrete helical VAWT geometry with rated specifications, manufactured hardware, and measured performance.
  - Did not add a parameter page because the paper motivates a low tip-speed ratio design target but does not run a controlled source-specific parameter sweep in the schema sense.
  - Updated existing methods pages instead of creating a new design-method note because the paper's reusable technique fits the current `Double-Multiple Streamtube Model`, `CFD`, and `Wind Tunnel Testing` pages.
- Open:
  - `sources/va22.md` is readable and complete enough to ingest, but some equation formatting is still preserved as compact extracted text rather than clean typeset math images.

### 2026-07-06 — Convert and ingest va21 rooftop VAWT prototype paper

- Task: convert `PDFs/va21_raw.pdf` into `sources/va21.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va21.md` with source frontmatter, cleaned section structure, linked figure images `va21-fig1` through `va21-fig23`, and converted the two in-paper tables into Markdown tables.
  - Extracted and corrected figure crops so the linked source figures show the actual figure content rather than surrounding body text on the multi-figure pages.
  - Added `wiki/summaries/va21-summary.md`.
  - Added the single-source design page `wiki/designs/va21 Rooftop Vertical-Axis Wind Turbine.md`.
  - Updated `wiki/concepts/Architectural Wind Turbines.md`, `wiki/concepts/Urban Wind Conditions.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/Economic Viability of VAWTs.md`, `wiki/methods/CFD.md`, and `wiki/index.md` with `va21`-supported claims and figure links.
  - Marked `sources/va21.md` as processed.
- Decisions:
  - Added a design page because the paper documents one concrete rooftop VAWT prototype with source-specific geometry, installation details, and measured performance.
  - Did not add a parameter page because the study does not run a clean source-specific sweep of a single design variable in the schema sense; its blade shaping is described as a trial-and-error prototype choice rather than a controlled parameter study.
  - Noted the source's optimistic `7-15 year` payback estimate as a discrepancy instead of folding it into a general rule, because the same paper reports only watt-scale measured output and other low-wind rooftop cases in the wiki are much less favorable.
- Open:
  - `sources/va21.md` is readable and fully figure-linked, but the converted note still contains some compact reference formatting and a few extraction artifacts in the back matter.

### 2026-07-06 — Re-extract va18 and va19 figures for readability

- Task: replace the `va18` and `va19` figure screenshots so they capture the actual figures cleanly and avoid surrounding body text.
- Actions:
  - Audited both PDFs and confirmed that many figure files could be rebuilt from embedded PDF image objects instead of broad page-region crops.
  - Replaced `va18-fig1` through `va18-fig16`, using embedded figure images where available and tighter figure-only composite crops for the multi-panel pages.
  - Replaced `va19-fig1` through `va19-fig24`, using embedded figure images where available and tighter vector-page crops for charts and survey plots that were not stored as standalone images in the PDF.
  - Verified that `sources/va18.md` and `sources/va19.md` do not have image embeds running into adjacent paragraph text.
- Decisions:
  - Preferred embedded image extraction whenever the original PDF asset existed, because it preserved the full figure with less surrounding noise than page clipping.
  - Used page clips only for vector-drawn figures and fragmented pages where there was no single embedded image to extract.
- Open:
  - Some `va19` vector-drawn figures are still page renders rather than original image objects because the PDF does not expose them as standalone embedded images.

### 2026-07-06 — Re-extract va20 figures from embedded PDF images

- Task: fix the `va20` figure screenshots so they capture the actual figures instead of large page regions with surrounding body text.
- Actions:
  - Audited the `va20` PDF layout and confirmed that the current figure files were broad page crops rather than figure-only captures.
  - Replaced `images/va20-fig1.jpg` through `images/va20-fig26.jpg` with the PDF's embedded figure images, which removed surrounding page text and preserved the full figures more cleanly.
  - Cleaned `sources/va20.md` so image embeds no longer run into following paragraph text on the same line.
- Decisions:
  - Used embedded PDF image extraction instead of manual page cropping because the original assets were available and produced cleaner figure-only outputs.
- Open:
  - Table and equation fallbacks for `va20` were left unchanged because this pass was specifically to correct the figure extraction problem.

### 2026-07-06 — Convert and ingest va20 involute rotor and wind-flow-modifier study

- Task: convert `PDFs/va20_raw.pdf` into `sources/va20.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va20.md` with source frontmatter, cleaned section structure, figure links `va20-fig1` through `va20-fig26`, table images `va20-table1` through `va20-table6`, and equation images for the governing-equation sections.
  - Cleaned the converted source note by removing rough OCR table/equation dumps where image fallbacks were clearer.
  - Added `wiki/summaries/va20-summary.md`.
  - Added `wiki/concepts/Wind Flow Modifier.md`.
  - Added three single-source design pages: `va20 H-Type Rotor with C-Blade`, `va20 Involute Blade Type Rotor`, and `va20 Involute Rotor with Wind Flow Modifier`.
  - Added two source-specific parameter pages: `va20 Rotor Blade Profile` and `va20 Wind Flow Modifier`.
  - Updated `wiki/methods/CFD.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Urban Wind Conditions.md`, and `wiki/index.md` with `va20`-supported claims and figure links.
  - Marked `sources/va20.md` as processed.
- Decisions:
  - Split the source into three design pages because the paper evaluates three explicit rotor configurations with separate geometry and performance outcomes.
  - Added two parameter pages because the studied changes are the rotor blade profile and the addition of the wind flow modifier.
  - Added a reusable concept page for the wind flow modifier because the source presents it as a general low-wind augmentation idea, not only as a one-off design detail.
- Open:
  - `sources/va20.md` is readable and substantially cleaned, but a few mathematical-symbol lines in the turbulence-model section are still preserved more as textual remnants around the equation-image fallback than as perfectly typeset math.

### 2026-07-06 — Convert and ingest vj14 H-Darrieus LCA study

- Task: convert `PDFs/vj14.pdf` into `sources/vj14.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj14.md` with source frontmatter, cleaned paper structure, and linked figure images `vj14-fig1` through `vj14-fig8`.
  - Added `wiki/summaries/vj14-summary.md`.
  - Added the new concept page `Capacity Factor` and the new method page `Life Cycle Assessment`.
  - Added the design page `Windkop 5 kW H-Darrieus VAWT`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/Economic Viability of VAWTs.md`, `wiki/concepts/Urban Wind Conditions.md`, and `wiki/index.md` with `vj14`-supported claims and links.
  - Marked `sources/vj14.md` as processed.
- Decisions:
  - Treated the paper as both a design note and an LCA/method note because it reports a concrete deployed H-Darrieus turbine and a cradle-to-grave assessment of that exact system.
  - Added a capacity-factor concept page because the paper treats capacity factor as the key variable driving both performance and lifecycle conclusions.
  - Kept the source-based design page narrowly scoped to the one prototype described in the paper.
- Cleanup:
  - Corrected the source frontmatter publication date to the online date reported in the paper (`2019-12-03`).
  - Removed page markers and footer noise from `sources/vj14.md` after confirming the PDF text layer was readable.
  - Converted the three main table blocks in `sources/vj14.md` into markdown tables.
- Open:
  - The source note is readable and figure-linked.

### 2026-07-06 — Convert and ingest vj13 Savonius cluster study

- Task: convert `PDFs/vj13.pdf` into `sources/vj13.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/vj13.md` with source frontmatter, cleaned paper structure, and linked figure images `vj13-fig1` through `vj13-fig14`.
  - Added `wiki/summaries/vj13-summary.md`.
  - Added new concept pages `Savonius Wind Turbine Cluster` and `Wake Effect`.
  - Added new methods pages `Variable Rotational Speed Method` and `Power Curve Annual Prediction`.
  - Added the parameter page `vj13 Cluster Installation Orientation`.
  - Added the design page `vj13 Three-Turbine Savonius Cluster` because the paper defines a concrete cluster geometry and evaluates it as a system.
  - Updated `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/Annual Energy Output.md`, `wiki/concepts/Urban Wind Conditions.md`, and `wiki/index.md` with `vj13`-supported claims and links.
  - Marked `sources/vj13.md` as processed.
- Decisions:
  - Treated the cluster as a concept rather than a novel named turbine design because the paper studies a conventional Savonius cluster layout and an orientation strategy, not a new rotor geometry.
  - Added a source-specific parameter page because installation orientation is the main design variable the paper varies to improve annual output.
  - Kept the new method pages separate because the paper's variable-speed control and power-curve annual prediction are reusable workflow ideas.
  - Added a design page because the paper's three-rotor cluster is a concrete reusable geometry even though its main contribution is the orientation strategy.
- Open:
  - `sources/vj13.md` is readable and figure-linked, but some table text is still in extracted line form rather than clean markdown tables.

### 2026-07-06 — Improve va19 source-note readability after conversion

- Task: clean `sources/va19.md` so the converted source is readable without rough extraction artifacts.
- Actions:
  - Removed OCR text that had been pulled from inside figures, including chart axes, legend labels, and decorative figure text that should not appear in the source note.
  - Replaced rough appendix table dumps with readable Markdown for Tables 1-3 and table-image inserts for Tables 4-17.
  - Added an image for Equation 3 and cleaned several obvious extraction issues such as broken product names and unreadable cross-reference placeholders.
  - Verified that `sources/va19.md` now links 24 figure images, 17 table images or clean table renderings, and 3 equation images without unresolved local-note links.
- Decisions:
  - Used image fallbacks for most appendix tables because they were symbol-heavy or badly laid out in extraction, and forcing them into text would have made the note less readable.
  - Kept the original wording where readable, limiting edits to cleanup and presentation rather than rewriting content.
- Open:
  - `sources/va19.md` is substantially cleaner, but a few references still contain original line-wrap awkwardness from the source PDF rather than fully normalized bibliography formatting.

### 2026-07-06 — Convert and ingest va19 MIT campus wind-feasibility study

- Task: convert `PDFs/va19_raw.pdf` into `sources/va19.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va19.md` with source frontmatter, cleaned extracted text, linked extracted figures `va19-fig1` through `va19-fig24`, and added equation images for the MCP and wind-power equations.
  - Added `wiki/summaries/va19-summary.md`.
  - Added `wiki/methods/Measure-Correlate-Predict (MCP).md`.
  - Added source-specific design pages `wiki/designs/va19 Skystream 3.7.md` and `wiki/designs/va19 AeroVironment AVX1000.md`.
  - Updated `wiki/concepts/Architectural Wind Turbines.md`, `wiki/concepts/Urban Wind Conditions.md`, `wiki/methods/Payback Period Analysis.md`, and `wiki/index.md` with `va19`-supported claims and figure links.
  - Marked `sources/va19.md` as processed.
- Decisions:
  - Added two design pages because the source directly compares two concrete turbine products with source-specific geometry, installation intent, and reported economic outcomes.
  - Added an MCP method page because the source's resource-normalization workflow is one of its main reusable technical pieces.
  - Did not add parameter pages because the source is a siting and feasibility study rather than a turbine design-parameter experiment.
- Open:
  - `sources/va19.md` is usable and grounded, but parts of the long appendix remain rough text extraction rather than fully normalized Markdown tables, and some captions still reflect the original scan formatting.

### 2026-07-06 — Convert and ingest va18 urban CFD resource-assessment paper

- Task: convert `PDFs/va18_raw.pdf` into `sources/va18.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va18.md` with source frontmatter, cleaned section structure, linked extracted figures `va18-fig1` through `va18-fig16`, one equation image, and a screenshot for `Table 2`.
  - Added `wiki/summaries/va18-summary.md`.
  - Added `wiki/methods/Climatology Assimilation.md`.
  - Updated `wiki/concepts/Urban Wind Conditions.md`, `wiki/methods/CFD.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/Wind Shear.md`, and `wiki/index.md` with `va18`-supported claims and figure links.
  - Marked `sources/va18.md` as processed.
- Decisions:
  - Did not add a design page because the paper compares urban candidate sites and assessment methods rather than documenting one source-owned turbine design.
  - Did not add a parameter page because the controlled variables are resource-assessment inputs and climatology-transfer techniques, not turbine design parameters in the schema sense.
  - Added a new method page for climatology assimilation because it is the source's main reusable technical contribution beyond generic CFD siting.
- Open:
  - `sources/va18.md` is readable and grounded, but some figure-heavy content was preserved as images rather than fully retyped tables/equations, and the paper still leaves the low 2-year TopoWind-assimilation result unexplained.

### 2026-07-06 — Convert and ingest va17 MIT rooftop wind-resource thesis

- Task: convert `PDFs/va17_raw.pdf` into `sources/va17.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va17.md` with source frontmatter, cleaned section structure, and linked extracted figures `va17-fig1` through `va17-fig12`.
  - Added `wiki/summaries/va17-summary.md`.
  - Added `wiki/concepts/Architectural Wind Turbines.md`.
  - Updated `wiki/concepts/Urban Wind Conditions.md`, `wiki/methods/CFD.md`, `wiki/concepts/CFD and Validation.md`, and `wiki/index.md` with `va17`-supported claims and figure links.
  - Marked `sources/va17.md` as processed.
- Decisions:
  - Did not add a design page because the thesis studies rooftop siting for a generic small building-mounted turbine rather than documenting one source-owned turbine design.
  - Did not add a parameter page because the comparison is primarily between candidate sites and building geometries, not a turbine design-parameter sweep in the sense used by `schema/Ingest Source`.
  - Added a new concept page for architectural wind turbines because the source's main reusable idea is roof-edge siting with Venturi acceleration.
- Open:
  - `sources/va17.md` is readable and complete enough to ingest, but a few figure captions still reflect OCR artifacts from the scan, especially Figures 1, 3, and 5.

### 2026-07-03 — Rename va17 PDF to va16 and ingest panel-method span/solidity study

- Task: rename `PDFs/va17_raw.pdf` to `PDFs/va16_raw.pdf`, convert it into `sources/va16.md`, and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Renamed `PDFs/va17_raw.pdf` to `PDFs/va16_raw.pdf` because `va16` was unused and the user explicitly requested the source-number correction.
  - Created `sources/va16.md` with source frontmatter, section structure, figure links `va16-fig1` through `va16-fig12`, table screenshots, and a nomenclature screenshot.
  - Added `wiki/summaries/va16-summary.md`.
  - Added `wiki/methods/Panel Method.md`.
  - Added parameter pages `va16 Solidity` and `va16 Span-to-Diameter Ratio (H-D)`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/H-rotor Wake Aerodynamics.md`, and `wiki/index.md` with `va16`-supported claims and links.
  - Marked `sources/va16.md` as processed and re-ran source-backlink and Obsidian-link verification checks.
- Decisions:
  - Added a new method page because the paper is specifically about a three-dimensional panel method with a free-vortex wake rather than a CFD workflow.
  - Added two parameter pages because the paper directly studies solidity and span-to-diameter ratio as the main design variables.
  - Did not add a design page because the paper uses a generic straight-bladed reference turbine for a parameter sweep rather than introducing a reusable named turbine design.
- Open:
  - `sources/va16.md` remains readable but still has some OCR compression and duplicated caption/table text around the article-info and figures.

### 2026-07-03 — Convert and ingest va15 H-Darrieus startup parameter study

- Task: convert `PDFs/va15_raw.pdf` into `sources/va15.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va15.md` with source frontmatter, section structure, linked figure images `va15-fig1` through `va15-fig20`, and screenshots for the two tables plus nomenclature.
  - Added `wiki/summaries/va15-summary.md`.
  - Added five source-specific parameter pages: `va15 Solidity`, `va15 Blade Profile`, `va15 Blade Pitch Angle`, `va15 Blade Surface Roughness`, and `va15 Blade Aspect Ratio`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/methods/Wind Tunnel Testing.md`, `wiki/concepts/CFD and Validation.md`, and `wiki/index.md` with `va15`-supported claims and links.
  - Marked `sources/va15.md` as processed and re-ran source-backlink and Obsidian-link verification checks.
- Decisions:
  - Added five parameter pages because the paper is explicitly organized around independent design variables rather than a single stable turbine design.
  - Did not add a design page because the paper is a multi-parameter experimental rig study, not one canonical single-source design note.
  - Preserved the tension between `va15` and older startup claims from `vj4`/`va14` by updating shared concept pages instead of overwriting those source-specific parameter notes.
- Open:
  - `sources/va15.md` is usable but still contains some OCR/header artifacts and duplicated caption text in places; the wiki claims added here were limited to the clear source-supported findings.

### 2026-07-03 — Convert and ingest va14 solidity and blade-count study

- Task: convert `PDFs/va14_raw.pdf` into `sources/va14.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va14.md` with source frontmatter, linked figure images `va14-fig1` through `va14-fig20`, and added screenshots for symbol-heavy tables and nomenclature.
  - Added `wiki/summaries/va14-summary.md`.
  - Added parameter pages `va14 Solidity` and `va14 Blade Number`.
  - Updated `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/H-VAWT.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/H-rotor Wake Aerodynamics.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, and `wiki/index.md` with `va14`-supported claims and links.
  - Marked `sources/va14.md` as processed and re-ran source-backlink and Obsidian-link verification checks.
- Decisions:
  - Added source-specific parameter pages because the paper directly studies solidity and blade number as the main design variables.
  - Did not add a design page because the paper is a characterization study around a reference H-type turbine rather than a distinct single-source turbine design note.
  - Treated the urban low-solidity recommendation as a post-start constant-speed design recommendation, not a startup recommendation.
- Open:
  - `sources/va14.md` is usable but still contains some compressed OCR text around the article-info/abstract area and the long references section.

### 2026-07-03 — Convert and ingest va13 urban-building VAWT study

- Task: convert `PDFs/va13_raw.pdf` into `sources/va13.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va13.md` with source frontmatter, cleaned section structure, and linked screenshots for Figures 1-9 plus Tables 1-2.
  - Added `wiki/summaries/va13-summary.md`.
  - Added `wiki/methods/Payback Period Analysis.md`.
  - Added three single-source design pages: `va13 Helical-Type VAWT`, `va13 Ice-Type VAWT`, and `va13 Combined Helical-IceWind VAWT`.
  - Updated `wiki/concepts/Hybrid VAWT.md`, `wiki/concepts/Economic Viability of VAWTs.md`, `wiki/concepts/Urban Wind Conditions.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, and `wiki/index.md` with `va13`-supported claims and links.
  - Marked `sources/va13.md` as processed and re-ran source-backlink and Obsidian-link verification checks.
- Decisions:
  - Added design pages because the paper compares three explicit named rooftop turbine cases with case-specific geometry and performance.
  - Did not add parameter pages because most changed values in `va13` are bundled whole-design differences rather than isolated single-parameter studies.
  - Left cut-in and cut-out fields blank on the design pages because Table 1 appears internally inconsistent on those values and the source was not clear enough to trust those fields.
- Open:
  - `sources/va13.md` is readable and source-grounded, but still contains some light extraction artifacts such as duplicated caption text after inserted images and compact equation formatting in the payback section.

### 2026-07-03 — Improve readability of va11 and va12 source notes

- Task: make `sources/va11.md` and `sources/va12.md` more readable without changing the source wording or adding commentary.
- Actions:
  - Replaced `va11` nomenclature and the unreadable wake-model equation blocks with screenshots extracted from the PDF.
  - Cleaned the most disruptive extraction noise in `va12`, including duplicate title/front-matter text and repeated page-header/page-number artifacts.
  - Replaced unreadable symbolic blocks in `va12` with screenshots for the orientation equation, normalization equation, reduced-frequency expression, and tracer-response equations.
  - Added source-structure headings where the converted text already had section labels so the notes are easier to navigate.
- Decisions:
  - Preserved the paper wording and used screenshots only where the symbol-heavy content was not reliably readable as plain text.
  - Kept the cleanup focused on readability rather than re-converting either paper from scratch.
- Open:
  - Both converted notes still contain some OCR/PDF artifacts in plain-text sections, but the worst symbol-heavy failures are now represented directly from the source pages.

### 2026-07-03 — Convert and ingest va12 interacting-VAWT array study

- Task: convert `PDFs/va12_raw.pdf` into `sources/va12.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va12.md` with source frontmatter, extracted text, and links to `images/va12-fig1.jpg` through `images/va12-fig15.jpg`.
  - Added `wiki/summaries/va12-summary.md`.
  - Added `wiki/methods/3D Particle Tracking Velocimetry.md`.
  - Added parameter pages for the three studied array knobs: `va12 Array Angle in Paired VAWT Arrays`, `va12 Turbine Spacing in Paired VAWT Arrays`, and `va12 Relative Rotational Orientation in Paired VAWT Arrays`.
  - Updated `wiki/concepts/H-rotor Wake Aerodynamics.md`, `wiki/concepts/VAWT.md`, `wiki/methods/Wind Tunnel Testing.md`, `wiki/methods/PIV Testing.md`, and `wiki/index.md` with `va12`-supported claims and links.
  - Marked `sources/va12.md` as processed and re-ran source-backlink and Obsidian-link verification checks.
- Decisions:
  - Added source-specific parameter pages because `va12` directly studies array angle, spacing, and relative rotational orientation as the paper's main controlled design variables.
  - Did not add a new design page because the paper is primarily an interaction and parameter study on a paired test setup rather than a reusable single-source turbine design note.
- Open:
  - `sources/va12.md` remains a lightly cleaned extraction and still contains some PDF/OCR formatting artifacts, especially in equations and repeated page text; the wiki claims added here were kept to source points that remained clear despite those artifacts.

### 2026-07-03 — Convert and ingest va11 wake-aerodynamics review

- Task: convert `PDFs/va11_raw.pdf` into `sources/va11.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Created `sources/va11.md` with source frontmatter, extracted text, and links to `images/va11-fig1.jpg` through `images/va11-fig39.jpg`.
  - Added `wiki/summaries/va11-summary.md`.
  - Added `wiki/concepts/H-rotor Wake Aerodynamics.md` and `wiki/methods/PIV Testing.md`.
  - Updated `wiki/concepts/H-VAWT.md`, `wiki/concepts/Straight-bladed Darrieus.md`, `wiki/concepts/Atmospheric Turbulence.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/CFD and Validation.md`, `wiki/methods/CFD.md`, and `wiki/methods/Wind Tunnel Testing.md` with `va11`-supported claims and figure links.
  - Updated `wiki/index.md` and marked `sources/va11.md` as processed.
  - Re-ran source-backlink and Obsidian-link verification checks on the changed pages and the wiki as a whole.
- Decisions:
  - Kept the ingest minimal by creating one new wake concept page and one new PIV method page rather than splitting the review into design or parameter pages.
  - Did not create new single-source design or parameter pages because `va11` is a broad review that summarizes many primary studies rather than presenting one source-owned turbine design or one isolated parameter study.
- Open:
  - `sources/va11.md` is readable and source-grounded, but some PDF-extraction artifacts remain in equations and line wrapping; the wiki claims added here were limited to points that were clear despite that formatting noise.

### 2026-07-03 — Convert and ingest va10 CFD review source

- Task: convert `PDFs/va10_raw.pdf` into `sources/va10.md` and ingest it into the wiki according to `schema/Convert PDF to MD` and `schema/Ingest Source`.
- Actions:
  - Recreated `sources/va10.md` with source frontmatter, extracted text, figure captions, and links to `images/va10-fig1.jpg` through `images/va10-fig20.jpg`.
  - Extracted a displayed solidity equation as `images/va10-eq1.jpg` and linked it from the source note.
  - Added `wiki/summaries/va10-summary.md`.
  - Updated `wiki/methods/CFD.md`, `wiki/concepts/CFD and Validation.md`, and `wiki/concepts/Dynamic Stall.md` with `va10`-supported claims and figure links.
  - Updated `wiki/index.md` and marked `sources/va10.md` as processed.
  - Re-ran source-backlink and Obsidian-link verification checks on the edited wiki pages and the wiki as a whole.
- Decisions:
  - Kept the ingest minimal because `va10` is a broad CFD review and the existing wiki already had the right concept and method pages; no new design or parameter pages were added on this pass.
  - Treated `va10` as the current source ID for this 2017 Darrieus-CFD review even though older log entries describe a different, previously removed `va10`; the historical log was preserved and the ID reuse is documented here instead of rewriting past entries.
- Open:
  - The PDF text extraction still contains some two-column ordering artifacts in `sources/va10.md`; the wiki pages added here were grounded conservatively in claims that were clear in the source despite those artifacts.

### 2026-07-03 — Verify source backlinks in wiki properties

- Task: verify that wiki pages include source-note backlinks in their properties for every source they cite, and add any missing links.
- Actions:
  - Audited content pages in `wiki/summaries/`, `wiki/concepts/`, `wiki/methods/`, `wiki/designs/`, and `wiki/parameters/` by comparing body citations against frontmatter source links.
  - Added missing frontmatter source backlinks and corrected `Source_count` values on 10 pages: `Darrieus Turbine`, `Design Checklist`, `Rules of Thumb`, `Savonius Turbine`, `Structures and Loads`, `Turbine Concept Selection`, `VAWT Design Overview`, `VAWT Types`, `CFD`, and `VAWT Aerodynamic Design Parameters`.
  - Re-ran the audit to confirm no remaining cited-source gaps on content pages.
  - Cleaned example-only link syntax in this log so the wiki-wide link verification passes without false unresolved links.
- Decisions:
  - Treated the source-backlink requirement as applying to content pages that use the frontmatter source-properties convention, not to administrative pages like `index`, `evals`, and `learning-log`.
  - Kept the fix minimal by updating only pages whose cited sources were missing from frontmatter, rather than normalizing unrelated metadata.
- Open:
  - If you want the same `Sources` frontmatter convention added to administrative pages as well, that would need a separate schema decision because those pages currently use a different format.

### 2026-07-03 — Normalize Obsidian backlinks across repo documents

- Task: check all document backlinks for Obsidian compatibility and remove any non-functional local Markdown note links or malformed wikilinks.
- Actions:
  - Audited all `.md` files for local Markdown links to other notes, quoted wikilinks, and unresolved wikilinks.
  - Converted local Markdown note links such as source-note path links and other local `.md` references into Obsidian wikilinks.
  - Used aliased wikilinks to retarget stale bare names such as Classical Savonius and Aerodynamic Design Parameters to the current source-prefixed files.
  - Replaced broken references to missing notes such as workshop files and the non-existent `sources/README.md` with plain text so no broken local links remain.
  - Neutralized example-only wikilinks in `resources/Obsidian + Markdown Cheatsheet.md` so they do not appear as broken notes.
- Decisions:
  - Kept external web links in standard Markdown form; only local document links were normalized to Obsidian wikilinks.
  - For concept-style bare links that no longer had matching files after source-prefix renames, used aliased wikilinks to the current canonical notes instead of recreating duplicate pages.
- Open:
  - The repo still references workshop content as plain text because those workshop note files are not present in the workspace.

### 2026-07-03 — Backfill missing design and parameter pages by source

- Task: go through all current `sources/*.md` files and create any missing single-source `wiki/designs/` and `wiki/parameters/` pages required by `schema/Ingest Source`.
- Actions:
  - Audited all source files against the existing `wiki/designs/` and `wiki/parameters/` coverage using the current schema rule that these pages must be source-specific and single-source.
  - Added missing design pages for `HRI2526`, `va1`, `va4`, `va7`, `va8`, and `vj9`.
  - Added missing parameter pages for `va2`, `va7`, `va8`, `va9`, `vj4`, `vj7`, `vj8`, `vj9`, and `vj12`.
  - Updated `wiki/index.md` so all new design and parameter pages are linked from the central map.
- Decisions:
  - Used a conservative threshold for page creation: a new design or parameter page was only added when the source clearly discussed a specific turbine configuration or a specific changed design parameter.
  - Did not add new design or parameter pages for sources that remained review-level or too brief to support a source-specific page without stretching the evidence.
- Open:
  - Some sources such as `va3`, `vj1`, and `vj11` still contain broad review material that could be split more aggressively under a stricter interpretation, but they did not clearly require additional source-specific design or parameter pages on this conservative pass.

### 2026-07-03 — Split legacy multi-source design pages

- Task: audit `wiki/designs/` for old pages that combined multiple sources or multiple turbine configurations, then separate them into single-source design pages.
- Actions:
  - Audited every design page against the current single-source design-page rule.
  - Split the old `vj2 Savonius-Darrieus Hybrid Wind Turbine` coverage into three source-specific design pages: the original middle-Savonius layout, the shaftless middle-Savonius variant, and the split-Savonius outside-Darrieus variant.
  - Split the old contra-rotating design coverage by keeping `vj8 Contra-rotating VAWT` specific to the `vj8` optimization study and adding `vj12 Counter-rotating Dual-Rotor VAWT` for the separate `vj12` review design.
  - Removed cross-source claims from the legacy HRI design pages `HRI2526 Eggbeater Darrieus`, `HRI2526 Troposkien Darrieus`, `HRI2526 Outer Darrieus with Inner Savonius`, and `HRI2526 Helical Hybrid` so each now cites only `sources/HRI2526.md`.
  - Updated `wiki/index.md`, relevant summary pages, and related links from concept/parameter pages to point to the new design pages.
- Decisions:
  - Treated the two optimized `vj2` configurations as separate turbine designs because the paper materially changes rotor structure and placement, not just an abstract parameter value.
  - Treated the extra `vj4`, `n2`, and `vj8` citations on the HRI pages as cleanup issues rather than new design pages, because those pages were still describing a single HRI concept each.
- Open:
  - Some older HRI design pages that were already single-source still use older frontmatter formatting and may be worth normalizing later for consistency.

### 2026-07-03 — Link wiki images to original source captions

- Task: update every existing wiki image so it displays the original figure caption and links back to the source Markdown file.
- Actions:
  - Audited all image embeds across `wiki/` and matched each image filename to its source caption in `sources/*.md`.
  - Added an `Original caption:` line below each wiki image that links to the corresponding source file.
  - Replaced stale or paraphrased image alt text with a neutral image label while moving the exact source caption into visible page text, including cases where the surrounding wiki text had the wrong figure number.
  - Used explicit caption recovery for `HRI2526` figures where the converted source still contains placeholder extracted-image labels near the top of the file.
- Decisions:
  - Linked each image back to its source Markdown file rather than inventing deep anchors, because the converted sources do not have stable figure anchors.
  - Preserved existing page structure and figure selection, limiting the change to caption accuracy and source traceability.
- Open:
  - Some converted source captions still contain OCR/PDF extraction artifacts such as unusual symbols; those were preserved rather than silently rewritten.

### 2026-07-03 — Rename parameter pages to include source prefixes

- Task: rename every file in `wiki/parameters/` so the filename includes the source, for example `va9 EN0005 Blade Profile.md`.
- Actions:
  - Renamed all 7 files in `wiki/parameters/` to source-prefixed names using each page's source metadata or primary source.
  - Updated the parameter-section entries in `wiki/index.md` to the new filenames.
  - Updated the wiki links that intentionally target parameter pages so they now point to the source-prefixed names.
- Decisions:
  - For single-source pages, used the exact source prefix such as `va3`, `va9`, and `vj2`.
  - For the older multi-source page `Aerodynamic Design Parameters`, used `HRI2526` as the primary source prefix, matching the design-page rename approach.
- Open:
  - Bare links like `[[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]]` still remain where they intentionally refer to the concept page rather than a source-specific parameter page.

### 2026-07-03 — Rename design pages to include source prefixes

- Task: rename every file in `wiki/designs/` so the filename includes the source, for example `va9 EN0005 Self-start Darrieus VAWT.md`.
- Actions:
  - Renamed all 22 files in `wiki/designs/` to source-prefixed names using the page's source metadata or primary source.
  - Updated design-section entries in `wiki/index.md` to the new filenames.
  - Updated the wiki links that intentionally target design pages so they now point to the source-prefixed names.
- Decisions:
  - For single-source pages, used that exact source prefix such as `va3`, `va5`, `va9`, and `vj2`.
  - For older multi-source design pages, used the primary design source rather than every supporting source, for example `HRI2526` for the hybrid-family variants and `vj8` for `Contra-rotating VAWT`.
- Open:
  - Some old links that previously used ambiguous bare names now resolve to concept pages instead of design pages by default; this is intentional unless a page explicitly meant the design document.

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
  - Added missing summary-page frontmatter backlinks so older source summaries now include source-note wikilinks in `Sources` metadata.
  - Converted remaining wiki-to-wiki Markdown links in `wiki/index.md` and `wiki/learning-log.md` to Obsidian wikilinks.
  - Left single-source `Source` properties, claim citations like `sources/va9.md`, and non-wiki Markdown links unchanged because those already match the schema or serve a different purpose.
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

### 2026-07-06 — Rebuild vj16 with figures

Task: Re-ingest `vj16.pdf` one source at a time, this time keeping the paper structure and extracting the figures.

Actions:
- Created `sources/vj16.md` from the PDF text layer with the paper headings exposed as Markdown sections.
- Extracted 12 figure images to `images/vj16-fig1.jpg` through `images/vj16-fig12.jpg`.
- Added the figure links and captions to the source note.
- Created `wiki/summaries/vj16-summary.md`.
- Created `wiki/methods/PSO-ANFIS Forecasting.md`.
- Updated `wiki/index.md` to point to the new `vj16` pages.

Decisions:
- Kept `vj16` isolated so the ingest stays one source at a time.
- Used rendered crops for the vector figures and direct extraction for the embedded image figures.
- Left unrelated leftover files from the earlier aborted ingest alone.

Open:
- `vj15` and `vj17` remain for separate one-at-a-time passes later.

### 2026-07-06 - Expand parameter pages across wiki

- Task: Review all pages in `wiki/parameters/` and add more detail according to `schema/Ingest Source`.
- What I did:
  - Audited the full `wiki/parameters/` folder against the current parameter-page schema.
  - Expanded the thinner parameter pages with more source-specific compared cases, quantitative results, tradeoffs, and mechanism explanations.
  - Added helpful figures to several pages where they directly supported the new detail, including `va8 Blade-to-Horizontal-Beam Angle`, `va8 Asymmetrical Blade Profile`, and `vj9 Savonius Blade Shape`.
  - Normalized remaining quoted `Tags: "#parameters"` front matter to `Tags: #parameters` across the folder.
  - Left already-detailed parameter pages largely unchanged when they already met the current depth standard.
- Pages materially expanded:
  - `vj4 Airfoil Camber Line`
  - `vj4 Blade Axis Inclination`
  - `vj4 Blade Number`
  - `vj7 Blade Material`
  - `va2 H-VAWT Airfoil Geometry`
  - `va8 Asymmetrical Blade Profile`
  - `va8 Blade-to-Horizontal-Beam Angle`
  - `va9 Blade-End Position`
  - `vj9 Savonius Blade Shape`
  - `vj12 Savonius Aspect Ratio`
  - `vj12 Savonius Number of Stages`
  - `vj12 Savonius End Plates`
  - `vj12 Savonius Overlap Ratio`
  - `vj12 Savonius Blade Count`
  - `vj12 Savonius Inner Blades`
  - `vj12 Savonius Twist Angle`
  - `vj8 Airfoil Relative Thickness`
  - `vj8 Included Angle Between Rotors`
  - `vj8 Rotor Spacing`
  - `va15 Blade Aspect Ratio`
  - `va15 Blade Pitch Angle`
  - `va15 Solidity`
  - `va16 Solidity`
  - `va16 Span-to-Diameter Ratio (H-D)`
- Structural cleanups:
  - Normalized `Tags: #parameters` on remaining schema-compliant pages that still used quoted tag strings, including `va3`, `va9`, `vj2`, and `vj8` parameter pages.
  - Verified no local Markdown `.md` links were introduced in `wiki/parameters/`.
- Decisions:
  - Focused edits on pages that were materially thin under the new schema, rather than rewriting pages that already had clear parameter change descriptions, outcomes, and source figures.
  - Kept source-backed caveats when the reviewed paper was itself a literature review or when outcomes varied across cited studies.
- Open:
  - `wiki/concepts/VAWT Aerodynamic Design Parameters.md` is a multi-source overview page and now lives under `wiki/concepts/`, which better matches its cross-source concept role.

### 2026-07-06 - Move aerodynamic-parameters overview into concepts

- Task: Rename the legacy `HRI2526 Aerodynamic Design Parameters` overview page, move it into `wiki/concepts/`, and update its front matter and tags accordingly.
- What I did:
  - Moved `wiki/parameters/HRI2526 Aerodynamic Design Parameters.md` to `wiki/concepts/VAWT Aerodynamic Design Parameters.md`.
  - Renamed the note to reflect that it is a cross-source VAWT concept page rather than an `HRI2526`-specific parameter page.
  - Updated the front matter to the concept-page schema with multi-source backlinks and changed the tag to `concepts`.
  - Updated `wiki/index.md` and all live wikilinks that referenced the old note name so the rename does not leave broken links.
- Decisions:
  - Kept the page content largely unchanged because the existing synthesis already matches a concept/overview role; the problem was classification, not substance.
- Open:
  - None.

### 2026-07-06 - Expand va4 parameter detail

- Task: Revisit `wiki/parameters/va4 Tip Speed Ratio.md` and add more detail following `schema/Ingest Source`.
- What I did:
  - Expanded the page with more specific source-backed detail on the studied TSR set, the reported optimum at `TSR 1.8`, the low-TSR and high-TSR tradeoffs, and the mechanisms the paper gives for those tradeoffs.
  - Added two additional related figures, `va4-fig7` and `va4-fig19`, to support the torque-fluctuation and wake-interaction discussion.
  - Split the explanation into more detailed sections so the page better reflects the schema requirement to include high detail and specific results where helpful.
- Decisions:
  - Kept `Target: increase Cp` and `Outcome: significant positive effect` unchanged because the new detail reinforces the same high-level interpretation rather than changing it.
- Open:
  - None.

### 2026-07-06 - Update va4 and va7 parameter pages

- Task: Re-read `schema/Ingest Source` and review the parameter pages for `va4` and `va7`.
- What I did:
  - Updated `wiki/parameters/va7 Helix Angle.md` to match the current parameter-page schema, including normalized `Tags: #parameters` front matter.
  - Expanded the `va7` page with more source-specific detail on the compared helix angles, the performance peak at `60 degrees`, and the torque-ripple / `Cp`-standard-deviation tradeoff.
  - Added related source figures to the `va7` parameter page.
  - Created `wiki/parameters/va4 Tip Speed Ratio.md` because `sources/va4.md` explicitly studies TSR as the varying parameter across the paper and the updated ingest instructions say to create a source-specific page for each parameter studied in each paper.
  - Added related `va4` figures and updated `wiki/index.md` to include `[[va4 Tip Speed Ratio]]`.
  - Verified the affected parameter pages contain no quoted `Tags` front matter and no local Markdown `.md` links.
- Decisions:
  - Used `Target: reduce torque ripple` and `Outcome: significant positive effect` for `va7 Helix Angle` because the clearest source-backed design benefit is the strong reduction in cyclic variation as helix angle increases, even though peak power is best at the lower 60 degree case.
  - Used `Target: increase Cp` and `Outcome: significant positive effect` for `va4 Tip Speed Ratio` because the paper frames TSR selection as a major determinant of power output and identifies an optimized TSR near `1.8` for both higher power output and more stable supply in the studied case.
- Open:
  - None.

### 2026-07-06 - Correct Turby whole-turbine rating fields

- Task: Re-check whether populated design-page properties represent whole-turbine data rather than component-level data, and correct the Turby page.
- What I did:
  - Audited the populated design-page rating fields that were most likely to be confused with generator or power-electronics values.
  - Updated `wiki/designs/va3 Turby Wind Turbine.md` so the front matter uses the turbine's reported rated point: `Rated speed (m/s): 14` and `Rated power (W): 2500`.
- Decisions:
  - Treated the separate `Peak power: 3.0 kW` note on the Turby page as not appropriate for the schema's `Rated power (W)` field because `sources/va3.md` explicitly reports rated power as `2.5 kW at 14 m/s`.
  - Left other audited populated pages unchanged where the page body explicitly reports the metric for the turbine as a whole, even if the same page also mentions generator hardware.
- Open:
  - None.

### 2026-07-06 - Refresh all design-page front matter to current schema

- Task: Re-read `schema/Ingest Source` and update every page in `wiki/designs/` to the current design-page front matter format.
- What I did:
  - Normalized all 38 design pages to the latest required keys: `max Cp (1-4 m/s)`, `max Cp (4-8 m/s)`, `Efficiency (%)`, `max TSR (1-4 m/s)`, `max TSR (4-8 m/s)`, `Swept area (m^2)`, `Cut-in speed (m/s)`, `Cut-out speed (m/s)`, `max starting torque (Nm), (0-3 m/s)`, `Rated speed (m/s)`, and `Rated power (W)`.
  - Replaced older free-text keys such as `Cp`, `TSR`, `Starting torque`, and legacy quoted `Tags` values across the entire `wiki/designs/` folder.
  - Added the new `Cut-out speed (m/s)` field to all design pages, including the already-updated `va3` and `va9` pages.
  - Converted populated front matter values to numeric-only entries in the requested units.
  - Populated source-backed values where the existing design pages and their cited source material supported them, including swept-area calculations from rotor height times diameter where available.
  - Verified there are no remaining old design-frontmatter keys in `wiki/designs/`, every design page now includes `Cut-out speed (m/s)`, and no local Markdown `.md` links were introduced.
- Decisions:
  - Left fields blank whenever the page/source did not clearly provide a single compliant numeric value for the schema field.
  - For `va13` rooftop designs, left cut-in and cut-out blank because the source values around those limits were ambiguous in the existing page/source notes, while keeping the rated wind speed and maximum power values that were clearly supported.
  - For `va3 Turby Wind Turbine`, kept `Rated power (W): 3000` as the maximum reported output, added `Cut-out speed (m/s): 14`, and left `Rated speed (m/s)` blank because the page reports `2.5 kW at 14 m/s` but does not state the wind speed at which the separate `3.0 kW` peak occurs.
  - For pages that only discussed design concepts or comparative geometries without explicit operating metrics, kept most numeric fields blank rather than inferring values.
- Open:
  - Some design pages remain sparse because the underlying source pages do not report the full schema metrics; filling those gaps would require either more detailed source extraction or leaving them intentionally blank.

### 2026-07-06 - Update va9 design front matter

- Task: Re-read `schema/Ingest Source` and update the `va9` design page front matter to match the current design-page schema.
- What I did:
  - Updated `wiki/designs/va9 EN0005 Self-start Darrieus VAWT.md` to use the exact required properties keys: `max Cp (1-4 m/s)`, `max Cp (4-8 m/s)`, `Efficiency (%)`, `max TSR (1-4 m/s)`, `max TSR (4-8 m/s)`, `Swept area (m^2)`, `Cut-in speed (m/s)`, `max starting torque (Nm), (0-3 m/s)`, `Rated speed (m/s)`, and `Rated power (W)`.
  - Normalized populated values to numeric-only entries.
  - Calculated swept area as rotor height times rotor diameter using the source dimensions `0.48 m` and `0.346 m`, giving `0.16608 m^2`.
  - Used the field-test torque table to populate `max Cp (1-4 m/s): 0.416`, `Cut-in speed (m/s): 1.25`, and `max starting torque (Nm), (0-3 m/s): 0.156`.
  - Verified the page no longer uses the old front matter keys and contains no local Markdown `.md` links.
- Decisions:
  - Left both TSR fields blank because the page does not report a specific maximum TSR value tied to the required `1-4 m/s` or `4-8 m/s` ranges.
  - Left `Efficiency (%)` blank because the source reports power coefficient rather than a separate turbine efficiency figure for this design page.
  - Left `Rated speed (m/s)` and `Rated power (W)` blank because the source does not report a maximum power output value or the wind speed at which that maximum occurs.
- Open:
  - Other non-`va3` and non-`va9` design pages may still need the same schema-alignment pass.

### 2026-07-06 - Correct Turby rated speed

- Task: Correct the `Rated speed (m/s)` field on `wiki/designs/va3 Turby Wind Turbine.md`.
- What I did:
  - Set `Rated speed (m/s): 14` on the Turby page to match the source statement that rated power is reported at `14 m/s`.
- Decisions:
  - Treated the source's reported rated-power condition as the appropriate rated-speed value for the front matter.
- Open:
  - None.

### 2026-07-06 - Revisit va3 front matter after schema update

- Task: Re-check `va3` design pages after further changes to `schema/Ingest Source` and update their front matter accordingly.
- What I did:
  - Re-read the ingest schema and applied the latest design-page front matter requirements across all `va3` design pages.
  - Renamed the final two design metrics to `Rated speed (m/s)` and `Rated power (W)` to match the updated schema.
  - Reinterpreted rated speed as wind speed at maximum power output, not rotor rpm, and updated values accordingly.
  - Calculated and populated swept area where rotor height and diameter were available from the source text, including the QR5, Turby, and the example turbines in the counter-rotating array page.
  - Updated maximum-power fields where the source explicitly reported a larger peak output than the prior rated-power figure, such as `va3 Turby Wind Turbine` and `va3 Venturi Wind Turbine`.
  - Verified there are no remaining `Rated speed (rpm)` or `Rated power (w)` fields on `va3` design pages and no local Markdown `.md` links in those pages.
- Decisions:
  - Left `Rated speed (m/s)` blank when the source gave a maximum power value but not the wind speed where that maximum occurs, such as the Aerogenerator concept and Turby peak-power note.
  - Kept `Rated speed (m/s): 10` and `Rated power (W):` blank on the Solwind page because the source states the wind speed for rated output but does not report the output magnitude.
  - Kept fields blank where the source still did not provide a single compliant numeric value.
- Open:
  - This pass only updated the `va3` design set; other design pages may still need the same schema refresh.

### 2026-07-06 - Update va3 design properties tables

- Task: Update the `va3` design pages to follow the revised properties-table instructions in `schema/Ingest Source`.
- What I did:
  - Reviewed `schema/Ingest Source` and applied the exact design-page front matter keys now required for source-specific design pages.
  - Updated all ten `va3` design pages in `wiki/designs/` to use the normalized properties table fields: `max Cp (1-4 m/s)`, `max Cp (4-8 m/s)`, `Efficiency (%)`, `max TSR (1-4 m/s)`, `max TSR (4-8 m/s)`, `Swept area (m^2)`, `Cut-in speed (m/s)`, `max starting torque (Nm), (0-3 m/s)`, `Rated speed (rpm)`, and `Rated power (w)`.
  - Converted populated values to plain numbers in the required units and left fields blank where `sources/va3.md` did not clearly report a single compliant value.
  - Verified that the updated `va3` design pages contain no local Markdown `.md` links and no remaining uses of the old property names.
- Decisions:
  - Left several front matter fields blank where the source only gave descriptive text, ranges, non-matching operating conditions, or values that were not clearly the requested metric.
  - Used `3.7` m/s for Solwind cut-in because the source distinguishes startup at `1.5` m/s from power production beginning at `3.7` m/s.
  - Left rated-speed fields blank when the source only reported maximum rpm or a range rather than a single rated rpm.
- Open:
  - Other design pages outside the `va3` set still appear to use the older properties layout and may need the same schema-alignment pass later.

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

### 2026-07-06 - Convert and ingest vj15 harmonic pitch study

- Task: convert `PDFs/vj15.pdf` into `sources/vj15.md` and ingest it into the wiki according to the repository source-ingest workflow.
- Actions:
  - Extracted the 12 paper figures from `vj15` into `images/vj15-fig1.jpg` through `images/vj15-fig12.jpg`.
  - Created `sources/vj15.md` with source frontmatter, section structure, and inline figure links placed at the matching captions.
  - Added `wiki/summaries/vj15-summary.md`.
  - Added the source-specific parameter page `vj15 Pitch Amplitude`.
  - Updated `wiki/concepts/Darrieus Turbine.md`, `wiki/concepts/Dynamic Stall.md`, `wiki/concepts/Optimization.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/H-VAWT.md`, and `wiki/index.md` with `vj15`-supported claims and links.
  - Marked `sources/vj15.md` as processed.
- Decisions:
  - Treated harmonic pitch amplitude as the main source-specific parameter because it is the clearest reusable knob the paper varies.
  - Kept the new supporting pages minimal and let the existing Darrieus, dynamic-stall, optimization, and CFD pages absorb the broader claims.
- Open:
  - The source note is written and figure-linked; the next source can be ingested the same way.

### 2026-07-06 - Revise vj15 source note to be paper-like

- Task: correct `sources/vj15.md` because the first pass read too much like a summary instead of a source conversion.
- Actions:
  - Reworked the abstract, introduction, methodology, results, and conclusions into a more paper-faithful markdown transcription style.
  - Kept the inline figure links and source metadata in place.
- Decision:
  - Preserved the existing wiki links and parameter pages; only the source note needed to be made more source-like.
- Open:
  - `sources/vj15.md` now reads more like a markdown conversion of the paper text.

### 2026-07-06 - Convert and ingest vj17 Savonius airfoil optimization study

- Task: convert `PDFs/vj17.pdf` into `sources/vj17.md` and ingest it into the wiki according to the repository source-ingest workflow.
- Actions:
  - Extracted the 14 paper figures from `vj17` into `images/vj17-fig1.jpg` through `images/vj17-fig14.jpg`.
  - Created `sources/vj17.md` with source frontmatter, paper-ordered sections, inline figure links, and tables for the reported optimization data.
  - Added `wiki/summaries/vj17-summary.md`.
  - Added method pages `Discrete Vortex Method` and `Salp Swarm Algorithm`.
  - Added the design page `vj17 Airfoil-Based Savonius Wind Turbine`.
  - Updated `wiki/concepts/Savonius Turbine.md`, `wiki/concepts/Optimization.md`, `wiki/concepts/CFD and Validation.md`, `wiki/concepts/Wind Turbine Parameters.md`, `wiki/concepts/VAWT Aerodynamic Design Parameters.md`, `wiki/methods/CST Parameterization.md`, and `wiki/index.md` with `vj17`-supported claims and links.
  - Marked `sources/vj17.md` as processed.
- Decisions:
  - Treated DVM, CST, and SSA as reusable methods worth their own pages because the paper explicitly couples them into a workflow.
  - Kept the design page focused on the optimized airfoil-based Savonius rotor rather than inventing a broader design family.
- Open:
  - `sources/vj17.md` is converted and figure-linked; the wiki map now includes the new source, method, and design pages.

### 2026-07-08 - Convert and ingest va28 raw PDF

- Task: convert `PDFs/va28_raw.pdf` into `sources/va28.md` and ingest it into the wiki according to the repository source-ingest workflow.
- Actions:
  - Extracted the paper figures into `images/va28-fig1.jpg` through `images/va28-fig8.jpg` and added one displayed equation crop as `images/va28-eq1.jpg`.
  - Created `sources/va28.md` with source frontmatter, cleaned section structure, figure captions, inline image links, one equation image link, and Markdown tables for the reported scenario and end-of-life data.
  - Added `wiki/summaries/va28-summary.md`.
  - Added the source-specific design page `va28 Windkop 5 kW H-Darrieus VAWT`.
  - Updated `wiki/index.md` to include the new summary and design pages.
  - Marked `sources/va28.md` as processed.
- Decisions:
  - Kept the wiki changes minimal because `va28_raw.pdf` is a duplicate upload of the same Windkop/LCA paper already present as `sources/vj14.md`.
  - Did not create new concept, method, or parameter pages because the source content is already represented in existing wiki pages from `vj14` and did not add source-distinct findings.
- Open:
  - `va28` now exists as a separate converted and ingested source file, but its content substantially overlaps `vj14`.
