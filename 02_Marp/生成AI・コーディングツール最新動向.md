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
  .comparison-table {
    font-size: 16px;
    width: 100%;
    border-collapse: collapse;
  }
  .comparison-table th,
  .comparison-table td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
  }
  .comparison-table th {
    background-color: #007bff;
    color: white;
  }
---

# 生成AI・コーディングツール最新動向 2025

## エージェント時代の到来：開発革命の最前線

---

<!--
_style: "padding-bottom: 30px;"
-->

# 目次

1. **現在地の確認：2025年の開発現場**
2. **2025年主要プレイヤーマップ**
3. **Claude Code：最新エージェント型の実力**
4. **GitHub Copilot：進化する老舗の戦略**
5. **Google Jules：Gemini 2.0の潜在力**
6. **Devin：完全自律型の挑戦**
7. **Windsurf：補完設計の哲学**
8. **業界再編：買収・提携の嵐**
9. **技術比較：各ツールの特徴**
10. **目的別ツール選択ガイド**
11. **生産性インパクト：実証データ**
12. **導入時の重要課題**
13. **2025年下半期の予測**
14. **エンジニアへの提言**
15. **企業への提言**
16. **まとめ：開発革命の実現に向けて**

---

# このスライドで話すこと・話さないこと

## 話すこと ✅
- 2025年の生成AI・コーディングツールの実用化状況
- 主要ツール（Claude Code、GitHub Copilot、Devin等）の比較
- 実際の開発現場での活用事例と効果測定
- 企業・個人の導入戦略と選択指針

## 話さないこと ❌
- 各ツールの詳細な技術仕様
- 投資・株価に関する情報
- 個別企業の財務分析
- 競合他社の機密情報

---

# 現在地の確認：2025年の開発現場

## 生産性革命が現実に

<div class="data-box">
<strong>GitHub Copilot：コードの30-55%が自動生成</strong><br>
開発時間55%短縮を実現
</div>

- **市場急拡大**: 主要ツールで数百万ユーザー突破
- **企業導入**: 個人から組織規模へ本格展開
- **技術進化**: 補完ツール → 自律型エージェント

## パラダイムシフト
**AI支援開発** から **AI協調開発** への転換

---

# 2025年主要プレイヤーマップ

## エージェント型（自律実行）

<div class="highlight">
<strong>Claude Code</strong>: Anthropic、2025年2月発表<br>
<strong>Devin</strong>: 完全自律型AIエンジニア<br>
<strong>Google Jules</strong>: Gemini 2.0ベース
</div>

## 補完・支援型（リアルタイム）
- **GitHub Copilot**: エージェント機能も追加
- **Cursor**: リアルタイム支援重視
- **Windsurf**: 100万ユーザー突破

## 企業向け統合型
- **Amazon Q Developer**, **Cline**, **各社カスタマイズ**

---

# Claude Code：最新エージェント型の実力

## 基本仕様

<div class="data-box">
<strong>開発元</strong>: Anthropic<br>
<strong>発表</strong>: 2025年2月<br>
<strong>基盤</strong>: Claude 4.0 Sonnet
</div>

## 主要機能
- **自律タスク実行**: 要件から実装まで一気通貫
- **複数ファイル操作**: プロジェクト全体の理解と編集
- **高品質出力**: SWE-bench Verifiedで高スコア
- **企業対応**: セキュリティ・ガバナンス機能

## 競合差別化
**思考プロセス**: より人間らしい問題解決アプローチ

---

# GitHub Copilot：進化する老舗の戦略

## 2025年の新機能

<div class="highlight">
<strong>Copilot Agent Mode</strong>: 自律型実行機能を追加<br>
<strong>マルチモデル対応</strong>: Claude、Gemini選択可能
</div>

- **Copilot Edits**: 複数ファイル一括編集
- **企業機能強化**: より細かい制御とポリシー設定

## 実証された効果
- **生産性向上**: 約55%の作業時間短縮
- **コード品質**: レビュー指摘事項の削減
- **学習促進**: 新技術習得時間40%短縮

---

# Google Jules：Gemini 2.0の潜在力

## 技術仕様

<div class="data-box">
<strong>基盤</strong>: Gemini 2.0<br>
<strong>対応言語</strong>: Python、JavaScript（初期）<br>
<strong>特徴</strong>: 非同期処理による大規模対応
</div>

