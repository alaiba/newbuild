# Storage Deep Dive

Status: **Storage architecture selected / exact SSD models provisional**

## Selected architecture

The storage design is a **staged two-drive NVMe architecture**:

1. **Phase 1 / initial purchase:** one **2 TB high-quality PCIe 4.0 x4 NVMe SSD** for Windows, applications, development tools and the initial working set.
2. **Long-term work drive:** add a separate **4 TB-or-larger high-quality NVMe SSD** for source trees, Maven/Gradle caches, WSL2/Docker data, Android SDK/emulators, VMs, local databases and other write-heavy/project data.

The 4 TB work drive does **not** need to be purchased on day one. Unlike temporary Phase-1 RAM, the initial 2 TB SSD is not throw-away: it remains useful permanently as the system/tools drive after the larger work drive is added.

This staged layout is selected because it preserves the desired long-term separation while avoiding an unnecessary ~6 TB initial storage purchase during a period of elevated SSD pricing.

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

The initial 2 TB purchase should therefore be treated as permanent infrastructure, unlike the deliberately disposable Phase-1 RAM.

## Long-term capacity: 2 TB + 4 TB or larger

The current long-term planning point is:

- **2 TB system/tools SSD**
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

**PCIe 4.0 is the selected default for the initial SSD.**

Current high-end Gen4 drives already deliver roughly 7 GB/s-class sequential throughput and excellent low-latency random I/O. Current Gen5 drives can approximately double headline sequential bandwidth, but the workstation benefit is much smaller for ordinary OS, IDE, source-tree, build-cache and mixed random-I/O workloads.

A 2025/2026 comparison of Samsung's 9100 PRO operating at Gen5 versus Gen4 found only a small difference in a light PCMark system-drive workload, while current Romanian pricing still places premium 4 TB Gen5 models materially above strong Gen4 alternatives.

Therefore:

- do **not** pay a large Gen5 premium for the initial 2 TB drive;
- preserve a CPU-connected Gen5 M.2 slot for the future work drive;
- reassess Gen5 when the 4 TB+ work drive is purchased, because prices and workloads may have changed by then.

Gen5 is an **available future option**, not a requirement.

## Endurance

The workload warrants a good endurance rating, but extreme TBW should not become another prestige metric.

Current examples:

- Samsung 990 PRO 4 TB: **2400 TBW**, 5-year warranty;
- WD Black SN850X 4 TB: **2400 TBW**, 5-year warranty;
- Seagate FireCuda 530R 4 TB: **5050 TBW**, 5-year warranty and three years of Rescue Data Recovery Services where available;
- Seagate FireCuda 530R 2 TB: **2400 TBW**.

Even the 2400 TBW class provides very large write headroom for a development workstation over a decade. The FireCuda's much higher 4 TB endurance is attractive, but we should not pay a large premium for TBW that the actual workload is unlikely to consume.

Endurance is therefore a **minimum-quality criterion**, not a reason by itself to choose the most expensive drive.

## Current serious SSD families — August 2026

Exact models remain provisional because local SSD pricing is unusually volatile.

### Samsung 990 PRO

Role: mature all-around Gen4 reference.

Strengths:

- TLC + DRAM;
- excellent random and mixed workload performance;
- 2 TB and 4 TB capacities;
- 4 TB model is single-sided;
- 5-year / 2400 TBW rating at 4 TB;
- Samsung firmware/update tooling;
- broad market history.

Current Romanian snapshot:

- 2 TB: roughly **1.8–2.0k lei** at competitive offers;
- 4 TB: roughly **3.6k lei**.

Do not buy the optional SSD heatsink version for this workstation unless it is cheaper; both motherboard finalists already provide substantial M.2 heatsinks.

### WD Black SN850X

Role: current Gen4 price/performance challenger.

Strengths:

- TLC + DRAM;
- excellent random-I/O behavior;
- mature Gen4 platform;
- 5-year warranty;
- 4 TB endurance class of 2400 TBW.

Current Romanian snapshot:

- 2 TB: roughly **1.77–1.9k lei** for competitive offers;
- 4 TB: unusually attractive offers have appeared around **2.6–3.2k lei**, depending on heatsink/version/retailer.

If that 4 TB price advantage remains when the work drive is purchased, it is difficult to justify paying much more merely for another flagship badge.

### Seagate FireCuda 530R

Role: endurance/workstation-oriented Gen4 candidate.

Strengths:

- TLC + DRAM (Phison E18 platform);
- consistent sustained-write behavior;
- 2 TB rated at **2400 TBW**;
- 4 TB rated at **5050 TBW**;
- 5-year warranty;
- three years of Rescue Data Recovery Services where available;
- SeaTools diagnostic support.

