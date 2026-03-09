# HANDOFF: forque 第六段階 Claude セッション引き継ぎ
<!-- generated: 2026-03-07 / session: 6 / AI: Claude (Anthropic) -->

---

## あなたへ（次のClaude）

あなたはforqueという創作者マッチングサービスの仕様策定セッションを引き継ぎます。
このドキュメントを読めば、これまでの議論の全体像と未完了タスクを把握できます。

---

## context_state.json

```json
{
  "project": "forque",
  "repository": "https://github.com/sukoyaka-dopeness/Project-Relay-Hub/tree/main/forque",
  "current_session": 6,
  "current_ai": "Claude (Anthropic)",
  "session_status": "handoff",
  "user": "deadbody (鳩川カルキ)",
  "date": "2026-03-07",
  "pending_tasks": [
    "specifications.md の全文更新",
    "PHILOSOPHY.md への追記",
    "future-challenges.md への追記",
    "glossary.md の全文更新",
    "Paceアイコンの詳細設計",
    "チュートリアルフロー（/startコマンド）の設計"
  ],
  "deferred_tasks": [
    "mainless + lineageツリーの可視化実装（Web移行後）",
    "陪審制の実装（v1.0以降）",
    "物理派生のC2PA対応（MVP後期）",
    "Fediverse連携（v2.0）"
  ]
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
| **第六段階** | **Claude** | **用語設計・フロー設計・陪審制・ガバナンス** |

---

## 第六段階で確定した仕様

### 1. AI使用率申告の再設計
- 数値（パーセンテージ）申告を廃止
- **プロセス層申告**に変更
  - 使用した工程: 企画 / 下書き / 仕上げ / 翻訳 / その他
  - 使用ツール（任意）
  - 人間の主体性: 主導 / 協働 / 補助的
- メタデータ例: `generated-by: hybrid, process: [ideation, finishing]`
- WHY: プロセスの種類によってAI関与の性質が異なるため数値は無意味

### 2. 誠実度スコアの名称変更
- 「誠実度スコア」→「**申告一致率**」に変更
- 存在は開示・仕組みは非開示（方針B）
- 説明文: 「forqueは申告内容と実際の行動の一致を、コミュニティの健全性の指標として静かに観察しています」
- PHILOSOPHY.mdへの追記: 「申告一致率は完璧な誠実さの測定ではありません。コミュニティが健全であり続けるための、不完全だけど誠実な試みです。」
- レコメンド連動: つながり申請時の参考表示✅ / トップページ優先表示❌

### 3. ビジュアル設計（確定）
植物＋星座のハイブリッドメタファー：

| ブランチ状態 | 植物 | 星座 |
|---|---|---|
| 新規・派生元なし | 🌱 種 | ●単独の星 |
| 派生が発生している | 🌿 芽・茎 | ●—● 線が引かれた星 |
| 複数から合流 | 🌸 花 | ✦ 輝点 |
| 孤立（未接続） | 🫘 休眠種 | ●点滅する星 |
| mainless全体 | 🌲 森 | 星座全体 |

- 「枯れた」「死んだ」アイコンは使わない
- 孤立ブランチは「接続待ちの可能性」として表示
- 非公開（下書き）は家系図に表示しない

### 4. 用語確定リスト（三層構造）

| 技術用語 | UI（一般） | ドキュメント | 規格 |
|---|---|---|---|
| Fork（動詞） | 派生する | 枝分かれ | fork |
| Pull Request | つながり申請 | 取り込み依頼 | pull-request |
| Push | 公開する | 公開 | push |
| Branch | 枝 | 枝 | branch |
| Main Branch | 幹 | 幹／本流 | main-branch |
| Issue | 投げかけ | 投げかけ | issue |
| Lineage | 家系図を見る | 系譜 | lineage |
| Merge | 合流 | 合流 | merge |

### 5. 派生フローの4パターン（確定）
```
【パターン1】公開前 → 申請不可（公開を促すガイド表示）
【パターン2】公開後 → 申請 → 承認 → 家系図に接続
【パターン3】公開後 → 申請 → 却下 → 孤立ブランチとして存在
             └ 引き取りオプション: A.孤立継続 / B.独立プロジェクトとして再出発 / C.非公開
