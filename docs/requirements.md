# Build Requirements

## Scope

This is a **new build from scratch** for a long-lived professional workstation.

The following architecture decisions are fixed:

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5;
- **memory:** **128 GB from day one as 2×64 GB DDR5 UDIMM / 1DPC**;
- **storage roles:** **~1 TB system/tools NVMe + 4 TB work/data NVMe from day one**;
- **GPU:** reuse the existing NVIDIA GeForce RTX 3060 12 GB initially;
- **future GPU path:** one very high-performance/high-VRAM NVIDIA-class discrete GPU, not a multi-GPU workstation;
- **host OS:** Windows 11 Pro x64 with WSL2 + Ubuntu 26.04.1 LTS.

The exact motherboard, exact 2×64 GB memory kit, ECC/non-ECC verdict and exact SSD models remain open until the current optimization pass closes them.

Previously discussed parts and configurations are candidates only unless explicitly recorded as selected in `docs/decisions.md`.

## Workload priority

### Primary

- very heavy Java software development, including codebases with millions of lines;
- IntelliJ IDEA and Android Studio;
- Maven and Gradle builds;
- large automated test suites;
- static analysis and annotation processing;
- multiple concurrent JVM processes and local services;
- Docker/container workloads;
- WSL2;
- Android Emulator;
- local databases;
- occasional virtual machines.

### Secondary

- occasional PC gaming;
- future local AI experimentation, inference and model work using a substantially more capable discrete GPU.

Gaming and AI are secondary to development stability and workstation longevity.

## Longevity and design philosophy

Target approximately **10 years of useful life** for the core workstation where economically sensible.

This does not mean every component must remain untouched for ten years. It means expensive choices should earn their cost through durable performance, stability, serviceability, reliability, expansion or avoided replacement—not prestige or short-lived benchmark leadership.

Prioritize:

- conservative operation;
- firmware/driver maturity;
- stability under long sustained workloads;
- serviceability and replacement availability;
- thermal and electrical margin;
- standard, replaceable wear items where practical;
- memory stability rather than headline DDR5 frequency;
- storage reliability and sensible endurance;
- useful I/O and expansion without paying for unused topology;
- mature OS/tool compatibility;
- real backup and recovery rather than pseudo-redundancy.

Do **not** spend merely because the planning budget has headroom.

## Budget and procurement

- Planning level: approximately **30,000 lei**.
- Location: Iași, Romania.
- Self-assembled.
- Existing RTX 3060 reused initially.
- Maximum **three providers overall**; target **two hardware providers** where practical.
- PC Garage, eMAG, Altex, EvoMAG and other reputable Romanian/EU retailers may be used according to exact SKU, stock, delivered price and warranty clarity.
- For eMAG, include **Genius/free-delivery value** when comparing eligible offers.
- A third hardware provider should normally require material net savings or materially better exact-SKU/revision/warranty certainty.
- Software such as Windows may use a separate provider at a lower savings threshold because it has negligible RMA lifecycle burden.

The 30,000 lei figure is neither a hard cap nor a spending target. Higher prices are acceptable only where the extra cost buys a concrete durable benefit.

## Reliability principles

- **Stability outranks short-term peak performance.**
- Prefer mature components/firmware over newly introduced features when the practical benefit is small.
- Keep the CPU stock/conservative; no manual overclocking objective.
- Avoid marginal memory-controller settings or unnecessarily high SoC/memory voltages.
- Boot RAM at Auto/JEDEC during commissioning and validate extensively before any optional profile tuning.
- System-level ECC is desirable only if implemented end-to-end, stable with the exact 2×64 GB kit and operationally observable in the OS. DDR5 on-die ECC is not equivalent.
- Prefer cooling with sustained thermal/acoustic headroom and replaceable fans.
- Prefer storage with mature firmware, appropriate endurance and sensible thermal behavior.
- Maintain external/network/cloud backups as appropriate. **RAID is not backup.**
- Treat BIOS recovery/Flashback, diagnostics and long-term firmware support as material motherboard criteria.

## Memory requirements

The final memory configuration is fixed:

**128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC).**

There is:

- no Phase-1 temporary RAM;
- no planned 64 GB stage;
- no planned 4-DIMM expansion;
- no 256 GB architectural requirement.

The exact kit should be selected for:

- stable 2×64 GB operation with the selected motherboard/9950X3D;
- conservative JEDEC behavior;
- low/normal operating voltage;
- motherboard QVL/vendor evidence where available;
- sensible physical height with the NH-D15 G2;
- manufacturer warranty and availability;
- ECC only if exact-module support and OS-visible reporting are credible and the value/stability trade-off is favorable.

Do not pay materially for EXPO/XMP headline speed unless there is a demonstrated workload benefit and stability remains excellent.

## Motherboard requirements

Only AM5 boards compatible with the 9950X3D and the final 2×64 GB topology are eligible.

The old requirement to prove 4×64 GB / 256 GB operation is removed.

Evaluate:

- BIOS/AGESA maturity with Ryzen 9 9950X3D;
- strong evidence for stable **2×64 GB / 128 GB** operation;
- ECC implementation/reporting if ECC remains a candidate;
- conservative long-duration VRM behavior;
- BIOS Flashback/recovery and useful POST diagnostics;
- networking controller quality and driver maturity;
- USB4/high-speed external I/O where useful;
- virtualization/IOMMU behavior;
- long-term firmware support;
- PCIe/M.2 topology with the final two-drive storage arrangement;
- preservation of a full-performance primary GPU path;
- physical spacing for a future very large/high-power GPU;
- useful extra M.2/PCIe capacity for later additive expansion;
- value relative to cheaper boards with equivalent relevant capabilities.

