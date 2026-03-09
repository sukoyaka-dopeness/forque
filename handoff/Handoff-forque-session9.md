# HANDOFF: forque 第九段階 引き継ぎ
<!-- generated: 2026-03-09 / session: 8 / AI: Claude (Anthropic) -->

---

## あなたへ（次のAI）

あなたはforqueという創作者マッチングサービスの仕様策定セッションを引き継ぎます。
第八段階はClaude (Anthropic) が担当しました。
このドキュメントを読めば、現在の全仕様と未完了タスクを把握できます。

---

## context_state.json
```json
{
  "project": "forque",
  "repository": "https://github.com/sukoyaka-dopeness/forque",
  "relay_hub_repository": "https://github.com/sukoyaka-dopeness/Project-Relay-Hub/tree/main/forque",
  "current_session": 9,
  "current_ai": "TBD",
  "session_status": "handoff",
  "user": "sukoyaka-dopeness",
  "date": "2026-03-09",
  "pending_tasks": [
    "整形済みファイルのforqueリポジトリへの移行（4ファイル）",
    "forklore-galaxyとの接続仕様の正式化（future-challenges.md → specifications.md の順）",
    "系譜デモシナリオ「森の声」の詳細設計（onboarding用・specifications.md反映）",
    "future-challenges.md 4.5への追記（つながり申請断られた独立ブランチの商用利用不可自動設定の可否）",
    "discussion-summary.mdをdocs/サブフォルダへ移行（forqueリポジトリ上）"
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
    "ステータス文字数：英語版50 characters対応（多言語化時）",
    "ノード単位UI呼称の決定（「作品」「枝」「ノード」等・未決定）",
    "「声をかける」UI表示の最終決定（「コメントする」vs「声をかける」）",
    "Incorporation Request UI文言の非技術者向け設計",
    "「Author's Pick」英語翻訳の確定（現在 author's pick で暫定）",
    "推し枝指定確認ダイアログの最終文言確定",
    "商用二次利用時クレジット標準形の正式化",
    "派生文化前提への同意をLPで明示する設計",
    "展開案送信を派生フローに誘導するUIガイド設計"
  ],
  "file_status": {
    "PHILOSOPHY.md": "整形完了（session7）",
    "specifications.md": "整形完了（session8）・移行待ち",
    "glossary.md": "整形完了（session8）・移行待ち",
    "future-challenges.md": "整形完了（session8）・移行待ち",
    "discussion-summary.md": "整形完了（session8）・docs/移行待ち",
    "README.md": "既存（forqueリポジトリ）",
    "handoff/Handoff-forque-session8.md": "既存",
    "handoff/Handoff-forque-session9.md": "このファイル"
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
| 第八段階 | Claude | ファイル整形・設計議論・future-challenges追記 |
| **第九段階** | **TBD** | **ファイル移行・forklore-galaxy接続・「森の声」詳細設計** |

---

## 第八段階で完了した作業

### 1. ファイル整形（4ファイル）

| ファイル | 主な変更内容 |
|---|---|
| specifications.md | 英語一次化・Discord優先記述削除・JSON修正・Section 9テーブル補完・セッション7確定仕様統合（Pace・LP・チュートリアル等） |
| glossary.md | 英語一次化・8カテゴリに再編・AIリレーセッション関連セクション削除・17語追加・2語拡充 |
| future-challenges.md | セクション番号修正（1〜9）・優先度まとめを冒頭に一本化・Discord優先記述削除・セッション8追記9項目統合 |
| discussion-summary.md | 英語一次化・Grok重複解消・Copilot重複解消・Session 6・7・8を新規追記 |

### 2. リポジトリ構成の確定

```
forque/
├── README.md
├── PHILOSOPHY.md
├── specifications.md
├── glossary.md
├── future-challenges.md
├── docs/
│   └── discussion-summary.md
└── handoff/
    ├── Handoff-forque-session7.md
    ├── Handoff-forque-session8.md
    └── Handoff-forque-session9.md
```

**WHY `docs/` サブフォルダ：** discussion-summary.mdはサービス仕様ではなくプロセス記録であるため、仕様文書群と分離。興味のある人だけアクセスできればよい。

### 3. Topics タグの決定（10件）

```
creative-collaboration / fork-culture / lineage / creator-tools /
open-standard / psychological-safety / attribution /
indie-creator / anti-optimization / japanese
```

---

## 第八段階で決定した設計事項

### 独立ブランチ（旧：孤立ブランチ）

名称変更の理由：「孤立」は問題のある状態を連想させるが、「独立」は意志のある状態を示す。

発生ケース（4種）：
1. 取り込み依頼を送らずに派生したフォーク
2. 取り込み依頼がメインブランチ作成者に断られたフォーク
3. 作者不在・活動停止で接続先を失ったブランチ
4. 意図的に系譜から切り離されたブランチ（切断操作）

### 推し枝 / Author's Pick

- UIダイアログ：「この枝を推す」
- 指定されたブランチの呼称：「推し枝」
- 英語：`author's pick`（暫定）
- 商用二次利用（アニメ化等）において、推し枝が権利契約の参照ラインとなる
- 指定時に確認ダイアログを表示（重さを伝えつつビビらせない設計が必要）
- 変更可能だが変更履歴はlineageに残す

確認ダイアログ草案：
```
この枝を推しますか？
「推し枝」に指定すると、この枝が商用利用・
二次展開の際の公式ラインとして参照されます。
後から変更することもできます。
[やめておく]　[この枝を推す]
```

### 本流の暫定性

「本流」はforqueの哲学的中核ではなく、現代の著作権法・商慣習がそれを必要としているために存在している暫定的概念。mainlessへの移行は法制度・商慣習の変化を待つ側面がある。

### 展開案→フォークフローへの誘導

「声をかける」フォームへの事前ガイドを置き、展開案をフォークフローに誘導する設計方針。展開案専用UIは作らない。

```
この欄は感想・批評・コラボの申し出のためのものです。
展開案を提案したい場合は「枝として派生する」をどうぞ。
```

### 商用二次利用時クレジット標準形（暫定）

対外クレジット：「メインブランチ名＋プロジェクト」（例：「森の声プロジェクト」）
内部記録：lineageに全貢献者を記録
名義変更：メインブランチ作者が変更可能・変更履歴はlineageに残す

---

## 次のセッションでやること（優先度順）

1. **整形済みファイルのforqueリポジトリへの移行**（4ファイル＋docs/フォルダ作成）
2. **forklore-galaxy接続仕様の正式化**（future-challenges.md→specifications.mdの順）
3. **「森の声」デモシナリオの詳細設計**（specifications.mdに反映）
4. **future-challenges.md 4.5への追記**（独立ブランチの商用利用不可自動設定の可否）

---

## 引き継ぎ上の注意

- 作者表記は `sukoyaka-dopeness` で統一（他の表記は使わない）
- sukoyaka-dopeness はプログラミング経験がなく、2026年初頭からVS Code/GitHubを使い始めた
- ドキュメントは**英語一次・日本語二次**（見出し英語・本文EN→JPの順）
- WHY（理由）を必ず記録する
- **Web先行MVPへの方針転換は重要な前提。** Discord bot前提の設計に戻らないよう注意
- Discord botは概念検証として並走（廃止ではない）
- `context_state.json` を正規の状態管理として扱う
- 「本流」はUIには出さない方向。推し枝・author's pickを使う
- 未決定のUI用語が多数ある（deferred_tasks参照）——決定済みと混同しないよう注意

---

*このハンドオフ文書は Claude (Anthropic) / 第八段階 / 2026-03-09 に生成されました。*
