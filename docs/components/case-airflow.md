# Case and Airflow Deep Dive

Status: **Airflow-first strategy selected / exact case open**

## Selected design principle

The chassis should be **airflow-first** because the build prioritizes long-term stability, conservative thermals and a roughly 10-year useful-life objective.

This is a closed design principle, not an exact-case selection. The final chassis model and fan layout remain open until the motherboard, cooling, PSU and storage requirements are sufficiently clear.

The airflow objective is to keep the CPU, VRM, memory, NVMe drives and current/future GPU well below avoidable thermal limits under sustained workstation loads, while achieving acceptable acoustics with large, low-RPM fans rather than relying on restrictive panels or high fan speeds.

Good airflow is expected to improve the stability/endurance story by:

- reducing sustained temperatures of motherboard power delivery, memory, SSDs and GPU components
- reducing the probability of thermal throttling during long builds/tests, VM/container workloads and future AI workloads
- allowing fans and cooling devices to operate at lower RPM for a given component temperature
- preserving thermal headroom as filters accumulate dust between maintenance cycles
- providing enough heat-removal capacity for a future substantially higher-power GPU
- reducing the need to run components close to thermal limits for extended periods

Airflow is not a substitute for quality components, adequate heatsinks or proper validation, but it is a first-class reliability and longevity requirement for this build.

## Chassis design envelope

The chassis shortlist should favor a conventional, spacious, serviceable airflow layout and should be able to accommodate:

- standard ATX and preferably E-ATX motherboards, so workstation-oriented AM5 boards are not excluded unnecessarily
- the selected Ryzen 9 9950X3D cooling solution, including a large dual-tower air cooler or 360/420 mm radiator if later justified
- the existing RTX 3060
- a future very large 3.5–4-slot consumer GPU or high-power professional/AI accelerator
- generous GPU length, width and power-cable bend clearance
- strong front/bottom intake and rear/top exhaust paths without major obstruction
- large replaceable 140 mm or similarly low-RPM fans where practical
- a high-quality large ATX PSU with future high-power-GPU headroom
- several NVMe drives without trapping excessive heat around motherboard M.2 locations
- useful secondary PCIe-slot access where the selected motherboard topology permits it

A compact or showcase-oriented enclosure should not be preferred when it materially compromises airflow, component clearance, future GPU compatibility, serviceability or acoustic headroom.

## Dust and maintenance

Because the machine is intended for long ownership, airflow quality must include maintainability rather than raw open-mesh area alone.

Prefer:

- easily removable and cleanable intake filters
- filters that do not require major disassembly
- accessible fan mounts
- standard replaceable fans rather than proprietary fan assemblies
- straightforward cable routing that does not obstruct the primary airflow path
- positive or mildly positive pressure where practical to reduce uncontrolled dust ingress
- enough thermal margin that moderate filter loading does not immediately compromise component temperatures

## Acoustic objective

Airflow-first does **not** mean maximum fan speed.

The preferred design should use a low-restriction chassis and sufficiently large fans so that required airflow can be achieved at low RPM during normal development use. Fan curves should ramp only when sustained CPU/GPU/storage loads justify it.

For this workstation, a large low-restriction enclosure with slow fans is preferred over a restrictive 'silent' enclosure that requires higher fan speed or higher internal component temperatures to handle the same sustained load.

## Reference candidates

The previously discussed **Fractal Meshify 2** and **be quiet! Silent Base 802** remain reference candidates only. Neither is selected and both must be compared against current 2026 alternatives when the exact chassis review begins.

## Review focus

- motherboard form-factor support
- selected CPU-cooler clearance
- existing RTX 3060 fit
- future 3.5–4-slot / long / high-power GPU headroom
- airflow path and restriction
- GPU intake clearance
- dust filtration and pressure strategy
- acoustic behavior at sustained workstation loads
- support for large low-RPM fans
- radiator support if liquid cooling is later justified
- front I/O
- storage mounting requirements if any
- fan placement and header/control requirements
- cable-management quality and GPU power-cable clearance
- build/serviceability
- filter and fan accessibility
- replacement-part availability
- Romanian/EU pricing/value

## Required output

Finish with:

1. case requirements derived from selected motherboard/cooling/storage/PSU
2. serious candidate shortlist
3. exact case recommendation
4. fan layout and pressure strategy
5. clearance validation for the selected parts and a plausible future high-power GPU
6. front-I/O/header dependencies
7. maintenance and dust-management plan
8. expected acoustic/thermal operating approach
9. Romanian/EU price/value

## Current position

**Airflow-first chassis design is selected as a stability/longevity principle. The exact chassis and fan layout remain open and should be chosen only after the motherboard/cooling/PSU design envelope is sufficiently mature.**
