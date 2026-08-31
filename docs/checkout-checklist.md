# Checkout / Arrival Verification Checklist

Use this checklist for the final RAM purchase and again when physical packages arrive.

## Verification levels

For every purchased component, verify at three levels:

1. **Retailer product page** — exact manufacturer SKU/specification.
2. **Cart / order confirmation / invoice** — the same exact SKU, no silent normalization or substitution.
3. **Physical box label before assembly** — exact SKU and product identity match the order.

If any level disagrees, stop and resolve the discrepancy before installation.

## Purchase state — 2026-09-01

Already purchased from EvoMAG:

- CPU — Ryzen 9 9950X3D Box/WOF;
- motherboard — ASUS TUF GAMING B650E-E WIFI;
- SSD — Crucial T710 2 TB;
- PSU — be quiet! Pure Power 13 M 850W.

EvoMAG total: **6,531.95 lei including 11.99 lei courier**.

Already purchased from Vexio:

- case — be quiet! Pure Base 501 Airflow Black `BG074`, **415.99 lei**;
- cooler — Thermalright Phantom Spirit 120 standard, **246.99 lei**;
- shipping — **0.00 lei**.

Vexio total: **662.98 lei**.

**Committed total: 7,194.93 lei including shipping.**

Windows 11 Pro is already available and is **not a checkout item**.

Still to purchase:

- **RAM only**.

## Exact purchase / arrival gates

| Item | Required identity | Current state | Reject / special warning |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D **`100-100000719WOF`** | Purchased | Reject silent tray/OEM substitution |
| Motherboard | ASUS TUF GAMING B650E-E WIFI **`90MB1LT0-M0EAY0`** | Purchased by model name; physical SKU pending | Do not confuse with B650-E **`90MB1GT0-M0EAY0`** or B650E-PLUS |
| RAM | Crucial Pro **`CP2K24G56C46U5`**, 48 GB = **2x24 GB** | **Not yet purchased — only remaining buy** | Reject single-DIMM `CP24G56C46U5`, RDIMM or different topology |
| Cooler | Thermalright **Phantom Spirit 120 standard** | Purchased from Vexio | Reject SE/EVO substitution; confirm both fans and AM5 mounting hardware |
| Case | be quiet! Pure Base 501 Airflow Black **`BG074`** | Purchased from Vexio | Confirm non-window model and both included 140 mm PWM fans |
| SSD | Crucial T710 2 TB **`CT2000T710SSD8`** | Purchased | Must be bare/non-heatsink variant |
| PSU | be quiet! Pure Power 13 M 850W **`BP027EU`** | Purchased | Reject Pure Power 12 M, other wattage/revision; never mix modular cables |

## Remaining retailer-page checks — RAM only

For the RAM listing:

- confirm exact manufacturer part number `CP2K24G56C46U5`;
- confirm the product is new retail stock, not open-box/refurbished;
- confirm 48 GB total as two 24 GB desktop UDIMMs;
- confirm DDR5-5600 and non-ECC;
- record price including VAT;
- record stock state and realistic lead time;
- record warranty duration/path;
- record delivery/shipping cost when available.

Do not infer equivalence from capacity/speed alone. The exact matched kit is the purchase control.

## Arrival checks for the EvoMAG order

Before opening or installing the purchased hardware:

### CPU

Required:

> `100-100000719WOF` — Ryzen 9 9950X3D Box/WOF

Check the box label and package identity. Reject tray/OEM substitution.

### Motherboard

Required:

> `90MB1LT0-M0EAY0` — TUF GAMING B650E-E WIFI

Known naming trap:

> `90MB1GT0-M0EAY0` — TUF GAMING B650-E WIFI

The EvoMAG order text matches **B650E-E WIFI**, but the physical manufacturer part number is the final control. Do not install until `90MB1LT0-M0EAY0` is confirmed.

### SSD

Required:

> `CT2000T710SSD8`

Confirm the SSD has **no factory heatsink**. It will be installed under the selected ASUS motherboard M.2 heatsink in `M.2_1`.

### PSU

Required:

> `BP027EU`

Confirm:

- Pure Power **13 M**;
- **850 W**;
- new retail unit;
- original complete modular cable set;
- no shipping damage or signs of prior use.

Only cables supplied with this exact PSU may be used.

## Arrival checks for the Vexio order

### Cooler

Required:

> Thermalright **Phantom Spirit 120 standard**

Confirm:

- standard model, not **SE** or **EVO**;
- seven heatpipes;
- approximately 157 mm tower height;
- two 120 mm fans corresponding to the standard model;
- AM5 mounting hardware present;
- no shipping damage or signs of prior use.

### Case

Required:

> be quiet! Pure Base 501 Airflow Black **`BG074`**

Confirm:

- exact `BG074` identity;
- non-window Airflow Black variant;
- both included 140 mm PWM fans present;
- panels, mesh, connectors and accessory box undamaged/complete.

## RAM purchase check

Required:

> `CP2K24G56C46U5`

Confirm all of:

- 48 GB total;
- **2 modules**;
- **24 GB per module**;
- DDR5-5600;
- desktop UDIMM;
- non-ECC.

A listing for a single 48 GB module is not equivalent even if the frequency/timings look identical.

## Provider/price consolidation

Policy after the two executed orders:

- EvoMAG and Vexio are already the two hardware providers used;
- a third provider is acceptable for the exact RAM kit if necessary;
- exact SKU, warranty and retailer quality outrank small savings;
- do not disturb already placed orders for consolidation.

Calculate final cost using **delivered totals**. Do not include Windows in remaining procurement cost.

## Physical arrival checks — all hardware

Before opening/installing components:

- photograph the box label showing SKU/serial where practical;
- compare the printed SKU to this checklist and the invoice/order confirmation;
- inspect packaging/seals for signs of open-box substitution or shipping damage;
- keep packaging, invoices and serial records through commissioning and return windows.

Do not install a mismatched component merely to see whether it works; installation can complicate a return.

## After verification

Once RAM is purchased and every item passes the exact-SKU checks, proceed to assembly/commissioning using `docs/final-build.md` and the component dossiers.
