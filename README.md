<p align="center">
  <img src="motuan-icon.png" width="128" alt="墨团图标">
</p>

<h1 align="center">墨团 Motuan</h1>

<p align="center">
  把 Codex 状态留在桌面，把进度送到飞书。
</p>

<p align="center">
  <a href="Motuan-Beta-Setup.exe">下载 Windows 版</a>
  ·
  <a href="Motuan-Beta-Setup.dmg">下载 macOS 版</a>
  ·
  <a href="SHA256.txt">查看文件校验值</a>
</p>

![墨团产品海报](motuan-poster.png)

## 墨团是什么

墨团是一只常驻桌面的 Codex 状态桌宠。它会读取 Codex 写入本机的状态数据，以像素剩余额度和六种表情展示当前状态，并根据任务进度与额度变化向飞书汇报。

软件只读取本机状态文件，不抓屏、不注入 Codex 进程，也不会读取或上传 Codex 登录令牌。

## 主要功能

- 无边框透明桌宠，可拖动、隐藏，并可选择始终置顶。
- 根据 Codex 剩余额度自动切换六种状态表情。
- 显示剩余额度、预计重置时间、当前任务状态和估算进度。
- 自动识别 Codex 桌面版、Codex CLI 和 VS Code 官方 Codex 插件的本机数据。
- 支持飞书自定义机器人 Webhook，自动汇报任务开始、完成、失败、进度和额度变化。
- 支持飞书应用机器人长连接，可从飞书发送“状态、额度、任务、刷新、显示桌宠、隐藏桌宠、帮助”等指令。
- 支持系统托盘、开机自启和后台运行。
- 默认每 5 分钟评估是否汇报，任务进度或额度跨过 5% 档位时发送更新；可在设置中调整。

运行墨团的电脑不需要安装飞书客户端。墨团直接连接飞书云端接口，消息可在手机端、网页版或其他电脑上查看。

## 下载

| 系统 | 安装包 | 说明 |
|---|---|---|
| Windows 10/11 x64 | [Motuan-Beta-Setup.exe](Motuan-Beta-Setup.exe) | 图形化安装，可自行选择安装位置 |
| macOS Apple Silicon | [Motuan-Beta-Setup.dmg](Motuan-Beta-Setup.dmg) | 适用于 arm64（M 系列芯片）的内测版本 |

如果浏览器没有直接下载，请打开对应目录，再点击文件页面右上角的下载按钮。

## Windows 安装

1. 下载并双击 `Motuan-Beta-Setup.exe`。
2. 选择安装目录并完成安装。
3. 首次启动后，墨团会自动查找当前 Windows 用户的 Codex 数据。
4. 如需飞书联动，在设置页填写飞书机器人配置并保存。

目标电脑不需要另外安装 Python。

## macOS 安装

1. 下载并打开 `Motuan-Beta-Setup.dmg`。
2. 将墨团拖入“应用程序”目录。
3. 首次启动后按系统提示授予必要权限。

当前 macOS 安装包为 Apple Silicon 内测版本。

## 飞书联动

### 自动汇报

在飞书群中添加“自定义机器人”，把 Webhook 粘贴到墨团设置页即可。Webhook 只用于墨团向飞书发送消息。

### 双向指令

双向通信需要在飞书开放平台创建企业自建应用机器人，开启消息权限和长连接事件订阅，再把 App ID 与 App Secret 填入墨团。

## 内测期限

当前公开版本为免费内测版，服务固定截至北京时间 **2026 年 9 月 30 日 23:59**。到期后 Codex 监控、桌宠状态、飞书汇报和双向连接将停止。

## 文件校验

下载后可用 [SHA256.txt](SHA256.txt) 核验安装包是否完整。

Windows PowerShell 示例：

```powershell
Get-FileHash .\Motuan-Beta-Setup.exe -Algorithm SHA256
```

macOS 终端示例：

```bash
shasum -a 256 Motuan-Beta-Setup.dmg
```

## 支持范围

- Windows 10/11 x64
- macOS Apple Silicon（M 系列芯片）
- Codex 桌面版
- Codex CLI
- VS Code 官方 Codex 插件
- 飞书自定义机器人 Webhook
- 飞书应用机器人长连接

---

Copyright © 2026 Motuan. All rights reserved.
