# Build Requirements

## Scope

This is a **new build from scratch** for a long-lived professional workstation.

Fixed architecture decisions:

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5;
- **memory:** 128 GB from day one as **2×64 GB DDR5 UDIMM / 1DPC**;
- **active-work storage:** **1–2 TB NVMe on a CPU-direct M.2 x4 path**;
- **system storage:** about **1 TB**, NVMe preferred but SATA acceptable when that produces a better motherboard/value trade-off;
- **GPU:** reuse the existing RTX 3060 12 GB for as long as it remains useful/reliable;
- **host OS:** Windows 11 Pro x64 with WSL2 + Ubuntu 26.04.1 LTS;
- **UPS:** none in the initial BOM.

Open items include the exact motherboard, RAM kit/ECC verdict, storage models, premium 750/850 W PSU and final case reconfirmation.

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
- local AI only when it becomes concretely useful; cloud AI/training is an acceptable alternative.

## Design philosophy

Target a long useful life, approximately ten years where economically sensible, but **do not pre-buy speculative capability**.

Prioritize:

- stability and mature firmware;
- conservative stock operation;
- serviceability and replaceable wear items;
- thermal/electrical margin appropriate to real loads;
- memory stability over headline frequency;
- storage reliability/endurance appropriate to role;
- sensible I/O without paying for unused bandwidth;
- real backup and recovery;
- utility per leu rather than prestige.

## Memory requirements

Final configuration:

**128 GB = 2×64 GB DDR5 UDIMM / 1DPC.**

No temporary stage, no planned four-DIMM expansion, no 256 GB requirement.

Exact kit priorities:

- stable 2×64 operation with 9950X3D and selected board;
- conservative JEDEC behavior;
- sane voltage;
- good board/QVL evidence where available;
- reasonable physical height with NH-D15 G2;
- normal warranty/availability;
- ECC only if exact support and OS-visible reporting are credible without compromising stability/value.

## Motherboard requirements

The prior Creator-class/256 GB/multi-GPU feature set is **not** a baseline.

### Required / strongly preferred

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

The actual internet connection is below 1 Gb/s and local network throughput is irrelevant.

Therefore:

- **1 GbE is sufficient**;
- 2.5 GbE is a harmless/common bonus;
- do not pay a meaningful premium for 5/10 GbE;
- networking speed should not eliminate an otherwise better-value board.

### VRM / overclocking

The workstation will run the 9950X3D stock/conservatively. Require a competent, cool-running VRM, but **do not reward phase-count marketing, extreme current capability, LN2/OC controls or other enthusiast overclocking features**.

## Storage requirements

### Active-work SSD

Hard topology requirement:

- one **CPU-direct M.2 x4** path;
- it must coexist with the primary GPU without reducing the GPU's intended link.

Capacity:

- **1 TB sufficient**;
- **2 TB preferred when incremental price/value is attractive**;
- 4 TB not required initially.

Quality:

- TLC strongly preferred;
- DRAM desirable when reasonably priced;
- mature firmware;
- strong sustained/mixed behavior;
- sensible endurance/warranty;
- Gen4 sufficient; Gen5 optional only when effectively free/useful.

### System drive

Target around **1 TB**.

NVMe is preferred when naturally available, but **SATA SSD is acceptable** if a second clean M.2 path would otherwise force a worse/more expensive motherboard.

Optimize for reliability, headroom, mature firmware, warranty and price—not peak sequential bandwidth.

### Bulk/cold storage

Add only when needed via spare M.2, SATA SSD/HDD, external storage or NAS. Existing old HDDs may be reused after health checks for infrequently accessed data, but never as the sole copy of important information.

No RAID requirement; maintain independent backup/version-control protection.

## GPU / expansion requirements

Reuse the RTX 3060 for as long as it remains useful/reliable.

There is **no current plan to buy a higher-end GPU** merely because the platform can support one. Gaming is secondary and cloud AI availability reduces the need to provision aggressively for local training.

When/if a future GPU replacement occurs:

- retire the RTX 3060 rather than designing around dual-GPU operation;
- reevaluate PSU requirements at that time if necessary;
- CPU x8/x8 is not a motherboard requirement;
- do not pre-size today's platform for a hypothetical 500–600 W flagship.

## PSU requirements

Reopen selection around **premium 750 W and 850 W ATX 3.1 units**.

- 750 W is a legitimate long-term baseline;
- 850 W is preferred only when the premium is modest or the exact model is materially better acoustically/electrically;
- 1000–1200 W is not justified merely for speculative GPU headroom.

Prioritize:

- excellent electrical platform/protections;
- ATX 3.1/current transient handling;
- mature design and long warranty;
- quiet operation;
- current cabling/revision clarity.

## UPS / power protection

**No UPS in the initial BOM.**

Short outages are operationally acceptable and there is no need to keep working through them.

Use a reputable **plug-in surge protector / surge-protected power strip** at the workstation as the practical point-of-use protection measure. No electrical-installation modifications are part of this build. Understand that point-of-use surge protection is not equivalent to coordinated building-level SPD protection and relies on a sound protective-earth connection.

## Cooling

High-end air cooling remains preferred. The Noctua NH-D15 G2 standard is selected. No pump/liquid dependency unless a real requirement appears.

## Chassis

Airflow, serviceability, dust management and normal single-GPU compatibility remain important. The North XL is still selected but deserves one final value/size check because the old very-large-future-GPU requirement has weakened.

## Budget and procurement

Planning level remains approximately 30,000 lei, neither a cap nor a spending target. Maximum three providers overall; default target two hardware providers. Exact SKU/revision and warranty clarity outrank small nominal savings.

## Decision philosophy

For every premium ask:

1. Does the real workload need it?
2. Does it materially improve stability, serviceability, endurance or performance?
3. Is the benefit durable over ownership?
4. Can the capability be added/replaced later more cheaply if it ever becomes necessary?
5. Are we paying for a concrete requirement or for a hypothetical future scenario?

When performance and stability conflict, prefer stability unless the performance loss materially affects the workstation's core purpose.
