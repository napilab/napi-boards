# NAPI Boards — Industrial SBCs on Rockchip

This repository contains device trees, overlays, GPIO pinouts, Armbian build configs,
and usage examples for the **NAPI** and **NAPI2** industrial single-board computers.


## Documentation

- [NAPI2 Overview](./napi2/README.md)
- [NAPI-C\NAPI-P Overview](./napic/README.md)
- [NAPI-Slot Overview](./napi-slot/README.md)
- [Board Comparison](./docs/comparison.md)

## Boards

| Board  | SoC     | RAM   | Key Interfaces                        |
|--------|---------|-------|---------------------------------------|
| [NAPI2](./napi2/) | RK3568  | 4GB \ 32Gb  | 2× GbE, RS485, CAN, PCIe, HDMI, LVDS |
| [NAPIC\NAPIP ](./napic/) | RK3308  |512 MB \ 4Gb | Audio, UART, I2C, SPI, GPIO           |
| [NAPI-SLot](./napi-slot/) | RK3308  | 512 MB \ 32Gb | Audio, UART, I2C, SPI, GPIO           |


## Repository Structure

```
napi-boards/
├── napi2/          # RK3568-based board
│   ├── dts/        # Base device tree source
│   ├── overlays/   # DT overlays (RS485, CAN, LVDS, ...)
│   ├── gpio/       # Pinout tables and diagrams
│   ├── armbian/    # Armbian userpatches
│   └── examples/   # Application examples
├── napic/          # RK3308-based board
│   └── ...         # Same structure
└── docs/           # General documentation
```

## Topics

`rockchip` `rk3568` `rk3308` `armbian` `embedded-linux` `device-tree`
`industrial` `sbc` `single-board-computer` `rs485` `can-bus` `linux`
