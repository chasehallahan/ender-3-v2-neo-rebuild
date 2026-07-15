# Migration Plan

## Current State

- The original OneDrive project was copied into this repo under `CAD/`.
- SolidWorks temp files (`~$*`) and local agent folders were excluded from the copy.
- The copied top-level assembly was renamed from `Ender3V2NeoMain.SLDASM` to `E3V2_Rebuild.SLDASM`.
- Existing CAD subfolders were preserved for now to reduce reference breakage risk.

## Target Direction

Move toward this split:

```text
CAD/
  Design/
    Frame/
    Motion/
      X_Axis/
      Y_Axis/
      Z_Axis/
    Toolhead/
    Bed/
    Electronics/
    Wiring/
    Filament_Path/
    Enclosure/

  Library/
    Fasteners/
    Extrusions/
    Linear_Rails/
    Bearings_Bushings/
    Motors/
    Electronics/
    Belts_Pulleys/
    Heat_Set_Inserts/
    Springs/
    Fans/
    Sensors/
    Stock_Creality/
```

## Cleanup Sequence

1. Confirm `CAD/E3V2_Rebuild.SLDASM` opens from the new repo location.
2. Run SolidWorks `File > Find References` on the top-level assembly and save a reference report.
3. Identify any references that still point outside `C:\Code\Repos\Personal\ender-3-v2-neo-rebuild`.
4. Move reusable library components in small batches.
5. Move design-specific assemblies and parts by subsystem.
6. Rename files only after their destination category is clear.
7. Re-open the top-level assembly after each batch and resolve references immediately.

## Known Red Flags

- Duplicated library-ish files exist in multiple subsystem folders.
- Imported assemblies have names like `.iges.SLDPRT` and `.SLDASM.SLDASM`.
- Some files use spaces, punctuation, and temporary names that should be cleaned up later.
- The previous `.git` folder in OneDrive was invalid and was not copied.
