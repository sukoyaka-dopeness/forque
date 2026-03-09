# Discussion Summary: forque
<!-- last updated: 2026-03-09 / session: 8 / maintained by: sukoyaka-dopeness -->

A record of the multi-AI relay sessions through which forque's specifications were established.
This document lives in `docs/` as a process record, separate from the service specifications.

forqueの仕様が策定されたマルチAIリレーセッションのプロセス記録。仕様文書とは性質が異なるため `docs/` に配置。

---

## Session 1: Perplexity
**Focus:** Initial concept and safety design for amateur creator matching
**主なテーマ：** アマチュア創作者マッチングツールの構想と安全性の検討

- Cross-domain realtime matching for illustrators, musicians, novelists, etc.
- Safety concerns: preventing criminality, age issues, and dating-app drift.
- Solutions: age verification, behavioral monitoring AI, DM restrictions.
- Portfolio display via iframe embeds (pixiv / SoundCloud / BOOTH official players).
- MVP strategy: start from community, move to dedicated web app.

---

## Session 2: Gemini
**Focus:** Differentiation from existing services; elevating to essential design
**主なテーマ：** 既存サービスとの差別化・創作の本質的設計への昇華

**Technical deepening:**
- C2PA (Content Credentials) for content authenticity.
- World ID for proof of humanity.
- Git workflow reframed as creative "Lineage."

**Psychological design:**
- Work status visualization and Pace declaration.
- System-mediated declination and archiving to eliminate guilt.

**New models:**
- Family-tree circulation model: Creation → Critique → Creation.
- Automatic revenue distribution based on contribution graph.

**Service name candidates:** "Co-mit" (commit), "Forque" (fork).

**Conclusion:** Move away from authoritarian "famous creator collab" toward an honest platform that makes the process of creation at human scale visible.

---

## Session 3: Grok (xAI)
**Focus:** Specification review, MVP design, FORQUE format naming
**主なテーマ：** 仕様レビュー・MVP設計・FORQUE規格

**Specification review & clarifications:**
- Pace is a viewing-time judgment aid, not a matching score (WHY recorded).
- Revenue distribution positioned as motivation intrinsic to collaboration; MVP uses no-monetization mode.
- AI usage visualization: invisible integrity score for matching prioritization.
- C2PA analog gap addressed via evaluation-based approach.
- Declination Templates: preview + future AI tone check.
- Homage / plagiarism: user voting + moderator review.

**Legal & risk responses:**
- Automatic distribution: commercial declaration type + penalty.
- License: per-work optional selection (fixed at submission recommended; changes in loosening direction only).
- Age/gender hidden (WHY: prevent dating-app drift, preserve creative purity).
- Portfolio required + manual/AI check.
- World ID recommended (Orb badge; phone-number-limited version for regional access).

**Dating-app prevention measures:**
- DM restrictions, public timeline (Wall-bouncing) emphasis, no gender/age fields, portfolio OAuth/upload verification.

**MVP implementation:**
- Discord bot start (slash commands: /pace, /theme, /request, /decline, /help, /export-data etc.)
- Tutorial auto-send (/start or /help). Invitation link explanation + wait time notice.
- Corporate competition-style requests: future expansion.

**Future vision:**
- Fediverse-style distributed architecture (v2.0 Federated mode, cross-server lineage sync).
- Open standard for creator revenue API under the name "FORQUE."
- Discord bot open-sourced + data export/import for smooth Web migration.

**Naming update:**
- forque / Co-mit retained. FORQUE as unified brand agreed upon.

---

## Session 4: Copilot (Microsoft)
**Focus:** Ethics layer, main branch policy, inheritance policy, future-proofing
**主なテーマ：** 倫理層・本流ポリシー・継承ポリシー・未来対応設計

### Main Branch & Legitimacy

Scenarios requiring a main branch:
- When a derivative wants to claim "main" status
- When project direction needs to be determined
- For commercial use or officialization decisions
- When a community requires a standard (settings / timeline)

Priority order for main branch determination:
1. Consensus of all participants
2. Main branch creator's judgment
3. Author-designated co-maintainer
4. Inheritance policy rules
5. Mainless mode

### Absent-Author Handling

Survival determination is technically impossible; copyright law risks freezing projects for 50–70 years post-death. FORQUE's solution: "copyleft release after X years without login" — main-branch policy authority only is released, copyright is retained. Period is fully author-configurable (1 year to indefinite; 0 = immediate). FORQUE recommends 5 years as a reference value, without enforcement.

### main-branch-policy Structure

Core fields: `allow-claim-main` / `conditions-for-main-claim` / `co-maintainer` / `mainless` / `copyleft-release-after` / `multimain`

### inheritance-policy Structure

Principles: derivation permitted by default / credit is obligatory / commercial use is author's choice / downstream policies may only be loosened, never tightened / lineage always recorded / AI portions handled via self-declaration + metadata.

### Vocabulary Three-Layer Structure

