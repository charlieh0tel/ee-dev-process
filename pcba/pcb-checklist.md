# PCB Layout Review Checklist

---

## 1. Design Setup

- [ ] Stackup defined and documented
- [ ] Impedance requirements specified
- [ ] Design rules configured (trace width, spacing, via sizes)
- [ ] Manufacturing tolerances entered (solder mask, silkscreen, drill)
- [ ] Net classes defined with appropriate rules
- [ ] Board outline defined with correct dimensions

---

## 2. Component Placement

### 2.1 General Placement
- [ ] All components placed
- [ ] Components oriented consistently where practical
- [ ] Reference designators readable from one or two directions
- [ ] Polarity markings visible and unambiguous
- [ ] High-density ICs have pin 1 and pin numbers marked
- [ ] Functional groups placed together
- [ ] Signal flow logical (input to output)

### 2.2 Connector Placement
- [ ] **Connector pin 1 verified against schematic and mating part**
- [ ] **Connector pin 2 verified against schematic and mating part**
- [ ] Connectors accessible at board edge or per mechanical requirements
- [ ] Mating clearance verified (connector body and cable)
- [ ] Polarization/keying orientation correct
- [ ] EMI-sensitive connectors grouped on same board edge where possible

### 2.3 Thermal Placement
- [ ] Hot components separated from temperature-sensitive components
- [ ] Heat sinks have adequate clearance
- [ ] Thermal relief paths to ground planes or heat spreaders
- [ ] Airflow direction considered for forced-air cooling

### 2.4 EMC Placement
- [ ] I/O filtering components placed at board edge near connectors
- [ ] Decoupling capacitors placed close to IC power pins
- [ ] Crystal/oscillator placed close to driving IC
- [ ] Clock sources away from I/O and board edges
- [ ] Shield can footprints included where required

---

## 3. Routing

### 3.1 Power Distribution
- [ ] Power planes/pours connected and verified
- [ ] Adequate copper for current requirements (planes or trace width)
- [ ] Via count adequate for current on plane transitions
- [ ] Power trace widths sized for current with margin
- [ ] Star or distributed power topology implemented per design intent
- [ ] No isolated copper islands on power layers

### 3.2 Signal Routing
- [ ] All nets routed (no unconnected pins)
- [ ] No acute angles (< 90°) on traces
- [ ] Trace-to-pad connections at obtuse angles where possible
- [ ] Stubs minimized on high-speed signals
- [ ] Differential pairs routed together with matched length
- [ ] Impedance-controlled traces on appropriate layers
- [ ] Length matching complete for required nets

### 3.3 Return Paths
- [ ] Continuous ground reference under high-speed signals
- [ ] No traces routed over plane splits
- [ ] Ground return vias near signal vias for layer transitions
- [ ] Digital and analog signal separation maintained

### 3.4 Via Usage
- [ ] Via sizes appropriate for signal and current
- [ ] Via-in-pad used only where required (and specified for filling)
- [ ] Thermal vias in thermal pads where required
- [ ] Via stitching around board perimeter for ground ring
- [ ] Via fencing for RF traces (spacing < λ/20)

---

## 4. Ground and Power Planes

- [ ] Ground plane continuous (no unnecessary splits)
- [ ] Plane splits documented and intentional
- [ ] No traces creating ground loops
- [ ] Analog and digital ground separation maintained (if required)
- [ ] Ground pour connection points adequate
- [ ] Thermal reliefs on plane connections where appropriate
- [ ] No isolated copper (floating metal)
- [ ] All copper pours checked on all layers

---

## 5. Signal Integrity

### 5.1 High-Speed Signals
- [ ] Transmission line impedances verified
- [ ] Differential pair spacing and routing per requirements
- [ ] Length matching within tolerance
- [ ] Reference planes identified and continuous
- [ ] Layer transitions minimized
- [ ] Termination components placed correctly (source/load)

### 5.2 Sensitive Signals
- [ ] Crystal traces short, minimal vias
- [ ] Guard ring around crystal if required
- [ ] ADC input traces isolated from noisy signals
- [ ] Analog signal routing over analog ground
- [ ] No traces under sensitive components
- [ ] No vias under metal film resistors

### 5.3 Crosstalk Prevention
- [ ] Adequate spacing between parallel high-speed traces
- [ ] Aggressor and victim nets identified and separated
- [ ] Ground/power fills between sensitive traces where needed

---

## 6. EMC Design

### 6.1 Emissions Control
- [ ] Ground ring around board perimeter
- [ ] No traces at board edges
- [ ] Clock traces short and away from I/O
- [ ] Decoupling effective at harmonic frequencies
- [ ] Spread-spectrum clock provisions verified in layout

### 6.2 I/O Filtering
- [ ] Filter components at connector boundaries
- [ ] ESD protection devices close to connector pins
- [ ] Ferrites and capacitors in correct order (L-C vs C-L)
- [ ] Shield connections low-inductance

### 6.3 Shielding
- [ ] Shield can footprint and grounding provisions adequate
- [ ] Shield perimeter grounded with via stitching
- [ ] Cable shield termination at connector

---

## 7. Mechanical

### 7.1 Board Outline
- [ ] Outline matches mechanical specification
- [ ] Internal cutouts defined
- [ ] Corners rounded where required (minimum mill radius)
- [ ] Edge clearances maintained

