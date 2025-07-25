# Marp Web Editorでの文字切れ調整ガイド

## 問題が起きやすいスライド

1. **目次ページ** - 8項目のリスト
2. **Claude Codeとは** - 特徴とメリットのリスト
3. **効率的な指示のコツ** - 複数のリストと説明
4. **CLAUDE.mdの活用** - コードブロックを含む

## 調整方法

### 方法1: 個別スライドの微調整（推奨）

特定のスライドだけを調整したい場合、そのスライドの直後に以下を追加：

**軽度の調整：**
```markdown
<!-- _style: "padding-bottom: 45px;" -->

# スライドタイトル
```

**中程度の調整（リストが多い場合）：**
```markdown
<!-- _style: "padding-bottom: 60px;" -->

# スライドタイトル
```

**重度の調整（コンテンツが非常に多い場合）：**
```markdown
<!-- _style: "padding-bottom: 60px; font-size: 16px;" -->

# スライドタイトル
```

**超重度の調整（コードブロックや長いリスト）：**
```markdown
<!-- _style: "padding-bottom: 70px; font-size: 15px;" -->

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

### 方法5: 組み合わせ調整（最強）

非常にコンテンツが多い場合は、複数の手法を組み合わせ：

```markdown
<!--
_style: "
  padding-bottom: 70px; 
  font-size: 15px; 
  line-height: 1.3;
  padding-left: 50px;
  padding-right: 40px;
"
-->

# スライドタイトル
```

## 調整のレベル分け

1. **Lv.1（軽度）**: `padding-bottom: 45px;` - 基本的なリスト
2. **Lv.2（中度）**: `padding-bottom: 60px;` - 多数のリスト項目
3. **Lv.3（重度）**: `padding-bottom: 60px; font-size: 16px;` - 詳細説明付き
4. **Lv.4（超重度）**: `padding-bottom: 70px; font-size: 15px;` - コードブロック・長文
5. **Lv.5（最強）**: 組み合わせ調整 - 超大量コンテンツ

## よくある質問

**Q: どの方法を最初に試すべき？**
A: Lv.1から順番に試し、はみ出しが解消されるまで強化

**Q: 全体的に窮屈に見える場合は？**
A: 方法2（コンテンツ分割）を検討

**Q: プレゼン全体で統一感を保ちたい**
A: 方法3（スタイル全体調整）を使用

**Q: それでもはみ出す場合は？**
A: 方法5（組み合わせ調整）で最強の調整を適用

## 方法6: 左右分割レイアウト

内容が非常に多い場合は、左右に分割して表示：

```markdown
<!--
_style: "
  display: flex;
  flex-direction: row;
  padding: 30px 40px 60px 40px;
"
-->

# スライドタイトル

<div style="flex: 1; padding-right: 20px;">

## 左側コンテンツ

- 項目1
- 項目2  
- 項目3
- 項目4

</div>

<div style="flex: 1; padding-left: 20px;">

## 右側コンテンツ

- 項目5
- 項目6
- 項目7  
- 項目8

</div>
```

## 方法7: 極限調整（最終手段）

すべての手法を組み合わせた極限調整：

```markdown
<!--
_style: "
  padding: 15px 30px 80px 30px;
  font-size: 14px;
  line-height: 1.2;
  display: flex;
  flex-direction: column;
"
-->

# タイトル（上部固定）

<div style="display: flex; flex: 1;">
<div style="flex: 1; padding-right: 15px; font-size: 13px;">

## 左側
内容...

</div>
<div style="flex: 1; padding-left: 15px; font-size: 13px;">

## 右側  
内容...

</div>
</div>
```

## 調整のレベル分け（更新版）

1. **Lv.1（軽度）**: `padding-bottom: 45px;` - 基本的なリスト
2. **Lv.2（中度）**: `padding-bottom: 60px;` - 多数のリスト項目
3. **Lv.3（重度）**: `padding-bottom: 60px; font-size: 16px;` - 詳細説明付き
4. **Lv.4（超重度）**: `padding-bottom: 70px; font-size: 15px;` - コードブロック・長文
5. **Lv.5（最強）**: 組み合わせ調整 - 超大量コンテンツ
6. **Lv.6（左右分割）**: 左右分割レイアウト - 構造的解決
7. **Lv.7（極限）**: 全手法組み合わせ - 最終手段

## フォントサイズ調整パターン

### パターンA: 全体縮小
```markdown
<!-- _style: "font-size: 16px; line-height: 1.4;" -->
```

### パターンB: リストのみ縮小
```markdown
<!-- _style: "padding-bottom: 60px;" -->
<style>
ul li { font-size: 15px !important; line-height: 1.3 !important; }
ol li { font-size: 15px !important; line-height: 1.3 !important; }
</style>
```

### パターンC: 段階的縮小
```markdown
<!--
_style: "
  padding-bottom: 70px;
  font-size: 17px;
"
-->
<style>
h2 { font-size: 24px !important; margin-bottom: 15px !important; }
h3 { font-size: 20px !important; margin-bottom: 12px !important; }
ul li, ol li { 
  font-size: 14px !important; 
  line-height: 1.25 !important; 
  margin-bottom: 8px !important; 
}
</style>
```

## 具体的な問題別解決法

### 問題1: 長いリストがはみ出す
**解決策**: Lv.2-3 + リスト縮小

```markdown
<!-- _style: "padding-bottom: 65px;" -->
<style>
ul li { font-size: 15px !important; line-height: 1.3 !important; margin-bottom: 8px !important; }
</style>
```

### 問題2: コードブロックがはみ出す  
**解決策**: Lv.4 + コード縮小

```markdown
<!--
_style: "
  padding-bottom: 75px;
  font-size: 15px;
"
-->
<style>
pre { font-size: 12px !important; padding: 8px !important; margin: 8px 0 !important; }
</style>
```

### 問題3: 複雑な構造がはみ出す
**解決策**: Lv.6（左右分割）

```markdown
<!--
_style: "
  display: flex;
  flex-direction: row;
  padding: 25px 35px 70px 35px;
  font-size: 15px;
"
-->
```

### 問題4: 何をしてもはみ出す
**解決策**: Lv.7（極限調整）

```markdown
<!--
_style: "
  padding: 12px 25px 85px 25px;
  font-size: 13px;
  line-height: 1.15;
  display: flex;
  flex-direction: column;
"
-->
<style>
h1 { font-size: 32px !important; margin-bottom: 15px !important; }
h2 { font-size: 22px !important; margin-bottom: 12px !important; }
h3 { font-size: 18px !important; margin-bottom: 10px !important; }
ul li, ol li { 
  font-size: 12px !important; 
  line-height: 1.2 !important; 
  margin-bottom: 6px !important; 
}
pre { font-size: 10px !important; padding: 6px !important; }
</style>
```

## トラブルシューティング

**症状**: padding-bottomを増やしても効果がない
**原因**: コンテンツ量が多すぎる
**対策**: フォントサイズも同時に縮小

**症状**: 左右分割でも収まらない  
**原因**: 個別項目が長すぎる
**対策**: 内容の簡略化 + 極限調整

**症状**: 文字が小さすぎて読めない
**原因**: 過度な縮小調整
**対策**: コンテンツ分割を検討（2スライドに分ける）