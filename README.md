# reaper-jsfx-introduction
An introduction to jsfx in reaper written while I was developing.


## The struture of jsfx files
A jsfx consists of a number of callbacks called at different times represent with `@`. The core one is `@sample` which takes part of the music waveform and modifies it. 
See [the documentation](https://www.reaper.fm/sdk/js/basiccode.php) for a discussion

# Understanding jsfx plugins
The complete source code for a number of built in plugins can be found in `.config/REAPER/Effects`. One approach to learning jsfx will be to write your own plugins with reference to these files as appropriate.

This [open source aggregation](https://github.com/JoepVanlier/JSFX) of jsfx plugins may be a good place to read code as well.
