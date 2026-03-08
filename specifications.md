# Specifications: forque
<!-- last updated: 2026-03-09 / session: 8 / maintained by: sukoyaka-dopeness -->

---

## 1. Core Philosophy (WHY)

**"Creation is remix (re-construction)."**

Demanding pure originality places excessive psychological burden on creators. By recognizing derivation not as shame but as legitimate lineage, forque lowers the psychological barrier to collaboration and accelerates the cycle of creation.

**「創作はクリシェ（再構築）である。」**

ゼロからの完全なオリジナルを強いることは、クリエイターに過剰な心理的負荷をかける。「既存の何かから派生する」ことを「恥」ではなく「正当な系譜」として認めることで、コラボの心理的ハードルを下げ、創作の循環を加速させる。

---

## 2. UI Vocabulary Abstraction (WHY)

Technical terms are hidden. Human-readable names are adopted so creators can operate intuitively.

技術用語を隠蔽し、クリエイターが直感的に操作できる名称を採用する。

| Technical Term | forque Name (JP) | WHY |
|:---|:---|:---|
| Issue | 壁打ち・お題 | Reframes discussion as creative "thought rally," not administrative work. / 議論を事務作業ではなく「思考のラリー」と定義するため。 |
| Pull Request | 取り込み依頼 | Shifts from technical context to "enriching a work with others' contributions." / 技術的文脈から創造的文脈へ変換するため。 |
| Push | 公開・保存 | Emphasizes the active act of recording and sharing output. / 成果を記録・発表する能動的行為を強調するため。 |
| Fork | 創作の種・派生 | Shows the positive causality: existing work becomes the starting point of new creation. / 既存作品が次なる創作の出発点であることを示すため。 |

---

## 3. Trust & Safety: Psychological Design (WHY)

### 3.1 Pace Profile

**WHY:** Speed mismatches are the leading cause of collaboration breakdown. Requiring creators to declare their Pace upfront calibrates expectations and prevents conflict before it starts.

**WHY：** 制作速度の不一致はコラボ解消の最大の火種。事前に「歩幅」を申告させることで期待値を調整し、トラブルを未然に防ぐ。

#### Pace Levels (4 tiers)

| Icon | Label (JP) | Label (EN) | Discord Alt |
|:---:|:---|:---|:---|
| 🐢 | ゆっくり | Slow | `:turtle:` |
| 🐇 | ふつう | Steady | `:rabbit:` |
| 🚀 | 全力 | Sprint | `:rocket:` |
| 🫘 | 休眠 | Dormant | 💤 (provisional) |

**🐢 Slow**
- EN: I take my time. Replies may be slow, but I'm fully here.
- JP: 返信に時間がかかることがあります。でも、ちゃんと読んでいます。
- Suits: those balancing day jobs or studies; prioritizing careful craftsmanship.
- こんな人：本業・学業と並行 / 丁寧に仕上げることを優先。

**🐇 Steady**
- EN: Moving at my own rhythm, consistently.
- JP: マイペースで、でも継続的に動いています。
- Suits: those who secure creative time several times a week; long-term project participants.
- こんな人：週数回は創作時間を確保 / 長期プロジェクト参加可。

**🚀 Sprint**
- EN: I'm in full sprint mode. Fast replies, deep commitment.
- JP: 今は全力で走れる時期です。早めに動けます。
- Suits: same-day/next-day DM replies; short-burst intensive collaboration.
- こんな人：DM返信当日〜翌日 / 短期集中型コラボ向き。

**🫘 Dormant** *(system-assigned only; users cannot self-select)*
- Trigger: auto-detected after 90 days without login.
- Display: existing Pace icon fades to opacity 40% + 🫘 overlay at bottom-right.
- EN (shown to viewers): Currently inactive. This person hasn't been seen in a while.
- JP（閲覧者向け）: しばらく活動が止まっています。返信に時間がかかる可能性があります。
- Release: automatically removed upon next login.
- Discord version: 💤 (provisional; custom emoji planned for future).

#### Pace UI Copy (confirmed)

*Selection prompt:*
> あなたの「歩幅」を教えてください。
> 返信の速さ・制作のペース・関与の深さ——今の自分に近いものを選んでください。
> 速いほどいい、ということはありません。

*Change toast:*
> Paceを「ふつう」に変更しました。

