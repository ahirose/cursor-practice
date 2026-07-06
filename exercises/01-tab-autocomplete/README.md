# 演習 01: Tab 補完

**所要時間:** 15分  
**使う機能:** Cursor Tab（インライン補完）

## 目的

コードを書いている最中に AI が「次に書くべきコード」を提案する **Tab 補完** に慣れる。

## 背景

Tab 補完は Cursor で最も頻繁に使う機能です。チャットを開かずに、タイピングの流れのまま AI の提案を取り込めます。

## 手順

### Step 1: 新しいファイルを作成

`sample-app/src/utils.js` を新規作成し、次の 1 行だけ入力してください:

```javascript
export function formatDate(date) {
```

入力後、**数秒待つ**とグレーのゴーストテキスト（提案）が表示されます。

### Step 2: 補完を受け入れる

- **Tab** — 提案全体を受け入れ
- **Ctrl + →** — 単語単位で部分的に受け入れ
- **Esc** — 提案を却下

Tab を押して関数本体を受け入れてみてください。

### Step 3: 続きを書く

同じファイルに、次のコメントだけ入力:

```javascript
// TODO: 残り日数を計算する関数
export function daysUntil
```

`daysUntil` まで入力すると、関数名と引数・本体の提案が出るはずです。受け入れて完成させてください。

### Step 4: 既存コードでの補完

`sample-app/src/app.js` を開き、`render()` 関数の末尾（`countEl.textContent` の行の後）に新しい行を追加:

```javascript
  // 空の状態のメッセージを表示
```

Tab 補完が「Todo が空のときの UI」を提案するか試してください。

## 成功条件

- [ ] `utils.js` に `formatDate` と `daysUntil` の 2 関数がある
- [ ] Tab キーで補完を受け入れた経験がある
- [ ] Ctrl+→ で部分受け入れを試した（任意）

## ヒント

- 補完が出ない → もう数文字入力する、または改行して次の行から書き始める
- 提案が的外れ → Esc で却下し、コメントで意図を書いてから再試行

## 次の演習

[02-inline-edit](../02-inline-edit/README.md) — 選択範囲を Ctrl+K で編集
