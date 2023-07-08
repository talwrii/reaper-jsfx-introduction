# reaper-jsfx-introduction
An introduction to jsfx in reaper written while I was developing.


## The struture of jsfx files
A jsfx consists of a number of callbacks called at different times represent with `@`. The core one is `@sample` which takes part of the music waveform and modifies it. 
See [the documentation](https://www.reaper.fm/sdk/js/basiccode.php) for a discussion

# Understanding jsfx plugins
The complete source code for a number of built in plugins can be found in `.config/REAPER/Effects`. One approach to learning jsfx will be to write your own plugins with reference to these files as appropriate.

This [open source aggregation](https://github.com/JoepVanlier/JSFX) of jsfx plugins may be a good place to read code as well.

# Simple examples

## Pass through effect

```
desc: Do nothing
in_pin:left input
in_pin:right input
out_pin:left output
out_pin:right output

@sample
spl0=spl0
spl1=spl1
```


## Mute one of the channels so the sound runs only in one ear

```
in_pin:left input
in_pin:right input
out_pin:left output
out_pin:right output

@sample
spl0=0
```


## Record everything through the plugin to a file

See [this forum thread](https://forums.cockos.com/showthread.php?t=212561) and the [documentation](https://www.reaper.fm/sdk/js/file.php).

```
in_pin:left input
in_pin:right input
out_pin:left output
out_pin:right output

@init
recording = file_open("/tmp/file.data")

@sample
quant = floor(spl0 * 16)
file_string(handle, str) 
```

# Quick reference

An overview on jsfx

[Sections](https://www.reaper.fm/sdk/js/js.php) @init, @sample, @gfx

