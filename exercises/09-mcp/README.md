# 演習 09: MCP で外部ツール連携

**所要時間:** 25分  
**使う機能:** MCP (Model Context Protocol)

## 目的

MCP を使って Agent を**外部サービス・ツール**（GitHub、ブラウザ、データベース等）と接続する方法を学ぶ。

## 背景

MCP は AI が使える「USB ポート」のようなものです。Cursor に MCP サーバーを登録すると、Agent が GitHub の Issue 取得、ブラウザ操作、社内 API 呼び出しなどができるようになります。

## 手順

### Step 1: MCP 設定画面を開く

1. **Cursor Settings** → **MCP**（または **Features → MCP**）
2. 有効な MCP サーバー一覧を確認

よく使われる MCP:

| サーバー | 用途 |
|---------|------|
| GitHub | Issue / PR / リポジトリ操作 |
| Browser | Web ページの閲覧・操作 |
| Slack | メッセージ検索 |
| Postgres | DB クエリ |

### Step 2: ブラウザ MCP で Todo アプリを確認（有効な場合）

Browser MCP が有効なら Agent に:

```
Browser MCP を使って sample-app/src/index.html を開き、Todo を 1 件追加してスクリーンショットを取って。
```

MCP が無い場合は手動でブラウザ確認し、Step 3 へ。

### Step 3: GitHub MCP の概念演習

GitHub MCP が未設定でも、次のプロンプトで**設定手順**を Agent に調べさせる:

```
@Web

Cursor に GitHub MCP を設定する手順を 2026 年版で教えて。
Personal Access Token に必要なスコープも含めて。
```

設定できたら:

```
GitHub MCP を使って、自分の cursor-practice リポジトリに Issue を 1 件作成して。
タイトル: [演習09] MCP 動作確認
```

### Step 4: MCP なしでも使える CLI

Agent は MCP なしでも、インストール済み CLI を実行できます:

```
git --version
```

が動く環境なら:

```
git log --oneline -5

このリポジトリの直近 5 コミットを要約して。
```

### Step 5: 演習用メモ

`docs/mcp-notes.md` を作成し、自分の環境で使える MCP をメモ:

```markdown
# 私の MCP 設定メモ

## 有効なサーバー
- （ここに記入）

## 今後追加したい
- GitHub
- ...
```

Agent に依頼して作成しても OK。

## 成功条件

- [ ] MCP 設定画面を開いた
- [ ] MCP または CLI で「外部情報」を Agent に取得させた
- [ ] `docs/mcp-notes.md` にメモを残した

## セキュリティ注意

- MCP の API トークンは `.env` に置き、`.gitignore` に追加
- Auto-run ON 時は破壊的コマンドに注意

## 次の演習

[10-model-review](../10-model-review/README.md) — モデル選択と変更レビュー
