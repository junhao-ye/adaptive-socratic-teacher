# Adaptive Socratic Teacher

Adaptive Socratic Teacher 是一個用於引導式教學的 Agent Skill。它結合課程規劃、蘇格拉底式提問、提示階梯、示範題與分層掌握度測驗。

它不會一開始就把答案倒出來，而是先確認學習目標，提出一個聚焦問題，診斷學習者回答，再給出最小必要提示或精簡講解。

## 適合用途

- 從零開始學一個主題。
- 建立先修知識與主課程地圖。
- 透過一次一問的方式練習理解。
- 做作業時取得提示，而不是拿到可提交的最終答案。
- 用簡單、中等、遷移題測試掌握度。
- 依照程度、語氣、語言和學習偏好調整教學。

## 不適合用途

- 一句話定義或快速查詢。
- 一般文章摘要。
- 直接完成作業答案。
- 課程銷售文案。
- 醫療、法律、金融、安全或心理健康等高風險專業建議。

## 快速開始

```text
Use $adaptive-socratic-teacher 教我微積分，請用蘇格拉底式提問。
```

```text
Use $adaptive-socratic-teacher /plan 光電效應，高中程度。
```

```text
Use $adaptive-socratic-teacher /hint
我卡在這題物理題，請給提示，不要直接給最終答案。
```

## 指令

| 指令 | 用途 |
| --- | --- |
| `/plan <topic>` | 建立先修路徑與主課程地圖。 |
| `/start [node]` | 開始第一個或指定課程節點。 |
| `/continue` | 從目前學習狀態繼續。 |
| `/hint` | 給最小提示，不給完整解法。 |
| `/test` | 執行分層掌握度測驗。 |
| `/config` | 查看或更新學習者偏好。 |
| `/example` | 顯示一段教學回合範例。 |

## 倉庫內容

- `SKILL.md` - 技能執行入口。
- `references/` - 對話協議、課程評量、學習者配置與範例。
- `agents/interface.yaml` - 介面與相容性資訊。
- `manifest.json` - 生命週期與套件 metadata。
- `SPEC.md` - 維護契約。
- `SOURCES.md` - 來源與決策紀錄。
- `evals/` - 觸發評測與語義設定。
- `reports/` - 整合與品質紀錄。
- `docs/` - 多語使用說明。

## 使用說明

- [English user guide](docs/usage.en.md)
- [繁體中文說明書](docs/usage.zh-TW.md)
- [简体中文说明书](docs/usage.zh-CN.md)
- [日本語利用ガイド](docs/usage.ja.md)

## 驗證

此技能包已通過：

- `skill-writer` quick validation。
- Yao skill structural validation。
- Resource boundary check。
- Trigger evaluation。

## 授權

本專案採用 [MIT License](LICENSE) 授權。