*Project override (when different from user default):*
> このプロジェクトでは、普段より[速く/ゆっくり]動いています。

**Structure:** Two-tier — user-level default + per-project override.
**Change method:** Tap icon → instant switch → toast notification only. "?" button reopens 3-axis guide.

---

### 3.2 Status Free Text

A single free-text line at the top of the user profile, separate from Pace.

ユーザープロフィールトップに置かれる1行の自由投稿欄。Paceとは別軸。

- Pace = "the season." Status = "today's weather." / Paceが「季節」、ステータスが「今日の天気」。
- Character limit: 25 characters (JP) / 50 characters (EN, for future multilingual support).
- Optional; hidden when empty. No prompting.
- Examples: 「長編〆切前」「壁打ち歓迎中」「充電期間」

---

### 3.3 Positive Pause (Archive)

**WHY:** To eliminate negative feelings like "I got bored" or "I ran away." Treating creation as a completed harvest and formalizing the move to the next cycle encourages healthy fade-outs.

**WHY：** 「飽きた」「逃げた」という負の感情を排除するため。創作をひとつの収穫物として捉え、次のサイクルへ進む儀式化をすることで、健全なフェードアウトを促す。

---

### 3.4 Declination Templates

**WHY:** System-mediated refusal transforms rejection into a neutral "opportunity mismatch," removing emotional burden entirely.

**WHY：** 拒絶による罪悪感をシステムが仲介し、「機会のミスマッチ」という事務的事実に置き換えることで、精神的負担をゼロにするため。

- Multiple default templates provided.
- Preview available before sending.

---

## 4. Revenue & Sustainability (WHY)

**WHY:** Diversifying revenue sources allows maintaining a culture that prioritizes collaboration quality without sacrificing it for profit.

**WHY：** 収益源を多様化することで、売上のために「質」を犠牲にせず、コラボの「質」を重視する文化を維持するため。

- Automatic revenue distribution (deferred to post-MVP): A contribution-graph-inspired model eliminates interpersonal stress around rights negotiation.
- 自動収益分配（MVP後）：GitHubの貢献度グラフを応用した自動分配で、対人ストレスを排除する。

---

## 5. AI Coexistence Culture (WHY)

**WHY:** Rather than treating AI use as inherently bad, the design encourages honest disclosure. Dynamically separating users with inconsistent declarations protects and cultivates an environment of genuine creators.

**WHY：** AIの利用自体を悪とせず、正直な申告を奨励する設計。乖離があるユーザーを動的に分離することで、誠実なクリエイター同士の環境を保護・育成する。

- AI usage rate is visualized on profiles.
- Self-declaration model (see also Section 11 for metadata spec).

---

## 6. Onboarding & Tutorial

### 6.1 MVP Feature Scope

The MVP prioritizes validating psychological safety and lineage visualization in their most essential form. The Web application is the primary platform; Discord bot runs in parallel as a concept-validation companion (not primary delivery).

MVPは心理的安全性と創作の系譜可視化の本質的な検証を優先する。WebアプリがメインプラットフォームでありDiscord botは概念検証として並走する（主要デリバリーではない）。

**Core MVP (required / first to implement)**

- Pace declaration (required) + icon display
- Wall-bouncing (open theme posting)
- Incorporation Request (comment + minimal template message)
- Declination Templates (multiple defaults + preview)
- Portfolio required (external URL + initial work upload validation)
- Age/gender hidden by default (World ID recommended for backend auth; Orb badge optional)
- No-monetization mode (revenue distribution off)
- Year-of-birth/region registration (for minimum safety and community moderation)

**Post-MVP / Deferred (implement in priority order after validation)**

- Invisible integrity score for matching prioritization
- Automatic revenue distribution (commercial declaration type + penalty)
- Git-like history (metadata + external storage reference)
- Corporate competition-style request feature
- Fediverse federation (v2.0)
- FORQUE format implementation (contribution graph sharing format)

**MVP Goal:** Establish the minimum creative loop (theme drop → Request → lineage branching → decline/continue) at a 10–50 user scale to collect feedback.

---

### 6.2 Tutorial Flow (Web-first MVP)

