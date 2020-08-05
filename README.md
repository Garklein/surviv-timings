# Surviv timing simulator
# THIS IS CURRENTLY A WORK IN PROGRESS

Here will be instructions on how to use this [project](https://garklein.github.io/surviv-timings/survivsimulator). You can read about the logic behind the simulator from [Beyblade's guide](https://github.com/surviv-underclock/docs). To paraphrase:
* Your initial switch in a game is a `free switch`
* The next switch 1000ms or more after the last `free switch` will also be one
* Some guns have `deploy groups`
* On a `free switch`, you can fire after 250ms *unless* the `deploy groups` of your current weapon and the weapon that was switched from match
* If there is no `free switch`, or the `deploy groups` of your previous and current weapon match, your current weapon's `switch delay` is used
* `Free switches` do not affect melee, melee just has a (version of) `shot delay` and no `switch delay`
* Throwables are also not affected by free switches
Now, on to instructions:

# Keybinding

You can keybind in this project. To do so, open the console (ctrl-shift-i, and navigage to the "console" tab). Keybinding follows the format `[name of bind] = [name of key/mouse button]`. Here is a list of keybinds:
* `primary.bind` 
* `secondary.bind` 
* `melee.bind` 
* `throwable.bind` 
* `attack`
* `equipOtherGun`
* `equipPreviousWeapon`
* `equipNextWeapon`

**NB: when putting in the `name of key/mouse button`, make sure to surround it with either single or double quotes**
If you want to put in a key, go to http://keycode.info/, press the button, and look at the `event.key`. For mouse buttons, these have been set by me. They are:
* `leftMouse`
* `middleMouse`
* `rightMouse`
* `scrollUp`
* `scrollDown`
