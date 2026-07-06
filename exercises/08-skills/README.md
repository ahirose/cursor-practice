# 演習 08: Skills でワークフロー化

**所要時間:** 25分  
**使う機能:** Agent Skills

## 目的

繰り返し行う作業手順を **Skill** としてパッケージ化し、`/` コマンドで呼び出す。

## 背景

- **Rules** = 毎回自動で読む「常識」
- **Skills** = 必要なときだけ読む「専門手順書」

「PR を作る」「リリースノートを書く」など、定型フローは Skill が向いています。

## 手順

### Step 1: サンプル Skill を読む

`.cursor/skills/todo-app-check/SKILL.md` を開いて構造を確認。

### Step 2: Skill を手動で呼び出す

Agent チャットで:

```
/todo-app-check
```

または:

```
Todo アプリの動作確認 Skill を使って、sample-app をチェックして。
```

Skill に書かれた手順どおりにチェックが走るか確認。

### Step 3: 自作 Skill を作成

`.cursor/skills/add-todo-feature/SKILL.md` を作成:

```markdown
---
name: add-todo-feature
description: sample-app に新機能を追加する標準手順
---

# Todo 機能追加 Skill

## 手順

1. `@sample-app/src/app.js` `@sample-app/src/index.html` `@sample-app/src/styles.css` を読む
2. ユーザーの要件を確認（足りなければ質問）
3. app.js → index.html → styles.css の順で変更
4. `start sample-app\src\index.html` 相当で動作確認方法を案内
5. 変更ファイル一覧とテスト手順をまとめて報告

## 制約

- localStorage のキー `cursor-practice-todos` は変更しない
- 外部ライブラリは追加しない（バニラ JS のみ）
```

### Step 4: 自作 Skill を試す

新しいチャット:

```
/add-todo-feature

「Todo をダブルクリックで編集」機能を追加したい
```

### Step 5: ビルトイン Skill を試す（任意）

Cursor 付属の Skill 例:

```
/create-rule

sample-app 用に「テスト手順を必ず README に書く」Rule を作って
```

## 成功条件

- [ ] Skill の `SKILL.md` 構造（frontmatter + 手順）を理解
- [ ] サンプル Skill を 1 回実行した
- [ ] 自作 Skill を 1 つ作成し実行した

## Rules vs Skills 再確認

| 質問 | Rules | Skills |
|------|-------|--------|
| 毎回読む？ | はい | 必要時のみ |
| 例 | 命名規則 | PR 作成手順 |
| 呼び出し | 自動 | `/skill名` または Agent が判断 |

## 次の演習

[09-mcp](../09-mcp/README.md) — MCP で外部ツール連携
