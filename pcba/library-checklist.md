# Library Review Checklist
## Schematic Symbols and PCB Footprints

---

## 1. Symbol Review

### 1.1 Pin Configuration
- [ ] **Pin 1 identified and correctly placed**
- [ ] **Pin 2 identified and correctly placed**
- [ ] All pins present and accounted for
- [ ] Pin numbers match datasheet exactly
- [ ] Pin names match datasheet (or are functionally descriptive)
- [ ] Pin types assigned correctly (input, output, bidirectional, power, passive, open-collector, etc.)
- [ ] Active-low pins marked consistently (overbar, /prefix, _N suffix)
- [ ] No-connect pins marked as NC type
- [ ] Hidden pins exposed for power/ground where appropriate

### 1.2 Symbol Graphics
- [ ] Symbol represents function, not physical package
- [ ] Pins arranged logically by function (not physical pin order)
- [ ] Power pins grouped (typically top for VCC, bottom for GND)
- [ ] Input pins on left side
- [ ] Output pins on right side
- [ ] Bidirectional pins placed logically
- [ ] Internal pull-up/pull-down resistors indicated
- [ ] Internal ESD protection indicated where significant
- [ ] Open-drain/open-collector outputs indicated

### 1.3 Symbol Formatting
- [ ] Pin positions on grid (standard grid, typically 100 mil or 2.54mm)
- [ ] Symbol body on grid
- [ ] Text readable and not overlapping
- [ ] Reference designator field positioned clearly
- [ ] Value field positioned clearly
- [ ] Datasheet link included in symbol properties
- [ ] Symbol description field populated
- [ ] Default reference designator prefix correct (R, C, U, J, etc.)

### 1.4 Multi-Part Symbols
- [ ] All units defined for multi-part components
- [ ] Power pins in separate unit or repeated in all units (design choice documented)
- [ ] Unit swapping rules defined correctly
- [ ] Each unit labeled or identifiable

---

## 2. Footprint Review

### 2.1 Pad Geometry
- [ ] **Pin 1 pad clearly marked**
- [ ] **Pin 2 pad verified in correct position relative to Pin 1**
- [ ] All pad positions match datasheet recommended land pattern
- [ ] Pad sizes match datasheet or IPC-7351 recommendations
- [ ] Pad shapes appropriate (rectangular, rounded, oblong)
- [ ] Thermal pads included where required
- [ ] Thermal pad connected to correct net (usually GND, but verify)
- [ ] Exposed pad has solder paste aperture (with appropriate coverage reduction)
- [ ] Via-in-pad provisions if required (mark for filling/capping)

### 2.2 Dimensional Verification
- [ ] Component body outline matches datasheet dimensions
- [ ] Overall footprint dimensions verified against datasheet
- [ ] Pin pitch verified against datasheet
- [ ] Lead span (toe-to-toe) verified
- [ ] Component height documented in footprint properties
- [ ] Courtyard/assembly outline appropriate for placement

### 2.3 Silkscreen
- [ ] Component outline on silkscreen layer
- [ ] Pin 1 indicator clearly marked
- [ ] Polarity indicator for polarized components (capacitors, diodes, etc.)
- [ ] Reference designator placeholder positioned
- [ ] No silkscreen on pads
- [ ] Silkscreen legible at minimum fab line width

### 2.4 Fabrication Layers
- [ ] Assembly outline defined
- [ ] Courtyard defined (for placement spacing)
- [ ] 3D model associated (if available)
- [ ] Component height defined for 3D/clearance checks

### 2.5 Special Footprint Types

#### Through-Hole Components
- [ ] Hole sizes include plating allowance
- [ ] Annular ring adequate per fab capability
- [ ] Lead forming clearance if needed
- [ ] Square pad for pin 1 (convention)

