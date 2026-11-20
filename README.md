# 主题导入与混搭恢复 · 18 Fold

**HyperOS Theme Import & Mix Restore · libxposed API 102**

包名 / Application ID：`io.github.gkeyes.themeimport`

[下载正式 APK / Releases](https://github.com/Xposed-Modules-Repo/io.github.gkeyes.themeimport/releases) · [维护者 / Maintainer: gkeyes](https://github.com/gkeyes)

## 中文

### 功能与要求

恢复 HyperOS「主题壁纸」原生的本地 MTZ 导入和「混搭」入口，并提供主题商店、主题/壁纸页面及智能助理小组件目录的独立开关。`0.13.0-api102` 新装默认开启全部九个目录开关；已保存的关闭项会保留。

需要 **Android 14+、root，以及支持 libxposed API 102 的 LSPosed 或同类框架**。仅支持旧 API 82 的框架不适用。

适配参考：**18 Fold**，主题壁纸 `80.9.4.0`、智能助理 `25.41.87.00-10301052`。其他机型或应用版本未作兼容保证；未识别的方法或结构会跳过对应适配。

### 使用

1. 安装正式 APK，在 LSPosed 中启用模块。
2. 勾选「主题壁纸」`com.android.thememanager`；使用小组件目录功能时，同时勾选「智能助理」`com.miui.personalassistant`。重启对应应用进程。
3. 在主题壁纸的本地主题列表使用「导入」，在「我的」页使用「混搭」。模块没有桌面图标，目录开关位于 **LSPosed → 本模块 → 模块设置**。
4. 修改目录开关后，重启对应应用进程即可，无需清除应用数据。如果 HyperCeiler 也启用了恢复导入，请关闭其中一种实现，避免重复处理。

### 升级与边界

**旧临时 Debug 包首次迁移到正式签名：只卸载旧的本模块，再安装正式 APK，并重新启用模块及作用域。不要卸载或清除主题壁纸、智能助理的数据。** 后续相同正式签名的版本支持覆盖升级。

智能助理的推荐目录与功能分类可分别切换；推荐请求的手机类型选项需要同时开启推荐目录。目录内容由服务端决定，18 Fold 的手机分类可能只返回时钟、天气所在的一组卡片，不保证内容更多。

模块沿用原应用逻辑，不修改系统 APK、不伪装系统机型，也不绕过购买、授权、尺寸或添加校验。服务直达、导航和系统布局不在修改范围内。本发布面向 18 Fold，不包含 Fold 4 的独立适配版本。

## English

### Features and requirements

Restores HyperOS Theme Manager's native local MTZ import and theme mixing entries. Separate switches control supported theme-store requests, theme/wallpaper pages, and Personal Assistant widget catalogs. All nine catalog switches default to enabled on a fresh installation of `0.13.0-api102`; previously saved disabled choices are preserved.

Requires **Android 14+, root, and an LSPosed-compatible framework supporting libxposed API 102**. Framework builds supporting only legacy API 82 are not supported.

Compatibility references: **18 Fold**, Theme Manager `80.9.4.0`, and Personal Assistant `25.41.87.00-10301052`. Compatibility with other devices or app versions is not guaranteed. Unrecognized methods or structures are skipped.

### Usage

1. Install the release APK and enable the module in LSPosed.
2. Select Theme Manager (`com.android.thememanager`). Also select Personal Assistant (`com.miui.personalassistant`) for its widget catalog features. Restart the affected app processes.
3. Find **Import** in the native local-theme list and **Mix** on the **My/Account** page. There is no launcher icon; open the module settings from LSPosed.
4. Restart the affected app after changing catalog switches. Clearing app data is unnecessary. If HyperCeiler also restores theme import, enable only one implementation.

### Updates and limitations

**One-time migration from an old temporary Debug build: uninstall only this module, install the signed release APK, and re-enable the module and its scope. Do not uninstall Theme Manager or Personal Assistant, or clear their data.** Future releases using the same release certificate support in-place updates.

Personal Assistant's recommendation and category catalogs have separate switches. The recommendation phone-type option also requires the recommendation catalog switch. Catalog contents come from the server; on 18 Fold, the phone category may return only the group containing clock and weather cards. Additional content is not guaranteed.

The module preserves native app behavior. It does not modify system APKs, spoof the system device model, or bypass purchase, licensing, size, or add-item checks. Service shortcuts, navigation, and system layouts are outside its scope. This release targets 18 Fold and does not include the separate Fold 4 adaptation.

## 签名 / Signing certificate

正式 APK 使用固定发布证书。Official releases use the same signing certificate.

SHA-256:

```text
a6d9e7fe757502e17e4198c5fbd4e97d37330e1b7f6a1bf4774919137959d201
```

每个 Release 同时附有 `SHA256SUMS.txt` 和 `SIGNING-CERT-SHA256.txt`，用于核对 APK 文件及签名证书。Each release includes checksums for the APK and its signing certificate.
