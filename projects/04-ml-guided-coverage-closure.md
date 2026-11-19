# 04: ML-guided coverage closure

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🟡 Intermediate | Stage 2 · Track B | 2–3 weeks | Verilator, cocotb, cocotb-coverage, Optuna or scikit-learn |

## Goal

Show, with numbers, whether a machine-learning loop can reach functional coverage goals in fewer simulations than plain constrained-random testing.

## What you'll learn

- Defining functional coverage that actually reflects design intent
- Why some coverage bins are hard to hit with random stimulus
- Framing stimulus generation as an optimisation problem
- Running a fair experiment: baselines, seeds and repeated trials

## Prerequisites

- [Project 01](01-int8-mac-unit.md) or another block with a cocotb testbench
- Basic Python and NumPy

## Specification

- Design under test (DUT): a block with some hard-to-reach states. Good options: a FIFO with almost-full/empty flags, a small cache controller, an arbiter, or a simple ALU with flag conditions. Add one or two deliberately rare conditions.
- Coverage model: at least 20 bins, including crosses, some of which are rare under uniform random stimulus.
- Stimulus knobs: expose 4–8 parameters (e.g. operation mix, burst lengths, gap probability, value distributions).
- Baseline: constrained-random with fixed knob settings.
- ML loop: an optimiser that picks knob settings for the next batch of tests based on coverage gained so far.

## Suggested steps

1. Build the testbench and coverage model; run the random baseline and plot coverage vs. number of tests.
2. Wrap "run N tests with these knobs, return new coverage" as a Python function.
3. Use Optuna (Bayesian optimisation) to choose knobs that maximise new coverage per batch.
4. Run both approaches with at least 5 different seeds each.
5. Compare tests-to-90% and tests-to-100% coverage, with averages and spread.

## Done when

- [ ] A plot of coverage vs. simulations for the baseline and the ML loop, averaged over several seeds.
- [ ] A table with simulations needed to reach 90% and 100% coverage for each approach.
- [ ] An honest conclusion: where the ML loop helped, where it did not, and why.
- [ ] The whole experiment reruns with a single command.

## Stretch goals

- Try a reinforcement learning agent (using [Gymnasium](https://gymnasium.farama.org/)) instead of Bayesian optimisation.
- Inject a few bugs, collect failing logs and cluster them automatically with scikit-learn.
- Apply the loop to [riscv-dv](https://github.com/chipsalliance/riscv-dv) instruction stream knobs on a small RISC-V core.

## Resources

- [cocotb](https://github.com/cocotb/cocotb), [cocotb-coverage](https://github.com/mciepluc/cocotb-coverage), [Optuna](https://optuna.org/)
- *Coverage Directed Test Generation for Functional Verification using Bayesian Networks* (Fine & Ziv, DAC 2003)
- More in [resources/ml-verification.md](../resources/ml-verification.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
