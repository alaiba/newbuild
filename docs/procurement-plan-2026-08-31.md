# Procurement Plan — 2026-08-31

This document turns the selected BOM into an order plan optimized for **total ownership friction**, not merely the lowest item-by-item checkout price.

The procurement objective is now:

1. keep the initial order to **no more than three providers**;
2. prefer **two providers** when the price premium is modest;
3. add a third provider only when it saves roughly **300 lei or more net**, or materially improves stock, exact-SKU certainty, warranty, or revision certainty;
4. do not swap a long-lived component merely to eliminate a provider unless the replacement is at least as strong on stability, endurance and serviceability.

Prices and stock are observations, not promises. Re-check the live cart immediately before ordering.

## Recommended provider structure

### Provider 1 — EvoMAG: primary order

EvoMAG currently has a unusually strong concentration of the exact selected parts. Use it for the main order provided the live cart remains close to the current price controls.

| Item | Exact target | Current EvoMAG control | Gate |
|---|---|---:|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** | Exact Box/WOF; do not substitute Tray. |
| Motherboard | ASUS ProArt X870E-Creator WiFi | current feed ~**2,685 lei** | If live cart rises materially above ~2,850 lei, recompare before ordering. |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | **4,156.99 lei** current exact-SKU indexed offer | Strict `...U5` desktop-UDIMM gate; reject `...S5`. |
| CPU cooler | Noctua NH-D15 G2 **standard** | **690.99 lei** | Standard version, not LBC/HBC. |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | **1,899.99 lei** | Exact bare 2 TB drive. |
| Case | Fractal North XL Charcoal Black `FD-C-NOR1X-01` | **882.99 lei** | Exact SKU controls; retailer title says “Solid”, but Fractal identifies `-01` as the Mesh model. |
| Rear fan | Noctua NF-A14x25 G2 PWM, square frame | **200.99 lei** | Exact standard single fan is currently available, so no fan downgrade is needed for consolidation. |
| UPS | CyberPower `CP1600EPFCLCD` | current feeds conflict around **~1.55–1.90k lei** | Buy here if live cart is reasonably close to the broader market. See third-provider trigger below. |
| Windows | Windows 11 Pro Retail/FPP USB English `HAV-00163` | ~**1,200 lei** | Exact Retail/FPP SKU; the ~100–135 lei premium versus the lowest normal FPP offer is acceptable for consolidation. |
| GPU | Existing RTX 3060 12 GB | 0 lei | Reuse. |

### Provider 2 — Altex: PSU

Buy the selected PSU from Altex unless EvoMAG can explicitly confirm its unit is the current revision before shipment.

- **Seasonic VERTEX GX-1200**
- explicit **ATX 3.1** Altex listing
- current reference: **1,289.99 lei**
- required receipt/box gate: PCIe 5.1 + current **12V-2x6** cable

This remains preferable to changing PSU simply to reach one-provider procurement. Seasonic provides a **12-year warranty**, compact 160 mm depth, complete protections and an explicitly current ATX 3.1 product definition.

### One-provider opportunity

EvoMAG currently indexes a Seasonic VERTEX GX-1200 around the low-1.1k to low-1.3k lei range, but the listing does **not** identify the revision clearly enough to override the old-stock risk.

If EvoMAG confirms **in writing before shipment** that the exact unit is:

- ATX 3.1;
- PCIe 5.1;
- supplied with 12V-2x6 rather than old 12VHPWR;

then buy it from EvoMAG and collapse the entire initial BOM to **one provider**. Otherwise use Altex.

## Third-provider trigger

Do **not** add a third retailer for a 50–150 lei saving.

A third provider becomes rational only when one of these is true:

- net saving is roughly **300 lei or more** after delivery costs;
- the primary retailer cannot provide the exact SKU/revision;
- delivery/stock risk is materially better;
- warranty terms are materially better.

The most likely trigger is the UPS. Current CyberPower price feeds disagree materially. If EvoMAG checkout is around **1.55–1.70k lei**, keep it at EvoMAG. If EvoMAG is near **1.90k lei** while an established retailer such as Vexio remains around **1.53–1.55k lei**, using that retailer as provider #3 saves ~350 lei and is justified.

