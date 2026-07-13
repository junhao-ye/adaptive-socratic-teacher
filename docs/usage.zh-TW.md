# Adaptive Socratic Teacher 技能介紹及使用說明書

## 1. 技能定位

`adaptive-socratic-teacher` 是一個「自適應蘇格拉底式 AI 老師」技能。它不是單純把答案講出來，而是先理解學習者程度、建立學習路徑、提出引導問題、診斷回答狀態，再給出最小必要提示或精簡講解。

它適合用在：

- 想從零開始學一個主題。
- 想讓 AI 先問問題，而不是直接灌輸答案。
- 想建立課程大綱、先修知識和學習節點。
- 想用提示方式完成作業理解，而不是代寫答案。
- 想測試自己是否真正理解某個概念。
- 想依照程度、語言、學習風格調整教學方式。

它不適合用在：

- 只要一句定義或快速查詢。
- 只要文章摘要。
- 要 AI 直接完成作業並拿去提交。
- 要寫課程銷售文案。
- 醫療、法律、金融、安全、心理健康等高風險專業建議。

## 2. 核心特色

| 特色 | 說明 |
| --- | --- |
| 蘇格拉底式引導 | 先問問題，再根據回答推進教學。 |
| 課程規劃 | 可建立先修知識、主課程節點和掌握度檢查。 |
| 答案診斷 | 會判斷學習者回答是扎實、部分理解、猜測、誤解、卡住或過載。 |
| 提示階梯 | 先給小提示，再逐步加深，不會一開始就給完整答案。 |
| 分層測驗 | 透過簡單題、中等題、遷移題測試理解。 |
| 學習者配置 | 支援程度、學習風格、語氣、推理方式和語言調整。 |
| 作業輔導邊界 | 幫你學方法，但不直接代寫最終答案。 |

## 3. 安裝狀態

此技能已安裝在本機 Codex skills 目錄：

```text
C:\Users\mai_k\.codex\skills\adaptive-socratic-teacher
```

輸出備份位置：

```text
C:\Users\mai_k\Documents\Codex\2026-06-28\new-chat\outputs\adaptive-socratic-teacher
```

壓縮包位置：

```text
C:\Users\mai_k\Documents\Codex\2026-06-28\new-chat\outputs\adaptive-socratic-teacher.zip
```

## 4. 最快開始

在對話中直接指定技能名稱即可：

```text
Use $adaptive-socratic-teacher to teach me calculus with Socratic questions.
```

中文也可以：

```text
Use $adaptive-socratic-teacher 教我光電效應，高中程度，請先問問題再解釋。
```

如果想先做課程規劃：

```text
Use $adaptive-socratic-teacher /plan 機器學習，從零基礎開始。
```

如果想被測驗：

```text
Use $adaptive-socratic-teacher /test 測試我對供需曲線的理解。
```

如果正在做題但不想直接拿答案：

```text
Use $adaptive-socratic-teacher /hint
我卡在這題，請不要直接給答案，先給我一個提示。
```

## 5. 指令總覽

| 指令 | 用途 | 適合情境 |
| --- | --- | --- |
| `/plan <topic>` | 建立先修與主課程 | 想先知道學習路線 |
| `/start [node]` | 開始第一個或指定課程節點 | 已有課程，要開始學 |
| `/continue` | 延續目前學習狀態 | 已經上過一段，想接著學 |
| `/hint` | 給最小提示，不給完整答案 | 做題卡住、想自己推理 |
| `/test` | 進行掌握度測試 | 想檢查是否真的理解 |
| `/config` | 查看或調整學習偏好 | 想改程度、語氣、語言 |
| `/example` | 生成示範教學回合 | 想看技能會怎麼教 |

## 6. 常用啟動模板

### 6.1 從零開始學

```text
Use $adaptive-socratic-teacher to teach me [主題] from the basics. Ask one question at a time.
```

範例：

```text
Use $adaptive-socratic-teacher to teach me linear algebra from the basics. Ask one question at a time.
```

### 6.2 先規劃課程

```text
Use $adaptive-socratic-teacher /plan [主題]，[程度]，[目標]
```

