# world-crossword（多言語クロスワード）

静的サイト。ビルド不要。このフォルダの中身を**全部**リポジトリ直下に置く（`.nojekyll` などドットファイルも忘れずに）。

想定ドメイン: `crossword.labfond.com`（CNAME / canonical / sitemap / robots / OGP に入っています。変える場合はこれらの文字列を一括置換）

## 公開手順
1. GitHub（ツールサイト用アカウント）で新規リポジトリ `world-crossword` を作成
2. このフォルダの全ファイルをリポジトリ直下にアップロード（Add file → Upload files）。`.nojekyll` は見えないことがあるので、zip をそのまま展開して `git add .` で追加するのが確実
3. Settings → Pages → Branch: `main` / `/ (root)` で公開
4. Cloudflare の DNS に CNAME を追加（例: `crossword` → `<アカウント名>.github.io`）。Proxy は他サイトと同じ設定に
5. Settings → Pages の Custom domain に `crossword.labfond.com` を入力、Enforce HTTPS を有効化
6. 公開後、labfond.com のハブにツール一覧として追加

## 公開後に確認
- 3言語それぞれで、言語選択→難易度→パズル表示→戻るボタン
- スマホ表示（タイトル非表示）とPC表示（タイトル常時表示）
- フッターの「お問い合わせ」フォームが開くこと

## メモ
- 外部通信は Google Fonts のみ（広告タグ・解析タグは未設置。入れる場合は index.html の <head> に追記）
- 韓国語では「運動」「乗り物」のお題は非表示（単語が短くパズルが成立しにくいため）

## ファイル一覧
- index.html … 本体
- 404.html … 存在しないURL用
- favicon.svg / favicon.ico / favicon-32.png … ブラウザのタブ用アイコン
- apple-touch-icon.png … iPhone のホーム画面用
- icon-192.png / icon-512.png / icon-maskable-512.png + manifest.webmanifest … Android・PWA 用
- og-image.png … SNS共有時の画像（1200x630）
- robots.txt / sitemap.xml … 検索エンジン用
- CNAME … GitHub Pages のカスタムドメイン指定
- .nojekyll … Jekyll 処理を無効化
