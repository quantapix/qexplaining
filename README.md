# qexplaining-public

> 50 videos = 5 topics × 10 subjects each. 10–15 min per video,
> narrated by **Janet** over animated cards/text + D3.js / Cytoscape.js
> graphics. Brand-synced with the two product sites and the two
> product app shells.

A weekly-refreshed window into the explainer arc that runs alongside
the private working repository. The output of the work is **scripts**
(plus the data behind every graphic); rendering happens in Claude
Design; voice + lipsync in a separate pipeline. This repo publishes
the master plan and the scripts as they land.

- Parent organisation: <https://github.com/quantapix>
- Engineering output: <https://quantapix.com>
- Motivational record: <https://femfas.net>

## Profile-area tags

Every subject below carries one or two of these tags. Order within a
topic is **shootable order** — earlier subjects motivate later ones.

- **P1** — rigorous proofs for LLM "reasoning"
- **P2** — legal applications (Family Court → 1st Cir. → Qnarre)
- **P3** — financial applications (analyzing + accounting → Qresev)
- **P4** — grounding competing technical-analysis approaches
- **P5** — agentic software development (Claude Code + monorepo)

---

## Status — 2026-05-17

The three production episodes (1.1 + 1.5 + 2.1) have crossed the
final pre-Resolve gate: every B-roll component is Remotion-ported,
every internal cue is anchored to the actual narration word
boundaries, and both per-episode operator runsheets are locked.
What landed this week:

- **B-roll Remotion port complete** for 1.1, 1.5, 2.1 — 16 G-slot
  compositions registered, rendering to ProRes 4444 RGBA at the
  channel-locked 1920×1080 / 30 fps. Each composition's internal
  cue frames (line type-in, recolor, glow ramp, layout crossfade,
  zoom transition, etc.) re-anchored to the production-locked
  marker CSVs — the SRT word boundaries from the actual Janet
  takes, not the script's narrative estimates.
- **9:16-only HeyGen rule** (locked 2026-05-10) confirmed across
  all three production episodes. HeyGen ships portrait; Resolve
  composites the 16:9 long-form via Pan/Tilt crop on the keyed
  9:16 source. Halves credit spend, halves render latency,
  eliminates the crown-crop class of bugs that plagued earlier
  square→16:9 attempts.
- **1.1 production-prep parity** with 1.5 + 2.1. Both per-episode
  authoring aids landed: a Fusion-keyframe notes file (S5 corner
  PIP + S6 Shorts inset band + S7 trust-boundary glow timing) and
  a 10-phase operator runsheet from pre-flight through upload. 1.1
  is the channel's first end-to-end pass; the per-episode keyframe
  choreography it locks in templates for 1.5+.
- **Channel-canonical proper-noun pronunciation pins** locked at
  the channel-wide voice config. **Qnarre = `Kuh-NAR-REE`** (three
  syllables; stressed middle; French *qnarré* ending — channel
  debut at 2.1 beat 06 with 8 narrated instances); **Qresev =
  `Kuh-RES-ev`** (three syllables; stressed middle `-RES-`;
  sibling-shape to Qnarre — channel debut at 2.1 close). Per-take
  drift inside an episode (or across two episodes) is a re-render
  trigger, not a tolerance accept: trivially-verifiable consistency
  is the channel's structural promise.
- **Per-episode `assemble.py`** drivers (DaVinci Resolve assembly
  via the in-house Python wrapper + recipe library) verified
  against the 9:16-only source path. Single take-pool import; two
  parallel timelines off the same source; per-cue Remotion MOVs
  placed at marker frames; back-to-back YouTube-master + Shorts
  render.

What's coming up:

- First end-to-end Resolve run on 1.1 — assemble.py executes; S5 +
  S6 Fusion template builds (channel-wide one-time authoring); S7
  per-episode kernel-layer breathing-glow keyframes; S8 subtitle
  generation from the A-roll; S9 loudness normalization to −14
  LUFS; S10 dual render (long + short).