範例：

```text
Use $adaptive-socratic-teacher /plan 深度學習，研究生程度，目標是能讀懂 Transformer 論文。
```

### 6.3 蘇格拉底式教學

```text
Use $adaptive-socratic-teacher to teach me [主題]. Do not explain everything at once. Ask diagnostic questions first.
```

範例：

```text
Use $adaptive-socratic-teacher to teach me opportunity cost. Do not explain everything at once. Ask diagnostic questions first.
```

### 6.4 作業輔導，不要代寫

```text
Use $adaptive-socratic-teacher /hint
這是我的題目：[貼上題目]
這是我的嘗試：[貼上嘗試]
請只給提示，不要直接給最終答案。
```

### 6.5 測試理解

```text
Use $adaptive-socratic-teacher /test [主題]
請先給一個示範題，再用簡單、中等、遷移三種難度測我。
```

### 6.6 調整學習配置

```text
Use $adaptive-socratic-teacher /config
請把我的程度設為 undergraduate，語氣 friendly，學習風格 active，語言使用繁體中文。
```

## 7. 教學流程長什麼樣

這個技能通常會按以下順序工作：

1. 確認主題、程度、目標、語言和材料。
2. 如果主題不清楚，先問一個澄清問題。
3. 如果使用 `/plan`，先建立先修路線和主課程地圖。
4. 如果開始上課，先問一個診斷問題。
5. 根據你的回答判斷理解狀態。
6. 給出回饋、提示或精簡講解。
7. 再問下一個問題。
8. 最後用反思、下一步或練習題收束。

重點是：它每次只會問一個需要你回答的問題，避免一次丟太多內容。

## 8. 回答診斷機制

技能會根據你的回答做教學判斷：

| 狀態 | 代表意思 | 老師會怎麼做 |
| --- | --- | --- |
| Solid | 答對且能說出理由 | 確認理解，追問遷移題 |
| Partial | 有部分正確但不完整 | 保留正確部分，再問一個精準問題 |
| Guessed | 答案可能對，但缺理由 | 要你說明原因或舉例 |
| Misconception | 有明確誤解 | 用對比問題暴露矛盾 |
| Stuck | 卡住或不知道 | 給小提示，再把問題縮小 |
| Overwhelmed | 錯誤太多或感到挫折 | 暫停、回顧、降低難度 |

## 9. 提示階梯

當你卡住時，它不會立刻給完整解法，而會逐步提示：

1. 指出相關概念。
2. 排除一條錯誤方向。
3. 給一個小比喻。
4. 補上一個缺失步驟。
5. 給精簡講解，然後請你用自己的話重述。

這能保留學習者自己的推理空間。

## 10. 課程規劃格式

使用 `/plan` 時，預期會得到類似結構：

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

其中：

- `Prerequisite` 是先修知識。
- `Main Guided Curriculum` 是主課程。
- 每個主課程節點都會有一個 guiding question。
- `Mastery Checks` 用來檢查掌握度。

## 11. 測驗模式

使用 `/test` 時，技能會：

1. 先給一個 worked example。
2. 問一題簡單題。
3. 問一題中等題。
4. 問一題遷移題。
5. 每題後給出：
   - 正確性判斷
   - 推理回饋
   - 一個修正方向
   - 下一題或複習目標

測驗不是為了打分數，而是為了定位你卡在哪一層理解。

## 12. 學習者配置

預設配置：

| 欄位 | 預設 |
| --- | --- |
| 程度 | High school |
| 學習風格 | Active |
| 溝通風格 | Socratic |
| 語氣 | Encouraging |
| 推理框架 | Causal |
| 語言 | 跟隨使用者 |
| Emoji | 少量、可選 |

可調整配置：

```text
Use $adaptive-socratic-teacher /config
Depth: undergraduate
Learning style: visual and active
Communication style: Socratic
Tone: friendly
Reasoning frame: causal
Language: 繁體中文
```

## 13. 完整使用範例

### 範例一：學習光電效應

使用者：

```text
Use $adaptive-socratic-teacher /plan 光電效應，高中程度。
```

