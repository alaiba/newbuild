# Build Requirements

## Scope

This is a **new build from scratch**.

The CPU/platform decision is fixed:

- **AMD Ryzen 9 9950X3D**
- **AM5**

The memory strategy is also fixed at the architectural level:

- preserve a credible path to **256 GB** system memory;
- the initial purchase may start lower when high-capacity DDR5 pricing is disproportionate;
- **64 GB as 2×32 GB is the minimum acceptable initial configuration**;
- a larger initial capacity such as 96 GB or 128 GB may still be selected if current price/value is attractive.

The existing **NVIDIA GeForce RTX 3060 12 GB** will be reused initially.

The motherboard, exact memory kit/capacity above the 64 GB floor, cooling solution, storage architecture, PSU, case, UPS and operating system remain open.

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
- **Future local AI experimentation, inference and model training using a substantially more capable discrete GPU**

The AI objective is secondary: preserve a credible upgrade path without turning the current system into a specialized multi-GPU AI workstation or compromising the primary development/reliability goals.

## Future local AI upgrade objective

The system should be designed so that a future move from the existing RTX 3060 to a **very high-performance, high-VRAM GPU** does not require replacing otherwise suitable core components unnecessarily.

Design implications:

- prefer a motherboard that preserves a full-performance CPU-connected primary GPU slot with the intended storage configuration;
- consider CPU-connected **x8/x8 bifurcation across two physical x16 slots** a useful future-facing feature when it does not materially compromise stability, layout or cost, but do not make dual-GPU support a hard requirement;
- preserve physical space and airflow for a future very large/high-power GPU;
- size the eventual PSU and case with a plausible future 500–600 W-class accelerator in mind rather than only the current RTX 3060;
- avoid consuming the only useful secondary PCIe slot for functionality that could reasonably be integrated on the motherboard, where that would restrict future expansion;
- consider onboard 5/10 GbE useful when it avoids a future NIC consuming scarce expansion resources;
- treat **GPU VRAM as the primary capacity constraint for local model training/inference**; 256 GB of system RAM is valuable for data preparation, CPU offload, model loading and concurrent tooling, but it does not substitute for GPU VRAM;
- retain NVIDIA/CUDA compatibility as an important consideration for a future AI GPU, without selecting the future GPU model now.

A single very high-end GPU is a credible upgrade within AM5. If future requirements grow into **serious multi-GPU training**, the AM5 platform may become the limiting architecture because of PCIe lane count, physical slot layout, power and cooling. At that point it is acceptable to reopen the platform decision and consider Threadripper/WRX90 or another workstation/server-class platform rather than over-designing the current machine for an uncertain multi-GPU requirement.

## Longevity target

The system should be designed around a **10-year useful-life objective**, especially if the final cost approaches or exceeds the 30,000 lei planning level.

This does not mean every component must remain untouched for ten years. It means the build should justify a high initial investment through long-term stability, serviceability, reliability and retained usefulness rather than through short-lived peak benchmark performance.

Component selection should therefore prioritize:

- platform and firmware maturity
- conservative, stable operation rather than aggressive tuning
- maintainability and serviceability
- replaceability of failure-prone parts
- useful I/O and expansion headroom
- adequate memory capacity and proven memory stability
- storage endurance and data-integrity characteristics
- strong sustained thermal behavior without operating components near avoidable limits
- high-quality power delivery and PSU design
- acoustics compatible with sustained professional use
- mature drivers and broad OS/tool compatibility
- avoiding expenditure on features that are unlikely to provide material long-term value

For expensive components, ask not only whether they are faster today, but whether they improve the probability that the machine remains reliable, capable and easy to maintain over the intended lifetime.

## Budget and procurement

- Planning budget level: **30,000 lei**
- Location: **Iași, Romania**
- Self-assembled
- Existing NVIDIA GeForce RTX 3060 12 GB will be reused initially

The 30,000 lei figure is **not a hard cap and not a spending target**. The preferred outcome is to remain meaningfully below it when doing so does not compromise the workstation's technical objectives.

Cost should not drive component selection ahead of workload fit, stability, reliability, acoustics, expansion capability, endurance or longevity. More expensive parts are acceptable when they provide a concrete and durable benefit.

