# HANDOFF: forque 第八段階 引き継ぎ
<!-- generated: 2026-03-09 / session: 7 / AI: Claude (Anthropic) -->

---

## あなたへ（次のAI）

あなたはforqueという創作者マッチングサービスの仕様策定セッションを引き継ぎます。
第七段階はClaude (Anthropic) が担当しました。
このドキュメントを読めば、現在の全仕様と未完了タスクを把握できます。

---

## context_state.json
```json
{
  "project": "forque",
  "repository": "https://github.com/sukoyaka-dopeness/forque",
  "relay_hub_repository": "https://github.com/sukoyaka-dopeness/Project-Relay-Hub/tree/main/forque",
  "current_session": 8,
  "current_ai": "TBD",
  "session_status": "handoff",
  "user": "sukoyaka-dopeness",
  "date": "2026-03-09",
  "pending_tasks": [
    "specifications.mdの整形（英語一次・日本語二次・Discord優先MVP記述の削除）",
    "glossary.mdの整形（コア用語の大幅追加：Pace・lineage・fork・FORQUE規格等）",
    "future-challenges.mdの整形（セクション番号崩壊の修正・優先度まとめの重複解消）",
    "discussion-summary.mdの整形（Grok第三段階の重複記述解消）",
    "チュートリアルフロー設計の文書化（specifications.mdに反映）",
    "forklore-galaxyとの接続仕様の正式化（PHILOSOPHY.md追記済み・future-challenges.md・specifications.mdの順）",
    "forqueリポジトリへのファイル移行（整形完了後）",
    "系譜デモシナリオ「森の声」の詳細設計（オンボーディング用）"
  ],
  "deferred_tasks": [
    "mainless + lineageツリーの可視化実装（Web移行後）",
    "陪審制の実装（v1.0以降）",
    "物理派生のC2PA対応（MVP後期）",
    "Fediverse連携（v2.0）",
    "自動収益分配（商用申告型）",
    "企業コンペ形式依頼機能",
    "切断操作の詳細設計（v1.0）",
    "黙認二次創作問題の方針策定（継続議論）",
    "Dormantカスタム絵文字設計（Discord版）",
    "ステータス文字数：英語版50 characters対応（多言語化時）"
  ],
  "file_status": {
    "PHILOSOPHY.md": "整形完了（session7）",
    "specifications.md": "整形待ち",
    "glossary.md": "整形待ち（コア用語追加が必要）",
    "future-challenges.md": "整形待ち",
    "discussion-summary.md": "session7追記済み・整形待ち",
    "README.md": "新規作成済み（forqueリポジトリ）",
    "handoff/Handoff-forque-session7.md": "既存",
    "handoff/Handoff-forque-session8.md": "このファイル"
  }
}
```

---

## セッション概要

### リレー構成

| 段階 | AI | 主なテーマ |
|---|---|---|
| 第一段階 | Perplexity | 基本構想・安全性 |
| 第二段階 | Gemini | 差別化・系譜設計・心理的設計 |
| 第三段階 | Grok | 仕様レビュー・MVP設計・FORQUE規格 |
| 第四段階 | Copilot | 倫理層・本流ポリシー・継承ポリシー・未来対応 |
| 第五段階 | ChatGPT | 権利・メタデータ管理・ブランチ表示 |
| 第六段階 | Claude | 用語設計・Pace設計・ガバナンス・MVP戦略見直し |
| 第七段階 | Claude | LP文言・Paceアイコン完成・チュートリアル・リポジトリ構成 |
| **第八段階** | **TBD** | **ファイル整形・forklore-galaxy接続・ファイル移行** |

---

## 第七段階で確定した仕様（全文）

### 1. ランディングページ文言

**キャッチコピー（2案・使い分け運用）**
- LP本体ヒーロー：「あなたの作品が、誰かの種になる。」
- SNS告知・開発者向け：「派生を、誇れ。」

