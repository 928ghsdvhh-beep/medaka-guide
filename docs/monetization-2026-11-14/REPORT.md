# medaka-guide 収益化改善報告（2026年11月14日）

作業ブランチ：`improve/monetization-2026-11-14`。mainへのマージ・本番公開は未実施です。
既存サイトの修正です。公開中のデザイン、広告コード、Tracking ID、解析IDを保持。順位・AIO引用・成果発生は検証できていません。

## 優先問題と変更

稚魚用品・餌・水量の3記事を充実。用品の役割、粒径、掃除時の吸い込み、20Lの計算例、台の荷重を具体化。6記事の使い回し写真をテーマに沿う手順図解へ置換。確認済み商品比較への内部リンクを追加。

外部画像6リクエストを不要にし、画像の読み込み待ちや失敗時の消去に依存する表示を解消しました。図解は当サイト編集の手順であり商品写真ではありません。Amazonの商品リンクとレビューリンクの縦2段UIは保持。

## 本文を充実した既存記事

文字数はHTMLからscript/styleと空白を除いた概算で、評価指標ではありません。文字数のための水増しはしていません。

| 記事（公開ディレクトリからの相対パス） | 本文概算・改善前 → 改善後 |
| --- | --- |
| `articles/medaka-food-guide.html` | 1031 → 1638 |
| `articles/medaka-fry-tools.html` | 651 → 1632 |
| `articles/medaka-tank-size.html` | 771 → 1302 |

パンくずを追加した記事は、その表示内容に合うBreadcrumbListを設定。既存のArticleとcanonicalは照合済みです。架空のReview・AggregateRating・Offerは新設していません。購入者レビュー10本文以上を個別確認できた商品は0件で、レビュー要約は追加していません。価格・仕様の古い確認日を一律に新しくしていません。

## 検証結果

- 静的検証：20ページ（404含む）、エラー0。タイトル・description・h1、canonical、サイトマップ、内部リンク・アンカー・参照資産、JSON-LD、重複タイトル・canonical、トップからの到達性を点検。
- サイトマップ：19URL。noindexとの整合を検証。robots.txtは既存のクロール許可と本番Sitemap指定を維持。
- ブラウザ：360・390・1440pxの60ケース。ページ横はみ出し0。外部広告・解析への通信は遮断。画像の実配信や計測通信の成功を意味しません。
- 改善前の横はみ出し：0ケース → 改善後0ケース。
- 広告保全：リンク・広告画像のHTML断片42個をSHA-256照合、一致。`scripts/affiliate-baseline.json`が修正前の基準です。既存Tracking ID：ip17-22, moon12-22。
- 外部参照先：23URLをHTTP GETで点検。未確認・差し替え前404を含む応答記録は`external-links.json`参照。403/503はリンク切れと断定しません。
- 公開状態：本番の既存ページ・robots・sitemapは200、無効URLは404。ブランチの改善は本番未反映です。
- 表示速度：メダカでは外部画像6リクエストを除去。他サイトを含む本番CWV・Lighthouse・実ユーザーLCP/INP/CLSは未測定。高速化の数値効果は主張しません。

静的HTMLサイトのためビルド工程はありません。

既存ツールの動作確認：水量40×25×20cm＝20L。すべて成功。

## 未確認事項・公開前の判断

白濁記事の既存6リンクはip17-22、その他はmoon12-22です。どちらも変更していません。所有・意図の確認が必要です。未照合ASINの商品ボタンは保留を維持。メーカー4URLは503で再確認できず、既知のASINが現在の容量・セット・色に合うかを今回すべて再検証したとは扱っていません。

共通：Amazonの商品ページの現在の表示・レビュー本文10件、A8管理画面の提携・成果対象・掲載URL、Search Consoleのクエリ別表示回数・CTR・順位、Cloudflare実測速度、実際の成果計測は未確認。広告をテスト購入・申込する検証は行っていません。既存の商品画像は、A8バナー・イメージ・メーカー参照を区別。新しい未許諾写真を追加していません。

## 全ページの診断台帳

`page-audit.json`にtitle/h1/description/canonical・index可否・サイズ・リンク数・構造化データ・到達性を保存。全ページに一律のタイトル変更はせず、検索意図が重なる販売年違いを区別し、問題のある記事とUIを優先しました。トップから到達できないindex許可ページ・内部リンク切れ・完全なタイトル重複は検証後0件。記事の統合・削除はしていません。

| ページ | 検索設定 | 本文概算 | 内部リンク先数 | 広告リンク・画像数 | 構造化データ |
| --- | --- | ---: | ---: | ---: | --- |
| `about.html` | index許可 | 155 | 1 | 0 | AboutPage |
| `index.html` | index許可 | 2154 | 18 | 8 | WebSite |
| `404.html` | noindex | 63 | 1 | 0 |  |
| `privacy.html` | index許可 | 243 | 1 | 0 | WebPage |
| `articles/medaka-water-change.html` | index許可 | 1482 | 9 | 2 | Article, BreadcrumbList |
| `articles/medaka-winter-care.html` | index許可 | 3198 | 8 | 6 | Article, BreadcrumbList |
| `articles/medaka-cloudy-water.html` | index許可 | 2561 | 7 | 6 | Article, BreadcrumbList |
| `articles/medaka-food-guide.html` | index許可 | 1638 | 7 | 2 | Article, BreadcrumbList |
| `articles/medaka-dechlorinator.html` | index許可 | 1086 | 5 | 0 | Article, BreadcrumbList |
| `articles/medaka-sponge-filter.html` | index許可 | 2720 | 8 | 0 | Article, BreadcrumbList |
| `articles/medaka-fry-tools.html` | index許可 | 1632 | 8 | 0 | Article, BreadcrumbList |
| `articles/medaka-summer-heat.html` | index許可 | 945 | 6 | 0 | Article, BreadcrumbList |
| `articles/medaka-shopping-checklist.html` | index許可 | 1549 | 9 | 8 | Article, BreadcrumbList |
| `articles/medaka-not-eating.html` | index許可 | 3138 | 9 | 2 | Article, BreadcrumbList |
| `articles/medaka-tools.html` | index許可 | 1126 | 7 | 0 | Article, BreadcrumbList |
| `articles/medaka-thermometers.html` | index許可 | 940 | 3 | 4 | Article, BreadcrumbList |
| `articles/first-aquarium.html` | index許可 | 2780 | 12 | 0 | Article, BreadcrumbList |
| `articles/medaka-tank-size.html` | index許可 | 1302 | 7 | 0 | Article, BreadcrumbList |
| `articles/dechlorinator-products.html` | index許可 | 1510 | 4 | 4 | Article, BreadcrumbList |
| `tools/water-volume.html` | index許可 | 288 | 2 | 0 | WebPage |

## 再実行・差分の確認

- `python scripts/check_site.py .`（Python標準ライブラリのみ）
- 全差分：`git diff main...improve/monetization-2026-11-14`
- 本番へのマージ・デプロイは別途承認後。プレビュー環境が自動生成されても本番とは区別。
- 公開後はcanonical・サイトマップの実応答、Search Consoleの除外理由、記事→広告クリック→成果を確認。変更前後で同じ期間・クエリを比較してください。
