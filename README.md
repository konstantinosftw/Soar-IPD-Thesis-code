# Iterated Prisoner's Dilemma in SOAR Cognitive Architecture

*Having prior knowledge of Soar syntax will make your life awfully easier.*

## Introduction

A Reinforcement Learning Soar agent that plays against an environment of 12 opponent strategies. The strategies are included in the same file and are the following:

1. Cooperate
2. Defect
3. Interchange
4. Random
5. Tit for Tat (TFT)
6. Suspicious Tit for Tat (SuspTFT)
7. Tit for 2 Tats (TF2T)
8. Grofman
9. Grudger
10. Pavlov (win-stay, lose-switch)
11. Extort (ZD_Extort2)
12. Joss

More information about the strategies can be found in the [Axelrod Python library documentation](https://axelrod.readthedocs.io/en/stable/reference/overview_of_strategies.html)

## Prepare to Run

1. Download Soar Suite [here](https://soar.eecs.umich.edu/Downloads). (cerrent version is 9.6.0)
2. Pull or DL the repository anywhere on your computer
3. Launch SoarJavaDebugger.bat from the Suite folder.
4. Run the following 3 commands in the debugger's command line
```
rl --set learning on 
indifferent-selection –-epsilon-greedy
indifferent-selection --epsilon 0.3
```
5. Reduce the epsilon as training progresses to refine results. Do so by using the last command.

## Run the reinforcment larning Agent

1. Open `ipd-rl-look-back.soar` in an editor
2. Uncomment the strategy you want to play against; RANDOM is the default uncommented one. *Warning*: You can have only ONE opponent strategy uncommented at any given time, otherwise the opponent will run in an infinite ellaboration error.