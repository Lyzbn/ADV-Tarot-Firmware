# ADV Tarot Firmware v1.1.2 — Verified Complete Experience

[中文](#中文) · [English](#english)

## 中文

v1.1.2 是面向 M5Stack Cardputer ADV 的完整体验维护版本。

### 本版变化

- 全新安装默认启用完整 78 张占卜牌库
- 全新安装默认启用完整牌意；简约牌意仍可在设置中切换
- No-SD 固件内嵌全部 78 张正位牌面和蓝底黄星牌背，逆位实时旋转
- microSD 继续作为可选高清增强，用于透明 PNG 牌面和长期 JSON 占卜归档
- 固件由 `v1.1.2` 标记源码重新构建，并通过标准版、No-SD 版、主机逻辑、
  浏览器预览和 314 个牌面资源检查

已经保存在 NVS 中的有效用户设置仍会保留。M5Burner 合并镜像从 `0x0`
完整写入时会清除原有 NVS，因此安装后会直接使用“完整 78 张 + 完整牌意”
的新安装默认体验。

### 下载

- `ADV-Tarot-Cardputer-ADV-v1.1.2-NoSD-M5Burner.bin`
  - bootloader、8MB 单应用分区表和应用的完整合并镜像
  - M5Burner / esptool 写入地址：`0x0`
- `ADV-Tarot-v1.1.2-Optional-SD-Assets.zip`
  - 可选 157 张透明 PNG、157 张兼容 JPEG 与资源说明
- `SHA256SUMS.txt`

## English

v1.1.2 is a verified complete-experience maintenance release for M5Stack
Cardputer ADV.

### Changes

- Fresh installations default to the complete 78-card reading deck
- Fresh installations default to complete interpretations; concise mode remains available
- The No-SD build embeds all 78 upright faces and the blue/gold card back
- microSD remains an optional enhancement for transparent PNG faces and long-term JSON archives
- Firmware was rebuilt from the `v1.1.2` source tag and passed standard and
  No-SD builds, host logic tests, browser preview tests, and all 314 card-asset checks

Existing valid NVS preferences remain intact during ordinary updates. The merged
M5Burner image is written completely at `0x0` and clears old NVS data, so a fresh
installation starts with the full deck and complete interpretations.

### Downloads

- `ADV-Tarot-Cardputer-ADV-v1.1.2-NoSD-M5Burner.bin`
  - Complete bootloader, 8MB single-app partition table, and application image
  - M5Burner / esptool offset: `0x0`
- `ADV-Tarot-v1.1.2-Optional-SD-Assets.zip`
  - Optional 157 transparent PNG files, 157 compatible JPEG files, and notices
- `SHA256SUMS.txt`

Full guide:
<https://lyzbn.github.io/ADV-Tarot-Firmware/>
