# Why?

The upstream Minit build appears to be built against OpenSSL 1.0.0, so it doesn't install easily on modern Ubuntu (eg, Ubuntu 20.04). However, Snap *does* support an Ubuntu 18.04 base system, so by building a snap for Minit, it's easy to run on more modern Linux machines.

The snap itself contains all the game code and assets, so distributing it seems poor. However, the `snapcraft.yaml` file here should allow easily building it.

# Building Minit snap

1. Download the .deb for Minit (eg, from the download link on https://devolverdigital.itch.io/minit) and put it in this directory
2. Install `snapcraft` if necessary -- `apt install snapcraft` or `snap install snapcraft` should work
3. Run `snapcraft` in this directory to build the snap
4. Install the snap with `sudo snap install --dangerous --devmode minit_1.0_multi.snap`
5. Run with `snap run minit`

# Other notes

As described in [a Reddit post](https://www.reddit.com/r/linux_gaming/comments/jv8kds/minit_game_installation/), you'll probably want to disable the camera. The file the post mentions isn't right with a snap, though -- you'll want `~/snap/minit/current/.config/minit/camera/camera.ini`.

You will also probably want to run fullscreen -- I tried and failed to make the snap do that automatically, but the settings menu works, and it'll carry over across restarts.
