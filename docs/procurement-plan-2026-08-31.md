# Procurement Plan — 2026-08-31

Status: **purchase-ready**. CPU/platform, motherboard, RAM, cooling, chassis, storage and PSU are closed. No UPS or dedicated surge protector is required. Live Romanian price/provider consolidation is complete; only same-day checkout verification remains.

## Locked principles

1. Maximum three providers overall; target two hardware providers.
2. Optimize utility per leu, not benchmark prestige.
3. Do not pay for unused networking, PCIe, storage capacity, wattage, cooling capacity or extreme-overclocking capability.
4. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.
5. Software may use a separate provider when provenance/price justify it.

## Final provider split

- **EvoMAG — hardware provider 1:** CPU, RAM, cooler, case, SSD, PSU.
- **ForIT — hardware provider 2:** motherboard.
- **PROstore — software provider:** Windows 11 Pro Retail/FPP.

This meets the provider constraint exactly: **3 providers overall / 2 hardware providers**.

## Live-priced order table

Reference prices observed on 2026-08-31. Shipping excluded and all prices must be confirmed in-cart before payment.

| Provider | Item | Exact target | Reference price |
|---|---|---|---:|
| EvoMAG | CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** |
| ForIT | Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | **874.17 lei** |
| EvoMAG | RAM | Crucial `CT2K64G56C46U5`, 128 GB 2×64, DDR5-5600 CL46, 1.1 V, non-ECC | **7,699.99 lei** |
| EvoMAG | CPU cooler | Thermalright Phantom Spirit 120 standard | **249.99 lei** |
| EvoMAG | Case | be quiet! Pure Base 501 Airflow Black `BG074` | **423.99 lei** |
| EvoMAG | Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | **1,710.99 lei** |
| EvoMAG | PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **686.99 lei** |
| PROstore | Windows | Windows 11 Pro 64-bit English Retail/FPP USB `HAV-00163` | **1,123.60 lei** |
| Reuse | GPU | existing RTX 3060 12 GB | **0 lei** |
| Reuse | Cold storage | existing healthy SATA drives | **0 lei** |
| None | UPS / dedicated surge protector | not purchased | **0 lei** |

### Current totals

- EvoMAG basket: **14,121.94 lei**
- ForIT motherboard: **874.17 lei**
- Hardware subtotal: **14,996.11 lei**
- PROstore Windows: **1,123.60 lei**
- **Final selected-build reference total before shipping: 16,119.71 lei**

The ~30,000 lei planning level remains neither a cap nor a target; the current selected build is approximately **13,880 lei below** that planning figure.

## RAM price warning — primary checkout gate

The selected exact kit **Crucial `CT2K64G56C46U5`** is currently the only materially abnormal price in the build.

Current surfaced Romanian position:

- exact kit at EvoMAG: approximately **7,699.99 lei**;
- Romanian comparison data shows essentially no competing in-stock exact-SKU offer;
- the RAM represents roughly **48% of the complete selected-build total**;
- current European listings are also severely distorted, so this is a broader supply/market problem rather than a normal small retailer premium.

The architecture and SKU remain selected, but this is the **first item to refresh before checkout**. A credible exact-SKU offer that saves hundreds or thousands of lei is worth an additional provider or a short purchase delay. Do not silently replace it with RDIMM, four DIMMs, a different capacity topology or a high-voltage enthusiast kit.

## Motherboard procurement note

ForIT currently surfaces the exact **TUF GAMING B650E-E WIFI** at approximately **874.17 lei** as supplier stock.

ASUS's current Romanian Back-to-School Q3 2026 promotion lists this exact part (`90MB1LT0-M0EAY0`) for **90 lei cashback**, but the official eligible Romanian partner list is currently PC Garage, ITGalaxy and EvoMAG. ForIT is not listed.

The cashback does not currently justify switching: the directly surfaced PC Garage price is still around 1.09k lei before cashback, leaving it above the ForIT reference even after the 90 lei refund.

