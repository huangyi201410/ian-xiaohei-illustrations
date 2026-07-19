# Aiko Illustrations

> 把中文文章里的判断、流程、状态和隐喻，变成一张张白底、手绘、怪诞但清爽的正文配图。
>
> 16:9 横版 | Aiko 蓝白机器人 IP | 纯白手绘 | 少量红橙蓝中文批注 | Codex Skill

---

## 这个仓库是什么

Aiko Illustrations 是一个 Codex Skill，用来指导 AI Agent 为中文文章、帖子、博客、Notion 文档和方法论内容生成正文配图。

它不是通用插画 prompt，也不是 PPT 信息图模板。它的目标是先理解文章里的认知锚点，再把其中一个判断、流程、结构、状态或隐喻，变成一张有记忆点的 16:9 手绘解释图。

默认视觉 IP 是 Aiko，识别点为 **“蓝白机器人”**：卡通大头短身比例、黑色长直发、白色 T 恤、天蓝色下装，以及机器人袖章或腰侧挂件。每张图都附带 `assets/aiko-character-sheet.png` 作为角色参考；Aiko 用小而关键的动作参与结构，但观点隐喻始终是画面重点。

一句话：**让 AI 不只是“配一张图”，而是把文章里的一个关键认知动作画出来。**

## 它会产出什么

默认输出：

- 16:9 横版正文配图
- 一篇文章的 4-8 张 shot list
- 每张图的主题、核心意思、结构类型、Aiko 动作和中文标注建议
- 最终 PNG 图片，保存到 workspace 的 `assets/<article-slug>-illustrations/`

默认不输出：

- PPTX / PDF / Keynote
- SVG / HTML / Canvas 可编辑图
- 商业海报或封面 KV
- 大段文字型信息图

## 视觉风格

本 Skill 保留原有的怪诞正文配图语言：

- 纯白背景，不要纸纹、米色、阴影、渐变
- 黑色手绘线稿，细线，轻微抖动
- 大量留白，主体只占画面约 40%-60%
- 少量红色、橙色、蓝色中文手写批注
- 一张图只表达一个核心动作、结构、状态或隐喻
- Aiko 必须完成关键动作，并与她正在操作的局部关键物件同尺度；不能抢走观点重点
- 怪诞、有创意、清爽，但不幼稚、不卖萌

## 安装

克隆仓库：

```bash
git clone https://github.com/huangyi201410/ian-xiaohei-illustrations.git
cd ian-xiaohei-illustrations
```

复制 skill 到 Codex skills 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./ian-xiaohei-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

安装后，在 Codex 里使用：

```text
Use $ian-xiaohei-illustrations 为这篇中文文章设计并生成 5 张 Aiko 怪诞正文配图。
```

## 怎么用

### 只做配图规划

```text
Use $ian-xiaohei-illustrations 先不要生图。
请分析下面这篇文章哪里值得配图，输出 5 张左右的 shot list。
每张图写清楚：放在哪段后、主题、核心意思、结构类型、Aiko 在做什么、建议中文标注词。

<粘贴文章>
```

### 直接生成正文配图

```text
Use $ian-xiaohei-illustrations 把下面这篇文章生成 4 张 Aiko 怪诞正文配图。
要求：16:9 横版、纯白背景、黑色手绘线稿、少量红橙蓝中文手写批注。

<粘贴文章>
```

### 为单个概念生成一张图

```text
Use $ian-xiaohei-illustrations 为“信任不是喊出来的，而是一块证据一块证据铺过去”生成一张正文配图。
画面要怪诞但清爽，Aiko 必须承担核心动作。
```

更多示例见 [examples/prompts.md](examples/prompts.md)。

## 工作流程

1. 读取文章、Markdown、Notion 内容、截图或用户给的主题。
2. 提炼核心观点、认知转折、流程结构和适合视觉化的段落。
3. 先输出 shot list：每张图只选一个认知锚点。
4. 为每张图选择结构类型：Workflow、系统局部、前后对比、角色状态、概念隐喻、方法分层、地图路线或小漫画分镜。
5. 重新发明一个低科技、怪诞但成立的物理隐喻。
6. 先画观点隐喻，再让小比例 Aiko 完成关键动作。
7. 每张图单独调用图像模型生成。
8. 按 QA checklist 检查：白底、留白、Aiko 动作、中文标注、非 PPT 感、非旧案例复刻。
9. 保存最终 PNG，并报告用途和路径。

## 目录结构

```text
.
├── README.md
├── LICENSE
├── NOTICE.md
├── examples/
│   └── prompts.md
└── ian-xiaohei-illustrations/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   └── aiko-character-sheet.png
    └── references/
        ├── style-dna.md
        ├── aiko-ip.md
        ├── composition-patterns.md
        ├── prompt-template.md
        └── qa-checklist.md
```

真正需要安装到 Codex 的是子目录 `ian-xiaohei-illustrations/`。根目录的 README、LICENSE、NOTICE 和 examples 是 GitHub 分享文档。

## 注意事项

- 图片里的中文文字越短越稳定。
- 每张图只讲一个核心结构，不要把文章做成说明书。
- 每次生图都要附带 `assets/aiko-character-sheet.png`，只锁定角色外形，不复刻三视图版式。
- Aiko 必须完成关键动作，且高度约为局部关键物件的 0.8–1.2 倍；第一眼应看到观点隐喻，而不是 Aiko 的脸或服装。
- AI 图像模型可能出现错字、幻觉标签、风格漂移或多余标题，生成后需要检查。
- 如果中文错字严重，优先减少标注词并重生成。

## 致谢

本项目的 Skill 结构源自 [Ian Xiaohei Illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations)。Aiko 是本仓库适配版本使用的独立视觉 IP；详见 [NOTICE.md](NOTICE.md)。

## License

MIT License. See [LICENSE](LICENSE).
