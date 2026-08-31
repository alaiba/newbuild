# Procurement Plan — 2026-08-31

This plan is temporarily **paused for re-optimization** after two architecture changes were finalized:

- memory: **128 GB / 2×64 GB / 1DPC from day one**;
- storage: **~1 TB system NVMe + 4 TB work NVMe from day one**.

The previous 64 GB Phase-1 RAM assumption, Samsung 990 PRO 2 TB system-drive purchase and old purchase totals are obsolete.

## Locked procurement principles

1. **Maximum three providers overall.**
2. **Default target: two hardware providers.**
3. Add another hardware provider only for material net savings or materially better stock/SKU/revision/warranty certainty.
4. Windows/software may use a separate provider at a lower savings threshold because it has negligible RMA lifecycle burden.
5. Optimize **utility per leu**, including stability, endurance, serviceability, firmware quality, thermal/electrical margin and avoiding future replacement.
6. Do not pay merely for benchmark prestige or unused capability.
7. Buy exact SKUs/revisions only; no silent substitution.

## Decisions that remain purchase-ready

| Item | Target | Current status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| Cooler | Noctua NH-D15 G2 standard | selected |
| PSU architecture | 1200 W ATX 3.1 / PCIe 5.1 / 12V-2x6 | selected |
| PSU baseline | Seasonic VERTEX GX-1200 current ATX 3.1 | selected; PX preferred only at ≤~200 lei premium when available |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | selected |
| Rear fan | Noctua NF-A14x25 G2 PWM standard | selected |
| UPS | CyberPower PR1500ELCD | selected |
| Windows | Windows 11 Pro Retail/FPP; current exact target `HAV-00163` from PROstore | selected |
| GPU | existing RTX 3060 12 GB | reuse |

## Architecture locked; exact products reopened

### Motherboard

The ASUS ProArt X870E-Creator WiFi remains the incumbent reference but is **not currently purchase-final**.

Its strongest previous justification was the difficult 4×64 GB / 256 GB memory target. Re-optimize the board against the final 128 GB 1DPC target and the simplified two-drive storage topology.

Required storage topology:

- at least two simultaneously usable M.2 x4 slots;
- CPU-direct x4 preferred for the 4 TB work drive;
- chipset x4 is sufficient for the system drive;
- using those two slots must preserve GPU x16;
- Gen5 storage capability is a bonus, not a requirement.

### Memory

Final architecture is locked:

- **128 GB**;
- **2×64 GB**;
- **1DPC**;
- buy the final matched kit at initial assembly;
- no provisional 2×32 GB purchase.

Exact kit and ECC/non-ECC verdict remain open until the motherboard/RAM optimization pass.

### System SSD

Final role/capacity target:

- approximately **1 TB**;
- internal NVMe;
- reputable vendor and mature firmware;
- normal warranty;
- TLC preferred where price-effective;
- DRAM and flagship throughput are **not requirements**;
- Gen3/Gen4 performance is sufficient;
- chipset-connected M.2 x4 is acceptable.

Do not automatically buy the Samsung 990 PRO. Select the cheapest credible drive that meets the reliability/headroom criteria. Move from 500 GB to 1 TB when the price increment is small.

### Work SSD

Final role/capacity target:

- **4 TB from day one**;
- high-quality internal NVMe;
- TLC strongly preferred;
- DRAM-equipped design preferred when reasonably priced;
- mature firmware and good sustained/mixed behavior;
- endurance appropriate for repositories/build caches/WSL2/containers/VMs/databases;
- CPU-direct x4 preferred;
- **Gen4 is sufficient**.

Do not pay a material Gen5 premium without a demonstrated workload benefit.

### Storage RAID / backup

- no RAID requirement;
- use version control plus external/network/cloud backup as appropriate;
- internal drive redundancy is not a substitute for backup.

## Current provider references

The prior provider split remains a useful market reference, not a committed order:

- EvoMAG remains a strong candidate for much of the hardware;
- Altex remains the clean explicit-current Seasonic PSU route;
- PROstore remains the current verified Windows `HAV-00163` Retail/FPP target;
- eMAG is fully acceptable, and Genius/free-delivery value should be included when comparing eligible offers.

Recalculate provider consolidation after motherboard, RAM and both SSD models are closed.

## Price envelope

**Do not use the previous ~20k complete-order total.**

It assumed:

- 64 GB / 2×32 GB RAM;
- the ProArt as final motherboard;
- a Samsung 990 PRO 2 TB system SSD;
- the 4 TB work SSD deferred outside the initial order.

A new total will be calculated only after the reopened exact-product decisions are closed.

## Hard acceptance gates that remain valid

### CPU
- Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### RAM
- 128 GB total;
- exactly 2×64 GB matched DDR5 UDIMM kit;
- 1DPC;
- no temporary 2×32 GB purchase.

### Storage
- two drives purchased for initial assembly;
- ~1 TB system NVMe + 4 TB work NVMe;
- system drive selected for reliability/headroom/value, not flagship benchmarks;
- work drive TLC strongly preferred;
- no Gen5 requirement;
- motherboard slot combination must preserve GPU x16.

### Cooler
- NH-D15 G2 standard;
- no LBC/HBC substitution.

### PSU
- ATX 3.1;
- PCIe 5.1;
- current 12V-2x6 cable;
- reject explicit old ATX 3.0 / 12VHPWR stock.

### Case
- exact `FD-C-NOR1X-01` North XL Charcoal Black Mesh.

### Rear fan
- standard square-frame NF-A14x25 G2 PWM single fan.

### UPS
- exact PR1500ELCD;
- 1500 VA / 1350 W;
- new/sealed.

### Windows
- Windows 11 Pro;
- Retail/FPP;
- current target `HAV-00163`;
- not OEM/DSP or an undocumented standalone key.

## Next sequence

1. re-optimize **motherboard** against final memory/storage topology;
2. select exact **2×64 GB RAM** and ECC/non-ECC verdict;
3. select exact **~1 TB system + 4 TB work SSDs** using current Romanian prices;
4. refresh all current stock/prices, including eMAG Genius delivery where relevant;
5. produce a new ≤3-provider order plan and total;
6. only then order the reopened items.