| Layer | Terms |
|:---|:---|
| UI (general users) | 分岐 / 合流 / プロジェクトの流れ / 継承ポリシー / 本流の扱い |
| World-building docs | Forkforge / Forksmith / Forkline / Inheritance Note / Main-branch Ethics |
| FORQUE technical spec | fork / merge / main-branch-policy / inheritance-policy / lineage / origin / process-log / mainless / multimain / co-maintainer |

### AI Authorship Future

`generated-by` metadata (`human` / `ai` / `hybrid`). Model name and confidence optional. AI involvement recorded in lineage. AI main not prohibited.

### Future-Proof Modes

Formally retained in specification: mainless / multimain / co-maintainer.

**Copilot's overall assessment:** FORQUE could become the first serious specification for handling the creative process. It reconciles contemporary culture (legitimacy) with future culture (mainless), naturally incorporates copyleft thinking, and technically resolves the absent-author problem.

---

## Session 5: ChatGPT (OpenAI)
**Focus:** Rights management, metadata, branch display
**主なテーマ：** 権利・メタデータ管理・ブランチ表示

- At fork creation, original branch's rights conditions are referenced and inherited.
- If source data or AI-generated components carry potential license violations, the fork is automatically restricted from commercial use.
- Forks may hold their own CC settings and rights metadata.
- Post-hoc metadata additions/corrections can be made by maintainer-level users.
- Rights history tracked securely via signed transactions.
- Users notified when stale data is displayed due to node sync timing differences.
- "Main," "multimain," and "isolated branch" displayed with icons for intuitive lineage comprehension.
- Template-based responses for communication control; per-user muting available.
- Terms of service must state that future legal reforms may supersede original creator intent.

---

## Session 6: Claude (Anthropic) — First Session
**Focus:** Terminology design, Pace design, governance, MVP strategy revision
**主なテーマ：** 用語設計・Pace設計・ガバナンス・MVP戦略見直し

- Full Pace 4-tier design established: 🐢 Slow / 🐇 Steady / 🚀 Sprint / 🫘 Dormant (system-assigned only).
- Dormant: auto-assigned after 90 days without login; opacity 40% overlay; auto-released on login.
- Two-tier Pace structure: user-level default + per-project override.
- Pace UI copy finalized (selection prompt, change toast, project override message).
- Confirmed Web-first MVP; Discord bot repositioned as parallel concept-validation companion, not primary delivery.
- Observation mode introduced as solution to "no works yet" onboarding problem.
- Glossary restructured with FORQUE technical vocabulary (fork, lineage, origin, process-log, co-maintainer, mainless, multimain).
- FORQUE format defined as open, platform-agnostic technical specification.

---

## Session 7: Claude (Anthropic) — Second Session
**Focus:** LP copy, Pace icon completion, tutorial flow, repository structure
**主なテーマ：** LP文言・Paceアイコン完成・チュートリアル・リポジトリ構成

**LP copy confirmed:**
- Hero catchphrase: 「あなたの作品が、誰かの種になる。」
- SNS / developer-facing: 「派生を、誇れ。」
- Core values (3): 派生は、文化だ。/ 歩幅は、自分で決める。/ プロセスが、作品になる。
- CTA: 「先行登録する」 / 「○○人が、種を待っています。」

**Tutorial flow confirmed:**
Registration → ① Demo "Forest Voices" (skippable) → ② Pace declaration (required) → ③ Onboarding 2 questions → ④ Work registration (optional) → ⑤ Home.

**"Forest Voices" demo:** 4-panel vertical scroll story (Amara / Berk / Celia / Dani); static Carrd implementation for MVP.

**Onboarding 2 questions confirmed:** Q1 creative medium (multiple choice, 7 options) / Q2 desired involvement (multiple choice, 4 options including observation mode).

**Status free text:** 1-line optional field separate from Pace. 25 characters (JP) / 50 characters (EN, future). Hidden when empty.

**forque repository structure established:**
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
```

---

## Session 8: Claude (Anthropic) — Third Session
**Focus:** File reformatting, open design questions, future-challenges additions
**主なテーマ：** ファイル整形・設計上の未決定事項の整理・future-challenges追記

**Files reformatted:** specifications.md / glossary.md / future-challenges.md / discussion-summary.md (this file).

**Key design decisions made:**
- 孤立ブランチ → renamed to 独立ブランチ (independent, not abandoned).
- 推し枝 / Author's Pick introduced as UI term for main branch designation. "この枝を推す" as dialog action.
- Main branch dependency on current copyright law explicitly documented.
- Expansion proposals (story ideas sent via comment) routed into fork flow as structural solution.
- 壁打ち UI display: "コメントする" or "声をかける" — final decision pending.
- forque repository docs/ subfolder established for process documents.
- "メインブランチ名＋プロジェクト" proposed as standard external credit form for commercial secondary use.

**Open questions documented in future-challenges.md:**
- Node unit UI naming (未決定)
- "声をかける" target scope (branch vs. person)
- 推し枝 confirmation dialog copy (draft included)
- "Author's Pick" English translation gap
- Incorporation Request UI copy for non-technical users
- Commercial use of unauthorized independent branches + disclaimer design
- Creator psychology: explicit derivation-culture consent at LP/onboarding
