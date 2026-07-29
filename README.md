<div align="center">

<img src="motuan-icon.png" width="156" alt="墨团 Motuan">

<p><strong>MOTUAN BETA · CODEX STATUS COMPANION</strong></p>

# 墨团 BETA

## 把 Codex 状态留在桌面，把进度送到飞书

一只真正理解 Codex 工作状态的桌面伙伴。  
将额度、任务与进度集中到桌面，并在重要变化发生时主动送达飞书。

<p>
  <a href="Motuan-Beta-Setup.exe">
    <img src="https://img.shields.io/badge/Windows-下载内测版-087CD5?style=for-the-badge&logo=windows11&logoColor=white" alt="下载 Windows 内测版">
  </a>
  &nbsp;
  <a href="Motuan-Beta-Setup.dmg">
    <img src="https://img.shields.io/badge/macOS-下载内测版-111111?style=for-the-badge&logo=apple&logoColor=white" alt="下载 macOS 内测版">
  </a>
</p>

<p>
  <img src="https://img.shields.io/badge/阶段-公开内测-7C3AED?style=flat-square" alt="公开内测">
  <img src="https://img.shields.io/badge/版本-v0.2.0--beta-0F172A?style=flat-square" alt="内测版本">
  <img src="https://img.shields.io/badge/Codex-Desktop%20%7C%20CLI%20%7C%20VS%20Code-10B981?style=flat-square" alt="Codex 支持">
  <img src="https://img.shields.io/badge/飞书-自动汇报%20%2B%20双向指令-3370FF?style=flat-square" alt="飞书联动">
  <img src="https://img.shields.io/badge/体验期限-2026.09.30-F59E0B?style=flat-square" alt="体验期限">
</p>

<p>
  <a href="#内测亮点">内测亮点</a>
  ·
  <a href="#能力概览">能力概览</a>
  ·
  <a href="#工作方式">工作方式</a>
  ·
  <a href="#下载安装">下载安装</a>
  ·
  <a href="#内测须知">内测须知</a>
</p>

<img src="motuan-poster.png" width="960" alt="墨团 BETA 宣传海报">

</div>

---

## 内测亮点

### 从“反复查看”，变成“状态主动出现”

墨团将 Codex 写入本机的状态数据转换为桌面桌宠、额度数字、任务进度和飞书消息。  
无需持续盯着 Codex 窗口，也无需在不同设备之间反复确认任务是否完成。

<table>
<tr>
<td width="25%" align="center"><strong>6 种状态表情</strong><br><sub>额度变化一眼可见</sub></td>
<td width="25%" align="center"><strong>3 类 Codex 入口</strong><br><sub>Desktop · CLI · VS Code</sub></td>
<td width="25%" align="center"><strong>5 分钟默认策略</strong><br><sub>重要变化才汇报</sub></td>
<td width="25%" align="center"><strong>双向飞书联动</strong><br><sub>主动送达，也可随时查询</sub></td>
</tr>
</table>

| 桌面可见 | 主动汇报 | 随时查询 |
|---|---|---|
| 无边框透明桌宠，可选择始终置顶 | 额度、进度、完成、失败与重置状态主动发送 | 在飞书手机端、网页端或其他电脑查询 |
| 像素数字实时显示 Codex 剩余额度 | 按时间和变化阈值判断，减少重复消息 | 从飞书刷新状态，显示或隐藏桌宠 |
| 六种表情对应不同额度区间 | 低额度预警与关键任务事件即时汇报 | 运行电脑不需要安装飞书客户端 |

## 能力概览

| 能力 | 当前内测支持 |
|---|---|
| **桌面状态** | 透明桌宠、实时额度、六种表情、拖动、隐藏、始终置顶 |
| **任务感知** | 当前任务识别、进度估算、开始、完成与失败状态 |
| **Codex 识别** | Codex Desktop、Codex CLI、VS Code 官方 Codex 插件 |
| **额度更新** | 额度下降、额度重置与预计重置时间识别 |
| **飞书汇报** | Webhook 自动汇报、任务进度、额度变化与异常预警 |
| **飞书指令** | 长连接接收状态、额度、任务、刷新与桌宠控制指令 |
| **后台运行** | 系统托盘、开机自启、后台刷新 |
| **安全保护** | 本地只读、敏感数据排除、Windows DPAPI 加密 |

## 六种状态

