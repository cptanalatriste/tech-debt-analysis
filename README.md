# Equilibrium Analysis for Technical Debt

This model can generate the payoff values for a payoff matrix representing technical debt. After triggering the script `payoffbuilder.py`, the payoff information per strategy profile will be stored in the file `payoff_table_builder.log`.
This values can be later ported to a game solver like [Gambit](http://www.gambit-project.org/) to obtain its Nash Equilibrium.

Some relevant parameters of `payoffbuilder.py` are:

* `simulation_episodes` at line 44 controls the number of simulation iterations to execute.
The payoff values generated by the script is the average number of fixes per developer over these 
iterations.
* `sloppy_rework_factor` at line 48 controls the increased probability that a kludge commit will later generate rework, like a bug or a change request due to code review.

The payoff values are generated via simulation. Simulation-specific parameters are exposed via the script `trainingdriver.py`. 
Some of them are:

* `SCENARIO_TIME_UNITS` at line 13 is the time units simulated during an iteration.
* `SCENARIO_AVG_RESOLUTION_TIME` at line 14 is the average resolution time of a programming task.
* `SCENARIO_PROB_REWORK` at line 15 is the base probability of rework for the project.