**核心的価値観3点**

| # | JP | EN |
|---|---|---|
| 1 | 派生は、文化だ。 | Derivation is culture. |
| 2 | 歩幅は、自分で決める。 | You decide your own Pace. |
| 3 | プロセスが、作品になる。 | The process is the work. |

各価値観に説明文（日英）あり。discussion-summary.md参照。

**CTA文言**
- ボタン：「先行登録する」
- 登録数カウンター：「○○人が、種を待っています。」

**LP構成（Carrd想定）**
```
[ヒーロー] キャッチコピー + CTA
[価値観] 3点カード（3列 / スマホは縦積み）
[カウンター] ○○人が、種を待っています。
[フッター]
```

---

### 2. Paceアイコン詳細設計（完成）

**4段階**

| アイコン | ラベル | 英語名 | Discord代替 |
|---|---|---|---|
| 🐢 | ゆっくり | Slow | `:turtle:` |
| 🐇 | ふつう | Steady | `:rabbit:` |
| 🚀 | 全力 | Sprint | `:rocket:` |
| 🫘 | 休眠 | Dormant | 💤（暫定） |

**各Paceの説明文（確定）**

🐢 Slow
- JP：返信に時間がかかることがあります。でも、ちゃんと読んでいます。
- EN：I take my time. Replies may be slow, but I'm fully here.
- こんな人：本業・学業と並行 / 丁寧に仕上げることを優先

🐇 Steady
- JP：マイペースで、でも継続的に動いています。
- EN：Moving at my own rhythm, consistently.
- こんな人：週数回は創作時間を確保 / 長期プロジェクト参加可

🚀 Sprint
- JP：今は全力で走れる時期です。早めに動けます。
- EN：I'm in full sprint mode. Fast replies, deep commitment.
- こんな人：DM返信当日〜翌日 / 短期集中型コラボ向き

🫘 Dormant（システム付与・ユーザー選択不可）
- 付与条件：90日未ログイン（自動検知）
- 表示：既存Paceアイコンが薄く（opacity 40%）＋右下に🫘オーバーレイ
- JP（閲覧者向け）：しばらく活動が止まっています。返信に時間がかかる可能性があります。
- EN：Currently inactive. This person hasn't been seen in a while.
- 解除：ログイン後自動解除
- Web版：🫘 / Discord版：💤（暫定）。将来カスタム絵文字化

**Pace選択UI文言（確定）**

初回ガイド：
> あなたの「歩幅」を教えてください。
> 返信の速さ・制作のペース・関与の深さ——今の自分に近いものを選んでください。
> 速いほどいい、ということはありません。

変更時トースト：
> Paceを「ふつう」に変更しました。

プロジェクト上書き時（デフォルトと異なる場合）：
> このプロジェクトでは、普段より[速く/ゆっくり]動いています。

**粒度**
- ユーザーデフォルト＋プロジェクト上書き可の二層構造
- 変更：アイコンをタップ→即切り替え→トースト通知のみ
- 「？」ボタンで3軸ガイドを再表示可能

---

### 3. ステータス自由投稿

- ユーザープロフィールトップに1行の自由投稿欄
- Paceとは別軸（Paceが「季節」、ステータスが「今日の天気」）
- 文字数上限：日本語25字 / 英語50 characters（多言語化時・将来課題）
- 任意・空欄時は非表示（催促しない）
- 例：「長編〆切前」「壁打ち歓迎中」「充電期間」

---

### 4. チュートリアルフロー（Web先行MVP前提）
```
[登録完了]
     ↓
① デモシナリオ「森の声」（スキップ可）
     ↓
② Pace申告（必須・唯一の最初のアクション）
     ↓
③ オンボーディング2問
     ↓
④ 作品登録（任意・スキップ可）
     ↓
⑤ ホーム画面
```

**「森の声」デモ（4コマ縦スクロール静的版）**

