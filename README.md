# 智慧农业 Android 壳（APK）

WebView 在线壳：加载北京服务器 `http://62.234.223.89:8080/`，逻辑全在远端网页。

## 功能
- 全屏 WebView，无地址栏
- 网页图片上传自动调起系统相册（单/多选）
- 返回键 = 网页后退
- 明文 HTTP 允许（`usesCleartextTraffic` + mixed mode）
- UA 追加 `SmartAgriApp/2.0` 标识

## 编译
GitHub Actions 自动：push 到 main → `gradle assembleDebug` → APK 挂到 Release `apk-v2.0`。

## 安装
下载 `smartagri-v2.0-debug.apk` 到手机 → 点击安装（需允许「未知来源/安装未知应用」）。
debug 自签包，仅自用，不上架商店。

## 工程
- 零第三方依赖（无 AndroidX），`minSdk 24`（Android 7.0+），`targetSdk 34`
- `MainActivity.java`：WebView + onShowFileChooser + onBackPressed
