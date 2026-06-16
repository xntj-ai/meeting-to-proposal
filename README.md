# meeting-to-proposal

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-d97757.svg)](https://claude.com/claude-code)

**One client interview → a complete business proposal in about fifteen minutes.**

**一次客户访谈 → 十几分钟变成一份完整的商业提案。**

meeting-to-proposal is a [Claude Code](https://claude.com/claude-code) skill that takes a client interview — an audio recording or a meeting transcript — and runs it end to end into a deliverable proposal web page: a 13-dimension business canvas, a 5-dimension personal IP positioning, and a 5-dimension content topic library. It is an orchestrator that chunks and transcribes the recording, runs a multi-agent research team, then calls three sub-skills to write each part, and finally synthesizes one HTML page with the client's name redacted.

meeting-to-proposal 是一个 [Claude Code](https://claude.com/claude-code) 技能。给它一次客户访谈 —— 一段音频录音或一份会议记录 —— 它就端到端跑成一份可交付的提案网页:13 维度商业画布、5 维度个人 IP 定位、5 维度内容选题库。它是一个 orchestrator:把录音切段转写、组织一支多智能体调研团队,再调用三个子技能分别撰写每一部分,最后合成一个隐去客户名称的 HTML 页面。

This skill is distilled from a real run on the 「张拼拼·XNTJ」 episode [EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/): a 2.5-hour interview with a Singapore client turned into a full proposal in about ten minutes. The method here is the *thinking* — the field tables, the formulas, the constraints — not a tool lock-in.

这个技能沉淀自「张拼拼·XNTJ」[EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/) 的一次实战:一场 2.5 小时的新加坡客户访谈,约十分钟出一份完整提案。它的核心是**思路** —— 那些字段表、公式、约束 —— 而不是工具绑定。

## Why meeting-to-proposal · 为什么用 meeting-to-proposal

Meeting a client, mapping their needs, and writing a proposal is the most draining part of day-to-day business — whether you are a high-paid executive, a one-person company, or a founder. The usual path is days of manual work: re-listen to the call, hand-build a canvas that ends up thin, and produce a deck that does not differentiate. meeting-to-proposal takes the opposite stance: it distills your professional ability into a repeatable skill, so the whole chain collapses into about fifteen minutes — and the output is a redacted, hand-off-ready web page, not a pile of raw notes.

跟客户开会、梳理需求、写提案,是日常业务里最累人的环节 —— 不管你是百万年薪高管、一人公司、还是创业者。常规做法是好几天的手工活:把通话重听一遍、手搭一个最后写得很空的画布、出一份不出彩的方案。meeting-to-proposal 反其道而行:它把你的专业能力蒸馏成一个可重复调用的技能,于是整条链路压缩到十几分钟 —— 产物是一个隐去客户名、可直接交付的网页,而不是一堆原始笔记。

## Features · 功能特性

- **End-to-end orchestration** — one skill carries the run from raw recording all the way to a finished proposal web page; you do not stitch the steps together yourself. **端到端编排** —— 一个技能把整条链路从原始录音一路带到成品提案网页,你不用自己拼接各步骤。
- **Chunked ASR that beats meeting software** — splits audio into 7–8 minute segments to avoid the attention collapse of single-pass transcription, and feeds meeting background as context so accuracy runs 20–30 points above the built-in transcript. **切段 ASR,识别率高过会议软件** —— 把音频切成 7-8 分钟一段,避开整段转写的注意力塌陷,并把会议背景作上下文喂进去,识别率比软件自带逐字稿高 20-30 个百分点。
- **Multi-agent research team** — splits research into industry / competitor / customer-breakdown / market-sizing agents so the investigation stays focused instead of sprawling. **多智能体调研团队** —— 把调研拆成行业 / 竞品 / 客户拆解 / 规模测算几个 agent,让调查聚焦而不发散。
- **Three composable sub-skills** — `business-canvas` (13 dimensions), `personal-ip-positioning` (the cross-discipline triangle), and `content-topic-design` (5 dimensions × 10 topics), each usable on its own. **三个可组合的子技能** —— `business-canvas`(13 维度)、`personal-ip-positioning`(跨界三角)、`content-topic-design`(5 维度 × 10 选题),每个都能独立使用。
- **Field tables from a real run, not invented** — every dimension follows the actual field table reverse-engineered from the EP0013 public demo, so the canvas gets filled in full instead of left vague. **字段表来自真实实战,不是臆造** —— 每个维度都按 EP0013 公开 demo 反推的实际字段表,商业画布被强制填满而不是写得空。
- **Redaction by default** — the synthesized page writes "a company in the XX business" instead of the real client name, because this comes from real cases. **默认脱敏** —— 合成页面写「一家做 XX 业务的公司」而不是真实客户名,因为它来自真实案例。

## When to use · 适用场景

Reach for meeting-to-proposal when you have a client interview — audio or transcript — and you want the full package out of it: a business-canvas analysis, a personal-IP positioning, and a content-topic plan, synthesized into a deliverable consulting report. It fits consultants, freelancers, one-person-company founders, BD, and pre-sales.

当你手上有一次客户访谈 —— 音频或文字记录 —— 并且想从中拿到整套交付物:商业画布分析、个人 IP 定位、内容选题方案,合成成一份可交付的咨询报告时,就用 meeting-to-proposal。它适合咨询顾问、自由职业者、一人公司创始人、BD、售前。

It is not the right tool for plain transcript cleanup (use an ASR tool), for a client check-in with no consulting output, or for a pure RFP response.

它不适合纯粹的逐字稿整理(用 ASR 工具即可)、不产出咨询内容的客户回访,或纯 RFP 应答。

## Install · 安装

Clone this repository into your Claude Code skills directory:

把本仓库克隆到你的 Claude Code 技能目录:

```bash
# macOS / Linux
git clone https://github.com/xntj-ai/meeting-to-proposal.git ~/.claude/skills/meeting-to-proposal

# Windows (PowerShell)
git clone https://github.com/xntj-ai/meeting-to-proposal.git "$env:USERPROFILE\.claude\skills\meeting-to-proposal"
```

The skill itself is just Markdown — there is nothing to build. Chunked ASR (Step 2) does need an audio-transcription model and FFmpeg available in your environment; the rest is research and writing the skill drives on its own.

技能本身就是 Markdown —— 没有任何构建步骤。切段 ASR(Step 2)需要环境里有一个音频转写模型和 FFmpeg;其余的调研和撰写,技能自己驱动。

## Usage · 用法

**With Claude** — drop a client interview audio file (or its transcript) into the conversation and ask for the full proposal, e.g. *"use meeting-to-proposal to turn this client interview into a complete proposal."* Claude triggers the skill from its description, runs the 7-step orchestration, and produces an HTML proposal page with the client name redacted.

**对 Claude 说** —— 把一份客户访谈音频(或它的逐字稿)扔进对话,要求生成完整提案,比如"用 meeting-to-proposal 把这次客户访谈做成一份完整提案"。Claude 会根据 description 触发技能,跑完 7 步编排,产出一个隐去客户名的 HTML 提案页面。

**The best input is audio + transcript together.** The meeting software's transcript keeps the attendee names and timestamps (even if its accuracy is only 60–70%); the raw audio lets the skill re-recognize the speech with a stronger model. Give both.

**最佳输入是音频 + 逐字稿一起给。** 会议软件的逐字稿留下了参会人姓名和时间戳(哪怕它准确率只有 60-70%);原始音频则让技能用更强的模型重新识别。两个都给。

**Without Claude** — paste the contents of `SKILL.md` into any LLM (Claude / ChatGPT / Gemini). The method is the thinking, not the tool; the result is the same.

**不经 Claude** —— 把 `SKILL.md` 的内容直接粘进任意 LLM(Claude / ChatGPT / Gemini)。核心是思路而非工具,效果一样。

## Workflow · 工作流

The orchestration runs in 7 steps, from raw meeting material to a synthesized proposal page:

整条编排分 7 步,从原始会议素材到合成的提案页面:

1. **Prepare the material** — gather the interview audio and/or the existing meeting transcript. **准备会议素材** —— 收集访谈音频和/或已有的会议记录文本。
2. **Chunked ASR transcription** — split the audio into 7–8 minute segments with FFmpeg, transcribe each independently, feed meeting background as context, and merge with offset timestamps. **切段 ASR 转写** —— 用 FFmpeg 切成 7-8 分钟一段,每段独立转写,把会议背景作上下文喂入,按段偏移叠加时间码合并。
3. **Multi-agent research** — run an industry researcher, a competitor analyst, a customer-breakdown agent, and a market-sizing agent over the transcript. **多智能体调研** —— 让行业调研员、竞品分析员、客户拆解员、数据测算员对转写文本展开调查。
4. **Call `business-canvas`** — produce the 13-dimension business canvas, every dimension filled to the EP0013 field table. **调用 `business-canvas`** —— 产出 13 维度商业画布,每个维度按 EP0013 字段表填满。
5. **Call `personal-ip-positioning`** — turn the interviewee's background, career, and traits into a differentiated positioning. **调用 `personal-ip-positioning`** —— 把受访者的成长经历、职业生涯、个人特质转成差异化定位。
6. **Call `content-topic-design`** — build a 5-dimension × ~2–3 sub-direction × 10-topic content library. **调用 `content-topic-design`** —— 搭一个 5 维度 × 约 2-3 子方向 × 10 选题的内容库。
7. **Synthesize the proposal page** — fold the three outputs into one HTML page with four core sections (business analysis / personal IP / content plan / key assumptions & validation path), client name redacted. **合成提案页面** —— 把三份输出折进一个 HTML 页面,含四个核心区块(商业运营分析 / 个人 IP 定位 / 自媒体规划 / 关键假设与验证路径),隐去客户名。

## Examples · 示例

The EP0013 demo run: a 2.5-hour interview with a Singapore client became a complete proposal in about ten minutes — a 13-dimension business canvas plus a 5-dimension × 10-topic content plan. See it walked through in [EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/).

EP0013 的 demo 实跑:一场 2.5 小时的新加坡客户访谈,约十分钟变成一份完整提案 —— 13 维度商业画布 + 5 维度 × 10 选题的内容方案。完整走查见 [EP0013 AI 帮我拿单子](https://xntj.tv/ep/live-ep0013/)。

## How it works · 技术原理

The reason fifteen minutes is enough is not that the model got faster — it is that your professional ability was distilled beforehand. Three things are pre-loaded: the **input** (every past consulting meeting, even the pre-call questions, which were themselves AI-prepared), the **output** (the report you handed each client afterward, used as a best-practice reference), and the **process** (how to search, research, think, and write the report step by step — written into the skill). The three sub-skills carry the field-level expertise: `business-canvas` enforces all 13 dimensions, `personal-ip-positioning` runs the cross-discipline triangle (depth × breadth × traits), and `content-topic-design` lays out the 5 × 10 topic grid.

十几分钟够用的原因不是模型变快了 —— 是你的专业能力被提前蒸馏过。三样东西被预先装好:**input**(过去每一次咨询会议的内容,甚至会前问题都是 AI 准备的)、**output**(每次会后给客户的报告,作为最佳实践参考)、**process**(怎么搜索、调研、思考、一步步写报告 —— 写进了技能)。三个子技能承载字段级专业:`business-canvas` 强制 13 个维度全填,`personal-ip-positioning` 跑跨界三角(深度 × 跨度 × 特质),`content-topic-design` 铺开 5 × 10 选题网格。

## FAQ · 常见问题

**Why chunk the audio instead of transcribing it all at once?** Single-pass ASR on 5+ minutes triggers attention collapse — in the EP0013 run a 24-minute pass broke down around the 9-minute mark. Splitting into 7–8 minute segments and merging with offset timestamps keeps the transcript accurate.

**为什么要切段而不是整段转写?** 5 分钟以上的整段 ASR 会触发注意力塌陷 —— EP0013 第一次跑 24 分钟,9 分钟左右就崩了。切成 7-8 分钟一段、按偏移叠加时间码合并,才能保住转写准确率。

**Can I use the sub-skills on their own?** Yes. Each of `business-canvas`, `personal-ip-positioning`, and `content-topic-design` works standalone — give it the inputs listed at the top of its file and it produces that one section.

**子技能能单独用吗?** 能。`business-canvas`、`personal-ip-positioning`、`content-topic-design` 每个都能独立运行 —— 按各文件开头列的输入给它,它就产出那一个区块。

**Does it replace doing real consulting work?** No. The constraint is explicit: AI is augmentation, not replacement — it works on top of your professional ability. A client is an opportunity, not a closed deal; this flow exists to screen fast, build trust, and reach long-term cooperation, not to substitute the real service delivery.

**它会取代真正的咨询工作吗?** 不会。约束写得很明白:AI 是赋能不是取代 —— 它建立在你的专业能力之上。客户只是商机不是确定性客户;这条流程是为了快速筛选、建立信任、走向长期合作,而不是替代真实的服务交付。

**Why is the client name always hidden?** Because the cases are real. The synthesized page writes "a company in the XX business" and only names the business type, never the client.

**为什么客户名总是隐去?** 因为案例是真实的。合成页面写「一家做 XX 业务的公司」,只提业务类型,绝不点名客户。

## Related · 相关

- [live-video-postprod](https://github.com/xntj-ai/live-video-postprod) — the sister skill; its § 01 chapter is the same chunked-ASR methodology this skill reuses for Step 2. 姊妹技能;它的 § 01 章节就是本技能 Step 2 复用的同一套切段 ASR 方法论。
- [ppvi](https://github.com/xntj-ai/ppvi) — the PinPin Visual Identity design language the synthesized proposal page follows. 合成的提案页面所沿用的 PinPin 视觉设计语言。
- [xntj.tv](https://xntj.tv) — more Claude Code workflows and skills from 张拼拼 · XNTJ; every episode has an illustrated write-up. 更多来自张拼拼·XNTJ 的 Claude Code 工作流与技能,每期视频都有图文版。

## License · 许可证

[MIT](./LICENSE) © [张拼拼 · XNTJ](https://xntj.tv)
