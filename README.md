# CNN-DDQN: Candlestick Image Trading Agent

A Double Deep Q-Network trained on candlestick chart images for S&P 500 trading — an attempted replication of [Brim & Flann (2022), *Deep reinforcement learning stock market trading, utilizing a CNN with candlestick images*, PLOS ONE 17(2): e0263181](https://doi.org/10.1371/journal.pone.0263181).

## Approach
Following the paper's specification:
- Daily OHLC prices (2013–2019 training) rendered as 84×84 grayscale candlestick images
- DDQN with two CNNs (target / evaluation), 128–256–512 convolutional layers
- Evaluation network weights synced from the target network every 100 steps
- 3-action space: long, short, or no position

## Outcome
The agent did not reproduce the paper's reported performance. The original work reports 13.2% average geometric returns against the S&P 500's -4% over the 2020 test period, but omits key implementation details — hyperparameters in particular — needed to reproduce that result.

These reproducibility gaps are not unique to this attempt: they are independently documented in Tuininga, F. S. (2023), *Uncovering the Potential of Deep Learning in Algorithmic Trading: A Critique of "Deep reinforcement learning stock market trading, utilizing a CNN with candlestick images"*, BSc thesis, University of Twente.

Development stopped at this point. With the source specification incomplete, further tuning could not distinguish an implementation error from an unreproducible result — any improvement would have been unfalsifiable.

## Notes
Training checkpoints (~8 GB) are not tracked in this repository.
