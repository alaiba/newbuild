# Workstation commissioning status

Last updated: 2026-11-06. This is the **current operational and validation summary**. For authoritative component choices and procurement history, see [final-build.md](final-build.md); for dated observations and detailed test records, see [bring-up-2026-10-31.md](bring-up-2026-10-31.md).

## Current state

**Assembled, Windows 11 Pro installed and running.** Nearly one week of regular development use has been smooth and exceptionally quiet. The ASUS RTX 3060 12 GB was installed after a successful integrated-GPU first boot and is recognized by Windows and has passed driver and sustained-load checks. Initial CPU cooling, DDR5 memory and NVMe performance checks were favorable. Not every peripheral or extended load case has been validated.

## Installed configuration

| Component | Actual build |
|---|---|
| CPU | AMD Ryzen 9 9950X3D (16 cores / 32 threads) |
| Motherboard | ASUS TUF GAMING B650E-E WIFI, UEFI BIOS 3287 |
| RAM | Crucial Pro 48 GB (2 × 24 GB) DDR5-5600, dual-channel, CL46-45-45-90; A2/B2; EXPO previously observed off |
| Cooling | Thermalright Phantom Spirit 120, middle + rear fans; supplied TF7 paste |
| Case | be quiet! Pure Base 501 Airflow Black; one 140 mm intake and one 140 mm exhaust |
| SSD | Crucial T710 2 TB NVMe, PCIe 5.0 ×4, M.2_1 |
| GPU | ASUS RTX 3060 12 GB (reused), NVIDIA driver 621.01, VBIOS 94.06.25.00.b6 |
| PSU | be quiet! Pure Power 13 M 850 W |
| OS | Windows 11 Pro x64, operational |
| Linux | WSL2 + Ubuntu planned; not yet verified |

## Completed validation

| Area | Observation | Qualification |
|---|---|---|
| First boot | Successful POST on integrated graphics, then Windows 11 Pro installation | Completed |
| CPU cooling | Short HWiNFO SSE stress: 100% CPU utilization, ~4.8 GHz average effective clock, 80.5 °C peak, ~200 W package power, no observed WHEA errors | Short test; not a long-duration stability guarantee |
| RAM | MemTest86 v11.7 Free: 4 passes; 48/48 tests completed and passed; 0 errors in 3:05:13 at DDR5-5600 | Strong initial memory-integrity result |
| RAM thermals | MemTest86 RAM min/avg/max 33/42/46 °C; CPU 46/62/82 °C | Values reported by MemTest86 |
| SSD interface | PCIe 5.0 ×4 at 32.0 GT/s per lane | Link verified by HWiNFO |
| SSD sequential throughput | CrystalDiskMark 9, 3 runs, 1 GiB: 14,022.52 MB/s read; 12,936.93 MB/s write | Short-burst benchmark |
| SSD other throughput | Sequential Q1T1: 8,534.44 / 10,246.35 MB/s; random 4K Q32T1: 809.37 / 636.58 MB/s; random 4K Q1T1: 85.12 / 300.43 MB/s (read/write) | CrystalDiskMark |
| SSD health/thermals | SMART remaining life 100%; no drive warnings/failures; highest observed temperature 72 °C | No explicit thermal-throttling flag recorded |
| GPU driver | NVIDIA driver 621.01 (Windows driver 32.0.16.2101, 2026-10-19); VBIOS 94.06.25.00.b6; 12288 MiB recognized; idle 38 °C, 13 W, fan 0% (zero-RPM), PCIe Gen 1 x16 (power saving) | Verified with nvidia-smi |
| GPU sustained load | FurMark 2.10.2 (GL), about 2 min stress and 1080p preset benchmark (60 s) with 1 s nvidia-smi logging: 100% utilization, peak 71.5 °C, ~168 W average (170 W limit), 1477-1672 MHz, fan up to 75%, PCIe Gen 4 under load; only throttle reason was the software power cap; recovered to 42 °C with fan 0% | No thermal throttling; short test, not a long soak |
| GPU benchmark | FurMark GL P1080: 6341 points, 105 FPS ([score 3365574](https://www.gpumagick.com/scores/3365574)) | In line with typical RTX 3060 submissions (about 6,200-6,450) |
| Real-world operation | Nearly one week of smooth development workloads; very quiet operation reported | User observation |

## Installation note

Windows 11 offline installation initially lacked usable Wi-Fi and Bluetooth; wired Ethernet was needed to obtain drivers and Windows updates. Successful post-install Wi-Fi and Bluetooth operation has not yet been explicitly recorded.

## Open checks

- Wi-Fi/Bluetooth operation after drivers; USB, audio, display outputs (NVIDIA and iGPU), sleep/resume.
- Fan RPM and curves under sustained load, including independent visual confirmation of both CPU cooler fans.
- SSD firmware version; long-duration system stability only if symptoms or workload warrant it.
- WSL2/Ubuntu deployment and validation.
- BitLocker planning and securely retained recovery key once firmware/driver/storage setup is settled.

## References

- [Final build and procurement](final-build.md)
- [Assembly, bring-up and detailed test observations](bring-up-2026-10-31.md)
- [Purchase ledger](purchases-2026-09-01.md)
- [Agent handoff](../WORK.md)
