# Decision Intelligence - Interface Rebuild

The UI layer of my Decision Intelligence system: a reasoning-quality workspace where every recorded decision is classified, checked for structural integrity, and projected forward in time.

This is a clean-room rebuild of the interface with representative fixture data. The production system pairs this surface with a private scoring engine; that engine is not in this repository, and nothing here computes a score. What you can inspect is the part I care most about showing: how a dense analytical product stays readable.

## What it does

- **Decision registry.** Every decision with its type (explicit, implied, deferred), status, and integrity score. Search and filter narrow the list without repainting the survivors.
- **Integrity breakdown.** Four structural checks per decision - ownership, success metrics, documented assumptions, open critical issues - each with the evidence for its pass or fail.
- **Findings.** Reasoning risks surfaced as data (severity plus a one-line justification), sorted where they matter.
- **Next steps.** Each failing check maps to a concrete action and a reason it is worth doing.
- **Counterfactuals.** The paths not taken, each with a probability-better estimate and its honest tradeoff.
- **Temporal projection.** A decision's integrity is not static: the chart projects decay across five horizons as assumptions age and owners change, with the reason at every point on hover.

## Design decisions

- **Single file, no dependencies, no build.** Consistent with everything else in this repository.
- **Fixture data as an honest boundary.** The data layer is a plain array at the top of the file. Swapping it for a live engine is one function call; publishing that engine is not the job of a portfolio.
- **Color carries meaning, not decoration.** Score tones map to good/warning/critical and always ride alongside a number or label - never color alone. Status severity chips are reserved for severity.
- **One axis, one series.** The projection chart is a single line on a fixed 0-10 scale with direct end-labeling and per-point hover reasons. Grid and axes stay recessive.

## Run it

Open `index.html` directly, or serve the folder:

```
python3 -m http.server 8000
```
