# Procurement Plan — 2026-08-31

Motherboard and RAM are now closed. Procurement remains paused only for exact storage, PSU, surge-protector and final provider/price consolidation.

## Locked principles

1. Maximum three providers overall; target two hardware providers.
2. Optimize utility per leu, not benchmark prestige.
3. Do not pay for unused networking, PCIe, storage capacity, wattage, cooling capacity or extreme-overclocking capability.
4. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.
5. Software may use a separate provider when provenance/price justify it.

## Selected purchase targets

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| Motherboard | **ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`** | selected; supplier price refresh pending |
| RAM | **Crucial `CT2K64G56C46U5`, 128 GB 2×64, DDR5-5600 CL46, 1.1 V, non-ECC** | selected; supplier price refresh pending |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | selected |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | selected |
| Case fans | use two included 140 mm PWM fans only initially | selected |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Surge protection | reputable plug-in Schuko surge protector/power strip | exact product open |

## Motherboard acceptance gate

- exact model/part: **ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`**;
- normal new retail unit and warranty path;
- no substitution to another TUF/B850 variant without review;
- update to current stable production BIOS during commissioning.

Recent Romanian reference pricing has been around **1.06–1.07k lei**. Refresh immediately before checkout.

## RAM acceptance gate

- exact matched kit: **Crucial `CT2K64G56C46U5`**;
- 128 GB = 2×64 GB;
- non-ECC unbuffered DDR5;
- native DDR5-5600 CL46-class JEDEC operation at **1.1 V**;
- no RDIMM;
- no substitution to 4-DIMM topology or a high-voltage enthusiast kit without review.

### RAM price warning

The 128 GB 2×64 market is currently unusually expensive/volatile. A recent direct EvoMAG reference for the exact Crucial kit was about **7,699.99 lei**, while older cached Romanian results near **6.35–6.4k lei** are stale and must not be treated as current purchase controls.

The SKU remains selected; **supplier is not locked**. Recheck all intended hardware providers before ordering.

## Closed motherboard/RAM topology

Recommended slot use:

- primary PCIe x16: RTX 3060;
- `M.2_1` CPU x4: active-work SSD;
- `M.2_2` CPU x4: system/tools SSD;
- `M.2_3` chipset x4: optional future storage;
- 4× SATA: later bulk/cold storage.

Using `M.2_3` may consume the secondary PCIe x4 expansion resource. This is accepted because that expansion slot is not required.

## Items still to optimize

### Storage

Active-work:

- 1 TB sufficient;
- 2 TB if incremental price/value is attractive;
- install in CPU-direct `M.2_1`;
- mature Gen4 TLC preferred;
- DRAM preferred where reasonably priced;
- Gen5 not required.

System:

- around 1 TB;
- now **prefer NVMe** in CPU-connected `M.2_2` because the selected board provides it without meaningful trade-off;
- reliability/headroom/firmware/warranty/value over benchmark throughput.

Bulk/cold:

- buy later only when needed;
- `M.2_3`, SATA SSD/HDD, external/NAS all valid;
- healthy old HDD reuse allowed for inactive data, never sole copy.

### PSU

Compare premium **750 W and 850 W ATX 3.1** units.

- 750 W baseline;
- choose 850 W when premium is modest or exact model materially better;
- do not buy 1000–1200 W for speculative GPU headroom;
- prioritize electrical quality, protections, warranty, acoustics and current revision/cabling.

### Point-of-use surge protection

Select a reputable Schuko device with:

- 230 V / 16 A suitability;
- protective-earth continuity;
- protection-status indication;
- clear replacement/end-of-protection guidance;
- reputable manufacturer and normal Romanian/EU warranty path.

## Explicitly removed from the order

- CyberPower PR1500ELCD;
- 1200 W Seasonic VERTEX GX/PX targets;
- Noctua NH-D15 G2;
- Fractal North XL Mesh;
- Noctua NF-A14x25 G2 rear fan;
- Creator/X870E motherboard premium;
- 256 GB / four-DIMM RAM;
- ECC as a RAM purchase requirement;
- 4 TB initial work SSD requirement;
- 5/10 GbE and x8/x8 requirements.

## Price envelope

All earlier full-order totals are obsolete. Do not publish the final order total until exact SSDs, PSU and surge protection are selected and live Romanian pricing is refreshed for the **entire** selected BOM, especially the volatile RAM.

## Next sequence

1. exact system + active-work SSDs;
2. exact PSU;
3. exact surge protector;
4. full live price/provider refresh;
5. ≤3-provider order plan and final total.