Do not create a third-provider relationship solely to save ~50 lei on Windows or ~100–150 lei on another individual component.

## Component-swap review

The provider consolidation pass explicitly reopened plausible value substitutions. The conclusion is deliberately conservative because “performance” for this build includes stability, endurance, serviceability and long ownership.

| Possible swap | Approx. saving | Verdict | Why |
|---|---:|---|---|
| Ryzen 9 9950X3D → Ryzen 9 9950X Box | ~**650 lei** | **Keep 9950X3D** | The 9950X3D is marginally ahead in GamersNexus' Chromium compile test while also preserving substantially stronger gaming performance. Same AM5/170 W class; the saving is not enough to weaken a permanent 10-year CPU choice. |
| ProArt X870E-Creator → ASRock X870 Taichi Creator | ~**900–1,000+ lei** | **Keep ProArt** | This is the largest cash saving but gives up the strongest explicit vendor/firmware evidence we found for the difficult eventual 4×64 GB / 256 GB and ECC-oriented stability target. It cuts against the primary goal. |
| NH-D15 G2 → Thermalright Phantom Spirit 120 SE | ~**400–490 lei** | **Keep Noctua** | Thermalright is excellent price/performance, but Noctua brings the stronger long-term mounting/support ecosystem, soldered fin/heatpipe construction, >150k-hour fan MTTF and 6-year manufacturer warranty. Those attributes matter on a 10-year workstation. |
| Samsung 990 PRO 2 TB → Kingston KC3000 2 TB | ~**50–60 lei** at EvoMAG | **Keep Samsung** | KC3000 is excellent and has strong endurance, but the saving is trivial. Samsung's mature firmware/tooling and already-selected topology win at this delta. |
| Seasonic VERTEX GX-1200 → be quiet! Straight Power 12 1200W `BN339` | ~**30–80 lei** in the relevant consolidated routes | **Keep Seasonic** | Straight Power 12 is technically excellent (ATX 3.1, Platinum, Japanese 105 °C capacitors, 10-year warranty), but the small saving does not justify giving up Seasonic's 12-year warranty and more compact 160 mm chassis simply to remove Altex. |
| Noctua NF-A14x25 G2 → ARCTIC P14/P14 Max | ~**125–160 lei** | **Keep Noctua** | A valid budget swap, but unnecessary now that EvoMAG sells the exact Noctua single fan. The Noctua's explicit >150k-hour MTTF and 6-year warranty better match the endurance-first goal for a small absolute premium. |
| CyberPower CP1600EPFCLCD → cheaper simulated-sine UPS | several hundred lei | **Keep CyberPower** | Pure sine output, Active-PFC compatibility, AVR and USB shutdown are deliberate reliability features; do not trade them away for nominal VA-per-leu. |
| Windows Retail/FPP → OEM/grey-market key | large headline saving | **Keep Retail/FPP** | Retail/FPP `HAV-00163` is the clean Microsoft licensing path for this DIY build and removes provenance/transfer ambiguity. |

## Current consolidated cost envelope

Using the current EvoMAG price controls plus the explicit Altex PSU:

- EvoMAG main-order subtotal with the lower current UPS feed: approximately **16,620 lei**;
- Altex Seasonic PSU: **1,289.99 lei**;
- representative two-provider total: approximately **17,910 lei before shipping**.

Because the EvoMAG UPS feed currently conflicts with an older direct-page price around 1.9k lei, a conservative checkout range is approximately **17.9–18.3k lei** before shipping.

This is materially below the prior 18.9–19.3k snapshot, primarily because the exact Crucial 64 GB kit is now indexed at roughly **4,157 lei** rather than ~5k.

## Hard acceptance gates

### CPU

- Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF`;
- do not silently substitute Tray.

### Motherboard

- exact ASUS ProArt X870E-Creator WiFi;
- ignore stale retailer metadata claiming a 192 GB maximum; ASUS platform selection was based on current official 256 GB support and firmware evidence.

### RAM

- exact **`CT2K32G56C46U5`**;
- 64 GB, 2×32;
- 288-pin desktop UDIMM;
- DDR5-5600 CL46, 1.1 V;
- reject **`CT2K32G56C46S5`** laptop SO-DIMM.

### Cooler

- NH-D15 G2 **standard**;
- use included AM5 offset mount;
- do not substitute LBC/HBC.

### SSD

- exact `MZ-V9P2T0BW`;
- 2 TB, bare M.2 2280.

### PSU

- listing/box must say **ATX 3.1**;
- PCIe 5.1;
- current **12V-2x6** GPU cable supplied;
- reject explicit old ATX 3.0 / 12VHPWR inventory;
- use only Seasonic-approved modular cables.

### Case

- exact **`FD-C-NOR1X-01`**;
- Fractal official product mapping identifies this as North XL Charcoal Black **Mesh**;
- reject `FD-C-NOR1X-02` TG Dark.

### Rear fan

- standard square-frame **NF-A14x25 G2 PWM** single fan;
- not round-frame `NF-A14x25r G2`;
- not LS-PWM.

### UPS

- exact **`CP1600EPFCLCD`**;
- new/sealed;
- European/Schuko configuration;
- verify delivered outlet configuration against CyberPower's current specification.

### Windows

- **Windows 11 Pro Retail/FPP**;
- exact `HAV-00163`;
- normal packaged Microsoft product/invoice;
- not OEM/DSP and not an undocumented emailed key.

## Ordering strategy

Place the EvoMAG main order first, but capture screenshots/PDFs of each product page and exact SKU/price before checkout. Place the Altex PSU order in the same purchasing session. If the EvoMAG VERTEX listing can be confirmed as current ATX 3.1 stock, consolidate the PSU there instead.

For supplier-stock items with long ETAs, do not dismantle the current working PC until CPU, motherboard, RAM, cooler and case are physically received and inspected.

Keep invoices, serial labels, packaging and the purchase-page evidence together in a single warranty folder for the life of the build.

## Current source controls

- EvoMAG 9950X3D Box: https://www.evomag.ro/componente-pc-gaming-procesoare/amd-procesor-amd-ryzen-9-9950x3d-4.3ghz-144mb-170w-am5-box-4206997.html
- ProArt current market: https://www.price.ro/preturi-asus-proart-x870e-creator-wifi-4691168
- EvoMAG Crucial exact kit: https://www.evomag.ro/componente-pc-gaming-memorii/crucial-kit-memorii-ram-crucial-dual-channel-2x32gb-ddr5-negru-4147822.html
- EvoMAG NH-D15 G2 standard: https://www.evomag.ro/componente-pc-gaming-coolere-coolere-cpu/noctua-cooler-procesor-noctua-nh-d15-g2-standard-compatibil-intel-amd-4175302.html
- EvoMAG Samsung 990 PRO 2 TB: https://www.evomag.ro/componente-pc-gaming-solid-state-drive-ssd/samsung-ssd-samsung-990-pro-2tb-pci-express-4.0-x4-m.2-2280-4031722.html
- EvoMAG North XL `FD-C-NOR1X-01`: https://www.evomag.ro/componente-pc-gaming-carcase/fractal-design-carcasa-fractal-design-north-xl-solid-middle-tower-fara-sursa-atx-e-atx-negru-4149667.html
- Fractal official North XL product mapping: https://www.fractal-design.com/products/cases/north/north-xl/rc-charcoal-black-tg-dark/
- EvoMAG NF-A14x25 G2 PWM: https://www.evomag.ro/componente-pc-gaming-coolere-ventilatoare/noctua-ventilator-noctua-nf-a14x25-g2-pwm-140mm-4197885.html
- CyberPower current market control: https://www.price.ro/preturi-cyberpower-cp1600epfclcd-4589246
- Windows `HAV-00163` price control: https://www.price.ro/preturi-microsoft-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash-3737377
- Altex explicit current Seasonic: https://altex.ro/sursa-pc-seasonic-vertex-gx-1200-atx-3-1-1200w-135mm-80-plus-gold-full-modular/cpd/VERTEXGX1200/
- Seasonic official VERTEX GX ATX 3.1: https://seasonic.com/vertex-gx/
- be quiet! Straight Power 12 1200W control: https://www.bequiet.com/en/powersupply/4105
