# Manufacturing Change Order (MCO) Checklist

---

## 1. Change Identification

### 1.1 Change Classification
- [ ] Change type defined:
  - [ ] Component substitution (alternate manufacturer)
  - [ ] Process change (assembly, test, handling)
  - [ ] Tooling change (fixture, stencil, programming)
  - [ ] Documentation change (work instructions, BOM)
  - [ ] Supplier change (same component, different distributor)
- [ ] Urgency level assigned (routine, expedited, emergency)
- [ ] Scope defined (single product, product family, all products)

### 1.2 Reason for Change
- [ ] Root cause documented:
  - [ ] Component obsolescence or EOL
  - [ ] Supply chain disruption
  - [ ] Cost reduction
  - [ ] Quality improvement
  - [ ] Yield improvement
  - [ ] Process efficiency
  - [ ] Regulatory compliance
  - [ ] Customer request
- [ ] Supporting evidence attached (failure data, cost analysis, etc.)

---

## 2. Change Definition

### 2.1 Current State
- [ ] Affected part number(s) listed
- [ ] Current revision level documented
- [ ] Current approved manufacturer list (AML) documented
- [ ] Current process parameters documented
- [ ] Current documentation revision listed

### 2.2 Proposed State
- [ ] New configuration fully described
- [ ] New component specifications (if component change)
- [ ] New process parameters (if process change)
- [ ] Comparison table: current vs. proposed

### 2.3 Component Substitution Specifics (if applicable)
- [ ] Original part manufacturer and MPN
- [ ] Substitute part manufacturer and MPN
- [ ] Parametric comparison completed:
  - [ ] Electrical specifications match or exceed original
  - [ ] Package/footprint identical or verified compatible
  - [ ] Operating temperature range adequate
  - [ ] Reliability data reviewed
- [ ] Datasheet comparison attached
- [ ] Substitute is form-fit-function equivalent

---

## 3. Impact Assessment

### 3.1 Technical Impact
- [ ] Circuit function verified unchanged
- [ ] PCB footprint compatibility verified
- [ ] Assembly process compatibility confirmed
- [ ] Test coverage remains adequate
- [ ] Reliability impact assessed
- [ ] EMC/EMI impact assessed (if relevant)
- [ ] Thermal performance impact assessed

### 3.2 Quality Impact
- [ ] Incoming inspection requirements unchanged or updated
- [ ] In-process inspection requirements unchanged or updated
- [ ] Final test requirements unchanged or updated
- [ ] First-article inspection required? (yes/no)
- [ ] Process validation required? (yes/no)

### 3.3 Supply Chain Impact
- [ ] Lead time impact documented
- [ ] Minimum order quantity impact documented
- [ ] Cost impact documented (per unit, NRE, tooling)
- [ ] Inventory disposition plan for obsolete material
- [ ] Multiple source availability assessed

### 3.4 Regulatory/Certification Impact
- [ ] Regulatory compliance verified (RoHS, REACH, etc.)
- [ ] Safety certification impact assessed (UL, CE, etc.)
- [ ] Customer certification requirements reviewed
- [ ] Notification requirements to customers identified

---

## 4. Cross-Functional Review

### 4.1 Engineering Review
- [ ] Hardware engineering approval
- [ ] Firmware/software impact assessed (none, or changes identified)
- [ ] Test engineering approval
- [ ] Reliability engineering review (for critical components)

### 4.2 Manufacturing Review
- [ ] Assembly process engineer approval
- [ ] Equipment or tooling changes identified
- [ ] Work instruction updates required? (yes/no)
- [ ] Operator training required? (yes/no)
- [ ] Programming changes required? (pick-and-place, test, etc.)

### 4.3 Quality Review
- [ ] Quality engineering approval
- [ ] Inspection criteria updates required? (yes/no)
- [ ] Supplier qualification status verified
- [ ] Control plan updates required? (yes/no)

### 4.4 Supply Chain Review
- [ ] Procurement/purchasing approval
- [ ] Supplier approved and qualified
- [ ] Long-term availability confirmed
- [ ] Pricing confirmed