Also reject misleading sub-850-leu comparison-engine results unless the exact Romanian retailer and currency are verified. Some surfaced comparison data for this board traces to Polish Morele listings quoted in PLN and does not provide a trustworthy Romanian checkout price.

## Windows procurement note

Keep **PROstore `HAV-00163`** at approximately **1,123.60 lei**. EvoMAG currently lists the same broad SKU class around 1,200 lei, so the third software provider still saves about 76 lei while remaining within the project's maximum-three-provider rule.

Do not substitute suspicious ~225–350 lei listings described using `HAV-00163` without a separate provenance/licensing review.

## Exact acceptance gates

### CPU
- **AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`**;
- no tray substitution unless explicitly re-reviewed.

### Motherboard
- **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- do not confuse with B650-E or B650E-PLUS;
- normal new retail unit and warranty path;
- current stable production BIOS during commissioning.

### RAM
- exact **Crucial `CT2K64G56C46U5`** matched 2×64 GB kit;
- non-ECC UDIMM;
- DDR5-5600 CL46-class native JEDEC / 1.1 V;
- no RDIMM or four-DIMM substitution.

### Cooler
- **Thermalright Phantom Spirit 120 standard**;
- no silent SE/EVO substitution;
- AM5 hardware included.

### Case
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- two included 140 mm PWM fans present.

### Storage
- exact **Crucial T710 2 TB `CT2000T710SSD8`**;
- bare/non-heatsink variant;
- install in CPU-direct `M.2_1` under motherboard heatsink;
- no second NVMe, cache/tiering or RAID initially.

### PSU
- exact **be quiet! Pure Power 13 M 850W `BP027EU`**;
- ATX 3.1;
- new retail unit with normal 10-year manufacturer-warranty path;
- use only the modular cables supplied with this exact PSU.

Fallback remains **Corsair RM850x 2024 `CP-9020270-EU`** only if checkout price/warranty is materially better.

### Windows
- exact **Windows 11 Pro Retail/FPP English USB `HAV-00163`**;
- preserve invoice and license packaging.

## Closed motherboard/storage topology

- primary PCIe 5.0 x16: RTX 3060;
- `M.2_1` CPU Gen5 x4: Crucial T710 2 TB;
- `M.2_2` CPU Gen4 x4: empty / future expansion;
- `M.2_3` chipset Gen4 x4: empty / future expansion;
- second physical x16 slot: chipset Gen4 x1 only, no planned use;
- SATA: reuse existing healthy drives for cold storage.

## Mains-protection policy

- no UPS;
- no dedicated surge protector;
- properly earthed wall outlet;
- ordinary reputable 16 A Schuko power strip only if more sockets are needed;
- revisit only if actual power-quality problems appear.

## Explicitly removed from the order

- new GPU;
- CyberPower PR1500ELCD;
- dedicated plug-in surge protector;
- 1000–1200 W PSU targets;
- 750 W PSU as purchase target at current pricing;
- Noctua NH-D15 G2;
- Fractal North XL Mesh;
- extra premium rear fan;
- Creator/X870E and B850 platform premiums;
- 256 GB / four-DIMM RAM;
- ECC as RAM purchase requirement;
- separate system/work SSDs;
- dedicated SSD cache/tiering;
- 4 TB primary SSD;
- 5/10 GbE, x8/x8 and secondary x4 requirements.

## Checkout sequence

1. **Refresh the exact RAM kit first.** If price remains ~7.7k lei, consciously accept the current market premium rather than assuming it is normal.
2. Verify all EvoMAG exact SKUs and stock/lead times in one basket.
3. Verify the ForIT motherboard is exact `90MB1LT0-M0EAY0` and obtain final delivered price.
4. Verify PROstore `HAV-00163` Retail/FPP availability and final delivered price.
5. Confirm total shipping and decide only then whether moving a low-value item between EvoMAG/ForIT saves enough to matter.
6. Preserve invoices, serials and packaging through commissioning and return windows.

Detailed priced basket: [`final-order-plan-2026-08-31.md`](final-order-plan-2026-08-31.md).