- Channel music-bed selection (T1 register — minimalism / ambient
  electronic) — the loop chosen for 1.1 becomes the T1 default;
  every subsequent T1 episode must pick a different loop per the
  channel rebrand-event rule.
- Publish path validation: long-form master to the channel's
  binary CDN at `videos.quantapix.com`; YouTube upload with the
  AI-disclosure toggle and the stack disclosure in the description.
- 1.5 + 2.1 inherit the 1.1 path; 1.6+ inherit the lift-eligible
  pieces that fall out of running the chain three times.

## Working stack (locked)

- **A-roll (voice + face).** HeyGen Photo Avatar V against a single
  locked still. Voice generated via HeyGen's Design-a-Voice (channel
  voice locked retroactively to the production preview at
  <https://quantapix.com/videos/Janet-preview.mp4>). Per-beat
  generation — one MP4 + sidecar SRT per script beat per aspect —
  rather than monolithic takes; cheaper re-cuts, tighter lipsync.
- **B-roll (cards + graphics + animations).** Remotion: React-based
  programmatic video. Per-video components live alongside the
  script as JSX in a small workspace package; brand tokens
  (palette, type, easing) are read through a generated `tokens.ts`
  so no hex literals leak into renders.
- **Composition + finishing.** DaVinci Resolve Studio, scripted via
  an in-house Python wrapper plus a recipe library that turns
  per-episode `assemble.py` drivers from ~260-line scripts into
  ~80-line ones. The wrapper handles import, two-aspect timeline
  setup, A-roll comping with breath gaps, B-roll cue placement at
  marker frames, and back-to-back YouTube-master + Shorts render.
  Fusion node-tree authoring (Janet PIP corner ring + soft shadow,
  Shorts inset band, per-cue compositing) is manual at v1, guided
  by per-skill node-tree force-graph diagrams.
- **Captions + loudness.** Resolve native subtitle generation from
  the A-roll track (V4 burn-in plus sidecar SRT for upload
  metadata); Fairlight loudness normalization to −14 LUFS / −1 dBTP
  on the master bus.
- **Music + SFX.** YouTube Audio Library (free, no-attribution-
  required filter, monetization-safe); per-topic register pivot
  (T1 ambient electronic / T2 string-pad / etc.). SFX library
  selected per cue, kept sparing — no whooshes, no risers under
  Janet.

ElevenLabs is deferred — only revisited if HeyGen's voice quality
fails a real production take. So far it hasn't.

---

## Topic 1 — Why theorem provers… instead of semantic searches?

*Profile mix: **P1** dominant, P2 / P3 supporting.*