If the configuration approaches or exceeds 30,000 lei, the standard of justification becomes substantially higher: the additional cost should buy a credible long-term benefit in performance, reliability, endurance, serviceability, expansion headroom or reduced operational risk. A build at that price level should be designed explicitly as a long-term investment with an approximately **10-year useful-life objective**.

Do not spend extra for prestige, unused specifications, extreme-overclocking capability, marginal benchmark gains, or features likely to become irrelevant before they provide practical value.

If an otherwise justified configuration exceeds 30,000 lei, identify the cost driver and explain what durable benefit it buys before accepting the higher total. Do not automatically compromise core requirements, but do not allow price escalation without a concrete reliability/performance/longevity story either.

The build should preserve the **256 GB architectural memory target**, but it does not have to purchase that capacity immediately when the market price is disproportionate. Memory capacity is the preferred budget-release valve because it can be increased later without weakening the CPU/platform, motherboard, chassis, cooling, storage or PSU architecture. The initial memory kit should be treated as replaceable rather than forcing the eventual 256 GB configuration to reuse it.

## Reliability principles

These are governing evaluation principles:

- **Stability outranks short-term peak performance.**
- Prefer mature, well-understood components and firmware over newly introduced features with limited field history when the practical benefit is small.
- Prefer conservative stock or near-stock operation; avoid manual overclocking as a design objective.
- Do not rely on marginal memory-controller settings, unusually high SoC/memory voltages or fragile training behavior to achieve a headline RAM speed.
- Prioritize memory stability over headline memory speed, especially at 256 GB.
- Prefer two-DIMM configurations for the initial lower-capacity purchase where practical, both to reduce memory-controller loading and to avoid filling all four slots with small DIMMs.
- **System-level ECC is desirable for this workstation if it is implemented end-to-end and operationally observable.** Treat ECC as a strong preference, not yet a hard requirement, until ECC UDIMM availability, motherboard support, stable operating behavior and OS-visible error reporting are verified at the relevant capacity.
- Do not treat DDR5 on-die ECC as equivalent to system-level ECC; on-die ECC protects errors internal to the DRAM device and does not provide the same end-to-end protection across the memory path.
- Prefer cooling solutions that sustain expected loads with thermal and acoustic headroom rather than merely preventing throttling.
- Prefer storage with appropriate endurance, power-loss/data-integrity characteristics, firmware maturity and sustained-write behavior for VM/container/build workloads.
- Evaluate whether workload separation across physical drives is operationally useful before deciding drive count/capacity.
- Prefer a high-quality PSU with electrical and thermal headroom over sizing tightly to nominal consumption.
- Size the PSU for the selected platform plus a plausible future GPU rather than choosing wattage in advance.
- Design for good chassis airflow, dust management, low component temperature and maintainability.
- Avoid unnecessary small fans, pumps or other wear items when a simpler solution can meet the thermal objective; when such parts are justified, favor replaceability and proven reliability.
- Evaluate UPS protection as part of the complete system power design.
- Maintain external backups; RAID is not a backup.
- Treat BIOS/firmware updateability, recovery mechanisms and long-term vendor support as material motherboard-selection criteria.

## Platform evaluation criteria

### CPU/platform

**Selected:** AMD Ryzen 9 9950X3D on AM5.

Downstream component decisions should optimize around this platform unless the CPU/platform decision is explicitly reopened.

### Motherboard

Only consider AM5 motherboards whose **manufacturer officially specifies support for at least 256 GB of system memory**.

This remains a hard eligibility criterion because 256 GB is the architectural endpoint the build must preserve even if the initial purchase starts lower.

Motherboard evaluation should cover:

- BIOS/AGESA maturity with the Ryzen 9 9950X3D
- high-density DIMM support and QVL coverage
- realistic 256 GB behavior, including supported topology and data rate
- memory training/boot behavior with four high-density DIMMs
- conservative long-duration power-delivery and VRM thermal behavior
- PCIe/M.2 lane topology and sharing
- preservation of a strong primary-GPU path for the future AI objective
- availability of CPU-connected x8/x8 slot bifurcation where practical
- physical slot spacing and compatibility with very large/high-power future GPUs
- useful expansion after multiple NVMe drives are populated
- networking controller quality and driver maturity
- USB4/high-speed external I/O where useful
- ECC implementation and observability if supported
- virtualization/IOMMU behavior
- debug/recovery features, including BIOS recovery/Flashback where available
- long-term firmware support and serviceability

