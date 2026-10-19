# 第三方软件与资源声明

ADV Tarot v1.1.4 的第三方声明，核对日期：2026-10-20。本说明覆盖固件和配套重链接材料中实际提供的第三方库、SDK 文件及资源；某个库随 SDK 提供，不表示其全部功能进入最终固件。配套重链包使用 2026-10-16 实测应用 a2580940eedf 的原始本地 macOS arm64 构建对象；未重新编译应用。对象与验证结果由包内清单记录。

第三方组件保留各自许可。ADV Tarot 的[固件许可](LICENSE-FIRMWARE.md)与[重链许可补充](LICENSE-RELINK.md)不限制这些组件原有的权利。下表是阅读索引，完整版权、许可条款和逐文件声明见 [licenses/third-party](licenses/third-party/)；该目录的 `SHA256SUMS` 可检查材料完整性。原始声明保持原文，来源 JSON 仅将本地准备目录改为相对路径。

## Arduino 与设备库

| 组件及版本 | 适用文件或材料 | 许可与署名材料 |
| --- | --- | --- |
| Arduino-ESP32 2.0.17；PlatformIO framework `3.20017.241212+sha.dcc1105b` | Arduino core、SPI、Wire、FS、SD、Preferences 及其对应的六个 archive 和源码 | LGPL-2.1-or-later；Arduino、Espressif 及各文件作者。见 [LGPL 全文](licenses/third-party/LGPL-2.1.txt)和 [Arduino 文件声明](licenses/third-party/extracted-notices/ARDUINO_SOURCE_NOTICES.txt)，其中 libb64 另见[原声明](licenses/third-party/libb64-LICENSE.txt)。 |
| M5Cardputer Git tag 1.2.0 | `libM5Cardputer.a` | M5Stack Technology CO LTD；[MIT](licenses/third-party/M5Cardputer-MIT.txt)。 |
| M5Cardputer 内的 Adafruit TCA8418 驱动 | `libM5Cardputer.a(Adafruit_TCA8418.cpp.o)` | Copyright (c) 2019 Limor Fried (Adafruit Industries)；[完整 BSD 3-Clause 条款](licenses/Adafruit-TCA8418-BSD.txt)。M5 的移植文件明确保留 Adafruit 作者和 BSD 声明，不统一按外层 MIT 处理。 |
| M5Unified 0.2.18 | `libM5Unified*.a` | M5Stack；[MIT](licenses/third-party/M5Unified-MIT.txt)和[文件声明](licenses/third-party/extracted-notices/M5UNIFIED_SOURCE_NOTICES.txt)。 |
| M5GFX 0.2.25 / commit `ad9b814264d4e2000e9f30070002310bbccaffc9` | `libM5GFX*.a` | M5Stack；[MIT](licenses/third-party/M5GFX-MIT.txt)。其字体、解码器等文件另有声明，见 [M5GFX 文件声明](licenses/third-party/extracted-notices/M5GFX_SOURCE_NOTICES.txt)。Adafruit GFX 字体见 [BSD 全文](licenses/third-party/vendor-fonts/Adafruit-GFXFF-BSD.txt)，Tom Thumb 的 BSD 声明也保留于文件声明中。 |
| IRremote 4.7.1 | 构建配置依赖；实际链接 map 没有 IRremote 输入，当前重链包无 IRremote archive | [MIT 与原版权](licenses/third-party/IRremote-MIT.txt)保留作依赖出处，不将它计为已确认链接的独立库。 |

Arduino 的配套材料采用随包提供所需材料的方式：对应库源码、构建配方、可重链应用对象和操作说明一并提供。接收者可修改这些库并重新编译、链接；个人修改以及为调试这些修改而进行的逆向工程权限见重链许可补充。不以源码仓库链接代替这套材料，也不设置由维护者日后供给材料的多年承诺。

## ESP32-S3 SDK

SDK 的 ESP-IDF 基线为 `v4.4.7`，主仓提交 `38eeba213aa695aabfd6d89aa9f5078dbe5a94c3`。通用 Espressif 代码采用 [Apache 2.0](licenses/third-party/esp-idf-4.4.7/LICENSE)，具体文件另有许可的，以该文件声明为准。这里没有将整个 SDK 归为单一许可。

以下路径均相对于重链包 `framework/tools/sdk/esp32s3/`。原始头文件及链接脚本中的声明保留在包内；为便于随固件一起阅读，另集中保存 [SDK 原始版权与许可块](licenses/third-party/extracted-notices/SDK_SOURCE_NOTICES.txt)。

