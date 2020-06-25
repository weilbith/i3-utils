# i3 Utils

Utility scripts for the [i3](https://i3wm.org/) tiling window manager.

## Installation

Simply clone this repository and add the script to your `$PATH`. Alternatively
on _Arch Linux_ you use the `PKGBUILD` to install it as a package. This is not
available as `AUR`, since it is too personal and does therefore not fulfill the
requirements.

```sh
git clone https://github.com/weilbith/i3-utils.git /tmp/i3-utils
cd /tmp/i3-utils
makepkg --syncdeps --install
```

## Selections in a menu

Some of the scripts provide a list of options to the user he can select form.
Therefore the `dmenu` command is used. Therefore the origin
[dmenu](https://wiki.archlinux.org/index.php/Dmenu) can be used. The more
favorable and recommended alternative is
[rofi](https://github.com/davatorium/rofi). It supports a compatibility command
to mimic `dmenu`.
You can select one of them as optional dependency if you use the package
installation approach.

## Utilities

### i3-goto-mark

Opens a menu to select from all marked windows. Jumps to the window with the
selected mark.

Requirements:

- `i3-msg`
- `dmenu` (or alternative)

### i3-win-info

Prints a list of information for the clicked window. Useful to find unique
descriptions to define `for_window` statements or command criteria in the `i3`
configuration. Though not all
[criteria](https://i3wm.org/docs/userguide.html#command_criteria) are supported.

Requirements:

- `xwininfo`
- `xprop`

### i3-lock

Looks the screen with predefined settings and a given background image. Uses the
[forked version](https://github.com/Raymo111/i3lock-color) of the locker, called
`i3lock-color`. Expects the first argument to be a path to an image to use as
wallpaper. Else it defaults to `$HOME/images/wallpapers/wallpaper.png`.

**Attention:** Notice the intended slightly difference between the original
command `i3lock` and this here `i3-lock`. Related to the note below.

**Note:** This script is pretty much opinionated expect the image path.

Requirements:

- `i3lock-color`