A premium motherboard is justified only by concrete benefits such as better validated high-capacity memory behavior, more useful PCIe/storage topology, superior networking, operationally useful ECC, stronger recovery/serviceability features, materially better long-term firmware support, or a demonstrably more robust implementation. Extreme-overclocking features alone have little value for this build.

### Memory

**Architectural target: 256 GB. Minimum initial purchase: 64 GB as 2×32 GB.**

The exact initial capacity above that floor, DIMM kit, operating data rate and ECC/non-ECC choice remain open.

The memory review should determine:

- the best stable eventual 256 GB configuration for the selected 9950X3D + motherboard combination
- the best-value initial two-DIMM configuration at 64 GB, 96 GB or 128 GB based on current market pricing
- whether 4×64 GB is the practical/required 256 GB topology and what operating speed is realistically stable
- motherboard QVL and vendor support evidence for 64 GB DIMMs
- JEDEC versus EXPO/XMP trade-offs at 256 GB
- **whether a 256 GB ECC UDIMM configuration is available, validated and operationally useful**
- whether the motherboard exposes correctable/uncorrectable ECC events to Windows/Linux in a way that can be monitored
- memory-training and boot-time implications
- safe/conservative voltage requirements
- Romanian/EU availability and price
- whether ECC should be pursued for the initial kit or reserved for the eventual high-capacity configuration

Stability is more important than headline memory speed. The 256 GB endpoint should remain technically viable even if the initial purchase starts at 64–128 GB for economic reasons.

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
- data-integrity and power-loss characteristics where they materially improve long-term reliability

Previously discussed **2 TB system + 4 TB work/VM NVMe** is a candidate architecture only.

### GPU

- Reuse the existing **NVIDIA GeForce RTX 3060 12 GB** initially.
- Preserve a credible upgrade path to a future **very high-performance, high-VRAM GPU for local AI training/inference**.
- Ensure the motherboard, case, PSU and cooling choices do not unnecessarily constrain that upgrade.
- Do not replace the GPU merely to optimize gaming performance unless requirements change.
- Future AI-oriented GPU evaluation should emphasize VRAM, CUDA/software compatibility, sustained compute performance, power, thermals and physical fit.
- Multi-GPU AI is not a current requirement; if it later becomes necessary, reassess whether AM5 remains the correct platform rather than accepting severe lane/power/layout compromises.

### Networking and I/O

For a 10-year-oriented system, evaluate:

- wired Ethernet speed and controller quality
- Wi-Fi / Bluetooth only if useful
- Linux/WSL friendliness where relevant
- high-speed external I/O such as USB4 where justified
- sufficient rear and front I/O
- usable PCIe expansion after storage devices are installed
- topology/lane sharing rather than connector count alone
- whether onboard networking avoids consuming PCIe expansion needed for future accelerator/GPU use
- driver maturity and long-term support expectations

## Decision philosophy

Each component review should answer:

1. What does the workload actually require?
2. Which architectures/classes of component satisfy it reliably?
3. Which features materially improve reliability, performance, serviceability, endurance or longevity?
4. Which features are merely premium positioning or short-term benchmark optimization?
5. What compatibility or topology constraints does the choice impose on other components?
6. Which option best satisfies the technical requirements, and what does each additional price increment materially buy?
7. If the more expensive option is selected, is the benefit durable enough to justify the cost over a roughly 10-year ownership horizon?
8. Does the selected configuration operate conservatively, with sufficient thermal, electrical and memory-stability headroom?
9. Does the choice preserve the secondary future-AI upgrade path without compromising the primary development workstation?
10. What must be validated after purchase to establish a stable baseline?

When performance and stability conflict, **prefer stability unless the performance loss is material enough to affect the workstation's core purpose**.

A model mentioned in earlier discussions should be treated as a **candidate to compare**, not as the baseline that alternatives must displace, unless it is explicitly recorded as selected in `docs/decisions.md`.
