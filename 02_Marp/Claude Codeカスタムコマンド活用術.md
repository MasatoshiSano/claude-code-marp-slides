---
marp: true
theme: merpay-template
paginate: true
backgroundColor: #f8f8f8
style: |
  section {
    font-family: 'Hiragino Kaku Gothic ProN', 'メイリオ', 'Helvetica Neue', 'Segoe UI', sans-serif;
    padding: 40px 60px;
    font-size: 22px;
    color: #333333;
  }
  h1 {
    position: absolute;
    top: 20px;
    left: 170px;
    font-size: 48px;
    color: #007bff;
    border-bottom: 2px solid #eeeeee;
    padding-bottom: 10px;
    margin-bottom: 30px;
  }
  section:first-of-type h1 {
    position: static;
    text-align: center;
    top: auto;
    left: auto;
    margin-top: 100px;
    margin-bottom: 50px;
  }
  h2 {
    font-size: 36px;
    color: #007bff;
    margin-bottom: 20px;
  }
  h3 {
    font-size: 28px;
    color: #007bff;
    margin-bottom: 15px;
  }
  ul {
    list-style: none;
    padding-left: 0;
    margin-bottom: 20px;
  }
  ul li {
    position: relative;
    font-size: 20px;
    line-height: 1.8;
    margin-bottom: 15px;
    padding-left: 30px;
  }
  ul li::before {
    content: "●";
    position: absolute;
    left: 0;
    top: 0;
    color: #007bff;
    font-size: 24px;
    line-height: 1.4;
  }
  section::after {
    content: "merpay " attr(data-marp-page);
    position: absolute;
    bottom: 20px;
    right: 60px;
    font-size: 16px;
    color: #666666;
  }
  .highlight {
    background-color: #e3f2fd;
    padding: 20px;
    border-radius: 8px;
    border-left: 4px solid #007bff;
  }
  .data-box {
    background-color: #f0f8ff;
    padding: 15px 20px;
    border-radius: 5px;
    text-align: center;
    margin: 10px 0;
    border: 2px solid #007bff;
  }
  .code-block {
    background-color: #f5f5f5;
    padding: 15px;
    border-radius: 5px;
    font-family: 'Courier New', monospace;
    font-size: 18px;
    border-left: 4px solid #28a745;
  }
---

<!--
_color: white
_footer: 'Photo by Jefferson Santos on Unsplash'
-->

![bg brightness:0.5](https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=1920)

# Claude Codeカスタムコマンド活用術

## 開発効率を劇的に向上させる実践ガイド

---

<!--
_style: "padding-bottom: 50px;"
-->

# 目次

1. **カスタムコマンドとは何か？**
2. **基本的な設定方法**
3. **おすすめカスタムコマンド5選**
4. **高度な機能活用**
5. **チーム活用のベストプラクティス**
6. **よくある失敗パターン**
7. **まとめと次のステップ**

---

# このスライドで話すこと・話さないこと

## 話すこと ✅
- カスタムコマンドの具体的な作成・活用方法
- 実際の開発現場で使えるコマンド例
- チームでの共有・標準化手法
- 効率化の実測効果と事例

## 話さないこと ❌
- Claude Code基本機能の詳細説明
- 他のAIツールとの比較
- 料金・ライセンスに関する情報
- 技術的なトラブルシューティング詳細

---

<!--
_footer: 'Photo by Luca Bravo on Unsplash'
-->

![bg left:40% brightness:0.7](https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800)

# カスタムコマンドとは？

## 頻繁に使用するプロンプトをワンコマンドで実行

<div class="data-box">
<strong>Markdownファイルとして定義し</strong><br>
<strong>瞬時に呼び出し可能</strong>
</div>

## 主な解決課題
- プロンプトの品質バラツキ
- チーム作業方法の統一
- 複雑な指示の記憶負担

---

# なぜカスタムコマンドが重要？

## 従来の問題点

