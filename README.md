# NAPI Boards — Industrial SBCs on Rockchip

This repository contains device trees, overlays, GPIO pinouts, Armbian build configs,
and usage examples for the **NAPI** and **NAPI2** industrial single-board computers.

## Boards

| Board  | SoC     | RAM   | Key Interfaces                        |
|--------|---------|-------|---------------------------------------|
| [NAPI2](./napi2/) | RK3568  | up to 8 GB | 2× GbE, RS485, CAN, PCIe, HDMI, LVDS |
| [NAPIC](./napic/) | RK3308  | up to 512 MB | Audio, UART, I2C, SPI, GPIO           |

## Quick Start

```bash
# Clone the repo
git clone https://github.com/your-org/napi-boards.git
cd napi-boards

# Copy Armbian userpatches for your board (example: napi2)
cp -r napi2/armbian/userpatches ~/arb/userpatches

# Build image
cd ~/arb
./compile.sh BOARD=napi2 BRANCH=current BUILD_MINIMAL=no BUILD_DESKTOP=no
```

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

## Documentation

- [NAPI2 Overview](./napi2/README.md)
- [NAPIC Overview](./napic/README.md)
- [Board Comparison](./docs/comparison.md)
- [Building with Armbian](./docs/armbian-build.md)

## Topics

`rockchip` `rk3568` `rk3308` `armbian` `embedded-linux` `device-tree`
`industrial` `sbc` `single-board-computer` `rs485` `can-bus` `linux`