### 7.2 Mounting Holes
- [ ] Mounting holes in correct locations (verified against mechanical drawing)
- [ ] Mounting hole diameter correct for hardware (M3, #4-40, etc.)
- [ ] **Preferred construction: NPTH with via-stitched annular ring** (provides ground connection without plating thickness variation)
- [ ] If PTH used: hole diameter includes plating allowance
- [ ] Mounting holes isolated or grounded per requirement
- [ ] Keep-out around mounting holes maintained (component and trace clearance)
- [ ] Via stitching around grounded mounting holes for improved ground connection
- [ ] Annular ring sized for screw head or washer contact area

### 7.3 Height and Clearance
- [ ] Component heights within enclosure constraints
- [ ] Clearance for mating connectors verified
- [ ] Clearance for test probes where needed
- [ ] Clearance for programming/debug headers
- [ ] Clearance for rework (IC removal tools)

---

## 8. Design for Manufacturing (DFM)

### 8.1 Fabrication
- [ ] Minimum trace width meets fab capability
- [ ] Minimum spacing meets fab capability
- [ ] Minimum drill size meets fab capability
- [ ] Aspect ratio (board thickness : drill diameter) acceptable
- [ ] Annular ring adequate
- [ ] Solder mask openings adequate
- [ ] Copper-to-edge clearance maintained

### 8.2 Assembly
- [ ] Component spacing adequate for assembly method
- [ ] Fiducials placed for SMT (global and local if needed)
- [ ] Solder paste apertures appropriate (modified as needed)
- [ ] Thermal relief on large pads (wave solder)
- [ ] Component orientation consistent for inspection
- [ ] Tombstone risk mitigated (balanced pad thermals)
- [ ] BGA escape routing complete with proper fanout

### 8.3 Panel/Array
- [ ] Panel size compatible with assembly equipment
- [ ] Tooling holes and fiducials on panel rails
- [ ] V-score or tab routing defined
- [ ] Breakaway tabs located away from sensitive circuits

---

## 9. Silkscreen and Markings

### 9.1 Component Markings
- [ ] Reference designators visible (not covered by components)
- [ ] Reference designators in consistent orientation
- [ ] Pin 1 indicators clear and consistent
- [ ] Polarity indicators clear for all polarized components
- [ ] Connector pinouts labeled

### 9.2 Board Information
- [ ] Board name/part number present
- [ ] Revision number present
- [ ] Date or date code space
- [ ] Space for serial number (writable area)
- [ ] Company logo/name
- [ ] Regulatory markings (CE, FCC, UL) where required

### 9.3 Functional Markings
- [ ] Test points labeled
- [ ] LED functions labeled
- [ ] Switch/jumper functions labeled
- [ ] Fuse ratings marked

### 9.4 Silkscreen Quality
- [ ] No silkscreen on pads
- [ ] No silkscreen on exposed copper
- [ ] Text legible at fabrication capability (minimum 0.8mm height typical)
- [ ] No overlapping text

---

## 10. Safety and Compliance

### 10.1 Electrical Safety
- [ ] Creepage distances meet safety requirements
- [ ] Clearance distances meet safety requirements
- [ ] Isolation barriers properly implemented
- [ ] Slots or cutouts for isolation where required

### 10.2 Compliance Markings
- [ ] Space for required certification marks
- [ ] Country of origin marking if required
- [ ] RoHS marking if applicable

---

## 11. Cross-Functional Checks

### 11.1 Mechanical Interface
- [ ] Board outline matches enclosure model
- [ ] Mounting holes align with enclosure
- [ ] Connector positions match enclosure openings
- [ ] Component heights verified against enclosure
- [ ] LCD/display window alignment verified

### 11.2 Thermal Interface
- [ ] Thermal pads aligned with heat sink mounting
- [ ] Thermal interface material area defined
- [ ] Airflow path unobstructed

### 11.3 Test Interface
- [ ] Test point accessibility verified for fixturing
- [ ] Bed-of-nails access if required
- [ ] Flying probe accessibility

### 11.4 Production Interface
- [ ] Panel design reviewed with CM
- [ ] Special assembly requirements documented
- [ ] Conformal coating keep-outs defined if applicable

---

## 12. Final Verification

### 12.1 Design Rule Checks
- [ ] DRC passes with no errors
- [ ] All warnings reviewed and resolved or accepted
- [ ] Layout versus schematic (LVS) check passes
- [ ] Net connectivity verified

### 12.2 Visual Inspection
- [ ] All layers reviewed visually
- [ ] Gerber files generated and reviewed in CAM viewer
- [ ] Drill files verified
- [ ] Pick-and-place data verified
- [ ] Assembly drawings reviewed

### 12.3 Documentation
- [ ] Fabrication notes complete
- [ ] Assembly notes complete
- [ ] Special process requirements documented
- [ ] Stackup drawing included

---

## References and Credits

This checklist incorporates best practices from the following sources:

- **Henrik Enggaard Hansen**, *PCB Checklist* (pcbchecklist.com) — CC BY-SA 4.0
- **Hank Wallace / JLD Systems**, *Electronics Design Checklist* (jldsystems.com)
- **Altium Resources**, *PCB Design Guidelines* (resources.altium.com)
- **Sierra Circuits**, *PCB Design for Manufacturing* (protoexpress.com)
- **Autocuro**, *Ultimate PCB Design Checklist* (autocuro.com)
- **Mark Montrose**, *Printed Circuit Board Design Techniques for EMC Compliance*

---

*Document Version: 1.0*
