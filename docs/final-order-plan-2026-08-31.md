# Final Order Plan — 2026-08-31

> Updated 2026-09-01 after both hardware orders were executed and Windows was removed from procurement because the license is already available.

Status: **nearly complete**.

## Executed EvoMAG order — 2026-09-01

| Item | Ordered identity | Paid price incl. VAT | Status |
|---|---|---:|---|
| CPU | AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** | Purchased; arrival verification pending |
| Motherboard | ASUS TUF GAMING B650E-E WIFI, target SKU `90MB1LT0-M0EAY0` | **785.99 lei** | Purchased by exact model name; physical SKU verification pending |
| Primary SSD | Crucial T710 2 TB `CT2000T710SSD8` | **1,699.99 lei** | Purchased; arrival verification pending |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **683.99 lei** | Purchased; arrival verification pending |
| **Hardware subtotal** |  | **6,519.96 lei** |  |
| Courier |  | **11.99 lei** |  |
| **Order total** |  | **6,531.95 lei** |  |

## Executed Vexio order — 2026-09-01

| Item | Ordered identity | Vexio product code | Paid price incl. VAT | Status at capture |
|---|---|---|---:|---|
| Case | be quiet! Pure Base 501 Airflow Black **`BG074`** | `3137257` | **415.99 lei** | In processing |
| CPU cooler | Thermalright **Phantom Spirit 120 standard** | `2862553` | **246.99 lei** | Ready for delivery |
| Shipping |  |  | **0.00 lei** |  |
| **Order total** |  |  | **662.98 lei** |  |

**Committed total across both orders: 7,194.93 lei including shipping.**

Do not continue price-shopping any of these six purchased components unless an order is cancelled or a delivery/identity defect appears.

## Remaining selected build items

| Item | Exact target | Procurement status |
|---|---|---|
| RAM | Crucial Pro `CP2K24G56C46U5`, **48 GB = 2x24 GB**, DDR5-5600, non-ECC | **Not yet purchased — only remaining buy** |
| GPU | reuse existing RTX 3060 12 GB | Already owned |
| Host OS | Windows 11 Pro x64 | License already available; no procurement action |
| UPS | none | No purchase planned |
| Dedicated surge protector | none | No purchase planned |

## Provider strategy after two orders

EvoMAG and Vexio are now the two hardware providers used.

Only the exact RAM kit remains. A third provider is acceptable if necessary for `CP2K24G56C46U5`; do not disturb already executed orders for consolidation.

No Windows/software purchase remains.

## Motherboard naming warning

The selected board is:

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**

The EvoMAG order title matches **B650E-E WIFI**, but their page did not provide a trustworthy full manufacturer code. The decisive remaining check is the physical box label.

Reject:

> **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**

or B650E-PLUS / other similarly named boards.

## RAM decision — final

Selected:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2x24 GB DDR5-5600, non-ECC UDIMM.**

Do not substitute:

- a single 48 GB DIMM such as `CP24G56C46U5`;
- 2x32 / 2x64 merely because it is easier to source;
- four DIMMs as a planned upgrade path;
- RDIMM/server memory.

If 48 GB later proves insufficient under measured workloads, replace the pair with a larger matched two-DIMM kit rather than adding another pair.

## Remaining checkout gate

Before paying for RAM, verify:

1. exact SKU **`CP2K24G56C46U5`**;
2. total 48 GB as **2x24 GB**;
3. DDR5-5600 desktop non-ECC UDIMM;
4. new retail product with normal Romanian/EU warranty path;
5. delivered total including shipping and realistic lead time;
6. preserve invoice, serial numbers and packaging through commissioning and return windows.

## Arrival verification gates

### EvoMAG order

1. CPU: confirm **`100-100000719WOF`** / Box-WOF identity.
2. Motherboard: confirm **`90MB1LT0-M0EAY0`** on the physical box before opening/installing.
3. SSD: confirm **`CT2000T710SSD8`** and no factory heatsink.
4. PSU: confirm **`BP027EU`**, Pure Power 13 M 850W.
5. Inspect seals/packaging for damage or open-box substitution.
6. Photograph labels/serials and retain packaging.

### Vexio order

1. Case: confirm **Pure Base 501 Airflow Black `BG074`**, non-window model, with both included 140 mm PWM fans.
2. Cooler: confirm **Phantom Spirit 120 standard**, not SE/EVO, with both 120 mm fans and AM5 mounting hardware.
3. Inspect packaging for damage/prior use and retain labels/serials where applicable.

See `docs/checkout-checklist.md` for the operational verification workflow and `docs/purchases-2026-09-01.md` for the transaction ledger.

## Assembly-critical reminders

- RAM: install in **A2/B2**, Auto/JEDEC first.
- T710: install in **`M.2_1` CPU PCIe 5.0 x4** under the ASUS motherboard heatsink.
- PSU: use only modular cables supplied with the exact `BP027EU`.
- RTX 3060 is reused; no new GPU is in the order.
- Validate SMART/health before relying on older SATA drives.
- No UPS, RAID, SSD cache/tiering or dedicated surge protector initially.

## Purchase position

**Two hardware orders completed.** CPU, motherboard, SSD, PSU, cooler and case are committed. Windows is already available. Continue procurement only for **RAM**, then move to physical verification, assembly and commissioning.
