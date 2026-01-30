# Schematic Review Checklist

---

## 1. Design Setup and Configuration

- [ ] Design rules check (DRC) configured and enabled
- [ ] Grid size defined and consistent
- [ ] Sheet size appropriate for content (A3/Tabloid max recommended)
- [ ] Template applied correctly to all sheets
- [ ] Version control system in use (Git, SVN, etc.)
- [ ] Design decisions documented with rationale

---

## 2. Power Architecture

### 2.1 Power Tree
- [ ] Power tree diagram created showing all voltage rails and their relationships
- [ ] Input power source(s) identified with voltage and current ratings
- [ ] All voltage domains documented (analog, digital, I/O, etc.)
- [ ] Power sequencing requirements identified and documented
- [ ] Inrush current considered and managed
- [ ] Power budget calculated and verified against source capability

### 2.2 Power Supply Design
- [ ] Supply voltages verified against all component requirements
- [ ] Current capacity verified for each rail (include margin)
- [ ] Ripple and noise specifications defined
- [ ] Efficiency targets established
- [ ] Thermal dissipation calculated for regulators
- [ ] Under-voltage and over-voltage protection implemented where required
- [ ] Reverse polarity protection included where appropriate
- [ ] Power-good signals routed to supervisor circuits or MCU

### 2.3 Decoupling and Filtering
- [ ] Bulk capacitance adequate for load transients
- [ ] Decoupling capacitors specified for every IC power pin
- [ ] Capacitor values appropriate for target frequencies
- [ ] Voltage ratings of capacitors adequate (derate 50% minimum for MLCC)
- [ ] Ferrite beads specified for sensitive analog supplies
- [ ] Analog and digital power domains separated appropriately

### 2.4 Grounding
- [ ] Grounding scheme defined (single-point, multi-point, hybrid)
- [ ] Analog and digital grounds joined at single point (if applicable)
- [ ] Ground symbols consistent throughout schematic
- [ ] No upward-pointing ground symbols
- [ ] Chassis/earth ground connections identified

---

## 3. Component Verification

### 3.1 Selection
- [ ] All components have complete part numbers (MPN)
- [ ] Components available from multiple sources or alternates identified
- [ ] No obsolete or end-of-life components (or risk accepted)
- [ ] Errata sheets reviewed for all ICs
- [ ] Voltage ratings adequate with appropriate derating
- [ ] Power ratings adequate with appropriate derating
- [ ] Temperature ratings compatible with operating environment
- [ ] Package types appropriate for assembly method

### 3.2 Passive Components
- [ ] Resistor power ratings verified
- [ ] Resistor voltage ratings verified (especially high-value resistors)
- [ ] Capacitor voltage ratings verified with derating
- [ ] Capacitor temperature characteristics appropriate (X5R, X7R, C0G, etc.)
- [ ] Inductor saturation current adequate
- [ ] Inductor DC resistance acceptable for application
- [ ] Tantalum capacitors not driven by low-impedance sources without limiting

### 3.3 Active Components
- [ ] All IC power pins connected
- [ ] All IC ground pins connected
- [ ] Unused op-amp sections terminated (output to inverting input, non-inverting to ground)
- [ ] Unused comparator pins terminated per datasheet
- [ ] Unused digital inputs tied to appropriate level (not floating)
- [ ] Unused analog inputs terminated appropriately
- [ ] Reset pins properly biased and filtered
- [ ] Configuration/strap pins biased per datasheet requirements
- [ ] Breakout provided for spare/unused IC pins where practical

---

## 4. Connector Verification

### 4.1 Pin Assignment
- [ ] **Pin 1 explicitly verified against mating connector/cable**
- [ ] **Pin 2 explicitly verified against mating connector/cable**
- [ ] All remaining pins verified against mating connector/cable
- [ ] Pinout matches mating connector (check for mirror/flip errors)
- [ ] Keying or polarization specified to prevent mis-mating
- [ ] Ground pins make first contact on hot-plug connectors
- [ ] Connector gender correct (male vs. female)

### 4.2 Electrical
- [ ] Pin current ratings adequate
- [ ] Pin voltage ratings adequate
- [ ] Contact resistance acceptable for application
- [ ] Shielded connectors specified where EMC requires
- [ ] ESD protection on exposed connector pins
- [ ] TVS diodes or other transient protection where required

### 4.3 Mechanical
- [ ] Connector footprint matches selected part
- [ ] Mating clearance verified
- [ ] Retention force appropriate for application
- [ ] Strain relief considered for cable assemblies

---

## 5. Signal Integrity

### 5.1 Digital Signals
- [ ] Pull-ups on all open-drain/open-collector outputs
- [ ] I²C pull-up values calculated for bus capacitance and speed
- [ ] SPI chip selects active level verified
- [ ] UART TX/RX connections verified (TX→RX, RX→TX)
- [ ] Series termination resistors specified for high-speed signals
- [ ] Parallel termination specified where required
- [ ] Logic level translation provided between different voltage domains

### 5.2 Analog Signals
- [ ] Input impedance appropriate for source
- [ ] Output impedance appropriate for load
- [ ] Anti-aliasing filters on ADC inputs
- [ ] Reference voltage stability adequate
- [ ] Differential signaling used where appropriate
- [ ] Op-amp input filters for EMI immunity

### 5.3 High-Speed/RF
- [ ] Impedance-controlled signals identified
- [ ] Target impedance noted on schematic
- [ ] Differential pairs identified and matched
- [ ] AC coupling capacitors specified where required
- [ ] Common-mode filter footprints included for differential signals going off-board

---

## 6. Protection Circuits

