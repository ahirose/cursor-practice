# Sample App — Todo リスト

Cursor 実践演習用のシンプルな Todo アプリです。

## 起動方法

```powershell
# Windows — ブラウザで直接開く
start src\index.html
```

または `src/index.html` をブラウザにドラッグ＆ドロップ。

## 機能

- Todo の追加・完了・削除
- localStorage による永続化
- 件数表示
- 完了済み一括削除

## 演習での使い方

このアプリは意図的に**1 ファイルにロジックが集約**されています。演習 04〜05 でリファクタリング題材として使います。

## データ

localStorage キー: `cursor-practice-todos`

```javascript
[{ "id": 1234567890, "text": "タスク名", "completed": false }]
```
