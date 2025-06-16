# Shiden 開発環境セットアップ

本ドキュメントは、タスク管理アプリ「Shiden」の開発に必要な環境を構築する手順と構成方針を記載します。

---

## 使用技術スタック

| 区分          | 使用技術                         |
|---------------|----------------------------------|
| フレームワーク | React (18+)                      |
| ビルドツール   | Vite                             |
| UIライブラリ   | Yamada UI（Chakra UI ベース）    |
| 状態管理      | Zustand                          |
| スタイリング   | Tailwind CSS（必要に応じて）     |
| 型システム     | TypeScript                       |
| テスト        | Vitest + Testing Library（予定） |
| PWA対応       | Service Worker, Workbox（予定）  |

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

---

## セットアップ手順

```bash
git clone https://github.com/yourname/shiden.git
cd shiden

# パッケージインストール
pnpm install

# 開発サーバー起動
pnpm dev
```

---

## ディレクトリ構成(初期)
```bash
src/
├── components/       # 再利用可能なUIコンポーネント
├── pages/            # 画面単位のコンポーネント
├── stores/           # Zustandストア
├── utils/            # 共通関数
├── assets/           # アイコンや画像などのアセット
├── types/            # 型定義
├── styles/           # グローバルCSSやテーマ
└── main.tsx          # アプリのエントリーポイント
```

---

## TBD
- PWA有効化（Vite Plugin + Workbox）
- テスト環境：Vitest + Testing Library
- Storybook（UIドキュメンテーション用）
- CI: GitHub Actions によるテスト自動実行

---

## 備考
- .env.example を参考に .env を作成する必要があります。
- Yamada UI のデザインカスタマイズは /theme/ にて集中管理されます。