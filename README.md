# chaploud dev notes

chaploudの技術ブログ

## 記事追加

```sh
hugo new post/name-of-entry.md # draft = false/true
hugo server [-D] # -Dで下書きも含めて確認
git add .
git commit -m "commit message"
git push origin main # Github Actionsでデプロイされる
```

## ディレクトリ

- `content/` - ブログをMarkdownで格納
- `content/posts/` - ブログのポスト
- `layouts/` - レイアウトを上書きしたければ利用
- `static/` - Static assets
- `assets/` - 画像などのファイルを格納
- `archetypes/` - Content templates (default.md for new posts)
- `public/` - 生成されたサイト(Git管理外)
- `.github/workflows/hugo.yml` - GitHub Actionsの設定