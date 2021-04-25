# Notes from my experience building a FED

The online instructions for building a FED3 are good, though a little outdated in some areas. Here are my tips
from assembling a couple (and more failed) FED3s.

# Assembly
There are three main parts to the assembly:
1. Installing the relevant Arduino code
2. Assembling the electronics
3. Incorporating the electronics into the 3D-printed housing

The [Hackaday](https://hackaday.io/project/106885/instructions) instructions cover all three, though the steps for the
housing are outdated, so we'll be using something different. I recommend following it for the 1. and 2., with a few
addenda. This also assumes that you have all of the necessary parts. The parts box _should_ have enough components in it
for at least 2 complete FEDs, with two pre-packaged goodie bags for the electronics.

## Installing the code
- When you get to the `Install relevant libraries` step, the link to `FED3Libraries.zip` is broken, but you can find the
    contents [here](./ArduinoCode/FED3libraries.zip)

## Electronics Assembly
I would read this whole section before looking at Hackaday because I recommend switching some stuff up to make it
easier. There should be a demo white FED3 board in the box that has most of the electronics attached, except for a
couple botched photointerrupters -- we don't talk about those. It's nice to double check with this that you're soldering
parts onto the correct side of the board (this bit me more than once).

- Start with the first step in Hackaday, soldering in the various header pins. However, after that I recommend jumping
    to attaching the neopixel **before** starting with the photointerrupters. For the neopixel, the soldering paste +
    heat gun + epoxy works best. The soldering paste must be refridgerated after opening so check there for an open one.
    The reason I recommend doing this first is that it's not hard to melt the photointerrupters with the heat gun if
    it's on too high (looking at you demo board...).
- I once had the screen not turn on until I replaced what turned out to be a faulty motor driver. If possible, I
    recommend testing out the components individually before soldering them on. Admittedly, I didn't do that, and
    paid the price of a wasted board.

### Pro-tips for the soldering newbie
If you, like me, have never soldered before, it's tough at first.
I found [this video](https://www.youtube.com/watch?v=37mW1i_oEpA) helpful. Also,
- I conveniently and totally on purpose bent the soldering iron tip just a bit so it's easier to hook around the
    pins while making good contact with the metal on the board.
- Once you can get some solder to melt onto the metal on the board, it naturally fills and wraps the pin nicely.
- Getting impatient for the soldering iron to heat up and starting early only leads to bad times.
- Use actual solder.

## The Housing
At this point you should be able to flash a program onto the FED and see the little mouse dance. The housing used in the
Hackaday instructions is an older model, so at this point move over to the
[GitHub Wiki](https://github.com/KravitzLabDevices/FED3/wiki/Assembling-FED3) instructions for rest of the assembly.
This mostly works just like the video except:

- The old boards that we use might not screw correctly into the housing, though it's not super necessary. I skipped the
    screws since it took a bit of force to wedge the board in to begin with.
- The 3D-printed pellet disk is a little too thick to fit the motor through. I did the probably unadvisable thing and
    used the soldering iron to melt a slightly bigger cavity in the pellet disk until the motor fit through.

# Troubleshooting
- While checking the electronics after installing the BNC, I got failure to upload the sketch with a "SAM-BA operation failed".
    The Arduino IDE popped up saying that there were updates so I updated the SAMD board to the suggested 1.6.5, which
    appeared to fix the problem.
- The mentioned screws for fixing the motor in the casing are incorrect, you need flat screws and nuts, not metal sheet screws
