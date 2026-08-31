# Procurement Plan — 2026-08-31

Motherboard, RAM, primary storage and PSU are now closed. Procurement remains paused only for the exact surge protector and final provider/price consolidation.

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
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | selected; supplier price refresh pending |
| RAM | **Crucial `CT2K64G56C46U5`, 128 GB 2×64, DDR5-5600 CL46, 1.1 V, non-ECC** | selected; supplier price refresh pending |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | selected |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | selected |
| Case fans | use two included 140 mm PWM fans only initially | selected |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink, PCIe 5.0 x4 | selected; supplier price refresh pending |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | selected; supplier price refresh pending |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Surge protection | reputable plug-in Schuko surge protector/power strip | exact product open |

## Motherboard acceptance gate

- exact model/part: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- normal new retail unit and warranty path;
- no substitution to B650-E, B650E-PLUS, B850-PLUS or another similarly named TUF variant without review;
- update to current stable production BIOS during commissioning.

Current Romanian reference pricing is approximately **~839–844 lei**. Refresh immediately before checkout.

The **MSI B850 GAMING PLUS WIFI `7E56-001R`** remains the first fallback only if the selected ASUS becomes materially worse on price, stock or warranty. Its secondary x4 slot and 5 GbE are real advantages, but they are not current requirements.

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

## Storage acceptance gate

Primary storage:

- exact model: **Crucial T710 2 TB `CT2000T710SSD8`**;
- PCIe 5.0 x4 NVMe, TLC, DRAM-equipped;
- bare/non-heatsink version only unless a later physical review explicitly changes the heatsink policy;
- install in CPU-direct **`M.2_1`** under the ASUS motherboard M.2 heatsink;
- normal new retail unit, five-year-class warranty path and current firmware availability;
- refresh live Romanian price immediately before checkout.

Current storage use is approximately **600 GB**. The 2 TB target provides enough foreseeable active-storage headroom without buying unused 4 TB capacity. The roughly ~1.3k-leu step from the currently observed 2 TB T710 class to 4 TB is therefore rejected for the initial order.

No second NVMe is purchased initially. No SSD cache, write-back layer, Storage Spaces tiering or RAID is required.

Existing healthy SATA drives remain available for archives/cold data after SMART/health validation. `M.2_2` and `M.2_3` stay empty for later additive expansion.

## PSU acceptance gate

Selected PSU:

- exact model: **be quiet! Pure Power 13 M 850W `BP027EU`**;
- 850 W, ATX 3.1;
- native current-generation GPU-power cable supplied with the unit;
- fully modular;
- normal new retail unit and 10-year manufacturer-warranty path;
- use only the modular cables supplied with this exact PSU;
- refresh live Romanian price immediately before checkout.

The current observed Romanian price class is approximately **~687–718 lei**. The 850 W model was selected because its premium over the corresponding 750 W unit was only roughly **40–100 lei**, satisfying the project's existing value rule for the larger unit.

Preferred fallback: **Corsair RM850x 2024 850W `CP-9020270-EU`**, but only if delivered price is within roughly **30–40 lei** or retailer/warranty conditions are materially better.

Do not substitute a 1000–1200 W unit merely for speculative future GPU margin.

## Closed motherboard/storage topology

Recommended slot use:

- primary PCIe 5.0 x16: RTX 3060;
- `M.2_1` CPU Gen5 x4: **Crucial T710 2 TB primary SSD**;
- `M.2_2` CPU Gen4 x4: empty / future expansion;
- `M.2_3` chipset Gen4 x4: empty / future expansion;
- second physical x16 slot: chipset Gen4 x1 only, no planned use;
- 4× SATA: existing/later cold storage.

The absence of a secondary x4 expansion path is accepted because no current requirement needs one.

## Item still to optimize

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
- buying 750 W instead of the selected 850 W solely to minimize nominal wattage/cost;
- Noctua NH-D15 G2;
- Fractal North XL Mesh;
- Noctua NF-A14x25 G2 rear fan;
- Creator/X870E motherboard premium;
- ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0` as the selected motherboard;
- B850 as a platform requirement;
- 256 GB / four-DIMM RAM;
- ECC as a RAM purchase requirement;
- separate ~1 TB system SSD;
- separate active-work SSD;
- dedicated SSD cache device;
- 4 TB initial primary/work SSD requirement;
- 5/10 GbE, x8/x8 and secondary x4 expansion requirements.

## Price envelope

All earlier full-order totals are obsolete. Do not publish the final order total until the surge protector is selected and live Romanian pricing is refreshed for the **entire** selected BOM, especially the volatile RAM and SSD supplier availability.

## Next sequence

1. exact surge protector;
2. full live price/provider refresh;
3. ≤3-provider order plan and final total.
