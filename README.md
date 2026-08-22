# Zhihu++ (Android 6.0 Lite 版)

[![GitHub release](https://img.shields.io/github/v/release/Inky-Moon/zhihu-plus-plus)](https://github.com/Inky-Moon/zhihu-plus-plus/releases)

这是 [Zhihu++](https://github.com/zly2006/zhihu-plus-plus) 的一个极简分支版本，**专为 Android 6.0 (API 23) 等老旧设备打造**。保留了核心的纯净阅读体验，去除了所有臃肿依赖，APK 体积不到 4MB。

## 做了哪些精简？

- **兼容旧设备**：移除不兼容旧系统的高级 Markdown 引擎 (`tiqian`) 和高版本 WebView，回落至轻量级本地渲染器，彻底解决低版本安卓闪退问题。
- **极致瘦身**：移除本地 AI 过滤模型（ONNX）与桌面端依赖，专注轻量化 Android 打包。
- **全方位适配**：开启 API 脱糖（Desugaring），针对 Android 8.0+ 的新特性（通知渠道、音频焦点等）增加严格的降级保护。

## 应用截图

| 首页 | 关注 | 日报 | 个人主页 | 文章 |
| --- | --- | --- | --- | --- |
| ![首页截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/1_home.jpg) | ![关注截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/2_follow.jpg) | ![日报截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/3_daily.jpg) | ![个人主页截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/4_people.jpg) | ![文章截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/5_article.jpg) |

## 下载

[👉 点击这里前往 Release 页面下载最新版 APK](https://github.com/Inky-Moon/zhihu-plus-plus/releases)

> 提示：在代码仓库中推送 `v` 开头的 Tag（例如 `v1.0.0`），GitHub Actions 就会自动编译并发布。

## 致谢

感谢原作者 [zly2006](https://github.com/zly2006/zhihu-plus-plus) 提供的优秀开源项目底座。
