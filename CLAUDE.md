# CLAUDE.md — いのちの傍で 油彩個展LP

## プロジェクト概要

油彩画家の個展「いのちの傍で」のランディングページ（LP）。
静的HTML + 外部CSS/JS構成で、外部依存は Google Fonts のみ。

## ファイル構成

```
いのちの傍で/
├── index.html        メインHTML（コンテンツ・構造）
├── style.css         全スタイル
├── main.js           JavaScript（スクロールスパイ・フェードイン等）
├── images/           作品・プロフィール画像（JPG）
├── README.md         編集者向けファイル説明
└── CLAUDE.md         本ファイル
```

## 技術スタック

- 純粋 HTML / CSS / Vanilla JS（ビルドツール不使用）
- フォント: Shippori Mincho / Noto Serif JP / JetBrains Mono（Google Fonts）
- 配色トークンは `style.css` 冒頭の `:root { ... }` に集約

## コーディング規約

- スタイルは `style.css` に、JS は `main.js` に追記する
- スタイルは既存の CSS 変数（`--paper`, `--ink` 等）を優先して使う
- 画像は `images/` ディレクトリに格納し、パスを相対パスで記述する

### CSS の重要な制約

**`body` に `transform` を設定してはいけない。**
`transform` が設定された要素は、子孫の `position: fixed` の含有ブロックになるため、
`.left`（左固定パネル）がビューポート基準ではなく `body` 基準で固定され、
スクロールに追随してしまう。ページロードフェードは `opacity` のみで行うこと。

## Git 運用ルール

### リポジトリ

- GitHub: https://github.com/test-cloud-2026/otagiri.git
- メインブランチ: `main`

### コード変更のたびに必ず実行すること

**ファイルを変更するたびに、以下の手順で GitHub へプッシュする。**

```bash
# 1. 変更内容を確認
git status
git diff

# 2. ステージング（変更ファイルを指定して追加）
git add index.html        # HTML を変更した場合
git add style.css         # スタイルを変更した場合
git add main.js           # JS を変更した場合
git add images/           # 画像を追加・変更した場合

# 3. コミット
git commit -m "変更内容を簡潔に記述"

# 4. プッシュ
git push origin main
```

### コミットメッセージ規則

- 日本語で記述してよい
- 例: `展覧会情報の日程を更新`, `Works セクションに新作を追加`, `フォントサイズを調整`

### 注意事項

- 画像ファイル（JPG）は必ず `images/` 配下に置き、コミット対象に含める
- `.DS_Store` など macOS 固有ファイルはコミットしない（`.gitignore` で除外済み）
- `main` ブランチへ直接コミット・プッシュして構わない（単独開発のため）
