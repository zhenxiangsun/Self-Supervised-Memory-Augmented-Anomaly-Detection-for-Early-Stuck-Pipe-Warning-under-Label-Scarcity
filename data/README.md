# Data Description

This folder contains the five TSPP sequences used in the experiments associated
with the E-AMSL study.

## Sequence Roles

| Sequence | Well | Experimental role | Number of causal windows |
| TSPP1    | F-12 | Development       | 20,872 |
| TSPP2    | F-4 | Independent test   | 8,375 |
| TSPP3    | F-9A | Independent test  | 12,409 |
| TSPP4    | F-1 | Development        | 10,505 |
| TSPP5    | F-12 | Development       | 11,453 |

The three development sequences contain 42,830 causal windows in total.

The two independent test sequences contain 20,784 causal windows in total.

Overall, 63,614 causal windows are used in the experimental protocol.

## Window Construction

- Sampling interval: 4 s
- Window length: 125 samples
- Sliding-window stride: 1 sample
- Historical duration per window: 500 s
- Number of model input variables: 9

All input windows are strictly causal.

For the development data, chronological partitioning is performed before
sliding-window construction so that no window crosses the boundaries between
development subsets.

## Development and Test Allocation

Development sequences:

- TSPP1
- TSPP4
- TSPP5

Independent test sequences:

- TSPP2
- TSPP3

The stuck-pipe annotations associated with the independent test sequences are
used only for final evaluation and are not used for model training,
hyperparameter optimization, or threshold calibration.

## Data Source

The drilling measurements originate from the publicly available Volve field
dataset released by Equinor.

Users of this repository should also consult the original Volve dataset terms
and documentation when using or redistributing the underlying drilling data.
