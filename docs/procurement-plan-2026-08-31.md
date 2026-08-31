# Procurement Plan — 2026-08-31

This plan is temporarily **paused for re-optimization** after the memory architecture was finalized at **128 GB / 2×64 GB / 1DPC from day one**.

The previous 64 GB Phase-1 RAM assumption and the purchase total derived from it are obsolete.

## Locked procurement principles

1. **Maximum three providers overall.**
2. **Default target: two hardware providers.**
3. Add another hardware provider only for material net savings or materially better stock/SKU/revision/warranty certainty.
4. Windows/software may use a separate provider at a lower savings threshold because it has negligible RMA lifecycle burden.
5. Optimize **utility per leu**, including stability, endurance, serviceability, firmware quality, thermal/electrical margin and avoiding future replacement.
6. Buy exact SKUs/revisions only; no silent substitution.

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

## Decisions reopened before ordering

### Motherboard

The ASUS ProArt X870E-Creator WiFi remains the incumbent reference but is **not currently purchase-final**.

Its strongest previous justification was the difficult 4×64 GB / 256 GB memory target. With final memory now 2×64 GB / 128 GB, re-optimize the board against the remaining requirements.

### Memory

Final architecture is locked:

- **128 GB**;
- **2×64 GB**;
- **1DPC**;
- buy the final matched kit at initial assembly;
- no provisional 2×32 GB purchase.

Exact kit and ECC/non-ECC verdict remain open until the motherboard/RAM optimization pass.

### Storage

The incumbent architecture remains:

- Samsung 990 PRO 2 TB system/tools drive;
- future 4 TB+ work/VM/container/data drive;
- no RAID.

However, the user requested a storage-architecture optimization discussion before motherboard/RAM optimization. Do not order the SSD until that discussion is closed.

## Current provider references

The prior provider split is a useful market reference, not a committed order:

- EvoMAG remains a strong candidate for much of the hardware;
- Altex remains the clean explicit-current Seasonic PSU route;
- PROstore remains the current verified Windows `HAV-00163` Retail/FPP target.

Recalculate provider consolidation after motherboard, RAM and storage are closed.

## Price envelope

**Do not use the previous ~20k complete-order total.**

It assumed:

- 64 GB / 2×32 GB RAM;
- the ProArt as final motherboard;
- the current two-drive storage architecture without review.

A new total will be calculated only after the reopened decisions are closed.

## Hard acceptance gates that remain valid

### CPU
- Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### RAM
- 128 GB total;
- exactly 2×64 GB matched DDR5 UDIMM kit;
- 1DPC;
- no temporary 2×32 GB purchase.

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

1. close the **storage architecture** discussion;
2. re-optimize **motherboard + exact 2×64 GB RAM** together;
3. refresh current Romanian prices and stock;
4. produce a new ≤3-provider order plan and total;
5. only then order the reopened items.
