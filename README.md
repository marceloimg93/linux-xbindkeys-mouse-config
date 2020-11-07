# linux-xbindkeys-mouse-config

This is my setup for mouse and keyboard event mapper

At this time, setup were tested on Ubuntu 20.04.1 LTS

## packages

* xbindkeys is used to create mouse and keyboard events and associate it with shell commands
* xautomation is used to execute mouse events on screen
* x11-utils contains xve - it was merged after ubuntu 14.04 - which is used to find button numbers

```sudo apt-get install xbindkeys xautomation x11-utils```

## 1st Step - Finding button numbers

```xev -event mouse | grep Button --before-context=1 --after-context=2```

xve captures mouse moviments, thats why we use grep to filter data only when a button is clicked

## 2nd Step - Creating bindings

Create xbindkeys config

```xbindkeys --defaults > $HOME/.xbindkeysrc```

OR use the .xbindkeysrc at this repository

`
# double click mx ergo mouse
"xte 'mouseclick 1' 'mouseclick 1'"  
  b:8+Release

# tripple click mx ergo mouse
"xte 'mouseclick 1' 'mouseclick 1' 'mouseclick 1'"
  b:9+Release
`

## 3rd - Reload Xbindkeys

`
killall xbindkeys
xbindkeys
`