【パターン4】ポリシー許可 → 「派生する」ボタン押下 → 自動チェック → 即時接続
```

### 6. 継承ポリシーへの追加項目（確定）
メインブランチ作成時に設定：

| 設定項目 | 選択肢 |
|---|---|
| 派生の可否 | 許可（申請不要）/ 許可（承認制）/ 不可 |
| 却下後の扱い | 孤立ブランチとして存在を許可 / 系譜から切断 / 作品ごと削除要求可 |
| ポリシーの可視性 | 「派生する」ボタン押下前に表示 |

- WHY: Paceと同じ「期待値の事前調整」の原則を派生フローにも適用

### 7. 合流（merge）ポリシー（確定）
- 異なるプロジェクト同士の合流も可能
- 継承ポリシーが矛盾する場合は厳しい方が優先（自動統一）
- ポリシー競合時はシステム警告＋作者の明示的承認が必要

### 8. お断りテンプレート（確定・日英）

**設計原則:**
- 主語は「私の状況」（相手の作品を評価しない）
- 「今回は」を必ず入れる
- 感謝は一文まで

**日本語版:**
- A（タイミング）: 「いまの自分の歩幅では、このプロジェクトに誠実に向き合える状況ではありません。機会がずれてしまったようです。あなたの作品が誰かに届くことを願っています。」
- B（方向性）: 「拝見しました。今回は私の創作の方向と重なりが少ないと感じました。お声がけいただいたこと自体、ありがたく受け取っています。」
- C（キャパシティ）: 「現在進行中のプロジェクトがあり、新しいコラボへのエネルギーをうまく用意できません。状況が変わったときにまた考えさせてください。」
- D（孤立ブランチ通知・システム送信）: 「今回は系譜をつなげることができませんでした。あなたの作品はここに独立した枝として残ります。別の誰かが手を伸ばすかもしれません。」

**英語版:**
- A: "My current pace doesn't allow me to engage with this project the way it deserves. The timing just doesn't align right now. I hope your work finds the right collaborator."
- B: "Thank you for reaching out. After looking through your work, I feel our creative directions don't overlap enough this time. I genuinely appreciate the invitation."
- C: "I have ongoing projects that are using my full bandwidth right now. I can't take this on with the care it deserves. Let's keep the door open for another time."
- D: "We couldn't connect the lineage this time. Your work remains here as its own branch — someone else may reach for it someday."

### 9. 系譜デモシナリオ（確定・チュートリアル用）
登場人物4名（Amara/Berk/Celia/Dani）による「森の声」プロジェクト。
全仕様（Pace/つながり申請/継承ポリシー伝播/AI申告/投げかけ/孤立ブランチ/lineage）を網羅。
※詳細はdiscussion-summary.mdを参照。

### 10. homage／盗作判定ガバナンス（確定・ロードマップ）

**MVP期:**
- flagのみ実装（flagにはコスト: 回数制限・理由必須・虚偽flagペナルティ）
- 「議論ありバッジ」表示・判定なし
- タイムスタンプ自動防御（flagした側が新しければ自動却下）

**v1.0:**
```
陪審員: 3〜5名（系譜2〜3段階離れ・当該ブランチ未参加・ブランチごとに1票）
AI参考人（複数・投票権なし）:
  - 類似度分析AI: 線・構図・テキストの技術的一致度
  - メタデータAI: タイムスタンプ・制作履歴の整合性
  - 判例AI: 過去の類似ケースを提示
人間参考人: 当事者双方が各1名指名可（投票権なし・テキスト一回限り）
```

**陪審の熟慮促進設計:**
- コンテンツ種別で期限自動調整（イラスト7日/短編14日/長編30日）
- 最低閲覧時間を計測・短すぎる場合は確認を促す（強制なし）
- 判断理由の記述必須（一文以上）
- 陪審員の判断履歴を記録（覆った判断が多い場合は次回選出されにくい）
- 3回連続放棄→申告一致率にペナルティ（長期未ログインは除外）

### 11. 物理派生のメタデータ設計
```json
{
  "format": "physical/sculpture",
  "c2pa-verifiable": false,
  "verification-method": "author-trust"
}
```
- メインブランチ作成者に「検証不可形式の申請」として通知
- 実装はMVP後期フェーズ

---

## PHILOSOPHY.mdへの追記予定（未実施）

以下の4点を追記する：

1. **「制約はforkの母」**: AIリレー方式がトークン制約から生まれ、forqueの系譜思想の実証例になったという事実
2. **「申告一致率は不完全だけど誠実な試み」**: 完璧なシステムを目指さない姿勢の明文化
3. **孤立ブランチの設計思想**: 「接続待ちの可能性」として扱う
4. **「判定しない」選択の正当性**: forqueが正統性を決めないサービスであることと整合

---

## future-challengesへの追記予定（未実施）

- 黙認二次創作問題（文化的受容性の検証・日本 vs 海外）
- 「切断」操作の詳細設計
- 陪審参加の動機づけ設計（系譜への記録では不十分な可能性）
- 申告一致率のゲーミング対策の長期課題
- 物理派生のC2PA対応詳細

---

## 次のセッションでやること

優先度順：

1. **Paceアイコンの詳細設計**（カメ/ウサギ/ロケットの精緻化）
2. **チュートリアルフロー**（/startコマンドの体験設計）
3. **各ファイルの全文更新**（specifications / PHILOSOPHY / future-challenges / glossary）
4. **forqueリポジトリの作成**（deadbodyがClaude Claudeに依頼予定）

---

## 引き継ぎ上の注意

- deadbodyはプログラミング経験がなく、2026年初頭からVS Code/GitHubを使い始めた
- ドキュメントは**英語一次・日本語二次**の形式
- WHY（理由）を必ず記録する
- discussion-summary.mdにはセッション中の決定事項を随時追記する
- Claudeがリポジトリ最終ランナーとして全文書を担当する予定

---

*このハンドオフ文書はClaude (Anthropic) / 第六段階 / 2026-03-07 に生成されました。*
