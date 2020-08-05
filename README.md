# Surviv timing simulator
# THIS IS CURRENTLY A WORK IN PROGRESS

Here will be instructions on how to use [this project](https://garklein.github.io/surviv-timings/survivsimulator), which is a simulator of surviv.io's weapon switching and firing system. You can read about the logic behind the simulator from [Beyblade's guide](https://github.com/surviv-underclock/docs). To paraphrase:
* Your initial switch in a game is a `free switch`
* The next switch 1000ms or more after the last `free switch` will also be one
* Some guns have `deploy groups`
* On a `free switch`, you can fire after 250ms *unless* the `deploy groups` of your current weapon and the weapon that was switched from match
* If there is no `free switch`, or the `deploy groups` of your previous and current weapon match, your current weapon's `switch delay` is used
* `Free switches` do not affect melee, melee just has a (version of) `shot delay` and no `switch delay`
* Throwables are also not affected by free switches
Now, on to instructions:

# What does all these weird rectangles mean?

Current weapon delay, free switch delay and fps are self-explanatory. On the bottom, you can see 4 rows, with a bar and a square in the middle. This shows all your inputs and their consequences (this project was originally meant to be a way to practice underclock, and the bottom part was originally for seeing what was going wrong if it didn't work).  
Each row is a weapon (primary, secondary, melee, throwables), and it is ordered in the same way as surviv.io.  
The bar in the middle is current time. 
A black line that stretches from the bottom to the top of one row indicates an attack (shot/melee attack/throwable throw).  
A solid black rectangle outlined in white (doesn't reach all the way to the top or bottom of the row) is a delay (either firing or switch). While this rectangle is over the bar, it means the delay is still going on, and you can't fire. If it is a green rectangle, it means that it is the 250ms `free switch` delay.  
The grey background behind the delays shows where you've held your mouse down, regardless if it was on a delay (and didn't shoot) or not.

# Keybinding

You can keybind in this project. To do so, open the console (ctrl-shift-i, and navigage to the "console" tab). Keybinding follows the format `name of bind = name of key/mouse button`. Here is a list of keybinds:
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

Time for some examples: 
* If you wanted to set primary to spacebar, you would type `primary.bind = " "`
* If you wanted to set "equip other gun" to right click, you would type `equipOtherGun = "rightMouse"`

To view your current keybinds, type `keybinds()`.

# Setting weapon stats

The default weapons are an M870 (in primary slot), and an AK-47 (in secondary slot). If you wanted to, for example, practice Mosin-Nagant + Desert Eagle desync, you would need different stats. 

Weapon stats are also done in the console, and follow the format `weapon.property = value`.

Weapons are objects. I have already touched on this a bit in keybinding. The object names are `primary`, `secondary`, `melee`, and `throwable`. Here is a list of gun properties:
* `attackDelay`. A number. This is the cooldown after firing.
* `switchDelay`. A number. This is the default cooldown after switching.
* `automatic`. A boolean value. This tells if the weapon is automatic or not.
* `deployGroup`. Any type will work (though in surviv.io they are all numbers). This gun's `deploy group`. To make a gun not have a `deploy group`, use `undefined` (ex. `primary.deployGroup = undefined`).

`Melee` only has the properties `attackDelay` and `automatic`, and `throwable` only has the property `automatic`. There are other properties, but you will probably screw something up if you play around with them ~~(I'm not saying you shouldn't)~~.

To view all of these current weapon stats, type `weapons()`.

# Time

The `time` variable is the total amount of milliseconds it will take for a point to go from the right side of the screen to the right. As with all other variables, you can edit it by typing in the console `variable = value`, and you can check its value by just typing its name in the console. Default for `time` is 7000.
