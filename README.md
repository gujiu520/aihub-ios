# AIJIU · iOS + Android

![AIJIU](AIJIU-icon-preview.png)

GUJIU 的闭源 AI 客户端，版本1.1。原 AI Hub 更名为 AIJIU，采用原创 A/J 交叠标识。

- **iOS 16+**：原生 SwiftUI，IPA 用于兼容设备安装；保留原 bundle 与 Keychain 标识，以支持原配置延续。
- **Android 8+**：原生 Java，提供测试签名 APK。
- 聊天首页、模型 Logo 联动、默认跟随系统外观、多模型自定义配置、三种 API 协议、设备安全存储密钥。
- 每日检查 OpenRouter 免费目录，支持手动刷新与缓存；系统后台执行时间不保证准点。
- 推荐旗舰：DeepSeek V4 Pro、Qwen3.8-Max、GLM-5.3，均为需要个人 Key 的按量模型。
- 国内免费 API 预设：GLM-4.7-Flash、GLM-4.6V-Flash，按2026-11-21官方价格核实，仍需个人 Key，额度与可用性以官方为准。
- “免 Key 官方体验”通过外部浏览器打开 DeepSeek、千问、智谱清言官方网站，可能需要登录；与 App 内 API 聊天独立。

## 构建

`AIJIU-source.zip` 包含完整原生 iOS、Android 工程。私有仓库工作流 **Build AIJIU iOS and Android** 解压后分别在 macOS 和 Ubuntu 编译，生成 `AIJIU-iOS-IPA` 与 `AIJIU-Android-APK` 构建产物。

不用把 API Key 写进代码或 GitHub Secrets，用户在手机 App 内自行配置。没有内置共享 Key，也没有将付费模型伪装为免费。

GUJIU · gujiu520@proton.me · QQ 401738182 · 微信 V909800

Copyright © 2026 GUJIU. All rights reserved.
