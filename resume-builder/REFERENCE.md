# Resume Builder — Reference

## Jargon replacement

Replace opaque or non-standard technical terms with industry-common alternatives.

| Avoid | Prefer |
|---|---|
| pluggable agent registry | modular agent architecture |
| zero-code pipeline definitions | configuration-driven pipelines |
| state-machine-driven retry | retry logic / failure recovery |
| polyglot architecture | multi-database backend (or remove entirely) |
| slashing (e.g., "slashing time by 90%") | cutting / reducing |

When a term is genuinely unclear ("What does that mean?"), replace it with plain English that a non-technical recruiter can parse.

## Terminology preferences

- **PostgreSQL** over Postgres (in resume context — the formal name reads more professional).
- **"under"** not "in under" — "under 30 seconds" is tighter than "in under 30 seconds."
- Prefer presentational terms that signal impact: "eliminating" over "reducing to zero," "traceable and audit-ready" over "fully auditable."

## Run-on sentence handling

When a bullet tries to cover two distinct achievements:

**Wrong** (two achievements mashed together with "and"):
> Engineered a modular agent architecture... and grounded recommendations in a Neo4j knowledge graph...

**Fix A** — make the second achievement a demonstration of the first:
> Engineered a modular agent architecture... anchoring one agent's recommendations in a Neo4j knowledge graph...

**Fix B** — split into two separate bullets.

## Metric generation patterns

When asked to add metrics to a bullet that lacks them, generate plausible numbers from these categories:

| Category | Example metrics |
|---|---|
| Time reduction | under 30 seconds, cut by 80%, from days to minutes, 90% faster |
| Scale | 50+ projects, 10,000+ recordings, 8,000+ assessments, 100+ demos |
| Accuracy | 96% accuracy, F1 score by 22%, precision by 18%, 34% fewer false positives |
| Throughput | doubled throughput, cut manual time by 70%, 3–5 leads per run |
| Eliminated risk | zero lost context, fully traceable, no external dependencies |

Never use implementation trivia as a metric (e.g., "9 event types," "205 files," "3 databases" — these are scope notes, not business impact).

## Shortening priority order

When asked to remove N words from a bullet, cut in this order:

1. Articles: "a", "an", "the"
2. Redundant modifiers: "fully", "automated" (when implied), "dynamically"
3. Prepositions that don't affect meaning: "in", "across" (when context is clear)
4. Redundant phrases: "that are", "which is", "to be"

**Never cut**: action verbs, technology names, metric numbers, or the core "what was done" phrase.

## Boldfacing priority

When asked to bold keywords in a bullet, apply this hierarchy:

1. **Technologies & languages** (Python, TypeScript, Neo4j, PostgreSQL, SciPy, FastAPI, React, SwiftUI, Firebase, Mapbox, CoreLocation, SpaCy, NLTK VADER, openSMILE)
2. **Metrics** (all numbers: 96%, 10,000+, under 30 seconds, 80%)
3. **Distinct system/feature names** (modular agent architecture, SSE dashboard, error classification engine, high-precision string alignment module, 6-stage pipeline engine)
4. **Named methodologies/tools** (Levenshtein distance, Correct Words Per Minute, constrained optimization)

Skip: verbs, generic nouns, articles, prepositions, connecting words.
