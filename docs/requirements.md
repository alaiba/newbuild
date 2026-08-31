# Build Requirements

## Scope

This is a **new build from scratch** for a long-lived professional workstation.

Fixed architecture decisions:

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5;
- **motherboard:** ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`;
- **memory:** Crucial `CT2K64G56C46U5`, **128 GB = 2×64 GB DDR5-5600 / 1DPC / non-ECC**, native 1.1 V JEDEC;
- **cooler:** Thermalright Phantom Spirit 120 standard;
- **chassis:** be quiet! Pure Base 501 Airflow Black `BG074`;
- **initial airflow:** two included 140 mm PWM fans, front intake + rear exhaust;
- **primary storage:** **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe, installed in CPU-direct `M.2_1` under the motherboard heatsink;
- **storage architecture:** one primary NVMe initially; no separate cache/system/work SSD and no automatic SSD tiering;
- **cold/bulk storage:** reuse existing SATA drives where appropriate after health validation;
- **GPU:** reuse RTX 3060 12 GB for as long as useful/reliable;
- **host OS:** Windows 11 Pro x64 with WSL2 + Ubuntu 26.04.1 LTS;
- **UPS:** none initially.

Open items: premium 750/850 W PSU, exact plug-in surge protector and final provider/price consolidation.

## Workload priority

### Primary
- very heavy Java development across codebases with millions of lines;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- multiple JVMs/local services;
- WSL2, containers, Android Emulator, local databases and occasional VMs.

### Secondary
- occasional gaming;
- local AI only when concretely useful; cloud AI/training is acceptable.

## Design philosophy

Target a long useful life, approximately ten years where economically sensible, but **do not pre-buy speculative capability**.

Prioritize stability, mature firmware, conservative operation, serviceability, appropriate thermal/electrical margin, memory stability, storage endurance and utility per leu.

## Motherboard requirements — satisfied

Selected: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

The board satisfies:

- ATX fit in the selected case;
- Ryzen 9 9950X3D / Ryzen 9000 support with an actively maintained BIOS branch;
- 256 GB platform memory capacity and support categories covering 2×64 GB / DDR5-5600 configurations;
- primary CPU-connected **PCIe 5.0 x16** graphics path;
- CPU-connected `M.2_1` PCIe 5.0 x4 for the selected primary SSD;
- CPU-connected `M.2_2` PCIe 4.0 x4 for later expansion;
- chipset-connected `M.2_3` PCIe 4.0 x4 for later expansion;
- sufficient stock/conservative 9950X3D power delivery;
- BIOS FlashBack and Q-LED diagnostics;
- four SATA ports for existing/later cold storage;
- reliable 2.5 GbE, already beyond the actual network requirement.

The following are explicitly **not requirements**: B850 itself, 5/10 GbE, CPU x8/x8, a secondary PCIe x4 expansion slot, multiple Gen5 M.2 slots, extreme-overclocking power delivery and provisioning for a hypothetical 500–600 W future GPU.

The second physical x16 slot operates at chipset PCIe 4.0 x1. This is acceptable because no high-bandwidth add-in card has a planned use.

## Memory requirements — satisfied

Selected: **Crucial `CT2K64G56C46U5`**.

- 128 GB total;
- matched 2×64 GB DDR5 UDIMM;
- 1DPC, A2/B2;
- DDR5-5600 CL46-class native JEDEC operation;
- 1.1 V;
- non-ECC;
- low-profile physical design compatible with the Phantom Spirit 120.

Operating policy:

- current stable production BIOS;
- Auto/JEDEC first;
- no EXPO/XMP required;
- extended memory validation before commissioning;
- no voltage/timing tuning merely for benchmark gains.

### ECC verdict

The CPU and motherboard support ECC UDIMM, but the selected 128 GB / 2×64 GB topology uses non-ECC memory because practical current 64 GB ECC UDIMM availability is poor. Common 64 GB server parts are RDIMM and cannot be used on AM5.

Do not reduce capacity, populate four DIMMs or use incompatible RDIMM merely to obtain ECC.

## Cooling and chassis

Selected cooler: **Thermalright Phantom Spirit 120 standard**.

Selected chassis: **be quiet! Pure Base 501 Airflow Black `BG074`**.

Policy:

- stock/conservative 9950X3D;
- no liquid/pump dependency unless real measurements establish a need;
- no silent substitution of Phantom Spirit SE/EVO;
- use only the two included 140 mm case fans initially;
- add another front intake only if closed-case measurements justify it.

## Storage requirements — satisfied

Current storage use is approximately **600 GB**. Even allowing for more ambitious projects, the foreseeable active-storage requirement is not expected to exceed **2 TB** soon. Existing slower SATA drives will remain available for cold/bulk data.

### Primary SSD

Selected: **Crucial T710 2 TB `CT2000T710SSD8`**.

Requirements and role:

- install in CPU-direct `M.2_1` at PCIe 5.0 x4;
- use the bare/non-heatsink SSD variant under the ASUS motherboard M.2 heatsink;
- one filesystem may contain Windows, applications, repositories, Gradle/Maven caches, WSL2, containers, Android emulator data, active VMs/databases, games and other actively used data;
- TLC NAND and DRAM-equipped flagship-class behavior are preferred for sustained development workloads;
- 2 TB provides generous headroom over current usage without paying for unused 4 TB capacity;
- Gen5 is justified here because the live premium over credible premium Gen4 alternatives is small enough to use the board's CPU-direct Gen5 capability without distorting the budget.

### Deliberately rejected initial complexity

Do **not** buy a second NVMe merely to separate Windows from work data. Do **not** buy a small SSD specifically as an L2 cache for the primary SSD. Do **not** create Storage Spaces/Fusion-style automatic SSD tiering.

The active working set fits comfortably on one fast SSD, so direct placement is simpler, more predictable and avoids cache warm-up, duplicated NAND writes, write-back failure semantics and unnecessary device/partition management.

### Bulk/cold storage

Reuse existing healthy SATA SSD/HDD devices for infrequently accessed data such as archives, old projects, installers/ISOs, media, old VM images and backup staging. Validate health/SMART data before relying on old devices.

Important data must not exist only on an old SATA drive merely because it currently reports healthy.

`M.2_2` and `M.2_3` remain free for additive future storage if a concrete need appears.

No RAID requirement; maintain independent backup/version-control protection.

## GPU / expansion

Reuse the RTX 3060 for as long as useful/reliable. When a future replacement occurs, retire the 3060 rather than designing around dual-GPU operation.

A secondary PCIe x4 path is not a requirement. If a future high-speed NIC/HBA/capture-card requirement actually appears, revisit the motherboard then rather than purchasing unused capability now.

Do not pre-size today's motherboard/PSU/case for an unknown 500–600 W flagship. If a future GPU genuinely exceeds the current replaceable component envelope, revisit it then.

## Networking

Internet is below 1 Gb/s and LAN throughput is irrelevant.

- 1 GbE is sufficient;
- the board's 2.5 GbE is more than adequate;
- 5/10 GbE carries no purchase premium value.

## PSU requirements

Compare premium **750 W and 850 W ATX 3.1** units.

- 750 W is the baseline;
- 850 W wins only when its premium is modest or the exact product is materially better;
- do not buy 1000–1200 W for speculative GPU headroom.

Prioritize electrical quality/protections, transient handling, long warranty, quiet operation and current revision/cabling clarity.

## UPS / power protection

No UPS initially. Short outages are operationally acceptable.

Use a reputable **plug-in Schuko surge protector / surge-protected power strip** with proper earth, 230 V / 16 A suitability and protection-status indication. No electrical-installation modifications are part of this build.

## Budget and procurement

Planning level remains approximately 30,000 lei, neither a cap nor a spending target. Maximum three providers overall; target two hardware providers. Exact SKU/revision and warranty clarity outrank small nominal savings.

Memory pricing is currently unusually volatile/high; the exact RAM SKU is fixed, but supplier/price must be refreshed immediately before ordering.

## Decision philosophy

For every premium ask:

1. Does the real workload need it?
2. Does it materially improve stability, serviceability, endurance or performance?
3. Is the benefit durable over ownership?
4. Can it be added/replaced later more cheaply if necessary?
5. Are we paying for a concrete requirement or a hypothetical scenario?

When performance and stability conflict, prefer stability unless the performance loss materially affects the workstation's core purpose.
