# PT-1210
## Digital ProTracker Turntable Software

Credits:

  * **Original Concept** - [Akira](http://kikencorp.com)
  * **Code** - [Hoffman](https://github.com/djh0ffman) & [d0pefish](https://github.com/dwhinham)
  * **Additional code on the original** StingRay (system kill/restore)
  * **Additional assistance** - [robinsonb5](https://github.com/robinsonb5) (repitching algorithm math)
  * **v1.1+ C Rewrite** - [d0pefish](https://github.com/dwhinham)
  * **Graphics** - [Akira](http://kikencorp.com)
  * **Main Testing** - [tecon](https://demozoo.org/sceners/5311/) & [Akira](http://kikencorp.com)

---

## What is it?

PT-1210 is a Protracker Digital Turntable, that is, a computer program that will let you play [Amiga Protracker](https://en.wikipedia.org/wiki/Protracker) module files (.MOD) as if you were playing with a [CDJ](https://en.wikipedia.org/wiki/CDJ)
turntable. Think of it as Traktor for the Protracker generation.
It runs on your [Commodore Amiga](https://en.wikipedia.org/wiki/Amiga) and turns it into the ultimate tool for you to play live at shows and DJ sets. Don't worry about how old your machine is! Taking optimized advantage of the 680x0 CPU, PT-1210 runs even in the most humble Amiga setups.

PT-1210 is the first player of its kind, providing the ability to re-pitch samples to match the BPM you want to play the tune at, looping effects, channel muting and step/pattern navigation.

## Why?
We are people who love the Amiga, ProTracker, DJing and live electronic music. Up until this point there was no real Amiga tool aimed at live performance that DJs and musicians could use in any kind of live setting.

It all started with Akira researching this possibility for his livesets. After [modifying a version of Protracker with Delek](http://kikencorp.com/wp-content/gimgs/9_ptlivepreview.png) to do some of what he wanted to do, he went to the English Amiga Board to [discuss the possibility of repitching a .MOD](https://web.archive.org/web/20201103201440/http%3A%2F%2Feab.abime.net%2Fshowthread.php%3Ft%3D63413), finding the solution in an ancient and forgotten version of Protracker and with some big help from robinsonb5 who figured out the math. Hoffman got interested in what Akira was trying to do, swooped in and did a [basic prototype](https://www.kikencorp.com/wp-content/uploads/2015/05/002.png) of the functionality. Thus PT-1210 was born.

The Amiga is a computer that kickstarted the career of [many](https://www.discogs.com/master/1603682-Equinox-Early-Works-93-94-The-Demos) [people](https://en.wikipedia.org/wiki/I_Created_Disco) who are music professionals today. As an affordable machine, it gave the tools to produce [studio-quality tracks](https://www.youtube.com/watch?v=57J0Ckdr9JQ) to many people that otherwise would have been left out by the much higher cost of studio equipment for making electronic music. It's very stable and responsive, and it still sounds really good.

Lots of tunes made in the 90s are still very relevant, aesthetically, today. New music is being made in Protracker format every year by both old heads and new blood, attracted to the platform by its simplicity and its connection to the roots of certain music genres like [hardcore](https://boozedrome.bandcamp.com/album/boozedrome-winter-2025) and [jungle](https://futureretrolondon.bandcamp.com/album/life-energy).

Playing Protracker modules in real time also allows you to modify them slightly at runtime, something you are not able to do with rendered audio files, introducing a lot of new options into your setup and performance. Traktor Stems? We did it first! So why not? Being an Amiga DJ is cool :)

## System Requirements

Minimum:
- A 68k-based Amiga computer ([emulators](http://winuae.net) and [FPGAs](https://github.com/mist-devel/mist-board/wiki) are 68k. PPC/next gen is not supported)
- 512KB Chip RAM, you will have very little RAM left for tunes though.
- A convenient display monitor
- Bunch of [module files](https://www.exotica.org.uk/wiki/Modland) on disk

Recommended:
- 68EC020 processor @ 14Mhz or higher
- 2MB Chip RAM
- 0.5MB Fast RAM or more
- Kickstart 2.x or higher
- Compactflash as solid state hard drive
- Compactflash/SD/MMC on PCMCIA slot
- lowlevel.library in LIBS: or ROM for CD32 pad support

## How do I use it? I want to learn more

[Read the documentation for more information](https://github.com/kikendo/PT1210/wiki).

---

## Changelog

2024-06-25
Included two fixes, one by Piru to the file requester, and I spliced 8bitbubsy's fix for the 9xx command on samples larger than 64KB. 9XX will now work but it will still only let you go through the first 64KB of the sample. At least the samples will not be muted now and this should assure compatibility with tracks made on pt2clone.


### Legacy changelog

2014-05-06
Fixed bug where scopes would crash if they hit a sample 0.
Added folder re-scan function but crashes if you switch floppy disk! (no good!)

2014-04-14
Final build before Revision, which means we are now V1.0.
Program now quits if no modules are found in the folder (used to crash)

STATIC SCROLLER ALERT!!!

Firstly massive thanks to Akira for all his hard work with ideas, testing, graphics,
PR and generally everything else. It's been enough work getting the code done let
alone managing everything else surrounding the release of this program. 

Next up massive props to Tecon, the only man I know to exploit more bugs in the PT
replay source than me! Your the reason it's so dam solid now, great bug hunting.

Lastly a big thank you to all the people who have shown an interest in this little
program. When we started this project I never knew so many people wanted to dust 
off their Amiga's and hook them up to their mixers. I hope you all enjoy playing
ProTracker mods in the mix with this tool. Now you can all stop harassing Akira
for a release!!

2013-03-21
BPM re-arranged, now shows fine as larger digits and percentage diff
Slip mode light changed
Removed one line for file selecta
Copper bug fixed in file selecta
Added Chip Ram notification on startup
Added F8 Kb file size in file selecta
Added lovely splash screen
Added some easter fun!
Added A-Z 0-9 keys for finding file

2013-03-05
Added fine tune BPM, working well but needs UI changes
Added Cue Point mover (CTRL + -)

2013-02-28 - Tecons test run!
Added blank sample so empty samples play this instead otherwise junk gets played. 
Reset some variables in PT Replay on load so E6 command doesnt freak 
Fonts now supports Underscore char
Implemented n_altperiod so ARPS and Vibrato now work with Re-Pitch
Bug where ED command caused pitch change too early now fixed

2014-02-26
Implemented new pattern loop sprites
Grid now above and below the track display
Pattern cue slip now flashes when engaged
Near end of track warning now flashes track bar
Increased BPM range again with saftey
Diabled VB Interrupt during loading as it could cause screen corruption
Fixed bug where if number of tunes is less the screen, you could scroll
past and fuck everything up!
Implemented Shift + / - which moves the size of the loop

2014-02-24
Track bar now replaced with overall track display with pattern splits

2014-02-14 - Datastorm!
Scopes now switch off when track is paused and when new track is loaded
Fixed bug where loading new tune would show the pattern from the last tune
Code split for fast mem not working, need to speak to someone about that

2013-12-17 - Code name UI!
Added graphics from Akira and complete UI re-work
Shaved loads of memory usage
Ditched all old UI code
Split code into fast mem if available

2013-09-23
Added fix for what looks like lame FT2 modules where the REPLEN isn't set
BPM detection will now default to 125 if not found on first line of the mod
Max tunes raised to 200
Fixed bug when max number of tunes is reached it wont load anything
File selector over scroll fixed (when less than a screens worth of tunes)
Added key repeat function on tempo and file selection
Quit is now done by holding ESCAPE key in file selector only
Added file sorting by name and BPM

2013-09-04
Added channel toggles on screen!
Fixed $F00 bug (god was dividing by zero!)
stopped tune from restarting after ending
Temporary fix on loading error but still buggy
Fix for VBR CIA (Again?)

2013-09-02
Fixed bug where ARP's and Vibrato wouldn't work
however don't re-pitch chip tunes, they sound shit
Added pattern move forward and back
Counter remove from display, pointless
Pattern Loop now shows start and end only when activated
Pattern Lock removed from display
Now resets all values when loading a tune
TO DO - Song cue point store

2013-05-17
Pattern display added
File selector supports more files
File selector now shows BPM! (BPM Detection on based on first line of mod)
Files no longer need to be called mod., file is now checked for M.K.

2012-09-09 
Inital beater
