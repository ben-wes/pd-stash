# [stash/hub] + [stash]
Puredata (Pd) abstractions for preset management, based on central [stash/hub] and small [stash] plugin objects

### Requirements
* requires `iemguts` library (available via `Deken`)

### Usage (draft)
* connect [stash] objects to any number of objects to store their values
* create a central [stash/hub] to control presets (store, restore, ease, fade, etc.)
* an additional [stash/arr <array_name>] object can be used to store and restore array values

see help of [stash] object for example application.
