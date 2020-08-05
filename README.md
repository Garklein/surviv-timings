# THIS IS CURRENTLY A WORK IN PROGRESS

Here will be instructions on how to use this [project](https://garklein.github.io/surviv-timings/survivsimulator). You can read about the logic behind the simulator from [Beyblade's guide](https://github.com/surviv-underclock/docs). To paraphrase:
* Your initial switch in a game is a `free switch`
* The next switch 1000ms or more after the last `free switch` will also be one
* Some guns have `deploy groups`
* On a `free switch`, you can fire after 250ms *unless* the `deploy groups` of your current weapon and the weapon that was switched from match
* If there is no `free switch`, or the `deploy groups` of your previous and current weapon match, your current weapon's `switch delay` is used
