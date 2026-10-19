# SDK 补充许可材料

核对日期：2026-10-16。材料来自 ESP-IDF `v4.4.7` 主仓提交 `38eeba213aa695aabfd6d89aa9f5078dbe5a94c3` 记录的固定子模块提交。下载原文未改；逐文件 URL、SHA-256 和适用路径见 `SUPPLEMENT_SOURCE_ORIGINS_code_agent.json` 与 `SUPPLEMENT_SOURCE_ORIGINS_text_agent.json`。

| 组件 | 固定提交 | 随包许可文件 | 与现有 SDK 的匹配证据 |
| --- | --- | --- | --- |
| Asio | `f31694c9f1746ba189a4bcae2e34db15135ddb22` | `submodules/asio/asio/COPYING`、`LICENSE_1_0.txt`；Boost Software License 1.0 | 412 个上游头文件的 Git blob 与 SDK 逐字节一致；适用于 `include/asio/asio/**`，另需为 `lib/libasio.a` 保留对应库署名 |
| libcoap | `3aa11612c143c9734d72022720f33e12506f7a2c` | `submodules/libcoap/LICENSE`、`COPYING`；BSD 2-Clause 及文件内列明的其他组件条款 | 41 个上游头文件与 SDK 一致；对应 `include/coap/libcoap/**`、`lib/libcoap.a`。保留 uthash/utlist 自带声明 |
| libsodium | `4f5e89fa84ce1d178a6765b8b46f2b6f91216677` | `submodules/libsodium/LICENSE`；ISC | 70/70 个 SDK 上游头文件一致；对应 `include/libsodium/libsodium/**`、`lib/liblibsodium.a` |
| Expat | `454c6105bc2d0ea2521b8f8f7a5161c2abd8c386` | `submodules/expat/COPYING`；MIT | 14/14 个 SDK 上游头文件一致；对应 `include/expat/expat/**`、`lib/libexpat.a` |
| TinyCBOR | `7c349dbb6b8d76db39383b226d3ebdf59b8ab37d` | `submodules/tinycbor/LICENSE`；MIT | IDF 包装头与固定主仓 tree 一致；kit 缺少其引用的 TinyCBOR 上游头，不能据此独立确认 `lib/libcbor.a` 的实际源码提交 |
| Espressif Wi-Fi 预编译库 | `f2aae4d44ec7908013066e69d29b9948846c335c` | `submodules/esp32-wifi-lib/LICENSE`；Apache 2.0 | SDK 的 `libcoexist/libcore/libespnow/libmesh/libnet80211/libpp/libsmartconfig/libwapi.a` 共 8 个 archive 与该提交逐字节一致 |
| Espressif PHY 预编译库 | `dcfdccf6cc2fc02d0886624b7998c890d1a19b28` | `submodules/esp-phy-lib/LICENSE`；Apache 2.0 | SDK 的 `ld/libphy.a`、`ld/libbtbb.a` 均与该提交逐字节一致 |

表中 SDK 相对路径均位于 `framework/tools/sdk/esp32s3/`。头文件匹配证明这些文件的来源，不将其扩大为整个预编译 archive 已重现。Wi-Fi、PHY 的匹配直接覆盖所列 archive；IDF 的 `esp_wifi`、`esp_phy` 包装层仍归主仓材料说明。

后续已补齐以下实际随 SDK 提供组件的材料。所有全文保留上游原字节；版权块只摘取公开第三方文件中的原声明，不包含私有应用实现。

## 其余固定 IDF 子模块

来源记录：`SUPPLEMENT_SOURCE_ORIGINS_extra_agent.json`。

| 组件 | 固定提交 | 许可文件 | 检查范围 |
| --- | --- | --- | --- |
| spiffs | `0dbb3f71c5f6fae3747a9d935372773762baf852` | `submodules/spiffs/LICENSE` | 许可来自主仓固定 gitlink；不以版本号推定 archive 可重现 |
| unity | `7d2bf62b7e6afaf38153041a9d53c21aeeca9a25` | `submodules/unity/docs/license.txt` | 2/2 个存在于本地的上游文件逐字节一致 |
| cmock | `eeecc49ce8af123cf8ad40efdb9673e37b56230f` | `submodules/cmock/LICENSE.txt` | 2/2 个存在于本地的上游文件逐字节一致 |
| lwip | `a45be9e438f6cf9c54ec150581819c3b95d5af6b` | `submodules/lwip/COPYING` | 158/158 个存在于本地的上游文件逐字节一致 |
| protobuf-c | `abc67a11c6db271bedbb9f58be85d6f4e2ea8389` | `submodules/protobuf-c/LICENSE` | 1/1 个存在于本地的上游文件逐字节一致 |
| cjson | `87d8f0961a01bf09bef98ff89bae9fdec42181ee` | `submodules/cjson/LICENSE` | 23/23 个存在于本地的上游文件逐字节一致 |
| mbedtls | `2b8e772fc1cb0732cda3bae7d1e9d6f4cfaf63d9` | `submodules/mbedtls/LICENSE` | 96/96 个存在于本地的上游文件逐字节一致 |
| esp-mqtt | `bb9c8af9d552b608dd3aabf9617bde757a538ebe` | `submodules/esp-mqtt/LICENSE` | 2/2 个存在于本地的上游文件逐字节一致 |
| esp32-bt-lib | `e5c0f7256ecf5b5f8eb28c1793051a6b88f95124` | `submodules/esp32-bt-lib/LICENSE` | ESP32-S3 libbtdm_app.a 与固定提交逐字节一致 |