| 组件或 archive | 许可及完整声明 |
| --- | --- |
| FreeRTOS：各构建目录下 `libfreertos.a` | [MIT](licenses/third-party/esp-idf-4.4.7/components/freertos/LICENSE.md)；Amazon、Cadence 及移植文件的版权见 SDK 文件声明。 |
| newlib 的 SDK 适配代码：`libnewlib.a`、`include/newlib/` | Espressif Apache 代码及 [newlib 多作者条款](licenses/third-party/esp-idf-4.4.7/components/newlib/COPYING.NEWLIB)。工具链独立 libc/libm 见后文外部依赖范围。 |
| lwIP：`liblwip.a` | Swedish Institute of Computer Science 等；[BSD 与原文件声明](licenses/third-party/submodules/lwip/COPYING)。 |
| Mbed TLS：`libmbedtls*.a`、`libmbedcrypto.a`、`libmbedx509.a` | ARM、Mbed TLS 作者等；[Apache 2.0](licenses/third-party/submodules/mbedtls/LICENSE)。 |
| wpa_supplicant：`libwpa_supplicant.a` | Jouni Malinen 等；[BSD 及原组件声明](licenses/third-party/esp-idf-4.4.7/components/wpa_supplicant/COPYING)。 |
| Asio：`libasio.a` | Christopher M. Kohlhoff；[Boost Software License 1.0](licenses/third-party/submodules/asio/asio/LICENSE_1_0.txt)，另保留 [COPYING](licenses/third-party/submodules/asio/asio/COPYING)。 |
| libcoap：`libcoap.a` | Olaf Bergmann 等；[BSD 2-Clause 及文件所列条款](licenses/third-party/submodules/libcoap/LICENSE)，保留 uthash/utlist 文件声明。 |
| libsodium：`liblibsodium.a` | Frank Denis 等；[ISC](licenses/third-party/submodules/libsodium/LICENSE)。 |
| Expat：`libexpat.a` | Expat 作者；[MIT](licenses/third-party/submodules/expat/COPYING)。 |
| TinyCBOR：`libcbor.a` | Intel Corporation；[MIT](licenses/third-party/submodules/tinycbor/LICENSE)。许可取自 IDF 固定 gitlink；本地只有包装头，未据此声称独立重现 archive 的源码提交。 |
| nghttp2：`libnghttp.a` | Tatsuhiro Tsujikawa 及贡献者；[MIT 全文](licenses/third-party/esp-idf-4.4.7/components/nghttp/COPYING)。 |
| protobuf-c：`libprotobuf-c.a` | Dave Benson 及 protobuf-c 作者；[BSD 2-Clause](licenses/third-party/submodules/protobuf-c/LICENSE)。 |
| cJSON、JSMN：`libjson.a`、`libjsmn.a` | Dave Gamble、cJSON 贡献者与 Serge A. Zaitsev；[cJSON MIT](licenses/third-party/submodules/cjson/LICENSE)及 SDK 文件声明内的 JSMN MIT 全文。 |
| SPIFFS：`libspiffs.a` | Peter Andersson；[MIT](licenses/third-party/submodules/spiffs/LICENSE)。 |
| FatFs：`libfatfs.a` | ChaN；`include/fatfs/src/ff.h` 的原许可全文保留于 SDK 文件声明。 |
| TLSF：`libheap.a` 中的实现 | Matthew Conte；[BSD 3-Clause 原声明](licenses/third-party/tlsf/TLSF-BSD-3-Clause-NOTICE.txt)。Espressif heap 包装层另有 Apache 声明。 |
| LittleFS：`libesp_littlefs.a` | `esp_littlefs` 1.14.1 / 提交 `41873c20…` 的 [MIT](licenses/third-party/littlefs/esp_littlefs-MIT-LICENSE.txt)；其固定 littlefs `f53a0cc9…` 的 [BSD 3-Clause](licenses/third-party/littlefs/littlefs-BSD-3-Clause-LICENSE.md)。 |
| FreeModbus：`libfreemodbus.a` | Christian Walter、Armink、Espressif 等；保留 [23 份有差异的原 BSD 声明](licenses/third-party/freemodbus/)，以及 [IDF 包装层许可](licenses/third-party/esp-idf-4.4.7/components/freemodbus/LICENSE)。 |
| Unity、CMock：`libunity.a`、`libcmock.a` | Mike Karlesky、Mark VanderVoord、Greg Williams；[Unity MIT](licenses/third-party/submodules/unity/docs/license.txt)、[CMock MIT](licenses/third-party/submodules/cmock/LICENSE.txt)。 |
| Console 的 argtable3、linenoise | [argtable3 原条款](licenses/third-party/esp-idf-4.4.7/components/console/argtable3/LICENSE)、[linenoise BSD](licenses/third-party/esp-idf-4.4.7/components/console/linenoise/LICENSE)。 |
| SDMMC、UBSan、QR Code 实现 | 分别保留 [SDMMC 原声明](licenses/third-party/extracted-notices/SDMMC_SOURCE_NOTICES.txt)、[UBSan 原声明](licenses/third-party/extracted-notices/UBSAN_SOURCE_NOTICES.txt)、[QR Code MIT](licenses/third-party/extracted-notices/QRCODE_SOURCE_NOTICES.txt)；包装层不替代其底层声明。 |
| Xtensa/Cadence 支持代码；SDK Bluetooth 主机代码 | Cadence MIT、Espressif/其他作者的 Apache/BSD 等原文件声明均保留在 SDK 文件声明及对应头文件中。 |
| Espressif Wi-Fi：`libcore/libcoexist/libespnow/libmesh/libnet80211/libpp/libsmartconfig/libwapi.a` | 固定上游提交的 [Apache 2.0](licenses/third-party/submodules/esp32-wifi-lib/LICENSE)；8 个实际 archive 已与该提交逐字节核对。 |
| Espressif PHY：`ld/libphy.a`、`ld/libbtbb.a`；Bluetooth 控制器：`ld/libbtdm_app.a` | [PHY Apache 2.0](licenses/third-party/submodules/esp-phy-lib/LICENSE)、[BT Apache 2.0](licenses/third-party/submodules/esp32-bt-lib/LICENSE)；所列 archive 已与各固定提交逐字节核对。 |
| ESP-DL：`ld/{libdl,libmfn,libcat_face_detect,libhuman_face_detect,libcolor_detect}.a` | Espressif Systems；固定 `0632d244…` 的 [MIT](licenses/third-party/submodules/esp-dl/LICENSE)。 |
| ESP32 Camera / FB GFX、ESP RainMaker、ESP-DSP | SDK 更新记录中固定 `f0bb4291…`、`d8e93454…`、`9b4a8b42…`；分别见 [Camera](licenses/third-party/submodules/esp32-camera/LICENSE)、[RainMaker](licenses/third-party/submodules/esp-rainmaker/LICENSE)、[DSP](licenses/third-party/submodules/esp-dsp/LICENSE)。保留源内单独版权与许可声明，包括 Camera 的 OpenMV 来源声明。 |
| Arduino TinyUSB：`libarduino_tinyusb.a` | 固定 `a0e5626b…` 的 [MIT](licenses/third-party/submodules/tinyusb/LICENSE)，保留其文件内及附属组件声明。 |
| ESP-MQTT 及其余 Espressif SDK 包装/功能组件 | [ESP-MQTT Apache 2.0](licenses/third-party/submodules/esp-mqtt/LICENSE)及 SDK 主仓 Apache 2.0；各文件版权与例外见 SDK 文件声明。 |