### Required storage topology

The selected motherboard must support at least two M.2 x4 devices simultaneously such that:

- the **4 TB work SSD** can preferably use a CPU-direct x4 connection;
- the **~1 TB system SSD** can use a chipset-connected x4 connection;
- populating the selected two M.2 slots does **not reduce the primary GPU from x16**.

Gen5 storage capability is optional. Do not pay a motherboard premium merely to obtain more Gen5 M.2 bandwidth than the workload needs.

CPU-connected x8/x8 bifurcation is useful future-facing functionality when inexpensive, but it is not a hard requirement because serious multi-GPU work would trigger a platform reassessment rather than forcing AM5 into an unsuitable role.

## Storage requirements

The final role architecture is fixed at initial assembly:

### System/tools drive

Target approximately **1 TB NVMe**.

Optimize for:

- reputable manufacturer;
- mature firmware;
- normal warranty path;
- capacity headroom;
- sensible price;
- TLC preferred where cost-effective;
- normal NVMe responsiveness.

DRAM and flagship sequential throughput are **not requirements**. Good Gen3/Gen4 NVMe performance is sufficient. A chipset-connected x4 M.2 slot is acceptable.

The system volume contains Windows, applications/tools, page file/crash-dump infrastructure, servicing space and ordinary profile data.

### Work/data drive

Target **4 TB NVMe from day one**.

Optimize for:

- TLC strongly preferred;
- DRAM-equipped design preferred where the price difference is reasonable;
- mature firmware/tooling;
- strong sustained/mixed behavior;
- endurance appropriate for development caches, WSL2, containers, VMs and databases;
- reasonable thermals;
- five-year-class warranty where available;
- CPU-direct x4 connection preferred.

Gen4 is sufficient. Gen5 should be purchased only when its premium is negligible or a demonstrated workload materially benefits.

Expected work-drive data includes repositories, Maven/Gradle caches/build output, WSL2 VHDX and Linux-native working sets, container stores, Android SDK/AVDs, VMs, local databases, games, datasets and AI models where practical.

### Expansion and backup

The initial ~1 TB + 4 TB arrangement is not a lifetime capacity ceiling. Storage should expand additively through extra drives when needed rather than replacing the initial pair merely to add capacity.

No RAID is required. Important data must have independent backup/version-control protection.

## Future local AI upgrade objective

Preserve a credible path from the RTX 3060 to one very high-performance/high-VRAM GPU without replacing otherwise suitable core components unnecessarily.

Implications:

- primary GPU should retain full expected CPU-connected bandwidth with the selected storage configuration;
- case/airflow must accommodate a very large high-power GPU;
- PSU architecture should handle a plausible future 500–600 W-class accelerator;
- onboard networking can be valuable if it avoids consuming scarce expansion slots;
- GPU VRAM remains the primary AI capacity constraint; 128 GB system RAM is useful for development/data preparation/offload workflows but does not substitute for VRAM;
- retain NVIDIA/CUDA compatibility as an important consideration for the future GPU.

If future requirements become serious multi-GPU training, reopen the **platform** and consider Threadripper/workstation/server options rather than compromising the AM5 build.

## Cooling, power and chassis requirements

### Cooling

- high-end air cooling is preferred for simplicity and serviceability;
- CPU cooling must sustain stock/conservative 9950X3D operation without unacceptable throttling/noise;
- avoid pump/liquid dependencies unless a real thermal requirement justifies them.

### PSU

- size for the selected system plus the future single high-power GPU;
- ATX 3.1 / PCIe 5.1 / current 12V-2x6;
- strong warranty and mature platform;
- avoid unnecessary wattage inflation beyond useful transient/aging margin.

### Chassis

- airflow-first;
- large future-GPU clearance;
- standard replaceable fans;
- good dust management and service access;
- enough motherboard/M.2 airflow for long sustained workloads.

### UPS

UPS capacity should remain useful through the future GPU upgrade and support graceful OS shutdown.

## Networking and I/O

Evaluate:

- wired Ethernet speed and controller quality;
- long-term driver support;
- high-speed external I/O such as USB4 where useful;
- adequate rear/front I/O;
- usable PCIe expansion after the two initial NVMe drives are installed;
- lane sharing rather than connector count alone;
- onboard networking value where it avoids an add-in NIC.

10 GbE is useful if obtained at sensible incremental cost but should not by itself justify a large motherboard premium without a concrete use case.

## Decision philosophy

Each component review should answer:

1. What does the workload actually require?
2. Which component classes satisfy it reliably?
3. Which features materially improve stability, performance, serviceability, endurance or longevity?
4. Which features are merely premium positioning or benchmark optimization?
5. What topology/compatibility constraints does the choice impose?
6. What does each additional price increment materially buy?
7. Is that benefit likely to remain useful over the ownership horizon?
8. Does the configuration operate conservatively with adequate thermal/electrical/memory margin?
9. Does it preserve the secondary future-AI path without compromising the primary workstation?
10. What must be validated after purchase?

When performance and stability conflict, **prefer stability unless the performance loss materially affects the workstation's core purpose**.