```
[Registration complete]
     ↓
① Demo scenario "Forest Voices" (skippable)
     ↓
② Pace declaration (required — the only mandatory first action)
     ↓
③ Onboarding 2 questions
     ↓
④ Work registration (optional / skippable)
     ↓
⑤ Home screen
```

Skip recovery: 🌱「はじめての方へ」— persistent link always available on home screen.

---

### 6.3 Demo Scenario: "Forest Voices" (森の声)

A 4-panel vertical-scroll static story illustrating lineage formation.

**WHY:** First-time users can intuitively visualize that their work could become someone else's seed. / 初回ユーザーが「自分の作品も誰かの種になり得る」という成功体験を直感的にイメージできるようにするため。

| Panel | Character | Action | Text |
|:---:|:---|:---|:---|
| 1 | Illustrator Amara | Draws a forest character and publishes it | 「種を蒔きました」 |
| 2 | Novelist Berk | Inspired by Amara, writes a short story | 「芽が出ました」 |
| 3 | Musician Celia | Composes a forest theme | 「枝が伸びました」 |
| 4 | Critic Dani | Posts a critique connecting all three | 「森になりました」 |

*After final panel:*
> あなたの作品も、誰かの種になる。
> [はじめる]　[スキップ]

**MVP implementation:** Static vertical card layout (Carrd). Card-swipe UI deferred to full Web implementation.

---

### 6.4 Onboarding Questions (confirmed)

**Q1: What is your primary creative medium? (multiple choice)**

```
□ Illustration / manga　（イラスト・漫画）
□ Fiction / writing　（小説・文章）
□ Music / sound　（音楽・サウンド）
□ Video / animation　（映像・アニメーション）
□ Games / interactive　（ゲーム・インタラクティブ）
□ Criticism / commentary　（批評・評論）
□ Other　（その他）
```

**Q2: What kind of involvement are you looking for right now? (multiple choice)**

```
□ I want to derive from someone's work (receiver)　（誰かの作品から派生したい）
□ I want my work to be derived from (giver)　（自分の作品が派生してほしい）
□ I want to co-create together (collaboration)　（一緒に何かを作りたい）
□ I just want to observe for now (observation mode)　（まず眺めていたい）
```

"Observation mode" selectors: excluded from matching (browse-only); can change later.
**WHY:** Naturally resolves the "no works yet" onboarding problem without friction. / 作品なし問題を観察モードで自然に解消するため。

---

## 7. Landing Page Copy (confirmed)

### 7.1 Catchphrases (two variants, used contextually)

- **LP hero:** 「あなたの作品が、誰かの種になる。」
- **SNS / developer-facing:** 「派生を、誇れ。」

### 7.2 Core Values (3 points)

| # | JP | EN |
|:---:|:---|:---|
| 1 | 派生は、文化だ。 | Derivation is culture. |
| 2 | 歩幅は、自分で決める。 | You decide your own Pace. |
| 3 | プロセスが、作品になる。 | The process is the work. |

### 7.3 CTA Copy

- Button: 「先行登録する」
- Registration counter: 「○○人が、種を待っています。」

### 7.4 LP Structure (Carrd, MVP)

```
[Hero]　Catchphrase + CTA
[Values]　3-card layout (3 columns / vertical stack on mobile)
[Counter]　○○人が、種を待っています。
[Footer]
```

---

## 8. Main Branch Policy

The main branch is a provisional concept for handling legitimacy and official status in current creative culture. In future creative culture, "mainless" may become the natural default. FORQUE defines a flexible policy to handle this transition.

本流（main）は現代の創作文化における「正統性」「公式性」を扱うための暫定的な概念。将来は「mainless」が自然になる可能性がある。FORQUEはこの過渡期に対応するため、柔軟な本流ポリシーを定義する。

### 8.1 Priority Order for Main Branch Determination

1. Consensus of all participants / 参加者全員の合意
2. Main branch creator's judgment / メインブランチ作成者の判断
3. Author-designated co-maintainer / 作者が指定した代理人
4. Inheritance policy rules / 継承ポリシーに従う
5. Mainless mode / 本流なし（mainless）モード

### 8.2 Absent-Author Handling (Copyleft Release)

Determining author survival is technically impossible, and copyright law risks freezing works indefinitely. To avoid cultural stagnation, FORQUE adopts the following:

作者の生存判定は技術的に不可能であり、著作権法により作品が凍結する危険がある。文化的停滞を避けるためFORQUEは以下を採用する。

