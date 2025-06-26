# chaploud dev notes

chaploudの技術ブログ

## 記事追加

```sh
hugo new posts/name-of-entry.md # draft = false/true
hugo server [-D] # -Dで下書きも含めて確認
git add .
git commit -m "commit message"
git push origin main # Github Actionsでデプロイされる
```

## ディレクトリ

- `content/` - ブログをMarkdownで格納
  - `_index.md` - トップページ
  - `posts/` - ブログのポスト
  - `pages/` - 固定ページ
    - `links.md` - リンク集
- `static/` - ダイレクトにhtmlを配置
  - `ai-generated` - AIで生成したページを格納
- `layouts/` - レイアウトを上書きしたければ利用
- `assets/` - 画像などのファイルを格納
- `archetypes/` - `hugo new`の際のテンプレート
- `.github/workflows/hugo.yml` - GitHub Actionsの設定
- `public/` - 生成されたサイト(Git管理外)

## リンクの書き方

```markdown
- [About Page]({{< ref "./pages/about.md" >}})
- [Clojure CLI](/blog/ai-generated/clojure-cli.html)
```