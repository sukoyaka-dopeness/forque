# Future Challenges: forque
<!-- last updated: 2026-03-09 / session: 8 / maintained by: sukoyaka-dopeness -->

Unresolved problems and long-term challenges for the forque platform.
Items are tracked here to acknowledge their existence — not all require resolution before launch.

未解決問題と長期的課題の一覧。存在を認識し記録することが目的であり、すべてをリリース前に解決する必要はない。

---

## Priority Overview / 優先度まとめ（2026-03現在）

| Priority | Phase | Items |
|:---|:---|:---|
| High | MVP (required) | Evaluation-based alternative for analog works, voting + review instead of auto-detection, no-monetization mode, psychological safety UI |
| Medium | Post-MVP / v1.0 | FORQUE format draft, moderator system, disconnect operation design |
| Low | v2.0+ | Full distributed storage, Fediverse federation, global multilingual support |

---

## 1. Content Authenticity & Storage

### 1.1 Metadata Verification Load
C2PA and similar verification require access to original files, but storing all files server-side is costly and privacy-invasive.

- MVP: Temporary upload at verification time, or hash-only storage + external API verification.
- Future: Zero platform burden via distributed storage reference (IPFS / Arweave).

### 1.2 Proving Authenticity of Analog Works
How to guarantee digital "authenticity of creation" for analog works that have been printed and re-scanned.

- MVP: Supplemented by invisible integrity score from other users. C2PA prioritized for digitally born works.
- Future: Procedure guide for analog-to-digital conversion + trust badge via score accumulation.

---

## 2. Similarity Detection & Rights Protection

### 2.1 Auto-Detection Algorithm
Can intentional modifications (noise injection, paraphrasing) to evade detection be automatically identified at sufficient accuracy?

- MVP: No automated judgment (high false-positive risk). User voting ("homage" / "suspicious" flags) + moderator review.
- Future: AI-assisted detection (CLIP similarity etc.) + weighted voting for improved accuracy.

### 2.2 Defining the Homage / Infringement Boundary
How does the system define the line between homage and infringement?

- Future: Community guidelines + RFC-ization of voting criteria.

---

## 3. Psychological Safety UI

### 3.1 Declination & Fade-out Automation
Will guilt-minimizing templates convey refusal correctly without making the other party feel bad?

- MVP: Multiple default templates + preview function.
- Future: A/B testing for optimal tone. Optional AI tone-check.

### 3.2 Handling Inactivity & Broken Links
Preventing inactivity badges or score drops from inhibiting creative activity.

- MVP: Inactivity treated as "positive archive"; penalties kept light.

### 3.3 Creator Psychology: "Someone Is Doing Whatever They Want With My Work"
forque is built on derivation culture, but many contemporary creators are not accustomed to this. Participants must genuinely understand and consent to the premise that their work may be forked.

The LP and onboarding must explicitly communicate: "This is a service for people who embrace derivation culture." Only those who consent should enter.

forqueは派生文化を前提としているが、現代の創作者の多くはこれに慣れていない。参加者が「自分の作品が派生されうる」という前提を理解・同意した上で入ってくる設計が必要。LPとオンボーディングでの明示設計を要検討。

- Future: LP copy and onboarding flow design that makes the derivation premise explicit.

### 3.4 "声をかける" Feature: Preventing Unsolicited Story Proposals
The "声をかける" (comment / reach out) feature cannot completely prevent users from sending unsolicited story proposals. Mitigation through design:

- Display a guide in the input form: "This field is for impressions, critique, or collaboration requests. To propose a story direction, please use 'fork this branch' instead."
- Route the impulse to propose expansions into the fork flow rather than comments.

「声をかける」フォームへの事前ガイド表示で、展開案送信を派生フローに誘導する。完全な防止は不可能だが抑制はできる。

---

## 4. Rights, Law & Commercial Use

### 4.1 Revenue Distribution Transparency & Legal Compliance
How much of contribution-based distribution can be automated, and where does human agreement take over?

- MVP: No-monetization mode (distribution off). Commercial declaration type only.
- Future: Commercial declaration trigger + retroactive distribution (monthly/quarterly graph preservation). Lawyer-reviewed terms required.

### 4.2 Smart Contract Applicability
Platform responsibility scope when auto-execution is involved.

- Future: Open definition within FORQUE format + explicit disclaimer.

### 4.3 Legal & Cultural Change Adaptation
Future legal reforms or shifts in cultural interpretation may supersede the main branch creator's original intent.

- Terms of service must explicitly state that future legal changes may take precedence.
- Need a mechanism to track and reflect the impact of legal regulations and international treaties.
- Support for post-hoc metadata addition and updates for later-noticed branches.

法改正や文化的解釈の変化が既存の権利条件に影響する可能性を規約に明記する。

