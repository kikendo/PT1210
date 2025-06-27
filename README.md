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
