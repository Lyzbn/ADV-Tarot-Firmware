# v1.1.4 固件来源与验收 / Provenance and validation

当前稳定版：[v1.1.4](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/tag/v1.1.4)。
2026-10-20 发布的是 2026-10-16 已完成基础实机验收的 No-SD 应用与其原始配套分段；没有为本次发布重新编译或修改应用字节。

## 固定来源

- 源码提交：`a2580940eedf43ed539a94f9d8fc66ba77820b1e`。
- 源码树：`19d9ef93daa7ec541af7eb3dc1f9588fe59a1094`。
- 应用 SHA-256：`e8f5846a60f9a971ad7e5ae4e1e3466dc26f7f556862ff3207fbe22f6ec7cb1a`。
- 完整镜像 SHA-256：`8f6ed1e7c2a3d9caafa9c1a4a26a3efa47275520c7e19f218137d2846be63fc8`。
- 来源是固定提交的干净本机构建归档。相同源码的 CI 检查与双变体构建通过；CI 生成物与这份实测文件分开记录，不能互换摘要。
- 机器可读记录：[PROVENANCE_v1.1.4.json](https://github.com/Lyzbn/ADV-Tarot-Firmware/blob/main/PROVENANCE_v1.1.4.json)。Release 中同一文件名为 `PROVENANCE.json`。

`v1.1.4` 是这些原始字节的对外发行标签，不是通过修改二进制内的版本字符串得到的新构建。

## 已完成的检查

| 检查 | 结果与证据范围 |
| --- | --- |
| 源码与自动测试 | 当时完成核心及真实应用路径测试、持久化故障注入、预览行为测试、11 项 Python 打包测试、标准版与 No-SD 版构建；同源码 Linux CI 成功 |
| 本次发布包 | 原归档 329 项摘要通过；完整镜像中的 bootloader、分区表、boot_app0、应用与原分段逐字节一致；启动头 DIO / 80MHz / 8MB；应用未超出分区 |
| 配套重链接 | 保留的原对象可完整重现原 ELF 与应用；公开去调试对象包可重链接，并已完成修改底层库后的重编验证。重链接产物未做设备验收，不替代正式发布 BIN |
| SD 资源 | 314 个图片文件与 v1.1.3 逐字节相同；157 PNG + 157 JPEG |
| 启动日志 | 20 秒受控重启观察进入首页，无 panic、WDT 或再次重启；这段观察本身不等于冷启动或长期稳定性测试 |
| 普通三牌 | 用户确认逐张翻牌正常、结果可读、历史只新增一条 |
| 二择／核心建议 | 用户确认 A/B 同时翻牌正常、后续流程可完成、历史只新增一条 |
| 实际无卡运行 | 用户关机取出 microSD 后，确认 USB 与电池两种冷启动正常、可看学习牌面、刚才的新历史保留 |

实机验收设备为 **M5Stack Cardputer ADV**，采用四个分段分别写入、保留 NVS 的方式。公开完整镜像包含同一组分段，但从 `0x0` 整体烧录会清空 NVS；本轮没有将“保留 NVS 的分段验收”描述为“清空 NVS 的首次安装验收”。

## 仍待补充的设备场景

- 公开完整镜像从 `0x0` 写入、清空 NVS 后的首次安装。
- 所有设置、删除／清空、学习进度的设备持久化组合及设备故障注入。
- 全部图片逐张显示、音频、帧率和 IMU 操作手感。
- 连续 50–100 次生命周期及长期 heap 趋势。

RTC 不可用时采用从编译时间起算的软件时钟，记录时间属于估算时间。

## 安装与分发

完整镜像只适用 Cardputer ADV / ESP32-S3 / 8MB Flash，写入 **`0x0`**，Flash mode 使用 **DIO**。会清除 NVS 设置、学习进度和最近记录；microSD 文件不受影响。不把完整镜像当成应用段写入 `0x10000`。先保存需要保留的信息，并用 Release 的 `SHA256SUMS.txt` 校验文件。

GitHub Release 与 M5Burner 平台条目独立更新。本次更新 GitHub；M5Burner 实际分发版本、下载摘要及烧录参数仍需单独核对，不以 GitHub 发布成功替代。检查时记录版本、文件 SHA-256、地址 `0x0`、DIO 和 NVS 数据影响。

[Issue #1](https://github.com/Lyzbn/ADV-Tarot-Firmware/issues/1) 保持打开，等待原受影响用户反馈。自己的设备验收不等于对该用户设备问题的复现或确认解决。

v1.1.3 当时的验收状态保存在 [历史记录](https://github.com/Lyzbn/ADV-Tarot-Firmware/blob/main/VALIDATION_v1.1.3.md)，旧 Release 与标签不变。

## English

v1.1.4 publishes the unchanged application accepted on a Cardputer ADV on 16 October 2026. The selected binary comes from a clean local build of the fixed commit above. Successful CI validates the same source; its artifact is not substituted for the accepted binary.

The user confirmed normal three-card reveals, simultaneous A/B reveals and the core-guidance flow, exactly one new history record per reading, and actual no-SD USB and battery cold starts with learning faces and new history retained. All four merged-image segments match the original archived segments byte for byte, with a DIO / 80MHz / 8MB boot header. All 314 optional SD images are unchanged from v1.1.3.

Hardware acceptance used separately flashed segments while preserving NVS. A fresh full-image install with reset NVS, exhaustive settings/deletion/study persistence, image-by-image display, audio/IMU evaluation and long-duration stress remain untested. Flashing the public full image at `0x0` clears NVS settings, progress and history; microSD files are unaffected. Do not write the full image at `0x10000`.

The M5Burner listing is a separate distribution channel whose actual downloaded version and digest require separate verification. Issue #1 remains open for feedback from the originally affected user.