## 自律機能の特徴
- **計画立案**: タスクから詳細実装計画を自動生成
- **包括的対応**: コード生成、バグ修正、テスト作成
- **GitHub統合**: 既存ワークフローとの親和性

## 提供状況
**現在**: ベータ版・ウェイティングリスト / **正式版**: 2025年前半

---

# Devin：完全自律型の挑戦

## 開発経緯

<div class="data-box">
<strong>初発表</strong>: 2024年3月（プロト）<br>
<strong>正式版</strong>: 2024年12月「Devin 1.0」<br>
<strong>最新版</strong>: 2025年4月「Devin 2.0」
</div>

## 自律性レベル
- **完全独立**: 人間の監督下で全工程実行
- **学習能力**: プロジェクトから知識蓄積
- **継続改善**: フィードバックによる性能向上

## 実用性と課題
- **制御の難しさ**: 完全自律性による予測困難性
- **品質担保**: 人間レビューの重要性継続

---

# Windsurf：補完設計の哲学

## 設計思想

<div class="highlight">
<strong>補完型アプローチ</strong><br>
開発者を「置き換える」ではなく「補完する」
</div>

## 急成長の実績
- **2025年初頭**: 80万アクティブユーザー
- **2025年4月**: **100万ユーザー突破**
- **企業導入**: Fortune 500企業での採用拡大

## 機能特徴
- **リアルタイム提案**: 即座のコード支援
- **既存統合**: 慣れ親しんだワークフローとの調和
- **学習機能**: 使用パターン分析と最適化

---

# 業界再編：買収・提携の嵐

## 2025年の主要動向

### Google による人材獲得
<div class="data-box">
<strong>Windsurf社主要人材獲得</strong><br>
契約金額：24億ドル
</div>

### Cognition による Windsurf買収
- **発表**: 2025年7月14日
- **シナジー**: DevinとWindsurfの技術統合
- **方向性**: 自律型と補完型の融合

### 市場への影響
**技術統合**、**価格競争激化**、**標準化争い**の同時進行

---

# 技術比較：各ツールの特徴

<table class="comparison-table">
<tr>
<th>ツール</th><th>自律性</th><th>リアルタイム</th><th>企業対応</th><th>価格(月)</th><th>特徴</th>
</tr>
<tr>
<td>Claude Code</td><td>高</td><td>中</td><td>強</td><td>従量制</td><td>エージェント型</td>
</tr>
<tr>
<td>GitHub Copilot</td><td>中</td><td>高</td><td>強</td><td>$10-19</td><td>バランス型</td>
</tr>
<tr>
<td>Google Jules</td><td>高</td><td>低</td><td>強</td><td>TBD</td><td>大規模対応</td>
</tr>
<tr>
<td>Devin</td><td>最高</td><td>低</td><td>中</td><td>$20-50</td><td>完全自律</td>
</tr>
<tr>
<td>Windsurf</td><td>低</td><td>最高</td><td>中</td><td>無料-有料</td><td>補完重視</td>
</tr>
<tr>
<td>Cursor</td><td>中</td><td>高</td><td>中</td><td>無料-有料</td><td>開発者体験</td>
</tr>
</table>

---

# 目的別ツール選択ガイド

## 個人開発者
- **初心者**: GitHub Copilot（学習効果重視）
- **上級者**: Claude Code or Cursor（高度機能）
- **予算重視**: Windsurf（無料枠活用）

## 小規模チーム
- **スタートアップ**: Cursor or Windsurf（コスト効率）
- **プロトタイプ**: Claude Code（高品質・高速）
- **維持管理**: GitHub Copilot（安定性）

## 企業・大規模組織
- **Microsoft環境**: GitHub Copilot（統合性）
- **Google環境**: Jules（将来性）
- **カスタム要件**: Claude Code（柔軟性）

---

# 生産性インパクト：実証データ

## GitHub Copilot の成果

<div class="data-box">
<strong>コード生成率</strong>: 30-55%が自動生成<br>
<strong>開発速度</strong>: 平均55%の時間短縮<br>
<strong>品質向上</strong>: バグ率20%削減
</div>

## 企業導入事例
- **Netflix**: 開発チーム全体で月40%の生産性向上
- **Shopify**: コードレビュー時間50%削減
- **Goldman Sachs**: 新人立ち上がり時間60%短縮

