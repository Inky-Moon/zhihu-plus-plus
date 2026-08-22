# Zhihu++ (Android 6.0 兼容特别版)

[![GitHub release](https://img.shields.io/github/v/release/Inky-Moon/zhihu-plus-plus)](https://github.com/Inky-Moon/zhihu-plus-plus/releases)

这是 [Zhihu++](https://github.com/zly2006/zhihu-plus-plus) 的一个特别分支版本，**专为运行 Android 6.0 (API 23) 等老旧设备优化和定制**。

我们在原版强大的去广告、防沉迷、本地化推荐功能基础上，对底层依赖进行了深度精简与重构，成功让这款现代化的纯净知乎客户端在十年前的 Android 设备上焕发第二春。

## 特色与修改说明

原版 `Zhihu++` 随着功能迭代，使用了大量仅支持 Android 7.0/8.0 甚至更高版本的新技术库（例如用于高级数学公式排版的 `tiqian-markdown` 引擎、高版本的 WebView 容器、复杂的 AI 离线推理模型等）。这导致老设备在编译和运行时会遭遇严重的 `Manifest Merger` 失败和各种 `NoSuchMethodError` 闪退。

本分支做了以下核心调整以保障极致的向下兼容性：
- **移除高版本 Markdown 引擎**：彻底剥离了要求 API 27 的 `org.tiqian` 排版引擎及其依赖的 `syntaxmp` 等包，在 Android 端回落并修复了本地 `com.hrm.markdown` 轻量级渲染器，确保在旧设备上打开文章和回答时不再闪退。
- **降级高级 WebView 组件**：将 `androidx.webkit` 降级至支持 API 21 的低版本。
- **专注轻量化 Lite 版**：修改了 GitHub Actions 脚本，构建流专注于 `Lite` 版本的打包，剥离 ONNX 离线推理框架和臃肿的桌面端，APK 体积仅需不到 4MB，对老设备内存和存储极度友好。
- **Java 8+ Desugaring**：配置了完整的 API 脱糖（Desugaring）支持，确保现代 Kotlin 特性与新型 Time API 在 Android 6.0 上完美运行。
- **兼容性代码保护**：对应用内通知渠道（NotificationChannel）、音频焦点请求等 Android 8.0+ 的新 API 增加了严格的运行期版本检测和降级处理代码。

## 应用截图

| 首页 | 关注 | 日报 | 个人主页 | 文章 |
| --- | --- | --- | --- | --- |
| ![首页截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/1_home.jpg) | ![关注截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/2_follow.jpg) | ![日报截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/3_daily.jpg) | ![个人主页截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/4_people.jpg) | ![文章截图](fastlane/metadata/android/zh-CN/images/phoneScreenshots/5_article.jpg) |

## 下载

告别官方 110MB+ 的卡顿体验，专为旧手机打造的 Lite APK，不到 4 MB！

[前往 Release 页面下载最新 APK](https://github.com/Inky-Moon/zhihu-plus-plus/releases)

> 开发者提示：当你在代码仓库中推送 `v` 开头的 Tag（例如 `v1.0.0`）时，GitHub Actions 会自动编译并把 APK 发布到 Release 页面。

## 核心功能

* 完整继承了原版 Zhihu++ 的核心阅读与交互功能
* **登录与账号**：手机验证码、扫码、Cookie 登录
* **信息流与推荐**：去广告、去盐选，本地独立推荐算法
* **屏蔽系统**：屏蔽词、用户、话题
* **阅读体验**：回答、文章、想法、专栏、沉浸式阅读、导出 PDF/图片
* **极致性能**：去掉 AI 功能，内存占用极低，老旧手机畅滑无阻

## 致谢

感谢原作者 [zly2006](https://github.com/zly2006/zhihu-plus-plus) 提供的优秀开源项目底座。本分支致力于让这份纯粹的阅读体验惠及更多坚守旧设备的用户。
