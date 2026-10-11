# ESP32 Bit Pirate — Weekly Firmware Health

Last update: `2026-10-11T14:26:12Z`

Source: [`8022f80`](https://github.com/songbangyan/ESP32-Bit-Pirate/commit/8022f80381bb12bc87c5d4d69bd296db661d6d1c)

Full workflow logs and artifacts: [GitHub Actions run](https://github.com/songbangyan/ESP32-Bit-Pirate/actions/runs/38147154926)

## Overall status

✅ **Current Bit Pirate firmware is healthy.**

- Boards: **18/18** build successfully
- Native tests: **✅ passed**
- Latest pioarduino: **⚠️ build incompatible**
- Direct library updates available: **3**
- Library update build regressions: **1**

## Current reference build

| Item | Value |
|---|---:|
| Environment | `s3-devkit` |
| Arduino framework | `3.3.7` |
| Platform | `Espressif 32 (55.3.37) > Espressif ESP32-S3-DevKitC-1-N8 (8 MB QD, No PSRAM)` |
| Static RAM | 88,448 B |
| Flash | 3,772,104 B |

## Supported environment builds

| Environment | Status | Static RAM | Flash |
|---|---|---:|---:|
| `custom` | ✅ | 88,676 B | 3,796,983 B |
| `cardputer` | ✅ | 91,324 B | 4,028,503 B |
| `cardputer-adv` | ✅ | 91,324 B | 4,028,467 B |
| `m5stack-sticks3` | ✅ | 92,936 B | 4,013,515 B |
| `s3-devkit` | ✅ | 88,448 B | 3,772,104 B |
| `s3-devkit-n16-r8` | ✅ | 88,916 B | 3,777,362 B |
| `m5stack-stamps3` | ✅ | 91,228 B | 3,915,679 B |
| `atom-lite-s3` | ✅ | 91,228 B | 3,918,255 B |
| `t-display-s3` | ✅ | 89,344 B | 3,942,239 B |
| `waveshare-s3-geek` | ✅ | 89,016 B | 3,933,143 B |
| `t-embed-s3` | ✅ | 88,980 B | 3,930,983 B |
| `t-embed-s3-cc1101` | ✅ | 88,980 B | 3,931,451 B |
| `t-embed-s3-cc1101plus` | ✅ | 88,980 B | 3,931,815 B |
| `xiao-esp32s3` | ✅ | 88,368 B | 3,771,256 B |
| `vision-master-t190` | ✅ | 89,272 B | 3,923,627 B |
| `heltec_wifi_lora_32_V4` | ✅ | 88,452 B | 3,774,982 B |
| `heltec_wifi_lora_32_V3` | ✅ | 88,312 B | 3,765,732 B |
| `um_pros3` | ✅ | 88,532 B | 3,775,518 B |

## Pioarduino framework compatibility

| Build | Arduino | Platform | RAM | Flash |
|---|---|---|---:|---:|
| Current pinned | `3.3.7` | `Espressif 32 (55.3.37) > Espressif ESP32-S3-DevKitC-1-N8 (8 MB QD, No PSRAM)` | 88,448 B | 3,772,104 B |
| Latest stable | `3.3.12` | `Espressif 32 (55.3.312) > Espressif ESP32-S3-DevKitC-1-N8 (8 MB QD, No PSRAM)` | n/a | n/a |

⚠️ The currently pinned framework builds, but latest stable pioarduino does not.

<details>
<summary>Latest framework build errors</summary>

```text
/home/runner/work/_temp/pio-health-latest/packages/framework-arduinoespressif32/libraries/USB/src/USBMSCFS.h:26:10: fatal error: FS.h: No such file or directory
*** [.pio/build/s3-devkit/libda6/USB/USBHostMSC.cpp.o] Error 1
```

</details>

## Direct dependency health

Latest versions are tested individually against the currently pinned framework.

| Library | Declared | Resolved | Latest | Test environment | Compatibility | RAM Δ | Flash Δ |
|---|---:|---:|---:|---|---|---:|---:|
| `adafruit/Adafruit Si4713 Library` | `^1.2.3` | `1.2.4` | `1.2.4` | `s3-devkit` | ✅ up to date | — | — |
| `autowp/autowp-mcp2515` | `^1.2.1` | `1.3.1` | `1.3.1` | `s3-devkit` | ✅ up to date | — | — |
| `bblanchon/ArduinoJson` | `^7.3.0` | `7.4.3` | `7.4.3` | `s3-devkit` | ✅ up to date | — | — |
| `crankyoldgit/IRremoteESP8266` | `^2.9.0` | `2.9.0` | `2.9.0` | `s3-devkit` | ✅ up to date | — | — |
| `ewpa/LibSSH-ESP32` | `^5.6.0` | `5.10.0` | `5.10.0` | `s3-devkit` | ✅ up to date | — | — |
| `fastled/FastLED` | `3.10.3` | `3.10.3` | `3.10.7` | `s3-devkit` | ⚠️ update fails to build | — | — |
| `gilman88/XModem` | `^1.0.3` | `1.0.3` | `1.0.3` | `s3-devkit` | ✅ up to date | — | — |
| `hideakitai/ESP32SPISlave` | `^0.6.8` | `0.6.9` | `0.8.0` | `s3-devkit` | ✅ update builds | +0 B | +0 B |
| `m5stack/M5Unified` | `^0.2.7` | `0.2.25` | `0.2.25` | `m5stack-stamps3` | ✅ up to date | — | — |
| `mathertel/RotaryEncoder` | `1.5.3` | `1.5.3` | `1.6.0` | `t-embed-s3` | ✅ update builds | +0 B | +40 B |
| `miq19/eModbus` | `^1.7.4` | `1.7.4` | `1.7.4` | `s3-devkit` | ✅ up to date | — | — |
| `paulstoffregen/OneWire` | `^2.3.8` | `2.3.8` | `2.3.8` | `s3-devkit` | ✅ up to date | — | — |
| `pstolarz/OneWireNg` | `^0.14.0` | `0.14.1` | `0.14.1` | `s3-devkit` | ✅ up to date | — | — |
| `sparkfun/SparkFun External EEPROM Arduino Library` | `^3.2.10` | `3.2.13` | `3.2.13` | `s3-devkit` | ✅ up to date | — | — |
| `throwtheswitch/Unity` | `^2.6.1` | `2.6.1` | `2.6.1` | `native-tests` | ✅ up to date | — | — |

### Dependency compatibility regressions

#### `fastled/FastLED`

`3.10.3` → `3.10.7`

<details>
<summary>Build errors</summary>

```text
src/Services/LedService.cpp:31:11: error: call of overloaded 'memset(CRGB*&, int, unsigned int)' is ambiguous
*** [.pio/build/s3-devkit/src/Services/LedService.cpp.o] Error 1
```

</details>


## Git-based dependencies

| Source | Environment | Pinning |
|---|---|---|
| `https://github.com/lovyan03/LovyanGFX` | `custom` | ⚠️ unpinned HEAD |
| `https://github.com/m5stack/M5Cardputer` | `cardputer` | ⚠️ unpinned HEAD |
| `https://github.com/m5stack/M5Cardputer` | `cardputer-adv` | ⚠️ unpinned HEAD |
| `https://github.com/m5stack/M5Unified.git` | `m5stack-sticks3` | ⚠️ unpinned HEAD |
| `https://github.com/lovyan03/LovyanGFX` | `t-display-s3` | ⚠️ unpinned HEAD |
| `https://github.com/lovyan03/LovyanGFX` | `waveshare-s3-geek` | ⚠️ unpinned HEAD |
| `https://github.com/lovyan03/LovyanGFX` | `t-embed-s3` | ⚠️ unpinned HEAD |
| `https://github.com/lovyan03/LovyanGFX` | `t-embed-s3-cc1101` | ⚠️ unpinned HEAD |
| `https://github.com/lovyan03/LovyanGFX` | `vision-master-t190` | ⚠️ unpinned HEAD |

## PlatformIO package update report

<details>
<summary>Current / Wanted / Latest</summary>

```text
Checking

Semantic Versioning color legend:
<Major Update>  backward-incompatible updates
<Minor Update>  backward-compatible features
<Patch Update>  backward-compatible bug fixes

Package        Current    Wanted    Latest    Type     Environments
-------------  ---------  --------  --------  -------  ----------------------
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  custom
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  cardputer
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  cardputer-adv
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  m5stack-sticks3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  s3-devkit
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  s3-devkit-n16-r8
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  m5stack-stamps3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  atom-lite-s3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  t-display-s3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  waveshare-s3-geek
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  t-embed-s3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  t-embed-s3-cc1101
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  t-embed-s3-cc1101plus
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  xiao-esp32s3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  vision-master-t190
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  heltec_wifi_lora_32_V4
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  heltec_wifi_lora_32_V3
ESP32SPISlave  0.6.9      0.6.9     0.8.0     Library  um_pros3
FastLED        3.10.3     3.10.3    3.10.7    Library  custom
FastLED        3.10.3     3.10.3    3.10.7    Library  cardputer
FastLED        3.10.3     3.10.3    3.10.7    Library  cardputer-adv
FastLED        3.10.3     3.10.3    3.10.7    Library  m5stack-sticks3
FastLED        3.10.3     3.10.3    3.10.7    Library  s3-devkit
FastLED        3.10.3     3.10.3    3.10.7    Library  s3-devkit-n16-r8
FastLED        3.10.3     3.10.3    3.10.7    Library  m5stack-stamps3
FastLED        3.10.3     3.10.3    3.10.7    Library  atom-lite-s3
FastLED        3.10.3     3.10.3    3.10.7    Library  t-display-s3
FastLED        3.10.3     3.10.3    3.10.7    Library  waveshare-s3-geek
FastLED        3.10.3     3.10.3    3.10.7    Library  t-embed-s3
FastLED        3.10.3     3.10.3    3.10.7    Library  t-embed-s3-cc1101
FastLED        3.10.3     3.10.3    3.10.7    Library  t-embed-s3-cc1101plus
FastLED        3.10.3     3.10.3    3.10.7    Library  xiao-esp32s3
FastLED        3.10.3     3.10.3    3.10.7    Library  vision-master-t190
FastLED        3.10.3     3.10.3    3.10.7    Library  heltec_wifi_lora_32_V4
FastLED        3.10.3     3.10.3    3.10.7    Library  heltec_wifi_lora_32_V3
FastLED        3.10.3     3.10.3    3.10.7    Library  um_pros3
RotaryEncoder  1.5.3      1.5.3     1.6.0     Library  t-embed-s3
RotaryEncoder  1.5.3      1.5.3     1.6.0     Library  t-embed-s3-cc1101
RotaryEncoder  1.5.3      1.5.3     1.6.0     Library  t-embed-s3-cc1101plus
```

</details>

## Native tests

✅ Native test suite passed.

## Development activity — last 7 days

No commits during the last 7 days.

## Recent resource history

| Date | Commit | RAM | Flash | Boards | Tests |
|---|---|---:|---:|---:|---|
| 2026-09-27 | `d972aa8` | 97,328 B | 3,772,136 B | 18/18 | ✅ |
| 2026-10-04 | `8022f80` | 97,328 B | 3,772,120 B | 18/18 | ✅ |
| 2026-10-11 | `8022f80` | 88,448 B | 3,772,104 B | 18/18 | ✅ |

---

This branch is generated automatically. Do not edit it manually.

Static RAM is PlatformIO's compile-time `.data + .bss` measurement; it is not runtime heap consumption after boot.
