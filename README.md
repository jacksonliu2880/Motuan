<div align="center">

<img src="motuan-icon.png" width="150" alt="墨团 Motuan">

# 墨团 · Motuan

### 你的 Codex 桌面状态伙伴

**把 Codex 状态留在桌面，把进度送到飞书。**

一只会读懂 Codex 额度与任务进度的桌面宠物。  
六种状态表情、实时额度显示、任务追踪、飞书自动汇报与双向指令——安静常驻，随时可见。

<p>
  <a href="Motuan-Beta-Setup.exe">
    <img src="https://img.shields.io/badge/Windows-下载安装-087CD5?style=for-the-badge&logo=windows11&logoColor=white" alt="下载 Windows 版">
  </a>
  &nbsp;
  <a href="Motuan-Beta-Setup.dmg">
    <img src="https://img.shields.io/badge/macOS-下载安装-111111?style=for-the-badge&logo=apple&logoColor=white" alt="下载 macOS 版">
  </a>
</p>

<p>
  <img src="https://img.shields.io/badge/版本-v0.2.0--beta-7C3AED?style=flat-square" alt="版本">
  <img src="https://img.shields.io/badge/Codex-Desktop%20%7C%20CLI%20%7C%20VS%20Code-16C7C7?style=flat-square" alt="Codex 支持">
  <img src="https://img.shields.io/badge/飞书-自动汇报%20%2B%20双向指令-3370FF?style=flat-square" alt="飞书联动">
  <img src="https://img.shields.io/badge/内测期限-2026.09.30-F59E0B?style=flat-square" alt="内测期限">
</p>

<p>
  <a href="#核心能力">核心能力</a>
  ·
  <a href="#下载安装">下载安装</a>
  ·
  <a href="#飞书联动">飞书联动</a>
  ·
  <a href="#安全与隐私">安全与隐私</a>
  ·
  <a href="SHA256.txt">SHA256 校验</a>
</p>

<img src="motuan-poster.png" width="920" alt="墨团产品海报">

</div>

---

## 核心能力

| 桌面状态感知 | Codex 全端识别 | 飞书实时联动 |
|---|---|---|
| 无边框透明桌宠，可拖动、隐藏并选择始终置顶 | 自动发现 Codex 桌面版、CLI 和 VS Code 官方插件的本机数据 | 自动汇报额度、任务开始、进度、完成与异常 |
| 像素字体实时显示剩余额度 | 显示额度、预计重置时间、任务状态和估算进度 | 支持从飞书查询状态并控制桌宠 |
| 根据额度变化自动切换六种表情 | 换电脑后自动识别新电脑上的 Codex 数据 | 运行电脑不需要安装飞书客户端 |

### 六种状态，一眼看懂

墨团会根据 Codex 剩余额度自动切换状态：

| 剩余额度 | 墨团状态 |
|---:|---|
| 85% 及以上 | 开心 |
| 65%–84% | 平静 |
| 45%–64% | 担心 |
| 25%–44% | 疲惫 |
| 低于 25% | 警觉 |
| 暂无额度数据 | 休眠 |

### 更聪明的汇报策略

- 默认每 5 分钟评估一次是否需要向飞书汇报。
- 任务进度跨过 5% 档位时发送进度更新。
- Codex 剩余额度每下降 5% 汇报一次。
- 任务开始、完成、失败及低额度预警会即时汇报。
- 检查间隔、进度档位、额度档位和预警线均可在设置中调整。

## 下载安装

| 平台 | 安装包 | 支持范围 |
|---|---|---|
| Windows | **[Motuan-Beta-Setup.exe](Motuan-Beta-Setup.exe)** | Windows 10/11 x64 |
| macOS | **[Motuan-Beta-Setup.dmg](Motuan-Beta-Setup.dmg)** | Apple Silicon，M 系列芯片 |

> GitHub 文件页面不会直接预览大型安装包。打开文件后，点击右上角的 **Download raw file** 即可下载。

### Windows

1. 下载并双击 `Motuan-Beta-Setup.exe`。
2. 自行选择安装目录并完成安装。
3. 首次启动后，墨团会自动查找当前 Windows 用户的 Codex 数据。
4. 如需飞书联动，在设置页填写机器人配置并保存。

目标电脑无需安装 Python。

### macOS

1. 下载并打开 `Motuan-Beta-Setup.dmg`。
2. 将墨团拖入“应用程序”目录。
3. 首次启动后按系统提示授予必要权限。

当前 macOS 安装包为 Apple Silicon 内测版本。

## 飞书联动

### 自动汇报

在飞书群中添加“自定义机器人”，将 Webhook 粘贴到墨团设置页即可。Webhook 用于墨团向飞书发送消息。

### 双向指令

在飞书开放平台创建企业自建应用机器人，开启消息权限和长连接事件订阅，再将 App ID 与 App Secret 填入墨团，即可从飞书发送：

`状态` · `额度` · `任务` · `刷新` · `显示桌宠` · `隐藏桌宠` · `帮助`

运行墨团的电脑不需要安装飞书客户端。墨团直接连接飞书云端接口，你可以在手机端、网页版或其他电脑上查看消息并发送指令。

## 安全与隐私

- 只读取 Codex 已写入本机的状态文件。
- 不抓屏，不注入 Codex 进程。
- 不读取或上传 Codex 登录令牌。
- 飞书 Webhook 与 App Secret 在 Windows 上使用 DPAPI 加密，只能由当前 Windows 用户在本机解密。
- 换电脑后需要重新填写受本机加密保护的飞书密钥。

## 内测说明

当前公开版本为免费内测版，服务固定截至北京时间 **2026 年 9 月 30 日 23:59**。到期后 Codex 监控、桌宠状态、飞书汇报和双向连接将停止。

## 文件校验

安装包的 SHA256 值记录在 **[SHA256.txt](SHA256.txt)**。

Windows PowerShell：

```powershell
Get-FileHash .\Motuan-Beta-Setup.exe -Algorithm SHA256
```

macOS：

```bash
shasum -a 256 Motuan-Beta-Setup.dmg
```

<div align="center">

---

**MOTUAN · CODEX DESKTOP COMPANION**

Copyright © 2026 Motuan. All rights reserved.

</div>
