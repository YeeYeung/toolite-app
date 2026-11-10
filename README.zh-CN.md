# 徒轻 TooLite

[English](README.md) | [简体中文](README.zh-CN.md)

原生 iOS 徒步装备清单。建好清单，每趟行程的基重、穿着和消耗品一眼看清。一条链接把 LighterPack 清单搬过来，清单还能生成带二维码的图片分享出去。无账号、无广告、不订阅。

<p>
  <a href="https://toolite.win"><img src="badges/website-zh.svg" height="48" alt="访问官网：toolite.win"></a>
</p>

## 技术栈

| | |
|---|---|
| 语言 | Swift 6 |
| 界面 | SwiftUI，iOS 17 起 |
| 数据 | SwiftData；iCloud 同步走用户自己的 CloudKit 私有库 |
| 付费 | StoreKit 2：一次付清，不订阅 |
| 分享 | Core Image 生成二维码，Vision 从相册图片里识别还原 |
| 天气 | WeatherKit 行程预报 |
| 语言 | 英文、简体中文 |

## 工程要点

- 整份清单装在二维码里：紧凑二进制、zlib 压缩，再以 base64url 放进链接的片段部分。31 件装备的清单约 780 个字符，不上传任何数据。
- 分享图经得起聊天软件压缩：二维码的尺寸和纠错等级按微信的图片压缩实测选定。
- 重量算法沿用 LighterPack：基重等于总重减去穿着和消耗品，穿着的装备不论数量只算一件。算出来的数和网页上一致。
- 支持从 LighterPack 分享链接或 CSV 导入，也能导出成同样格式的 CSV。

## 隐私

- 无账号、无统计、无广告。
- 清单存在设备上；开启同步后，存在用户自己的 iCloud 私有库。
- [隐私政策](https://toolite.win/privacy/)
