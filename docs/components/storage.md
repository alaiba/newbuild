# Storage Deep Dive

Status: **Single-drive active-storage architecture selected / exact primary SSD selected / cold SATA storage retained**

## Decision

Buy **one internal NVMe drive from day one**:

- **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4, TLC, DRAM-equipped;
- install it in the board's CPU-direct **`M.2_1` PCIe 5.0 x4** slot;
- use the non-heatsink SSD variant under the ASUS motherboard M.2 heatsink.

Do **not** buy a second NVMe merely to split Windows/tools from active work. Do **not** buy a small SSD as a cache for another SSD. Do **not** build automatic SSD tiering/Storage Spaces for the initial machine.

Current storage use is approximately **600 GB**. Even with more ambitious development workloads, the foreseeable active-storage requirement is not expected to exceed **2 TB** soon. Existing slower SATA drives will remain available for cold/bulk data.

## Why the architecture changed

The previous two-drive plan assumed that system/tools and active development data deserved permanent physical separation. Further analysis showed that this imposed complexity without solving a concrete capacity or performance problem:

- the current machine uses only about 600 GB in total;
- a 2 TB primary SSD leaves roughly 1.4 TB of nominal growth headroom before filesystem overhead/free-space policy;
- the selected motherboard leaves two additional M.2 sockets free for additive expansion;
- existing SATA drives can hold archives, old projects, installers, inactive VMs and other cold data;
- modern Windows already uses abundant RAM as a filesystem cache;
- a separate SSD cache in front of another SSD provides little real benefit when the entire active working set already fits on one very fast NVMe.

The simpler architecture also eliminates cache warm-up, block-cache driver dependence, duplicated NAND writes, write-back failure semantics, partition/cache sizing and opaque hot/cold placement.

## Selected primary SSD

**Crucial T710 2 TB `CT2000T710SSD8`**.

Role:

- Windows 11;
- installed applications and development tools;
- source repositories;
- Gradle caches/build outputs;
- Maven local repository;
- IntelliJ/Android Studio state and indexes;
- WSL2 distributions/VHDX;
- container images/layers/volumes;
- Android SDK and active emulator images;
- active VMs/databases;
- current games and other latency-sensitive data.

### Why 2 TB

1 TB would fit today's data, but it would leave only modest headroom once Android emulators, WSL2, containers, games, caches and larger projects accumulate.

2 TB is therefore the capacity sweet spot: materially more operating headroom without paying the large absolute premium for 4 TB capacity that is not expected to be used soon.

4 TB is explicitly **not** an initial requirement. Storage remains additive: if a real future need appears, `M.2_2`, `M.2_3`, SATA or external/NAS storage can be added then.

### Why Gen5 now

Earlier policy treated Gen5 as unnecessary because premium Gen4 drives already provide excellent workstation performance. That remains technically true.

However, current Romanian pricing makes the premium for a credible 2 TB flagship Gen5 drive small enough that the selected T710 offers a durable benefit without distorting the budget. The board already provides CPU-direct PCIe 5.0 x4 in `M.2_1`, so using that capability requires no platform compromise.

The selection is not based on expecting 2x application performance from 2x sequential bandwidth. Java/Android development will often be CPU-, memory- or cache-bound. The value case is instead:

- flagship TLC NAND and DRAM-equipped design;
- strong random/mixed and sustained-write behavior;
- high available sequential bandwidth for large transfers/VM/container workloads;
- no need to preserve the Gen5 slot for a hypothetical future device;
- small current price premium over premium Gen4 alternatives.

## PCIe topology

With the Ryzen 9 9950X3D and selected ASUS board:

- **`M.2_1`: CPU PCIe 5.0 x4 — selected T710 2 TB**;
- **`M.2_2`: CPU PCIe 4.0 x4 — empty, future expansion**;
- **`M.2_3`: chipset PCIe 4.0 x4 — empty, future expansion**;
- **4× SATA — existing/later cold storage**.

Populating `M.2_1` does not reduce the primary GPU from its intended x16 path on this configuration.

## Cold/bulk storage

Existing healthy SATA SSD/HDD devices may be reused for data whose latency is not important:

