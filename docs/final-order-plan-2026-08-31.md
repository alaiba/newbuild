# Final Order Plan — 2026-08-31

Status: **component selection closed; same-day checkout verification remains.**

Prices below are reference values observed during the 2026-08-31 procurement pass. They must be rechecked immediately before payment. Shipping is excluded unless explicitly noted.

## Selected build

| Item | Exact target |
|---|---|
| CPU | AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF` |
| Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` |
| RAM | Crucial Pro `CP2K24G56C46U5`, **48 GB = 2×24 GB**, DDR5-5600, non-ECC |
| Cooler | Thermalright Phantom Spirit 120 — standard |
| Case | be quiet! Pure Base 501 Airflow Black `BG074` |
| Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` |
| GPU | reuse existing RTX 3060 12 GB |
| Windows | Windows 11 Pro 64-bit English Retail/FPP USB `HAV-00163` |
| UPS | none |
| Dedicated surge protector | none |

## Provider strategy

Preferred outcome is at most **three providers overall / two hardware providers**.

Current procurement shape:

1. **EvoMAG** — preferred main hardware basket if all exact SKUs are confirmed in-cart, especially motherboard `90MB1LT0-M0EAY0`.
2. **RAM supplier** — use another Romanian hardware retailer if the exact `CP2K24G56C46U5` is materially cheaper or unavailable at EvoMAG. Current research has surfaced ForIT/dataSPOT/CEL-class alternatives; refresh live availability and delivered price.
3. **PROstore** — Windows 11 Pro Retail/FPP `HAV-00163` unless another equally trustworthy Retail/FPP source is materially better.

Do not force RAM into EvoMAG merely for consolidation if doing so requires a worse kit or a large premium.

## Motherboard naming warning

The selected board is:

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**

EvoMAG also sells the similarly named:

> **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**

They are distinct boards. Verify the exact manufacturer part number on the product page, in cart/order confirmation, and on the physical box.

## RAM decision — final

Selected:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2×24 GB DDR5-5600, non-ECC UDIMM.**

Do not substitute:

- a single 48 GB DIMM such as `CP24G56C46U5`;
- 2×32 / 2×64 merely because it is easier to source;
- four DIMMs as a planned upgrade path;
- RDIMM/server memory.

Current reference price class during the decision was approximately **~2.6–2.9k lei**, depending on supplier/lead time. Treat that only as a comparison reference and refresh immediately before payment.

If 48 GB later proves insufficient under measured workloads, replace the pair with a larger matched two-DIMM kit rather than adding another pair.

## Reference non-RAM basket

The last consolidated non-RAM reference was approximately:

| Provider | Item | Exact target | Reference price |
|---|---|---|---:|
| EvoMAG | CPU | `100-100000719WOF` | ~3,349.99 lei |
| EvoMAG | Motherboard | `90MB1LT0-M0EAY0` | ~843.99 lei class |
| EvoMAG | Cooler | Phantom Spirit 120 standard | ~249.99 lei |
| EvoMAG | Case | `BG074` | ~423.99 lei |
| EvoMAG | SSD | `CT2000T710SSD8` | ~1,710.99 lei |
| EvoMAG | PSU | `BP027EU` | ~686.99 lei |
| PROstore | Windows | `HAV-00163` | ~1,123.60 lei |

Reference non-RAM subtotal including Windows: approximately **8,389.54 lei** before shipping.

With RAM around **2.6–2.9k lei**, the complete build is therefore roughly **~11.0–11.3k lei before shipping**, reusing the RTX 3060 and existing SATA storage.

This is **not a live checkout quote**.

## Checkout gates

Before payment, verify all of the following:

1. CPU is **`100-100000719WOF`**, Box/WOF, not tray.
2. Motherboard is **`90MB1LT0-M0EAY0`**, not `90MB1GT0-M0EAY0` or another similarly named board.
3. RAM is **`CP2K24G56C46U5`**, total 48 GB as **2×24 GB**.
4. SSD is **`CT2000T710SSD8`**, the bare/non-heatsink T710 2 TB variant.
5. PSU is **`BP027EU`**, Pure Power 13 M 850W.
6. Windows is genuine **Retail/FPP English USB `HAV-00163`**.
7. All hardware is new retail product with a normal Romanian/EU warranty path.
8. Delivered totals include shipping and any lead-time implications.
9. Preserve invoices, serial numbers and packaging through commissioning and return windows.

See `docs/checkout-checklist.md` for the operational verification workflow.

## Assembly-critical reminders

- RAM: install in **A2/B2**, Auto/JEDEC first.
- T710: install in **`M.2_1` CPU PCIe 5.0 x4** under the ASUS motherboard heatsink.
- PSU: use only modular cables supplied with the exact `BP027EU`.
- RTX 3060 is reused; no new GPU is in the order.
- Validate SMART/health before relying on older SATA drives.
- No UPS, RAID, SSD cache/tiering or dedicated surge protector initially.

## Purchase position

**Purchase-ready architecture.** No component-selection question remains open. Perform only same-day live verification of stock, exact SKUs, warranty, delivered prices and retailer quality before paying.
