# Procurement Plan — 2026-08-31

This document turns the selected BOM into an order plan. Prices and stock are **observations, not promises**: re-check the actual product page/cart immediately before purchase.

## Procurement policy

- **PC Garage and Altex are co-preferred Romanian retailers**; **eMAG is also acceptable**.
- Use another established Romanian/EU retailer when a preferred source is unavailable, materially more expensive, or does not identify the exact SKU/revision clearly.
- Exact SKU/revision, seller quality, invoice/warranty path and product condition matter more than chasing the absolute lowest indexed price.
- Buy **new, sealed** components unless a deliberate exception is recorded.
- Do not substitute a similar-looking SKU without rechecking compatibility.

## Recommended initial order

| Item | Exact target | Current purchase route | Observed price | Confidence / gate |
|---|---|---|---:|---|
| CPU | AMD Ryzen 9 9950X3D **Box/WOF `100-100000719WOF`** | **EvoMAG** | **3,349.99 lei** | High: direct indexed page showed exact code, Box, limited local stock. Do not substitute Tray `100-000000719`. |
| Motherboard | ASUS **ProArt X870E-Creator WiFi** | **ITGalaxy** preferred for this order; ITArena is price-control alternative | ~**2,654 lei** ITGalaxy; ~2,542 lei ITArena | Medium-high: ITGalaxy offer was refreshed much more recently; paying ~112 lei over ITArena is acceptable for fresher stock evidence and consolidation. PC Garage was indexed unavailable and eMAG ~3,056 lei. |
| Phase-1 RAM | Crucial **`CT2K32G56C46U5`**, 64 GB (2×32), DDR5-5600 CL46, 1.1 V | Buy from a reputable seller only after exact-SKU cart check | ~**4.97–5.20k lei** current market control | **Strict gate:** page/cart/invoice must say `CT2K32G56C46U5`. Reject `CT2K32G56C46S5` (SO-DIMM/laptop). Romanian indexing is inconsistent. If Crucial rises close to Kingston pricing, recompare `KF556C36BBEK2-64`. |
| CPU cooler | Noctua **NH-D15 G2 standard `CPNTD15G2`** | **ITGalaxy** if exact standard SKU is confirmed; otherwise PC Garage/eMAG/Vexio | ~**701–730 lei** | Verify standard G2, not LBC/HBC or another variant. ITGalaxy currently indexed in stock around 701 lei. |
| System SSD | Samsung **990 PRO 2 TB `MZ-V9P2T0BW`** | **ITGalaxy** (consolidated) or PC Garage | ~**1,953 lei** ITGalaxy / **1,949.99 lei** PC Garage | High: exact SKU broadly identified. Buy bare drive; motherboard heatsink is used. |
| PSU | Seasonic **VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 revision** | **Altex**, product code `VERTEXGX1200` | **1,289.99 lei** | High listing confidence; **receipt gate remains mandatory**: ATX 3.1 + PCIe 5.1 + supplied 12V-2x6. Reject explicit ATX 3.0/12VHPWR old inventory. |
| Case | Fractal Design **North XL Mesh Charcoal Black `FD-C-NOR1X-01`** | **ForIT** | **1,018.51 lei** | High: direct listing explicitly says mesh and exact SKU/EAN. Reject TG Dark `FD-C-NOR1X-02` or ambiguous 'Solid' descriptions. |
| Rear fan | Noctua **NF-A14x25 G2 PWM**, standard square frame, EAN `9010018100617` | **Vexio** or another exact single-fan listing | ~**192.99 lei** | Verify **standard PWM**, not `NF-A14x25r`, not LS-PWM, and not an unnecessary 2-pack. |
| UPS | CyberPower **`CP1600EPFCLCD`** | **Checkout comparison required** | roughly **1.65–1.75k lei** in the latest consolidated controls | Model is closed, seller is not. Aggregators disagree materially and some direct pages are stale. Prefer an exact new unit from PC Garage/Altex/eMAG or another established seller when the checkout price is reasonable. Do not use a resigilat unit merely to hit an old low price. |
| Windows | Microsoft **Windows 11 Pro Retail/FPP USB English `HAV-00163`** | **ForIT** for consolidation; Prostore is price-control alternative | **1,146.55 lei** ForIT; **1,123.60 lei** Prostore | High: both direct indexed pages explicitly identify Retail/FPP and exact Microsoft SKU. **Do not substitute OEM/DSP or a standalone grey-market key.** |
| GPU | Existing RTX 3060 12 GB | Reuse | 0 lei | No purchase. |

## Suggested seller grouping

A practical order minimizes seller count without paying large premiums:

### EvoMAG

- Ryzen 9 9950X3D Box `100-100000719WOF`.
- RAM may also be bought here **only if the live cart shows exact `CT2K32G56C46U5` at a competitive price**. Cached/indexed EvoMAG RAM prices conflict, so do not rely on an old search snapshot.

### ITGalaxy

- ASUS ProArt X870E-Creator WiFi.
- Noctua NH-D15 G2 standard, after exact-SKU verification.
- Samsung 990 PRO 2 TB `MZ-V9P2T0BW`.

This grouping costs very little versus splitting each item across the absolute lowest seller and simplifies delivery/returns.

### Altex

- Seasonic VERTEX GX-1200 ATX 3.1 `VERTEXGX1200`.

### ForIT

