# Initial BOM Purchase Review — 2026-08-31

This is a **price snapshot**, not a permanent price promise. Refresh all prices immediately before ordering.

## Procurement policy

- **PC Garage and Altex are co-preferred Romanian retailers**.
- **eMAG is also acceptable**.
- Exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order.
- Small price differences do not matter.
- Material differences can justify another reputable Romanian/EU seller, especially for temporary Phase-1 RAM.

## Current initial-build price envelope

| Component | Selected target | Current price reference |
|---|---|---:|
| CPU | AMD Ryzen 9 9950X3D | ~3.35–3.52k lei |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~2.68–2.90k lei |
| CPU cooler | Noctua NH-D15 G2 standard | ~0.69–0.73k lei |
| System SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | ~1.90–1.95k lei |
| PSU | Seasonic VERTEX GX-1200 current ATX 3.1 revision | ~1.29k lei at explicit Altex ATX 3.1 listing |
| Case | Fractal Design North XL Mesh | ~0.93–1.06k lei market class |
| Rear fan | Noctua NF-A14x25 G2 PWM | ~0.19–0.21k lei |
| UPS | CyberPower CP1600EPFCLCD | ~1.53–1.59k lei |
| Existing GPU | RTX 3060 12 GB | 0 lei new spend |

Non-RAM selected hardware subtotal: approximately **12.6–13.3k lei**.

## RAM comparison at final review

### 32 GB minimum-cost baseline

- GOODRAM `GR5600D564L46/32G`
- 1×32 GB DDR5-5600 CL46 1.1 V
- current PC Garage reference: ~**2.20k lei**
- whole initial build: ~**14.8–15.5k lei**

### 64 GB selected Phase-1 target

- Crucial `CT2K32G56C46U5`
- 2×32 GB DDR5-5600 CL46 1.1 V
- current low Romanian market: ~**4.7–4.8k lei**
- whole initial build: ~**17.3–18.1k lei**

### 64 GB compatibility fallback

- Kingston `KF556C36BBEK2-64`
- 2×32 GB DDR5-5600 CL36 EXPO
- Kingston explicitly lists it for the ASUS ProArt X870E-Creator WiFi
- current PC Garage reference: ~**5.5k lei**
- whole initial build: ~**17.9–18.8k lei**

## Decision

**Start with 64 GB.**

The extra ~2.5–3k lei versus the 32 GB minimum buys:

- double capacity;
- dual-channel memory bandwidth;
- materially better concurrency headroom for IntelliJ, Android Studio, emulators, Gradle/Maven builds, Docker/WSL2, local services and VMs.

Even with 64 GB, the initial build remains roughly **11k+ lei below the ~30k planning level**, before the deferred future work SSD and future GPU.

No permanent component needs to be downgraded to fund the memory upgrade.

## Current source controls

Price-control/reference pages used in this review:

- Ryzen 9 9950X3D: https://www.price.ro/preturi-amd-ryzen-9-9950x3d-box-4718281
- ASUS ProArt X870E-Creator WiFi: https://www.price.ro/preturi-asus-proart-x870e-creator-wifi-4691168
- Noctua NH-D15 G2: https://www.price.ro/preturi-noctua-nh-d15-g2-4652246
- Samsung 990 PRO 2 TB: https://www.price.ro/preturi-samsung-ssd-990-pro-2tb-pci-express-4.0-x4-m.2-2280-mz-v9p2t0bw-3974614
- North XL price control: https://www.price.ro/preturi-fractal-design-north-xl-charcoal-black-4533131
- Noctua NF-A14x25 G2 PWM: https://www.price.ro/preturi-noctua-nf-a14x25-g2-pwm-140mm-4713497
- CyberPower CP1600EPFCLCD: https://www.compari.ro/ups-uri-surse-neintreruptibile-c3133/cyberpower/cp1600epfclcd-1600va-p1051248901/
- GOODRAM 32 GB baseline: https://www.price.ro/preturi~goodram-32gb-ddr5-5600mhz-cl46-4737947.html
- Crucial 64 GB target: https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/
- Kingston 64 GB fallback: https://www.price.ro/preturi-kingston-memorie-fury-beast-64gb-2x32gb-ddr5-5600mhz-cl36-kf556c36bbek2-64-4046486
- Kingston ProArt compatibility: https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard
- Crucial ProArt compatibility selector: https://www.crucial.com/compatible-upgrade-for/asus/proart-x870e-creator-wifi

## Deferred cost

The following are intentionally excluded from the initial total:

- future 4 TB-or-larger work/VM/container SSD;
- future replacement high-VRAM GPU;
- eventual 256 GB memory configuration;
- any future UPS enlargement associated with a high-power GPU.

Those are separate future purchase events and should be priced against then-current requirements and market conditions.
