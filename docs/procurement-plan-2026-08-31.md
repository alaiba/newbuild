# Procurement Plan — 2026-08-31

Status: **all architecture decisions are closed except RAM purchase capacity, reopened because current 128 GB pricing is anomalously high. Motherboard procurement naming error corrected.**

## Locked principles

1. Maximum three providers overall; target two hardware providers.
2. Optimize utility per leu, not benchmark prestige.
3. Preserve exact product identities where a similarly named substitute is materially different.
4. Prefer two-DIMM / 1DPC memory topology on AM5.
5. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.

## Motherboard procurement correction

Selected motherboard remains:

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**, EAN `4711387992494`.

Do not confuse it with:

> **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**.

Earlier notes incorrectly attributed B650-E listings at EvoMAG/ForIT to the selected B650E-E. Those supplier references and the old 16,119.71-leu total are superseded.

Current exact Romanian reference used in the plan is approximately **1,073.60 lei** from a previously verified Elektroshock listing. Reconfirm the exact SKU/EAN immediately before payment.

## Selected purchase targets

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | selected; exact supplier to reconfirm |
| RAM | two matched DDR5-5600 UDIMMs / A2+B2 / 1DPC | **capacity under review: 48 / 64 / 128 GB are serious candidates** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | selected |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | selected |
| Case fans | two included 140 mm PWM only initially | selected |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink | selected |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | selected |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Dedicated surge protector | none | selected |

## RAM capacity/value review

AMD officially rates the 9950X3D for **DDR5-5600 with two DIMMs** and only **DDR5-3600 with four DIMMs**. Therefore capacity optimization must preserve the two-DIMM topology.

Current representative Romanian snapshots:

| Capacity | Topology | Representative price | Build total before shipping | Savings vs 128 GB |
|---|---|---:|---:|---:|
| 32 GB | 2×16 | ~2,454.99 lei | ~11,074.14 lei | ~5,245.00 lei |
| 48 GB | 2×24 | ~2,899.00 lei | ~11,518.15 lei | ~4,800.99 lei |
| 64 GB | 2×32 | ~4,799.99 lei | ~13,419.14 lei | ~2,900.00 lei |
| 96 GB | 2×48 | ~7,399.00 lei | ~16,018.15 lei | ~300.99 lei |
| 128 GB | 2×64 | ~7,699.99 lei | ~16,319.14 lei | baseline |

Interpretation:

- **32 GB:** technically workable, but poor value versus 48 GB and too close to the current machine's constraint.
- **48 GB:** cheapest sensible bridge; requires some concurrency discipline.
- **64 GB:** principal value candidate for the intended workload.
- **96 GB:** currently bad value because it is almost the price of 128 GB.
- **128 GB:** maximum-convenience target, but current price requires explicit acceptance rather than automatic purchase.

If a smaller kit is purchased and future capacity becomes insufficient, replace it with 2×64 GB rather than adding another pair and moving to four DIMMs.

Detailed analysis: `ram-capacity-sensitivity-2026-08-31.md`.

## Current 128 GB baseline basket

Using the corrected exact-board reference and the previous 128 GB kit:

- fixed non-RAM subtotal including Windows: **8,619.15 lei**;
- 128 GB RAM: **~7,699.99 lei**;
- corrected reference total: **~16,319.14 lei before shipping**.

This is now a comparison baseline, not a final checkout total until RAM capacity is chosen.

## Exact acceptance gates

### CPU
- Ryzen 9 9950X3D Box/WOF `100-100000719WOF`.

### Motherboard
- exact **TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- EAN `4711387992494`;
- reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS and similarly named variants without review.

### RAM
- two matched DDR5 UDIMMs only;
- A2/B2 / 1DPC;
- prefer stable DDR5-5600 operation at conservative voltage;
- exact capacity/kit to be selected after value review;
- do not plan a four-DIMM upgrade path.

### Cooler
- Thermalright Phantom Spirit 120 standard.

### Case
- be quiet! Pure Base 501 Airflow Black `BG074` with two included 140 mm PWM fans.

### Storage
- Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink, `M.2_1`.

### PSU
- be quiet! Pure Power 13 M 850W `BP027EU`;
- use only supplied modular cables.

### Windows
- Windows 11 Pro Retail/FPP English USB `HAV-00163`.

## Next sequence

1. Choose RAM capacity from the sensitivity analysis.
2. Optimize the exact kit for that capacity using live Romanian stock/prices.
3. Re-run the final supplier consolidation and total.
