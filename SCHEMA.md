# Wiki Schema

## Domain
AI/大模型学习知识库。来源主要是B站AI博主（清华姜学长、晓辉博士等）的视频字幕，
以及偶尔补充的arxiv论文、技术文章。目标：把每天看的AI视频内容沉淀成越来越厚的、
可检索、可交叉引用的个人知识库，避免"看完就忘"。

## Conventions
- 文件名：小写、连字符、无空格（如 `model-distillation.md`）。中文概念用拼音或英文（如 `model-distillation.md` 而非 `模型蒸馏.md`），标题里写中文
- 每个wiki页面以YAML frontmatter开头（见下）
- 用 `[[wikilinks]]` 链接页面（每页至少2个出链）
- 更新页面时务必更新 `updated` 日期
- 每个新页面必须加入 `index.md` 对应分区
- 每次操作必须追加到 `log.md`
- 综合3+来源的页面，段落末尾用 `^[raw/transcripts/source.md]` 标注来源

## Frontmatter
```yaml
---
title: 页面标题（中文）
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [来自下方taxonomy]
sources: [raw/transcripts/BVxxxx.md]
confidence: high | medium | low
---
```

### raw/ Frontmatter
```yaml
---
source_url: https://www.bilibili.com/video/BVxxxx
author: 博主名
ingested: YYYY-MM-DD
sha256: <正文sha256>
---
```

## Tag Taxonomy
新tag必须先加到这里再使用，防止tag泛滥。

- 模型相关: model, architecture, benchmark, training, distillation, fine-tuning, moe
- 技术方法: rag, agent, prompt, inference, alignment, multimodal, reasoning
- 人物机构: person, company, lab, open-source, blogger
- 学习/应用: learning-path, tool, workflow, career, application
- 元信息: comparison, timeline, controversy, prediction, concept-intro

## Page Thresholds
- **建页**：某概念/实体在2+来源出现，或在单一来源中是核心主题
- **补充已有页**：来源提到已覆盖的内容
- **不建页**：一带而过的提及、领域外内容
- **拆页**：超过~200行时拆成子主题
- **归档**：内容完全被取代时移到 `_archive/`

## Entity Pages
人物/公司/产品/模型。含：是什么、关键事实日期、与其他实体关系([[wikilinks]])、来源

## Concept Pages
概念/技术。含：定义解释、当前认知状态、开放问题/争议、相关概念([[wikilinks]])

## Comparison Pages
横向对比（表格优先）。含：对比什么及为何、对比维度、结论、来源

## Update Policy
新信息与旧内容冲突时：
1. 看日期，新来源一般取代旧的
2. 真矛盾则两方观点都记，标注日期来源
3. frontmatter标 `contradictions: [page-name]`
4. lint时flag给用户复查
