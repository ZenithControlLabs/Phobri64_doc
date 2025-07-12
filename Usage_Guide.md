Everything in this guide is done through the [configuration gui](https://zenithcontrollabs.github.io/Zenith_FW/web/platforms/phobri64/). I also assume you have flashed [the latest firmware](https://github.com/ZenithControlLabs/Zenith_FW/releases/); in general the website will not work consistently if you are using older firmware than the latest.

# GUI explanation

The input display is showing 2 things: the green dot is the raw signal from the controller mapped directly to the range in the square, and the white/black dot is your calibrated output. The white/black dot is what you get when you plug your controller into the console. The green dot is only there for debugging/info purposes. You can turn it off by unchecking "debug output." 

The remaining settings will be explained in more detail below.

# Calibration

When you initially build your controller, or change your sensors/stick setup, you need to calibrate. Hit the "start calibration button". The interface will change and the input display will lock to a certain direction. It goes through each of the 8 notches and collects 8 center readings. You should simply match your stick position to the notch or center position shown on screen, and hit next. You can also undo by hitting back. Some tips:

* Don't immediately change position after hitting next as it may mess up the calibration.
* Don't push the stick into the notch harder than you normally would because that may also mess it up.
* Once again, the green dot is only your raw signal. If the green dot ends up being in the range of the calibrated (this happens more on the remapper than the Phobri), a misconception that I've seen is that the difference between the two is some kind of messed up calibration. It is not; the goal is not for these dots to align in any way. You just want the black and white dot to match the notches you have set.

# 

