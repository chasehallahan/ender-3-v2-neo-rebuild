# Ender 3 V2 Neo Rebuild

Progressively built SolidWorks model of a heavily modified Creality Ender 3 V2 Neo.

The assembly is being organized as both a working design aid for the physical printer and a public portfolio-quality CAD project. The current top-level assembly is:

```text
CAD/E3V2_Rebuild.SLDASM
```

## Structure

```text
CAD/
  E3V2_Rebuild.SLDASM
  Design/      Printer-specific assemblies and custom or modified parts
  Library/     Reusable purchased, stock, and reference components
  Sandbox/     Temporary design experiments

Docs/
  Measurements/
  Photos/
  Notes/

Exports/
  Print_Files/
    3MF/
    STL/
  STEP/
  DXF/
  Drawings/

Archive/
```

## CAD Organization Rules

- Keep reusable hardware and purchased/reference models in `CAD/Library/`.
- Keep printer-specific parts, modified stock parts, and subsystem assemblies in `CAD/Design/`.
- If a library item is cut, drilled, tapped, or otherwise changed for this printer, save that modified version under `CAD/Design/`.
- Prefer clear `Pascal_Case_With_Underscores` file names.
- Avoid revision suffixes in CAD file names; use Git history and branches for project checkpoints.
- Avoid external references outside this repository.

## Git Notes

SolidWorks files are binary, so this repo uses Git LFS for CAD source and export formats. Git is useful here for checkpoints and publishing, but SolidWorks files cannot be meaningfully line-merged.
