# Design Release Package Checklist

---

## 1. Source Design Files

### 1.1 Schematic Files
- [ ] Native CAD schematic files (project and all sheets)
- [ ] Schematic PDF (all sheets, searchable)
- [ ] Schematic revision matches release identifier
- [ ] All warnings/errors resolved or documented

### 1.2 PCB Layout Files
- [ ] Native CAD layout files (board and libraries)
- [ ] Layout revision matches release identifier
- [ ] DRC clean or all violations documented and accepted
- [ ] LVS (layout versus schematic) verified

### 1.3 Library Files
- [ ] Schematic symbol library (or embedded symbols)
- [ ] Footprint library (or embedded footprints)
- [ ] 3D model files (STEP or equivalent)
- [ ] Library version documentation

---

## 2. Fabrication Outputs

### 2.1 Gerber Files (RS-274X or Gerber X2)
- [ ] Top copper layer
- [ ] Bottom copper layer
- [ ] All inner copper layers
- [ ] Top solder mask
- [ ] Bottom solder mask
- [ ] Top silkscreen
- [ ] Bottom silkscreen (if used)
- [ ] Top solder paste
- [ ] Bottom solder paste
- [ ] Board outline/mechanical layer
- [ ] Gerber files verified in standalone CAM viewer

### 2.2 Drill Files
- [ ] NC drill file (Excellon format)
- [ ] Drill table/drawing
- [ ] Plated vs. non-plated holes distinguished
- [ ] Blind/buried via files (if applicable)
- [ ] Slot routing file (if applicable)

### 2.3 Fabrication Drawing
- [ ] Board dimensions and tolerances
- [ ] Stackup specification
- [ ] Material specification (FR4, Rogers, etc.)
- [ ] Copper weight per layer
- [ ] Finished board thickness
- [ ] Surface finish (HASL, ENIG, OSP, etc.)
- [ ] Solder mask color
- [ ] Silkscreen color
- [ ] Impedance requirements (if controlled impedance)
- [ ] IPC class (Class 2, Class 3)
- [ ] Special requirements (gold fingers, via fill, etc.)
- [ ] Acceptance criteria referenced

### 2.4 Alternative Formats (if required)
- [ ] ODB++ package
- [ ] IPC-2581 file
- [ ] Netlist file (IPC-D-356A for test)

---

## 3. Assembly Outputs

### 3.1 Bill of Materials (BOM)
- [ ] Item number/line number
- [ ] Reference designators (all instances)
- [ ] Quantity per board
- [ ] Manufacturer name
- [ ] Manufacturer part number (MPN)
- [ ] Description
- [ ] Package/footprint type
- [ ] Approved alternates (if any)
- [ ] DNP (Do Not Populate) items clearly marked
- [ ] BOM matches schematic component count
- [ ] BOM in Excel/CSV format (not PDF for production)

### 3.2 Pick-and-Place / Centroid File
- [ ] Reference designator
- [ ] X coordinate
- [ ] Y coordinate
- [ ] Rotation angle
- [ ] Layer (top/bottom)
- [ ] Part number or value
- [ ] Coordinate origin defined
- [ ] Rotation convention documented

### 3.3 Assembly Drawing
- [ ] Top assembly view with reference designators
- [ ] Bottom assembly view (if components on bottom)
- [ ] Component polarity indicators visible
- [ ] Pin 1 orientation indicators
- [ ] Special assembly instructions
- [ ] Variant information (if applicable)
- [ ] Conformal coating boundaries (if applicable)

### 3.4 Stencil Data
- [ ] Top stencil aperture file
- [ ] Bottom stencil aperture file (if required)
- [ ] Stencil thickness specified
- [ ] Aperture modifications documented

---

## 4. Test Outputs

### 4.1 Test Documentation
- [ ] Test point locations/coordinates
- [ ] IPC-D-356A netlist (for ICT/flying probe)
- [ ] Expected test values for key points
- [ ] Test fixture design data (if required)

### 4.2 Functional Test
- [ ] Test procedure document
- [ ] Pass/fail criteria defined
- [ ] Test equipment requirements listed
- [ ] Test firmware or software (if required)

---

## 5. Supporting Documentation

### 5.1 Design Documentation
- [ ] Block diagram
- [ ] Power tree diagram
- [ ] Design specification or requirements document
- [ ] Design review records
- [ ] Known issues or limitations documented

### 5.2 Application Information
- [ ] Operating instructions
- [ ] Interface specifications
- [ ] Firmware/software version compatibility
- [ ] Regulatory compliance information

### 5.3 Revision History
- [ ] Change log from previous revision
- [ ] ECO/ECN reference (if applicable)
- [ ] Changes marked on schematic/layout (redline or comparison)

---

## 6. File Organization and Naming

### 6.1 Naming Convention
- [ ] Project identifier in all filenames
- [ ] Revision/version in all filenames
- [ ] Date or date code in package name
- [ ] No spaces or special characters in filenames

### 6.2 Directory Structure
- [ ] Source files in dedicated folder
- [ ] Fabrication outputs in dedicated folder
- [ ] Assembly outputs in dedicated folder
- [ ] Documentation in dedicated folder
- [ ] README or manifest file included

### 6.3 Archive
- [ ] Complete package archived (ZIP or equivalent)
- [ ] Archive stored in version control or document management system
- [ ] Archive retrievable and verified

---

## 7. Cross-Functional Review

### 7.1 Manufacturing Review
- [ ] Fabrication package reviewed with fab vendor (or per capability matrix)
- [ ] Assembly package reviewed with assembly vendor
- [ ] Lead times confirmed for all components
- [ ] Special process requirements communicated

### 7.2 Quality Review
- [ ] Inspection criteria defined
- [ ] Acceptance/rejection criteria documented
- [ ] First-article inspection requirements specified

### 7.3 Supply Chain Review
- [ ] All BOM components available
- [ ] Long-lead items identified and mitigated
- [ ] Alternates approved and documented
- [ ] EOL/obsolescence risk assessed

### 7.4 Firmware/Software Review
- [ ] Pin assignments confirmed with firmware team
- [ ] Programming interface requirements confirmed
- [ ] Test firmware available (if needed for production test)

---

## 8. Release Approval

### 8.1 Verification
- [ ] All checklist items completed or waived with documented rationale
- [ ] Package contents verified against checklist
- [ ] Files opened and verified in target applications

### 8.2 Authorization
- [ ] Hardware engineer approval
- [ ] Cross-functional stakeholder approvals (as required per company process)
- [ ] Release package assigned unique identifier
- [ ] Release logged in project tracking system

---

## Quick Reference: Minimum Production Release

| Category | Essential Files |
|----------|-----------------|
| Fabrication | Gerbers, drill files, fab drawing |
| Assembly | BOM, pick-and-place, assembly drawing |
| Stencil | Paste layer Gerbers |
| Test | IPC-D-356A netlist (for ICT) |
| Reference | Schematic PDF, revision history |

---

## References and Credits

This checklist incorporates best practices from the following sources:

- **Sierra Circuits**, *Files Required for PCB Fabrication and Assembly* (protoexpress.com)
- **Altium Resources**, *PCB Design Output Files* (resources.altium.com)
- **RBB Systems**, *Pre-Quote Checklist* (rbbsystems.com)
- **APTPCB**, *BOM Preparation for Turnkey Assembly* (aptpcb.com)
- **IPC-2581**, Printed Board Assembly Manufacturing Description Data

---

*Document Version: 1.0*
