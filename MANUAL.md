# PT-1210 Documentation

## Keyboard Controls
## File Selector Mode

|Key|Function|
|---|---|
| HELP        | Switch screens between load and DJ mode) |
| UP / DOWN   | Select file |
| RETURN      | Load MOD file |
| LEFT / RIGHT   | Navigate through folders / load MOD file |  	  
| A-Z / 0-9   | Navigate to first file matching that character |
| F5          | Refresh folder - Needed every time you make changes to a folder! |
| F10         | Sort list by BPM (toggles asc / desc) |
| F9          | Sort list by Filename (toggles asc / desc) |
| ESCAPE      | Quit (hold for a second) |
NOTE: Quit will not work if a tune is playing!

## DJ Mode

|Key|Function|
|---|---|
| HELP        | Switch between File Selector and DJ Mode) |
| SPACE       | Stop / Play |
| LEFT        | Soft nudge backward |
| RIGHT       | Soft nudge forward |
| SHIFT LEFT  | Hard nudge backward |
| SHIFT RIGHT | Hard nudge forward  |
| UP          | Increase BPM |
| DOWN        | Decrease BPM |
| SHIFT UP    | Fine increase BPM |
| SHIFT DOWN  | Fine decrease BPM |
| TAB         | Master tempo On/Off |
| BACKSPACE   | Pitch Lock On/Off |
| DELETE 	  | Resets tempo to original |
| \`          | Kills sound DMA |
| 1/2/3/4		  | Mute / Unmute channel |
| SHIFT 1/2/3/4	  | Solo channel |
| 5			  | Unmute all channels |
| F5          | Activate Line Loop |
| F6          | Decrease Line Loop size |
| F7          | Increase Line Loop size |
| F4          | Toggle Slip Mode On / Off |
| ESCAPE      | Quit (hold for a second) |
NOTE: Quit will not work if a tune is playing!

## Pattern / Position Functions

|Key|Function|
|---|---|
| F1          | Jump to Cue pattern |
| F2          | Jump to Cue pattern after current pattern ends |
| F3          | Set current pattern as Cue pattern |
| F10         | Pattern Loop toggle (start / stop / deactivate) |
| +           | Move forward one pattern |
| -           | Move back one pattern |
| CTRL +      | Move cue forward a pattern |
| CTRL -      | Move cue back a pattern |
| SHIFT +     | Move playhead forward (loop size determines steps) |
| SHIFT -     | Move playhead back (loop size determines steps) |


# FAQ
## The BPM is wrong!

There is no real BPM detection.
PT-1210 relies on looking at the first line of the first pattern in the module. Here, it expects to find an apropriate F command setting the BPM of the module (F command range from 20 to FF).
In the  case where no BPM is set on this step, it will assume that it is VBR timing rather than CIA and set the BPM to 125. This is OK if the tune was written to actually be 125BOPM at a tick speed of 6 or multiples thereof. In any other cases, the BPM reading will be inaccurate and you will have to use your DJ skills to figure it out. 
This does not affect the pitching ability since it is percentual.

## My module sounds weird!

The player is one of the original ProTracker replay sources so it should be
pretty dam accurate. If it sounds weird, check it in ProTracker v2.3d first
and fix it there. If it still sounds weird, provide us with an example and 
we'll take a look.

Becareful when pitching tunes up higher in BPM. As you probably know the Paula
chip can only play samples up to a certain pitch. If your module runs the
samples high in pitch and you push then tempo up too much, they wont go any
further.

## I wrote my module in FastTracker II and it crashes ProTracker!

There are a number of modules that exist where they have no REPLEN set on the
samples. Our guess is they've been written in FastTracker or similar. These
actually crash ProTracker when trying to play them. Crashing is a bad thing
so we apply a patch to the modules on load to fix this issue.

## Using different Amigas

I've tried using an A600 alongside an A1200 and found that by default they do
sound different. This is because they made the A600 badly and chopped a lot of
the high end off the sound. There is a hardware hack, ask Akira! I also noticed
that the timing was slightly different between the two Amigas which we believe
is a small difference in the two systems CIA chips. There is a fine pitch adjust
which should help with this timing issue.

## I don't understand the different looping modes?

Pattern loop: 
This will loop between a number of patterns.
F10 will cycle through different functions. The first press will store the loop start point and activate the pattern looping mode, and the second press will store the loop end point. The third press will deactivate the loop. 

Line Loop:
Line looping enables you to loop small sections of steps whithin the current pattern.
The loop start point currently quantises to a beat (assuming speed 6) so positions 0,4,8,12,16,20,24,28... etc.
Press F5 to initiate loop, then press it again to deactivate it. You can change the size in real time to mimic some stutter effects
Slip mode is enabled by default. This mode plays the line loop while continuing to keep track of the playhead as it would progress normally, so when you deactivate the loop, the track will continue playing from the position it would have had if you had never looped it. Slip Mode off means the playhead will continue from right after the loop when you deactivate the loop.


---


# Legacy Changelog

2024-04-19
It's been ten years, might as well put it all out there now :D

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
