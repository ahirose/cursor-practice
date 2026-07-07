# Cursor 実践教材 — よくある使い方 Top 10

Cursor を「触ったことはあるが、日常開発に組み込めていない」方向けの、**手を動かして覚える**演習教材です。

**GitHub:** https://github.com/ahirose/cursor-practice

## この教材で身につくこと

| # | 使い方 | いつ使う？ |
|---|--------|-----------|
| 1 | [Tab 補完](./exercises/01-tab-autocomplete/README.md) | コードを書いている最中、続きを提案してほしい |
| 2 | [Inline Edit (Ctrl+K)](./exercises/02-inline-edit/README.md) | 1ファイル内の小さな修正・リファクタ |
| 3 | [Ask モードで理解](./exercises/03-ask-mode/README.md) | コードベースを**変更せず**調査・理解したい |
| 4 | [Agent で機能実装](./exercises/04-agent/README.md) | 複数ファイル・ターミナル操作が必要なタスク |
| 5 | [Plan Mode で計画](./exercises/05-plan-mode/README.md) | 大きな変更の前に方針を固めたい |
| 6 | [@ メンションでコンテキスト指定](./exercises/06-at-mentions/README.md) | 必要なファイルだけ AI に渡したい |
| 7 | [Rules で規約を設定](./exercises/07-rules/README.md) | 毎回同じ指示を繰り返したくない |
| 8 | [Skills でワークフロー化](./exercises/08-skills/README.md) | 定型作業を `/コマンド` で呼び出したい |
| 9 | [MCP で外部ツール連携](./exercises/09-mcp/README.md) | GitHub・ブラウザなど外部サービスと連携 |
| 10 | [モデル選択と変更レビュー](./exercises/10-model-review/README.md) | 出力品質のコントロールと安全なマージ |

## クイックスタート

### 1. このリポジトリを Cursor で開く

```powershell
git clone https://github.com/ahirose/cursor-practice.git
cd cursor-practice
cursor .
```

すでにクローン済みの場合は `cursor .` でフォルダを開くだけで OK です。

### 2. サンプルアプリを確認

```powershell
# sample-app/src/index.html をブラウザで開く
start sample-app\src\index.html
```

シンプルな Todo アプリが表示されます。各演習でこのアプリを題材にします。

### 3. 演習の進め方

1. `exercises/01-tab-autocomplete/` から順番に進める（番号順がおすすめ）
2. 各フォルダの `README.md` に**目的・手順・成功条件**が書いてあります
3. 各演習は **15〜30 分** を目安に
4. 詰まったら `docs/troubleshooting.md` を参照

## 4つの AI サーフェス（覚えておくと効く）

```
タスクの規模 ──────────────────────────────────────────────►

 Tab          Inline Edit      Ask / Chat        Agent
 (Tab キー)    (Ctrl+K)         (Ctrl+L)         (Ctrl+I)
   │               │                │                │
 1行〜数行      1関数〜1ファイル    理解・調査      複数ファイル
 リアルタイム   選択範囲を編集     変更なし        ターミナル実行
```

**経験則:** 1関数なら Ctrl+K、3〜10ファイルなら Agent、リポジトリ全体の調査なら Ask → Plan → Agent。

## ディレクトリ構成

```
cursor-practice/
├── README.md                 ← 今読んでいるファイル
├── docs/
│   ├── setup.md              ← 初回セットアップ
│   ├── top10-cheatsheet.md   ← 1枚チートシート
│   └── troubleshooting.md    ← よくあるつまずき
├── exercises/                ← 演習（01〜10）
├── sample-app/               ← 演習用 Todo アプリ
└── .cursor/
    └── rules/                ← 演習07で使うサンプル Rules
```

## 推奨学習スケジュール

| 日 | 内容 | 時間 |
|----|------|------|
| 1日目 | セットアップ + 演習 01〜03 | 1.5h |
| 2日目 | 演習 04〜06 | 1.5h |
| 3日目 | 演習 07〜09 | 1.5h |
| 4日目 | 演習 10 + 総合課題 | 1h |

## 総合課題（すべて終わったら）

Agent に次のプロンプトを送って、学んだことを総合的に使ってみましょう:

```
@sample-app/src/app.js @sample-app/src/styles.css

Todo アプリに以下を追加してください:
1. フィルター（すべて / 未完了 / 完了済み）
2. ダークモード切り替え
3. 変更後、ブラウザで動作確認できることを README に記載

Plan Mode で計画を立ててから実装してください。
```

## 参考リンク

- [Cursor 公式ドキュメント](https://cursor.com/docs)
- [Agent のベストプラクティス](https://cursor.com/blog/agent-best-practices)
- [Rules / Skills のカスタマイズ](https://cursor.com/learn/customizing-agents)

## ライセンス

MIT — 自由に学習・改変・共有してください。
