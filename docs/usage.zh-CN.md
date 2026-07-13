# Adaptive Socratic Teacher 使用说明书

## 1. 技能概述

`adaptive-socratic-teacher` 是一个自适应苏格拉底式 AI 老师技能。它会帮助助手像学习教练一样工作：规划学习路径、提出聚焦问题、诊断学习者回答、给出小提示，并一步步检查掌握度。

核心原则是：先引导发现，再简洁讲解。

## 2. 适合使用的场景

适合：

- 从零开始学习一个主题。
- 建立先修知识和引导式课程地图。
- 通过一次一问的方式练习理解。
- 做作业时获得提示，而不是直接得到最终答案。
- 用简单题、中等题、迁移题检查掌握度。
- 按程度、语气、语言和学习偏好调整教学方式。

不适合：

- 一句话定义。
- 普通文章摘要。
- 可直接提交的作业答案。
- 课程营销文案。
- 医疗、法律、金融、安全或心理健康等高风险专业建议。

## 3. 快速开始

```text
Use $adaptive-socratic-teacher 教我微积分，请用苏格拉底式提问。
```

```text
Use $adaptive-socratic-teacher /plan 光电效应，高中程度。
```

```text
Use $adaptive-socratic-teacher /hint
我卡在这道题，请给提示，不要直接给最终答案。
```

```text
Use $adaptive-socratic-teacher /test 供需曲线。
```

## 4. 指令说明

| 指令 | 作用 |
| --- | --- |
| `/plan <topic>` | 建立先修路径、主课程地图、掌握度检查和下一步。 |
| `/start [node]` | 开始第一个或指定课程节点。 |
| `/continue` | 从当前学习状态继续。 |
| `/hint` | 给最小必要提示，不给完整解法。 |
| `/test` | 执行分层掌握度测试。 |
| `/config` | 查看或更新学习者偏好。 |
| `/example` | 显示一段简短的老师回合示例。 |

不用指令也可以，但指令能让模式更明确。

## 5. 教学流程

通常流程：

1. 确认主题、程度、目标、语言和材料。
2. 如果主题不清楚，先问一个澄清问题。
3. `/plan` 时建立先修路径和概念地图。
4. 开始上课时先问一个诊断问题。
5. 根据回答判断理解状态。
6. 给出反馈、小提示或简短讲解。
7. 再问一个下一步问题。
8. 用反思、下一步或练习题收束。

重点：一次只问一个需要你回答的问题。

## 6. 回答诊断

| 状态 | 信号 | 老师动作 |
| --- | --- | --- |
| Solid | 答对且能说明理由 | 确认理解，指出原则，问迁移题。 |
| Partial | 有正确片段但不完整 | 保留正确部分，追问一个精确问题。 |
| Guessed | 答案可能对但没有理由 | 要求解释原因、证据或例子。 |
| Misconception | 自信但模型错误 | 用对比问题暴露矛盾。 |
| Stuck | 不知道或反复绕圈 | 给小提示，把问题缩小。 |
| Overwhelmed | 挫折或错误太多 | 回顾、降低难度，给一个容易成功的问题。 |

## 7. 提示阶梯

当你卡住时，技能会逐步提示：

1. 指出相关概念。
2. 排除一个错误方向。
3. 给一个小类比。
4. 补上一个缺失步骤。
5. 给简短讲解，然后请你复述。

除非你明确要求，或者小提示失败，它不会直接跳到完整答案。

## 8. 课程规划格式

`/plan` 预期输出：

```markdown
## Learning Frame
- Topic:
- Assumed level:
- Goal:

## Prerequisite
0.1 ...
0.2 ...

## Main Guided Curriculum
1.1 [concept] - guiding question:
1.2 [concept] - guiding question:

## Mastery Checks
- Easy:
- Medium:
- Transfer:

## Next Step
[Start node or learner choice]
```

## 9. 测试模式

`/test` 会：

1. 先给一个示范题。
2. 一次问一题。
3. 使用简单、中等、迁移三种难度。
4. 每题后给：
   - 正确性判断
   - 推理反馈
   - 一个修正方向
   - 下一题或复习目标

## 10. 学习者配置

默认：

| 字段 | 默认 |
| --- | --- |
| 程度 | High school |
| 学习风格 | Active |
| 沟通风格 | Socratic |
| 语气 | Encouraging |
| 推理框架 | Causal |
| 语言 | 跟随学习者 |
| Emoji | 少量、可选 |

示例：

```text
Use $adaptive-socratic-teacher /config
Depth: undergraduate
Learning style: visual and active
Tone: friendly
Language: 简体中文
```

## 11. 常见工作流

学习新主题：

```text
Use $adaptive-socratic-teacher /plan 线性代数，初学者。
```

开始课程：

```text
Use $adaptive-socratic-teacher /start 1.1
```

作业提示：

```text
Use $adaptive-socratic-teacher /hint
题目：[贴上题目]
我的尝试：[贴上尝试]
请只给提示。
```

检查理解：

```text
Use $adaptive-socratic-teacher /test 机会成本。
```

## 12. 提示词写法建议

推荐：

```text
Use $adaptive-socratic-teacher 教我贝叶斯思维。我是本科程度，请先问诊断问题，并使用简单例子。
```

不推荐：

```text
Tell me everything about Bayesian thinking.
```

前者给了程度、模式和风格；后者容易变成长篇讲解。

## 13. 使用边界

技能会避免：

- 直接完成可提交作业。
- 假装执行了隐藏工具。
- 假装读过没有提供的文件或学习历史。
- 给高风险专业建议。
- 一次问多个需要回答的问题。

## 14. 一句话总结

`adaptive-socratic-teacher` 是一个通过规划、提问、诊断、提示和掌握度测试来帮助你真正学会知识的 AI 老师技能。
