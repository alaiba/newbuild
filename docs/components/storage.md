# Storage Deep Dive

Status: **Two-drive architecture selected / exact SSD models open**

## Decision

Buy the final two-drive storage architecture from day one:

1. **System/tools SSD:** approximately **1 TB NVMe**, optimized for reliability, capacity headroom and price rather than flagship benchmark speed.
2. **Work/data SSD:** **4 TB NVMe**, optimized for sustained development/VM/container/database workloads, endurance and value.

This supersedes the previous staged plan of buying a 2 TB Samsung 990 PRO first and adding a 4 TB work drive later.

The exact SSD models remain open for the next optimization pass.

## Why the architecture changed

The previous 2 TB system drive was sized to carry the entire machine temporarily: Windows, tools, repositories, build caches, WSL2, containers, Android data, VMs and other working data until a second drive was purchased.

That temporary role no longer exists. The dedicated work drive will be present from initial assembly, so the system drive can be sized for its permanent role instead of for a transitional one-drive phase.

The user's current machine provides useful empirical evidence. Its roughly decade-old 240 GB Intel SATA SSD is nearly full, but storage speed and boot time are not a significant pain point. The actual long-term problem is **capacity headroom**, not lack of sequential throughput.

The new system also has **128 GB RAM**, giving Windows and applications abundant memory for filesystem caching and working sets. Once applications and frequently accessed data are warm in memory, the system SSD is not continuously on the critical path.

Therefore the storage budget should not be spent on flagship OS-drive throughput merely because it is available.

## System/tools SSD role

Target capacity: **approximately 1 TB**.

The capacity is a value target rather than a prestige target. A 500 GB drive could be technically sufficient for a cleanly separated system volume, but 1 TB is preferred whenever the price premium is modest because it provides substantially more long-term servicing/update/application headroom.

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

A good Gen3 or mainstream Gen4 NVMe drive is already more than fast enough for the role. There is no requirement for a 7 GB/s flagship drive, and **no justification for paying a Gen5 premium for the OS drive**.

The system SSD may use a **chipset-connected M.2 x4 slot** without concern.

## Work/data SSD role

Target initial capacity: **4 TB**.

Expected contents include:

- source repositories;
- Gradle caches and build outputs;
- Maven local repository;
- WSL2 distributions/VHDX and Linux-native high-I/O working sets;
- container images/layers/volumes;
- Android SDK components and AVD/emulator images where relocation is supported;
- virtual machines;
- local databases;
- large test datasets;
- games;
- local AI models/datasets when practical;
- other project or scratch data with substantial capacity or I/O demand.

### Work-drive quality priorities

Prefer:

- **TLC NAND**;
- **DRAM-equipped design** where the price difference is reasonable;
- mature firmware and vendor diagnostic/update tooling;
- strong mixed/random and sustained-write behavior;
- solid endurance appropriate for build/cache/VM/container activity;
- five-year-class warranty where available;
- standard M.2 form factor compatible with motherboard heatsinks.

TBW is a useful minimum-quality/endurance signal, not a prestige metric. Do not pay a large premium merely for the largest published TBW number if the practical workload is unlikely to consume it.

## PCIe generation policy

**PCIe 4.0 is sufficient for both drives.**

The work drive should receive the better storage connection because it is where the sustained and random development I/O is expected to occur. Prefer a **CPU-direct x4 M.2 slot** for it.

Gen5 is a bonus, not a requirement. A Gen5 work SSD should be selected only if:

- its price premium over a comparably credible Gen4 drive is negligible; or
- a demonstrated workload materially benefits from the additional bandwidth.

Do not select a motherboard or SSD merely to preserve a synthetic sequential-throughput number.

## Motherboard topology requirement

The motherboard optimization should now require:

