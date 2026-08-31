# Memory Deep Dive

Status: **Phase-1 purchase target nominated / 256 GB endpoint deferred**

## Fixed strategy

The memory strategy has two deliberately independent levels:

- **Architectural endpoint:** preserve a credible path to **256 GB** system memory.
- **Phase-1 minimum:** **32 GB** in any simple, stable configuration that reliably boots and runs the workstation.

Phase-1 RAM is explicitly **temporary commissioning memory**. It does not need to resemble the eventual 256 GB configuration, use ECC, maximize frequency, or preserve an upgrade path through the same DIMMs.

If buying new, **2×16 GB** is preferred when it costs about the same as alternatives because it preserves dual-channel bandwidth. However, **1×32 GB or any other stable 32 GB-or-larger configuration is acceptable** if it is materially cheaper or more convenient.

This lets memory act as the build's strongest budget-release valve without weakening the CPU/platform, motherboard, chassis, cooling, storage or PSU architecture.

The Phase-1 kit should be treated as **replaceable**, not as a sunk-cost constraint on the eventual 256 GB configuration. Reuse or resale later is a bonus, not a design requirement.

## Phase-1 purchase-readiness pass — 2026-08-31

The Romanian DDR5 market is currently unusually expensive. Ordinary 32 GB desktop DDR5 kits that would normally be commodity purchases are commonly listed around 2.3–3.0k lei or more.

### Current preferred Phase-1 target

**KLEVV FIT V 32 GB (2×16 GB) DDR5-5600 CL30 — `KD5AGU880-56K300F`**

Reason:

- meets the selected 32 GB floor;
- 2×16 GB preserves dual-channel operation;
- low-profile desktop UDIMM form factor;
- DDR5-5600 is conservative enough for easy AM5 operation;
- AMD EXPO is available but is not required for Phase 1;
- current Romanian offers were around **2,390 lei**, materially below many Crucial/Kingston alternatives in the same capacity class.

### Operating policy

For commissioning:

1. install in the motherboard-recommended two-DIMM slots;
2. update the ProArt BIOS first;
3. boot at **Auto/JEDEC** settings;
4. do not enable EXPO until baseline stability is established;
5. if Auto/JEDEC is stable, leaving it there is fully acceptable because this is temporary RAM;
6. run an extended memory test before treating the system as commissioned.

The advertised CL30/EXPO profile is not part of the requirement. The purchase is being made for capacity, dual-channel topology, low-profile fit and acceptable price.

### Price controls observed on 2026-08-31

- KLEVV FIT V 32 GB (2×16) DDR5-5600 CL30: ~**2,390 lei** current low offer.
- Crucial 32 GB (1×32) DDR5-5600 CL46 `CT32G56C46U5`: ~**2,390–2,700 lei** current offers.
- Crucial 32 GB (2×16) DDR5-5600 CL46 `CT2K16G56C46U5`: ~**2,834 lei+**.
- Kingston Fury Beast 32 GB (2×16) DDR5-5600 CL36: ~**2,300 lei+** at the best observed listing, but with higher-voltage performance profiling and no durable advantage for a temporary kit.

Because this market is volatile, the exact Phase-1 SKU remains a **purchase-time provisional target rather than a long-term architectural decision**. If another reputable 2×16 GB DDR5 kit is materially cheaper on order day, use that instead, provided it is ordinary desktop UDIMM and boots stably at conservative settings.

## ECC posture

**System-level ECC is a strong preference for the eventual long-term memory configuration, but not a requirement for Phase 1.**

The rationale is reliability rather than performance. A long-lived workstation with large JVM heaps, multiple VMs/containers, databases and long-running build/test/analysis workloads has meaningful memory-resident state worth protecting. ECC can reduce the risk that a memory fault becomes a silent data corruption, unexplained process/test failure, VM crash or corrupted in-memory/page-cache state.

The Ryzen 9 9950X3D supports ECC when the motherboard implements it. DDR5 on-die ECC is not equivalent to system-level ECC: on-die ECC only corrects errors internal to individual DRAM devices and does not provide the same end-to-end protection across the module/bus/controller path.

For the eventual high-capacity configuration, prefer ECC UDIMM if all of the following are true:

- the selected motherboard officially supports ECC UDIMM with the 9950X3D;
- the target capacity is credibly supported/validated;
- correctable and uncorrectable ECC events are exposed to Windows/Linux in a way that can actually be monitored;
- stable operation does not require marginal tuning;
- the cost and data-rate trade-off are reasonable relative to the reliability benefit.

Do not select ECC merely because a board can boot ECC DIMMs. If ECC reporting is hidden/non-functional, capacity support is weak, or the available configuration is materially less stable than a proven non-ECC configuration, prefer the more reliable overall system rather than the ECC label.

For **Phase 1**, do not pay a material premium for ECC.

## Eventual 256 GB configuration

The endpoint remains **4×64 GB or equivalent**.

At upgrade time:

1. reassess the ProArt's current BIOS/AGESA and QVL;
2. identify the best exact 4×64 GB configuration then available;
3. prefer ECC UDIMM if exact 64 GB modules, four-DIMM support, stability and OS-visible reporting are all credible;
4. otherwise choose a strongly validated 4×64 GB non-ECC configuration;
5. start at JEDEC/Auto and accept 5200 MT/s or lower if required for stability;
6. avoid EXPO/XMP merely to preserve headline frequency at 256 GB;
7. perform extended memory stability testing;
8. if ECC is used, verify Windows WHEA and/or Linux EDAC/RAS reporting before treating ECC as operationally useful.

**RDIMM is incompatible with this AM5 platform.** Many 64 GB server ECC products are RDIMMs and must not be confused with ECC UDIMMs.

## Workload implications

A 32 GB Phase-1 configuration is acceptable because that capacity is already sufficient for the current working environment. The main limitation is concurrency headroom for combinations of IntelliJ, Android Studio, emulators, Docker/WSL2, local services and VMs. That is acceptable in Phase 1 because the kit is intentionally temporary.

The 256 GB endpoint remains valuable for larger JVM heaps, more concurrent JVMs/IDEs/services/VMs, local databases/data processing and future AI support workflows.

## Upgrade policy

Do **not** assume the Phase-1 kit will be expanded into the final 256 GB configuration. Replace/resell/reuse it if convenient when the 256 GB upgrade is performed.
