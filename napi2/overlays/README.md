# NAPI2 Device Tree Overlays

Overlays allow enabling optional hardware interfaces without recompiling the kernel.
They are applied at boot time by U-Boot and the Armbian overlay system.

## Available Overlays

| File                    | Interface       | Description                              |
|-------------------------|-----------------|------------------------------------------|
| `rs485-uart3.dts`       | RS485           | UART3 as RS485, half-duplex, auto-RTS    |
| `can0.dts`              | CAN 2.0B        | CAN0 via MCP2515 or built-in            |
| `lvds-1280x800.dts`     | LVDS display    | 1280×800 @ 71 MHz, VESA-24bit           |
| `i2c3-m0.dts`           | I2C             | I2C3 on M0 pins (header pins 3, 5)      |
| `spi1-m1.dts`           | SPI             | SPI1 on M1 pins (header pins 19–26)     |
| `pwm4.dts`              | PWM             | PWM4 on header pin 7                    |
| `uart8.dts`             | UART            | UART8 on header pins 32, 36             |

## Enabling Overlays

Edit `/boot/armbianEnv.txt`:

```
overlays=rk3568-napi2-rs485-uart3 rk3568-napi2-can0
```

Multiple overlays are separated by spaces. Reboot after changes.

## Compiling Overlays Manually

```bash
# Compile single overlay
dtc -@ -I dts -O dtb -o rs485-uart3.dtbo rs485-uart3.dts

# Copy to overlays directory
sudo cp rs485-uart3.dtbo /boot/dtb/rockchip/overlay/
```

## Via Armbian Build System

Place `.dts` files in:
```
userpatches/overlay/overlays-rk3568-current/
```

They will be compiled and installed automatically during the build.

## Notes

- All overlays target the **mainline kernel (6.12)** branch unless noted
- For vendor kernel (6.1 / rk35xx branch) overlays, check the `vendor/` subdirectory
- Overlay syntax uses `target-path` for compatibility with older U-Boot versions
