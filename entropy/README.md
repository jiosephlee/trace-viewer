# Token entropy: current three-run Gold traces

[Open the viewer](https://jiosephlee.github.io/trace-viewer/entropy/?repetition=all).

All 48 saved BBB/Oral traces are included: four queries per task, two evidence
configurations, and three original generation repetitions per configuration.
The shared input remains visible while each generation repetition has its own
reasoning, answer, entropy overlay, and token probabilities.

Each saved trace was scored in three new full-prefill passes using eight A100
GPUs with tensor parallelism (TP8), at analysis temperature 1. Hover, focus, or
tap a token to see its probability mean and sample standard deviation (SD,
n=3 scoring passes, ddof=1). Tooltips show probabilities only, with SD in
percentage points (pp). Entropy means drive the heatmap; entropy means and SDs
in nats are available in the companion files and summary. These are
repeat-variation statistics, not confidence intervals or measures of prediction
correctness.

The four reference alternatives retain the fixed token IDs from the original
one-pass viewer. They are ordered by their new mean probability; they are not
claimed to be the four highest-mean tokens across the full vocabulary.
Percentages are not renormalized over the displayed candidates. Leading
whitespace and newlines are shown as quoted token text.

These are provisional local checkpoint estimates. The A100 decoder previously
failed repeatability. At three checked positions, full-prefill and
immediate-prefix means differed by up to 11.25 percentage points. The displayed
SD describes repeat variation within full-prefill scoring; agreement between
execution paths and backend correctness are not established. Historical
provider logits are not recovered.

Source prompts, outputs, evidence, and all original one-pass score sidecars
remain unchanged. The displayed statistics come from separate companion files.
Coverage: 469,350 reasoning tokens, 38,866 answer tokens, and 96 structural
delimiters, with five fixed candidates for all 508,312 output positions. The
shared color scale uses the pooled 99th percentile of mean reasoning/answer
entropy. Optional top-20% highlighting ranks mean entropy within each trace's
reasoning or answer section.

- [Entropy summary TSV](summary.tsv)
- [Entropy distribution](entropy_distribution.svg)
- [Statistics manifest](entropy_statistics_manifest.json)
- [Original one-pass source manifest](entropy_manifest.json)
- [Original three-run viewer](../)

Method: [token entropy definition, Section 2.1](https://arxiv.org/html/2506.01939v2#S2.SS1).
