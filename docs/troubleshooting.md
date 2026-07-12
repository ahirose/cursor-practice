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

## @Codebase が機能しない

- Codebase Indexing が完了しているか確認
- `.cursorignore` / `.gitignore` で除外されていないか確認

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
