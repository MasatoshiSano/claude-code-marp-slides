# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

このファイルは、本プロジェクトでClaudeを運用するためのガイドラインです。

## 1. 基本原則 (General Principles)

### 1.1. ルールの自己進化
-   **目的**: ユーザーからの指示を通じて、このガイドライン自体を継続的に改善する。
-   **プロセス**:
    1.  **ルール化の提案**: 繰り返し発生する可能性のある指示を受けた場合、`CLAUDE.md`へのルール追加をユーザーに提案する。
    2.  **承認と反映**: ユーザーの承認を得た場合のみ、ルールを追記または更新する。

### 1.2. プロジェクト再開時の状況把握
-   **目的**: 作業の一貫性を保つため、プロジェクト再開時には必ず現状を把握する。
-   **プロセス**:
    1.  **ログ確認**: `Log/`フォルダ内の最新ログを確認し、前回の作業内容と中断点を把握する。
    2.  **ファイル確認**: `git status`と`ls -R`等で、ファイルの変更状況とプロジェクト構造を確認する。
    3.  **計画の提示**: 上記を基に、その日の作業計画をユーザーに提示する。

### 1.3. 日本語での対話
-   すべてのやり取りは、原則として日本語で実施する。

### 1.4. ファイル削除時の確認
-   `rm`コマンドを使用する際は、必ず事前にユーザーの確認を取る。
-   削除対象のファイル/フォルダを明示し、削除の影響を説明する。

### 1.5. 変更の記録
-   **重要**: ファイルを変更した後はローカルにコミットして変更履歴を管理する。
-   **プロセス**:
    1.  `git add -A` で全変更をステージング
    2.  `git commit -m "説明的なコミットメッセージ"` でコミット
-   **コミットメッセージ**: 変更内容を明確に記載
-   **注意**: GitHubへのプッシュは自動では実行しない

## Project Purpose

**Main Goal**: スライド作成手順をMarp形式で文書化し、PPTXファイルとして出力する。

This project aims to:
1. スライド作成のワークフローを明確に文書化する
2. Marpを使用してPPTX形式のプレゼンテーションを生成する
3. 効率的なスライド作成手順のガイドを提供する

## Repository Structure

```
claude-code-marp-slides/
├── CLAUDE.md                    # 本ガイドラインファイル
├── 00_アイデア方針/             # アイデアと方針
│   ├── 今回のスライド生成の作業内容.md
│   └── 方針.md                 # スライド作成のガイドライン
├── 01_ドラフト/                # コンテンツドラフト（通常のMarkdown）
│   └── スライド作成手順.md
├── 02_Marp/                   # Marp形式のプレゼンテーション
│   └── スライド作成手順.md
├── 03_Export/                 # 生成された出力ファイル
│   └── PPTX/
│       └── スライド作成手順.pptx
└── XX_Resource/               # フィードバック用リソース
    ├── template.css           # merpayテンプレートCSS
    └── スクリーンショット*.png  # フィードバック用画像
```

## 2. ワークフロールール (Workflow Rules)

### 2.1. スライド作成の4段階プロセス
1. **00_アイデア方針**: 何を書くか、どう書くかの指針を記載
   - `方針.md`: 全体的な方向性とターゲット設定
   - `今回のスライド生成の作業内容.md`: 作業記録と学習事項
2. **01_ドラフト**: スライドの骨組み、記載内容を通常のMarkdownで作成
3. **02_Marp**: ドラフトをMarp形式に変換（フロントマター追加、スライド分割）
4. **03_Export**: MarpファイルをPPTX形式にエクスポート

### 2.2. フォルダ間の同期ルール
-   **重要**: 各フォルダは以下の依存関係を持つ
    ```
    00_アイデア方針（設計）
        ↓ 反映
    01_ドラフト（内容作成）
        ↓ 変換
    02_Marp（プレゼン形式）
        ↓ エクスポート
    03_Export（最終出力）
    ```