| コマ | キャラ | アクション | テキスト |
|---|---|---|---|
| 1 | 絵師 Amara | 森のキャラを描いて公開 | 「種を蒔きました」 |
| 2 | 小説家 Berk | Amaraの絵に触発されて短編を書く | 「芽が出ました」 |
| 3 | 音楽家 Celia | テーマ曲を作る | 「枝が伸びました」 |
| 4 | 批評家 Dani | 3人を繋ぐ批評を投稿 | 「森になりました」 |

最終コマ後：
> あなたの作品も、誰かの種になる。
> [はじめる] [スキップ]

- MVP実装：Carrdで静的縦並び（カード送りUIはWeb本実装時）
- スキップ後のリカバリー：🌱「はじめての方へ」常設リンク

---

### 5. オンボーディング2問（確定）

**Q1：あなたは主にどんな手段で創ります？（複数選択可）**
```
□ イラスト・漫画
□ 小説・文章
□ 音楽・サウンド
□ 映像・アニメーション
□ ゲーム・インタラクティブ
□ 批評・評論
□ その他
```

**Q2：今、どんな関わりを探していますか？（複数選択可）**
```
□ 誰かの作品から派生したい（受け取る側）
□ 自分の作品が派生してほしい（渡す側）
□ 一緒に何かを作りたい（共同制作）
□ まず眺めていたい（観察モード）
```

- 「観察モード」選択者：マッチング対象外（閲覧のみ）・後から変更可
- WHY：作品なし問題を観察モードで自然に解消

---

### 6. forqueリポジトリ構成（確定）

**リポジトリ：** `https://github.com/sukoyaka-dopeness/forque`
```
forque/
├── README.md          （英語のみ）
├── PHILOSOPHY.md      （整形完了）
├── specifications.md  （整形待ち）
├── glossary.md        （整形待ち）
├── future-challenges.md （整形待ち）
├── discussion-summary.md （session7追記済み・整形待ち）
└── handoff/
    ├── Handoff-forque-session7.md
    └── Handoff-forque-session8.md
```

---

### 7. ファイル整形方針（確定）

| ファイル | 形式 |
|---|---|
| README.md | 英語のみ |
| 仕様文書群 | 見出し英語・本文EN→JP併記 |

**既知の整形問題（次セッションで対応）**

| ファイル | 問題 |
|---|---|
| specifications.md | Discord優先MVP記述が残存・Section 9テーブルが空・JSON構文エラー |
| future-challenges.md | セクション番号崩壊・優先度まとめが重複 |
| glossary.md | コア用語（Pace・lineage・fork等）が未掲載 |
| discussion-summary.md | Grok第三段階の記述がほぼ全文重複 |

---

## 次のセッションでやること（優先度順）

1. **specifications.mdの整形**（Discord優先MVP記述削除・JSON修正・英語一次化）
2. **glossary.mdの整形＋コア用語追加**
3. **future-challenges.mdの整形**（番号崩壊修正・重複解消）
4. **discussion-summary.mdの整形**（Grok重複解消）
5. **forklore-galaxy接続仕様の正式化**（future-challenges.md→specifications.mdの順）
6. **整形済みファイルのforqueリポジトリへの移行**

---

## 引き継ぎ上の注意

- 作者表記は `sukoyaka-dopeness` で統一（他の表記は使わない）
- sukoyaka-dopeness はプログラミング経験がなく、
  2026年初頭からVS Code/GitHubを使い始めた
- ドキュメントは**英語一次・日本語二次**（見出し英語・本文EN→JPの順）
- WHY（理由）を必ず記録する
- **Web先行MVPへの方針転換は重要な前提。**
  Discord bot前提の設計に戻らないよう注意
- Discord botは概念検証として並走（廃止ではない）
- `context_state.json` を正規の状態管理として扱う

---

*このハンドオフ文書は Claude (Anthropic) / 第七段階 / 2026-03-09 に生成されました。*
