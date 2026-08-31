# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

## Purpose

Greenfield self-built workstation optimized primarily for:

- very heavy Java development across very large codebases;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- Docker/WSL2, local services/databases and occasional VMs;
- occasional gaming as a secondary workload;
- a future single very high-performance/high-VRAM GPU for local AI.

The design philosophy is **stability first**: conservative operation, mature firmware, thermal/electrical margin, reliability, serviceability and long ownership are preferred over short-lived benchmark gains or aggressive tuning.

Planning level is approximately **30,000 lei**, not a target and not a hard cap. Do not spend merely because headroom exists; premiums must buy a material benefit for the real workload or lifetime ownership.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **Reopened for optimization**; ASUS ProArt X870E-Creator WiFi remains incumbent reference |
| RAM | **128 GB final from day one, 2×64 GB DDR5 UDIMM / 1DPC**; exact kit and ECC verdict open |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset |
| System SSD | **~1 TB NVMe**, reliability/capacity/value optimized; chipset M.2 x4 acceptable; exact model open |
| Work SSD | **4 TB high-quality NVMe from day one**, Gen4 TLC preferred; CPU-direct x4 preferred; exact model open |
| Storage RAID | **None**; real external/network backup required |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6**; PX preferred only at ≤~200 lei premium when available |
| Case | **Fractal Design North XL Mesh `FD-C-NOR1X-01`** |
| Airflow | 3× included 140 mm front intake + 1× **Noctua NF-A14x25 G2 PWM** rear exhaust |
| GPU | Existing **RTX 3060 12 GB**, reused initially |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** |
| Host OS | **Windows 11 Pro x64**, initial install 25H2 GA |
| Windows license | **Retail/FPP USB English `HAV-00163`**, current purchase target PROstore |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Final memory decision

The workstation will **not** use provisional RAM.

The initial assembly receives the intended lifetime configuration:

**128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC).**

This supersedes the old 64 GB Phase-1 / 256 GB eventual plan. There is no planned RAM expansion or disposal step.

Because the previous motherboard promotion depended heavily on 4×64 GB / 256 GB behavior, the exact motherboard is reopened.

## Final storage architecture

The workstation will also avoid a temporary one-drive storage phase.

Initial assembly receives:

- **~1 TB system/tools NVMe**;
- **4 TB work/data NVMe**.

The system SSD is deliberately not optimized for flagship sequential performance. With 128 GB RAM and the active development data on a separate work SSD, its priorities are mature firmware, reliability, adequate free-space headroom, warranty and price. A good Gen3/Gen4 chipset-connected NVMe is sufficient.

The 4 TB work SSD receives the performance/endurance priority because it will host repositories, build caches, WSL2/container data, Android images, VMs, databases and other large/high-I/O data. Prefer TLC and a CPU-direct x4 connection; **Gen4 is sufficient and Gen5 is not a requirement**.

The previous Samsung 990 PRO 2 TB system-drive selection and staged 2 TB-now / 4 TB-later plan are superseded. Future storage expansion should be additive through additional drives rather than replacing the initial pair merely for more capacity.

## Important operating policies

- Ryzen CPU remains stock/conservative; no uncapped-PBO policy.
- RAM starts at Auto/JEDEC and receives extended stability testing before any optional profile tuning.
- Exact 2×64 GB kit is selected for stability first; ECC only if exact-module support and OS-visible reporting are credible.
- The selected two M.2 slots must preserve the primary GPU at x16.
- System SSD may use chipset x4; work SSD preferably uses CPU-direct x4.
- Keep large/high-I/O WSL2, build, VM, container, Android and database data on the work SSD using supported relocation mechanisms.
- Keep initial case airflow simple: front intake + rear exhaust; add top/side fans only if measurements justify them.
- Windows baseline is production/GA only; no Insider baseline.
- Linux-native high-I/O work belongs inside the WSL filesystem rather than `/mnt/c`.
- BitLocker is enabled only after the initial BIOS/firmware/driver/storage baseline is stable.

## Procurement policy

- Maximum three providers overall; target two hardware providers where practical.
- Exact SKU/revision, invoice/warranty path and product condition outrank retailer loyalty.
- Hardware supplier fragmentation needs a meaningful price, stock, warranty or revision-certainty benefit.
- Software such as Windows may use a separate supplier at a lower savings threshold because it has negligible RMA lifecycle burden.
- Do not pay for benchmark prestige or unused capability; higher cost is justified only by a material workload, stability, endurance or lifecycle benefit.

The current procurement plan is intentionally paused until the reopened motherboard/RAM and exact-SSD selections are closed: [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md).

## Current open work

1. Re-optimize the **motherboard** against 128 GB / 2×64 GB / 1DPC and the finalized two-drive storage topology.
2. Select the exact **2×64 GB RAM kit**, including ECC/non-ECC verdict.
3. Select the exact **~1 TB system SSD + 4 TB work SSD** using current Romanian pricing and role-specific requirements.
4. Recalculate provider consolidation and final purchase total.
5. Future high-VRAM GPU remains deferred.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload, constraints and evaluation criteria
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened decisions and rationale
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement state and purchase gates
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/compatibility constraints
- [`docs/components/`](docs/components/) — component deep dives and evidence

## Current stage

**Memory and storage architectures are final. Motherboard, exact RAM and exact SSD models are the next coupled optimization before procurement resumes.**
