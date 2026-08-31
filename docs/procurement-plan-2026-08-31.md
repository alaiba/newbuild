# Procurement Plan — 2026-08-31

This plan remains paused for the still-open motherboard/RAM/storage/PSU optimization.

## Locked principles

1. Maximum three providers overall; target two hardware providers.
2. Optimize utility per leu, not benchmark prestige.
3. Do not pay for unused networking, PCIe, storage capacity, wattage, cooling capacity or extreme-overclocking capability.
4. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.
5. Software may use a separate provider when provenance/price justify it.

## Purchase-ready / stable decisions

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | selected |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | selected |
| Case fans | use the **two included 140 mm PWM fans** only initially | selected |
| RAM architecture | 128 GB = 2×64 GB / 1DPC | selected; exact kit open |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Surge protection | reputable plug-in surge protector/power strip | selected policy; exact product open |

### Cooler acceptance gate

- exact product: **Thermalright Phantom Spirit 120 standard**;
- AM5 mounting hardware included;
- do not silently substitute PS120 SE, EVO or another variant;
- verify box/product identity before purchase.

### Case acceptance gate

- exact model: **be quiet! Pure Base 501 Airflow Black `BG074`**;
- new/sealed;
- both included 140 mm PWM fans present;
- no dedicated Noctua rear-fan purchase;
- no additional case fan initially.

## Items to optimize before ordering

### Motherboard

Start from a broad AM5 candidate set constrained to **ATX or smaller**.

Hard/strong requirements:

- stable Ryzen 9 9950X3D support;
- stable 2×64 GB / 128 GB / 1DPC operation;
- one CPU-direct M.2 x4 path for the active-work SSD without reducing the main GPU link;
- competent stock-load VRM thermals;
- BIOS Flashback/recovery strongly preferred;
- useful diagnostics/serviceability preferred;
- practical SATA and/or spare-storage path.

Do **not** pay materially for:

- 5/10 GbE;
- x8/x8 multi-GPU capability;
- multiple Gen5 M.2 slots;
- extreme-overclocking VRM design;
- future 500–600 W GPU provisioning.

1 GbE is sufficient; 2.5 GbE is a bonus.

### Memory

- 128 GB total;
- matched 2×64 GB DDR5 UDIMM;
- 1DPC;
- stability/JEDEC behavior first;
- ECC only when exact support and OS-visible reporting are credible;
- verify clean physical fit with Phantom Spirit 120, including any front-fan lift.

### Storage

Active-work:

- 1 TB sufficient;
- 2 TB if current incremental price/value is attractive;
- CPU-direct M.2 x4 mandatory;
- Gen4 TLC preferred;
- Gen5 not required.

System:

- around 1 TB;
- NVMe preferred;
- SATA SSD acceptable if that enables a materially better motherboard/value choice;
- reliability/headroom/value over benchmark throughput.

Bulk/cold:

- buy later only when needed;
- spare NVMe/SATA SSD/HDD/external/NAS all valid;
- healthy old HDDs may be reused for inactive data, never as the only copy of important data.

### PSU

Compare premium **750 W and 850 W ATX 3.1** units.

- 750 W is the legitimate baseline;
- choose 850 W when the premium is modest or exact model is materially better;
- do not buy 1000–1200 W for speculative GPU headroom;
- prioritize electrical quality, protections, warranty, acoustics and current revision/cabling.

### Point-of-use surge protection

Select a reputable Schuko plug-in surge protector / protected power strip with:

- 230 V / 16 A suitability;
- protective-earth continuity;
- protection-status indication;
- clear replacement/end-of-protection guidance;
- reputable manufacturer and normal Romanian/EU warranty path.

## Explicitly removed from the order

- CyberPower PR1500ELCD;
- 1200 W Seasonic VERTEX GX/PX targets;
- Noctua NH-D15 G2;
- Fractal North XL Mesh `FD-C-NOR1X-01`;
- Noctua NF-A14x25 G2 rear fan;
- 4 TB initial work SSD requirement;
- 5/10 GbE requirement;
- multi-GPU/x8+x8 requirement;
- motherboard premium for extreme VRM/OC capability.

## Price envelope

All earlier complete-order totals are obsolete.

Do not produce a new final total until:

1. motherboard is selected;
2. exact 2×64 GB kit is selected;
3. exact system/active-work drives are selected;
4. exact 750/850 W PSU is selected;
5. exact surge protector is selected or separately budgeted;
6. live Romanian stock/prices are refreshed.

## Next sequence

1. motherboard optimization;
2. exact RAM;
3. exact SSDs;
4. exact PSU;
5. surge protector;
6. provider consolidation and final total.
