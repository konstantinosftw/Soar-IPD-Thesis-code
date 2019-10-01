# Iterated Prisoner's Dilemma in SOAR Cognitive Architecture

*Having prior knowledge of Soar syntax will make your life awfully easier.*

## Introduction

This is the code for 4 differend PD and IPD agents, with and without reinforcment learning abilities. Specifically:

1. `pd-standalone.soar` is a PD agent that plays against an opponent (opponents are: random, always coop, always defect)
2. `pd-standalone-rl.soar` is a PD adent that uses reinforcement learning to handle the above opponents (it always results to the dominant strategy, of course)
3. `ipd-rl-look-back.soar` in an IPD agent that uses reinforcement learning to win any one of the following 12 opponents
4. `ipd-multi-opponent-runs.soar` in an IPD agent that uses reinforcement learning and plays consequtively with all the following 12 opponents, straight. That is 2400 iterations.

The rules are Axelrod's Tournament rules, 200 iterations per game.

The 12 opponent strategies are the following:

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
3. Launch `SoarJavaDebugger.bat` from the Suite folder.
4. Run the following 3 commands in the debugger's command line
```
rl --set learning on 
indifferent-selection –-epsilon-greedy
indifferent-selection --epsilon 0.3
```
5. Reduce the epsilon as training progresses to refine results. Do so by using the last command.

## Run the Agent

1. Open the agent you want to run, e.g. `ipd-rl-look-back.soar` in an editor
2. Uncomment the single strategy you want to play against; RANDOM is the default uncommented one. *Warning*: You can have only ONE opponent strategy uncommented at any given time, otherwise the opponent will run in an infinite ellaboration error. If you want to play against a chain opponents, select the `ipd-multi-opponent-runs.soar` and move to the next step.
3. After having also completed the `Prepare to Run` part, click on the `Source` button in the SoarJavaDebugger and load the selected agend.
4. Click `Initialize` follower by `Run`
5. Watch the magic happen
