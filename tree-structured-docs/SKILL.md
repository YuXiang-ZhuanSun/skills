---
name: tree-structured-docs
description: Restructure flat, confusing, or interface-heavy Chinese or English documentation into a tree-shaped 总-分-总 / overview-detail-synthesis manual with a mind-map overview, grouped sections, clear reading order, and a final checklist. Use when writing or revising README files, user manuals, design docs, architecture docs, API guides, onboarding docs, or any document that currently reads like a long flat list of points.
---

# Tree Structured Docs / 树形结构文档

Use this skill to turn documentation from a flat list into a guided tree.

使用这个 skill，把“平铺条目式文档”重构成“树形总分总文档”。

The goal is not to add more text. The goal is to help readers build a mental map before they see details.

目标不是增加字数，而是让读者在进入细节前先建立心智地图。

## Core Shape / 核心结构

Use a 总-分-总 / overview-detail-synthesis structure:

```text
总 / Overview:
  +-- who the document is for / 谁读
  +-- what the reader should do after reading / 读完能做什么
  +-- one-sentence mental model / 一句话心智模型
  +-- tree or mind-map overview / 树形图或思维导图

分 / Details:
  +-- grouped branches, not flat lists / 分组分支，而不是平铺列表
  +-- concept -> relationship -> mechanism -> example / 概念 -> 关系 -> 机制 -> 例子
  +-- each branch answers one reader question / 每个分支回答一个读者问题

总 / Synthesis:
  +-- recap how parts cooperate / 回到整体协作关系
  +-- checklist / 检查表
  +-- learning path or next exercise / 学习路径或下一步练习
```

## Diagnose the Current Failure / 先诊断问题

Look for these failure modes before rewriting:

先判断文档坏在哪里，再改写。

```text
Flat list / 平铺列表:
  Many peer headings with no hierarchy.
  很多同级标题，没有层次。

Interface encyclopedia / 接口百科:
  APIs are explained one by one, but the reader cannot see how they cooperate.
  接口逐个解释了，但读者看不出它们如何一起工作。

Missing map / 缺少地图:
  Details appear before the reader knows the whole system.
  读者还没看到整体，就被推入细节。

Wrong order / 顺序错误:
  Advanced concepts appear before the basic workflow.
  高级概念出现在基本流程之前。

No return / 没有回到整体:
  The document ends after details, without summary, checklist, or learning path.
  文档讲完细节就结束，没有总结、检查表或学习路径。
```

## Workflow / 工作流

1. Identify the reader and task. / 先确定读者和任务。

```text
Reader / 读者:
  Who opens this document?
  谁会打开这份文档？

Task / 任务:
  What should they be able to do after reading?
  读完后应该能做什么？

Primary confusion / 主要困惑:
  What blocks understanding today?
  现在最阻碍理解的是什么？
```

2. Extract all topics. / 抽取所有主题。

Do not preserve current heading levels by default. Treat headings as raw material.

不要默认保留原来的标题层级。把原标题当作素材。

Group topics into 3-6 major branches. Good branch names answer reader questions:

把主题合并成 3-6 个大分支。好的分支名应该回答读者问题：

```text
What is this? / 这是什么？
How do the parts work together? / 这些部分如何合作？
What are the core concepts? / 核心概念是什么？
How do I use it? / 我怎么使用？
How do I debug or validate it? / 我如何调试或验证？
What should I do next? / 下一步做什么？
```

3. Build the mind-map overview. / 建立思维导图式总览。

Place this near the top:

把它放在文档靠前的位置：

```text
System / Topic
  +-- Branch A / 分支 A
  |     +-- Concept / 概念
  |     +-- Mechanism / 机制
  |     +-- Example / 例子
  |
  +-- Branch B / 分支 B
  |     +-- ...
  |
  +-- Summary / 总结
        +-- checklist / 检查表
        +-- learning path / 学习路径
```

4. Write each branch in layered order. / 每个分支按层次写。

For each branch:

每个分支都遵守：

```text
Purpose / 目的:
  Why this branch exists.
  这个分支为什么存在。

Concepts / 概念:
  Define new terms before using them.
  新概念先解释，再使用。

Relationships / 关系:
  Show how parts cooperate.
  先说明各部分如何协作。

Mechanism / 机制:
  Explain APIs, rules, or implementation details.
  再解释 API、规则或实现细节。

Example / 例子:
  Show one concrete path.
  给一条具体链路。

Practical rule / 实用规则:
  End with a short guideline.
  最后给一句可执行原则。
```

