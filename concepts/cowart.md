---
title: Cowart 开源标注改图插件
created: 2026-06-26
updated: 2026-06-26
type: concept
tags: [tool, open-source, workflow]
sources: [raw/transcripts/BV1qLj26iE2o.md]
confidence: high
---

# Cowart 开源标注改图插件

Cowart（GitHub搜covert）是一个开源插件，给AI编程工具Codex接上**无限画布**（电子白板），实现"标注式改图"——像在打印稿上画红笔一样圈图、画箭头、写字，AI照做不误。^[raw/transcripts/BV1qLj26iE2o.md]

## 核心能力

- **标注式改图**：把图片放画布上，用画笔直接在图上：
  - 标题旁画箭头→写上"放大"
  - 某区域圈起来→打个叉→删除
  - 空白处框一块→写"加一句：每日限量30万"
- AI照着你画的标记重新生成干净海报，原图不动，新旧对照一目了然
- 本质上**从"你迁就AI"变成"AI迁就你"**——不用费劲把改图需求写成文字

## 作者与背景

- 开发者推特名：中二线
- 身份：豆包桌面端产品经理（专门研究人与AI交互）
- 设计理念："大家本来就在用截图工具打标记，我只是把这个动作做顺了"

## 使用须知
- 依赖image2模型，**仅在Codex上可用**
- 生成图消耗Codex额度
- 完全开源，GitHub搜covert

## 相关概念
- [[ai-information-sources]] — 博主推荐的其他工具
- [[qinghua-jiang-xuezhang|清华姜学长]] — 本工具推荐博主