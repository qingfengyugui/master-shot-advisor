# 大师镜头推荐 · Master Shot Advisor

把短剧 / AI 视频创作者的**剧情描述**，翻译成**专业镜头技法 + 可核查的大师范例 + 可直接复刻的提示词**。

> 剧情/情绪 → 镜头技法 → 大师范例 → 可直接复刻的提示词

创作者大多有画面感、没术语。这个 Skill 就是那个翻译器：先拆戏（冲突 / 信息差 / 转折点 / 权力流向），再选镜头，禁止按关键词直配；给出 1 个主推 + 2 个备选，每个带大师出处、为什么是它、换备选损失什么；主推拆到复刻粒度（景别、机位高度与角度、焦段感、构图、运镜四段、时长、光线色调、表演调度、剪辑切点、声音），并做**横屏→竖屏 9:16 转译**；一次交付三份输出：

- **A. 实拍分镜卡**（给导演/摄影照着拍，含低成本替代）
- **B. AI 视频生成提示词**（通用版：正向 + 负向 + 首帧图提示词，预留即梦/可灵等平台分版位）
- **C. 剪辑提示**（切点、节奏、音乐/音效进出）

主推还必带一张**原镜对照表**：逐项并排大师原镜与为你改的新镜（机位/构图/运镜/光线…），列明改了什么、为什么改，并附原镜出处链接与原片定位，方便你调出原镜同屏比对（只给链接，不抓取原站 GIF）。

默认场景：竖屏 9:16 短剧，节奏快，设备与场景条件有限。

## 文件结构

```
SKILL.md                        核心技能文件（工作流、追问规则、输出模板、竖屏转译、红线）
references/technique-library.md 技法库索引：按戏剧功能反查 + Eyecannndy 136 技法全量目录
examples/self-test-3-scenes.md  3 个短剧场景的全规格自测（偷听窥视 / 决裂 / 反转打脸）
platforms/chatgpt/              ChatGPT 适配（精简指令 + 知识文件用法）
AGENTS.md                       Muse 等 Agent 工具的入口指针
GEMINI.md                       Gemini / Antigravity 的入口指针
```

## 各平台用法

### Claude（Claude Code / Claude 桌面端 Skills）
把整个文件夹放进 skills 目录（如 `~/.claude/skills/master-shot-advisor/`），或在支持自定义 Skill 的界面中导入本仓库。触发词示例：「这场戏怎么拍」「帮我给这段剧情配镜头」。

### Muse
仓库根目录的 `AGENTS.md` 已指向 `SKILL.md`：把本仓库克隆到工作区，Codex 会按 AGENTS.md 的指引读取技能本体与技法库。也可把文件夹放进 `~/.codex/skills/` 作为技能使用。

### WorkBuddy
WorkBuddy 兼容 SKILL.md 技能格式：把整个 `master-shot-advisor` 文件夹导入技能目录即可，`references/` 与 `examples/` 会作为附属文件一并带入。

### Antigravity
Antigravity 支持 Agent Skills（SKILL.md 格式）：把文件夹放入其 skills 目录（全局 `~/.gemini/antigravity/skills/` 或工作区 `.agent/skills/`）。

### Gemini（Gemini CLI / 网页版）
Gemini CLI：根目录 `GEMINI.md` 已做入口指针，克隆到工作区即可被读取。网页版 Gemini：把 `platforms/chatgpt/instructions.md` 的精简指令粘进 Gem 的「指令」框，并把 `SKILL.md` 与 `references/technique-library.md` 作为知识文件上传（用法与 ChatGPT 相同，见下）。

### ChatGPT
ChatGPT 不直接加载 SKILL.md 文件夹，用 `platforms/chatgpt/` 里的适配版：
1. 新建一个 Custom GPT（或在项目里新建自定义指令）；
2. 把 `platforms/chatgpt/instructions.md` 全文粘进 Instructions；
3. 把仓库根目录的 `SKILL.md` 和 `references/technique-library.md` 作为 Knowledge 文件上传。
这样 ChatGPT 会按同样的工作流干活：先拆戏、查技法库、给 1+2 推荐与三份输出。

## 技法库来源与红线

- 技法分类框架来自 [Eyecannndy](https://eyecannndy.com/)（站长 Jacobi 的 Visual Technique Library，免费、社区共建）。该站自述内容 "never 100% accurate"，其标签与出处只作参考，Skill 要求大师范例出处必须可核查、查不到不许编。
- 只借鉴技法与构图思路，不复刻演员脸、不照搬受版权保护的具体画面细节；商用时有侵权风险提醒。
- 不批量抓取 Eyecannndy 的 GIF/图片再分发；本仓库只收录技法名称、分类与链接。

## 许可

本仓库文字内容以 MIT 许可发布；引用的技法名称与分类来自 Eyecannndy，其权利归原站所有。