## ROI計算例
**投資**: $19/月 → **効果**: $1,200/月 → **ROI**: 6,200%

---

# 導入時の重要課題

## 技術的課題
- **コード品質**: AI生成コードの品質バラツキ
- **セキュリティ**: 機密情報漏洩リスク
- **技術負債**: 短期効率優先による設計品質低下

## 法的・契約課題

<div class="highlight">
<strong>著作権・ライセンス問題</strong><br>
既存コードからの学習による権利問題
</div>

- **データプライバシー**: 企業コードの外部送信懸念
- **規制対応**: GDPR等データ保護法への対応

## 組織・人的課題
- **スキル変化**: 新しい能力要件への対応
- **チーム動学**: 開発プロセス・役割分担の見直し

---

# 2025年下半期の予測

## 技術発展方向

### マルチモーダル対応
<div class="data-box">
<strong>現状</strong>: テキストベース<br>
<strong>発展</strong>: 画像・音声からのコード生成
</div>

### リアルタイム協調
- **機能**: 複数AIエージェントの協調作業
- **効果**: 大規模プロジェクトの並列開発

### ドメイン特化
- **傾向**: 業界・領域特化AIの登場
- **例**: 金融系、医療系、ゲーム開発専用

---

# 市場予測と新プレイヤー

## 普及率拡大予測

<div class="data-box">
<strong>現在</strong>: 先進企業30%が導入<br>
<strong>2025年末</strong>: 50%超の企業が利用<br>
<strong>2026年</strong>: 個人開発者70%が日常利用
</div>

## 価格競争激化
- **トレンド**: 基本機能の無料化進行
- **差別化**: 企業向け機能で収益化
- **新モデル**: 成果報酬型、利用量課金

## 新プレイヤー参入予想
**Apple、Meta、Tesla** 等の参入検討

---

# エンジニアへの提言

## 学習すべき領域

<div class="highlight">
<strong>1. AI活用スキル</strong>: プロンプトエンジニアリング<br>
<strong>2. アーキテクチャ設計</strong>: システム全体俯瞰力<br>
<strong>3. コードレビュー</strong>: AI生成コード評価能力<br>
<strong>4. ドメイン知識</strong>: 業務領域の深い理解
</div>

## キャリア転換
- **従来**: 実装中心のコーダー
- **将来**: AI協調型エンジニア
- **価値**: 設計・判断・調整能力
- **差別化**: 複合領域での専門性

---

# 企業への提言

## 段階的導入アプローチ

1. **Phase 1**: 個人利用での効果検証（1-3ヶ月）
2. **Phase 2**: 小規模チームパイロット（3-6ヶ月）
3. **Phase 3**: 部門全体への展開（6-12ヶ月）
4. **Phase 4**: 全社標準化と最適化（12ヶ月以降）

## 成功要因

<div class="data-box">
<strong>経営支援</strong> + <strong>変革管理</strong> + <strong>技術基盤</strong> + <strong>人材育成</strong>
</div>

## 投資判断基準
- **短期**: 開発速度向上、バグ減少率
- **中期**: 人的リソース最適化、品質向上
- **長期**: イノベーション創出、競争優位性

---

# まとめ：開発革命の実現に向けて

## 現在の到達点

<div class="highlight">
生成AI・コーディングツールは実証段階を超え、<br>
本格的な産業変革の段階に突入
</div>

## 2025年の重要トレンド
1. **エージェント化**: 補完から自律実行への完成
2. **市場統合**: 買収・提携による技術融合
3. **企業導入**: 組織規模での本格活用
4. **標準化**: デファクトスタンダード争い

---

# 成功への道筋

## 重要な選択基準

<div class="data-box">
<strong>技術選択</strong>: 目的・組織適合性<br>
<strong>段階的導入</strong>: リスク管理された変革<br>
<strong>継続学習</strong>: 急速変化への適応力<br>
<strong>品質担保</strong>: AI活用と品質の両立
</div>

## 未来への準備
生成AI・コーディングツールは効率化ツールを超え、**ソフトウェア開発そのものを再定義**する革新技術

<div class="highlight">
<strong>2025年は、AIと人間の協調による<br>新しい開発時代の始まり</strong>
</div>