## Arduino SDK 更新对应组件

官方 SDK 更新记录：[Arduino-ESP32 PR #9339](https://github.com/espressif/arduino-esp32/pull/9339)。完整固定提交、各文件下载 URL 和摘要见 `SUPPLEMENT_SOURCE_ORIGINS_builder_agent.json`。这里按该次 SDK 更新提供的来源记录许可版本；头文件核对不宣称已经从源代码重建所有 archive。

| 组件 | 固定提交 | 许可 | SDK 文件检查 |
| --- | --- | --- | --- |
| esp-dl | `0632d2447dd49067faabe9761d88fa292589d5d9` | `submodules/esp-dl/LICENSE` | 64/64 个文件逐字节一致 |
| esp32-camera | `f0bb42917cddcfba2c32c2e2fb2875b4fea11b7a` | `submodules/esp32-camera/LICENSE` | 4/4 个文件逐字节一致 |
| esp-rainmaker | `d8e93454f495bd8a414829ec5e86842b373ff555` | `submodules/esp-rainmaker/LICENSE` | 16/16 个文件逐字节一致 |
| esp-dsp | `9b4a8b42b98f2f7cd614e47bb4d159acbe500bee` | `submodules/esp-dsp/LICENSE` | 70/70 个文件逐字节一致 |
| tinyusb | `a0e5626bc50d484a23f33000c48082179f0cc2dd` | `submodules/tinyusb/LICENSE`、`submodules/tinyusb/lib/SEGGER_RTT/LICENSE.md`、`submodules/tinyusb/lib/fatfs/LICENSE.txt` | 88/88 个文件逐字节一致 |

## TLSF、FreeModbus、LittleFS

来源：`SUPPLEMENT_SOURCE_ORIGINS_storage_agent.json`。三项本地 SDK archive 均与 Arduino 官方 `dcc1105b…` 的 ESP32-S3 对应文件逐字节一致。

- TLSF：固定 IDF `components/heap/tlsf/tlsf.c` 的 Matthew Conte BSD 3-Clause 声明已保存至 `tlsf/TLSF-BSD-3-Clause-NOTICE.txt`；heap 公开头文件 7/7 与该 IDF 提交一致。
- FreeModbus：固定 IDF 中 70 个 `.c/.h` 已按 Git blob 核对，23 份不同 BSD 声明保存在 `freemodbus/`，包括 Christian Walter、Armink、Espressif 及原文件列明的其他署名；4/4 个已提供包装头一致。保留 Apache 包装许可，未以其替代底层 BSD。
- `esp_littlefs`：`v1.14.1`、完整提交 `41873c20fb5cdbcf28d7d6cc04e4bcb4a1305317`；PR #9339 对应，提供的头文件逐字节一致。其子模块 `littlefs-project/littlefs` 固定 `f53a0cc961a8acac85f868b431d2f3e58e447ba3`。组件 MIT 与底层 BSD 3-Clause 全文均保存于 `littlefs/`。

## 已提供文件内的声明

`extracted-notices/` 保存实际提供的 SDK、Arduino、M5GFX、M5Unified 公开文件中的版权及许可注释。`EXTRACTED_SOURCE_NOTICES_ORIGINS.json` 记录范围与摘要。另从固定 IDF 提取 SDMMC、UBSan、QR Code 底层实现声明，来源和文件摘要见 `IDF_SOURCE_NOTICES_ORIGINS.json`。libb64 原声明和 M5GFX 随附的 IPA/Adafruit 字体许可另行保存；CI 对应 M5GFX archive 已删除未用 `lgfx_font_japan.c.o`（59→58 成员），删除前后原 CI 对象重链的应用字节完全一致；其他 GFXFF/efont 成员仍保留。IPA 许可仅保留作已移除成员的来源材料。

## 工具链边界

已从实际安装的 Espressif Xtensa ESP32-S3 `8.4.0+2021r2-patch5` 包保存 87 份 package/许可文件，包括 GCC Runtime Library Exception 3.1、GPL/LGPL 与 newlib/libgloss 版权条款，位于 `toolchain-xtensa-esp32s3/`。`SOURCE.json` 记录原文摘要与参考 runtime 摘要，没有复制 runtime archive。该参考安装包是 macOS ARM64，不能替代 Linux CI 包身份的核对。

最终公开重链包采用外部官方 Linux 工具链；不分发 GCC/libstdc++/libgcc 等独立运行库或工具二进制。已真实下载核对的官方 Linux x86_64 包为 `8.4.0+2021r2-patch5`，67,385,729 字节，SHA-256 `6618e8a91fca47da09c840a61bf008b1f06698553389c01c8788e595d8e84da9`；其 1,737 个文件与 CI 导出一致。实际 CI esptool package.version 为 `2.41100.260830`（内部 4.11.0）。完整下载/安装记录由重链包提供。Runtime Exception 对合并目标代码的条件不扩大为独立 `.a` 的无条件分发许可。私有 CI 导出可用于验证，但其工具链目录不直接复制进公开包。

最终分发将本映射、许可原文、来源 JSON 与 `THIRD_PARTY_NOTICES.md` 一起提供。公开副本已将来源 JSON 的本地准备目录归一为相对路径；原始许可文本不改。
