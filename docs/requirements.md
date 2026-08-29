# Build Requirements

## Scope

This is a **new build from scratch**.

The CPU/platform decision is fixed:

- **AMD Ryzen 9 9950X3D**
- **AM5**

The memory-capacity target is also fixed at **256 GB for the initial build**, subject to a fallback only if current 256 GB cost is disproportionate or stable AM5 operation at that capacity requires an unacceptable performance/stability compromise.

The existing **NVIDIA GeForce RTX 3060 12 GB** will be reused initially.

The motherboard, exact memory configuration, cooling solution, storage architecture, PSU, case, UPS and operating system remain open.

Previously discussed parts and configurations are research candidates only unless explicitly recorded as selected in `docs/decisions.md`.

## Workload priority

### Primary

- Very heavy Java software development, including codebases with millions of lines
- IntelliJ IDEA and Android Studio
- Maven and Gradle builds
- Large automated test suites
- Static analysis and annotation processing
- Multiple concurrent JVM processes and local services
- Docker workloads
- WSL2
- Android Emulator
- Occasional virtual machines

### Secondary

- Occasional PC gaming
- Local AI experimentation may become relevant

## Longevity target

The system should remain useful and serviceable for approximately **7–10 years**. Component selection should therefore prioritize:

- platform stability
- maintainability and serviceability
- replaceability of failure-prone parts
- useful I/O and expansion headroom
- adequate memory capacity and stability
- storage endurance
- good thermal behavior under sustained workloads
- mature firmware and drivers
- avoiding expenditure on features that are unlikely to provide material value

## Budget and procurement

- Planning budget ceiling: **30,000 lei**
- Location: **Iași, Romania**
- Self-assembled
- Existing NVIDIA GeForce RTX 3060 12 GB will be reused initially

The budget is **not a primary optimization target** and should not drive component selection ahead of workload fit, stability, reliability, acoustics, expansion capability or longevity. It is a planning ceiling rather than a spending target.

More expensive parts are acceptable when they provide a concrete, material benefit. Conversely, do not spend extra for prestige, unused specifications, extreme-overclocking capability or other features that do not improve the actual workstation.

If an otherwise justified configuration exceeds 30,000 lei, identify the cost driver and evaluate whether the additional benefit warrants revisiting the planning ceiling rather than automatically compromising core requirements.

The current design should preserve the **256 GB memory target first**. Reduce memory capacity only if the real market cost of a suitable 256 GB configuration is disproportionate to its benefit or if achieving 256 GB on AM5 imposes a stability/performance compromise that outweighs the capacity benefit.

## Reliability principles

These are evaluation principles, not component decisions:

- Prefer simpler, mature solutions when performance is sufficient.
- Avoid manual overclocking as a design objective.
- Prioritize memory stability over headline memory speed.
- Evaluate ECC explicitly rather than assuming either ECC or non-ECC.
- Prefer storage with appropriate endurance and sustained-write behavior for VM/container use.
- Evaluate whether workload separation across physical drives is operationally useful before deciding drive count/capacity.
- Size the PSU for the selected platform plus a plausible future GPU rather than choosing wattage in advance.
- Design for good chassis airflow, dust management and maintainability.
- Evaluate UPS protection as part of the complete system power design.
- Maintain external backups; RAID is not a backup.

## Platform evaluation criteria

### CPU/platform

**Selected:** AMD Ryzen 9 9950X3D on AM5.

Downstream component decisions should optimize around this platform unless the CPU/platform decision is explicitly reopened.

### Motherboard

Only consider AM5 motherboards whose **manufacturer officially specifies support for at least 256 GB of system memory**.

This is a hard eligibility criterion because **256 GB is the initial build target**, not merely theoretical future headroom.

Motherboard evaluation should cover:

- BIOS/AGESA maturity with the Ryzen 9 9950X3D
- high-density DIMM support and QVL coverage
- realistic 256 GB behavior, including supported topology and data rate
- memory training/boot behavior with four high-density DIMMs
- PCIe/M.2 lane topology and sharing
- useful expansion after multiple NVMe drives are populated
- networking controller quality
- USB4/high-speed external I/O where useful
- ECC implementation and observability if supported
- virtualization/IOMMU behavior
- debug/recovery features
- long-term firmware support and serviceability

### Memory

**Target installed capacity: 256 GB.**

The exact DIMM topology, kit, operating data rate and ECC/non-ECC choice remain open.

The memory review should determine:

- the best stable 256 GB configuration for the selected 9950X3D + motherboard combination
- whether 4×64 GB is the practical/required topology and what operating speed is realistically stable
- motherboard QVL and vendor support evidence for 64 GB DIMMs
- JEDEC versus EXPO/XMP trade-offs at 256 GB
- ECC value and implementation quality
- memory-training and boot-time implications
- Romanian/EU availability and price
- the exact cost/stability threshold at which scaling back to 192 GB or 128 GB would be justified

Stability is more important than headline memory speed. Capacity should be reduced only when the 256 GB configuration is economically or technically disproportionate, not merely because a smaller configuration is cheaper or faster on paper.

### Storage

Determine from the workload:

- required total capacity
- whether OS and VM/container workloads benefit from separate physical drives
- appropriate number of drives
- PCIe generation
- NAND type and controller characteristics
- sustained write performance
- endurance
- firmware maturity and thermal behavior

Previously discussed **2 TB system + 4 TB work/VM NVMe** is a candidate architecture only.

### GPU

- Reuse the existing **NVIDIA GeForce RTX 3060 12 GB** initially.
- Ensure the new platform does not unnecessarily constrain a future substantially higher-VRAM GPU.
- Do not replace the GPU merely to optimize gaming performance unless requirements change.
- Future AI-oriented GPU evaluation should emphasize VRAM, software compatibility, power, thermals and physical fit.

### Networking and I/O

For a 7–10 year system, evaluate:

- wired Ethernet speed and controller quality
- Wi-Fi / Bluetooth only if useful
- Linux/WSL friendliness where relevant
- high-speed external I/O such as USB4 where justified
- sufficient rear and front I/O
- usable PCIe expansion after storage devices are installed
- topology/lane sharing rather than connector count alone

## Decision philosophy

Each component review should answer:

1. What does the workload actually require?
2. Which architectures/classes of component satisfy it?
3. Which features materially improve reliability, performance, serviceability or longevity?
4. Which features are merely premium positioning?
5. What compatibility or topology constraints does the choice impose on other components?
6. Which option best satisfies the technical requirements, and what does each additional price increment materially buy?
7. Is there a more expensive alternative with a concrete, defensible benefit worth paying for?
8. What must be validated after purchase?

A model mentioned in earlier discussions should be treated as a **candidate to compare**, not as the baseline that alternatives must displace, unless it is explicitly recorded as selected in `docs/decisions.md`.