- If the author has not logged in for an author-defined period, **main-branch policy authority only** is released.
- Copyright is retained by the author.
- Period is freely configurable by the author (1 year to indefinite).
- FORQUE recommends **5 years** as a reference value; this is not enforced.

```json
"main-branch-policy": {
  "allow-claim-main": false,
  "conditions-for-main-claim": ["author-approval"],
  "co-maintainer": null,
  "mainless": false,
  "copyleft-release-after": "author-defined"
}
```

### 8.3 Multimain Mode

- Multiple mains recognized simultaneously.
- Supports multiverse-style creation.
- Each community can hold its own "main."

---

## 9. Inheritance Policy

The inheritance policy defines how works may be derived and reused. Like Creative Commons, it is opt-in, maximizing cultural freedom.

継承ポリシーは、作品がどのように派生・再利用されるかを定義する。Creative Commonsのように選択制とし、文化的自由度を最大化する。

### 9.1 Principles

- Derivation is culturally natural and permitted by default.
- Credit is a cultural obligation.
- Commercial use is the author's choice.
- Derivative policies may only be **loosened** downstream, never tightened.
- Lineage is always recorded.
- AI-generated portions are handled via self-declaration + metadata.

### 9.2 Fork Rights & Metadata

- When forking, the original branch's rights conditions are referenced and inherited.
- Forks may hold their own CC settings and rights metadata.
- If source data or AI-generated components carry potential license violations, the fork is automatically restricted from commercial use.

### 9.3 Metadata Update & History

- Metadata requiring post-hoc additions or corrections can be updated by the main branch creator or designated maintainer.
- Rights history tracked securely via signed transactions.
- Users are notified when temporary display of stale information occurs due to node sync timing differences.

### 9.4 Branch Type Display

Icons are used for "main," "multimain," and "isolated branch" to aid intuitive lineage comprehension.

「本流」「マルチ本流」「孤立ブランチ」をアイコンで表示し、系譜の直感的把握を支援する。

---

## 10. Technical Vocabulary (FORQUE Format)

FORQUE adopts neutral technical vocabulary only — no world-building terminology — for clarity with developers.

FORQUEは世界観語彙を含まず、技術者に伝わりやすい中立語彙のみを採用する。

| Term | Definition |
|:---|:---|
| `main-branch-policy` | Rules governing which branch is recognized as the main line |
| `inheritance-policy` | Rules defining how works may be derived, remixed, and reused |
| `fork` | Creating a derivative work from an existing branch |
| `merge` | Integrating a forked branch back into another branch |
| `lineage` | The full recorded chain of derivation from origin to present |
| `origin` | The first work in a lineage chain |
| `process-log` | Record of the creative process within a branch |
| `co-maintainer` | A designated person authorized to act on behalf of an absent author |
| `mainless` | A mode in which no branch is designated as main |
| `multimain` | A mode allowing multiple branches to simultaneously be recognized as main |

---

## 11. Future-Proof Modes

FORQUE formally maintains the following modes in its specification to adapt to future creative culture.

FORQUEは未来の創作文化に対応するため、以下のモードを正式に規格として保持する。

### 11.1 Mainless

- No main branch defined.
- Legitimacy is not handled centrally.
- Adapts to a future where all forks are equal.

### 11.2 Multimain

- Multiple mains recognized simultaneously.
- Supports multiverse-style creation.

### 11.3 Co-maintainer

- Prevents cultural stagnation during author absence.
- Mirrors OSS inheritance structures.

---

## 12. AI-Generated Content Handling

AI-generated portions are tracked using the following metadata:

```json
"generated-by": "human" | "ai" | "hybrid",
"model": "optional-model-name",
"confidence": "optional-confidence-score"
```

- Designed to accommodate a future where AI authors main branches.
- Self-declaration is the baseline; forced automated detection is not performed.
- AI involvement is recorded in lineage for transparency.

---

## 13. Communication Controls

- Template-based responses are used to discourage comment flooding.
- Specific users can be muted as needed.

---

## 14. Legal & Cultural Change Adaptation

- The possibility that future legal changes or cultural reinterpretations may supersede the main branch creator's intent is explicitly stated in terms of service.
- Post-hoc metadata addition and updates for later-noticed branches are supported.
