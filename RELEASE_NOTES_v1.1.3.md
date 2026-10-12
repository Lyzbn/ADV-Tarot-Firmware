# ADV Tarot v1.1.3 — Boot image fix / 启动镜像修复

## 中文

修复 v1.1.2 发布包的启动参数错误：合并过程曾将 PlatformIO 生成的 DIO
bootloader 头改写为 QIO，可能造成烧录成功但开机黑屏。v1.1.3 保留原始
DIO / 80MHz / 8MB 启动头；应用仍由 bootloader 配置正常的 Flash 运行模式。

- 新增发布打包校验，逐字节检查 bootloader、分区表、boot_app0 和应用。
- 打包回归测试 5 项通过，主机逻辑和预览行为测试通过，No-SD 构建通过。
- 保留完整 78 张牌、完整牌意默认值与所有现有功能；SD 牌面内容未变。
- 本轮没有连接 Cardputer ADV，尚未完成 USB 和电池冷启动实机复测。
  Issue #1 保持打开，等待受影响用户验证。

下载 `ADV-Tarot-Cardputer-ADV-v1.1.3-NoSD-M5Burner.bin`，完整写入 **0x0**。
如烧录工具要求 Flash mode，选择 **DIO**，不要覆盖为 QIO。
合并镜像会清除 NVS 设置、学习进度和最近占卜记录；microSD 文件不受影响。
无需先擦除整片 Flash。可选资源包只需在尚未安装 SD 资源时使用。

仅适用 **M5Stack Cardputer ADV / ESP32-S3 / 8MB Flash**。
M5Burner 平台条目的更新独立于此 GitHub Release；请核对下载版本为 1.1.3。

## English

Fixes an incorrect boot header in the v1.1.2 merged release image. Packaging
overrode PlatformIO's DIO bootloader header with QIO, which could prevent boot
despite successful flashing. v1.1.3 preserves the original DIO / 80MHz / 8MB
header. The software bootloader still configures normal application flash mode.

- Added byte-for-byte checks of all four flash sections and five packaging regression tests.
- No-SD compilation, host logic tests and preview behavior tests passed.
- The complete 78-card experience and existing defaults are retained; card artwork is unchanged.
- No Cardputer ADV was connected for this release task. USB and battery cold-boot
  verification is still pending; issue #1 remains open for affected-user feedback.

Flash `ADV-Tarot-Cardputer-ADV-v1.1.3-NoSD-M5Burner.bin` at **0x0**.
If the flasher asks for a flash mode, select **DIO**, not QIO. The merged image
clears NVS settings, learning progress and recent reading history. microSD files
are unaffected. A separate full-chip erase is not required.

For **M5Stack Cardputer ADV / ESP32-S3 / 8MB Flash** only. The M5Burner listing is
updated separately from GitHub; check that the downloaded version is 1.1.3.

Use `SHA256SUMS.txt` to verify the binary and optional SD archive.