技能預期會產出：

- 光電效應前需要知道的原子結構、能階、光的波動性、光子等先修。
- 主課程節點，例如光電效應現象、愛因斯坦解釋、功函數、閾頻、動能。
- 每個節點附一個引導問題。
- 最後邀請你從 `1.1` 開始。

接著：

```text
Use $adaptive-socratic-teacher /start 1.1
```

技能會先問診斷問題，而不是直接講完整章節。

### 範例二：作業卡住

使用者：

```text
Use $adaptive-socratic-teacher /hint
題目問我為什麼提高光強不一定提高電子動能。我覺得光越強能量越大，但不確定。
```

技能應該會：

- 指出你的想法中「光越強」可能混淆了總能量與單個光子能量。
- 不直接給完整答案。
- 問你：單個光子的能量和哪個物理量有關？

### 範例三：測試供需曲線

使用者：

```text
Use $adaptive-socratic-teacher /test 供需曲線。
```

技能應該會：

- 先示範一題。
- 再問簡單題，例如價格上升時需求量如何變化。
- 再問中等題，例如供給下降與需求上升同時發生。
- 再問遷移題，例如套用到房租、晶片或咖啡市場。

## 14. 好用提示詞寫法

更好的寫法：

```text
Use $adaptive-socratic-teacher to teach me Bayesian thinking. I am an undergraduate. Ask diagnostic questions first and use simple examples.
```

普通但可用：

```text
Use $adaptive-socratic-teacher teach me Bayesian thinking.
```

不推薦：

```text
Tell me everything about Bayesian thinking.
```

原因：第三種太泛，容易變成長篇講解，不利於蘇格拉底式互動。

## 15. 使用邊界與注意事項

這個技能會避免：

- 直接代寫作業。
- 假裝讀過不存在的文件。
- 假裝執行過沒有執行的工具。
- 在高風險專業領域給確定性建議。
- 一次問多個問題造成負擔。

如果你想要快速答案，可以明確說：

```text
請先給我一個簡短答案，再用蘇格拉底方式檢查我是否理解。
```

這樣技能會在「直接說明」和「引導提問」之間取得平衡。

## 16. 常見問題

### Q1：一定要用英文指令嗎？

不用。技能名稱用英文即可，後面的需求可以用中文。

```text
Use $adaptive-socratic-teacher 教我微積分，請用繁體中文。
```

### Q2：可以直接說「教我某某」嗎？

可以，但建議補上程度和目標。

較好：

```text
Use $adaptive-socratic-teacher 教我線性代數，我是大一程度，目標是能理解矩陣乘法的意義。
```

### Q3：為什麼它一直問我問題？

因為這個技能的核心是蘇格拉底式教學。它會透過你的回答判斷你真正理解到哪裡，再決定下一步。

### Q4：如果我只想聽講解怎麼辦？

可以這樣說：

```text
Use $adaptive-socratic-teacher 請先用簡短講解介紹主題，然後再問我一個檢查理解的問題。
```

### Q5：它能幫我做作業嗎？

能幫你理解題目、拆解方法、給提示、做類題，但不應直接生成可提交的最終答案。

### Q6：它能記住我的長期學習進度嗎？

目前不會在對話外永久保存學習狀態。你可以在新對話開頭貼上目前進度，讓它接續。

## 17. 推薦工作流

初學一個新主題：

```text
Use $adaptive-socratic-teacher /plan [主題]，[程度]，[目標]
```

選一個節點開始：

```text
Use $adaptive-socratic-teacher /start 1.1
```

學到一半卡住：

```text
Use $adaptive-socratic-teacher /hint
我卡在：[描述卡點]
```

學完後測試：

```text
Use $adaptive-socratic-teacher /test [主題]
```

最後要求複習：

```text
Use $adaptive-socratic-teacher 請總結我剛才的薄弱點，並給下一步練習。
```

## 18. 一句話記住它

`adaptive-socratic-teacher` 是一個「先問、再診斷、再提示、最後測 mastery」的 AI 老師技能。它最適合拿來真正學會一個東西，而不是快速拿到一個答案。
