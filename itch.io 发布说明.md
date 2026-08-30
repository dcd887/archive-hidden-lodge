# itch.io 发布说明 ·《档案：隐庐》

本文件用于在 itch.io 「试水」上传，包含可直接复制的页面文案与两个发布压缩包。
发布包（已在 demo 目录生成）：
- `yinlu_windows.zip`（105 MB）—— Windows 便携版（双击 exe 即玩，含存档）
- `yinlu_html5.zip`（29 KB）—— 网页版（index.html，浏览器直接玩；存档用 localStorage）

**文件名已改为纯 ASCII 无中文，解决上传卡顿问题。**

推荐：先传 **Windows** 压缩包（存档最可靠）；网页版作「在线试玩」。

---

## 一、创建页面时填写

**标题**：档案：隐庐 / Archive: The Hidden Lodge
**分类**：Games
**类型**：单机 / 文字推理 / 解谜（Text / Story / Mystery）
**Genre**：Puzzle · Visual-Novel · Narrative
**Tags**（建议）：文字推理、本格推理、解谜、悬疑、电子文档、档案解密、剧情、中文
**成熟度**：内容均为虚构故事演绎，无实际血腥/惊悚依赖文件虚实不分；建议标注「虚构案情，现实无关」。

---

## 二、页头简介（Short description）
> 面对五沓互相关联的案件档案，用关键词检索还原时间线，在一个个证人独白与暗线「沉璧」之间，指认真正的凶手。

## 三、详细描述（Long description，可粘贴）
《档案：隐庐》是一款以「文字阅读 + 关键词搜索」为核心的档案解密式推理游戏。

你是一名专案组警探，接手五桩看似独立的凶案：古董商之死、顾宅夹层藏尸、大学教授"自杀"、拍卖行灭口、古镇密库之殇。每桩案件都有一沓档案——日记、录口供、验尸报告、监控文字记录——而随着你逐案侦破，一条贯穿五部、代号「沉璧」的暗线正缓缓浮现。

每案你要：
- 阅读 6 份档案，点击翻阅，用关键词（人名/日期/地点/物品）全局检索并高亮；
- 还原 8 段案发时间线（选择日期 + 事件）；
- 时间线 100% 后解锁一段「当事人独白」，在 4 名嫌疑人中指认真凶；
- 破案后将线索归档进「沉璧档案」，全五案通关，看穿被掩埋的真相。

特性：
- 五案 × 6 档案 × 8 时间线 × 4 嫌疑人，任一案均可独立解；
- 破案会解锁当事人第一人称独白（袁景行 / 顾明章 / 沈知白 / 宋守真 / 游守志…）；
- 本地自动存档（Windows 版写入 userData/saves），「继续 / 新游戏」随时可续；
- 卡关可逐条「侦查提示」，也有「沉璧档案」随时回看；
- 深色木质卷宗风界面、翻页音效、结案印章动画（可静音）。

免责：本作所有人物与地名均为虚构，仅用作架空推理叙事。

---

## 四、上传步骤（两种方式任选）

### 方式一：Butler 命令行（推荐，稳定可靠）

**Step 1 — Butler 已就绪**
Butler 已随 itch.io 桌面客户端安装，路径为：`C:\tools\butler.exe`

**Step 2 — 一键上传**
双击运行 `demo\一键上传.bat`，脚本会自动：
1. 弹出浏览器完成登录授权
2. 初始化项目通道
3. 上传 HTML5 版本（34 KB）到 web 通道
4. 上传 Windows 版本（105 MB）到 windows 通道

**或手动执行 PowerShell：**
```powershell
powershell -ExecutionPolicy Bypass -File "C:\Users\kjds\Desktop\demo\upload_with_butler.ps1"
```

**或手动执行 Butler 命令：**
```powershell
# 登录（首次只需一次）
C:\tools\butler.exe login

# 初始化项目（dcd2321 是用户名，yinlu 是项目名）
C:\tools\butler.exe init dcd2321/yinlu

# 上传 HTML5 到 web 通道（支持浏览器内嵌试玩）
C:\tools\butler.exe push "C:\Users\kjds\Desktop\demo\yinlu_html5.zip" dcd2321/yinlu:web --userversion 1

# 上传 Windows 到 windows 通道
C:\tools\butler.exe push "C:\Users\kjds\Desktop\demo\yinlu_windows.zip" dcd2321/yinlu:windows --userversion 1
```

> ⚠️ 重要：HTML5 版上传后，进入 itch.io 项目页面 → Settings → Build → 将 `index.html` 勾选为「Run in browser」，否则只会下载不会内嵌试玩。

### 方式二：网页上传（备用）
1. itch.io → **Create new project** → 填上「标题 / 简介 / 长描述 / Tags」；
2. **Uploads**：上传 `yinlu_html5.zip`，并在 **「Choose files to run in browser」** 里勾选 `index.html`；
   - 同时再传一份 `yinlu_windows.zip`，在 **"Windows"** 通道标记为下载项；
3. Cover image（胶囊图等商店素材，方向四补）这里先用一张「档案卡片/卷宗」竖图占位；
4. Publish → 得到页面链接，先在浏览器与另一台电脑各测试一次存档读写。

> ⚠️ 注意：网页上传不稳定时可切换至 Butler 命令行方式，Butler 增量上传且直连 API，成功率更高。

---

## 五、埋点与反馈
暂不做埋点；可在页面 Description 末尾留「遇到问题 → 反馈」邮箱占位，收集 Test-the-water 反馈为 Steam 版本迭代作参考。

## 六、AI 内容声明（对外透明）
本项目剧本与文案基于 AI 辅助生成，代码由 AI 协助编写，仅供娱乐与学习用途，所有人物与地名均为虚构。
