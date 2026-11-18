# Windows 桌面版

Windows x64 使用 Electron + NSIS 生成可交互安装程序。Windows 包不构建 DSH 案件助理的运行时依赖，助理入口会隐藏；案件台账、期限、待办、费用与文件功能保留。可选的快录模型入口仍按原配置工作。

## 直接下载（推荐）

已发布的 Windows 安装包：

- **[anqi-2.12.9-windows-x64.exe](https://github.com/echo0102/anqi/releases/download/v2.12.9/anqi-2.12.9-windows-x64.exe)**（Windows 10/11 x64）
- 全部版本：[Releases](https://github.com/echo0102/anqi/releases)

## 在 Windows 上构建

需要 Windows 10/11 x64、Node.js 22 和 npm。克隆仓库后，在项目根目录运行：

```powershell
npm ci
npm run dist:win
```

安装包输出在 `dist-electron/`，文件名形如 `anqi-2.12.9-windows-x64.exe`。`dist:win` 会先为当前 Electron 版本重建 `better-sqlite3` 原生模块，再生成 NSIS 安装程序。

也可以在 GitHub Actions 页面手动运行 **Windows build** 工作流，完成后下载 `anqi-windows-x64` artifact。

Windows 构建不启用 macOS 的 Swift OCR helper。包含文字层的 PDF 仍可读取；图片 OCR 能力取决于系统或外接模型配置。
