# [stash/hub] + [stash]
Puredata (Pd) abstractions for preset management, based on central [stash/hub] and small [stash] plugin objects

## Requirements
* requires `iemguts` library (available via `Deken`)

## Usage
* connect [stash] objects to any number of objects to store and restore their values (connections are made via "cross-connecting" - inlet->outlet, outlet->inlet)
* create a central [stash/hub] to control presets (store, restore, save, load, ease, fade, etc.)
* an additional [stash/arr <array_name>] object can be used to store and restore array values

## Features
* handles all objects that output their state on `bang` input
* save / load preset files
* store (and restore) arbitrary amount of preset states
* ease states with a variety of ease functions
* morph between states with float input (0..1 or 1..0 - depending on start value)
* additional helper object [stash/arr] facilitates management of array values
* optional argument to create black or randomly colored plugins (`-black` or `-color` based on id) 
* manually set id via `-id <number>` argument or simply by adding a float argument

see help of [stash] object for example application.