A recent 2026 Tom's Hardware review characterized the 2 TB 530R as a capable, consistent workstation-oriented drive. The underlying E18 platform is older and has historical firmware/controller caveats across the broader market, so current Seagate firmware should be verified before purchase rather than treating TBW alone as proof of reliability.

Current Romanian pricing is inconsistent: competitive 2 TB offers have appeared around the same class as the 990 PRO/SN850X, while 4 TB offers can range roughly **3.4–4.0k lei or more**. Buy only when the actual retailer/price is sensible.

### Crucial T500

Role: efficient high-end Gen4 alternative.

Strengths:

- TLC + DRAM;
- excellent client performance;
- good efficiency;
- 2 TB and 4 TB versions available.

Current Romanian snapshot is roughly **1.6–2.2k lei for 2 TB** and around **2.9–3.1k lei for 4 TB**, depending on retailer/version. It remains a strong price-dependent alternative.

### Samsung 9100 PRO / high-end Gen5

Role: Gen5 control, not current recommendation.

The 9100 PRO is a capable and comparatively efficient Gen5 drive, but current Romanian 4 TB pricing is roughly **4.2k lei or higher**. Its headline bandwidth does not currently justify the premium for our initial system drive.

Re-evaluate this class only when buying the future work drive or if a real workload emerges that can exploit sustained Gen5 bandwidth.

## Provisional initial-drive recommendation

Do **not** hard-code a single SSD SKU months before purchase because the current market is unusually volatile.

At purchase time, choose among the mature 2 TB TLC + DRAM Gen4 candidates using this order of criteria:

1. current firmware/health history;
2. reputable Romanian/EU retailer and full warranty;
3. price;
4. sustained/random performance;
5. endurance once the above are satisfactory.

Current provisional shortlist:

1. **Samsung 990 PRO 2 TB** — safest broad-market baseline;
2. **WD Black SN850X 2 TB** — equally credible if cheaper;
3. **Seagate FireCuda 530R 2 TB** — particularly attractive if priced near the first two and current firmware is confirmed;
4. **Crucial T500 2 TB** — strong alternative when materially cheaper.

No meaningful productivity benefit currently justifies a large premium among these models.

## Motherboard slot assignment

The storage architecture fits both motherboard finalists without compromising the future GPU path.

### ASUS ProArt X870E-Creator WiFi

Preferred eventual assignment:

- **M.2_3 (chipset PCIe 4.0 x4): 2 TB system/tools SSD**
- **M.2_1 (CPU PCIe 5.0 x4): future 4 TB+ work/VM SSD**

This intentionally leaves `M.2_2` unused because it shares the CPU graphics-lane group and would reduce the primary GPU from x16 when populated. `M.2_4` remains available for later bulk/scratch storage.

### ASRock X870 Taichi Creator

Preferred eventual assignment:

- **M2_3 (chipset PCIe 4.0 x4): 2 TB system/tools SSD**
- **M2_1 (CPU PCIe 5.0 x4): future 4 TB+ work/VM SSD**

This leaves `M2_2` free and avoids its USB4 bandwidth-sharing trade-off. `M2_4` remains available for later lower-priority storage, subject to its sharing with `PCIE3`.

### Why put the work drive on M.2_1

The system/tools SSD does not require a CPU-direct Gen5 slot. Reserving the fastest, cleanest CPU-connected M.2 slot for the future work drive gives us the best path for heavy VM/container/database/scratch I/O and lets us adopt a future Gen5 drive without rearranging the rest of the topology.

During Phase 1, install the initial 2 TB system SSD directly in the intended chipset-connected system slot rather than occupying M.2_1 temporarily and moving it later.

## Thermal policy

Use the motherboard's integrated M.2 heatsinks rather than paying extra for SSD-specific decorative/heatsink variants unless the pre-heatsinked model is actually cheaper.

During bring-up:

- verify SSD firmware before loading important data;
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
- **Phase 1:** 2 TB permanent system/tools SSD.
- **Long-term second drive:** 4 TB or larger work/VM/container/data SSD, purchased when needed.
- **Initial interface:** PCIe 4.0 x4 NVMe.
- **Primary-drive NAND class:** TLC preferred.
- **Primary-drive controller class:** DRAM-equipped high-end client design preferred.
- **Gen5:** deferred; preserve the slot and reassess when buying the work drive.
- **RAID:** not required.
- **Exact SSD model:** provisional until purchase-time price/firmware check.

## Promotion / purchase checks

Before ordering the initial SSD:

1. confirm current model firmware and any known unresolved health/corruption issues;
2. confirm full vendor/retailer warranty in Romania/EU;
3. compare the 2 TB 990 PRO, SN850X, FireCuda 530R and T500 at current prices;
4. prefer the bare drive where the motherboard heatsink will be used;
5. confirm the motherboard's M.2_3 heatsink supports the exact drive thickness;
6. record the SSD firmware version at bring-up;
7. establish backups before treating the workstation as the sole copy of important data.