### 6.1 ESD Protection
- [ ] ESD protection on all user-accessible pins
- [ ] ESD protection on all cable/connector interfaces
- [ ] TVS diode clamping voltages appropriate
- [ ] TVS diode capacitance acceptable for signal bandwidth

### 6.2 Overcurrent Protection
- [ ] Fuses sized appropriately (current rating, breaking capacity)
- [ ] Fuse blow time adequate for protected components
- [ ] Resettable fuses (PTCs) used where appropriate
- [ ] Current limiting on hot-swap circuits

### 6.3 Overvoltage Protection
- [ ] Clamping diodes on inductive loads
- [ ] Snubber circuits on switching nodes where required
- [ ] Zener or TVS protection on sensitive inputs

---

## 7. Testability and Debug

### 7.1 Test Points
- [ ] Test points on all voltage rails
- [ ] Test points on critical signals
- [ ] Ground test points distributed for probe access
- [ ] Test points accessible after assembly

### 7.2 Debug Interfaces
- [ ] Programming header included (JTAG, SWD, ICSP, etc.)
- [ ] Debug UART accessible
- [ ] Status LEDs on power rails
- [ ] Activity/status LEDs for firmware indication
- [ ] Jumpers or switches for configuration options
- [ ] Provisions for logic analyzer connections on critical buses

### 7.3 In-Circuit Test
- [ ] Board revision readable by firmware (GPIO straps, ADC divider, etc.)
- [ ] Built-in test provisions for production verification

---

## 8. EMC Considerations

### 8.1 Emissions
- [ ] Clock frequencies identified with harmonics
- [ ] Spread-spectrum options evaluated for clocks/switching supplies
- [ ] RC snubbers specified on switching supplies where needed
- [ ] Ferrite beads on power supply inputs/outputs
- [ ] Filtered connectors or filter components at I/O boundaries

### 8.2 Immunity
- [ ] ESD protection on external interfaces
- [ ] EMI filters on sensitive analog inputs
- [ ] Decoupling adequate for conducted immunity
- [ ] Shielding requirements identified

### 8.3 Regulatory
- [ ] Target EMC standards identified (FCC, CE, CISPR, etc.)
- [ ] Test levels documented (residential, industrial, automotive)

---

## 9. Cross-Functional Domain Checks

### 9.1 Firmware/Software Interface
- [ ] All required MCU peripherals available and assigned
- [ ] GPIO assignments reviewed with firmware team
- [ ] Interrupt-capable pins used where interrupts needed
- [ ] Bootloader/programming interfaces accessible
- [ ] Watchdog timer provisions adequate
- [ ] Reset behavior defined and documented

### 9.2 Mechanical Interface
- [ ] Board outline constraints communicated
- [ ] Connector locations compatible with enclosure
- [ ] Keep-out zones identified
- [ ] Height restrictions documented
- [ ] Mounting hole locations defined
- [ ] Thermal interface requirements identified

### 9.3 Thermal Considerations
- [ ] High-power components identified
- [ ] Heat sink requirements defined
- [ ] Thermal relief/dissipation path to PCB identified
- [ ] Thermal derating applied to component ratings
- [ ] Temperature-sensitive components placed away from heat sources

### 9.4 Manufacturing/Assembly
- [ ] BOM line count optimized (consolidate values where possible)
- [ ] All components have footprint assignments
- [ ] Footprints verified against component datasheets
- [ ] Assembly variants defined (if applicable)
- [ ] Mounted/not-mounted status defined for all components

### 9.5 Safety and Compliance
- [ ] Isolation barriers adequate for safety requirements
- [ ] Creepage and clearance requirements identified
- [ ] Safety-critical components identified
- [ ] RoHS/REACH compliance verified

---

## 10. Documentation and Drafting

### 10.1 Schematic Clarity
- [ ] Logical signal flow: inputs left, outputs right
- [ ] Related circuits grouped together
- [ ] No four-way wire junctions
- [ ] All junctions marked with dots
- [ ] No-connects explicitly marked
- [ ] No overlapping text, wires, or symbols
- [ ] All text horizontal (or vertical where necessary)

### 10.2 Naming and Labeling
- [ ] Net names meaningful and consistent
- [ ] Reference designators sequential by function or location
- [ ] All components have reference designator and value
- [ ] Decimal points avoided in values (use 4k7, 2R2 notation)
- [ ] Off-sheet destinations labeled clearly
- [ ] Power nets named consistently (VCC, VDD, 3V3, etc.)

### 10.3 Notes and Instructions
- [ ] Special layout requirements noted (impedance, routing, keep-out)
- [ ] Calculations or design rationale documented
- [ ] References to datasheets or application notes included
- [ ] Unpopulated components clearly marked

### 10.4 Final Verification
- [ ] Electrical rules check (ERC) passes or all warnings reviewed
- [ ] All nets connected (no unintended stubs)
- [ ] Net names unique (no duplicate names for different nets)
- [ ] Schematic compiles without critical errors
- [ ] Peer review completed

---

## References and Credits

This checklist incorporates best practices from the following sources:

- **Henrik Enggaard Hansen**, *PCB Checklist* (pcbchecklist.com) — CC BY-SA 4.0
- **Hank Wallace / JLD Systems**, *Electronics Design Checklist* (jldsystems.com)
- **Altium Resources**, *Schematic Review Checklist* (resources.altium.com)
- **Cadence**, *Electrical Schematic Design Checklist* (resources.pcb.cadence.com)
- **Memfault / Mark Schulte**, *Schematic Review Checklist for Firmware Engineers* (interrupt.memfault.com)
- **EMC FastPass**, *EMC Design Review* (emcfastpass.com)
- **EEVblog #1129**, *Creating a Nice Readable Schematic* (Dave Jones)

---

*Document Version: 1.0*