- archived repositories;
- old build artifacts;
- inactive VMs;
- ISO images and installers;
- historical datasets;
- media;
- backup staging;
- other infrequently accessed local material.

Before reuse, inspect SMART/health data and the physical/interface condition of old drives. Important data must not exist only on an old SATA device merely because SMART currently reports healthy.

The SATA devices are **not** part of an automatic tier with the NVMe drive. Data placement remains explicit and predictable.

## Why SSD caching was rejected

Several cache topologies were considered:

1. small fast NVMe caching a large HDD;
2. small Gen5 SSD caching a larger Gen4 SSD;
3. partitioning a flagship Gen5 SSD into L2 cache + explicit hot tier.

SSD caching can be valuable when a small fast device fronts a much larger, genuinely slow capacity tier and the active working set is much smaller than the backing store. That is not the present situation.

Here the entire expected active dataset fits within the 2 TB primary SSD. An SSD-to-SSD cache would therefore add complexity while accelerating storage that is already extremely fast. Sub-1 TB high-end SSDs also often have lower NAND parallelism and sustained write performance than larger drives, so "smaller" does not automatically mean "faster."

A read cache would usually be redundant with Windows' RAM cache and the fast primary NVMe. Write-back caching would add a period during which acknowledged writes exist only on the cache device, creating an unnecessary failure mode.

If future local capacity grows into the tens of terabytes and a large HDD becomes part of the active working set, SSD read caching can be revisited then.

## QLC / DRAM-less policy

For the selected primary drive:

- **TLC is required/preferred**;
- **DRAM-equipped design is preferred**;
- mature firmware and vendor support matter;
- strong sustained writes and mixed/random behavior matter more than a peak sequential benchmark alone.

QLC and DRAM-less drives remain valid candidates for future bulk/read-heavy expansion when the price advantage is meaningful, but they are not preferred for the primary workstation SSD.

## RAID and backup

**No RAID is required.**

RAID1 would protect against one physical SSD failure, but it would not protect against accidental deletion, replicated corruption, malware, application mistakes, theft or catastrophic machine loss. It also adds complexity.

The reliability strategy is instead:

- version control;
- external/network/cloud backup as appropriate;
- SMART/health monitoring;
- firmware maintenance;
- application/filesystem consistency mechanisms.

Do not treat any internal SSD or reused HDD as the sole copy of important data.

## Thermal policy

Use the motherboard M.2 heatsink with the bare/non-heatsink T710 variant.

During bring-up:

- update and record SSD firmware;
- monitor SMART/health data;
- monitor sustained-write temperature;
- verify no material thermal throttling under representative active-work loads;
- maintain normal motherboard/case airflow.

## Explicitly superseded storage decisions

The following are no longer purchase targets or architectural requirements:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as the selected system SSD;
- separate approximately 1 TB system/tools SSD;
- separate 1–2 TB active-work SSD;
- permanent two-NVMe system/work separation;
- buying a small SSD specifically as an L2 cache;
- automatic SSD tiering / Storage Spaces for the initial machine;
- a fixed 4 TB high-performance work SSD;
- buying high-performance NVMe capacity for archival/cold data;
- reserving `M.2_1` for a hypothetical later Gen5 upgrade;
- ProArt-specific storage slot assignments as architectural requirements.

## Selected conclusions

- **Architecture:** one primary internal NVMe SSD from initial assembly.
- **Exact SSD:** **Crucial T710 2 TB `CT2000T710SSD8`**.
- **Topology:** CPU-direct `M.2_1` PCIe 5.0 x4 under motherboard heatsink.
- **Capacity:** 2 TB selected; 4 TB rejected as unnecessary initial spend.
- **Second/third M.2:** remain empty for additive future expansion.
- **Cold storage:** reuse healthy existing SATA drives where appropriate.
- **SSD cache/tiering:** no.
- **RAID:** no.
- **Future capacity:** additive only when actual use justifies it.

## Remaining storage procurement checks

Before ordering:

1. verify the exact part is `CT2000T710SSD8` rather than the factory-heatsink variant;
2. refresh Romanian price and warranty/supplier quality;
3. confirm normal retail/new condition;
4. during commissioning, update firmware and validate temperatures/SMART under representative workloads.
