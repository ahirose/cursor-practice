# 初回セットアップ

Cursor を初めて使う方向けのセットアップ手順です。

## 1. Cursor のインストール

1. [cursor.com](https://cursor.com) からダウンロード
2. インストール後、GitHub アカウントでサインイン
3. VS Code から設定をインポートするか選択（既存ユーザー向け）

## 2. 推奨初期設定

**Settings → Cursor Settings** で以下を確認:

| 設定 | 推奨値 | 理由 |
|------|--------|------|
| Privacy Mode | ON | コードが学習に使われない |
| Codebase Indexing | ON | @codebase 検索が使える |
| Enable Partial Accepts（Cursor Tab） | ON | `Ctrl + →` で単語単位の部分受け入れ（演習01） |
| Auto-run terminal commands | OFF（最初は） | 意図しないコマンド実行を防ぐ |
| Default Model | お好みのモデル | 演習10で調整を学ぶ |

## 3. キーボードショートカット（Windows）

| 操作 | ショートカット |
|------|---------------|
| AI チャットを開く | `Ctrl + L` |
| Inline Edit | `Ctrl + K` |
| Composer / Agent | `Ctrl + I` |
| Tab 補完を受け入れ | `Tab` |
| 補完の一部だけ受け入れ | `Ctrl + →`（要: Enable Partial Accepts） |
| Plan Mode に切り替え | Agent パネル内で `Shift + Tab` |

> Mac の場合: `Ctrl` → `Cmd` に読み替えてください。

## 4. この教材を開く

```powershell
cd C:\Users\ahi\Projects\cursor-practice
cursor .
```

Cursor が `cursor-practice` フォルダをワークスペースとして開きます。

## 5. インデックスの確認

左下または Settings で **Codebase Indexing** が完了するまで数分待ちます。完了すると `@Codebase` でプロジェクト全体を検索できます。

## 6. 演習を始める

[exercises/01-tab-autocomplete/README.md](../exercises/01-tab-autocomplete/README.md) からスタートしてください。
