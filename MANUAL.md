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
