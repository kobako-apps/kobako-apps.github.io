# kobako-apps.github.io

iOS アプリの LP・サポート・プライバシーポリシーを置く GitHub Pages のサイト。
公開 URL: https://kobako-apps.github.io/

**このリポジトリは公開されている。** アプリのソース・秘密情報・未公開の資料は置かない。

## 構成

```
index.html            アプリ一覧（トップ）
404.html              見つからないとき（絶対パスで書く）
assets/site.css       全アプリ共通のスタイル
<app>/index.html      LP（日本語）
<app>/en/index.html   LP（英語）
<app>/support/        サポート（日英併記・お問い合わせは Google フォーム）
<app>/privacy/        プライバシーポリシー（日本語）、privacy/en/ に英語
<app>/images/         アイコン・スクリーンショット
```

- フォルダ名は小文字のアプリ名にする。App Store Connect に登録した URL（サポート・プライバシーポリシー）は**変えない**。
- ページ内のリンクと画像は相対パスで書く（`404.html` だけは絶対パス）。
- `.nojekyll` を置いているので、Markdown は変換されない。ページは HTML で書く。
- スクリーンショットは幅 660px の JPEG に縮めて置く（例: `sips -s format jpeg -s formatOptions 78 --resampleWidth 660 in.png --out out.jpg`）。

## アプリを足すとき

1. `shiftmate/` をコピーして `<app>/` を作り、文言・画像・App Store の ID・フォームの URL を差し替える
2. アプリの色は各ページの `<style>:root { --accent: … }</style>` で上書きする
3. `index.html` の一覧に1件足す
4. 手元で確認: `python3 -m http.server 8000` → http://localhost:8000/