<table>
<tr>
<td align="center"><strong>开心</strong><br><sub>85%–100%</sub></td>
<td align="center"><strong>平静</strong><br><sub>65%–84%</sub></td>
<td align="center"><strong>担心</strong><br><sub>45%–64%</sub></td>
<td align="center"><strong>疲惫</strong><br><sub>25%–44%</sub></td>
<td align="center"><strong>警觉</strong><br><sub>0%–24%</sub></td>
<td align="center"><strong>休眠</strong><br><sub>暂无数据</sub></td>
</tr>
</table>

额度发生重置时，墨团会重新识别上升后的额度、更新桌面表情，并按策略向飞书发送重置消息，不需要重新开启 Codex 对话。

## 工作方式

```text
Codex Desktop / CLI / VS Code
              │
              ▼
       本机状态数据（只读）
              │
       ┌──────┴──────┐
       ▼             ▼
  桌面墨团状态     任务与额度策略
                      │
                      ▼
               飞书自动汇报
                      ▲
                      │
               飞书双向指令
```

### 默认汇报策略

- 每 **5 分钟**评估一次是否需要汇报，而不是固定重复发送。
- 任务进度跨过 **5%** 档位时发送更新。
- Codex 剩余额度每下降 **5%** 汇报一次。
- 额度重置、任务开始、完成、失败和低额度预警即时汇报。
- 检查间隔、任务档位、额度档位与预警阈值均可在设置中调整。

## 飞书联动

### 自动汇报

在飞书群中添加自定义机器人，将 Webhook 填入墨团，即可接收 Codex 额度、任务进度与异常状态。

### 双向指令

配置飞书企业自建应用机器人与长连接后，可向墨团发送：

`状态` · `额度` · `任务` · `刷新` · `显示桌宠` · `隐藏桌宠` · `帮助`

墨团会实时判断当前状态并返回结果。运行墨团的电脑不需要安装飞书客户端。

## 下载安装

| 平台 | 安装文件 | 当前支持 | 大小 |
|---|---|---|---:|
| Windows | **[Motuan-Beta-Setup.exe](Motuan-Beta-Setup.exe)** | Windows 10/11 x64 | 约 44 MB |
| macOS | **[Motuan-Beta-Setup.dmg](Motuan-Beta-Setup.dmg)** | Apple Silicon（M 系列芯片） | 约 41 MB |

> GitHub 无法在线预览大型安装包。进入文件页面后，点击右上角 **Download raw file** 下载。

### Windows

1. 下载并运行 `Motuan-Beta-Setup.exe`。
2. 自行选择安装位置并完成安装。
3. 首次启动后，墨团会自动查找当前 Windows 用户的 Codex 数据。
4. 根据需要启用始终置顶、开机自启和飞书联动。

目标电脑无需安装 Python，也无需安装飞书客户端。

### macOS

1. 下载并打开 `Motuan-Beta-Setup.dmg`。
2. 将墨团拖入“应用程序”目录。
3. 首次启动后根据 macOS 提示完成必要授权。

当前 macOS 内测包面向 Apple Silicon 设备。

## 安全与隐私

- **本地只读**：仅读取 Codex 已写入本机的状态文件。
- **无屏幕采集**：不抓屏，不注入 Codex 进程。
- **令牌隔离**：不读取、不保存、不上传 Codex 登录令牌。
- **密钥保护**：Windows 端飞书 Webhook 与 App Secret 使用 DPAPI 加密。
- **跨设备隔离**：受保护的密钥无法直接复制到另一台电脑解密。
- **诊断脱敏**：诊断信息排除飞书密钥与 Codex 登录令牌。

## 内测须知

> **这是墨团公开内测版，并非正式商业版本。**

- 免费内测服务固定截至北京时间 **2026 年 9 月 30 日 23:59**。
- 到期后 Codex 监控、桌宠状态、飞书汇报与双向连接将停止。
- 当前 macOS 版本仅提供 Apple Silicon 构建。
- 内测期间功能、界面与汇报策略可能继续调整。
- 正式版本将在公司、服务端与支付体系完善后另行推出。

## 文件校验

安装包 SHA256 记录于 **[SHA256.txt](SHA256.txt)**。

```powershell
# Windows
Get-FileHash .\Motuan-Beta-Setup.exe -Algorithm SHA256
```

```bash
# macOS
shasum -a 256 Motuan-Beta-Setup.dmg
```

<div align="center">

---

### MOTUAN BETA

**CODEX STATUS · TASK PROGRESS · FEISHU COLLABORATION**

把 Codex 状态留在桌面，把进度送到飞书。

<sub>Copyright © 2026 Motuan. All rights reserved.</sub>

</div>
