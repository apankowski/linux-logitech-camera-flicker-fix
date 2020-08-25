# Linux Logitech BCC950 Camera Flicker Fix

This is a simple configuration of the Linux USB subsystem to fix flickering of the Logitech BCC950 camera. The flickering seems to be caused by the camera's _power line frequency_ setting defaulting to 60Hz. However, where I live (and most of the world as far as I know) the power line frequency is 50Hz which causes the flickering.

This configuration causes a command to be run whenever Logitech BCC950 camera is connected via USB. This command changes the _power line frequency_ setting to 50Hz, thus removing the flickering.

## Requirements

The configuration here requires `v4l2-ctl` binary which is bundled in the `v4l-util` package. You can install it by issuing these commands:

```bash
sudo apt update
sudo apt-get install v4l-utils
```

## Instructions

 1. Copy [this configuration file](/50-logitech-bcc950-conference-cam.rules) to `/etc/udev/rules.d/`.
 1. Disconnect the camera.
 1. Reconnect the camera.

That's it!