<div class="highlight">
<strong>毎回微妙に違うプロンプト</strong><br>
→ AIの挙動が不安定<br>
→ チーム間での作業品質差<br>
→ 複雑な作業フローの記憶負担
</div>

## 解決による効果
- **同じプロンプトで安定した結果**
- **チームルールのコマンド化**
- **新人でもベテランと同じ品質**
- **複雑な作業を1コマンドで実行**

---

<!--
_footer: 'Photo by Florian Olivo on Unsplash'
-->

![bg right:35%](https://images.unsplash.com/photo-1542831371-29b0f74f9713?w=600)

# 基本的な設定方法

## 2つのスコープ

### 1. プロジェクト固有（推奨）
<div class="code-block">
.claude/commands/
</div>
- チーム共有可能
- Gitで管理
- プロジェクト固有作業

### 2. 個人用
<div class="code-block">
~/.claude/commands/
</div>
- 個人環境のみ
- 全プロジェクト共通

---

# コマンド作成の3ステップ

## ステップ1: ディレクトリ作成
<div class="code-block">
mkdir -p .claude/commands
</div>

## ステップ2: ファイル作成
<div class="code-block">
touch .claude/commands/test-all.md
</div>

## ステップ3: プロンプト記述
<div class="code-block">
# テストを実行し、結果を表示
# 失敗時は修正方法を提案
</div>

## 呼び出し方法
<div class="code-block">
/test-all
</div>

---

# おすすめカスタムコマンド ①

## テスト＆コミット自動化

<div class="data-box">
<strong>コマンド名</strong>: test-and-commit<br>
<strong>機能</strong>: テスト→Lint→コミットの一連フロー
</div>

### 処理内容
1. 全テストを実行し結果確認
2. Lintチェック実行、問題修正提案
3. 適切なコミットメッセージ生成
4. コミット準備完了を報告

### 効果
- **従来**: 5-10分の手動チェック
- **コマンド後**: 1分で完了
- **品質向上**: 見落としリスク80%削減

---

<!--
_footer: 'Photo by FLY:D on Unsplash'
-->

![bg left:30% brightness:0.8](https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=600)

# おすすめカスタムコマンド ②

## セキュリティレビュー

<div class="highlight">
<strong>security-review</strong><br>
包括的セキュリティチェック
</div>

### チェック項目
- **入力検証**: SQLインジェクション、XSS対策
- **認証・認可**: 権限制御、セッション管理
- **データ保護**: 暗号化、情報漏洩防止
- **設定・デプロイ**: HTTPSヘッダー、ポート管理

### 出力形式
リスクレベル（高・中・低） + 具体的改善提案

---

# おすすめカスタムコマンド ③

## ドキュメント自動生成

<div class="data-box">
<strong>doc-generator</strong><br>
コードベースから仕様書を自動生成
</div>

### 生成内容
- **プロジェクト概要**: 目的、技術スタック
- **API仕様**: エンドポイント、認証方法
- **DB設計**: テーブル構造、リレーション
- **セットアップ**: 環境構築、初期設定
- **運用・保守**: 監視、バックアップ戦略

### 特徴
マークダウン出力 + 図表位置明示

---

# おすすめカスタムコマンド ④⑤

## コード最適化レビュー
<div class="highlight">
<strong>optimize-code</strong><br>
パフォーマンス + 保守性の最適化提案
</div>

- **アルゴリズム効率性**: 時間・空間計算量
- **データベース最適化**: クエリ、インデックス
- **保守性向上**: 可読性、設計改善

## Marpスライド生成
<div class="highlight">
<strong>create-marp-slide $ARGUMENTS</strong><br>
トピックからプレゼンテーション生成
</div>

- 完全なスライド構成（目次〜まとめ）
- Marpフロントマター含む完全出力

---

<!--
_footer: 'Photo by John Schnobrich on Unsplash'
-->

![bg right:40% brightness:0.6](https://images.unsplash.com/photo-1556075798-4825dfaaf498?w=800)

# 高度な機能活用

## 引数（Arguments）
<div class="code-block">
ファイル「$ARGUMENTS」をレビュー<br>
→ /code-review utils.js
</div>

## ファイル参照（@プレフィックス）
<div class="code-block">
@README.md を参考に概要説明作成
</div>

## Bashコマンド統合（!プレフィックス）
<div class="code-block">
!npm test<br>
結果を分析し修正提案
</div>

---

# チーム活用のベストプラクティス

## プロジェクト共有設定

<div class="code-block">
.claude/commands/<br>
├── team/           # チーム標準<br>
│   ├── code-review.md<br>
│   └── security-scan.md<br>
├── project/        # プロジェクト固有<br>
│   └── deploy-check.md<br>
└── README.md       # 使用ガイド
</div>

## バージョン管理
- **コミット対象**: チーム共有コマンド
- **除外対象**: 個人用コマンド（.gitignore設定）

---

# よくある失敗パターン

## ❌ 失敗例1: 過度な汎用化
<div class="code-block">
# 抽象的すぎる<br>
コードを改善してください。
</div>

## ✅ 改善例1: 具体的な指示
<div class="code-block">
# 明確で実行可能<br>
エラーハンドリング、変数名、<br>
単一責任、テストカバレッジを<br>
確認し改善提案を提示
</div>

## ❌ 失敗例2: 危険な引数使用
<div class="code-block">
$ARGUMENTS のファイルを削除
</div>

## ✅ 改善例2: 安全性チェック付き
<div class="code-block">
存在確認→バックアップ検討→<br>
依存関係チェック→削除提案
</div>

---

<!--
_footer: 'Photo by Austin Distel on Unsplash'
-->

![bg left:35%](https://images.unsplash.com/photo-1556761175-b413da4baf72?w=600)

# 導入ステップ

## Phase 1: 個人検証（1週間）

<div class="data-box">
基本3コマンド導入<br>
効果測定開始
</div>

## Phase 2: チーム試用（2-3週間）
- チーム標準コマンド作成
- ハンズオン研修実施
- フィードバック収集・改善

## Phase 3: 全社展開（1ヶ月）
- 組織標準化
- 継続的改善プロセス確立

---

# 成功指標（KPI）

## 定量的効果

<div class="highlight">
<strong>開発速度</strong>: 30%短縮<br>
<strong>品質向上</strong>: バグ発生率20%削減<br>
<strong>標準化</strong>: 作業統一率90%<br>
<strong>学習効果</strong>: 新人立ち上がり50%短縮
</div>

## 定性的効果
- **満足度**: 開発者エクスペリエンス向上
- **一貫性**: プロジェクト間品質統一
- **知識共有**: ベテランノウハウ資産化
- **モチベーション**: 単調作業からの解放

---

<!--
_color: white
_footer: 'Photo by Riccardo Annandale on Unsplash'
-->

![bg brightness:0.4](https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=1920)

# まとめ：次のアクションプラン

## 今日から始めること

<div class="data-box">
<strong>今日</strong>: 最初のコマンド作成<br>
<strong>今週</strong>: 3つの基本コマンドで効果測定<br>
<strong>来月</strong>: チームメンバーとコマンド共有
</div>

## 中長期展開
- **3ヶ月**: プロジェクト標準コマンドセット
- **6ヶ月**: 組織横断ベストプラクティス
- **1年**: AI協調開発文化の浸透

---

# 最後のメッセージ

<div class="highlight">
<strong>カスタムコマンドは、AIと人間がより良く協調して<br>価値を創出するための橋渡し役</strong>
</div>

## 成功の鍵
**小さく始めて、継続的に改善し、<br>チーム全体で価値を最大化する**

## 目指すゴール
単なる効率化を超えて、**より創造的で価値の高い仕事**にフォーカスできる環境づくりの実現

<div class="data-box">
今日からカスタムコマンド活用を開始しましょう！
</div>