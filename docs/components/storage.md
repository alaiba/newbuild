# Storage Deep Dive

Status: **Storage architecture selected / initial SSD selected**

## Selected architecture

The storage design is a **staged two-drive NVMe architecture**:

1. **Phase 1 / initial purchase:** **Samsung 990 PRO 2 TB (`MZ-V9P2T0BW`)**, a permanent PCIe 4.0 x4 NVMe system/tools SSD for Windows, applications, development tools and the initial working set.
2. **Long-term work drive:** add a separate **4 TB-or-larger high-quality NVMe SSD** for source trees, Maven/Gradle caches, WSL2/Docker data, Android SDK/emulators, VMs, local databases and other write-heavy/project data.

The 4 TB work drive does **not** need to be purchased on day one. Unlike temporary Phase-1 RAM, the initial 2 TB SSD is not throw-away: it remains useful permanently as the system/tools drive after the larger work drive is added.

This staged layout is selected because it preserves the desired long-term separation while avoiding an unnecessary ~6 TB initial storage purchase during a period of elevated SSD pricing.

## Selected initial SSD: Samsung 990 PRO 2 TB

Exact model:

- **Samsung 990 PRO 2 TB**
- manufacturer part number: **`MZ-V9P2T0BW`**
- bare M.2 2280 drive; use the motherboard's integrated M.2 heatsink
- role: permanent **system/tools** SSD
- interface: PCIe 4.0 x4 NVMe
- NAND/controller class: TLC + DRAM, mature high-end client platform

This selection is closed as of **2026-08-31**. The 990 PRO is preferred over the remaining Gen4 shortlist because it combines mature firmware/tooling, strong mixed/random performance, adequate endurance, a five-year-class warranty and broad market history. The goal is not to extract the last benchmark point; it is to buy a well-understood permanent system drive that should remain straightforward to maintain for the life of the workstation.

### Retailer policy

For this SSD, procurement preference is:

1. **PC Garage** first;
2. **eMAG** second;
3. use another reputable Romanian/EU retailer only if availability or price makes the preferred sources materially unattractive.

When the PC Garage versus eMAG price difference is small, prefer **PC Garage** rather than optimizing for the last few lei.

The exact SSD may be reopened only for a material pre-purchase issue such as an unresolved firmware/health problem, loss of normal warranty/availability, or an unusually large price premium relative to an equally credible alternative.

## Why two physical drives eventually

The second drive is not justified primarily by benchmark throughput. Modern high-end NVMe drives are already fast enough that ordinary Java builds and IDE work rarely require multiple drives merely for aggregate bandwidth.

The stronger reasons are operational:

- **OS/recovery separation:** Windows can be repaired/reinstalled or the system SSD can be replaced without making the work/VM drive part of that operation.
- **Workload isolation:** WSL2/Docker virtual disks, Android emulators, VMs, databases and build caches can generate substantial random and sustained writes without competing with OS/application housekeeping on the same NAND/controller.
- **Thermal distribution:** sustained I/O is split across two controllers and two M.2 locations rather than concentrating all activity on one SSD.
- **Capacity management:** large VM/container/data workloads can grow independently of the OS/tools volume.
- **Future replacement:** either drive can be upgraded independently.

This separation is **not a backup strategy**. Source code, important data and VM/database state that matters must still be backed up externally or to another system/service.

## Initial capacity: 2 TB

A 1 TB system drive would boot and run the machine, but it is unnecessarily tight for a workstation expected to host Android tooling, WSL2/Docker, local SDKs, large caches and potentially temporary VM images before the second drive is installed.

A **2 TB initial drive** provides enough room to operate comfortably during the one-drive phase and remains a useful long-term system/tools volume after the 4 TB+ work drive is added.

The initial 2 TB purchase is therefore permanent infrastructure, unlike the deliberately disposable Phase-1 RAM.

## Long-term capacity: 2 TB + 4 TB or larger

The current long-term planning point is:

- **2 TB Samsung 990 PRO system/tools SSD**
- **4 TB work/VM/container/data SSD**

The 4 TB figure is a planning point, not a hard ceiling. When the second SSD is actually purchased, re-evaluate current project/VM/container usage and SSD pricing. Moving directly to 8 TB may become rational if capacity needs or price/TB change materially.

Do not buy a 4 TB work drive early merely to satisfy the architectural diagram.

## NAND/controller policy

For the two primary internal workstation drives, prefer:

- **TLC NAND**;
- a **DRAM-equipped** high-end controller design where practical;
- mature firmware and vendor update/diagnostic tooling;
- five-year-class warranty;
- strong sustained-write behavior after pseudo-SLC cache exhaustion;
- adequate but not extreme TBW endurance;
- standard M.2 2280 form factor and motherboard heatsink compatibility.

### QLC

QLC is not prohibited for future bulk/secondary storage, but it is **not preferred for either of the two primary workstation drives**. The price saving would need to be substantial enough to justify weaker sustained-write behavior and lower endurance characteristics.

### DRAM-less drives

Modern DRAM-less NVMe drives can be excellent for many client workloads, but they are not the preferred default here. With VMs, containers, build caches, databases and a long ownership target, a mature TLC + DRAM design is a simple and conservative choice when the price difference is reasonable.

