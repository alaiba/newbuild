# Build Requirements

## Scope

This is a **new build from scratch**. No CPU platform, motherboard, memory configuration, cooling solution, storage architecture, PSU, case, UPS or operating system has been selected yet.

The only fixed hardware input is the existing **NVIDIA GeForce RTX 3060 12 GB**, which will be reused initially.

Previously discussed parts and configurations are research candidates only. They are not requirements and must not be treated as predetermined choices.

## Workload priority

### Primary

- Programming and general software development
- Docker workloads
- WSL2
- Multiple virtual machines

### Secondary

- Occasional Genshin Impact
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

Evaluate from first principles:

- sustained multi-core performance for builds, VMs and containers
- single-thread responsiveness
- virtualization support
- power efficiency and thermals
- memory capacity/support
- platform maturity and longevity
- chipset/PCIe/I/O capabilities
- total platform cost

No CPU vendor, socket or model is selected yet.

### Memory

Capacity, DIMM topology, data rate and ECC/non-ECC are all open questions.

The memory review should determine:

- realistic capacity requirement for the workload and 7–10 year horizon
- whether 64 GB, 96 GB, 128 GB, 192 GB, 256 GB or another capacity is justified
- optimal DIMM count/topology for the chosen platform
- stable supported data rate
- ECC value and implementation quality
- upgradeability versus initial cost

Previously discussed **128 GB as 2×64 GB DDR5-5600** is a hypothesis to test, not a requirement.

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

A model mentioned in earlier discussions should be treated as a **candidate to compare**, not as the baseline that alternatives must displace.
