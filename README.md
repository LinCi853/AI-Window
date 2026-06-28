# AI 窗口 (AI Window)

桌面多 AI 聚合工具，全局热键一键呼出，支持自定义网页挂载，配合后台语音输入不打断工作流。

## 功能特性

### 全局热键体系
- `Alt+Space`：主窗口一键呼出/隐藏
- `Alt+Q`：划词提问（选中文字后按下，自动填入当前网页）
- `Alt+V`：后台语音输入（不呼窗，直接转写后发送到后台）
- `Alt+Shift+P`：固定/取消置顶
- `Alt+Shift+M`：静音切换

### 后台语音输入
基于 whisper.cpp 本地语音识别，实现「不呼窗、直接问」的后台语音体验。
- 全程离线：语音识别在本地完成，不经过云端
- 后台运行：按下 Alt+V 直接说话，松开自动转写并发送
- 不打断：无需切窗、无需点按麦克风，保持当前工作流
- 预览反馈：识别结果通过预览窗短暂展示，自动隐藏

### 四态窗口系统
- 全屏态：沉浸式深度对话
- 侧边态：贴靠屏幕边缘，边写边问
- 预览态：小型悬浮窗，仅显示最后一条回复
- 隐藏态：后台静默运行，通过语音和热键交互

### 多网页挂载
采用 webview 原生挂载方式，支持添加任意自定义网页。
- 支持自定义网页 URL，灵活扩展
- visibility 切换，保留页面状态不重建
- 多标签页并行，独立登录态隔离
- 内置常用 AI 平台快捷入口

## 系统要求

当前 v0.1.0 版本支持：
- Windows 10 1903 及以上

后续规划支持：
- macOS 11 及以上
- Linux（Ubuntu 22.04 及以上）
- 移动端体验

## 下载

前往 [GitHub Releases](https://github.com/LinCi853/AI-Window/releases) 下载最新版本。

- **安装版**：NSIS 安装程序，推荐大多数用户使用
- **便携版**：绿色免安装，解压即用，数据存 exe 同级目录

## 首次使用

1. 安装或解压后启动应用
2. 授权键盘监听和麦克风权限
3. 按下 `Alt+Space` 呼出主窗口
4. 按下 `Alt+V` 体验后台语音输入

## 数据存储

- 安装版：数据存储在系统用户目录的 app 数据文件夹
- 便携版：数据存储在 exe 同级的 `data/` 目录
- 所有对话数据均在本地，可随时导出或清空

## 技术栈

- 框架：Electron 30 + React 18 + TypeScript
- 构建：electron-vite + electron-builder
- 状态管理：Zustand
- 本地存储：better-sqlite3
- 语音识别：whisper.cpp
- 网络请求：undici（SSE 流式支持）

## 开发

### 安装依赖

```bash
npm install
```

### 开发模式

```bash
npm run dev
```

### 构建

```bash
# Windows 安装版 + 便携版
npm run build:win-all

# 仅安装版
npm run build:win

# 仅便携版
npm run build:portable
```

## 许可证

MIT
