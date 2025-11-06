# zmk-config for Corne (nRF52840 / nice!nano)

This package mirrors a QMK Corne layout and ports it to ZMK for wireless BLE:
- Boards: nice_nano_v2 (left/right)
- Split over BLE, auto role
- RGB underglow on WS2812, **P0.10** (D6), 54 LEDs
- Optional SSD1306 status screen
- VS Code macros and Tap-Dance behaviors
- Hold-Tap tuned for 160 ms to match your QMK TAPPING_TERM

## Build locally
```bash
west build -b nice_nano_v2 -d build-left -- -DSHIELD=corne_left
west build -b nice_nano_v2 -d build-right -- -DSHIELD=corne_right
```

Double-tap reset on each half to flash the resulting UF2.

If you later switch to nice!view or need to move RGB to P0.08, edit:
```
config/corne.conf -> CONFIG_WS2812_STRIP_GPIO_PIN=8
```

