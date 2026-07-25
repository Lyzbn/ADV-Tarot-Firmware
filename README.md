# ADV Tarot Firmware

[中文](#中文) · [English](#english) · [产品页面 / Product page](https://lyzbn.github.io/ADV-Tarot-Firmware/) · [下载 / Downloads](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/latest)

> 面向 M5Stack Cardputer ADV 的离线 78 张塔罗学习、记忆与体感选牌固件。  
> Offline 78-card tarot study, recall, and motion-driven selection firmware for M5Stack Cardputer ADV.

## 中文

ADV Tarot 不是“按一下按钮就吐出一张随机牌”。每次占卜开始时，ESP32-S3
硬件随机源会先完成一副 22 或 78 张牌的完整不重复洗牌，并为每张牌独立确定
正逆位。之后，设备倾斜只会移动这副已经形成的环形牌序；按下确认时才锁定
屏幕中央的牌，已选牌会离开牌环，余牌不会重新随机。

### 主要功能

- 78 张大、小阿卡纳，156 组独立正逆位内容
- 简约与完整牌意模式
- 画面分析、牌义推演、感情、事业、学业、财务、身心、核心提示、行动研读、
  牌组旅程、体系对应与资料来源
- 大牌、权杖、圣杯、宝剑、星币五类独立学习与记忆测试
- 22 张大牌或完整 78 张参与占卜
- IMU 倾斜控制牌环方向、速度与停点
- 近大远小、四角透视、动态阴影、柔和高光、翻牌与横向全屏效果
- 四种三牌牌阵，包括“二择 / 核心建议”
- 主题、时间戳、最近 12 次占卜回顾与单条删除
- 离线运行，不需要 Wi-Fi、账号、云端或 API

### microSD 说明

当前公开版只发布固件，不包含 microSD 图片资源包。

- 没有 microSD：所有学习、牌意、体感选牌和占卜功能均可运行；牌背与 22 张
  大牌使用固件内嵌图片，56 张小牌使用安全占位牌。
- 使用完整 microSD 资源：可显示全部 78 张正逆位透明 PNG 高清牌面，并把完整
  占卜记录长期归档为 JSON。

### 安装

请从 [最新 Release](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/latest)
下载：

- `ADV-Tarot-Cardputer-ADV-v1.0.0-factory.bin`：首次安装，写入地址 `0x0`；
  会清除原有设置和占卜记录。
- `ADV-Tarot-Cardputer-ADV-v1.0.0-update.bin`：仅用于已经安装 ADV Tarot
  的设备，写入地址 `0x10000`，通常保留 NVS 设置与历史。
- `SHA256SUMS.txt`：文件完整性校验。

安装命令和进入下载模式的方法见
[中文安装说明](https://lyzbn.github.io/ADV-Tarot-Firmware/#install)。

## English

ADV Tarot is not a button that simply returns a newly randomized card. At the
start of a reading, the ESP32-S3 hardware random source shuffles the selected
22- or 78-card deck into one complete, non-repeating order and independently
assigns every card an upright or reversed orientation. Tilting then moves that
already established ring. A card is locked only when you confirm it; selected
cards leave the ring and the remaining deck is not rerolled.

### Highlights

- All 78 Major and Minor Arcana cards, with 156 distinct upright/reversed entries
- Concise and complete interpretation modes
- Visual analysis, interpretive development, relationships, career, study,
  finances, wellbeing, core guidance, practical reflection, deck journey,
  correspondences, and referenced sources
- Separate study and recall modes for Major Arcana, Wands, Cups, Swords, and Pentacles
- Readings with either 22 Major Arcana cards or the complete 78-card deck
- IMU-controlled deck direction, speed, and resting point
- Depth-scaled card ring, four-corner perspective, dynamic shadows, soft
  highlights, flip reveal, and landscape full-card view
- Four three-card spreads, including Choice A / Choice B / Core Guidance
- Reading titles, timestamps, review, and individual deletion for the latest 12 entries
- Fully offline operation with no Wi-Fi, account, cloud service, or API

### microSD

This initial public release contains firmware only and does not include the
microSD artwork pack.

- Without microSD: study, interpretations, motion selection, and readings remain
  functional. The card back and 22 Major Arcana faces are embedded; the 56 Minor
  Arcana cards use safe placeholders.
- With the complete microSD assets: all 78 upright/reversed transparent PNG card
  faces are available, and completed readings can be archived as JSON.

### Installation

Download the files from the
[latest Release](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/latest):

- `ADV-Tarot-Cardputer-ADV-v1.0.0-factory.bin`: first installation at `0x0`;
  existing settings and reading history are erased.
- `ADV-Tarot-Cardputer-ADV-v1.0.0-update.bin`: for devices already running
  ADV Tarot, written at `0x10000`; NVS settings and history are normally preserved.
- `SHA256SUMS.txt`: file integrity checks.

See the [English installation guide](https://lyzbn.github.io/ADV-Tarot-Firmware/en/#install).

## Compatibility and notice

- Target hardware: **M5Stack Cardputer ADV / Stamp-S3A / ESP32-S3FN8**
- Display: **ST7789V2, 240 × 135**
- This is an independent project and is not affiliated with or endorsed by M5Stack.
- Tarot content is provided for study, journaling, and personal reflection. It is
  not medical, legal, financial, or other professional advice.
- The firmware is proprietary binary software. See
  [LICENSE-FIRMWARE.md](LICENSE-FIRMWARE.md).
- Third-party components and public-domain artwork remain under their respective
  terms. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

