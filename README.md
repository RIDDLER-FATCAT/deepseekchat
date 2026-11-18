# 📱 DeepSeek Api Chat Mobile (非官方 Android 客户端)

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-green.svg" alt="Platform">
  <img src="https://img.shields.io/badge/Framework-Capacitor-blue.svg" alt="Capacitor">
  <img src="https://img.shields.io/badge/Base-DeepSeek_Web-orange.svg" alt="DeepSeek">
  <img src="https://img.shields.io/badge/License-MIT-purple.svg" alt="License">
</p>

> 本项目是基于 [DeepSeek 官方 chat-demo](https://github.com/deepseek-ai/chat-demo) 网页端，通过 [Capacitor](https://capacitorjs.com/) 技术封装而成的 Android App。

本项目旨在提供一个简洁、安全、无广告的deepseek api全家桶套壳方案，方便用户在 Android 手机上获得接近原生的对话体验。

---

## ✨ 核心特性

- 🚀 **无缝集成**：完美还原官方网页端的流式输出、Markdown 渲染及代码高亮体验。
- 🔒 **隐私安全**：纯本地运行，你的 API Key 仅保存在手机本地（LocalStorage/IndexedDB），不经过任何第三方服务器。
- 🪶 **极致轻量**：不包含任何多余的 SDK 和追踪代码，安装包体积小巧。
- 🎨 **自适应 UI**：支持系统深色模式，适配手机屏幕比例与键盘弹出交互。

---

## 🏗️ 项目架构

本项目主要由两部分组成：
1. **Web 层**：DeepSeek 官方开源的静态网页构建产物（存放于 `www/` 目录）。
2. **Native 层**：由 Capacitor 生成的 Android 原生工程（存放于 `android/` 目录），提供 WebView 容器及系统权限支持。

---
## 🚀正式版1.0
请前往https://github.com/RIDDLER-FATCAT/deepseekchat/releases
---

## 🛠️ 本地开发与编译指南

如果你想自行修改代码（如更改主题、默认 API 地址）或重新编译 APK，请遵循以下步骤。

### 1. 环境准备
在开始之前，请确保你的电脑已安装以下环境：
- [Node.js](https://nodejs.org/) (推荐 v20 或更高版本)
- [Android Studio](https://developer.android.com/studio) (推荐最新稳定版)
- 本地已配置好 **JDK 21** 及 **Android SDK**

### 2. 克隆仓库并安装依赖


# 克隆本项目
```bash
git clone https://github.com/RIDDLER-FATCAT/deepseekchat.git
cd deepseekchat
```

# 安装 Node 依赖
```bash
npm install
```
3. 网页端修改与同步
如果你修改了 www/ 目录下的 HTML/CSS/JS 代码，或者重新拉取了官方最新的网页构建产物，必须执行同步命令，将网页文件推送到安卓工程中：

```bash
npx cap sync android
```
4. 编译 APK
你可以通过两种方式生成安装包：

方式一：命令行编译（推荐）

```bash
cd android
./gradlew assembleDebug
```
生成的 APK 位于：android/app/build/outputs/apk/debug/app-debug.apk


方式二：Android Studio 编译

 自动用 Android Studio 打开项目
```bash
npx cap open android
```
在 Android Studio 中，点击顶部菜单 Build -> Generate App Bundles or APKs -> Generate APKs，等待右下角提示生成成功即可。


❓ 常见问题 (FAQ)
Q: 为什么 App 打开是白屏？
A: 请检查你的网络连接是否正常，或确认 npx cap sync 是否成功执行。如果你使用了代理，请确保代理软件允许该 App 联网。

Q: 为什么提示无法请求 API？
A: 请确保你在 App 的设置中正确填写了 DeepSeek 的 API Key。另外，由于部分国产 ROM 的限制，首次打开可能需要手动授予 App 网络权限。

Q: 为什么提示不支持语音功能？
A: 语音输入需要设备麦克风权限。请检查系统设置是否允许该 App 使用麦克风。

⚠️ 免责声明 (Disclaimer)
非官方声明：本项目为个人开发者基于开源代码独立构建，与 DeepSeek 官方无任何关联。

版权归属：本项目的前端 UI 及核心逻辑版权均归 DeepSeek 官方所有，本项目仅作为 WebView 容器及打包工具。

数据与费用：使用过程中产生的所有数据均保存在本地。调用 DeepSeek API 产生的任何费用，由使用者自行承担。

使用限制：本项目仅供个人学习、技术交流与测试使用，严禁用于任何商业或非法用途。

📄 开源协议
本项目采用 MIT License 协议开源。您可以自由分发、修改，但需保留原作者署名。

<p align="center">Made with ❤️ by riddler</p> 
