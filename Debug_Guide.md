This is a (WIP) list of frequent problems you may encounter while building, or using phobri and how to deal with them.

## Sticky stick

![](img/dbg/stickystick.gif)

If your stick is behaving like the vertical axis in this video, it's probably that there's sticky flux that's gotten into the assembly. Isopropyl alcohol can remove it, but the flux is usually too deep in the assembly for you to get at it directly, so you might want to just dunk the PCB in a bath of it.

## Controller not showing up on config tool after flashing

First check if it still shows up as a USB drive (RPI-RP2) like it did when you flashed it. Most likely it will, otherwise it would be a more serious problem that would have resulted in you being unable to flash it in the first place. This behavior of being able to flash but unable to fully boot is very common because the RP2040 goes to the flash bootloader as a fallback whenever something goes wrong: loading the program from the flash times out, the clock is not stable, etc. These things are often the result of the voltage being wrong because of some short or something like this. 

Here are some things you can test:

* Try it again with the stickboard unplugged. If it goes away, you know your problem is localized to either the flex cable (which can certainly break), or the stickboard itself. 
* If you have a multimeter, put it in continuity/ohmmeter mode and check for any obvious shorts between ground and power. The controller should not be on for this. If that's fine put the power back and check that the voltage is fine. Should be around 3 volts. Testpoints on each board are labeled below.

![](https://github.com/ZenithControlLabs/Phobri64_HW/blob/main/extras/mb_testpoints.png?raw=true)

![](https://github.com/ZenithControlLabs/Phobri64_HW/blob/main/extras/testpoints.png?raw=true)

* This is probably obvious, but if you notice the board getting hot anywhere, or certainly any smells or noises coming from it whatsoever, unplug it immediately. You definitely have a short somewhere in that case. You may or may not have caught it with the ohmmeter above, it's not always easily detectable that way. If it's manifesting as the board heating up, you can either take a thermal camera while it's running and look at the problem, or you can even put a bit of isopropyl alcohol on the board and see where it evaporates.

* Check the state of the BOOTSEL line when the controller is powered on. Testpoints are labeled BOOT, near the top of the PCB next to the button. It should be at the same as the 3.3V line. Otherwise, it's registering as though that button is held, and so it's forcing itself into boot mode every time.

Fixes will vary depending on the problem, but hopefully if it's a short resulting from soldering it can be fixed that way. Feel free to [post on the discord](https://discord.gg/MeemsWKHKk) for help.