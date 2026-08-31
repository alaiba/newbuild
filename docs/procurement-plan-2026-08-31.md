# Procurement Plan — 2026-08-31

Status: **purchase architecture closed**. RAM is finalized at 48 GB / 2×24 GB. Same-day price/provider verification remains before payment.

## Locked principles

1. Maximum three providers overall; prefer fewer when exact SKUs remain available.
2. Optimize utility per leu, not benchmark prestige.
3. Preserve exact product identities where similarly named substitutes differ.
4. Keep AM5 memory at **two DIMMs / 1DPC**.
5. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.

## Preferred provider split

- **EvoMAG:** hardware, provided exact SKUs are confirmed in-cart, especially motherboard `90MB1LT0-M0EAY0`.
- **PROstore:** Windows 11 Pro Retail/FPP `HAV-00163`.
- RAM may come from another Romanian retailer if `CP2K24G56C46U5` is materially cheaper; current market floor is around 2,899 lei.

## Selected purchase targets

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | selected |
| RAM | **Crucial Pro `CP2K24G56C46U5`, 48 GB = 2×24 GB, DDR5-5600, 1.1 V-class, non-ECC** | **selected / final** |
| CPU cooler | Thermalright Phantom Spirit 120 standard | selected |
| Case | be quiet! Pure Base 501 Airflow Black `BG074` | selected |
| Case fans | two included 140 mm PWM only initially | selected |
| Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | selected |
| PSU | be quiet! Pure Power 13 M 850W `BP027EU` | selected |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Dedicated surge protector | none | selected |

## RAM acceptance gate

- exact matched kit: **Crucial Pro `CP2K24G56C46U5`**;
- 48 GB = **2×24 GB**;
- non-ECC UDIMM;
- DDR5-5600;
- conservative 1.1 V-class operation;
- install in A2/B2;
- do not add a second pair later.

Current Romanian reference pricing is approximately **2,899 lei**, with surfaced offers including dataSPOT and CEL. Refresh immediately before checkout.

### Future capacity rule

If 48 GB later proves insufficient under measured real workloads, replace the pair with a larger matched two-DIMM kit. Do not move to four DIMMs simply to preserve the initial kit; Ryzen 9 9950X3D officially supports a lower memory rate with four populated DIMMs.

## Motherboard acceptance gate

- exact **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- do not confuse with **B650-E `90MB1GT0-M0EAY0`**;
- normal new retail condition and warranty;
- current stable BIOS during commissioning.

## Storage acceptance gate

- exact Crucial T710 2 TB `CT2000T710SSD8`;
- bare/non-heatsink variant;
- install in CPU-direct `M.2_1` under the ASUS heatsink;
- no second NVMe, SSD cache/tiering or RAID initially.

## PSU acceptance gate

- exact be quiet! Pure Power 13 M 850W `BP027EU`;
- ATX 3.1;
- normal new retail unit and manufacturer-warranty path;
- use only the modular cables supplied with this PSU.

## Mains-protection policy

- no UPS;
- no dedicated surge protector;
- properly earthed wall outlet;
- ordinary reputable 16 A Schuko strip only if additional sockets are needed.

## Current price position

Using the previous fixed non-RAM basket of approximately **8,389.54 lei**, replacing the 128 GB baseline with the selected ~2,899 lei 48 GB kit yields an indicative complete-build total around **11,288.54 lei before shipping**.

This is not a checkout quote; refresh all items before payment.

## Checkout sequence

1. Refresh **`CP2K24G56C46U5`** price and stock.
2. Verify exact motherboard `90MB1LT0-M0EAY0`; reject the similarly named B650-E.
3. Refresh CPU, cooler, case, SSD and PSU basket pricing.
4. Verify Windows Retail/FPP `HAV-00163`.
5. Recalculate delivered totals and consolidate suppliers where savings are meaningful.
6. Preserve invoices, serials and packaging through commissioning/return windows.

## Decision status

No component-selection question remains open. Procurement is awaiting only live checkout verification.
