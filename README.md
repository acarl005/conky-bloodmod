Conky Seamod Fork
====================

Seamod theme was built by [SeaJey](https://www.deviantart.com/seajey/art/Conky-Seamod-v0-1-283461046),
updated by [maxiwell](https://github.com/maxiwell/conky-seamod),
and modified by [IModThings](https://github.com/IModThings/conky-bloodmod).
I have modified it to work on my Lenovo U31-70.
It probably won't work on your system without similar mods.

![alt text](https://github.com/acarl005/conky-seamod/blob/master/screenshot.png?raw=true)


## Changes

- Change color scheme.
- Change various offsets, widths, and lengths, b/c they looked all wrong on my system.
- Use new font format.
- 4 CPU cores.
- Edit disk paths.
- Edit network interface name.
- Add "text offset" argument for the labels on the rings, allowing more concentric rings to be closely packed together.
- Change network graph max value from 100b/s to 5000b/s. There is no obvious max value for this graph, and 5000 is arbitrary.
- Fix bug where values exceeding the max value overflow the ring. The ring arc is now truncated to the max value.
- Add external IP address and city of the IP.


## Installation

Don't expect this to look right without editing the source files.

```sh
sudo apt install conky-all
git clone https://github.com/acarl005/conky-seamod.git ~/.config/conky
conky -d
```

Unfortunately, it only works when placed at that specific filepath, because I had to use an absolute path in the `lua_load` command in the Conky config.
When I was using a relative path, it was relative to the cwd instead of the script.
Because of this, calling `conky` would only work when calling it inside the folder with the Conky config.
I wanted to be able to start `conky` from any directory, so I switched to an absolute path.
