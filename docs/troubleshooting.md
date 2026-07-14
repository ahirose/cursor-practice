# トラブルシューティング

## Tab 補完が出ない

- Cursor Pro / 有効なサブスクリプションを確認
- Settings → Cursor Tab → Enable を ON
- ファイル形式が対応言語か確認（`.js`, `.ts`, `.py` 等）

## `Ctrl + →` で部分受け入れが効かない

- **Cursor Settings → Features → Cursor Tab**（または **Tab**）で **Enable Partial Accepts** を ON にする
- 設定後も動かない場合は Keyboard Shortcuts で `editor.action.inlineSuggest.acceptNextWord` のキーバインド・競合を確認

## Agent が勝手にファイルを大量変更する

- Plan Mode を先に使う（演習05）
- プロンプトに「変更は `@filename` のみ」と明記
- Auto-run を OFF にして、各ステップを確認

## コードベース検索がうまくいかない

- Codebase Indexing が完了しているか確認（Settings → Indexing）
- `.cursorignore` / `.gitignore` で除外されていないか確認
- `@Codebase` は不要。自然言語で「コードベースを検索して」と書く
- 分かっているファイルなら `@filename` で直接渡す

## `@Web` / `@Docs` が見つからない

- `@Web` は Cursor 2.0 で削除済み。「Web で調べて」と自然言語で依頼する
- `@Docs` は Agents ウィンドウでは使えないことが多い。ドキュメントも自然言語で調べさせるか、Editor ウィンドウを使う

## 日本語プロンプトで期待と違う結果

- 技術用語は英語のまま（例: `localStorage`, `addEventListener`）
- 成功条件を明示: 「〜が表示されること」「エラーが出ないこと」
- 変更してほしくないファイルを「触らないで」と明記

## ターミナルコマンドが失敗する

- Windows では PowerShell コマンドを使う（`dir` ではなく `Get-ChildItem` 等）
- パスにスペースがある場合は引用符で囲む

## 演習の答え合わせ

各演習 README の「成功条件」を満たしていれば OK です。実装方法は一つではありません。AI の出力が要件を満たしていれば合格です。

## さらに学ぶ

- [Cursor 公式 Learn](https://cursor.com/learn)
- [Cursor Forum](https://forum.cursor.com)
