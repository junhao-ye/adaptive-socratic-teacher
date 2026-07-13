# Adaptive Socratic Teacher

Adaptive Socratic Teacher は、対話型の学習支援を行う Agent Skill です。カリキュラム設計、ソクラテス式の質問、ヒントの段階化、例題、習熟度チェックを組み合わせています。

最初から答えを提示するのではなく、学習目標を確認し、焦点を絞った質問を行い、学習者の回答を診断し、必要最小限のヒントまたは短い説明を返します。

## 得意なこと

- 新しいテーマを基礎から学ぶ。
- 前提知識と学習マップを作る。
- 一問ずつ進む対話型チュータリング。
- 宿題について、最終答案ではなくヒントを得る。
- 易しい問題・中程度の問題・転移問題で理解度を確認する。
- レベル、語調、言語、学習スタイルに合わせる。

## 向いていないこと

- 一文だけの定義や即時の事実確認。
- 一般的な記事要約。
- 提出用の宿題答案作成。
- コース販売用コピー。
- 医療、法律、金融、安全、メンタルヘルスなどの高リスク専門助言。

## クイックスタート

```text
Use $adaptive-socratic-teacher to teach me calculus with Socratic questions.
```

```text
Use $adaptive-socratic-teacher /plan the photoelectric effect, high school level.
```

```text
Use $adaptive-socratic-teacher /hint
I am stuck on this physics problem. Please give me a hint, not the final answer.
```

## コマンド

| コマンド | 目的 |
| --- | --- |
| `/plan <topic>` | 前提知識とメインの学習マップを作る。 |
| `/start [node]` | 最初または指定した学習ノードを始める。 |
| `/continue` | 現在の学習状態から続ける。 |
| `/hint` | 完全な解答ではなく最小限のヒントを出す。 |
| `/test` | 段階的な習熟度チェックを行う。 |
| `/config` | 学習者の設定を表示または更新する。 |
| `/example` | 短いチューター応答例を表示する。 |

## リポジトリ構成

- `SKILL.md` - Skill の実行エントリーポイント。
- `references/` - 対話プロトコル、カリキュラム評価、学習者設定、例。
- `agents/interface.yaml` - インターフェースと互換性メタデータ。
- `manifest.json` - ライフサイクルとパッケージ metadata。
- `SPEC.md` - 保守契約。
- `SOURCES.md` - ソースと意思決定の記録。
- `evals/` - トリガー評価と semantic config。
- `reports/` - 統合と品質に関する記録。
- `docs/` - 多言語ユーザーガイド。

## ドキュメント

- [English user guide](docs/usage.en.md)
- [繁體中文說明書](docs/usage.zh-TW.md)
- [简体中文说明书](docs/usage.zh-CN.md)
- [日本語利用ガイド](docs/usage.ja.md)

## 検証

この Skill パッケージは以下で検証されています。

- `skill-writer` quick validation
- Yao skill structural validation
- Resource boundary check
- Trigger evaluation

## ライセンス

このプロジェクトは [MIT License](LICENSE) のもとで公開されています。
