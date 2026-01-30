# Pre-Assembly Verification Checklist

---

## Purpose

This checklist is a final "preflight" verification to be performed before sending a design package to a contract manufacturer (CM) for assembly. Its goal is to catch common errors and ambiguities that lead to production delays, holds, and incorrect builds.

---

## 1. Bill of Materials (BOM) Verification

- [ ] **Completeness**:
  - [ ] All `Item Number` fields are unique and sequential.
  - [ ] All `Quantity` fields are correct for a single board.
  - [ ] All `Reference Designator` fields are populated and match the layout.
  - [ ] All components have a `Manufacturer` and `Manufacturer Part Number (MPN)`.
  - [ ] No "TBD", "N/A", or empty critical fields.
- [ ] **Sourcing**:
  - [ ] Approved Vendor List (AVL) is populated where required.
  - [ ] All parts have confirmed lead times and availability.
  - [ ] Long-lead items are identified and have a mitigation plan.
  - [ ] All parts are active and not NRND (Not Recommended for New Designs) or Obsolete.
- [ ] **Special Instructions**:
  - [ ] `DNP` (Do Not Populate) or `DNI` (Do Not Install) items are clearly marked.
  - [ ] Substitute parts are clearly identified as `Alternate`.
  - [ ] Components requiring special handling (e.g., moisture sensitivity, programming) are noted.
- [ ] **Formatting**:
  - [ ] BOM is provided in an editable format (e.g., `.xlsx`, `.csv`).
  - [ ] File is machine-readable (no merged cells, extra headers, or comments in data fields).

---

## 2. Centroid / Pick-and-Place File Verification

- [ ] **Content**:
  - [ ] All SMT components are present in the file.
  - [ ] No through-hole or non-placed components are in the file.
  - [ ] Reference designators match the BOM and layout.
- [ ] **Formatting**:
  - [ ] File is in a standard format (`.csv`, `.txt`).
  - [ ] Columns for `RefDes`, `Layer`, `X`, `Y`, `Rotation` are present.
  - [ ] Units are clearly specified (mm or mils).
- [ ] **Accuracy**:
  - [ ] Coordinate origin point is defined (e.g., board origin, bottom-left corner).
  - [ ] Rotation for at least one non-symmetrical component on each side is visually verified against the layout. (e.g., a SOT-23 transistor or a polarized capacitor).
  - [ ] Component center (X, Y) is correct.

---

## 3. Assembly Drawing Verification

- [ ] **Clarity**:
  - [ ] Reference designators are legible and do not overlap.
  - [ ] A clear Pin 1 indicator is shown for all ICs and connectors.
  - [ ] Polarity is marked for all polarized components (diodes, electrolytic/tantalum capacitors).
  - [ ] A view of both top and bottom sides is included if double-sided assembly.
- [ ] **Special Instructions**:
  - [ ] Hardware installation instructions are present (e.g., standoffs, screws, heatsinks).
  - [ ] Keep-out areas for conformal coating or underfill are clearly marked.
  - [ ] Instructions for applying labels, adhesives, or masking are included.
  - [ ] Press-fit component requirements are specified.
  - [ ] Wires or other manual attachments are documented with lengths, colors, and locations.

---

## 4. Fabrication Data Sanity Check

- [ ] **Solder Paste Layers**:
  - [ ] Solder paste apertures exist for all SMT pads that will be soldered.
  - [ ] No paste apertures on non-soldered pads (e.g., test points, fiducials unless intended).
  - [ ] Aperture reductions for fine-pitch components are correct.
- [ ] **Silkscreen Layers**:
  - [ ] Silkscreen is clipped away from all pads (no ink on pads).
  - [ ] Polarity and Pin 1 markings are present and unambiguous.
- [ ] **Fiducials**:
  - [ ] At least three global fiducials are present on the board (or panel).
  - [ ] Fiducials are clear of solder mask and copper on all layers.
  - [ ] Local fiducials are present for fine-pitch components if required by the CM.
- [ ] **Board Outline**:
  - [ ] A continuous board outline is present on a mechanical or outline layer.
  - [ ] The outline is free of any other drawing elements.

---

## 5. Final Package Review

- [ ] **File Naming & Organization**:
  - [ ] All files are named according to a consistent convention (e.g., `Project_Rev_Filename.ext`).
  - [ ] All fabrication, assembly, and supporting files are included in a single compressed archive (e.g., `.zip`).
- [ ] **Documentation**:
  - [ ] A `README.txt` or manifest file is included in the archive, listing all files and providing a point of contact.
  - [ ] Any special instructions for the CM are noted in the README.
  - [ ] Stackup information and impedance requirements are included.
- [ ] **Verification**:
  - [ ] The BOM, Centroid, and Assembly Drawing have been cross-checked one last time.

---
*Document Version: 1.0*
