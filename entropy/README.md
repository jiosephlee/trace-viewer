# Token entropy: current three-run Gold traces

[Open the viewer](https://jiosephlee.github.io/trace-viewer/entropy/?repetition=all).

All 48 saved BBB/Oral traces are included: four queries per task, two evidence
configurations, and three recorded repetitions per configuration. The shared
input remains visible while each repetition has its own reasoning, answer,
entropy overlay, and token probabilities. Click a repetition heading for a
full-width view; return to all three without rebuilding the shared input.

Hover, focus, or tap a token to see its observed probability and the four
highest-probability other tokens. All five probabilities use the same local
full-vocabulary scoring pass at analysis temperature 1. Percentages are not
renormalized over the displayed alternatives. Leading whitespace and newlines
are shown as quoted token text. Entropy is in nats.

Local rescoring uses eight A100 GPUs with tensor parallelism (TP8).
These are provisional single-geometry local checkpoint estimates. No chunk-size
comparison was measured for this run. Historical provider logits are not
recovered. Source requests, outputs, and evidence remain unchanged.

Coverage: 469,350 reasoning tokens, 38,866 answer tokens, and 96 structural
delimiters, with four alternatives for all 508,312 output positions. The shared
color scale is capped at the pooled 99th percentile. Optional top-20%
highlighting ranks positions within each trace's reasoning or answer section.

- [Entropy summary TSV](summary.tsv)
- [Entropy distribution](entropy_distribution.svg)
- [Entropy manifest](entropy_manifest.json)
- [Original three-run viewer](../)

Method: [token entropy definition, Section 2.1](https://arxiv.org/html/2506.01939v2#S2.SS1).
