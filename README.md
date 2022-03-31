# suckless patches
Patches customizing or adding functionality to suckless tools: dwm and dmenu. See: https://dwm.suckless.org/

See also my corresponding https://github.com/solutionroute/dotfiles.

## st

* terminal.sexy colours 
* Roboto Mono font, size 11
* add "scroll" (You'll need to clone, edit in mouse wheel lines in
  <https://git.suckless.org/scroll>, make && sudo make install)
* st.desktop for use with desktop environments; map keyboard shortcut
  alt-shift-enter to st for a pleasant experience in GNOME. :-) Note: I found I
  had to install `libxft-bgra` to stop crashing on GNOME but it very well may
  have been an issue on XOrg as well.

## dwm

Combined patches rolled up into one diff: [dwm-mw-20220212.diff](https://github.com/solutionroute/suckless-patches/blob/main/dwm-mw-20220212.diff). 
The changes include adding some colours in support of colorbar, and:

* Made bar height padding a constant (`barpadpx`) in config.def.h (original
  default is 2, to my eye, somewhat larger font sizes look a bit crowded
  without a bit more space (4 or 6px).

* From suckless.org/patches/[pertag](https://dwm.suckless.org/patches/pertag/), 
  the ability to have different layouts for each tag.

* From suckless.org/patches/[rmaster](https://dwm.suckless.org/patches/rmaster/),
  making it possible to swap the master/client with a toggle, ideal for those
  of us with multi-head / dual monitors who like our master areas in the centre
  of our viewing space.

* From suckless.org/patches/[colorbar](https://dwm.suckless.org/patches/colorbar/),
  some changes that made my own bar customizations less hacky. My bar is pretty
  bland.  Blander, but only one colour, than the sock dwm!

## dmenu

* Implemented the same `bar_hpadx` configuration knob as in patched dwm. Patch: [dmenu-mw-barpad-20220212.diff](https://github.com/solutionroute/suckless-patches/blob/main/dmenu-mw-barpad-20220212.diff)

## slock

Feb 2022: Did away with a patch I'd added to avoid making slock translucent via picom/compton. 
Instead, this in picom.conf does the job:

    # exclude dwm, dmenu and the slock screen locker
    focus-exclude = "x = 0 && y = 0 && override_redirect = true";

## Obligatory Screenshot

These are bland screenshots showing off "pertag"; I'm not 100% convinced I need pertag, 
but for a multi-monitor set of desktops, I definitely need "rnmaster" which gives the 
ability to toggle where the master pane goes, right or left.

![pertag - tag 1](https://raw.githubusercontent.com/solutionroute/suckless-patches/main/screenshots/pertag1.png)
**Tag 1**

![pertag - tag 2](https://raw.githubusercontent.com/solutionroute/suckless-patches/main/screenshots/pertag2.png)
**Tag 2**
 
And a boring big two monitor desktop:
![Boring "desktop"](https://raw.githubusercontent.com/solutionroute/suckless-patches/main/screenshots/20220104-172007.png)
