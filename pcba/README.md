# Electronics Design Review Checklists

A collection of review checklists for electronics hardware development, covering the full lifecycle from schematic capture through manufacturing release.

---

## Contents

| Checklist | Description |
|-----------|-------------|
| [Schematic Review](schematic-checklist.md) | Power architecture, component selection, connectors, signal integrity, protection, EMC, and cross-functional reviews |
| [PCB Layout Review](pcb-checklist.md) | Pre-layout mechanical coordination, placement, routing, DFM, signal integrity, and EMC |
| [Library Review](library-checklist.md) | Schematic symbol and PCB footprint verification |
| [Release Package](release-checklist.md) | Fabrication outputs, assembly outputs, BOM, and documentation for production release |
| [Pre-Assembly Verification](assembly-checklist.md) | Final "preflight" checks for the assembly package to prevent common manufacturing holds |
| [Manufacturing Change Order (MCO)](mco-checklist.md) | Process for component substitutions, process changes, and AML updates |

---

## Usage

These checklists are intended for use during formal design reviews. They can be:

- Printed and marked up during review meetings
- Copied into issue trackers or project management tools
- Adapted to your organization's specific requirements

Each checklist includes cross-functional domain checks to ensure coordination between hardware, firmware, mechanical, manufacturing, and quality teams.

---

## Key Features

- **Connector verification**: Explicit pin 1 and pin 2 verification against mating parts
- **Power architecture**: Includes power tree documentation requirements
- **Pre-layout mechanical gate**: Mechanical drawing import and sign-off before layout begins
- **Mounting hole guidance**: Preference for NPTH with via-stitched annular ring
- **Cross-functional reviews**: Built into each checklist, not an afterthought
- **MCO vs. ECO guidance**: Clear distinction for when to use each change process

---

## Sources and Credits

These checklists incorporate best practices from the following sources:

- **Henrik Enggaard Hansen**, [PCB Checklist](https://pcbchecklist.com) — CC BY-SA 4.0
- **Hank Wallace / JLD Systems**, [Electronics Design Checklist](http://www.jldsystems.com/pdf/Electronics%20Design%20Checklist.pdf)
- **Altium Resources**, [Schematic Review Checklist](https://resources.altium.com/p/schematic-review-checklist)
- **Cadence**, [Electrical Schematic Design Checklist](https://resources.pcb.cadence.com/blog/2024-electrical-schematic-design-checklist)
- **Memfault / Mark Schulte**, [Schematic Review Checklist for Firmware Engineers](https://interrupt.memfault.com/blog/schematic-review-checklist)
- **EMC FastPass**, [EMC Design Review](https://emcfastpass.com/emc-design-review/)
- **Sierra Circuits**, [Files Required for PCB Fabrication and Assembly](https://www.protoexpress.com/kb/fabrication-assembly-files/)
- **Arena Solutions**, [Guide to Manufacturing and Engineering Change Orders](https://www.arenasolutions.com/resources/articles/guide-manufacturing-engineering-change-orders/)
- **KiCad Library Convention (KLC)**, [kicad.org/libraries/klc](https://kicad.org/libraries/klc/)
- **IPC-7351B**, Generic Requirements for Surface Mount Design and Land Pattern Standard
- **Dave Jones / EEVblog #1129**, *Creating a Nice Readable Schematic*

---

## Contributing

These checklists are living documents. If you find errors, have suggestions, or want to add items based on lessons learned, contributions are welcome.

---

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.

This repository incorporates ideas and best practices from various sources credited above. Those original works retain their respective licenses.
