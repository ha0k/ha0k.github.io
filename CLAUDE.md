# プロジェクト概要

Hiroto Aokiの個人ポートフォリオサイト。Hugo静的サイトジェネレーターとHugo Bloxテーマを使用。

## 技術スタック

- **フレームワーク**: Hugo + Hugo Blox (Academic CV テーマ)
- **スタイリング**: Tailwind CSS v4
- **検索**: Pagefind
- **デプロイ**: Netlify / GitHub Pages
- **パッケージマネージャー**: pnpm

## ディレクトリ構造

```
content/
├── ja/          # 日本語コンテンツ (デフォルト言語)
└── en/          # 英語コンテンツ
config/_default/ # Hugo設定ファイル
data/authors/    # 著者情報
layouts/         # カスタムレイアウト
assets/          # CSS・画像アセット
static/          # 静的ファイル
```

## 開発コマンド

```bash
# 開発サーバー起動
pnpm dev

# プロダクションビルド
pnpm build

# Hugoサーバーのみ
hugo server --disableFastRender
```

## 多言語対応

- デフォルト言語: 日本語 (`ja`)
- URL構造: `/ja/...` および `/en/...`
- コンテンツは `content/ja/` と `content/en/` に分離

## コンテンツ作成規則

1. **新規ページ作成時**: 必ず両言語のコンテンツを作成
2. **フロントマター**: YAML形式を使用
3. **画像**: 各ページディレクトリ内に `featured.jpg` として配置
4. **日付形式**: `YYYY-MM-DD` (例: 2025-02-04)

## 設定ファイル

| ファイル | 用途 |
|---------|------|
| `config/_default/hugo.yaml` | Hugo基本設定 |
| `config/_default/params.yaml` | サイトパラメータ |
| `config/_default/languages.yaml` | 多言語設定 |
| `config/_default/menus.yaml` | ナビゲーションメニュー |
| `data/authors/me.yaml` | 著者プロフィール |

## コーディング規約

- YAMLファイルはスペース2つでインデント
- コミットメッセージは日本語または英語で簡潔に
- CSSカスタマイズは `assets/` 配下で行う

## 注意事項

- `hasCJKLanguage: true` が設定済み（日本語の正しい処理に必要）
- ビルド時に `hugo_stats.json` が自動生成される（Gitにコミットしない）
- `public/` ディレクトリはビルド出力（Gitにコミットしない）
