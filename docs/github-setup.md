# GitHub リポジトリへの公開手順

**公開済み:** https://github.com/ahirose/cursor-practice

以下は、同様の手順を自分で再現する場合のメモです。

## 方法 A: GitHub Web UI（最も簡単）

1. [github.com/new](https://github.com/new) を開く
2. Repository name: `cursor-practice`
3. **Public** を選択
4. 「Add a README file」等は**チェックしない**（ローカルに既にあるため）
5. **Create repository** をクリック
6. 表示された手順の「push an existing repository」を実行:

```powershell
cd C:\Users\ahi\Projects\cursor-practice
git remote add origin https://github.com/YOUR_USERNAME/cursor-practice.git
git branch -M main
git push -u origin main
```

`YOUR_USERNAME` を自分の GitHub ユーザー名に置き換えてください。

## 方法 B: GitHub CLI

```powershell
winget install GitHub.cli
gh auth login
cd C:\Users\ahi\Projects\cursor-practice
gh repo create cursor-practice --public --source=. --remote=origin --push
```

## 方法 C: Cursor Agent に任せる

GitHub MCP または `gh` インストール後、Agent に:

```
GitHub に cursor-practice リポジトリを public で作成して push して
```

## 公開後

README が GitHub 上で教材の入口になります。Issue を「演習の質問」用に使うのもおすすめです。
