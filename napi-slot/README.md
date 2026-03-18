# NAPI-Slot — Compact SOM on RK3308

NAPIC is a compact single-board computer based on the **Rockchip RK3308** SoC,
optimized for audio processing, voice interfaces, and lightweight industrial I/O.

## Napi-Slot

![](img/napislot-2.jpeg)

## Napi-Slot GPIO

![](img/napislot-gpio.jpeg)

## Hardware Specifications

| Parameter        | Value                                  |
|------------------|----------------------------------------|
| SoC              | Rockchip RK3308 (4× Cortex-A35, 1.3 GHz) |
| RAM              | 512 MB DDR3                      |
| Storage          | 4Гб SDNAND \ eMMC 8/16/32 GB + microSD                |
| Ethernet         | 1× 100 Mbit                           |
| USB              | 1× USB 2.0 Host, 1× USB 2.0 OTG       |
| Audio            | I2S, PDM microphone array              |
| UART             | 4× UART                               |
| I2C              | 3× I2C                                |
| SPI              | 2× SPI                                |
| GPIO             | 26-pin header                          |
| OS               | Armbian (mainline), NapiLinux, OpenWRT            |



## Contents

```
napic/
├── dts/            # Base DTS (rk3308-napic.dts)
├── overlays/       # DT overlays for optional interfaces
├── gpio/           # 26-pin header pinout
├── armbian/        # Armbian userpatches
└── examples/       # Code and config examples
```

## Getting Started

1. Flash Armbian image
2. Boot the board
3. Enable overlays in `/boot/armbianEnv.txt`:

```bash
overlays=rk3308-napic-i2c1 rk3308-napic-spi0
```

4. Reboot

## Links

- [GPIO Pinout](./gpio/README.md)
- [Overlays](./overlays/README.md)
- [Board Comparison](../docs/comparison.md)
