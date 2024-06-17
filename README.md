# [stash/hub] + [stash]
Puredata (Pd) abstractions for preset management, based on central [stash/hub] and small [stash] plugin objects

![stash-help.pd screenshot](stash-help.pd.png)

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

## Mechanism
* when creating a [stash] object, it will self-assign its id and then check among other [stash] objects in the patch whether the id is unique. it will repeat this process with random ids from a range of `0..10'000'000` until it finds a unique id
* when storing a preset with [stash/hub], all [stash] objects get a `store` message and output a bang and send the numbers they receive in their inlet back to [stash/hub] with their id
* easing and morphing are handled in the [stash] objects based on the messages they receive
