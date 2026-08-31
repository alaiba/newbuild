# Checkout / Arrival Verification Checklist

Use this checklist for remaining purchases and again when physical packages arrive.

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

Order total: **6,531.95 lei including 11.99 lei courier**.

For these four, use the **arrival checks** below; do not re-shop them unless there is a problem.

Windows 11 Pro is already available and is **not a checkout item**.

Still to purchase:

- RAM;
- cooler;
- case.

## Exact purchase / arrival gates

| Item | Required identity | Current state | Reject / special warning |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D **`100-100000719WOF`** | Purchased | Reject silent tray/OEM substitution |
| Motherboard | ASUS TUF GAMING B650E-E WIFI **`90MB1LT0-M0EAY0`** | Purchased by model name; physical SKU pending | Do not confuse with B650-E **`90MB1GT0-M0EAY0`** or B650E-PLUS |
| RAM | Crucial Pro **`CP2K24G56C46U5`**, 48 GB = **2×24 GB** | Not yet purchased | Reject single-DIMM `CP24G56C46U5`, RDIMM or different topology |
| Cooler | Thermalright **Phantom Spirit 120 standard** | Not yet purchased | Do not silently substitute SE/EVO |
| Case | be quiet! Pure Base 501 Airflow Black **`BG074`** | Not yet purchased | Confirm both included 140 mm PWM fans are present |
| SSD | Crucial T710 2 TB **`CT2000T710SSD8`** | Purchased | Must be bare/non-heatsink variant |
| PSU | be quiet! Pure Power 13 M 850W **`BP027EU`** | Purchased | Reject Pure Power 12 M, other wattage/revision; never mix modular cables |

## Remaining retailer-page checks

For RAM, cooler and case:

- confirm the manufacturer part number/model in the specification table, not only the marketing title;
- confirm the product is new retail stock, not open-box/refurbished/tray unless explicitly accepted;
- record price including VAT;
- record stock state and realistic lead time;
- record warranty duration/path;
- record delivery/shipping cost when available;
- capture the product URL and, if useful, a screenshot/PDF before payment.

If the page does not expose the exact manufacturer SKU, do not infer it from the title. Ask the retailer or choose a clearer listing.

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

## Remaining component-specific purchase checks

### RAM

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

### Cooler

Required:

> Thermalright **Phantom Spirit 120 standard**

Do not silently substitute the **SE** or **EVO** variant. A different variant requires explicit review.

### Case

Required:

> be quiet! Pure Base 501 Airflow Black `BG074`

Confirm the exact non-window Airflow Black model and both included 140 mm PWM fans.

## Provider/price consolidation

Policy after the first order:

- EvoMAG is already the first hardware provider;
- prefer at most one additional hardware provider for RAM + cooler + case;
- exact SKU/model, warranty and retailer quality outrank small savings;
- do not substitute the case/cooler merely to keep everything at EvoMAG.

Calculate final cost using **delivered totals**, not product-price sums alone. Do not include Windows in remaining procurement cost.

## Physical arrival checks — all hardware

Before opening/installing components:

- photograph the box label showing SKU/serial where practical;
- compare the printed SKU to this checklist and the invoice/order confirmation;
- inspect packaging/seals for signs of open-box substitution or shipping damage;
- keep packaging, invoices and serial records through commissioning and return windows.

Do not install a mismatched component merely to see whether it works; installation can complicate a return.

## After verification

Once every item passes the exact-SKU checks, proceed to assembly/commissioning using `docs/final-build.md` and the component dossiers.
