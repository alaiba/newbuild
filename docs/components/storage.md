# Storage Deep Dive

Status: **Two-drive active-storage architecture selected / exact SSD models open / cold storage additive later**

## Decision

Buy two internal NVMe drives from day one:

1. **System/tools SSD:** approximately **1 TB NVMe**, optimized for reliability, capacity headroom and price rather than flagship benchmark speed.
2. **Active-work SSD:** **1 TB is sufficient; 2 TB is preferred when the absolute premium and price/TB are attractive**, optimized for sustained development/VM/container/database workloads, endurance and value.

Do **not** buy 4 TB of high-performance NVMe merely to hold data that is not part of the active working set.

If total local storage later becomes tight, add a third device for bulk/cold data. That device may be another chipset-connected NVMe, a SATA SSD or a healthy HDD depending capacity, price and access pattern.

The exact SSD models and whether the active-work SSD is 1 TB or 2 TB remain open for the next optimization pass.

## Why the architecture changed

The earlier 4 TB work-drive target conflated two different things:

- **active working data**, which benefits from low latency and strong random/sustained SSD behavior;
- **accumulated local data**, much of which may be infrequently accessed and does not justify premium storage.

For the primary workload, the high-performance tier only needs to contain current repositories and the surrounding development ecosystem. Source code itself is usually modest in capacity; the larger consumers are caches, container/WSL images, Android images, active VMs and databases.

A disciplined **1 TB active-work SSD is sufficient**. A **2 TB active-work SSD is the comfort choice** when its incremental price is modest. There is no architectural reason to jump directly to 4 TB.

The user's current machine also provides useful evidence: its decade-old 240 GB Intel SATA OS SSD is almost full, but boot/storage performance is not a significant pain point. The dominant issue is capacity management, not flagship throughput.

With **128 GB RAM**, Windows and development tools also have abundant memory for filesystem caching and working sets, further reducing the value of premium system-drive throughput.

## System/tools SSD role

Target capacity: **approximately 1 TB**.

Expected contents:

- Windows 11;
- installed applications and development-tool binaries;
- IDE binaries;
- JDKs and general SDK/tool installations that do not need to live with project data;
- drivers and firmware tools;
- normal user-profile data;
- page file and crash-dump infrastructure;
- Windows Update and servicing working space.

Do **not** move the entire Windows user profile merely to force separation. Move only large, well-understood workload stores whose applications support an explicit path/location.

### System-drive quality priorities

In order of importance:

1. reputable manufacturer and normal warranty path;
2. mature firmware and no unresolved reliability issue;
3. enough capacity to keep generous free space throughout ownership;
4. sensible price;
5. TLC preferred where price is reasonable;
6. normal NVMe random responsiveness;
7. DRAM cache is useful but **not mandatory** for this role;
8. peak sequential throughput is low priority.

A good Gen3 or mainstream Gen4 NVMe drive is already more than fast enough. There is no requirement for a flagship Gen4 drive and **no justification for paying a Gen5 premium for the OS drive**.

The system SSD may use a **chipset-connected M.2 x4 slot**.

## Active-work SSD role

Target capacity:

- **1 TB is technically sufficient and is the value baseline**;
- **2 TB is preferred when the price premium is modest enough to buy useful operating headroom without distorting the budget**;
- **4 TB is not an initial requirement**.

Expected contents include latency-sensitive and actively used data such as:

- current source repositories;
- Gradle caches and build outputs;
- Maven local repository;
- WSL2 distributions/VHDX and Linux-native high-I/O working sets;
- container images/layers/volumes;
- Android SDK components and active AVD/emulator images where relocation is supported;
- active virtual machines;
- active local databases;
- current large test datasets;
- currently used games or AI models when appropriate;
- other project/scratch data that materially benefits from SSD latency and throughput.

Old projects, inactive VMs, ISO images, installers, archives and similar low-frequency data do not need to remain on this drive.

### Active-work-drive quality priorities

Prefer:

- **TLC NAND**;
- **DRAM-equipped design** where the price difference is reasonable;
- mature firmware and vendor diagnostic/update tooling;
- strong mixed/random and sustained-write behavior;
- solid endurance appropriate for build/cache/VM/container activity;
- five-year-class warranty where available;
- standard M.2 form factor compatible with motherboard heatsinks.

TBW is a useful minimum-quality/endurance signal, not a prestige metric. Do not pay a large premium merely for the largest published TBW number.

## Bulk/cold-storage role

Bulk/cold storage is **not part of the initial performance requirement**.

Add it only when the active/system drives actually need relief. Appropriate data includes:

- archived repositories;
- old build artifacts;
- inactive VMs;
- ISO images and installers;
- historical datasets;
- media;
- old AI models/datasets not actively used;
- other infrequently accessed local material.

Suitable device classes include:

- spare chipset-connected NVMe SSD;
- SATA SSD;
- SATA HDD;
- external/NAS storage depending the use case.

Existing spinning disks may be reused after SMART/health inspection if their interface and physical condition are suitable. They should be treated as **convenience/bulk storage**, not trusted as the sole copy of important data simply because SMART currently reports healthy.

For old HDDs, important data must exist elsewhere as well.

## PCIe generation policy

**PCIe 4.0 is sufficient for both initial drives.**

The active-work SSD should receive the better storage connection because it is where sustained and random development I/O is expected. Prefer a **CPU-direct x4 M.2 slot** for it.