### 4.4 Main Branch Dependency on Current Copyright Law
The "main branch" concept exists not because forque philosophically requires it, but because current copyright law and commercial practice (e.g. animation adaptations, licensing agreements) require a designated "official line." The transition to mainless is partly contingent on evolution of legal frameworks.

「本流」はforqueの哲学的中核ではなく、現代の著作権法・商慣習がそれを必要としているために暫定的に存在している。mainlessへの移行は、法制度・商慣習の変化を待つ側面がある。

### 4.5 Commercial Use of Unauthorized Derivatives
If a branch created without an accepted connection request (an independent branch) is commercially exploited (e.g. animated), disputes are likely. forque's position:

> "Commercial use in a state where a connection request has been declined is outside forque's protection. Please follow applicable copyright law."

This disclaimer must be included in terms of service.

つながり申請が断られた状態での商用利用はforqueの保護範囲外。規約への免責明記が必要。

**Automatic "commercial use prohibited" for declined branches:**
Technically feasible, but two problems arise:

1. Indistinguishability: forque cannot distinguish between "applied
   and was declined" and "forked without applying" — both result in
   the same independent branch state.

2. Philosophical tension: auto-restricting all independent branches
   conflicts with forque's default position that derivation is
   culturally natural and permitted.

Proposed middle ground: if the original author sets
"commercial use: requires accepted connection request" in their
inheritance policy, branches without an accepted request are
automatically restricted from commercial use. The default remains
unrestricted (derivation-culture philosophy preserved).

派生元作者が継承ポリシーで「商用利用：つながり申請受理が必要」と設定した場合のみ、
受理されていないブランチを自動的に商用不可とする。
デフォルトは制限なし（派生文化の哲学を守る）。

When disputes arise over whether an independent branch's commercial
use is legitimate (homage vs. plagiarism), the jury system serves
as the resolution mechanism. See deferred task: jury system (v1.0+).

独立ブランチの商用利用の正当性（オマージュかパクリか）を巡る紛争は、
陪審制が解決機構となる。

### 4.6 Story Proposal Rights Problem
When a user sends a story expansion proposal via "声をかける," the proposal may carry automatic copyright (Berne Convention). Even if terms of service state "proposals are treated as idea provision," this has limited legal enforceability.

Possible directions:
- Separate "idea provision" and "work submission" as distinct submission types
- Require CC0 (public domain equivalent) license for proposals
- Route all expansion proposals into the fork flow, eliminating the need for a dedicated proposal UI

「声をかける」で送られた展開案には自動的に著作権が発生しうる（ベルヌ条約）。規約での放棄には限界があり、構造的解決（すべての展開案をフォークフローへ）が有力。

### 4.7 International Copyright Law Compatibility
Copyright law varies significantly by country. FORQUE format must not be structurally dependent on any single legal framework.

- MVP: Retain copyright while releasing only main-branch policy authority.
- Future: Time-based release independent of specific legal systems. Legal judgment placed outside the format specification.

---

## 5. Governance & Cultural Evolution

### 5.1 Absent Author Problem & Cultural Stagnation Prevention
Determining author survival is technically impossible, and international copyright law is not unified. Projects can freeze when authors become unavailable.

- Direction: Time-based copyleft release. Author-configurable period (1 year to indefinite). forque recommends 5 years as reference value (not enforced).

### 5.2 Main Branch Concept as Transitional
"Main branch" and "official" are demanded by contemporary culture, but "mainless" may become the natural default in future creative culture.

- Direction: Priority order for main determination → mainless as formal alternative → multimain mode support.

### 5.3 Multimain Mode Implementation
In multiverse-style creation, multiple mains coexisting is natural. How to visualize, branch, and merge lineage?

- Direction: Treat lineage as "forest" rather than tree structure. Explore UI for naturally displaying multiple mains.

### 5.4 Co-maintainer System
Scope of authority, succession, addition, removal, and fallback when co-maintainer is also absent.

- Direction: Author can designate multiple co-maintainers. Fallback to inheritance policy when none available.

### 5.5 "緩和のみ許可" Principle for Derivative Policies
If derivatives can impose stricter conditions than the origin, culture closes. Inheritance policy permits loosening only, never tightening.

- Direction: Structure similar to CC ShareAlike. Automatic consistency check included in format spec.

### 5.6 AI Authorship Future
In a future where AI is deeply involved in creation, AI authoring a main branch becomes plausible.

- Direction: Transparency via `generated-by` metadata. Self-declaration baseline. AI involvement recorded in lineage. AI main not prohibited.

### 5.7 Limits of Automating Legitimacy
Legitimacy is a value judgment; full automation is impossible. How to support community consensus formation?

