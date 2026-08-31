# Final Order Plan — 2026-08-31

Status: **Selected BOM closed; live Romanian price/provider consolidation complete.**

Prices below are reference checkout prices observed on 2026-08-31 and must still be confirmed in-cart immediately before payment. Shipping is excluded unless explicitly noted.

## Recommended provider split

Use **three providers overall, two for hardware**:

1. **EvoMAG** — CPU, RAM, cooler, case, SSD, PSU.
2. **ForIT** — exact motherboard.
3. **PROstore** — Windows 11 Pro Retail/FPP.

This satisfies the project's provider policy exactly: maximum three providers overall, with only two hardware suppliers.

## Order table

| Provider | Item | Exact target | Reference price |
|---|---|---|---:|
| EvoMAG | CPU | AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** |
| ForIT | Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | **874.17 lei** |
| EvoMAG | RAM | Crucial `CT2K64G56C46U5`, 128 GB (2×64 GB), DDR5-5600 CL46, 1.1 V | **7,699.99 lei** |
| EvoMAG | CPU cooler | Thermalright Phantom Spirit 120 — standard | **249.99 lei** |
| EvoMAG | Case | be quiet! Pure Base 501 Airflow Black `BG074` | **423.99 lei** |
| EvoMAG | Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | **1,710.99 lei** |
| EvoMAG | PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **686.99 lei** |
| PROstore | Windows | Windows 11 Pro 64-bit English Retail/FPP USB `HAV-00163` | **1,123.60 lei** |
| Reuse | GPU | Existing RTX 3060 12 GB | **0 lei** |
| Reuse | Cold storage | Existing healthy SATA drives | **0 lei** |
| None | UPS / dedicated surge protector | Not purchased | **0 lei** |

### Totals

- **EvoMAG hardware basket:** 14,121.94 lei
- **ForIT motherboard:** 874.17 lei
- **Hardware subtotal:** **14,996.11 lei**
- **PROstore Windows:** 1,123.60 lei
- **Selected-build total before shipping:** **16,119.71 lei**

Against the ~30,000 lei planning level, this leaves approximately **13,880 lei** unspent. That planning figure remains neither a cap nor a spending target.

## Why this split

### EvoMAG

EvoMAG currently consolidates six exact selected components without meaningful price sacrifice:

- CPU is in the ~3.35k-leu class and the exact Box/WOF SKU is surfaced;
- the exact Crucial RAM kit is the only currently surfaced Romanian offer for the selected SKU, despite its very poor market price;
- Phantom Spirit 120 is essentially at the current Romanian floor;
- Pure Base 501 is within only a few lei of the cheapest credible Romanian listing;
- T710 2 TB is within roughly tens of lei of the lowest surfaced offers while retaining the exact SKU and 60-month technical warranty listing;
- Pure Power 13 M 850W is competitively priced and carries the expected 120-month technical-warranty listing.

Fragmenting these six purchases across additional retailers would save only modest amounts outside the RAM item and would violate the supplier-consolidation objective without a useful architectural benefit.

### ForIT motherboard

ForIT currently lists the exact **TUF GAMING B650E-E WIFI** at about **874.17 lei** as supplier stock. This is materially better than the currently surfaced PC Garage price near 1.09k lei.

ASUS currently runs a Q3 2026 cashback promotion in which this exact motherboard (`90MB1LT0-M0EAY0`) qualifies for **90 lei**, but only purchases from the listed eligible partners qualify. The official Romanian partner list currently shows PC Garage, ITGalaxy and EvoMAG; ForIT is not listed. Even after a 90 lei cashback, the surfaced PC Garage price remains above the ForIT reference, so cashback does not currently change the supplier choice.

Do not rely blindly on comparison-engine sub-850-leu results for this board. Some surfaced comparison data traces to Polish retailer Morele and prices expressed in PLN, creating an unreliable apparent Romanian price floor. Use the exact Romanian retailer/SKU page at checkout.

### PROstore Windows

Keep the established **PROstore `HAV-00163`** target at approximately **1,123.60 lei**. It is the exact Retail/FPP English USB SKU and remains cheaper than the current EvoMAG listing by roughly 76 lei. A suspicious class of ~225–350 lei listings exists for products described with the same Microsoft part number; do not substitute one of those without a separate provenance/licensing review.

## RAM warning — only abnormal item

The exact **Crucial `CT2K64G56C46U5`** kit is by far the least attractive price in the order:

- current surfaced EvoMAG price: **~7,699.99 lei**;
- roughly **48% of the entire selected-build total**;
- Romanian comparison listings show essentially no competing in-stock offer for the exact SKU;
- European listings are also currently highly distorted, ranging from approximately €1.2k to well above €1.8k, so this is not merely one Romanian retailer charging an ordinary premium.

The RAM architecture and exact SKU remain selected. However, **this is the one component worth refreshing immediately before checkout and the one item where delaying purchase for a materially better supply window could save meaningful money**.

Do not replace it silently with RDIMM, four DIMMs, a different capacity topology or a high-voltage enthusiast kit merely to escape the current price.

## Checkout gates

Before paying:

1. Verify every exact manufacturer SKU, especially `90MB1LT0-M0EAY0`, `CT2K64G56C46U5`, `CT2000T710SSD8` and `BP027EU`.
2. Confirm all products are new retail units, not tray/open-box/refurbished substitutes unless explicitly accepted.
3. Recheck the RAM price first; stop and re-evaluate if a credible exact-SKU offer materially undercuts EvoMAG.
4. Confirm the T710 is the **bare/non-heatsink** `CT2000T710SSD8` variant.
5. Confirm the CPU is **Box/WOF `100-100000719WOF`**, not the tray SKU.
6. Confirm PSU is **Pure Power 13 M 850W `BP027EU`**, not Pure Power 12 M or another wattage/revision.
7. Confirm motherboard is **B650E-E**, not the easily confused B650-E or B650E-PLUS.
8. Confirm Windows is genuine **Retail/FPP English USB `HAV-00163`**.
9. Check delivered shipping totals before deciding whether any low-value item should move between EvoMAG and ForIT.
10. Preserve invoices, serial numbers and packaging through commissioning/return windows.

## Assembly-critical reminders

- Install RAM in **A2/B2** and commission at Auto/JEDEC first.
- Install T710 in **M.2_1 CPU PCIe 5.0 x4** under the ASUS motherboard heatsink.
- Reuse only the modular cables supplied with the exact `BP027EU` PSU.
- Reuse the RTX 3060; no new GPU is in the order.
- Validate SMART/health before reusing older SATA drives.
- No UPS, RAID, SSD cache/tiering or dedicated surge protector is part of the initial order.

## Purchase position

The architecture no longer needs another component-selection pass. The build is **purchase-ready**, subject only to same-day stock/price verification — with special scrutiny on the exceptionally volatile 128 GB RAM kit.
