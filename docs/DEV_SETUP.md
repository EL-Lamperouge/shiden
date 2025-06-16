# Shiden 開発環境セットアップ

本ドキュメントは、タスク管理アプリ「Shiden」の開発に必要な環境を構築する手順と構成方針を記載します。

---

## 使用技術スタック

| 区分          | 使用技術（バージョン）                |
|---------------|----------------------------------------|
| フレームワーク | React (^19.1.0)                        |
| ビルドツール   | Vite (^6.3.5)                          |
| UIライブラリ   | Yamada UI (^1.7.7)                     |
| UI拡張         | @yamada-ui/calendar (^1.8.17), @yamada-ui/charts (^1.5.15), @yamada-ui/markdown (^1.1.4), @yamada-ui/fontawesome (^1.0.55) |
| 状態管理      | Zustand (^5.0.5)                        |
| スタイリング   | Tailwind CSS（@tailwindcss/vite ^4.1.10）|
| 型システム     | TypeScript (~5.8.3)                     |
| テスト        | Vitest (^3.2.3) + @testing-library/react (^16.3.0) |
| PWA対応       | vite-plugin-pwa (^1.0.0) + Workbox（TBD） |
| Storybook     | storybook (^9.0.10) + @storybook/react-vite (^9.0.10) |
| Lint/Format   | ESLint (^9.25.0), Prettier (^3.5.3)      |
| 環境変数管理  | dotenv (^16.5.0)                         |

---

## 前提環境

- Node.js (推奨: v18+)
- pnpm (推奨: v8+)

```bash
# Node.js（nvm 推奨）
nvm install 18
nvm use 18

# pnpm インストール
npm install -g pnpm
```

---

## セットアップ手順

```bash
git clone https://github.com/yourname/shiden.git
cd shiden

# Vite用ディレクトリ作成＆移動
mkdir vite
cd vite

# Vite + React + TypeScript プロジェクト初期化
pnpm create vite .
# → 対話形式で「React」「TypeScript + SWC」を選択

# 依存パッケージインストール
pnpm install

# (TBD)Tailwind CSS v4 + Viteプラグイン追加
# pnpm add -D @tailwindcss/vite

# 開発サーバー起動
pnpm dev
```

---

## ディレクトリ構成(初期)
```bash
vite/
├── src/
│   ├── components/       # 再利用可能なUIコンポーネント
│   ├── pages/            # 画面単位のコンポーネント
│   ├── stores/           # Zustandストア
│   ├── utils/            # 共通関数
│   ├── assets/           # アイコンや画像などのアセット
│   ├── types/            # 型定義
│   ├── styles/           # グローバルCSSやテーマ
│   └── main.tsx          # アプリのエントリーポイント
├── index.html
├── package.json
├── tsconfig.json
└── ...
```

---

## TBD
- PWA有効化（Vite Plugin + Workbox）
- テスト環境：Vitest + Testing Library
- Storybook（UIドキュメンテーション用）
- CI: GitHub Actions によるテスト自動実行

---

## 備考
- `.env.example` を参考に `.env` を作成する必要があります。
- Yamada UI のデザインカスタマイズは `/theme/` にて集中管理されます。
- Tailwind CSS v4 + PostCSS利用時は[公式ドキュメント](https://tailwindcss.com/docs/installation/using-postcss)も参照。