### 4.5 Documentation Review
- [ ] BOM update required? (yes/no)
- [ ] AML update required? (yes/no)
- [ ] Assembly drawing update required? (yes/no)
- [ ] Test procedure update required? (yes/no)
- [ ] Work instruction update required? (yes/no)
- [ ] Customer documentation update required? (yes/no)

---

## 5. Implementation Planning

### 5.1 Validation Requirements
- [ ] Validation plan defined:
  - [ ] Engineering samples to evaluate
  - [ ] First-article inspection requirements
  - [ ] Process validation requirements
  - [ ] Reliability testing requirements
- [ ] Sample quantity and source identified
- [ ] Test results acceptance criteria defined

### 5.2 Effectivity
- [ ] Effectivity type defined:
  - [ ] Immediate (next production lot)
  - [ ] Date-based (specific effective date)
  - [ ] Serial number-based
  - [ ] Inventory depletion (use existing stock first)
- [ ] Cutover date or trigger documented
- [ ] Mixed inventory handling defined (allowed/prohibited)

### 5.3 Inventory Disposition
- [ ] Current stock quantity documented
- [ ] Disposition of existing inventory:
  - [ ] Use as-is until depleted
  - [ ] Scrap
  - [ ] Return to supplier
  - [ ] Rework
- [ ] Cost of disposition documented

### 5.4 Communication Plan
- [ ] Internal stakeholders identified and notified
- [ ] Customer notification required? (yes/no, per contract)
- [ ] Supplier notification required? (yes/no)
- [ ] Training scheduled (if required)

---

## 6. Documentation Updates

### 6.1 Design Documentation (typically unchanged for MCO)
- [ ] Schematic: no change required / change via ECO
- [ ] PCB layout: no change required / change via ECO
- [ ] If design changes needed, separate ECO initiated

### 6.2 Manufacturing Documentation
- [ ] BOM updated with new AML entry
- [ ] Assembly work instructions updated
- [ ] Incoming inspection procedure updated
- [ ] Test procedure updated
- [ ] Programming files updated (if required)
- [ ] Stencil/tooling changes documented

### 6.3 Quality Documentation
- [ ] Control plan updated
- [ ] PFMEA updated (if process change)
- [ ] Supplier quality record updated

---

## 7. Verification and Closure

### 7.1 Validation Results
- [ ] Engineering samples evaluated: Pass / Fail
- [ ] First-article inspection completed: Pass / Fail
- [ ] Process validation completed: Pass / Fail
- [ ] Reliability testing completed: Pass / Fail / Waived
- [ ] All acceptance criteria met

### 7.2 Implementation Verification
- [ ] Documentation updates completed
- [ ] System updates completed (ERP, PLM, etc.)
- [ ] Production personnel trained
- [ ] Inventory records updated
- [ ] First production lot monitored

### 7.3 Closure
- [ ] All action items completed
- [ ] Validation records archived
- [ ] MCO closed in tracking system
- [ ] Lessons learned captured (if applicable)

---

## MCO vs. ECO: When to Use Each

| Scenario | Document Type |
|----------|---------------|
| Add alternate manufacturer to AML (same part) | MCO |
| Change assembly process parameter | MCO |
| Change test fixture or procedure | MCO |
| Change component to different part number | ECO |
| Change PCB layout | ECO |
| Change schematic | ECO |
| Change firmware | ECO or SCO |
| Process change affecting product form/fit/function | ECO |

---

## References and Credits

This checklist incorporates best practices from the following sources:

- **Arena Solutions**, *Guide to Manufacturing and Engineering Change Orders* (arenasolutions.com)
- **Propel Software**, *Manufacturing Change Order Glossary* (propelsoftware.com)
- **Versa Electronics**, *Engineering Change Order Best Practices* (versae.com)
- **Aligni**, *Engineering Change Orders in Manufacturing* (aligni.com)
- **CMII (Configuration Management II)**, Institute of Configuration Management

---

*Document Version: 1.0*
