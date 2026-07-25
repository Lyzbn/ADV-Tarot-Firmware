# ADV Tarot Firmware v1.1.0 — No-SD / M5Burner

[中文](#中文) · [English](#english)

## 中文

v1.1.0 面向 M5Stack Cardputer ADV，重点是把完整 78 张牌面带进 Flash，让用户
无需准备 microSD 也能获得完整视觉和全部功能。

### 本版变化

- 内嵌 78 张正位 Rider–Waite–Smith JPEG 与蓝底黄星牌背
- 逆位共用同一张内嵌图并在渲染时旋转，不重复占用 Flash
- 无 SD 时设置页明确显示 `FLASH 78/78`
- 有 SD 时仍优先使用 157 张透明 PNG，并保留长期 JSON 占卜归档
- 使用 8MB 单应用大分区，为全部牌面保留空间
- 提供从 `0x0` 烧录的完整合并镜像，适合 M5Burner 一键安装
- 提供可选 SD 资源 zip、牌面许可说明和 SHA-256 校验

### 下载

- `ADV-Tarot-Cardputer-ADV-v1.1.0-NoSD-M5Burner.bin`
  - bootloader、分区表和应用合并为一个文件
  - M5Burner / esptool 写入地址：`0x0`
  - 会清除设备现有 NVS 设置、学习进度与占卜历史
- `ADV-Tarot-v1.1.0-Optional-SD-Assets.zip`
  - 157 张 PNG + 157 张 JPEG
  - 解压后把 `tarot` 文件夹复制到 microSD 根目录
- `SHA256SUMS.txt`

推荐 microSD：8GB–32GB SDHC、Class 10/U1、FAT32、MBR 单分区。SD 是可选项：
不插卡仍有完整 78 张内嵌牌面；插卡后获得透明 PNG 和长期 JSON 归档。

## English

v1.1.0 targets M5Stack Cardputer ADV and moves all 78 card faces into Flash,
so the complete visual experience no longer requires a microSD card.

### Changes

- Embeds all 78 upright Rider–Waite–Smith JPEG faces and the blue/gold card back
- Reversed cards reuse and rotate the upright image instead of duplicating Flash data
- Reports `FLASH 78/78` when running without SD
- Still prefers 157 transparent PNG faces and enables long-term JSON archives when SD is present
- Uses a single large application partition on the 8MB Flash
- Includes a complete offset-`0x0` merged image for one-file M5Burner installation
- Includes an optional SD asset zip, artwork notices, and SHA-256 checksums

### Downloads

- `ADV-Tarot-Cardputer-ADV-v1.1.0-NoSD-M5Burner.bin`
  - Merged bootloader, partition table, and application
  - M5Burner / esptool offset: `0x0`
  - Erases existing NVS settings, learning progress, and reading history
- `ADV-Tarot-v1.1.0-Optional-SD-Assets.zip`
  - 157 PNG + 157 JPEG files
  - Extract the `tarot` folder to the root of the microSD card
- `SHA256SUMS.txt`

Recommended microSD: 8–32GB SDHC, Class 10/U1, FAT32, one MBR partition. SD is
optional: the complete 78-card embedded deck works without it; adding SD enables
transparent PNG art and long-term JSON archives.

Full guide:
<https://lyzbn.github.io/ADV-Tarot-Firmware/>
