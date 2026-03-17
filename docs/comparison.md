# NAPIC vs NAPI2 — Board Comparison

| Feature           | NAPIC (RK3308)              | NAPI2 (RK3568)                        |
|-------------------|-----------------------------|---------------------------------------|
| SoC               | RK3308, 4× Cortex-A35       | RK3568, 4× Cortex-A55                 |
| CPU speed         | 1.3 GHz                     | 2.0 GHz                               |
| RAM               | 256–512 MB DDR3             | 2–8 GB LPDDR4                         |
| Storage           | eMMC + microSD              | eMMC + microSD                        |
| Ethernet          | 1× 100 Mbit                 | 2× Gigabit                            |
| RS485             | —                           | 1× (isolated)                         |
| CAN               | —                           | 1× CAN 2.0B                          |
| PCIe              | —                           | 1× PCIe 3.0 (1-lane)                 |
| USB               | 1× USB2 Host + OTG          | 2× USB3 + 1× USB2 OTG                |
| Display           | —                           | HDMI 2.0 + LVDS                       |
| Audio             | I2S, PDM mic array          | I2S                                   |
| GPIO header       | 26-pin                      | 40-pin                                |
| Typical use       | Voice UI, audio, light I/O  | Industrial automation, edge computing |
| Kernel            | Armbian mainline / vendor   | Armbian mainline (6.12) / vendor (6.1)|

## Choosing the Right Board

**Choose NAPIC if:**
- You need compact form factor and low power
- Audio processing or microphone array is required
- Light I/O is sufficient (UART, I2C, SPI, GPIO)

**Choose NAPI2 if:**
- You need dual Gigabit Ethernet (e.g. router, gateway, industrial switch)
- RS485 or CAN bus connectivity is required
- Display output (HDMI or LVDS panel) is needed
- Higher compute performance is required
- PCIe expansion is needed (4G modem, NVMe SSD, etc.)