-   **00_アイデア方針が変更された場合**:
    1. 変更内容を01_ドラフトに反映
    2. 01_ドラフトから02_Marpに変換
    3. エクスポート確認後、03_Exportに出力

-   **01_ドラフトが変更された場合**:
    1. 重要な変更は00_アイデア方針に逆反映
    2. 文言などはそのまま02_Marpに反映
    3. 02_Marpに変換
    4. エクスポート確認後、03_Exportに出力

-   **エクスポートの確認**: 「エクスポートしますか？」と質問
-   明示的に「エクスポート」と指示された場合のみ、03_Exportフォルダに**PPTX形式のみ**でエクスポート

### 2.4. コンテンツ作成ルール
-   **方針確認**: `00_アイデア方針/方針.md`に記載された目的とターゲットを確認
-   **文章作成**: 方針に従った内容で記載
-   **一貫性維持**: プロジェクト全体で統一された表現を使用

### 2.5. PPTXエクスポートルール
-   **エクスポート方法**: 通常のPPTXエクスポート
    ```bash
    marp 02_Marp/[ファイル名].md --pptx --output 03_Export/PPTX/[ファイル名].pptx
    ```
-   **編集が必要な場合**: 
    - Web版Marp Editor（https://marpwebeditor.app/）を使用
    - 02_Marpのファイル内容をコピー＆ペーストして編集
    - PowerPointで開いて「名前を付けて保存」でも編集可能化
-   **出力先**: 03_Export/PPTXフォルダに保存
-   **確認**: エクスポート前に「エクスポートしますか？」と確認
-   **merpayスタイル**: XX_Resource/template.cssを使用してスタイリング

### 2.6. 変換時の処理内容
-   **01→02の変換**:
    ```yaml
    # Marpフロントマターを追加（余白とフォント設定含む）
    ---
    marp: true
    theme: default
    paginate: true
    backgroundColor: #fff
    style: |
      section {
        font-family: 'Hiragino Kaku Gothic ProN', 'メイリオ', sans-serif;
        padding: 40px 50px 40px 50px;
        font-size: 22px;
      }
      # その他のスタイル設定...
    ---
    ```
    - 適切な位置でスライド分割（`---`）
    - 1スライド1トピックの原則を適用
    
-   **02→03の変換**:
    ```bash
    # PPTX出力（03_Export/PPTX直下に出力）
    marp 02_Marp/[ファイル名].md --pptx --output 03_Export/PPTX/[ファイル名].pptx
    ```

## 3. プロジェクト固有の内容

### 3.1. このプロジェクトの概要
このプロジェクトは「スライド作成手順」をMarpで文書化し、PPTXファイルとして出力することを目的としています。

### 3.2. 主要ファイル
- **方針.md**: Marpを使用したプレゼンテーション作成の教育用スライドの方針
- **スライド作成手順.md**: 各フォルダに同名で存在し、段階的に内容が洗練される

### 3.3. コンテンツの特徴
- **ターゲット**: Marp初心者、Markdownでのプレゼン作成に興味がある人
- **内容**: 環境構築から実際の作成まで一連の流れ
- **スタイル**: 画面キャプチャやコマンド例を豊富に使用

## 4. 一般的なタスク

### 4.1. 新規プレゼンテーション作成時
```bash
# 0. Marp CLIが利用可能か確認
which marp || npm list -g @marp-team/marp-cli

# 1. 01_ドラフトで内容作成
Edit 01_ドラフト/スライド作成手順.md

# 2. Marp形式に変換（Claudeが自動で実行）
# フロントマター追加、スライド分割

# 3. プレビュー確認
marp 02_Marp/スライド作成手順.md --preview

# 4. PPTXエクスポート（ユーザー確認後）
marp 02_Marp/スライド作成手順.md --pptx --output 03_Export/PPTX/スライド作成手順.pptx
```

### 4.2. Marpスライドのベストプラクティス
- `---`でスライドを分割
- Marpディレクティブでスタイリング（例：`<!-- _class: lead -->`）
- スピーカーノートは`<!-- speaker notes -->`
- 背景画像は`![bg](image.jpg)`
- テーマを一貫して適用

