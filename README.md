# JIJIEFPVH743 ArduPilot custom target

This repository is a private/custom ArduPilot target for the JIJIEFPV H743 flight controller.

## Important board-ID decision

The board uses `AP_HW_DAKEFPVH743` / board ID 1193 instead of inventing a new board ID.
Current ArduPilot reserves the 1000-19999 range for official bootloader IDs, and 1193 is already assigned to DAKEFPVH743.

The build target is still named `JIJIEFPVH743`.

## Hardware map

- STM32H743xx, 480 MHz, 8 MHz HSE
- 2 x LSM6DSK320X: SPI1/PA4 and SPI4/PB1
- DPS310: I2C2 PB10/PB11, address 0x76
- 16 MB SPI flash: SPI3, CS PA15
- OSD: SPI2, CS PB12
- ELRS/CRSF: UART2 PD5/PD6
- GPS: UART1 PA9/PA10
- ESC telemetry: UART3 PD8/PD9
- 8 motor outputs: PA0-PA3, PD12-PD15
- LED strip: PE9
- Buzzer: PC2
- Battery voltage: PC1
- Battery current: PC0
- RSSI ADC: PC5
- Status LEDs: PD10, PD11, PA8

## Safety

Build and verify the firmware on the bench with propellers removed before flight. Verify IMU orientation, RC input, failsafe, battery scaling, barometer, motor order, motor direction, and arming checks.
