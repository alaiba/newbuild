# Final Order Plan — 2026-08-31

Status: **All components except RAM purchase capacity are selected. Motherboard procurement naming error corrected.**

Prices below are reference checkout prices observed on 2026-08-31 and must be confirmed in-cart immediately before payment. Shipping is excluded unless explicitly noted.

## Important motherboard correction

Do **not** substitute **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`** for the selected **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**. They are distinct products despite the confusingly similar names.

Earlier procurement notes incorrectly treated EvoMAG/ForIT B650-E listings as the selected B650E-E. Those references are superseded.

Current exact-board Romanian reference used for this plan:

- **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**
- EAN **4711387992494**
- exact Romanian listing previously verified at approximately **1,073.60 lei** at Elektroshock

Recheck the exact SKU/EAN before payment. If that listing disappears, search again rather than substituting B650-E/B650E-PLUS.

## Current provider split

With the 128 GB RAM baseline:

1. **EvoMAG** — CPU, RAM, cooler, case, SSD, PSU.
2. **Elektroshock / another exact-SKU Romanian retailer** — motherboard `90MB1LT0-M0EAY0`.
3. **PROstore** — Windows 11 Pro Retail/FPP.

This remains within the project constraint: maximum three providers overall and two hardware providers.

## Order table — 128 GB baseline

| Provider | Item | Exact target | Reference price |
|---|---|---|---:|
| EvoMAG | CPU | AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** |
| Exact-SKU Romanian retailer | Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | **1,073.60 lei** reference |
| EvoMAG | RAM baseline | Crucial `CT2K64G56C46U5`, 128 GB (2×64 GB), DDR5-5600 CL46, 1.1 V | **7,699.99 lei** |
| EvoMAG | CPU cooler | Thermalright Phantom Spirit 120 — standard | **249.99 lei** |
| EvoMAG | Case | be quiet! Pure Base 501 Airflow Black `BG074` | **423.99 lei** |
| EvoMAG | Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | **1,710.99 lei** |
| EvoMAG | PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **686.99 lei** |
| PROstore | Windows | Windows 11 Pro 64-bit English Retail/FPP USB `HAV-00163` | **1,123.60 lei** |
| Reuse | GPU | Existing RTX 3060 12 GB | **0 lei** |
| Reuse | Cold storage | Existing healthy SATA drives | **0 lei** |
| None | UPS / dedicated surge protector | Not purchased | **0 lei** |

### Corrected 128 GB baseline total

- Non-RAM subtotal including Windows: **8,619.15 lei**
- 128 GB RAM reference: **7,699.99 lei**
- **Reference total before shipping: 16,319.14 lei**

The previous **16,119.71 lei** total is superseded because it used the wrong motherboard procurement reference.

## RAM capacity sensitivity — purchase decision reopened

The platform policy remains **two DIMMs / 1DPC**. The purchase-capacity alternatives being evaluated are therefore:

| Capacity | Topology | Current representative price | Complete-build total | Savings vs 128 GB |
|---|---|---:|---:|---:|
| **32 GB** | 2×16 GB DDR5-5600 | ~2,454.99 lei | **~11,074.14 lei** | **~5,245.00 lei** |
| **48 GB** | 2×24 GB DDR5-5600 | ~2,899.00 lei | **~11,518.15 lei** | **~4,800.99 lei** |
| **64 GB** | 2×32 GB DDR5-5600 | ~4,799.99 lei | **~13,419.14 lei** | **~2,900.00 lei** |
| **96 GB** | 2×48 GB DDR5-5600 | ~7,399.00 lei | **~16,018.15 lei** | **~300.99 lei** |
| **128 GB** | 2×64 GB DDR5-5600 | ~7,699.99 lei | **~16,319.14 lei** | baseline |

These are market snapshots, not locked purchase prices. Exact kits must be re-optimized after the capacity is chosen.

### Topology rule

Do not turn a cheaper initial kit into a planned four-DIMM upgrade. Ryzen 9 9950X3D officially supports DDR5-5600 with two DIMMs but only DDR5-3600 with four DIMMs. If a smaller capacity is bought now and 128 GB is later required, prefer replacing the two-DIMM kit with a 2×64 GB kit and reselling/reusing the old kit.

## RAM decision status

128 GB remains the **maximum-convenience/performance baseline**, but its current ~7.7k-leu price is poor enough that capacity/value is reopened before payment.

Current serious alternatives:

- **48 GB:** budget bridge; meaningful concurrency limits likely under heavy Java + Android + WSL/container workloads.
- **64 GB:** main value candidate; likely indistinguishable from 128 GB whenever the working set fits, but with less VM/container/AVD concurrency and less filesystem cache.
- **128 GB:** maximum headroom; mainly buys concurrency and freedom from memory management, not higher CPU speed when 64 GB is sufficient.

32 GB and 96 GB are currently weak value positions: 48 GB costs only modestly more than 32 GB, while 96 GB costs almost as much as 128 GB.

See `docs/ram-capacity-sensitivity-2026-08-31.md` for the detailed performance model.

## Checkout gates

1. Verify motherboard exact **`90MB1LT0-M0EAY0` / EAN `4711387992494`**. Do not accept `90MB1GT0-M0EAY0` merely because the name looks almost identical.
2. Choose RAM capacity after the current sensitivity review, then perform a fresh exact-kit search for that capacity.
3. Keep RAM at **two matched DIMMs / A2+B2 / 1DPC**.
4. Confirm T710 is bare/non-heatsink `CT2000T710SSD8`.
5. Confirm CPU is Box/WOF `100-100000719WOF`, not tray.
6. Confirm PSU is Pure Power 13 M 850W `BP027EU`.
7. Confirm Windows is genuine Retail/FPP English USB `HAV-00163`.
8. Preserve invoices, serial numbers and packaging through commissioning/return windows.

## Assembly-critical reminders

- RAM: A2/B2, Auto/JEDEC first.
- T710: `M.2_1` CPU PCIe 5.0 x4 under ASUS heatsink.
- PSU: use only modular cables supplied with `BP027EU`.
- RTX 3060 reused; no new GPU.
- Validate SMART/health before reusing older SATA drives.
- No UPS, RAID, SSD cache/tiering or dedicated surge protector initially.

## Purchase position

The build remains architecturally closed except for **RAM purchase capacity**, which is under explicit value review because current 128 GB pricing is anomalously high.
