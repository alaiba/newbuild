# Initial BOM Purchase Review — 2026-08-31

This is the current dated procurement/value snapshot. Exact order execution and acceptance gates are in `docs/procurement-plan-2026-08-31.md`.

## Optimized complete-order position

The final provider/value pass optimizes both **price and useful lifetime**, with a default of **two providers**.

Representative total with the purchase-ready **Seasonic VERTEX GX-1200**:

- **~19,949 lei before shipping**.

If the **VERTEX PX-1200** is in stock at the current ~160 lei premium:

- **~20,109 lei before shipping**.

The higher total versus the previous snapshot is mainly the deliberate UPS upgrade from a 1000 W current-system unit to a 1350 W model that is expected to remain suitable through the future high-power GPU upgrade.

## Current controls

| Component | Selected target | Working control |
|---|---|---:|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** EvoMAG |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~**2,685 lei** EvoMAG-class current control |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | ~**4,799.99 lei** fresh EvoMAG/comparison control |
| Cooler | Noctua NH-D15 G2 standard | ~**690.99 lei** |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | **1,899.99 lei** |
| PSU baseline | VERTEX GX-1200 current ATX 3.1 | **1,289.99 lei** Altex |
| PSU conditional upgrade | VERTEX PX-1200 current ATX 3.1 | **1,449.99 lei** reference, currently explicit listing out of stock |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | **882.99 lei** EvoMAG |
| Rear fan | Noctua NF-A14x25 G2 PWM | **200.99 lei** EvoMAG |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **2,948.99 lei** EvoMAG/current market |
| GPU | existing RTX 3060 12 GB | 0 lei |
| Windows | **Windows 11 Pro Retail/FPP `HAV-00197` Romanian USB** | **1,199.99 lei** EvoMAG |

## Key value changes

### UPS — upgraded

`CP1600EPFCLCD` was replaced by **PR1500ELCD**.

Reason: the future design case around 900–980 W would put the former 1000 W UPS near full load. The 1350 W PR1500 keeps that load around 67–73%, adds better runtime/AVR and hot-swappable battery serviceability, and may avoid buying another UPS later.

### PSU — conditional premium

GX-1200 remains the purchase-ready baseline. **PX-1200 is preferred when available at ≤~200 lei premium**, because the Platinum-efficiency premium is small enough to be sensible over a long ownership period. Do not delay the build while PX is out of stock.

### Windows — consolidated

Use **Retail/FPP `HAV-00197` from EvoMAG** rather than creating provider #3 for the slightly cheaper English package. Windows 11 Pro can install/switch to English display language.

### RAM — keep Crucial

The exact Crucial 64 GB kit remains the value leader at the current ~4.8k control. Kingston's explicit ProArt compatibility is attractive but not worth the present ~500–600+ lei premium; reconsider if the gap shrinks to roughly 200–250 lei.

## Provider plan

### EvoMAG

CPU, motherboard, RAM, cooler, SSD, case, rear fan, PR1500ELCD and Windows Retail/FPP.

### Altex

Current-revision Seasonic VERTEX PSU.

A third provider requires approximately **≥300 lei net saving** or materially better stock/SKU/revision/warranty certainty.

## Deferred cost

Still excluded:

- future 4 TB+ work/VM/container SSD;
- eventual 256 GB matched RAM configuration;
- future high-VRAM GPU.

Those remain separate future purchases.
