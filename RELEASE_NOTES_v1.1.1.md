# ADV Tarot Firmware v1.1.1 — Complete by Default

[中文](#中文) · [English](#english)

## 中文

v1.1.1 是面向 M5Stack Cardputer ADV 的默认体验更新。

### 本版变化

- 全新安装后，占卜牌库默认使用完整 78 张，而不是仅 22 张大牌
- 全新安装后，牌意详细度默认使用“完整”，而不是“简约”
- 简约牌意和仅大牌模式仍保留，可随时在设置中切换
- 已经保存在 NVS 中的用户选择仍会被尊重；只有没有有效设置的全新安装使用新默认值
- No-SD 固件继续内嵌全部 78 张正位牌面和牌背，不插 microSD 也可完整使用

M5Burner 合并镜像从 `0x0` 写入并会清除旧 NVS，因此通过 M5Burner 全新安装
v1.1.1 后会直接看到“完整 78 张 + 完整牌意”的新默认体验。

### 下载

- `ADV-Tarot-Cardputer-ADV-v1.1.1-NoSD-M5Burner.bin`
  - bootloader、8MB 单应用分区表和应用的完整合并镜像
  - M5Burner / esptool 写入地址：`0x0`
- `ADV-Tarot-v1.1.1-Optional-SD-Assets.zip`
  - 可选 157 张透明 PNG、157 张兼容 JPEG 与说明文件
- `SHA256SUMS.txt`

## English

v1.1.1 updates the first-run experience for M5Stack Cardputer ADV.

### Changes

- Fresh installations now default to the complete 78-card reading deck
- Fresh installations now default to complete interpretations instead of concise text
- Major-only and concise modes remain available in Settings
- Existing valid NVS preferences are respected; the new defaults apply only when no saved settings exist
- The No-SD build still embeds all 78 upright faces and the card back

The merged M5Burner image is written at `0x0` and clears old NVS data, so a fresh
M5Burner installation starts directly with the complete deck and complete text.

### Downloads

- `ADV-Tarot-Cardputer-ADV-v1.1.1-NoSD-M5Burner.bin`
  - Complete bootloader, 8MB single-app partition table, and application image
  - M5Burner / esptool offset: `0x0`
- `ADV-Tarot-v1.1.1-Optional-SD-Assets.zip`
  - Optional 157 transparent PNG files, 157 compatible JPEG files, and notices
- `SHA256SUMS.txt`

Full guide:
<https://lyzbn.github.io/ADV-Tarot-Firmware/>
