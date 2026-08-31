# Checkout Verification Checklist

Use this checklist immediately before payment and again when the physical packages arrive.

## Verification levels

For every purchased component, verify at three levels:

1. **Retailer product page** — exact manufacturer SKU/specification.
2. **Cart / order confirmation / invoice** — the same exact SKU, no silent normalization or substitution.
3. **Physical box label before assembly** — exact SKU and product identity match the order.

If any level disagrees, stop and resolve the discrepancy before installation.

## Exact purchase gates

| Item | Required identity | Reject / special warning |
|---|---|---|
| CPU | AMD Ryzen 9 9950X3D **`100-100000719WOF`** | Reject silent tray/OEM substitution |
| Motherboard | ASUS TUF GAMING B650E-E WIFI **`90MB1LT0-M0EAY0`** | Do not confuse with B650-E **`90MB1GT0-M0EAY0`** or B650E-PLUS |
| RAM | Crucial Pro **`CP2K24G56C46U5`**, 48 GB = **2×24 GB** | Reject single-DIMM `CP24G56C46U5`, RDIMM or different topology |
| Cooler | Thermalright **Phantom Spirit 120 standard** | Do not silently substitute SE/EVO |
| Case | be quiet! Pure Base 501 Airflow Black **`BG074`** | Confirm both included 140 mm PWM fans are present |
| SSD | Crucial T710 2 TB **`CT2000T710SSD8`** | Must be bare/non-heatsink variant |
| PSU | be quiet! Pure Power 13 M 850W **`BP027EU`** | Reject Pure Power 12 M, other wattage/revision; never mix modular cables |
| Windows | Windows 11 Pro **Retail/FPP English USB `HAV-00163`** | Reject OEM/System Builder or suspicious digital-key substitution |

## Retailer-page checks

For each page:

- confirm the manufacturer part number in the specification table, not only the marketing title;
- confirm the product is new retail stock, not open-box/refurbished/tray unless explicitly accepted;
- record price including VAT;
- record stock state and realistic lead time;
- record warranty duration/path;
- record delivery/shipping cost when available;
- capture the product URL and, if useful, a screenshot/PDF before payment.

If the page does not expose the exact manufacturer SKU, do not infer it from the title. Ask the retailer or choose a clearer listing.

## Cart / order checks

Before submitting an order:

- re-check every exact SKU in cart;
- check quantities;
- check VAT and shipping;
- check seller identity if the retailer operates a marketplace;
- make sure no automatic alternative/substitute has been inserted;
- preserve the order confirmation and invoice.

## Component-specific checks

### Motherboard

Required:

> `90MB1LT0-M0EAY0` — TUF GAMING B650E-E WIFI

Known naming trap:

> `90MB1GT0-M0EAY0` — TUF GAMING B650-E WIFI

The names differ by a single `E`, so the manufacturer part number is the purchase control.

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
- normal manufacturer-warranty path;
- original complete modular cable set.

Only cables supplied with this exact PSU may be used.

### Windows

Required:

> `HAV-00163`

Confirm:

- Windows 11 Pro;
- Retail/FPP;
- English;
- USB package.

A cheap key-only/OEM listing is not an equivalent substitute.

## Provider/price consolidation

Policy:

- maximum three providers overall;
- target at most two hardware providers;
- use a separate RAM supplier if the exact `CP2K24G56C46U5` is materially cheaper than the main hardware retailer;
- exact SKU, warranty and retailer quality outrank small savings.

Calculate final cost using **delivered totals**, not product-price sums alone.

## Physical arrival checks

Before opening/installing components:

- photograph the box label showing SKU/serial where practical;
- compare the printed SKU to this checklist and the invoice;
- inspect packaging/seals for signs of open-box substitution or shipping damage;
- keep packaging, invoices and serial records through commissioning and return windows.

Do not install a mismatched component merely to see whether it works; installation can complicate a return.

## After verification

Once every item passes the exact-SKU checks, proceed to assembly/commissioning using `docs/final-build.md` and the component dossiers.
