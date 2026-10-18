# Table S1. Train-to-test overlap in all 11 TweetEval configurations
| Configuration | Raw rows / keys / source rows | Raw A / C / U | Trimmed rows / keys / source rows | Trimmed A / C / U |
|---|---:|---:|---:|---:|
| emoji | 0 / 0 / 0 | 0 / 0 / 0 | 41 / 41 / 182 | 9 / 24 / 8 |
| emotion | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| hate | 231 / 230 / 230 | 141 / 90 / 0 | 233 / 232 / 232 | 142 / 91 / 0 |
| irony | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| offensive | 4 / 4 / 5 | 4 / 0 / 0 | 4 / 4 / 5 | 4 / 0 / 0 |
| sentiment | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| stance abortion | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| stance atheism | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| stance climate | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| stance feminist | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |
| stance hillary | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 | 0 / 0 / 0 |

Rows count shared target/test rows; keys count distinct shared text keys; source rows count all matching training rows. A: the training label set equals the test singleton; C: the test label is absent from that set; U: the test label is present in a multi-label training set. Raw keys remove line terminators only; trimmed keys additionally strip leading/trailing whitespace. Only hate received the retraining experiments. Emoji has no raw train-to-test overlap, but trimming introduces 41 shared rows: 9 A, 24 C and 8 U. Separately, its raw validation-to-test comparison has 16 shared rows, including one U row; that is a different split pair. Complete counts for all 66 rule/split-pair/configuration comparisons are in all-split-overlap-audit.csv.
