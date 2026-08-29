# Build Requirements

## Scope

This is a **new build from scratch**.

The CPU/platform decision is fixed:

- **AMD Ryzen 9 9950X3D**
- **AM5**

The existing **NVIDIA GeForce RTX 3060 12 GB** will be reused initially.

The motherboard, memory configuration, cooling solution, storage architecture, PSU, case, UPS and operating system remain open.

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

- Maximum total project budget: **20,000 lei**
- Location: **Iași, Romania**
- Self-assembled
- Existing NVIDIA GeForce RTX 3060 12 GB will be reused initially

The budget is a ceiling, not a spending target. More expensive parts should be selected only when they provide a concrete benefit for the workload, reliability, expandability or expected lifespan.

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

This is a hard eligibility criterion intended to preserve long-term memory expansion headroom. It does **not** mean that 256 GB must be installed initially.

Motherboard evaluation should also cover:

- BIOS/AGESA maturity with the Ryzen 9 9950X3D
- high-density DIMM support and QVL coverage
- realistic memory behavior at 128 GB, 192 GB and 256 GB
- PCIe/M.2 lane topology and sharing
- useful expansion after multiple NVMe drives are populated
- networking controller quality
- USB4/high-speed external I/O where useful
- ECC implementation and observability if supported
- virtualization/IOMMU behavior
- debug/recovery features
- long-term firmware support and serviceability

### Memory

The installed capacity, DIMM topology, data rate and ECC/non-ECC choice remain open.

The memory review should determine:

- realistic capacity requirement for the workload and 7–10 year horizon
- whether 128 GB, 192 GB, 256 GB or another capacity is justified
- optimal DIMM count/topology for AM5
- stable supported data rate at the selected capacity
- ECC value and implementation quality
- upgradeability versus initial cost

The motherboard must not constrain a future move to 256 GB, but actual memory selection must prioritize stability over headline speed.

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
6. What is the best value point in the current Romanian market?
7. Is there a more expensive alternative with a concrete, defensible benefit?
8. What must be validated after purchase?

A model mentioned in earlier discussions should be treated as a **candidate to compare**, not as the baseline that alternatives must displace, unless it is explicitly recorded as selected in `docs/decisions.md`.