- Direction: Automation limited to "condition checking." Legitimacy judgment remains with humans or community. Transparency + logs + policy consistency checks formalized in spec.

### 5.8 FORQUE as Cultural Infrastructure
FORQUE is not merely a technical spec — it has potential to become the foundation of creative culture.

- Direction: Neutral technical vocabulary (world-building terms stay in UI only). PHILOSOPHY.md kept independent for philosophical inheritance. Formalize anti-conflict mechanisms in spec.

---

## 6. UI & Design Open Questions

### 6.1 Node Unit Naming
What is the user-facing name for a single work/node in the lineage tree? "作品"? "枝"? "ノード"? Not yet decided. Affects "声をかける" target language and all related UI copy.

系譜ツリー上の単一の作品・ノードのUI呼称が未決定。「声をかける」の対象表現など関連するUI文言全体に影響する。

### 6.2 "声をかける" Target Scope
Is "声をかける" addressed to a branch (work) or to an author (person)? Current direction: branch unit ("この枝に声をかける") — aligning with forque's philosophy of addressing the work, not the person.

「声をかける」は枝（作品）に向けるか、作者（人）に向けるか。現時点の方向性：枝単位（この枝に声をかける）。

### 6.3 "推し枝指定" Confirmation Dialog Design
Designating an author's pick has legal implications (commercial use reference line). The UI must communicate this weight without causing excessive hesitation.

Draft copy:
> この枝を推しますか？
> 「推し枝」に指定すると、この枝が商用利用・二次展開の際の公式ラインとして参照されます。
> 後から変更することもできます。
> [やめておく]　[この枝を推す]

推し枝指定は法的に重い操作（商用利用の参照ライン）。重さを伝えつつビビらせない確認ダイアログの設計が必要。

### 6.4 "Author's Pick" English Translation
"推し枝" carries a nuance of ongoing endorsement (推す = to back/support actively) that is difficult to translate. Current provisional: `author's pick`. The translation gap itself is a design issue worth tracking.

「推す」の継続的・能動的なニュアンスは英語に完全には翻訳できていない。`author's pick`は暫定。

### 6.5 Incorporation Request UI Copy
"取り込み依頼" / "Incorporation Request" is opaque to non-technical users. Current direction: use contextual natural language in UI ("この枝を、〇〇の森に加えてもらう" / "つながりを申請する") rather than displaying the technical term directly. Tutorial ("Forest Voices" demo) is the primary explanation vehicle.

非技術者には伝わりにくい。UIには技術用語を出さず、文脈に応じた自然な表現を使う方向。チュートリアルデモが主要な説明手段。

### 6.6 "壁打ち" / Wall-bouncing UI Display
"壁打ち" as a term may not be intuitive even to Japanese speakers in all contexts. Candidate UI labels: 「コメントする」(neutral) / 「声をかける」(warmer, forque-aligned). Final decision pending LP and world-building consistency review.

「壁打ち」の語のUI表示は未決定。「コメントする」または「声をかける」が候補。

---

## 7. Distributed & Federated Architecture

### 7.1 Data Migration & Compatibility
Smooth migration path: Web MVP → Federated servers.

- MVP: JSON export. User-driven import.
- Future: ActivityPub extension or proprietary protocol for cross-server lineage sync.

### 7.2 Privacy & Distributed Trust
Avoiding central DB dependency while enabling user-controlled data management.

- MVP: Minimum data storage + open-source for self-hosting.

### 7.3 Cold Start Problem
Matching requires users. How to reach critical mass?

- MVP: Community partnership + invite-only start.

---

## 8. Credit & Attribution

### 8.1 Authorship Credit in Commercial Secondary Use
When a work with a rich lineage is commercially exploited (e.g. animated), who gets credited?

Current direction: "メインブランチ名＋プロジェクト" as standard external credit form (e.g. "森の声プロジェクト"). All contributors recorded internally in lineage. Main branch creator can change the external name; change history preserved in lineage.

商用二次利用（アニメ化等）時のクレジット標準形：「メインブランチ名＋プロジェクト」。内部ではlineageに全貢献者を記録。外部名義はメインブランチ作者が変更可能だが変更履歴はlineageに残す。

### 8.2 Contribution Weight Measurement
In automatic revenue distribution, how is each contributor's "weight" measured? Depth in lineage? Volume of contributed content? Human agreement required beyond a threshold?

- Future: To be defined in FORQUE format specification.

---

## 9. Metadata Management

### 9.1 Fork Metadata Inheritance Reliability
Ensuring rights conditions and usage terms are reliably inherited at fork creation time.

### 9.2 Complexity from Scale
Large-scale forks, multimain configurations, and isolated branches will significantly complicate metadata management.

### 9.3 Node Sync & Stale Data
Users must be notified when temporary display of stale information occurs due to node sync timing differences.
