# Arrival Verification Checklist

Procurement is complete. Use this checklist when the physical packages arrive and before installation.

## Verification levels

For every purchased component, verify:

1. retailer/order identity;
2. physical box label and product identity;
3. packaging/seals/condition and required accessories.

If any level disagrees, do not install the part until the discrepancy is resolved.

## Purchase state — 2026-09-02

| Provider | Purchased items | Order total |
|---|---|---:|
| EvoMAG | CPU, motherboard, SSD, PSU | **6,531.95 lei** |
| Vexio | case, CPU cooler | **662.98 lei** |
| CEL.ro | RAM — **received and identity-verified 2026-09-02** | **2,899.00 lei** |
| **Total committed** | all required newly purchased hardware | **10,093.93 lei** |

Windows 11 Pro is already available and is not a purchase item. RTX 3060 and suitable SATA drives are reused.

## Exact arrival gates

| Item | Required identity | Status / reject warning |
|---|---|---|
| CPU | AMD Ryzen 9 9950X3D `100-100000719WOF` | Pending; reject tray/OEM substitution |
| Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | Pending; reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS or other near-name variants |
| RAM | Crucial Pro `CP2K24G56C46U5`, 48 GB = 2x24 GB | **PASSED 2026-09-02** — package/photo confirms Crucial Pro, 48 GB (2x24 GB), DDR5-5600 CL46 UDIMM; matching kit identity visible on modules |
| Cooler | Thermalright Phantom Spirit 120 standard | Pending; reject SE/EVO substitution |
| Case | be quiet! Pure Base 501 Airflow Black `BG074` | Pending; confirm non-window model and both included 140 mm PWM fans |
| SSD | Crucial T710 2 TB `CT2000T710SSD8` | Pending; must be bare/non-heatsink variant |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` | Pending; reject other revision/wattage; never mix modular cables |

## EvoMAG arrival checks

### CPU
- box must identify `100-100000719WOF` / Ryzen 9 9950X3D Box/WOF;
- inspect seal/packaging for damage or prior use.

### Motherboard
- box must identify `90MB1LT0-M0EAY0`;
- model must be **TUF GAMING B650E-E WIFI**;
- do not open/install a B650-E or B650E-PLUS substitute.

### SSD
- confirm `CT2000T710SSD8`;
- confirm no factory heatsink;
- retain label/serial information for firmware/SMART baseline records.

### PSU
- confirm `BP027EU`, Pure Power 13 M 850W;
- confirm complete original modular cable set;
- use only cables supplied with this exact PSU.

## Vexio arrival checks

### Cooler
Confirm:
- Phantom Spirit 120 **standard**;
- seven heatpipes;
- approximately 157 mm tower height;
- two standard-model 120 mm fans;
- AM5 mounting hardware present;
- no damage/prior-use indicators.

### Case
Confirm:
- exact `BG074` identity;
- Pure Base 501 Airflow Black, non-window;
- both included 140 mm PWM fans present;
- panels, mesh, connectors and accessory box complete/undamaged.

## CEL.ro RAM arrival checks — passed 2026-09-02

Required:

> **Crucial Pro `CP2K24G56C46U5`**

Verified from the supplied package photo:
- 48 GB total;
- **2 modules**;
- **24 GB per module**;
- DDR5-5600;
- CL46;
- desktop UDIMM;
- Crucial Pro series;
- AMD EXPO and Intel XMP 3.0 support markings;
- matching kit identity visible on the module labels.

Physical package appears to be the expected retail kit. Preserve the packaging and serial information through commissioning/return windows.

Install the pair in **A2/B2** and commission at **Auto/JEDEC first**. Do not enable EXPO/XMP during the initial stability baseline unless later justified.

## Physical handling

Before opening/installing components:
- photograph box labels/SKUs/serials where practical;
- compare them to the order ledger;
- inspect packaging for shipping damage/open-box substitution;
- preserve invoices, packaging and serial records through commissioning and return windows.

## After verification

Once every item passes identity and condition checks, proceed to assembly/commissioning using `docs/final-build.md` and the component dossiers.
