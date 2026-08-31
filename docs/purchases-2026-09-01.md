# Purchases — 2026-09-01

This file is an immutable procurement record for the first executed order of the build.

## Retailer

**EvoMAG**

## Ordered items

| Item | Exact intended identity | Price incl. VAT |
|---|---|---:|
| AMD Ryzen 9 9950X3D Box | `100-100000719WOF` | **3,349.99 lei** |
| ASUS TUF GAMING B650E-E WIFI | target manufacturer SKU `90MB1LT0-M0EAY0` | **785.99 lei** |
| Crucial T710 2 TB, PCIe 5.0 x4, M.2 2280 | `CT2000T710SSD8` | **1,699.99 lei** |
| be quiet! Pure Power 13 M 850W | `BP027EU` | **683.99 lei** |
| **Hardware subtotal** |  | **6,519.96 lei** |
| Courier |  | **11.99 lei** |
| **Total paid / ordered** |  | **6,531.95 lei** |

All values include VAT.

## Retailer product links

- CPU: https://www.evomag.ro/componente-pc-gaming-procesoare/amd-procesor-amd-ryzen-9-9950x3d-4.3ghz-144mb-170w-am5-box-4206997.html
- Motherboard: https://www.evomag.ro/componente-pc-gaming-placi-de-baza/asus-placa-de-baza-asus-tuf-gaming-b650e-e-wifi-am5-amd-b650-atx-4254553.html
- SSD: https://www.evomag.ro/componente-pc-gaming-solid-state-drive-ssd/crucial-ssd-crucial-t710-2tb-pcie-5.0-x4-m.2-2280-4256933.html
- PSU: https://www.evomag.ro/componente-pc-gaming-surse-de-alimentare-pc/be-quiet-sursa-be-quiet-pure-power-13-m-80-gold-850w-full-modulara-4237999.html

## Important verification state

The order is **placed**, but purchase identity is not considered fully closed until the delivered physical labels are checked.

Required arrival checks:

- CPU box must identify **`100-100000719WOF`** / Box-WOF, not tray/OEM.
- Motherboard box must identify **`90MB1LT0-M0EAY0`**. The retailer page/order title says **TUF GAMING B650E-E WIFI**, but EvoMAG did not expose a sufficiently trustworthy full manufacturer SKU in its catalogue metadata. Reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS, or another similarly named board.
- SSD must identify **`CT2000T710SSD8`** and be the bare/non-heatsink variant.
- PSU must identify **`BP027EU`**, Pure Power 13 M 850W, with its complete original modular cable set.

Do not install any mismatched item before resolving a return/replacement.

## Build-state effect

After this order:

**Purchased / committed**
- CPU
- motherboard
- primary SSD
- PSU

**Still to purchase**
- Crucial Pro `CP2K24G56C46U5` RAM, 48 GB = 2×24 GB
- Thermalright Phantom Spirit 120 standard cooler
- be quiet! Pure Base 501 Airflow Black `BG074` case
- Windows 11 Pro Retail/FPP English USB `HAV-00163`

The existing RTX 3060 and suitable existing SATA drives are reused and therefore are not purchase items.
