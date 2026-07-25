# ADV Tarot Firmware v1.0.0

[中文](#中文) · [English](#english)

## 中文

ADV Tarot 首个公开二进制版本，面向 M5Stack Cardputer ADV。

### 本版内容

- 完整 78 张大、小阿卡纳及 156 组独立正逆位牌意
- 简约与完整牌意模式
- 大牌、权杖、圣杯、宝剑、星币五类独立学习与记忆测试
- 22 张大牌或完整 78 张参与占卜
- 硬件随机完成整副牌洗牌及逐牌正逆位；体感只移动已经形成的牌环
- IMU 倾斜变速、中心牌确认、已选牌移除与三张不重复
- 近大远小牌环、四角透视、动态阴影、柔和高光、水平翻牌与横向全屏
- 四种三牌牌阵，包括“二择 / 核心建议”
- 主题、时间戳、最近 12 次占卜回顾和单条删除
- 完全离线，不使用 Wi-Fi、云端、账号或 API

### 下载文件

- `ADV-Tarot-Cardputer-ADV-v1.0.0-factory.bin`
  - 首次安装或完整重装
  - 写入地址 `0x0`
  - 会清除现有设置、学习进度和占卜记录
- `ADV-Tarot-Cardputer-ADV-v1.0.0-update.bin`
  - 仅用于已经安装 ADV Tarot 的设备
  - 写入地址 `0x10000`
  - 通常保留 NVS 数据
- `SHA256SUMS.txt`
  - 下载完整性校验

### microSD

本次 Release 只包含固件，不包含 microSD 图片资源包。无 SD 时所有功能仍可运行，
22 张大牌及牌背使用内嵌图；56 张小牌显示安全占位牌。完整 78 张高清牌面及
长期 JSON 档案需要另行准备 microSD 资源。

完整介绍和安装命令：
<https://lyzbn.github.io/ADV-Tarot-Firmware/>

## English

The first public binary release of ADV Tarot for M5Stack Cardputer ADV.

### Included

- All 78 Major and Minor Arcana cards with 156 distinct upright/reversed entries
- Concise and complete interpretation modes
- Separate study and recall paths for Major Arcana, Wands, Cups, Swords, and Pentacles
- Readings using either 22 Major Arcana cards or the complete 78-card deck
- One hardware-random full-deck shuffle and independent orientation per card;
  motion moves the established ring instead of rerolling it
- IMU-controlled direction and speed, centered-card confirmation, selected-card
  removal, and non-repeating three-card results
- Depth-scaled ring, four-corner perspective, dynamic shadows, soft highlights,
  horizontal reveal, and landscape full-card view
- Four three-card spreads, including Choice A / Choice B / Core Guidance
- Reading titles, timestamps, review, and individual deletion for the latest 12 entries
- Fully offline operation with no Wi-Fi, cloud service, account, or API

### Assets

- `ADV-Tarot-Cardputer-ADV-v1.0.0-factory.bin`
  - First installation or full reinstall
  - Flash at `0x0`
  - Erases settings, learning progress, and reading history
- `ADV-Tarot-Cardputer-ADV-v1.0.0-update.bin`
  - Only for devices already running ADV Tarot
  - Flash at `0x10000`
  - Normally preserves NVS data
- `SHA256SUMS.txt`
  - Download integrity checks

### microSD

This Release contains firmware only and does not include the microSD artwork
pack. All functions remain available without SD; the 22 Major Arcana faces and
card back are embedded, while the 56 Minor Arcana cards use safe placeholders.
The complete 78-card high-resolution artwork and long-term JSON archive require
separately prepared microSD assets.

Full product page and installation commands:
<https://lyzbn.github.io/ADV-Tarot-Firmware/en/>

## Compatibility

- M5Stack Cardputer ADV
- Stamp-S3A / ESP32-S3FN8
- ST7789V2 240 × 135 display

This is an independent project and is not affiliated with or endorsed by
M5Stack. Tarot content is intended for study, journaling, and personal
reflection and is not professional advice.

