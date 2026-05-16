# いのちの傍で  ―  油彩個展LP

VSCode等のエディタで編集できるよう、必要なファイル一式を同梱しています。

## ファイル構成

```
いのちの傍で/
├── index.html        ← メインのHTML（ここを編集）
└── images/           ← 作品 / プロフィール画像
    ├── work-red.jpg          赤い演奏作品（左固定パネル）
    ├── work-window.jpg       作品 01 「窓」
    ├── work-blue.jpg         作品 02 「かくされた悪を注意深くこばむこと」
    ├── work-yellow.jpg       作品 03 untitled / 黄
    ├── work-cat.jpg          作品 04 untitled / 眠る
    ├── work-lastcity.jpg     作品 05 「ラストシティ」
    ├── profile-chorus.jpg    甲府 風の合唱団
    └── profile-studio.jpg    アトリエにて
```

## 開発・編集

外部依存はGoogle Fontsのみ。ローカルでは `index.html` をブラウザで直接開けば表示されます。

- フォント: Shippori Mincho / Noto Serif JP / JetBrains Mono （Google Fonts経由）
- 主要カラー変数は `<style>` 冒頭の `:root { ... }` にまとまっています
- スクロールスパイ、To Top、フェードイン等のJSは末尾 `<script>` 内

## 配色トークン

```
--paper:   #f1ece2   紙色（背景）
--ink:     #2a2620   柔らかい黒
--ink-2:   #6b655a
--ink-3:   #a39b8c
--rule:    #cfc8b8
--redink:  #f6e1d4   赤の上に乗る文字
```

## セクション順

1. Statement
2. Works （5点）
3. Profile
4. Exhibition （会場・会期 / クロージングイベント）
