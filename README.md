# Sightline Schematic

Stadium seating bowl designer. Set the field, tiers and side-by-side stand profiles (NEZ/SEZ, East/West), and every riser is solved to your C-value. Exports straight to Revit (via Dynamo) and SketchUp.

**Open the app:** `https://<your-github-username>.github.io/<repo-name>/`

Sightline Schematic runs entirely in the browser. Nothing is uploaded, and there is no server or account. Your work is kept as **projects**: a project name plus its saved options (any mix of sports). The open project stays in your browser between visits; **Save project** writes it to a `.json` file and **Open project** reads it back. Keep the file in Google Drive (or any shared folder) to open it on another computer. In Chrome and Edge, Save writes straight back to the file you opened. Option names and the project name can be edited; double-click an option's name or use the pencil.

## Revit

In Sightline, **Deliver › Models › Revit package (.zip)** downloads `Stadium_Bowl_Revit_R2024.zip`: the bowl workbook (`Stadium_Bowl_Excel_YYYYMMDD_hhmmss.xlsx`), the Dynamo graphs in [`dynamo/`](dynamo/) and the step-by-step guides.

- `Stadium_Bowl_Mass_Revit_R2024.dyn`: the whole bowl in a Generic Model (or Mass) family. Guide: [`guides/Stadium_Bowl_Mass_Revit_R2024_Guide.pdf`](guides/Stadium_Bowl_Mass_Revit_R2024_Guide.pdf)
- `Stadium_Bowl_Profile_R2024.dyn`: one profile family per tier, origin at the point of focus, for sweeps. Guide: [`guides/Stadium_Bowl_Profile_R2024_Guide.pdf`](guides/Stadium_Bowl_Profile_R2024_Guide.pdf)
- `Stadium_Bowl_Aisle_Step_R2024.dyn`: the precast aisle steps, in the project.

Base version: Revit 2024.0 / Dynamo 2.17 (CPython3). No packages needed.

## SketchUp

**Deliver › Models › SketchUp model (.zip)** downloads `Stadium_Bowl_Mass_Sketchup.zip` with one COLLADA file. File › Import › COLLADA. Units are metres; each stand is its own solid. Guide: [`guides/Stadium_Bowl_Mass_Sketchup_Guide.pdf`](guides/Stadium_Bowl_Mass_Sketchup_Guide.pdf)

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole app |
| `vendor/` | SheetJS 0.18.5 and JSZip 3.10, bundled so the app works where CDNs are blocked |
| `dynamo/` | Revit 2024 Dynamo graph |
| `publish.py` | Publishes a new version to this repo (used when Claude updates the app) |

## Changes

- **2026.09.27** Bowl split into tiers x four sides with per-side profiles, bench seating, open corners where sides differ, guard and headroom checks, suite levels, per-stand Revit subcategories. Standalone web version with option backup.
- **2026.09.26** Focal path export; auto bowl-mass Dynamo graph.
