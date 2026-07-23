# Brand Guidelines Portal

社内ブランドのガイドラインをまとめたポータルサイトです。
外部ライブラリなし・ビルド不要の静的HTMLのみで構成されています。

## 構成

```
index.html                        … TOPページ（ブランド一覧）
template/guideline-template.html  … 新ブランド追加用の原本テンプレート
brands/
  brand-a/index.html              … Brand A ガイドライン（サンプル）
  brand-b/index.html              … Brand B ガイドライン（サンプル）
```

各HTMLは単一ファイルで完結しており、冒頭の設定オブジェクトを
編集するだけで内容が反映されます。

- TOPページ: `index.html` 冒頭の `SITE_CONFIG`
- 各ガイドライン: 各 `index.html` 冒頭の `BRAND_CONFIG`

## ブランドを追加する

1. `template/guideline-template.html` を `brands/<新ブランドID>/index.html` としてコピー
2. コピー先の `BRAND_CONFIG` を新ブランドの内容に書き換える
   （`portalUrl` は `"../../index.html"` のままでOK）
3. ロゴ画像を `brands/<新ブランドID>/assets/` に配置
   - `logo-primary.svg` / `logo-white.svg` / `logo-symbol.svg`
   - 未配置でもブランド名テキストのプレースホルダーで動作します
4. ルートの `index.html` にある `SITE_CONFIG.brands` 配列に1件追加

詳細な手順は各HTMLファイル冒頭のコメントにも記載しています。

## 閲覧方法

- ローカル: `index.html` をブラウザで開くだけで動作します
- GitHub Pages を有効化すると URL で社内共有できます
  （Settings → Pages → Branch: `main` / root）

## PDF化

各ガイドラインページはブラウザの印刷機能でセクションごとに
改ページされたPDFを出力できます（ナビゲーションは自動非表示）。
