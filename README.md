# Qiita 記事アナリティクス

Qiitaユーザーの記事一覧を取得し、統計情報を表示するWebアプリケーションです。Google Gemini APIを使用したAI機能により、記事の傾向分析や次の記事ネタの提案なども行えます。

## 機能

### 基本機能
- **記事一覧取得**: 指定したQiitaユーザーの公開記事を最大100件取得
- **統計情報表示**: 
  - 取得記事数
  - 総LGTM数
  - 平均LGTM/記事
- **ソート機能**: タイトル、投稿日、LGTM数でソート可能
- **CSVエクスポート**: 記事データをCSV形式でダウンロード

### AI機能（Gemini API使用）
- **プロフィール分析**: 記事タイトルとタグから、エンジニアとしての技術的強みや関心領域を分析
- **記事ネタ提案**: 過去の執筆履歴に基づいて、次に書くべき記事テーマを3つ提案
- **タイトル改善案**: 各記事のタイトルをよりキャッチーでLGTMが集まりやすいタイトルに改善する案を提示

## 技術スタック

- **React 18** - UIフレームワーク
- **TypeScript** - 型安全性
- **Vite** - ビルドツール
- **Tailwind CSS** - スタイリング
- **Lucide React** - アイコン
- **Google Gemini API** - AI機能

## セットアップ

### 必要な環境
- Node.js 18以上
- npm または yarn

### インストール

```bash
# 依存関係のインストール
npm install
```

### 開発サーバーの起動

```bash
npm run dev
```

ブラウザで `http://localhost:5173` にアクセスします。

### ビルド

```bash
npm run build
```

ビルドされたファイルは `dist` ディレクトリに出力されます。

## 使用方法

### 1. 記事の取得

1. **Qiita ユーザーID** を入力（例: `Junpei_Takagi`）
2. （任意）**Qiita APIトークン** を入力（API制限を緩和するため）
3. **取得** ボタンをクリック

### 2. AI機能の使用

AI機能を使用する場合は、以下の手順が必要です：

1. **Gemini APIキーの取得**
   - [Google AI Studio](https://makersuite.google.com/app/apikey) でAPIキーを取得
2. **APIキーの設定**
   - アプリケーションの「Gemini APIキー」フィールドにAPIキーを入力
3. **AI機能の実行**
   - **AI プロフィール分析**: 「分析する」ボタンをクリック
   - **次の記事ネタ提案**: 「アイデアを出す」ボタンをクリック
   - **タイトル改善案**: 各記事のSparklesアイコンをクリック

## APIキーについて

### Qiita APIトークン（任意）

- 未設定でも利用可能ですが、API制限（1時間あたり60リクエスト）があります
- トークンを設定することで、制限が緩和されます
- トークンの取得方法: [Qiita API ドキュメント](https://qiita.com/api/v2/docs)

### Gemini APIキー（AI機能用）

- AI機能を使用する場合のみ必要です
- 無料枠がありますが、使用量に応じて課金される場合があります
- APIキーの取得方法: [Google AI Studio](https://makersuite.google.com/app/apikey)

## プロジェクト構造

```
qiita_qrticle_analyzer/
├── src/
│   ├── App.tsx          # メインコンポーネント
│   ├── main.tsx         # エントリーポイント
│   └── index.css        # グローバルスタイル
├── index.html           # HTMLテンプレート
├── package.json         # 依存関係
├── tsconfig.json        # TypeScript設定
├── vite.config.ts       # Vite設定
├── tailwind.config.js   # Tailwind CSS設定
└── postcss.config.js    # PostCSS設定
```

## ライセンス

このプロジェクトは個人利用を想定しています。

## 注意事項

- APIキーはブラウザに保存されますが、セキュアな環境での使用を推奨します
- Qiita APIの利用規約に従って使用してください
- Gemini APIの利用規約に従って使用してください