- Fractal Design North XL Mesh `FD-C-NOR1X-01`.
- Windows 11 Pro Retail/FPP USB `HAV-00163`.

### Vexio / exact alternative

- one Noctua NF-A14x25 G2 PWM standard square-frame fan.

### UPS seller

Choose at checkout after a direct exact-product comparison. The UPS price is the least trustworthy part of the current aggregator snapshot and is not worth forcing into a specific seller prematurely.

## Current total

Using the current representative values:

- CPU 3,349.99
- motherboard ~2,654
- RAM ~4,974 (low current exact-SKU market control)
- cooler ~701
- SSD ~1,952.99
- PSU 1,289.99
- case 1,018.51
- rear fan ~192.99
- UPS ~1,666.10 representative current control
- Windows Retail/FPP 1,146.55

Representative complete initial purchase: approximately **18,946 lei**, before shipping.

Because RAM and UPS listings are volatile/inconsistent, use a practical checkout envelope of approximately **18.9–19.3k lei** rather than false precision.

The reused RTX 3060 is excluded from purchase cost. The future 4 TB+ work SSD, future GPU, eventual 256 GB memory and future UPS enlargement remain deferred.

## Hard acceptance gates

### CPU

- exact processor: Ryzen 9 9950X3D;
- prefer Box/WOF `100-100000719WOF`;
- do not accidentally order Tray because a search listing is cheaper.

### RAM

- exact string **`CT2K32G56C46U5`**;
- 2×32 GB;
- 288-pin desktop UDIMM;
- reject **`CT2K32G56C46S5`**, which is SO-DIMM/laptop memory;
- if the exact Crucial kit is no longer sensible at checkout, compare the explicitly ProArt-listed Kingston `KF556C36BBEK2-64` before substituting anything else.

### Cooler

- Noctua NH-D15 G2 **standard** base;
- exact ordinary model `CPNTD15G2` where retailer exposes a product code;
- do not substitute LBC/HBC without reopening the cooler decision.

### SSD

- exact Samsung `MZ-V9P2T0BW`;
- 2 TB, bare M.2 2280 drive;
- no bundled third-party heatsink required.

### PSU

- box/listing says **ATX 3.1**;
- PCIe 5.1 support;
- current **12V-2x6** GPU cable included;
- reject explicit ATX 3.0 / PCIe 5.0 / 12VHPWR old stock;
- use only Seasonic-approved modular cables.

### Case

- exact **`FD-C-NOR1X-01`**;
- Charcoal Black **Mesh** side panel;
- reject `FD-C-NOR1X-02` TG Dark unless the case decision is deliberately changed.

### Rear fan

- exact standard **NF-A14x25 G2 PWM**, 140 mm, square frame, 1500 RPM class;
- EAN `9010018100617` is useful confirmation;
- reject round-frame `NF-A14x25r G2` and LS-PWM variants for this role.

### UPS

- exact **`CP1600EPFCLCD`**;
- new/sealed;
- current European/Schuko configuration;
- verify delivered outlet count/configuration against current CyberPower specification.

### Windows

- **Windows 11 Pro**;
- **Retail/FPP**, not OEM/DSP;
- exact target `HAV-00163`;
- normal invoice and identifiable Microsoft packaged product;
- do not replace it with a cheap emailed standalone key.

## Ordering order

1. **CPU + motherboard + RAM** first because stock and RAM pricing are the most volatile.
2. **Cooler + SSD + PSU + case + rear fan** next; these are mature, well-identified parts.
3. **Windows Retail/FPP** can be ordered with the case or separately; it does not constrain hardware assembly.
4. **UPS** can be bought in the same wave, but choose the seller from a fresh direct-price check rather than an old aggregator minimum.
5. Keep all packaging, serial labels and invoices until the full workstation passes burn-in/validation.

## Sources / current controls

- EvoMAG Ryzen 9 9950X3D Box: https://www.evomag.ro/componente-pc-gaming-procesoare/amd-procesor-amd-ryzen-9-9950x3d-4.3ghz-144mb-170w-am5-box-4206997.html
- ProArt market control: https://www.pricy.ro/ProductUrlId/placa-de-baza-asus-proart-x870e-creator-wifi--socket-am5-7E95DB2CF7553837275C1FDE2803A4E0
- Crucial exact-kit market control: https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/
- NH-D15 G2 control: https://www.price.ro/preturi-noctua-nh-d15-g2-4652246
- Samsung 990 PRO control: https://solid-state-drive-ssd-intern.compari.ro/samsung/990-pro-2tb-m-2-mz-v9p2t0bw-p885630345/
- Seasonic Altex listing: https://altex.ro/sursa-pc-seasonic-vertex-gx-1200-atx-3-1-1200w-135mm-80-plus-gold-full-modular/cpd/VERTEXGX1200/
- North XL Mesh ForIT: https://www.forit.ro/fractal-design-north-xl-charcoal-black-tower-case-black-mesh-version-bp939671
- Noctua fan Vexio category control: https://www.vexio.ro/noctua/pagina10/
- CyberPower market control: https://www.compari.ro/ups-uri-surse-neintreruptibile-c3133/cyberpower/cp1600epfclcd-1600va-p1051248901/
- Windows Retail/FPP ForIT: https://www.forit.ro/sistem-de-operare-microsoft-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash-bp414367
- Windows Retail/FPP Prostore: https://www.prostore.ro/sisteme_de_operare/microsoft/93926-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash/
