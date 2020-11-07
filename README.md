## About

This is my setup for mouse and keyboard event mapper

At this time, setup were tested on Ubuntu 20.04.1 LTS

## Packages

* xbindkeys is used to create mouse and keyboard events and associate it with shell commands
* xautomation is used to execute mouse events on screen
* x11-utils contains xve - it was merged after ubuntu 14.04 - which is used to find button numbers

```bash
sudo apt-get install xbindkeys xautomation x11-utils
```

## 1st Step - Finding button numbers

```bash
xev -event mouse | grep Button --before-context=1 --after-context=2
```

xve captures mouse moviments, thats why we use grep to filter data only when a button is clicked

## 2nd Step - Creating bindings

Create a NEW xbindkeys config OR use the .xbindkeysrc in this repo

```bash
xbindkeys --defaults > $HOME/.xbindkeysrc
```


## 3rd - Reload Xbindkeys

```bash
killall xbindkeys
xbindkeys
```