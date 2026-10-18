# TweetEval hate audit numerical supplement

Supplement S1 for **Exact Text Overlap and Label Disagreement in TweetEval Hate**.
This repository contains reproducibility materials for the 17 October 2026 reporting revision.
It makes no claim of final publication, acceptance or independent replication.

## Download and verify

- [Download the numerical supplement ZIP](https://raw.githubusercontent.com/ianliuy/tweeteval-hate-audit-supplement/v2026-10-17/tweeteval-numerical-supplement-2026-10-17.zip) (27.2 MB).
- [View compact Table S1 for all 11 configurations](Table-S1.md).
- [Read the complete reproduction instructions](REPRODUCIBILITY.txt).
- [Check the archive SHA-256](SHA256SUMS.txt).

Version tag: `v2026-10-17`. Archive SHA-256:

```
c6848c69784800ef08874a1c9ec54260308adbdaad73565090ce253dfb271fe4
```

Extract the ZIP. With Python 3 and NumPy installed, run:

```
python verify_supplement.py
python recalculate_metrics.py
```

The first command checks file identities, 66 overlap comparisons, 2,000 deletion lists,
point summaries and 118 interval endpoints. By default it independently regenerates
eight bootstrap draws for each of 30 model/group combinations. To regenerate all saved
draws, use `python verify_supplement.py --bootstrap-draws 5000`.
The second command writes 32,284 unique model/condition/subset metric records.
These checks do not train models. A fresh local ZIP extraction passed these checks.

## Contents and scope

The package contains saved predictions for 4,052 model conditions, exact zero-based deletion
indices, control summaries and per-condition metrics, common test-row masks, representation
diagnostics, bootstrap draws, fixed protocols and a SHA-256 manifest. Row-ordered hashed text
keys and labels cover all 11 TweetEval configurations under raw and boundary-trimmed rules.
Only hate received the detailed retraining experiments. Methods distinguish raw test rows,
distinct text keys and retained feature-count equivalents.

The release manifest pins 74 upstream files: 66 split text/label files, seven label mappings
and a README. Raw tweet text is not redistributed here. The included retrieval script obtains
the immutable upstream files and verifies their bytes:

```
python fetch_pinned_release.py --destination ./pinned-release
```

Data source: [CardiffNLP TweetEval at the pinned commit](https://github.com/cardiffnlp/tweeteval/tree/4fbd22cd78421f05b1ecdb4fc5725bc7a7bd8f66).
Key hashes are linkage identifiers, not a privacy guarantee.

The raw 1,000 controls remove a mean of 13.399 matching training rows (range 4–24);
the 20 encoder controls average 14.30 (9–22); trimmed Word LR controls average 13.684 (5–27).
Conditional paired text-key intervals hold fitted models and realized controls fixed and
exclude training and annotation uncertainty. Neither random controls nor interval widths
establish causal identification or general model stability. The analysis is retrospective.

This supplement is a numerical recalculation package, not a self-contained model-training
environment. Preserved source analysis files document provenance; the standalone checks
operate directly on the packaged predictions, keys and masks.
