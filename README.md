# Claude CodeとMarpで作る対話型スライド作成

AIとの対話を通じて効率的にプレゼンテーションを作成する方法を紹介するプロジェクトです。

## 概要

このプロジェクトは、Claude Codeを使用してMarp形式のスライドを作成するワークフローを実践的に示したものです。

## フォルダ構造

```
スライド作成手順/
├── CLAUDE.md           # プロジェクトルールブック
├── 00_アイデア方針/     # 設計・方針
├── 01_ドラフト/        # 内容作成
├── 02_Marp/           # Marp形式
├── 03_Export/         # 最終出力
└── XX_Resource/       # フィードバック用
```

## 主な特徴

- **4段階ワークフロー**: アイデア→ドラフト→Marp→エクスポート
- **対話型開発**: Claude Codeとの自然な対話でスライド作成
- **mercoinスタイル**: プロフェッショナルなデザインテンプレート
- **フィードバックループ**: XX_Resourceフォルダでの視覚的フィードバック

## 使い方

1. **Claude Codeのインストール**
   - [公式サイト](https://claude.ai/code)からダウンロード

2. **プロジェクトを開く**
   ```bash
   claude-code open スライド作成手順
   ```

3. **対話でスライドを作成**
   - 「〇〇についてのスライドを作って」と指示
   - Claude Codeが4段階ワークフローに沿って作成

4. **編集が必要な場合**
   - [Marp Web Editor](https://marpwebeditor.app/)を使用
   - 02_Marpフォルダの内容をコピー＆ペースト

## 必要な環境

- Claude Code
- Marp CLI (`npm install -g @marp-team/marp-cli`)
- PowerPoint（PPTXファイルの閲覧用）

## ライセンス

MIT License

## 作成者

y-b-ito