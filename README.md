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

Planning level is approximately **30,000 lei**, not a target and not a hard cap.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **Reopened for optimization**; ASUS ProArt X870E-Creator WiFi remains incumbent reference |
| RAM | **128 GB final from day one, 2×64 GB DDR5 UDIMM / 1DPC**; exact kit and ECC verdict open |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset |
| Storage | Incumbent: **Samsung 990 PRO 2 TB system/tools + future 4 TB+ work SSD**; architecture under requested review |
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

Because the previous motherboard promotion depended heavily on 4×64 GB / 256 GB behavior, the exact motherboard is reopened and will be re-optimized after the storage discussion.

## Important operating policies

- Ryzen CPU remains stock/conservative; no uncapped-PBO policy.
- RAM starts at Auto/JEDEC and receives extended stability testing before any optional profile tuning.
- Exact 2×64 GB kit is selected for stability first; ECC only if exact-module support and OS-visible reporting are credible.
- Keep initial case airflow simple: front intake + rear exhaust; add top/side fans only if measurements justify them.
- Windows baseline is production/GA only; no Insider baseline.
- Linux-native high-I/O work belongs inside the WSL filesystem rather than `/mnt/c`.
- BitLocker is enabled only after the initial BIOS/firmware/driver baseline is stable.

## Procurement policy

- Maximum three providers overall; target two hardware providers where practical.
- Exact SKU/revision, invoice/warranty path and product condition outrank retailer loyalty.
- Hardware supplier fragmentation needs a meaningful price, stock, warranty or revision-certainty benefit.
- Software such as Windows may use a separate supplier at a lower savings threshold because it has negligible RMA lifecycle burden.

The current procurement plan is intentionally paused until the reopened motherboard/RAM/storage decisions are closed: [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md).

## Current open work

1. Review/optimize the **storage architecture**.
2. Re-optimize the **motherboard** against 128 GB / 2×64 GB / 1DPC and the finalized storage requirements.
3. Select the exact **2×64 GB RAM kit**, including ECC/non-ECC verdict.
4. Recalculate current Romanian pricing, provider consolidation and final purchase total.
5. Future high-VRAM GPU remains deferred.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload, constraints and evaluation criteria
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened decisions and rationale
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement state and purchase gates
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/compatibility constraints
- [`docs/components/`](docs/components/) — component deep dives and evidence

## Current stage

**Memory architecture is final. Storage is being reviewed next; motherboard and exact RAM will then be re-optimized before procurement resumes.**
