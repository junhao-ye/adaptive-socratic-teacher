# Adaptive Socratic Teacher

Adaptive Socratic Teacher 是一个用于引导式教学的 Agent Skill。它结合课程规划、苏格拉底式提问、提示阶梯、示范题和分层掌握度测试。

它不会一开始就直接给答案，而是先确认学习目标，提出一个聚焦问题，诊断学习者回答，再给出最小必要提示或简洁讲解。

## 适合用途

- 从零开始学习一个主题。
- 建立先修知识和主课程地图。
- 通过一次一问的方式练习理解。
- 做作业时获得提示，而不是拿到可提交的最终答案。
- 用简单、中等、迁移题测试掌握度。
- 按程度、语气、语言和学习偏好调整教学。

## 不适合用途

- 一句话定义或快速查询。
- 普通文章摘要。
- 直接完成作业答案。
- 课程营销文案。
- 医疗、法律、金融、安全或心理健康等高风险专业建议。

## 快速开始

```text
Use $adaptive-socratic-teacher 教我微积分，请用苏格拉底式提问。
```

```text
Use $adaptive-socratic-teacher /plan 光电效应，高中程度。
```

```text
Use $adaptive-socratic-teacher /hint
我卡在这道物理题，请给提示，不要直接给最终答案。
```

## 指令

| 指令 | 用途 |
| --- | --- |
| `/plan <topic>` | 建立先修路径和主课程地图。 |
| `/start [node]` | 开始第一个或指定课程节点。 |
| `/continue` | 从当前学习状态继续。 |
| `/hint` | 给最小提示，不给完整解法。 |
| `/test` | 执行分层掌握度测试。 |
| `/config` | 查看或更新学习者偏好。 |
| `/example` | 显示一段教学回合示例。 |

## 仓库内容

- `SKILL.md` - 技能执行入口。
- `references/` - 对话协议、课程评量、学习者配置和示例。
- `agents/interface.yaml` - 界面与兼容性信息。
- `manifest.json` - 生命周期与包 metadata。
- `SPEC.md` - 维护契约。
- `SOURCES.md` - 来源与决策记录。
- `evals/` - 触发评测和语义配置。
- `reports/` - 整合与质量记录。
- `docs/` - 多语言使用说明。

## 使用说明

- [English user guide](docs/usage.en.md)
- [繁體中文說明書](docs/usage.zh-TW.md)
- [简体中文说明书](docs/usage.zh-CN.md)
- [日本語利用ガイド](docs/usage.ja.md)

## 验证

此技能包已通过：

- `skill-writer` quick validation。
- Yao skill structural validation。
- Resource boundary check。
- Trigger evaluation。

## 授权

目前尚未声明授权。公开发布前请加入 `LICENSE` 文件。
