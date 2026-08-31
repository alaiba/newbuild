# Procurement Plan — 2026-08-31

> Updated 2026-09-01 after the EvoMAG and Vexio orders were placed and Windows was removed from procurement because the license is already available.

Status: **nearly complete**. Architecture remains closed.

## Locked principles

1. Maximum three providers overall; prefer fewer when exact SKUs remain available.
2. Optimize utility per leu, not benchmark prestige.
3. Preserve exact product identities where similarly named substitutes differ.
4. Keep AM5 memory at **two DIMMs / 1DPC**.
5. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.
6. **Do not re-shop components already purchased** unless an order/delivery defect requires it.
7. Windows is already available and must not be included in remaining procurement totals.

## Executed orders

### EvoMAG — 2026-09-01

| Item | Paid price incl. VAT |
|---|---:|
| Ryzen 9 9950X3D Box/WOF | **3,349.99 lei** |
| ASUS TUF GAMING B650E-E WIFI | **785.99 lei** |
| Crucial T710 2 TB | **1,699.99 lei** |
| be quiet! Pure Power 13 M 850W | **683.99 lei** |
| **Hardware subtotal** | **6,519.96 lei** |
| Courier | **11.99 lei** |
| **Total** | **6,531.95 lei** |

### Vexio — 2026-09-01

| Item | Paid price incl. VAT |
|---|---:|
| be quiet! Pure Base 501 Airflow Black `BG074` | **415.99 lei** |
| Thermalright Phantom Spirit 120 standard | **246.99 lei** |
| Shipping | **0.00 lei** |
| **Total** | **662.98 lei** |

**Committed total: 7,194.93 lei including shipping.**

These six new hardware items are committed purchases. Their next gate is physical arrival verification.

## Remaining provider strategy

- EvoMAG and Vexio are already the two hardware providers used.
- Only RAM remains to purchase.
- A third provider is acceptable if needed for the exact `CP2K24G56C46U5` at a sensible delivered price.
- Do not change any already purchased component for consolidation.
- No software retailer is required for Windows.

## Selected purchase targets and state

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **purchased 2026-09-01 / arrival verification pending** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **purchased 2026-09-01 by exact model name / physical SKU verification pending** |
| RAM | **Crucial Pro `CP2K24G56C46U5`, 48 GB = 2x24 GB, DDR5-5600, 1.1 V-class, non-ECC** | **selected / not yet purchased — only remaining buy** |
| CPU cooler | Thermalright Phantom Spirit 120 standard | **purchased 2026-09-01 from Vexio / arrival verification pending** |
| Case | be quiet! Pure Base 501 Airflow Black `BG074` | **purchased 2026-09-01 from Vexio / arrival verification pending** |
| Case fans | two included 140 mm PWM only initially | included with purchased case |
| Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | **purchased 2026-09-01 / arrival verification pending** |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **purchased 2026-09-01 / arrival verification pending** |
| GPU | existing RTX 3060 12 GB | reuse |
| Host OS | Windows 11 Pro x64 | **license already available / no procurement action** |
| UPS | none | selected |
| Dedicated surge protector | none | selected |

## RAM acceptance gate

- exact matched kit: **Crucial Pro `CP2K24G56C46U5`**;
- 48 GB = **2x24 GB**;
- non-ECC UDIMM;
- DDR5-5600;
- conservative 1.1 V-class operation;
- install in A2/B2;
- do not add a second pair later.

If 48 GB later proves insufficient under measured real workloads, replace the pair with a larger matched two-DIMM kit. Do not move to four DIMMs simply to preserve the initial kit.

## Arrival acceptance gates for purchased hardware

### Motherboard

- required physical SKU: **`90MB1LT0-M0EAY0`**;
- order title matches **TUF GAMING B650E-E WIFI**;
- do not accept **B650-E `90MB1GT0-M0EAY0`** or another similarly named board;
- verify before opening/installing.

### CPU

- confirm **`100-100000719WOF`** / Box-WOF identity;
- reject tray/OEM substitution.

### Cooler

- confirm **Thermalright Phantom Spirit 120 standard**;
- reject SE/EVO substitution;
- confirm both 120 mm fans and AM5 mounting hardware.

### Case

- confirm **be quiet! Pure Base 501 Airflow Black `BG074`**;
- confirm non-window Airflow Black model and both included 140 mm PWM fans.

### Storage

- confirm Crucial T710 2 TB **`CT2000T710SSD8`**;
- bare/non-heatsink variant;
- install in CPU-direct `M.2_1` under the ASUS heatsink.

### PSU

- confirm be quiet! Pure Power 13 M 850W **`BP027EU`**;
- ATX 3.1;
- complete original modular cable set;
- use only cables supplied with this PSU.

## Mains-protection policy

- no UPS;
- no dedicated surge protector;
- properly earthed wall outlet;
- ordinary reputable 16 A Schuko strip only if additional sockets are needed.

## Current cost position

**Committed spend:** **7,194.93 lei including shipping** for CPU + motherboard + SSD + PSU + cooler + case.

Remaining spend is only for **RAM**. Windows is already available and is excluded from procurement cost calculations.

## Next procurement sequence

1. Source exact **`CP2K24G56C46U5`** RAM.
2. When EvoMAG delivery arrives, verify CPU/motherboard/SSD/PSU identities before installation.
3. When Vexio delivery arrives, verify `BG074` case and standard Phantom Spirit 120 identity before installation.
4. Preserve invoices, serials and packaging through commissioning/return windows.

## Decision status

No architecture question remains open. Procurement is nearly complete; continue only with the **RAM purchase** and arrival verification of the two executed orders.