#### Fine-Pitch Components (< 0.5mm pitch)
- [ ] Pad dimensions per IPC-7351 or manufacturer recommendation
- [ ] Solder paste aperture reduction applied
- [ ] Local fiducials added if required
- [ ] Stencil thickness considerations noted

#### BGA/LGA Components
- [ ] Ball/pad matrix matches datasheet exactly
- [ ] Non-populated positions verified
- [ ] Escape routing feasibility confirmed
- [ ] Solder paste aperture appropriate
- [ ] Via-in-pad requirements defined

#### Connectors
- [ ] Mechanical mounting holes/slots included
- [ ] Mounting pad sizes adequate for retention
- [ ] Shroud/body outline accurate
- [ ] Mating direction indicated
- [ ] Polarization key represented

---

## 3. Symbol-to-Footprint Mapping

### 3.1 Pin Mapping
- [ ] Every symbol pin maps to a footprint pad
- [ ] Pin numbers match between symbol and footprint
- [ ] No-connect pins handled correctly
- [ ] Thermal/exposed pads mapped to correct symbol pin

### 3.2 Verification
- [ ] Forward annotation tested (symbol to footprint)
- [ ] Back annotation tested (footprint to symbol)
- [ ] Test placement in layout confirms correct mapping

---

## 4. Datasheet Verification

### 4.1 Source Documentation
- [ ] Datasheet revision number recorded
- [ ] Datasheet source URL documented
- [ ] Land pattern source identified (datasheet, IPC, application note)
- [ ] Any deviations from datasheet documented with rationale

### 4.2 Package Verification
- [ ] Package type confirmed (SOIC-8, QFN-32, etc.)
- [ ] Package dimensions cross-checked with physical sample if available
- [ ] Variation in package dimensions across manufacturers considered

---

## 5. Library Metadata

### 5.1 Component Properties
- [ ] Manufacturer name populated
- [ ] Manufacturer part number (MPN) populated
- [ ] Description field complete and accurate
- [ ] Datasheet link valid
- [ ] Component category/type assigned
- [ ] Footprint variants listed (if multiple packages available)

### 5.2 Lifecycle and Sourcing
- [ ] Component status noted (active, not recommended for new design, obsolete)
- [ ] Alternate parts cross-referenced
- [ ] Supplier part numbers added where applicable

### 5.3 Library Organization
- [ ] Naming convention followed
- [ ] Component placed in correct library/category
- [ ] Version or revision tracked
- [ ] Creation/modification date recorded
- [ ] Author/owner identified

---

## 6. Quality Assurance

### 6.1 Review Process
- [ ] Symbol reviewed by second person
- [ ] Footprint reviewed by second person
- [ ] First-article verification planned (build before production release)

### 6.2 Test Placement
- [ ] Symbol placed in test schematic
- [ ] Footprint placed in test layout
- [ ] ERC/DRC pass with test placement
- [ ] 3D clearance check performed (if model available)

---

## Common Errors to Catch

| Error Type | Check |
|------------|-------|
| Mirrored footprint | Verify datasheet view (top vs. bottom) |
| Wrong pin 1 location | Trace pin 1 from datasheet through symbol to footprint |
| Metric/imperial mix-up | Verify units throughout |
| Pad too small | Compare to IPC-7351 minimum |
| Missing thermal pad | Check datasheet exposed pad requirements |
| Wrong hole size | Add plating allowance to lead diameter |
| NC pin connected | Verify NC pins have no-connect type |

---

## References and Credits

This checklist incorporates best practices from the following sources:

- **KiCad Library Convention (KLC)** (kicad.org/libraries/klc)
- **IPC-7351B**, Generic Requirements for Surface Mount Design and Land Pattern Standard
- **Henrik Enggaard Hansen**, *PCB Checklist* (pcbchecklist.com)
- **Altium**, *Creating Schematic Library Components* (altium.com)
- **Dave Jones / EEVblog #1129**, *Creating a Nice Readable Schematic*

---

*Document Version: 1.0*
