# Adaptive Socratic Teacher 利用ガイド

## 1. 概要

`adaptive-socratic-teacher` は、適応型のソクラテス式 AI チューター Skill です。学習目標を確認し、学習経路を作り、焦点を絞った質問を行い、学習者の回答を診断し、必要最小限のヒントや短い説明を返します。

基本方針は「先に発見を導き、必要なところだけ説明する」です。

## 2. 使うべき場面

向いていること:

- 新しいテーマを基礎から学ぶ。
- 前提知識と学習マップを作る。
- 一問ずつ対話しながら理解する。
- 宿題について、最終答案ではなくヒントを得る。
- 易しい問題・中程度の問題・転移問題で理解度を確認する。
- レベル、語調、言語、学習スタイルに合わせる。

向いていないこと:

- 一文だけの定義。
- 一般的な記事要約。
- 提出用の宿題答案作成。
- コース販売用コピー。
- 医療、法律、金融、安全、メンタルヘルスなどの高リスク専門助言。

## 3. クイックスタート

```text
Use $adaptive-socratic-teacher to teach me calculus with Socratic questions.
```

```text
Use $adaptive-socratic-teacher /plan the photoelectric effect, high school level.
```

```text
Use $adaptive-socratic-teacher /hint
I am stuck on this problem. Please give me a hint, not the final answer.
```

```text
Use $adaptive-socratic-teacher /test supply and demand.
```

## 4. コマンド

| コマンド | 役割 |
| --- | --- |
| `/plan <topic>` | 前提知識、メインの学習マップ、習熟度チェック、次のステップを作る。 |
| `/start [node]` | 最初または指定した学習ノードを開始する。 |
| `/continue` | 現在の学習状態から続ける。 |
| `/hint` | 完全な解答ではなく最小限のヒントを出す。 |
| `/test` | 段階的な習熟度チェックを行う。 |
| `/config` | 学習者の設定を表示または更新する。 |
| `/example` | 短いチューター応答例を表示する。 |

自然文でも使えますが、コマンドを使うとモードが明確になります。

## 5. 教学フロー

通常の流れ:

1. テーマ、レベル、目標、言語、資料を確認する。
2. テーマが曖昧な場合は、確認質問を一つだけ行う。
3. `/plan` では前提知識と概念マップを作る。
4. レッスン開始時は診断質問を一つ行う。
5. 学習者の回答を分類する。
6. フィードバック、小さなヒント、または短い説明を返す。
7. 次の質問を一つだけ行う。
8. 最後に短い振り返り、次のステップ、練習問題を提示する。

重要なのは、一度に複数の回答質問をしないことです。

## 6. 回答診断

| 状態 | シグナル | チューターの対応 |
| --- | --- | --- |
| Solid | 理由つきで正しい | 原理を確認し、転移問題を出す。 |
| Partial | 一部は正しいが不完全 | 良い部分を残し、絞った質問をする。 |
| Guessed | 答えは合っているが根拠が弱い | 理由、証拠、例を求める。 |
| Misconception | 自信はあるがモデルが誤っている | 対比質問で矛盾を見せる。 |
| Stuck | わからない、同じ所を回る | 小さなヒントを出し、質問を狭める。 |
| Overwhelmed | 混乱や誤答が多い | 要約し、難度を下げ、答えやすい質問にする。 |

## 7. ヒントの段階

学習者が詰まったときは、段階的に支援します。

1. 関連する概念を示す。
2. 間違った方向を一つ取り除く。
3. 小さなたとえを出す。
4. 欠けている一手を補う。
5. 短く説明し、学習者に言い換えてもらう。

学習者が明示的に求めるか、小さなヒントで進めない場合以外は、完全な説明に飛びません。

## 8. 学習計画の形式

`/plan` の出力例:

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

## 9. テストモード

`/test` は次の流れで進みます。

1. まず例題を一つ示す。
2. 一度に一問だけ出す。
3. 易しい問題・中程度の問題・転移問題を使う。
4. 各回答後に以下を返す。
   - 正誤
   - 推論へのフィードバック
   - 修正ステップ
   - 次の質問または復習目標

## 10. 学習者設定

デフォルト:

| 項目 | デフォルト |
| --- | --- |
| レベル | High school |
| 学習スタイル | Active |
| コミュニケーション | Socratic |
| トーン | Encouraging |
| 推論フレーム | Causal |
| 言語 | 学習者に合わせる |
| 絵文字 | 少量、任意 |

例:

```text
Use $adaptive-socratic-teacher /config
Depth: undergraduate
Learning style: visual and active
Tone: friendly
Language: Japanese
```

## 11. よく使う流れ

新しいテーマを学ぶ:

```text
Use $adaptive-socratic-teacher /plan linear algebra, beginner level.
```

レッスンを始める:

```text
Use $adaptive-socratic-teacher /start 1.1
```

宿題のヒント:

```text
Use $adaptive-socratic-teacher /hint
Problem: [問題を貼る]
My attempt: [自分の試みを貼る]
Please guide me with hints only.
```

理解度確認:

```text
Use $adaptive-socratic-teacher /test opportunity cost.
```

## 12. 良いプロンプト例

良い例:

```text
Use $adaptive-socratic-teacher to teach me Bayesian thinking. I am an undergraduate. Ask diagnostic questions first and use simple examples.
```

弱い例:

```text
Tell me everything about Bayesian thinking.
```

前者はレベル、モード、スタイルが明確です。後者は長い講義になりやすいです。

## 13. 境界

この Skill は以下を避けます。

- 提出用の宿題を直接完成させる。
- 実行していないツール実行を主張する。
- 提供されていないファイルや学習履歴を見たふりをする。
- 高リスク専門助言をする。
- 一度に複数の回答質問をする。

## 14. 一文まとめ

`adaptive-socratic-teacher` は、計画、質問、診断、ヒント、習熟度チェックを通じて、答えを受け取るだけでなく本当に理解するための AI チューター Skill です。