### 4.3. エクスポートコマンド
```bash
# PPTXエクスポート（基本）
marp 02_Marp/スライド作成手順.md --pptx --output 03_Export/PPTX/スライド作成手順.pptx

# PPTXエクスポート（ローカルファイル許可）
marp 02_Marp/スライド作成手順.md --pptx --output 03_Export/PPTX/スライド作成手順.pptx --allow-local-files

# HTMLエクスポート（必須）
marp 02_Marp/スライド作成手順.md --html --output 03_Export/HTML/スライド作成手順.html --allow-local-files

# 編集が必要な場合はWeb版Marp Editorを使用
# https://marpwebeditor.app/
```

**エクスポート形式について**:
- **PPTX**: PowerPoint形式、テキストが画像として埋め込まれる
- **HTML**: ブラウザで表示可能、編集・共有に便利
- **必須**: 両方の形式で出力すること

**重要**: PPTXはテキストが画像として埋め込まれます。編集が必要な場合は、Web版Marp Editor（https://marpwebeditor.app/）にMarpファイルの内容をコピー＆ペーストして編集してください。

### 4.4. 背景・画像挿入のルール
背景や画像を挿入する場合は、以下の形式に従ってください：

#### 全面背景画像（brightness調整付き）
```markdown
---
marp: true
theme: uncover
---
<!--
_color: white
_footer: 'Photo by Benjamin Rascoe on Unsplash'
-->

![bg brightness:0.6](benjamin-rascoe-JS6PY31e2P0-unsplash.jpg)

# タイトル全面背景

Brightnessを落とし、文字の視認性を上げました
```

#### 左右分割配置
```markdown
---
<!--
_footer: 'Photo by Michal Vasko　on Unsplash'
paginate: true
-->

![bg left:40%](michal-vasko-GOfQNTI_9Og-unsplash.jpg)

### 左に画像をいれる

- 表示場所、比率を指定する
- 次頁では、複数画像を並べます
- footerで画像クレジット表示も
```

#### 複数画像の組み合わせ
```markdown
---
<!--
_backgroundColor: white
_footer: 'Photo by Chris Campbell, Dan on Unsplash'
-->

![bg right:60% contrast:1.5 brightness:1.2](christopher-campbell-rDEOVtE7vOs-unsplash.jpg)
![bg 350% contrast:1.2 brightness:1](dan-ROJFuWCsfmA-unsplash.jpg)

# 進め、
#### 新しいわたし。

なんて、
小洒落た感じにも。
```

**注意事項**：
- 画像ファイルは適切なフォルダに配置し、相対パスで指定
- クレジット表示は`_footer`で必ず記載
- `brightness`, `contrast`等で視認性を調整
- 画像比率は`left:40%`, `right:60%`等で指定

### 4.5. スライド構成の標準ルール

#### 必須要素
1. **表紙**: タイトルは中央配置（CSSで自動調整）
2. **目次**: 必ず2番目のスライドに配置
3. **話すこと・話さないこと**: 目次の直後に明記
4. **h1の位置**: 表紙以外は上から20px、左から170pxに固定

#### 画像使用ルール
- **頻度**: 適度にUnsplashから画像を挿入
- **選択基準**: スライド内容に適した画像を選定
- **使用方法**: 背景画像として`![bg]`形式で配置
- **視認性**: 必要に応じて`brightness`等で調整

#### スライド構成テンプレート
```markdown
1. 表紙（タイトル中央）
2. 目次
3. このスライドで話すこと・話さないこと
4. 本編スライド（h1は上20左170固定）
5. まとめ
```

## 5. Git ワークフロー

このプロジェクトは大きなObsidian vaultの一部としてGit管理されています：
- `スライド生成手順/`ディレクトリ内のファイルのみに集中
- ObsidianとMarpの両方でレンダリングできるMarkdownを維持
- コミット時は変更内容を明確に記載
- **重要**: GitHubへのプッシュは自動では実行しない（ローカルコミットのみ）