# Initial BOM Purchase Review — 2026-08-31

This is a **price snapshot**, not a permanent price promise. Refresh all prices immediately before ordering.

## Procurement policy

- **PC Garage and Altex are co-preferred Romanian retailers**.
- **eMAG is also acceptable**.
- Exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order.
- Small price differences do not matter.
- Material differences can justify another reputable Romanian/EU seller.

## Current initial-build price envelope

| Component | Selected target | Current price reference |
|---|---|---:|
| CPU | AMD Ryzen 9 9950X3D | ~3.35–3.52k lei |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~2.68–2.90k lei |
| Phase-1 RAM | Crucial `CT2K32G56C46U5`, 64 GB (2×32) | ~4.7–4.8k lei |
| CPU cooler | Noctua NH-D15 G2 standard | ~0.69–0.73k lei |
| System SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | ~1.90–1.95k lei |
| PSU | Seasonic VERTEX GX-1200 current ATX 3.1 revision | ~1.29k lei at explicit Altex ATX 3.1 listing |
| Case | Fractal Design North XL Mesh | ~0.93–1.06k lei market class |
| Rear fan | Noctua NF-A14x25 G2 PWM | ~0.19–0.21k lei |
| UPS | CyberPower CP1600EPFCLCD | ~1.53–1.59k lei |
| Existing GPU | RTX 3060 12 GB | 0 lei new spend |
| Host OS | Windows 11 Pro x64 | **1,199 RON** official Microsoft Store if a new license is required |
| WSL Linux | Ubuntu 26.04.1 LTS | 0 lei |

Selected hardware subtotal with 64 GB: approximately **17.3–18.1k lei**.

If a new Windows 11 Pro license is required, selected hardware + OS is approximately **18.5–19.3k lei**.

If a legitimate transferable Pro license is already available, the Windows row adds no new spend.

## RAM decision

**Start with 64 GB.**

Selected target:

- Crucial `CT2K32G56C46U5`;
- 2×32 GB DDR5-5600 CL46 1.1 V;
- current low Romanian market: ~**4.7–4.8k lei**.

The 32 GB GOODRAM `GR5600D564L46/32G` remains only an emergency/minimum-cost fallback.

The 64 GB choice buys double capacity plus dual-channel bandwidth and leaves the initial build comfortably below the planning level.

Compatibility fallback:

- Kingston `KF556C36BBEK2-64`;
- 2×32 GB DDR5-5600 CL36 EXPO;
- explicitly listed by Kingston for the ProArt;
- use only if Crucial stock/warranty/pricing becomes materially worse.

## Windows decision

Selected:

- **Windows 11 Pro x64**;
- install **Windows 11 25H2 General Availability** for the August 2026 build;
- WSL2 + Ubuntu 26.04.1 LTS for Linux development;
- no Pro for Workstations and no native Linux dual boot initially.

Current official Microsoft Store Romania controls:

- Windows 11 Home: **690 RON**;
- Windows 11 Pro: **1,199 RON**;
- Windows 11 Pro for Workstations: **1,999 RON**.

The Pro premium over Home is justified by the development/virtualization/management use case. The additional Pro-for-Workstations premium is not justified for one CPU socket and a 256 GB memory target.

## Current source controls

- Ryzen 9 9950X3D: https://www.price.ro/preturi-amd-ryzen-9-9950x3d-box-4718281
- ASUS ProArt X870E-Creator WiFi: https://www.price.ro/preturi-asus-proart-x870e-creator-wifi-4691168
- Noctua NH-D15 G2: https://www.price.ro/preturi-noctua-nh-d15-g2-4652246
- Samsung 990 PRO 2 TB: https://www.price.ro/preturi-samsung-ssd-990-pro-2tb-pci-express-4.0-x4-m.2-2280-mz-v9p2t0bw-3974614
- North XL price control: https://www.price.ro/preturi-fractal-design-north-xl-charcoal-black-4533131
- Noctua NF-A14x25 G2 PWM: https://www.price.ro/preturi-noctua-nf-a14x25-g2-pwm-140mm-4713497
- CyberPower CP1600EPFCLCD: https://www.compari.ro/ups-uri-surse-neintreruptibile-c3133/cyberpower/cp1600epfclcd-1600va-p1051248901/
- Crucial 64 GB target: https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/
- Kingston 64 GB fallback: https://www.price.ro/preturi-kingston-memorie-fury-beast-64gb-2x32gb-ddr5-5600mhz-cl36-kf556c36bbek2-64-4046486
- Kingston ProArt compatibility: https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard
- Crucial ProArt compatibility selector: https://www.crucial.com/compatible-upgrade-for/asus/proart-x870e-creator-wifi
- Windows 11 Pro official Romanian store: https://www.microsoft.com/ro-ro/d/windows-11-pro/dg7gmgf0d8h4
- Windows 11 Pro for Workstations official Romanian store: https://www.microsoft.com/ro-ro/d/windows-11-pro-pentru-statii-de-lucru/dg7gmgf0kr4m
- Windows release information: https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information
- Ubuntu on WSL: https://ubuntu.com/download/wsl

## Deferred cost

The following are intentionally excluded from the initial total:

- future 4 TB-or-larger work/VM/container SSD;
- future replacement high-VRAM GPU;
- eventual 256 GB memory configuration;
- any future UPS enlargement associated with a high-power GPU.

Those are separate future purchase events and should be priced against then-current requirements and market conditions.
