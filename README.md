# qexplaining

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

## Janet narration — working stack

Decision deferred until after the outline is locked; the working
candidates are:

- **Voice cloning:** ElevenLabs (high naturalness, SSML pacing).
  Fallback: PlayHT.
- **Photo → video lipsync from a single still:** HeyGen Photo Avatar
  IV. Fallback: D-ID Studio.
- **Render pipeline:** Remotion (React-based programmatic video) for
  animated cards/text + D3 / Cytoscape composition. Fallback: Motion
  Canvas.

## Cadence

Refreshed weekly from the private working tree. Outline edits, new
profile-area tags, and finalised scripts are committed as ordinary
diffs — the commit log is the change record. Scripts land under
`scripts/<topic-slug>/<n.n>.md` as they finish; the master plan in
this README stays in sync.

## Contact

[`quantapix@gmail.com`](mailto:quantapix@gmail.com)
