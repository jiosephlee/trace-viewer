# Token entropy viewer (provisional)

Live page: https://jiosephlee.github.io/trace-viewer/entropy/

Sixteen saved Gold BBB/Oral traces: eight paired queries across Direct and
Direct + indirect. Original reasoning, raw answers, and evidence citations are
preserved. Hover over tokens for full-vocabulary entropy, observed-token log
probability, an alternate entropy estimate, and their absolute difference.

Entropy is calculated in nats at analysis temperature 1 using the original
DeepSeek-V4-Flash-0731 checkpoint, revision
`7872f01b1d1fe23eabc4c98b48bffcef5a386062`, and Transformers. Original generation
requests used temperature 0. Scored completion coverage: 113,873 reasoning tokens,
12,920 answer tokens, and 32 structural delimiters.

## Provisional numerical results

Strict chunk-size consistency has not passed. Every trace was scored with
1,024-token chunks and again with 512-token chunks. The same-geometry prefix
check reproduced exactly; the cross-geometry check exceeded the unchanged
0.01-nat tolerance. The difference between these settings measures sensitivity,
not an error bound.

For reasoning tokens, the median absolute difference is 0.00613 nats, the mean
is 0.04075 nats, and the maximum is 1.33926 nats. Top-20% reasoning-position overlap
between settings is 93.72%. Original provider logits and generated token IDs were
not archived; native tokenization is reconstructed. Three Baidu examples have
23 fewer reconstructed prompt tokens than the saved usage counts. Original
providers were local endpoints for 12 traces, Baidu for three, and Cohere for one.

The shared color scale is capped at the pooled 99th percentile. Optional top-20%
highlighting ranks positions separately within each trace's reasoning or answer
section using the primary geometry. These selected examples are illustrative.

- [Entropy summary TSV](summary.tsv)
- [Entropy distribution](entropy_distribution.svg)
- [Entropy manifest](entropy_manifest.json)
- [Original trace viewer](../)

Method: [token entropy definition, Section 2.1](https://arxiv.org/html/2506.01939v2#S2.SS1).
