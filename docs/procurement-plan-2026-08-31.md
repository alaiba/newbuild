# Procurement Plan — 2026-08-31

This plan optimizes the selected workstation for **total lifetime value and administrative simplicity**, not the absolute lowest item-by-item price.

## Procurement objective

1. Maximum **three providers**.
2. Default target: **two hardware providers**.
3. Add a third hardware provider only for roughly **≥300 lei net saving**, materially better stock/revision certainty, or materially better warranty/service.
4. **Windows is an explicit exception**: because a Retail/FPP license has negligible long-term RMA burden, use a separate reputable software retailer when it gives a cleaner price/provenance result even for a smaller saving.
5. Consider both cheaper substitutions and premium upgrades when they improve utility per leu for stability, endurance, serviceability or useful lifetime.

## Recommended provider structure

### Provider 1 — EvoMAG: primary hardware order

Use EvoMAG for the ordinary BOM while the live cart remains close to current controls.

| Item | Exact target | Working price control | Gate |
|---|---|---:|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | ~3,349.99 lei | exact Box/WOF preferred |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~2,685 lei | recompare if cart moves materially above ~2.85k |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | ~4,799.99 lei | exact `...U5`; reject laptop `...S5` |
| Cooler | Noctua NH-D15 G2 standard | ~690.99 lei | standard, not LBC/HBC |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | ~1,899.99 lei | exact bare 2 TB drive |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | ~882.99 lei | exact SKU; `-01` is Mesh |
| Rear fan | Noctua NF-A14x25 G2 PWM standard single | ~200.99 lei | square-frame standard PWM |
| UPS | CyberPower PR1500ELCD | ~2,948.99 lei | exact 1500 VA / 1350 W model |
| GPU | existing RTX 3060 12 GB | 0 lei | reuse |

### Provider 2 — Altex: PSU

Baseline purchase:

- **Seasonic VERTEX GX-1200 ATX 3.1**
- current explicit reference: ~**1,289.99 lei**
- hard receipt gate: PCIe 5.1 + supplied 12V-2x6.

Premium rule: if a known-current **VERTEX PX-1200 ATX 3.1** is actually in stock at **≤~200 lei premium** over GX, prefer PX. Do not delay the build for it.

### Provider 3 — PROstore: Windows

Selected Windows purchase:

- **Microsoft Windows 11 Pro Retail/FPP USB English `HAV-00163`**
- direct verified listing: **1,123.60 lei**
- supplier stock
- manufacturer code explicitly shown as `HAV-00163`
- Retail/FPP explicitly stated
- country shipping currently **27.23 lei**, for an effective delivered control of about **1,150.83 lei** outside Bucharest.

This is preferable to paying ~1,199.99 lei for `HAV-00197` at EvoMAG solely to keep Windows inside the hardware order. Windows has essentially no wear/RMA lifecycle, so the additional invoice/provider relationship carries little long-term cost.

Purchase page: https://www.prostore.ro/sisteme_de_operare/microsoft/93926-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash/

## Windows provider comparison

| Seller | Exact verified product | Working price | Delivery / stock | Verdict |
|---|---|---:|---|---|
| **PROstore** | `HAV-00163`, Retail/FPP, English USB | **1,123.60 lei** | supplier stock; ~27.23 lei delivery outside Bucharest | **Selected** |
| ForIT | `HAV-00163`, Retail/FPP, English USB | 1,146.55 lei | supplier stock; ~21.99 lei delivery | Good fallback, ~18 lei more delivered |
| CEL.ro | `HAV-00163`, English USB | ~1,141–1,144 lei | seller-direct but current stock shown as “ask” | Do not prefer over a verified supplier-stock route |
| EvoMAG | `HAV-00163` English / `HAV-00197` Romanian Retail package | ~1,199.99 lei | consolidation benefit only | Not worth ~49 lei extra versus PROstore delivered once Windows is treated as low-RMA friction |
| Very cheap 20–250 lei marketplace/ESD offers | unclear provenance/channel | much lower | key-only / provenance uncertain | Reject |

Price aggregators also show an apparent ~1,055.84 lei offer from Shoop, but it was not sufficiently verified in the direct-source pass to displace the clearly identified PROstore offer. Reopen if a direct page confirms exact `HAV-00163`, Retail/FPP, stock and normal invoice/provenance.

## Current provider count

The planned purchase therefore uses exactly **three providers**:

1. **EvoMAG** — main hardware;
2. **Altex** — explicit-current Seasonic PSU;
3. **PROstore** — Windows Retail/FPP.

This satisfies the maximum-three-provider requirement. The third provider is software-only and therefore does not materially increase future warranty/RMA complexity.

## Widened value decisions

- Keep **9950X3D** rather than save ~650 lei with 9950X.
- Keep **ProArt X870E-Creator** rather than save ~900–1,000+ lei and weaken the strongest 256 GB/ECC evidence.
- Keep **NH-D15 G2** rather than downgrade long-term support/endurance for ~400–490 lei.
- Keep **990 PRO 2 TB**; KC3000 saves too little and 9100 PRO's Gen5 premium is wasted in the selected system slot.
- Keep **Crucial 64 GB** while its price advantage over the explicitly compatible Kingston remains material.
- **Upgrade UPS to PR1500ELCD** for 1350 W real output and future-GPU lifecycle value.
- Prefer **VERTEX PX-1200** only if actually available within ~200 lei of GX; otherwise buy GX.

## Hard acceptance gates

- CPU: Ryzen 9 9950X3D Box/WOF `100-100000719WOF` preferred.
- Motherboard: exact ASUS ProArt X870E-Creator WiFi.
- RAM: exact `CT2K32G56C46U5`, 64 GB 2×32 desktop UDIMM; reject `...S5`.
- Cooler: NH-D15 G2 standard, no LBC/HBC substitution.
- SSD: exact Samsung `MZ-V9P2T0BW`.
- PSU: ATX 3.1, PCIe 5.1, supplied current 12V-2x6; reject explicit old ATX 3.0/12VHPWR stock.
- Case: exact `FD-C-NOR1X-01` North XL Mesh.
- Fan: standard square-frame NF-A14x25 G2 PWM single.
- UPS: exact PR1500ELCD, 1500 VA / 1350 W, new/sealed.
- Windows: exact **Windows 11 Pro Retail/FPP `HAV-00163`** from a normal retailer invoice; no OEM/DSP or undocumented key.

## Ordering strategy

1. Build and verify the EvoMAG hardware cart.
2. Place the Altex PSU order in the same purchasing session unless EvoMAG can prove a current-revision VERTEX unit.
3. Order Windows `HAV-00163` from PROstore independently.
4. Do not dismantle the current PC until CPU, motherboard, RAM, cooler and case are physically received and inspected.
5. Keep invoices, serial numbers, product-page evidence and packaging in one long-term warranty folder.
