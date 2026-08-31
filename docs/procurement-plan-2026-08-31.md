# Procurement Plan — 2026-08-31

> Finalized 2026-09-01 after all required hardware purchases were completed.

Status: **complete**. Architecture remains closed.

## Executed orders

### EvoMAG — 2026-09-01

| Item | Paid price incl. VAT |
|---|---:|
| Ryzen 9 9950X3D Box/WOF | **3,349.99 lei** |
| ASUS TUF GAMING B650E-E WIFI | **785.99 lei** |
| Crucial T710 2 TB | **1,699.99 lei** |
| be quiet! Pure Power 13 M 850W | **683.99 lei** |
| Hardware subtotal | **6,519.96 lei** |
| Courier | **11.99 lei** |
| **Total** | **6,531.95 lei** |

### Vexio — 2026-09-01

| Item | Paid price incl. VAT |
|---|---:|
| be quiet! Pure Base 501 Airflow Black `BG074` | **415.99 lei** |
| Thermalright Phantom Spirit 120 standard | **246.99 lei** |
| Shipping | **0.00 lei** |
| **Total** | **662.98 lei** |

### CEL.ro — 2026-09-01

| Item | Paid price incl. VAT |
|---|---:|
| Crucial Pro `CP2K24G56C46U5`, 48 GB = 2x24 GB | **2,899.00 lei** |
| **Total reported** | **2,899.00 lei** |

No separate CEL.ro shipping charge was shown in the supplied checkout total.

## Final cost position

| Provider | Total |
|---|---:|
| EvoMAG | **6,531.95 lei** |
| Vexio | **662.98 lei** |
| CEL.ro | **2,899.00 lei** |
| **Committed hardware total** | **10,093.93 lei** |

Windows 11 Pro is already available and is excluded from procurement cost. RTX 3060 and suitable SATA storage are reused.

## Final purchase state

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | Purchased — EvoMAG |
| Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | Purchased — EvoMAG; physical SKU verification pending |
| RAM | Crucial Pro `CP2K24G56C46U5`, 48 GB = 2x24 GB | **Purchased — CEL.ro** |
| CPU cooler | Thermalright Phantom Spirit 120 standard | Purchased — Vexio |
| Case | be quiet! Pure Base 501 Airflow Black `BG074` | Purchased — Vexio |
| Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | Purchased — EvoMAG |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` | Purchased — EvoMAG |
| GPU | existing RTX 3060 12 GB | Reuse |
| Host OS | Windows 11 Pro x64 | License already available |
| UPS | none | No purchase planned |
| Dedicated surge protector | none | No purchase planned |

## Arrival acceptance gates

- CPU: confirm `100-100000719WOF` / Box-WOF.
- Motherboard: confirm `90MB1LT0-M0EAY0`; reject B650-E `90MB1GT0-M0EAY0` and other near-name variants.
- RAM: confirm `CP2K24G56C46U5`, 48 GB total as 2x24 GB, DDR5-5600 desktop non-ECC UDIMM.
- Cooler: confirm standard Phantom Spirit 120, not SE/EVO; both fans and AM5 mounting hardware present.
- Case: confirm `BG074`, non-window Airflow Black, both included 140 mm PWM fans.
- SSD: confirm `CT2000T710SSD8`, bare/non-heatsink.
- PSU: confirm `BP027EU`, complete original modular cable set.

## Next sequence

1. Receive and verify all boxes before installation.
2. Preserve invoices, labels/serials and packaging.
3. Assemble only after identities and condition pass.
4. Update BIOS and establish a conservative firmware baseline.
5. Install RAM in A2/B2 and start at Auto/JEDEC.
6. Perform extended stability/thermal/storage validation.
7. Install Windows 11 Pro + WSL2/Ubuntu after hardware baseline is stable.

## Decision status

**Procurement is complete. There are no remaining purchase items.** Reopen sourcing only for cancellation, incorrect delivery, damage, or a material compatibility defect.