1. **The hallucination tax — where LLMs lose at high stakes.** [P1] A complaint that hinges on a § 1983 element the model "remembered wrong"; probabilistic recall vs. provable derivation; the cost curve as stakes rise.
2. **What semantic search actually does (and doesn't).** [P1, P5] Cosine similarity demoed as a magic trick that's not magic; embeddings cluster, they do not derive.
3. **The Lean4 kernel — a 10kloc oracle for proof correctness.** [P1] "Every proof is checked by a program small enough to read." Type checker as the trust boundary; one `.lean` file's type elaboration *is* the verdict.
4. **Predicates as the LLM-Lean bridge — where judgment lives.** [P1] Not the kernel, not the LLM — the markdown predicate. Three-layer split: kernel + predicate sub-agents + thin driver; each predicate has provenance + cite + question.
5. **Negative verification — when the kernel says "no, that's not RICO."** [P1, P2] The demo where the build *fails*, and that's the right answer. `sorry` on the affected theorem; other theories still elaborate.
6. **Axioms vs. evidence — why we don't trust the LLM with everything.** [P1] Which knobs are policy, which are facts, which are model output. Axioms first-class with cite + scope; LLM output never enters the trust base.
7. **Civil RICO walkthrough — predicate, sub-axioms, verdict.** [P1, P2] A single complaint reduced to a Prop. Person → predicate acts → enterprise → pattern → § 1962 elements; each one a provable lemma.
8. **Title VI walkthrough — discriminatory intent has structure.** [P1, P2] "Intent" sounds soft. It isn't. Protected class, recipient of federal funds, intentional treatment, causation; predicates render each as a question with required cites.
9. **Why this scales to financial contracts (and on to TREND / MOMENTUM).** [P1, P3] Same machinery, different axioms. TREND, MOMENTUM, OPTIONS-RISK, SECTOR, DRAWDOWN as kernel-checkable predicate vocabularies over an OHLCV trace.
10. **The cost — latency, surface area, and auditability as a feature.** [P1, P5] 30s elaboration vs. 1s vector search; predicate library upkeep; but every result ships with a witness.

---

## Topic 2 — Why narrative analysis… or Qnarre?

*Profile mix: **P2** dominant, P1 supporting, P5 cameo.*

1. **The Family Court that ate the file — a real narrative-analysis use case.** [P2] A real docket, dispositions misread, a brief built on a wrong premise. Why Qnarre's first job is procedural posture.
2. **What is a "narrative" formally? — predicates over named entities.** [P1, P2] A story is a graph plus a calendar. Actors, acts, edges, time; the narrative reduces to a Lean structure.
3. **Three-zone Qnarre — input, kernel, witness.** [P2, P5] A tour of the live `/app` island: docx/text in (left), kernel elaboration (middle), witness + fail trace (right).
4. **SSE event streaming — watching a proof elaborate live.** [P2, P5] 12 seconds of a real Lean elaboration as a stream of `{stage, msg, kind}` events; the events drive the React island's colors.
5. **From DOCX to Lean — how a complaint becomes a claim object.** [P2] A paragraph of pleading mapped to four structured predicates. Extraction → predicate match → axiom selection → theorem assembly.
6. **`RAv:p` record citations — when the appendix is the source of truth.** [P2] Every assertion carries `RAII:203`. 10-vol Combined Record Appendix; ground-truth pagination by footer stamp; never cite raw filings on appeal.
7. **Pro se on appeal — why ordinary people need this.** [P2] The asymmetry between counsel and pro se on procedural traps. Rule 4(a), tolling motions, the SO 2-99 page ceiling — encoded as predicates so a brief doesn't trip them.
8. **Counterfactual narratives — what a defense story has to deny.** [P1, P2] Every theorem has a contrapositive. Opposing counsel's narrative as a competing predicate set; Qnarre shows which axioms they would need.
9. **Federal civil RICO + § 1983 — stacking predicates.** [P1, P2] One fact pattern, two statutory frames, one kernel. Shared facts file, framework-specific axioms, theorems compose.
10. **What Qnarre never does — write your brief for you.** [P2, P5] The verifier's modesty. Predicates check, witnesses cite, but legal-strategy and prose are the lawyer's; auditability over autonomy.

---

## Topic 3 — Why result evaluations… or Qresev?

*Profile mix: **P3** dominant, P1 + P4 supporting.*

1. **Backtests lie — the survivorship + look-ahead industry.** [P3] A hand-picked equity curve that explodes when delisted names are removed. Where standard backtests cheat; what a kernel-checked evaluator must refuse.
2. **Six defined-risk strategies, hard refusal of everything else.** [P3] "We won't even compute it" for naked options. Long calls/puts, debit spreads, covered calls, protective puts — the allow-list.
3. **TREND, MOMENTUM, OPTIONS-RISK, SECTOR, DRAWDOWN — five frameworks.** [P3, P1] A portfolio is judged five ways at once. Each framework a Lean theorem set with its own predicate library.
4. **Why sector-cap claims need a kernel, not a spreadsheet.** [P3] "Max 25% Tech" — under whose definition? GICS sectors as the only acceptable referent; canonical 11 names; cap is a provable predicate.
5. **OHLCV parquet hub — the same bars feed every framework.** [P3, P4] One bar schema, ten consumers. `{ts, o, h, l, c, v, adj_c}`; vendor names die at the boundary.
6. **Live evaluator walkthrough — portfolio in, verdict + witness out.** [P3] 90 seconds of Qresev rendering verdicts on a 10-name portfolio. SSE events tagged by framework; the witness card carries the cite chain.
7. **Drawdown as a theorem — the conservative PM's mandate.** [P3] "No drawdown > 8%" is a Prop, not a wish. How the predicate phrases historical drawdown; how a conservative PM uses it as a precondition.
8. **Where the LLM lives — predicate judgments over price action.** [P1, P3] A chart segment, a question, an answer with a cite. Structured-output prompts return JSON predicate values; never free text into the kernel.
9. **Aggressive vs. conservative — same kernel, different axioms.** [P3] Three PMs disagree. The kernel doesn't. Per-PM `risk_policy.md` becomes per-PM axiom set; same theorems, different verdicts.
10. **What Qresev refuses — naked options, leverage, look-ahead.** [P3] Refusal as a feature. UI hard-refuse on disallowed legs; kernel rejection on look-ahead reads.

---

## Topic 4 — Why rigorous debates about… technical analysis?

*Profile mix: **P4** dominant, P3 + P5 supporting.*

1. **The TA bestiary — 117 indicators, mostly redundant.** [P4] Scrolling the catalog with a counter that ends at 117. The indicator-inflation problem; equivalence classes hidden in plain sight.
2. **TA-Lib as ground truth — the MACD EMA-realignment quirk.** [P4] A "wrong" MACD that's actually right. TA-Lib realigns both EMAs to slow-1; naive subtraction misses by one bar; parity is non-negotiable.
3. **DuckDB + Parquet — why columnar beats row-store for bars.** [P4, P5] "10 years of bars in 30 ms." Column-oriented IO, predicate pushdown, single-file portability.
4. **Lightweight-charts v5 — rendering 10y of bars at 60fps.** [P4] The chart that doesn't blink at zoom-out. Pinned via npm at `5.2.0`; canvas-only rendering; v5 shape.
5. **Aggregators — small-multiples, heatmaps, Three.js surfaces.** [P4] From one symbol to a sector. Tab-switching; aggregates = symbol sets; operators DuckDB-first.
6. **Three competing PMs on the same feed — where disagreements live.** [P3, P4] Same bars, three verdicts. Separation of capital + differentiated strategies; per-PM watchlists; disagreement as a signal.
7. **The defined-risk options floor — why the chart viewer enforces it too.** [P3, P4] Even the chart viewer refuses naked legs. Cross-project rule; UI never offers a leg the runtime would refuse.
8. **Alpaca IEX live + yfinance / Stooq — data sourcing tradeoffs.** [P4] The bar you saw vs. the bar you traded on. Live IEX vs. consolidated tape; backfill sources; reconciliation at the canonical schema.
9. **GICS as the only acceptable "sector" referent.** [P3, P4] "Tech" is not a sector — `Information Technology` is. 11 canonical names; shared parquet, thin readers per project.
10. **What an indicator is, formally — turning TA into testable predicates.** [P1, P4] "RSI > 70" as a Prop with a witness. Predicate libraries promote indicators from cosmetic to provable; the bridge from analyzing to accounting.

---

## Topic 5 — About Quantapix… the two-teammate practice

*Profile mix: **P5** dominant, all others as illustrations.*

1. **Two teammates, one repo — what the practice looks like.** [P5] Sole developer + expert AI assistant; narrow team, wide repo, explicit `CLAUDE.md` contracts at every boundary.
2. **The monorepo tour — twelve subprojects, one venv, one workspace.** [P5] Sixty seconds, every subproject. Cytoscape repo map; edges are shared-data hubs.
3. **Claude Code as the third teammate — agents you can fire.** [P5] A sub-agent that did one job and vanished. Per-task agents; when to spawn vs. inline; `CLAUDE.md` as the contract.
4. **`CLAUDE.md` — writing instructions for the colleague who never reads twice.** [P5] A short, harsh `CLAUDE.md` beats a long polite one. Rules over preferences; pointers over prose; the trim discipline.
5. **memsearch — how the assistant remembers what was said last Tuesday.** [P5] Cross-session recall. ONNX `bge-m3`, per-subproject collection scope, fork-isolated recall.
6. **The 5×10 video plan — made by Claude, for Claude to make.** [P5] Outlining as a structured-output task; the design hand-off; the brand-sync constraint; the very plan you're watching being executed.
7. **Verifying + Evaluating — shipping two products from one kernel.** [P1, P5] Two SSE servers, two Astro islands, one type-checked Lean. How product variation lives above a shared kernel without copy-paste.
8. **The legal arc — from pro-se filings to a verifier product.** [P2, P5] A 2025 Family-Court motion that became an axiom set in 2026. Dogfooding across Family Court → 1st Cir. → Qnarre.
9. **The financial arc — from analyzing TA to evaluating portfolios.** [P3, P5] An indicator becoming a predicate becoming a portfolio verdict. Data hub → analyzer → evaluator; each layer narrower.
10. **What Quantapix is betting on — kernels under everything.** [P1, P5] The thesis in one card. An LLM is fast and frequently right; a kernel is slow and rarely wrong; both, audited together, change which industries can adopt this.

---

## Brand sync (must hold across all 50 videos)

- Single source of truth for color / type / spacing is the
  `tokens.css` shipped to <https://quantapix.com>; D3 / Cytoscape
  themes pull palette from it, never hex literals.
- Wordmark, accent shapes, and closing-card lockup match the live
  product sites and the two `/app` shells (Qnarre, Qresev).
- Voice and pacing match the calm, declarative cadence of the site
  copy. No marketing exclamations. No rhetorical questions. No
  activist framing.
- Every closing card carries the same Quantapix wordmark + a
  one-sentence pull-quote.

## Cadence

Refreshed weekly from the private working tree. Outline edits, new
profile-area tags, and finalised scripts are committed as ordinary
diffs — the commit log is the change record.

Per-video deliverables follow a seven-file shape under
`scripts/<topic-slug>/<n.m>-<slug>/`:

- `script.md` — Janet narration with timing, on-screen card cues,
  graphic-spec slugs, pacing notes for the voice generator.
- `design.md` — Claude Design prompts for the per-video B-roll
  bundle; tokens contract; cue-state spec for each Remotion
  component.
- `resolve.md` — DaVinci Resolve project preset, V1–V4 / A1–A4
  track layout, A↔B sync strategy via marker CSV, render preset.
- `SHOOTING.md` — production-readiness gate (voice, takes,
  per-cue motion exports, marker CSV, SFX, music) plus the
  cut → review → render → publish sequence.
- `FUSION-NOTES.md` — per-episode Fusion-comp keyframe schedule
  (S5 PIP corner / S6 Shorts inset band / S7 trust-boundary
  glow), color-page guard, SFX placement, music-bed register.
- `PRODUCTION.md` — 10-phase operator runsheet from pre-flight
  through upload (markers → Resolve → assembly → channel-bed
  + SFX + music → Remotion B-roll → Fusion → finishing →
  render → cuts rescue → upload).
- `heygen-aroll.md` — per-beat HeyGen call payloads (one
  `create_video_from_avatar` payload per script beat) plus
  per-take acceptance gate.

Plus two Python siblings (`assemble.py` — wrapper-consumer driver;
`retime_markers.py` — cue-key → SRT-phrase resolver that emits
the per-episode marker CSVs from the actual take SRTs).

Three episodes currently carry the full set: 1.1, 1.5, 2.1.
Channel pilot 1.0 carries an integrated identity README and
shares the same production architecture.

## Contact

[`quantapix@gmail.com`](mailto:quantapix@gmail.com)
