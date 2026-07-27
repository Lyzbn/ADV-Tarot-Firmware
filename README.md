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
- 全新安装默认启用完整 78 张占卜牌库和完整牌意
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

v1.1.2 是完整的 No-SD 版本，并同时提供可选 SD 资源包。

- 没有 microSD：78 张正位 JPEG 与牌背全部内嵌，逆位实时旋转；所有学习、
  牌意、体感选牌、牌阵和最近 12 次记录均可使用。
- 使用可选 microSD 资源：自动优先显示全部 78 张正逆位透明 PNG，并把完整
  占卜记录长期归档为 JSON。
- 推荐 microSD：8GB–32GB SDHC、Class 10/U1、FAT32、MBR 单分区。

### 安装

请从 [最新 Release](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/latest)
下载：

- `ADV-Tarot-Cardputer-ADV-v1.1.2-NoSD-M5Burner.bin`：完整合并镜像，
  可直接用于 M5Burner，写入地址 `0x0`；会清除原有设置、学习进度和占卜记录。
- `ADV-Tarot-v1.1.2-Optional-SD-Assets.zip`：可选透明 PNG/JPEG 资源包；
  解压后把 `tarot` 文件夹复制到 FAT32 microSD 根目录。
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
- Fresh installations default to the full 78-card reading deck and complete interpretations
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

v1.1.2 is a complete No-SD build and also offers an optional SD asset pack.

- Without microSD: all 78 upright JPEG faces and the card back are embedded;
  reversed cards are rotated at render time. Study, interpretations, motion
  selection, spreads, and the latest 12 readings remain available.
- With the optional microSD assets: all 78 upright/reversed transparent PNG
  faces are preferred, and completed readings can be archived as JSON.
- Recommended card: 8–32GB SDHC, Class 10/U1, FAT32, single MBR partition.

### Installation

Download the files from the
[latest Release](https://github.com/Lyzbn/ADV-Tarot-Firmware/releases/latest):

- `ADV-Tarot-Cardputer-ADV-v1.1.2-NoSD-M5Burner.bin`: complete merged image for
  M5Burner or flashing at `0x0`; existing settings, learning progress, and
  reading history are erased.
- `ADV-Tarot-v1.1.2-Optional-SD-Assets.zip`: optional transparent PNG/JPEG
  assets; extract the `tarot` folder to the root of a FAT32 microSD card.
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