Gen5 is a bonus, not a requirement. A Gen5 work SSD should be selected only if:

- its price premium over a comparably credible Gen4 drive is negligible; or
- a demonstrated workload materially benefits from the additional bandwidth.

Do not select a motherboard or SSD merely to preserve a synthetic sequential-throughput number.

## Motherboard topology requirement

The motherboard optimization should require:

1. at least **two simultaneously usable M.2 x4 slots** for the initial SSDs;
2. one preferably **CPU-direct x4** slot for the active-work SSD;
3. one chipset-connected x4 slot is fully acceptable for the ~1 TB system SSD;
4. populating these two selected slots must **not reduce the primary GPU from x16**;
5. integrated M.2 heatsinks are preferred;
6. at least one practical later expansion route for bulk storage is desirable, whether additional M.2, SATA or both;
7. extra high-speed M.2 capacity should not command a large motherboard premium by itself.

Exact M.2 slot numbers will be assigned only after the motherboard is selected. Do not carry ProArt-specific labels into another board without checking its lane-sharing table.

## Why two physical SSDs from day one

The objective is operational separation rather than aggregate benchmark throughput:

- **OS/recovery separation:** Windows can be repaired/reinstalled without making the active-work volume part of that operation.
- **Workload isolation:** VMs, containers, databases, caches and build output do not share one NAND/controller with Windows housekeeping.
- **Capacity management:** active work can be managed independently of the system volume.
- **Thermal distribution:** sustained activity is spread across two devices and motherboard locations.
- **Independent replacement:** either SSD can be replaced without forcing replacement of the other.

This is a permanent role separation, not a temporary Phase-1 arrangement.

## Expansion policy

Storage capacity is deliberately **additive**.

When the active-work SSD starts accumulating data that is no longer active, move that material to a bulk/cold tier instead of buying an oversized performance SSD in advance.

A later third drive can be sized for capacity/value rather than latency. This may be a large inexpensive SSD or even an existing healthy HDD, depending the data.

This differs from the RAM decision: RAM topology is deliberately fixed at 2×64 GB / 128 GB, while storage can expand cleanly through independent devices.

## QLC and DRAM-less policy

### System drive

QLC or DRAM-less designs are **not automatically rejected** for the system role. A mature implementation from a reputable vendor can be adequate if the price saving is meaningful and endurance/reliability are appropriate.

TLC remains preferred when the incremental cost is modest.

### Active-work drive

For the primary active-work SSD, **TLC is strongly preferred** and a DRAM-equipped design is preferred when reasonably priced because sustained writes, VMs, containers, databases and build caches create a more demanding workload.

QLC belongs mainly in later bulk/read-heavy storage unless its price advantage becomes compelling.

## RAID and backup

**No RAID is required.**

RAID1 would protect against one physical SSD failure, but it would not protect against accidental deletion, replicated corruption, malware, application mistakes, theft or catastrophic machine loss. It also adds complexity.

The reliability strategy is instead:

- version control;
- external/network/cloud backup as appropriate;
- UPS-backed power;
- SMART/health monitoring;
- firmware maintenance;
- application/filesystem consistency mechanisms.

Do not treat any internal SSD or reused HDD as the sole copy of important data.

## Thermal policy

Use motherboard M.2 heatsinks where appropriate rather than paying extra for SSD heatsink variants unless the chosen drive/motherboard combination specifically benefits.

During bring-up:

- update and record SSD firmware;
- monitor SMART/health data;
- monitor sustained-write temperature;
- verify no material thermal throttling under representative active-work loads;
- maintain normal motherboard airflow.

## Explicitly superseded storage decisions

The following are no longer purchase targets:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as the selected system SSD;
- a 2 TB system SSD justified by a temporary one-drive phase;
- a fixed 4 TB high-performance work SSD;
- buying the active-work SSD later;
- reserving a Gen5 drive as the preferred work-drive class;
- buying high-performance NVMe capacity for archival/cold data;
- ProArt-specific storage slot assignments as architectural requirements.

The 990 PRO remains technically credible and may still appear in price comparisons, but it must win on role-specific value rather than incumbent status.

## Selected conclusions

- **Architecture:** two physical internal NVMe SSDs from initial assembly.
- **System/tools:** approximately **1 TB**, value/reliability/capacity optimized; exact model open.
- **Active work:** **1 TB sufficient; 2 TB preferred when the incremental cost is attractive**; high-quality Gen4 TLC preferred; exact capacity/model open.
- **Active-work topology:** CPU-direct x4 preferred.
- **System-drive topology:** chipset-connected x4 fully acceptable.
- **Gen5:** not required for either initial drive.
- **Bulk/cold storage:** add later only when needed; may use NVMe, SATA SSD or healthy HDD.
- **RAID:** no.
- **Future capacity:** additive; no planned replacement of the initial pair merely to expand capacity.

## Next optimization questions

For the exact SSD pass:

1. identify the cheapest reputable ~1 TB system-drive candidates with mature firmware and normal warranty;
2. compare **1 TB versus 2 TB active-work SSDs on absolute premium and price/TB**, not on an arbitrary fixed capacity target;
3. prioritize TLC, sustained behavior, endurance, warranty and firmware maturity for the active-work drive;
4. reject Gen5 premiums that do not buy a demonstrated workload benefit;
5. evaluate the two-drive lane topology and later bulk-storage expansion path on each motherboard finalist.