来源与版本证据见[补充映射](licenses/third-party/SUPPLEMENT_SOURCE_MAP.md)及同目录 `SUPPLEMENT_SOURCE_ORIGINS_*.json`。IDF gitlink、Arduino 官方 [SDK 更新 PR #9339](https://github.com/espressif/arduino-esp32/pull/9339)、头文件/二进制逐字节核对分别记录，匹配若只覆盖头文件，不扩大为整个库已可重现。

## 字体

应用中文界面使用 M5GFX 的 efontCN_12。efont、Adafruit GFXFF、Tom Thumb 等库内字体保留其单独作者与条款，见 [efont 完整 BSD 条款](licenses/efont-COPYRIGHT.txt)、[M5GFX 文件声明](licenses/third-party/extracted-notices/M5GFX_SOURCE_NOTICES.txt)及 [Adafruit GFXFF BSD 全文](licenses/third-party/vendor-fonts/Adafruit-GFXFF-BSD.txt)。未将所有字体统一归为 M5GFX 的 MIT 许可。

efont 条款与实际固定 M5GFX 源码中的 `src/lgfx/Fonts/efont/COPYRIGHT.txt` 逐字相同，[上游固定文件](https://github.com/m5stack/M5GFX/blob/ad9b814264d4e2000e9f30070002310bbccaffc9/src/lgfx/Fonts/efont/COPYRIGHT.txt)可核对。Adafruit TCA8418 完整条款取自[官方固定提交的 license.txt](https://github.com/adafruit/Adafruit_TCA8418/blob/df1319acbe1f250b74d155c3535c177a20854030/license.txt)；M5 提供的是该驱动的移植，不据此声称其实现与上游文件逐字相同。

重链包已从 M5GFX archive 删除未使用的 `lgfx_font_japan.c.o`（IPA 衍生日文字体），成员由 59 变为 58。删除前后用原应用对象重链，应用均逐字节等于实测 SHA256 `e8f5846a60f9a971ad7e5ae4e1e3466dc26f7f556862ff3207fbe22f6ec7cb1a`。该日文字体成员不随包分发；[IPA 原许可](licenses/third-party/vendor-fonts/IPA_Font_License_Agreement_v1.0.txt)仅作为裁剪来源记录保留。

## 外部工具链

重链包不分发 GCC 工具链，也不单独提供其 `libgcc.a`、`libstdc++.a`、`libsupc++.a`、工具链 `libc.a/libm.a/libnosys.a`。接收者安装官方 `espressif/toolchain-xtensa-esp32s3@8.4.0+2021r2-patch5` 的 macOS arm64 包，以及 `platformio/tool-esptoolpy@2.41100.0`（内部 esptool 4.11.0）。这些是本次已验证的实际工具版本，不沿用其他项目的 Linux 环境。工具包许可由其官方发行提供。

[官方工具链归档](https://dl.registry.platformio.org/download/espressif/tool/toolchain-xtensa-esp32s3/8.4.0+2021r2-patch5/toolchain-xtensa-esp32s3-darwin_arm64-8.4.0+2021r2-patch5.tar.gz)为 66,266,308 字节，SHA256 `f5e195ac5268b560262af9eab058bee0572301240678fc687484186bbe56c823`；下载后 1,727 个普通文件与实测构建的工具链逐字节一致。[官方 esptool 归档](https://dl.registry.platformio.org/download/platformio/tool/tool-esptoolpy/2.41100.0/tool-esptoolpy-2.41100.0.tar.gz)为 520,571 字节，SHA256 `ec80a347efa02e64706075575fbe07b32d3140f4c4aaa7002350ea7d9f71b826`，199 个普通文件逐字节一致。`TOOLCHAIN_PACKAGE.json`、`ESPTOOL_PACKAGE.json` 保留官方归档信息与逐文件摘要；`README.md` 给出安装与核验步骤。

工具链的 [GCC Runtime Library Exception 3.1](licenses/third-party/toolchain-reference/gcc/COPYING.RUNTIME)、[GPL 3](licenses/third-party/toolchain-reference/gcc/COPYING3)、相关 LGPL 文本及 [newlib](licenses/third-party/toolchain-reference/newlib/COPYING.NEWLIB) / [libgloss](licenses/third-party/toolchain-reference/newlib/COPYING.LIBGLOSS) 声明作为参考原文保留。没有把 Runtime Exception 解释为可省略独立运行库发行材料的通用许可。

## 随包材料

本说明与 `licenses/third-party/` 应随发行资产一起提供；`SHA256SUMS` 校验许可材料，重链包自身的清单与 `VALIDATION.json` 校验构建输入及结果。硬件验收和发布状态由项目维护记录说明，不由许可材料的准备状态代替。

## Interface reference notice

The private development project documented a non-commercial interface reference
to:

- Project: `nongxl/CyberDeck-Tarot`, branch `StickS3`
- License: PolyForm Noncommercial License 1.0.0
- License URL:
  <https://polyformproject.org/licenses/noncommercial/1.0.0>

Required Notice: Copyright (c) 2026 nongxl
(https://github.com/nongxl/CyberDeck-Tarot)

A copy of the PolyForm Noncommercial License 1.0.0 is included in `licenses/`.

## Rider–Waite–Smith artwork

The No-SD firmware and optional microSD asset pack include technically resized
copies of all 78 Major and Minor Arcana cards from the original 1909
Rider–Waite–Smith deck:

- Artist: Pamela Colman Smith (1878–1951)
- Design and text: Arthur Edward Waite (1857–1942)
- Source collection:
  <https://commons.wikimedia.org/wiki/Category:Rider-Waite_tarot_deck>
- Wikimedia Commons marks the original files as public domain.

Public-domain status can differ by jurisdiction. The distributed firmware does
not claim exclusive rights over the original Rider–Waite–Smith artwork,
traditional card names, or traditional tarot correspondences.

## ADV Tarot card back

The blue-and-yellow star card back was generated for this project with OpenAI
image-generation tooling and subsequently cropped, scaled, and framed for the
Cardputer display. The finished project-specific design is not designated as
public domain and is covered by the ADV Tarot proprietary terms to the extent
owned by the project copyright holder and permitted by applicable terms and law.