5. Collapse long peer lists. / 折叠过长平铺列表。

```text
Before / 修改前:
  ## Interface A
  ## Interface B
  ## Interface C
  ## Interface D
  ## Interface E

After / 修改后:
  ## Core Interfaces / 核心接口
  ### Time-related interfaces / 时间相关接口
  ### Execution interfaces / 执行接口
  ### Observability interfaces / 观测接口
```

6. Add synthesis at the end. / 结尾回到整体。

End with one or more of:

结尾至少包含其中一类：

```text
Mental model recap / 心智模型回顾
Good implementation checklist / 好实现检查表
Common mistakes / 常见错误
Recommended reading path / 推荐阅读路径
Next exercise / 下一步练习
```

## Writing Rules / 写作规则

- Prefer 3-6 top-level sections after the intro. / 引言之后最好只有 3-6 个一级大节。
- Avoid 10+ top-level peer headings unless the document is a reference index. / 除非是索引，否则避免 10 个以上同级大标题。
- Introduce a concept before using it in examples. / 新概念先解释，再进入例子。
- Explain relationships before listing APIs. / 先讲协作关系，再列接口。
- Put examples after the reader understands the cooperating parts. / 读者理解协作关系后再给例子。
- Use tree diagrams for structure and flow diagrams for behavior. / 结构用树形图，行为用流程图。
- Keep useful reference detail, but nest it under meaningful groups. / 保留有用细节，但放到有意义的分组下。
- Preserve useful existing content; change shape first, wording second. / 先改结构，再改句子。
- Do not hide important warnings at the end. / 重要边界和警告不要藏到最后。

## User Manual Target Structure / 用户说明书目标结构

English:

```text
# Manual Title

## Overview
  +-- one-sentence mental model
  +-- mind-map
  +-- glossary
  +-- complete example path

## Part 1: Runtime / Workflow
  +-- what happens first
  +-- how execution proceeds
  +-- minimal runnable example

## Part 2: Core Concepts and APIs
  +-- grouped by role, not alphabetically
  +-- each API tied back to the workflow

## Part 3: Building Real Things
  +-- templates
  +-- patterns
  +-- examples

## Part 4: Debugging and Validation
  +-- logs
  +-- stats
  +-- tests
  +-- common mistakes

## Summary
  +-- checklist
  +-- learning path
```

中文：

```text
# 用户说明书标题

## 总览：先建立心智地图
  +-- 一句话理解
  +-- 思维导图
  +-- 关键术语
  +-- 一条完整示例链路

## 第一部分：运行闭环
  +-- 第一件事是什么
  +-- 执行如何推进
  +-- 最小可运行例子

## 第二部分：核心概念和接口
  +-- 按角色分组，不按接口字母表平铺
  +-- 每个接口都要回到运行闭环

## 第三部分：开发真实模型
  +-- 模板
  +-- 模式
  +-- 例子

## 第四部分：调试和验证
  +-- 日志
  +-- 统计
  +-- 测试
  +-- 常见错误

## 总结：检查表和学习路径
```

## Architecture Doc Target Structure / 架构文档目标结构

English:

```text
# Architecture Title

## System Positioning
## Architecture Map
## Layer Responsibilities
## Data / Control Flow
## Extension Points
## Boundaries and Non-goals
## Review Checklist
```

中文：

```text
# 架构文档标题

## 系统定位
## 架构地图
## 分层职责
## 数据流 / 控制流
## 扩展点
## 边界和非目标
## 评审检查表
```

## Quality Check / 质量检查

Before finishing, verify:

完成前检查：

```text
The first page gives a useful map.
第一页是否给了有用地图？

The top-level headings form a tree, not a list.
一级标题是否形成树，而不是列表？

Each major section answers one reader question.
每个大节是否回答一个读者问题？

New concepts are introduced before use.
新概念是否先解释再使用？

APIs are grouped by how they cooperate.
接口是否按协作关系分组？

There is at least one complete end-to-end example.
是否至少有一个端到端完整例子？

The ending returns to a summary/checklist.
结尾是否回到总结或检查表？

The document can be skimmed by reading only headings and diagrams.
只读标题和图，是否也能大致理解文档？
```
