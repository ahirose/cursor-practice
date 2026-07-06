# 演習 07: Rules でプロジェクト規約を設定

**所要時間:** 25分  
**使う機能:** Cursor Rules

## 目的

`.cursor/rules/` にプロジェクト規約を書き、**毎回同じ指示を繰り返さなくて済む**ようにする。

## 背景

Rules は Agent が会話を始めるたびに自動で読み込む指示書です。「コメントは日本語」「console.log 禁止」など、チーム共通のルールをここに置きます。

## このリポジトリのサンプル Rule

`.cursor/rules/sample-app-conventions.mdc` を確認してください。

## 手順

### Step 1: 既存 Rule を読む

`.cursor/rules/sample-app-conventions.mdc` を開き、内容を理解。

### Step 2: Rule を有効化した状態で Agent を試す

**新しいチャット**を開き（Rules は新規チャットで反映されやすい）:

```
@sample-app/src/app.js

新しい Todo 項目に「作成日時」を表示する機能を追加して。
```

→ Rule に従い、コメントが日本語・`const` 使用・等のはず。

### Step 3: 自分の Rule を追加

`.cursor/rules/my-preferences.mdc` を新規作成:

```markdown
---
description: 個人の好み設定（演習用）
globs: sample-app/**/*
alwaysApply: false
---

# 個人ルール

- 変数名は英語、UI 表示テキストは日本語
- 新規関数には必ず JSDoc を付ける
- CSS の色は #2563eb をプライマリカラーとして統一
```

### Step 4: Rule の効き方をテスト

新しいチャットで:

```
@sample-app/src/app.js

formatTodoText という、Todo テキストの前後空白を trim するユーティリティ関数を追加して。
```

JSDoc が付くか、色指定が統一されるか確認。

### Step 4: Rule を改善

AI が Rule を無視した場合:

1. Rule を**短く**する（長い Rule は無視されやすい）
2. `globs` で適用範囲を絞る
3. 具体例を 1 つ入れる

例:

```markdown
## 例

// ✅ Good
/** Todo テキストを整形する */
export function formatTodoText(text) {
  return text.trim();
}
```

## 成功条件

- [ ] `.cursor/rules/` の仕組みを理解した
- [ ] サンプル Rule + 自作 Rule の 2 つがある
- [ ] Rule 適用後の Agent 出力で差を確認した

## Rules のアンチパターン

| ❌ 避ける | ✅ 代わりに |
|----------|-----------|
| ESLint で済むことを Rule に | linter を使う |
| 50 行の Rule | 10 行以内 + 具体例 1 つ |
| すべて alwaysApply | globs で必要なファイルだけ |

## 次の演習

[08-skills](../08-skills/README.md) — Skills でワークフロー化
