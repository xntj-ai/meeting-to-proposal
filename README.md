# meeting-to-proposal

> 把一次客户访谈，十几分钟变成完整商业提案的 Claude Code skill。
> 沉淀自「张拼拼·XNTJ」[EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/) 实战。

## 它做什么

不管你是百万年薪高管、OPC、还是创业者 —— 日常业务最头疼的就是跟客户开会、梳理需求、提案。

这个 skill 把这条链路压缩到十几分钟：

```
客户访谈音频 ─→ 切段 ASR 转写 ─→ 多智能体调研
                                       │
                                       ▼
              ┌──────────── 调用三个子 skill ────────────┐
              │                                          │
        business-canvas       personal-ip       content-topic
      (13 维度商业画布)    (5 维度 IP 定位)    (5 维度 × 10 选题)
              │                  │                  │
              └─────── 合成完整提案网页 ──────────────┘
                          (隐去客户名称)
```

## 它解决什么坑

EP0013 demo 实例：一次跟新加坡客户的 2.5 小时访谈 → 10 分钟出完整提案（13 维度商业画布 + 5 维度 × 10 选题的自媒体规划）。

| 痛点 | skill 怎么解 |
|---|---|
| 整段 ASR 注意力塌陷 | **切段 ASR**（7-8 分钟一段）+ 背景信息作上下文 |
| 调研发散无重点 | **多智能体团队拆分**（行业 / 竞品 / 客户拆解 / 数据测算）|
| 商业画布写得空 | **强制 13 个维度全填**，按 EP0013 实战字段表 |
| IP 定位飘 | **跨界三角公式**（深度 × 跨度 × 特质）|
| 选题做不长久 | **5 维度 × 10 选题** 结构，跑 6 个月不重样 |
| 提案不能给真实客户名 | **强制脱敏**，写「一家做 XX 业务的公司」 |

## 仓库结构

```
meeting-to-proposal/
├── SKILL.md                              主 skill (orchestrator, 含 frontmatter)
├── skills/
│   ├── business-canvas.md                子方法论：13 维度商业画布
│   ├── personal-ip-positioning.md        子方法论：5 维度 IP 定位
│   └── content-topic-design.md           子方法论：5×10 选题库
├── LICENSE                               MIT
└── .gitignore
```

## 安装到 Claude Code

```bash
# macOS / Linux
cd ~/.claude/skills
git clone https://github.com/xntj-ai/meeting-to-proposal.git

# Windows (PowerShell)
cd $env:USERPROFILE\.claude\skills
git clone https://github.com/xntj-ai/meeting-to-proposal.git
```

之后在 Claude Code 里直接调用 `/meeting-to-proposal`，或者把客户访谈音频扔进对话框，Claude 会按 description 自动触发。

## 不安装也能用

把 `SKILL.md` 内容直接粘贴到任意 LLM（Claude / ChatGPT / Gemini）对话里，效果一样。这套方法论的核心是**思路**而不是工具绑定。

## 重要说明

这套 skill 的方法论**框架基于 EP0013 公开 demo 提炼**。具体每个子 skill 内部的：

- 商业画布的 13 个维度顺序与字段
- 个人 IP 定位的「跨界三角」公式
- 选题库的「5 维度 × 10 选题」结构

都是张拼拼·XNTJ 实战提炼。**未来会持续迭代** —— 如果你在用的过程中发现新的踩坑或最佳实践，欢迎在 issue / 视频号留言。

## 核心理念

> AI 是来帮助我们的，是去赋能我，让我们的能力放大化、规模化、效率化的。
> 它**并不是完全取代人** —— AI 能做到今天的效果，建立在你的专业性的基础上。
>
> 一定要切记 —— **用最好的模型和 AI 的工具，把自己的专业能力萃取出来**，
> 完成对自己真实业务的赋能和提效。
>
> —— EP0013 AI 帮我拿单子

## 出处

- 张拼拼·XNTJ — 17 年跨 7 个行业，一人公司副业 8 年，40 岁 All in AI
- 配套博客：[xntj.tv](https://xntj.tv)（每期视频都有图文版）
- 这套 skill 来自这期：[EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/)
- 视频后期生产线（姊妹 skill）：[xntj-ai/live-video-postprod](https://github.com/xntj-ai/live-video-postprod)

## License

MIT — 把方法论拿走改成你自己的。如果有用，欢迎在视频号让我知道。
