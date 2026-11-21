# AI Hub · iOS 16+

GUJIU 的闭源 iPhone AI 客户端工程。源码无第三方包依赖，使用 SwiftUI、URLSession、Keychain 与 BackgroundTasks。

## 已实现的代码

- 聊天首页，默认跟随系统外观；模型 Logo 随当前选择更新。
- 自定义多个独立模型：名称、模型 ID、接口地址、接口协议、可选密钥和图标。
- 三种明确的请求适配：OpenAI 兼容 Chat Completions、Anthropic Messages、Google Gemini generateContent。模型 ID 可自定义，服务端必须符合所选协议；这不是对所有厂商私有协议的兼容保证。
- 从 OpenRouter 公共目录发现文本聊天免费变体，要求当前报告的输入、输出及附加价格均为零。推理使用用户自己的 OpenRouter Key；发送前重新核验目录，并限定零输入/输出价格路由，无付费模型回退。
- 每隔 24 小时前台补刷新、手动刷新、iOS 最佳努力后台刷新，失败保留上次缓存。iOS 不保证每天固定时间运行。
- 密钥仅写设备钥匙串；普通模型信息和目录缓存写本地文件。没有内置共享 Key。
- 开发者资料与 GUJIU 字母头像：邮箱 gujiu520@proton.me，QQ 401738182，微信 V909800。

## 在 Mac 构建 IPA

安装完整 Xcode 和 iOS SDK 后，在此目录运行：

```sh
bash build-ipa.sh
```

成功后生成 `build/AIHub-1.0.0-arm64-unsigned.ipa`。脚本会先真正编译 iPhone arm64 可执行程序，再验证架构与归档结构。该包没有 Apple 分发签名，安装方式和系统支持以 TrollStore 官方项目为准。

## GitHub Actions

工程根目录的 `.github/workflows/build-ipa.yml` 可手动触发，使用 macOS runner，成功后上传 `AIHub-IPA` artifact。源码和工作流应放在私有仓库；不用在仓库或 Actions Secrets 中保存 API Key，密钥由用户在手机内填写。

当前会话为了通过浏览器上传保留目录结构，将完整工程封装成 `AIHub-iOS-source.zip`，仓库根目录工作流会先解压再编译。这和把源码直接放在仓库中使用同一套 Xcode 构建命令。

## 验证范围

工程最初在 Windows 编写，进行了静态交叉检查和目录规则/交互测试。本地没有 Xcode；是否编译通过，以云端 Actions 的实际结果为准。尚未进行真实 API Key 推理、iPhone 真机安装及后台刷新实测。

## 官方参考

- OpenRouter 模型列表：https://openrouter.ai/docs/api/api-reference/models/list-all-models-and-their-properties
- 免费模型与账户限制：https://openrouter.ai/collections/free-models/
- iOS 后台调度说明：https://developer.apple.com/documentation/backgroundtasks/bgtaskrequest/earliestbegindate
- TrollStore：https://github.com/opa334/TrollStore

Copyright © 2026 GUJIU. All rights reserved.
