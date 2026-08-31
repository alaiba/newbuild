# Build Requirements

## Scope

This is a **new build from scratch** for a long-lived professional workstation.

Fixed architecture decisions:

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5;
- **memory:** 128 GB from day one as **2×64 GB DDR5 UDIMM / 1DPC**;
- **cooler:** **Thermalright Phantom Spirit 120 standard**;
- **chassis:** **be quiet! Pure Base 501 Airflow Black `BG074`**;
- **initial case airflow:** two included 140 mm PWM fans, front intake + rear exhaust;
- **active-work storage:** **1–2 TB NVMe on a CPU-direct M.2 x4 path**;
- **system storage:** about **1 TB**, NVMe preferred but SATA acceptable when that produces a better motherboard/value trade-off;
- **GPU:** reuse the existing RTX 3060 12 GB for as long as useful/reliable;
- **host OS:** Windows 11 Pro x64 with WSL2 + Ubuntu 26.04.1 LTS;
- **UPS:** none in the initial BOM.

Open items include the exact motherboard, RAM kit/ECC verdict, storage models, premium 750/850 W PSU and exact plug-in surge protector.

## Workload priority

### Primary
- very heavy Java development across codebases with millions of lines;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- multiple JVMs/local services;
- WSL2 and container workloads;
- Android Emulator;
- local databases;
- occasional VMs.

### Secondary
- occasional gaming;
- local AI only when concretely useful; cloud AI/training is an acceptable alternative.

## Design philosophy

Target a long useful life, approximately ten years where economically sensible, but **do not pre-buy speculative capability**.

Prioritize stability, mature firmware, conservative operation, serviceability, replaceable wear items, appropriate thermal/electrical margin, memory stability, storage reliability/endurance and utility per leu.

## Memory requirements

Final configuration:

**128 GB = 2×64 GB DDR5 UDIMM / 1DPC.**

No temporary stage, planned four-DIMM expansion or 256 GB requirement.

Exact kit priorities:

- stable 2×64 operation with 9950X3D and selected board;
- conservative JEDEC behavior and sane voltage;
- good board/QVL evidence where available;
- clean physical compatibility with the Phantom Spirit 120;
- normal warranty/availability;
- ECC only if exact support and OS-visible reporting are credible without compromising stability/value.

## Cooling requirements

Exact cooler is selected: **Thermalright Phantom Spirit 120, standard model**.

Requirements/policy:

- sustain stock/conservative 9950X3D operation under long development/test workloads without material thermal throttling;
- acceptable acoustics under sustained work;
- clean compatibility with final RAM/motherboard;
- use replaceable fans and simple long-lived construction;
- no silent substitution with Phantom Spirit 120 SE/EVO or another variant without review;
- no liquid/pump dependency unless measured operation later establishes a real need.

## Chassis and airflow requirements

Exact chassis is selected: **be quiet! Pure Base 501 Airflow Black `BG074`**.

Relevant envelope:

- ATX or smaller motherboard;
- approximately **178 mm CPU-cooler clearance**;
- approximately **368 mm GPU clearance**;
- two included 140 mm PWM fans;
- practical 3.5-inch HDD support for later cold storage.

Initial airflow is **one included 140 mm front intake + one included 140 mm rear exhaust**. Do not pre-buy more fans. Add another front intake only if closed-case measurement shows a material benefit.

## Motherboard requirements

The prior Creator-class/256 GB/multi-GPU feature set is **not** a baseline.

### Required / strongly preferred

- **ATX or smaller** for the selected case;
- AM5 + Ryzen 9 9950X3D support;
- mature BIOS/AGESA;
- strong evidence for stable **2×64 GB / 128 GB / 1DPC**;
- one **CPU-direct M.2 x4** path for the active-work SSD that does not reduce the main GPU link;
- competent VRM thermals for stock/conservative operation;
- BIOS Flashback/recovery strongly preferred;
- useful diagnostics/serviceability preferred;
- sufficient SATA and/or additional storage connectivity for later bulk storage;
- normal wired Ethernet reliability.

### Explicit non-requirements

- 256 GB/four-DIMM validation;
- 5 GbE or 10 GbE;
- CPU x8/x8 bifurcation;
- multiple clean Gen5 M.2 slots;
- extreme-overclocking power delivery;
- motherboard features selected mainly for a hypothetical 500–600 W future GPU.

### Networking

Internet is below 1 Gb/s and LAN throughput is irrelevant.

- **1 GbE is sufficient**;
- 2.5 GbE is a harmless/common bonus;
- do not pay a meaningful premium for 5/10 GbE.

### VRM / overclocking

The 9950X3D will run stock/conservatively. Require competent, cool-running power delivery; do not reward phase-count marketing, extreme current capability or enthusiast OC features.

## Storage requirements

### Active-work SSD

Hard topology requirement:

- one **CPU-direct M.2 x4** path;
- it must coexist with the primary GPU without reducing the intended GPU link.

Capacity:

- **1 TB sufficient**;
- **2 TB preferred when incremental price/value is attractive**;
- 4 TB not required initially.

Prefer TLC, mature firmware, good sustained/mixed behavior, sensible endurance/warranty and Gen4 unless Gen5 is effectively free/useful.

### System drive

Target around **1 TB**. NVMe is preferred, but **SATA SSD is acceptable** if a second clean M.2 path would otherwise force a worse/more expensive motherboard.

### Bulk/cold storage

Add only when needed via spare M.2, SATA SSD/HDD, external storage or NAS. Existing old HDDs may be reused after health checks for infrequently accessed data, but never as the sole copy of important information.

No RAID requirement; maintain independent backup/version-control protection.

## GPU / expansion requirements

Reuse the RTX 3060 for as long as useful/reliable.

When/if a future GPU replacement occurs:

- retire the RTX 3060 rather than designing around dual-GPU operation;
- reevaluate PSU/case only if the chosen future GPU actually requires it;
- CPU x8/x8 is not a motherboard requirement;
- do not pre-size today's platform for a hypothetical 500–600 W flagship.

## PSU requirements

Reopen selection around **premium 750 W and 850 W ATX 3.1 units**.

- 750 W is a legitimate long-term baseline;
- 850 W wins only when the premium is modest or the exact model is materially better;
- 1000–1200 W is not justified merely for speculative GPU headroom.

Prioritize electrical platform/protections, current transient handling, mature design, long warranty, quiet operation and revision/cabling clarity.

## UPS / power protection

**No UPS in the initial BOM.** Short outages are operationally acceptable.

Use a reputable **plug-in surge protector / surge-protected power strip** as the practical point-of-use protection measure. No electrical-installation modifications are part of this build.

## Budget and procurement

Planning level remains approximately 30,000 lei, neither a cap nor a spending target. Maximum three providers overall; default target two hardware providers. Exact SKU/revision and warranty clarity outrank small nominal savings.

## Decision philosophy

For every premium ask:

1. Does the real workload need it?
2. Does it materially improve stability, serviceability, endurance or performance?
3. Is the benefit durable over ownership?
4. Can it be added/replaced later more cheaply if it becomes necessary?
5. Are we paying for a concrete requirement or a hypothetical scenario?

When performance and stability conflict, prefer stability unless the performance loss materially affects the workstation's core purpose.
