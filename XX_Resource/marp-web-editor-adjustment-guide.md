# Marp Web Editorでの文字切れ調整ガイド

## 問題が起きやすいスライド

1. **目次ページ** - 8項目のリスト
2. **Claude Codeとは** - 特徴とメリットのリスト
3. **効率的な指示のコツ** - 複数のリストと説明
4. **CLAUDE.mdの活用** - コードブロックを含む

## 調整方法

### 方法1: 個別スライドの微調整（推奨）

特定のスライドだけを調整したい場合、そのスライドの直後に以下を追加：

```markdown
<!-- _class: content -->
<!-- _style: "padding-top: 20px; padding-bottom: 40px;" -->

# スライドタイトル
```

### 方法2: コンテンツの分割

内容が多すぎる場合は、スライドを2枚に分割：

```markdown
---

<!-- _class: content -->

# タイトル（前半）

1. 項目1
2. 項目2
3. 項目3
4. 項目4

---

<!-- _class: content -->

# タイトル（後半）

5. 項目5
6. 項目6
7. 項目7
8. 項目8
```

### 方法3: スタイル全体の調整

styleセクションで以下を変更：

```css
/* より少ない余白 */
section.content {
    padding-top: 20px;      /* 30px → 20px */
    padding-bottom: 50px;   /* 60px → 50px */
    padding-left: 60px;     /* 80px → 60px */
    padding-right: 50px;    /* 60px → 50px */
}

/* 小さいフォント */
section.content h1 {
    font-size: 40px;        /* 48px → 40px */
    margin-bottom: 20px;    /* 30px → 20px */
}

section.content ol li {
    font-size: 20px;        /* 22px → 20px */
    line-height: 1.4;       /* 1.6 → 1.4 */
    margin-bottom: 10px;    /* 15px → 10px */
}

/* コードブロックの調整 */
pre {
    font-size: 16px;        /* 18px → 16px */
    padding: 12px;          /* 16px → 12px */
    margin: 12px 0;         /* 16px → 12px */
}
```

### 方法4: フッターとの重なり対策

merpayロゴが内容と重なる場合：

```css
section.content::after {
    bottom: 10px;           /* 20px → 10px */
    font-size: 14px;        /* 16px → 14px */
}
```

## 具体的な調整例

### 目次ページの調整前
```markdown
<!-- _class: content -->

# 目次

1. **Claude Codeとは**
2. **4段階ワークフローの概要**
...（8項目）
```

### 目次ページの調整後
```markdown
<!-- _class: content -->
<!-- _style: "padding-bottom: 45px;" -->

# 目次

1. **Claude Codeとは**
2. **4段階ワークフローの概要**
...（8項目）
```

## テスト方法

1. Marp Web Editor (https://marpwebeditor.app/) を開く
2. Markdownを貼り付ける
3. プレビューで確認
4. 必要に応じて上記の方法で調整
5. 調整後、再度エクスポート

## よくある質問

**Q: どの方法を最初に試すべき？**
A: 方法1（個別調整）が最も簡単で影響が少ない

**Q: 全体的に窮屈に見える場合は？**
A: 方法2（コンテンツ分割）を検討

**Q: プレゼン全体で統一感を保ちたい**
A: 方法3（スタイル全体調整）を使用