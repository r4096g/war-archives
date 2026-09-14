# war-archives
# 军史馆 · War Archives

记录实战战役：bug 上报、项目作战。档案随窗口转移，永不失传。

## 战役一览

| # | 战役 | 战场 | 状态 |
|---|------|------|------|
| 001 | Gemini Voyager 导出缺 AI 回复 | github.com/Nagi-ovo/voyager/issues/943 | ✅ 已修复上架 |
| 002 | ChatGPT TTS 朗读引号 | community.openai.com/t/.../1394874 | 🕐 已上报 |
| 003 | 阿罗托计划 v1.0 建站 | github.com/r4096g/villa-azur | 🚧 进行中 |

## 001 · Voyager #943（2026-08）
- **现象**：导出「Select AI only」仅抓到 2 条 AI 消息，导出文档缺 AI 回答
- **定位**：DevTools 排除法——Console 零报错（脚本正常注入）、59 条 CSP 拦截全是 Google 自家 KaTeX 字体（排除背锅）→ 研判为 Gemini 新版**虚拟滚动**，视口外消息不在 DOM
- **建议**：扫描前模拟整页滚动，以「连续无新增消息」为加载完成信号
- **战术**：不重复立案，在现有 issue 下跟帖补充分析
- **战果**：作者次日回复（早于预测 3 天），约两天后新版发布修复

## 002 · OpenAI TTS blockquote（2026）
- **现象**：TTS 把引号朗读为 "open quote / close quote"，实时语音不出现
- **触发条件**（多条消息实测锁定）：**仅 blockquote 格式触发**，普通段落引号不触发
- **研判**：blockquote 标记疑似被原样传入 TTS，非模型行为
- **链接**：community.openai.com/t/tts-reads-quotation-marks-aloud-open-quote-close-quote-when-the-sentence-is-formatted-as-a-blockquote/1394874

## 003 · 阿罗托计划（进行中）
- Villa Azur React+Vite 三语站，源码已入库：`r4096g/villa-azur`
- 详细档案见该仓库 `docs/`（建站手册、行军日志、战地日志）

## 军规沉淀（能力清单）
1. DevTools Console + CSP 面板**排除法**定位，不瞎猜
2. Bug report 规范：环境 + 版本 + 复现步骤 + 期望结果 + 脱敏诊断
3. 先搜现有 issue，**跟帖优于重复立案**
4. 给出**最小触发条件**是 bug report 的灵魂
5. 档案入库三地备份：军营(GitHub) + 帐篷(沙盒) + 行军枕(本机)

---
*汇报人 ID：r4096g · 档案随战事更新*
