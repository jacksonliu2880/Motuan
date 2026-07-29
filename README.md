<div align="center">

<img src="motuan-poster.png" width="100%" alt="墨团公开内测版">

<br>

### 墨团 · 公开内测

把 Codex 状态留在桌面，把进度送到飞书。

<br>

<a href="Motuan-Beta-Setup.exe?raw=1">
  <img src="https://img.shields.io/badge/Windows-下载内测版-1473E6?style=for-the-badge&logo=windows11&logoColor=white" alt="下载 Windows 内测版">
</a>
&nbsp;&nbsp;
<a href="Motuan-Beta-Setup.dmg?raw=1">
  <img src="https://img.shields.io/badge/macOS-下载内测版-111827?style=for-the-badge&logo=apple&logoColor=white" alt="下载 macOS 内测版">
</a>

<br><br>

![公开内测](https://img.shields.io/badge/公开内测-v0.2.0--beta-22C55E?style=flat-square)
![Codex](https://img.shields.io/badge/Codex-Desktop%20%C2%B7%20CLI%20%C2%B7%20VS%20Code-06B6D4?style=flat-square)
![飞书](https://img.shields.io/badge/飞书-自动汇报%20%C2%B7%20双向查询-3370FF?style=flat-square)
![内测期限](https://img.shields.io/badge/内测期限-2026.09.30-F59E0B?style=flat-square)

</div>

<br>

## 让 Codex 的状态，主动来到你面前

墨团是一款为 Codex 用户打造的桌面状态伙伴。

它把原本藏在 Codex 窗口里的剩余额度、任务进度和运行状态，变成桌面上随时可见的“小墨团”；当重要变化发生时，还能主动把消息送到飞书。你不必反复切换窗口，也不必守在电脑旁等待任务结束。

> **看得见状态，等得到结果，离开电脑也不会错过进度。**

<br>

## 内测版能做什么

### 01 · 桌面状态伙伴

无边框透明桌宠常驻桌面，可自由拖动、隐藏或保持置顶。剩余额度以像素数字显示，小墨团会根据额度区间切换不同表情。

### 02 · Codex 自动识别

支持 **Codex Desktop、Codex CLI 和 VS Code Codex 插件**。墨团从本机只读状态数据中识别额度、任务与运行变化，不需要手动录入。

### 03 · 重要进度主动汇报

默认每 5 分钟检查一次状态，并结合额度变化、任务进度与关键事件决定是否汇报。额度重置、任务完成、失败和低额度预警会及时送达。

### 04 · 飞书双向联动

墨团不仅能自动发送消息，也能响应来自飞书的查询与控制指令。即使你不在电脑旁，也可以了解状态、刷新数据或控制桌宠显示。

<br>

## 六种状态，一眼看懂

从元气满满到额度警觉，墨团会随着 Codex 剩余额度自然变化；暂时没有数据时，它会安静休眠。

**元气满满** `80–100%`　·　**平静工作** `60–79%`　·　**稍有担心** `40–59%`

**有点疲惫** `20–39%`　·　**额度警觉** `01–19%`　·　**休眠待机** `OFFLINE`

<br>

## 下载内测版

### Windows

**[下载 Motuan-Beta-Setup.exe](Motuan-Beta-Setup.exe?raw=1)**

适用于 Windows 10 / 11 x64。安装时可以自行选择安装位置，目标电脑无需安装 Python，也无需安装飞书客户端。

### macOS

**[下载 Motuan-Beta-Setup.dmg](Motuan-Beta-Setup.dmg?raw=1)**

当前内测包面向 Apple Silicon（M 系列芯片）。打开 DMG 后，将墨团拖入“应用程序”即可。

> 如果浏览器没有自动下载，请进入安装包文件页面，点击右上角 **Download raw file**。

<br>

## 飞书联动

自动汇报只需要配置飞书群自定义机器人 Webhook。

如需双向查询与远程指令，可进一步配置企业自建应用机器人和长连接。

可用指令包括：

`状态`　`额度`　`任务`　`刷新`　`显示桌宠`　`隐藏桌宠`　`帮助`

运行墨团的电脑不需要安装飞书客户端。

<br>

## 本地优先，保护隐私

- 只读取 Codex 已写入本机的状态数据，不截屏、不注入 Codex 进程。
- 不读取、不保存、不上传 Codex 登录令牌。
- Windows 端使用 DPAPI 保护飞书 Webhook 与 App Secret。
- 诊断信息会排除飞书密钥与 Codex 登录令牌。

<br>

## 关于本次公开内测

这不是墨团的正式商业版本，而是面向早期用户的公开内测版。

- 免费内测服务截止至北京时间 **2026 年 9 月 30 日 23:59**。
- 到期后，Codex 监控、桌宠状态、飞书汇报与双向连接将停止服务。
- 内测期间，功能、界面与汇报策略仍可能继续调整。
- 正式版本将在公司、服务端与支付体系完善后另行推出。

<details>
<summary><strong>查看默认汇报策略</strong></summary>

<br>

- 每 5 分钟评估一次是否需要汇报，不固定重复发送。
- 任务进度跨过 5% 档位时发送更新。
- Codex 剩余额度每下降 5% 汇报一次。
- 额度重置、任务开始、完成、失败和低额度预警即时汇报。
- 检查间隔、任务档位、额度档位与预警阈值均可在设置中调整。

</details>

<details>
<summary><strong>查看安装包完整性校验</strong></summary>

<br>

校验值记录在 **[SHA256.txt](SHA256.txt)**。

Windows：

```powershell
Get-FileHash .\Motuan-Beta-Setup.exe -Algorithm SHA256
```

macOS：

```bash
shasum -a 256 Motuan-Beta-Setup.dmg
```

</details>

<br>

<div align="center">

<img src="motuan-icon.png" width="72" alt="墨团图标">

### 墨团 BETA

**SEE · TRACK · REPORT**

<sub>Copyright © 2026 Motuan. All rights reserved.</sub>

</div>
