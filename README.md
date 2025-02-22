# X servers in container for use with x11docker, ppc64le version

This Dockerfile provides a set of X servers that can be used by [x11docker](https://github.com/mviereck/x11docker).
The resulting image `smanceau44/xserver` can be used automatically to run the supported X servers in a container.
This allows to isolate the X servers from host and to reduce x11docker dependencies on host.

Pull the image from docker hub with `docker pull smanceau44/xserver`.

Or build image yourself with: `x11docker --build smanceau44/xserver`
The build takes a while because nxagent is built from source.

This image supports all x11docker X server options and also contains several tools to reduce x11docker dependencies on host.
The image includes X servers and Wayland compositors `kwin_wayland`, `nxagent`, `Xephyr`, `Xorg`, `Xvfb`, `weston`, `Xwayland` and `xpra`.

Supported x11docker options (formerly host only) for use with image `x11docker/xserver`:
 - `--kwin`
 - `--nxagent`
 - `--weston`
 - `--weston-xwayland`
 - `--xephyr`
 - `--xorg`
 - `--xpra`
 - `--xpra-xwayland`
 - `--xvfb`
 - `--xwayland`

New options that depend on image `smanceau44/xserver` and `xpra` on host:
 - `--xpra2`
 - `--xpra2-xwayland`
 
`--xpra2` and `--xpra2-xwayland` run X server and xpra server in container, but xpra client on host. 
This should provide the best possible combination of security and performance for `xpra`.

![x11docker logo](https://github.com/mviereck/x11docker/blob/screenshots/x11docker-512x512.png)