1. at least **two simultaneously usable M.2 x4 slots** for the initial drives;
2. one preferably **CPU-direct x4** slot for the 4 TB work SSD;
3. one chipset-connected x4 slot is fully acceptable for the ~1 TB system SSD;
4. populating these two selected slots must **not reduce the primary GPU from x16**;
5. integrated M.2 heatsinks are preferred;
6. additional M.2 capacity for future additive expansion is desirable but should not command a large premium.

Exact M.2 slot numbers will be assigned only after the motherboard is selected. Do not carry ProArt-specific `M.2_1` / `M.2_3` assumptions into another board without checking its lane-sharing table.

## Why two physical drives from day one

The objective is not aggregate benchmark throughput. It is operational separation:

- **OS/recovery separation:** Windows can be repaired/reinstalled without making the work volume part of the operation.
- **Workload isolation:** VMs, containers, databases, caches and build output do not share one NAND/controller with Windows housekeeping.
- **Capacity management:** work data can grow independently of the system volume.
- **Thermal distribution:** sustained activity is spread across two devices and motherboard locations.
- **Independent replacement:** either SSD can be replaced or expanded without forcing replacement of the other.

This is a permanent role separation, not a temporary Phase-1 arrangement.

## Expansion policy

The initial 1 TB + 4 TB layout is **not a lifetime storage-capacity ceiling**.

Storage is naturally additive. If future AI models, VMs, games, project data or archives require another 4 TB/8 TB/greater SSD, add another drive if the selected motherboard provides a suitable slot. There is no reason to discard the initial system or work SSD merely to expand capacity.

This differs from the RAM decision: RAM topology is deliberately fixed at 2×64 GB / 128 GB, while storage can expand cleanly through additional independent devices.

## QLC and DRAM-less policy

### System drive

QLC or DRAM-less designs are **not automatically rejected** for the system role. A mature implementation from a reputable vendor can be entirely adequate if the price saving is meaningful and endurance/reliability are appropriate.

TLC remains preferred when the incremental cost is modest.

### Work drive

For the primary 4 TB work drive, **TLC is strongly preferred** and a DRAM-equipped design is preferred when reasonably priced because sustained writes, VMs, containers, databases and build caches create a more demanding workload.

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

Do not treat either internal SSD as the sole copy of important data.

## Thermal policy

Use motherboard M.2 heatsinks where appropriate rather than paying extra for SSD heatsink variants unless the chosen drive/motherboard combination specifically benefits.

During bring-up:

- update and record SSD firmware;
- monitor SMART/health data;
- monitor sustained-write temperature;
- verify no material thermal throttling under representative work-drive loads;
- maintain normal motherboard airflow.

## Explicitly superseded storage decisions

The following are no longer purchase targets:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as the selected system SSD;
- a 2 TB system SSD justified by a temporary one-drive phase;
- buying the work SSD later;
- reserving a Gen5 drive as the preferred long-term work-drive class;
- ProArt-specific storage slot assignments as architectural requirements.

The 990 PRO remains a technically credible SSD and may still appear in price comparisons, but it must win on current role-specific value rather than incumbent status.

## Selected conclusions

- **Architecture:** two physical internal NVMe drives from initial assembly.
- **System/tools:** approximately **1 TB**, value/reliability/capacity optimized; exact model open.
- **Work/data:** **4 TB**, high-quality Gen4 TLC preferred; exact model open.
- **Work-drive topology:** CPU-direct x4 preferred.
- **System-drive topology:** chipset-connected x4 fully acceptable.
- **Gen5:** not required for either initial drive.
- **RAID:** no.
- **Future capacity:** additive through additional drives; no planned replacement of the initial pair merely to expand capacity.

## Next optimization questions

For the exact SSD pass:

1. identify the cheapest reputable ~1 TB system-drive candidates with mature firmware and normal warranty;
2. move to 1 TB over 500 GB whenever the incremental price is small;
3. compare serious 4 TB TLC work-drive candidates on price, sustained behavior, endurance, warranty and firmware maturity;
4. reject Gen5 premiums that do not buy a demonstrated workload benefit;
5. evaluate the two-drive lane topology on each motherboard finalist before selecting exact slots.
