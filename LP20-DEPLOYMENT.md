# LP20 公開手順

## 公開先

- 公開予定URL: `https://abies-law.jp/lp20/`
- サーバー上の配置先: ドキュメントルート直下の `lp20/`
- 一般的な配置例: `public_html/lp20/`

`https://abies-law.jp/lp20/` は、2026年7月24日の確認時点で `404 Not Found` であり、未使用です。

## アップロードするファイル

`deploy/lp20/` ディレクトリの中身を、そのままサーバーの `lp20/` ディレクトリへアップロードしてください。

```text
public_html/
├── 既存サイトのファイル（変更しない）
└── lp20/
    ├── index.html
    ├── assets/
    ├── styles.css
    ├── figma-overrides.css
    ├── scroll-fix.css
    ├── figma-sections.css
    ├── figma-remaining.css
    └── responsive-scale.css
```

既存の `public_html/index.html`、DNS、SSL、メール、既存ページ、GTM設定は変更しません。

## 技術構成

- 静的HTML/CSS
- JavaScriptなし
- ビルド不要
- CSS・画像・faviconは相対パス参照
- WebフォントのみGoogle Fontsから読み込み
- CTAは `tel:` と外部LINE URL

## 計測の現状

- LP内のMeta Pixel: 未実装
- LP内のGoogle Tag Manager: 未実装
- コンバージョンイベント: 未実装
- 問い合わせフォーム: なし
- サンクスページ: なし
- 申込導線: 外部LINEへの遷移

既存トップページでは `GTM-TDFP9MXQ` が確認できましたが、このLPへ同じコンテナを導入してよいかは計測設計の確認が必要なため、自動では追加していません。Meta Pixel IDやイベント名も追加していません。

## 検索・OGP設定

- LPページだけに `noindex, nofollow` を設定
- canonical: `https://abies-law.jp/lp20/`
- og:url: `https://abies-law.jp/lp20/`
- og:image: `https://abies-law.jp/lp20/assets/hero.jpg`
- サイト全体の `robots.txt` は変更しない

## 公開後の確認

1. `https://abies-law.jp/lp20/` が200で表示されること
2. スマートフォン・PCでデザインが崩れていないこと
3. 電話CTAが `03-6381-6582` を開くこと
4. LINE CTAが `https://lin.ee/WGSG1bM` を開くこと
5. `?utm_source=facebook&utm_medium=paid_social&utm_campaign=test` を付けても表示されること
6. favicon、画像、CSSが404になっていないこと
7. ブラウザコンソールに重大なエラーがないこと
8. 広告運用担当者と、GTM・Meta Pixel・コンバージョンイベント名を確認すること