## PCIe 4.0 versus PCIe 5.0

**PCIe 4.0 is selected for the initial SSD.**

Current high-end Gen4 drives already deliver roughly 7 GB/s-class sequential throughput and excellent low-latency random I/O. Current Gen5 drives can approximately double headline sequential bandwidth, but the workstation benefit is much smaller for ordinary OS, IDE, source-tree, build-cache and mixed random-I/O workloads.

Therefore:

- do **not** pay a large Gen5 premium for the initial 2 TB drive;
- preserve a CPU-connected Gen5 M.2 slot for the future work drive;
- reassess Gen5 when the 4 TB+ work drive is purchased, because prices and workloads may have changed by then.

Gen5 is an **available future option**, not a requirement.

## Endurance

The workload warrants a good endurance rating, but extreme TBW should not become another prestige metric.

The selected 990 PRO provides ample endurance for a development workstation. Higher-TBW alternatives remain useful reference points for a future work drive, but the build should not pay a large premium for write endurance that the real workload is unlikely to consume.

Endurance is therefore a **minimum-quality criterion**, not a reason by itself to choose the most expensive drive.

## Alternatives considered

The following remain credible alternatives if the 990 PRO selection ever has to be reopened:

### WD Black SN850X

A mature TLC + DRAM Gen4 competitor with strong random-I/O behavior, a five-year warranty and similar endurance class. It remains the primary substitute if the 990 PRO develops a material procurement or firmware issue.

### Seagate FireCuda 530R

A workstation/endurance-oriented Gen4 candidate with TLC + DRAM and unusually high TBW at some capacities. Its endurance is attractive, but TBW alone does not justify displacing a mature, broadly supported system-drive choice.

### Crucial T500

An efficient high-end Gen4 alternative with TLC + DRAM and excellent client performance. It remains price-dependent rather than preferred over the selected 990 PRO.

### Samsung 9100 PRO / high-end Gen5

A capable Gen5 control, not a current recommendation for the system SSD. Re-evaluate this class only when buying the future work drive or if a real workload emerges that can exploit sustained Gen5 bandwidth.

## Motherboard slot assignment

The selected storage architecture fits the **ASUS ProArt X870E-Creator WiFi** without compromising the future GPU path.

Preferred eventual assignment:

- **M.2_3 (chipset PCIe 4.0 x4): Samsung 990 PRO 2 TB system/tools SSD**
- **M.2_1 (CPU PCIe 5.0 x4): future 4 TB+ work/VM SSD**

This intentionally leaves `M.2_2` unused because it shares the CPU graphics-lane group and would reduce the primary GPU from x16 when populated. `M.2_4` remains available for later bulk/scratch storage.

### Why put the work drive on M.2_1

The system/tools SSD does not require a CPU-direct Gen5 slot. Reserving the fastest, cleanest CPU-connected M.2 slot for the future work drive gives us the best path for heavy VM/container/database/scratch I/O and lets us adopt a future Gen5 drive without rearranging the rest of the topology.

During Phase 1, install the 990 PRO directly in the intended chipset-connected system slot rather than occupying M.2_1 temporarily and moving it later.

## Thermal policy

Use the motherboard's integrated M.2 heatsink rather than paying extra for an SSD-specific heatsink variant.

During bring-up:

- verify and update SSD firmware before loading important data;
- record the installed firmware version;
- monitor SMART/composite temperature under sustained writes;
- confirm no thermal throttling during long file copies, builds or VM activity;
- maintain airflow across the motherboard/M.2 area as part of the selected airflow-first chassis strategy.

## Data-integrity and recovery policy

Consumer high-end NVMe SSDs generally do not provide enterprise-class power-loss protection. The storage reliability plan therefore depends on the system as a whole:

- quality PSU;
- UPS;
- filesystem/application consistency mechanisms;
- version control;
- external backups;
- SMART/health monitoring;
- firmware maintenance.

Do not treat RAID1 as a substitute for backup. No RAID configuration is required for the initial workstation.

## Selected conclusions

- **Architecture:** staged two-drive NVMe layout.
- **Phase 1 system/tools SSD:** **Samsung 990 PRO 2 TB (`MZ-V9P2T0BW`) — Selected**.
- **Long-term second drive:** 4 TB or larger work/VM/container/data SSD, purchased when needed; exact model deferred.
- **Initial interface:** PCIe 4.0 x4 NVMe.
- **Primary-drive NAND class:** TLC preferred.
- **Primary-drive controller class:** DRAM-equipped high-end client design preferred.
- **Gen5:** deferred; preserve M.2_1 and reassess when buying the work drive.
- **RAID:** not required.
- **Retailer preference:** PC Garage first, eMAG second when the price difference is small.

## Purchase / bring-up checks

Before ordering/installing the selected SSD:

1. confirm no new unresolved 990 PRO firmware/health issue has appeared;
2. confirm normal Romanian/EU warranty and reputable-seller stock;
3. compare PC Garage and eMAG, preferring PC Garage when the difference is small;
4. buy the bare `MZ-V9P2T0BW` drive and use the ProArt M.2 heatsink;
5. install it in `M.2_3`;
6. update/record firmware during bring-up;
7. establish backups before treating the workstation as the sole copy of important data.
