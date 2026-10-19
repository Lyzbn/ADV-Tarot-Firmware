# ADV Tarot v1.1.4 — 可靠性维护 / Reliability maintenance

## 中文

发布 2026-10-16 已在 Cardputer ADV 上完成基础验收的维护构建。`v1.1.4` 是对外发行标签，固件应用与当时实测文件逐字节一致。

- 修复普通选牌与二择双牌翻转时的计时问题，避免刚开始的翻牌动画被旧时钟误判为结束。
- 历史保存失败时保留待保存状态、提示并节流重试；删除、清空、设置与学习进度写入失败时保留原状态，避免显示假成功。
- 固定验证过的依赖版本，补充实际应用路径的持久化故障注入与打包回归检查。
- 用户已确认普通三牌、二择／核心建议、每次新增一条历史，以及真正无卡时的 USB／电池冷启动、学习牌面和历史保留。
- 保留完整 78 张内嵌牌面、DIO 启动头和既有功能；314 张可选 SD 图片与 v1.1.3 相同。

### 下载与安装

| 文件 | 用途 |
| --- | --- |
| `ADV-Tarot-Cardputer-ADV-v1.1.4-NoSD-M5Burner.bin` | 完整合并固件，写入 `0x0`，DIO |
| `ADV-Tarot-v1.1.4-Optional-SD-Assets.zip` | 可选图片包；把 `tarot` 文件夹复制至 FAT32 microSD 根目录 |
| `ADV-Tarot-v1.1.4-Relink.zip` | 框架源码、应用对象、许可与重链接说明；普通安装无需下载 |
| `PROVENANCE.json`、`VALIDATION.md` | 构建来源、摘要与实际验收范围 |
| `SHA256SUMS.txt` | 发布文件完整性校验 |

仅适用 **M5Stack Cardputer ADV / ESP32-S3 / 8MB Flash**。
完整镜像从 **`0x0`** 写入，使用 **DIO**，会清除 NVS 设置、学习进度和历史；microSD 文件不受影响。不要将完整镜像写入 `0x10000`。

实机验收采用保留 NVS 的分段写入；完整镜像已逐段校验，但清空 NVS 后的首次安装、长期压力和全部设置组合尚未另行实测。来源为固定提交 `a258094` 的干净本机构建；同源码 CI 通过，CI 归档不冒充实测文件。详见 [验收记录](https://github.com/Lyzbn/ADV-Tarot-Firmware/blob/main/VALIDATION.md)。

M5Burner 平台条目与 GitHub 独立更新，请核对下载版本和摘要。[Issue #1](https://github.com/Lyzbn/ADV-Tarot-Firmware/issues/1) 继续等待原受影响用户反馈。

## English

Publishes the maintenance build accepted on Cardputer ADV on 16 October 2026. v1.1.4 is the distribution label for the unchanged, hardware-tested application bytes.

- Fixes stale-clock timing in ordinary and simultaneous card reveals.
- Preserves pending history after failed saves, with feedback and throttled retry. Failed deletion, clearing, settings or study-progress writes retain the previous state instead of reporting false success.
- Pins verified dependencies and adds persistence fault-injection and packaging regression coverage.
- The user confirmed both reading flows, one new record per reading, and actual no-SD USB/battery cold starts with learning faces and history retained.
- Retains all 78 embedded faces and the DIO boot header. The 314 optional SD images are unchanged.

Flash the merged `.bin` at **`0x0`**, using **DIO**, on **Cardputer ADV / ESP32-S3 / 8MB Flash** only. This clears NVS settings, progress and history. microSD files are unaffected. Verify `SHA256SUMS.txt` first; do not flash the full image at `0x10000`.

Acceptance used separate segments while preserving NVS. The full image is verified against those segments; fresh installation into reset NVS, exhaustive persistence combinations and long-duration stress have not been separately tested. `PROVENANCE.json` distinguishes the clean local accepted build from same-source CI validation. The optional `Relink.zip` contains framework sources, application objects, notices and relinking instructions; application source remains private.

M5Burner updates independently of GitHub. Check its actual download version and digest. Issue #1 remains open for the originally affected user's feedback.
