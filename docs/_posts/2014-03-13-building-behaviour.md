---
layout: post
title: "Building Behaviour"
categories: game-mechanics
---

While most buildings operate exactly as described in the game's manual,
some behave in undocumented or unexpected ways. See also
[PAFW and Resource Deficiency](pafw-and-resource-deficiency.html) for how
buildings fail in a power outage, and [Building Hitpoints](building-hitpoints)
for how buildings behave when damaged.

### Storage Facility / Storage Tower

If an ore storage building is destroyed, no ore is lost unless the total
amount of ore stored at the asteroid now exceeds the total storage capacity.
When this happens, ore is lost starting with Selenium and going through the
ores in order until capacity is sufficient again.

### Anti-Missile Pod

Each incoming missile has a 21% chance to be shot down if you have one
Anti-Missile Pod. Each additional pod increases the chance by 2%, to a maximum
of 71% at 26 pods.

However, for all aliens which use this technology (Ore Eater's Defence Battery,
Rigellian Defence Battery, and Swixaran Tentacular Defender), each additional
pod increases the chance by 4%, to a maximum of 71% at 14 pods.

Anti-Missile Pods will fire at missiles you shoot at your own asteroids, but
will ignore Anti-Virus missile.

### Decontamination Filter

Each Decontamination Filter decreases the radiation at a colony by 30%. See
[Health, Radiation and Population
Growth](health-radiation-and-population-growth.html).

### Mine, Deep Bore Mine and Seismic Penetrator

Each Mine recovers one ore per 4 days, or one per 2 days with the 2nd Generation
Mines blueprint. Each Deep Bore Mine recovers one every 16 days, or every 8
days with the 2nd Generation Deep Bore Mines blueprint.
Each Seismic penetrator recovers one ore every 16 days.

The ore mined is chosen at random from the types the mine is compatible with.
If there is none of that ore, the others are tried in order. For example, if
an asteroid has only Selenium and Asteros, 50% of the time it will attempt to
mine Barium or Crystalite and get Selenium instead. This effect applies only
to the Mine and Deep Bore Mine, but not the Seismic Penetrator, e.g. if there
is only Nexos but no Traxium, the Seismic Penetrator will recover Nexos 50%
of the time and do nothing the other 50%.

If there is not enough ore storage capacity at an asteroid, the ore will
not be mined. You cannot waste ore by building mines before storage. However,
due to a Powerplant bug, un-mined Asteros depletes automatically as if by
radioactive decay.

Each mine of any type requires eight colonists as workers. If there are
not enough workers, or the colony's workers are on strike, the mine operates
at 40% efficiency. Each time it would normally
recover an ore, it instead has a random 40% chance to succeed.
In event of a worker shortage, Mines are given precedence over Deep Bore Mines
and Seismic Penetrators.
If the mine is without power, it does not mine any ore.

### Screen Generator

All buildings covered by at least one Screen Generator reduce all damage taken
by 50%. The Screen Generator benefits from its own protection.

### Gravity Nullifier

In the event of a power outage, the Gravity Nullifier will switch off, but when
power returns, it does not automatically switch back on. It cannot distinguish
between intentionally turned off by the player and automatically turned off by
power shortage.

### Missile Silo

Every 8 days, one of each missile type on order is built.

Each Missile Silo requires 8 colonists as workers. If there are not
enough workers or the colony's workers are on strike, missile construction
operates at 40% efficiency. Each day, there is only a 40% chance that
one missile will be built. Workers are not required to fire missiles.

### Repair Facility

Each Repair Facility restores one point of damage to each building every eight
days, up to the building's normal maximum. Multiple facilities stack.

If the blueprint Building Armour is available, all buildings' maximum hit points
are increased by 10. A Repair Facility will retroactively apply this bonus maximum
to buildings constructed before the Building Armour blueprint was purchased.

Small ships in hangars are repaired at the same rate of one point per Repair Facility
every eight days, to a maximum of the ship's base armour without shields. Contrary
to the manual, ships in orbit are never repaired, and ships in hangars only repair if
the colony has a Repair Facility.

### Laser, Plasma and Photon Turret

Terran turrets have the following damage output:

| Turret | Damage | With Optimizer |
|:-------|-------:|---------------:|
| Laser  | 2      |  4             |
| Plasma | 5      | 10             |
| Photon | 8      | 16             |

The Turret Optimizer blueprint doubles the output. "Protected" buildings operate
exactly as a Laser Turret. Each Turret fires once every five days, and the
cooldown resets on a power outage or a miss.

Alien turrets have different (usually higher) damage and different (usually
worse) cooldown timers.

### Asteroid Engines

A [random event](random-events.html) can cause Asteroid Engines to explode,
increasing the colony's radiation level by 10%.

Asteroid Engines require 2-7 power based on current speed (not 0-5 as
described in the manual).

### Powerplant

Un-mined Asteros depletes at a rate of one unit per four days, _even_ if no
Powerplants hae been built. This is either a bug, or an attempt to represent the
half-life of a radioactive element.

Powerplants run on un-mined ore _in the asteroid_, not in store. As long as
there is one unit of Asteros left un-mined, every Powerplant on the asteroid
produces 32MW of power. Powerplants do not use up the Asteros or cause it to
deplete any more quickly, no matter how many Powerplants you have.

When Asteros is depleted, the Powerplant produces no power. Although the
manual states that it produces 8MW/day without Asteros, this appears to
be a misinterpretation of the game code, which produces 8MW/day per
C.P.U, the building appearing next to it in the code (since the four-square
buildings appear to have been all added around the same time).

A [random event](random-events.html) can cause a Powerplant to explode,
increasing the colony's radiation level by 10%.

### Command Centre

A Command Centre requires 8 colonists as workers. A worker shortage is likely to
affect only the Command Center's speed at building an Orbital Space Dock, in
which case it operates at 40% efficiency.

### Construction Yard

In order to make a day's progress toward a construction job, the yard requires
one day's worth of payment from Vehicle Fund. One of each ore is required per day
at the end of the ship's construction, e.g. the last two days of an Assault
Fighter's construction require one Selenium and Crystalite each. If all requirements
are met, the ship is reduced.

Each Construction Yard requires 8 colonists as workers. If there are not
enough workers or the colony's workers are on strike, all yards operate
at 40% efficiency. Each day, there is only a 40% chance that a day's
progress will be made.

There appears to he a maximum of 64 shipyards at any one time. Orbital Space
Docks and Command Centres (producing Orbital Space Docks) may count
toward this limit.

### Landing Pad

Ships landed in hangars do not repair damage unless the colony also has a
Repair Facility.

### Medical Centre

Each Medical Centre reduces the effects of radiation (but not the radiation
level itself) by 10%. In the event of a virus outbreak, a colony also
requires one Medical Centre for every 100 full colonists after the first 50
in order to end the outbreak.

See [Health, Radiation and Population Growth](health-radiation-and-population-growth.html).

### Security Centre

A colony needs one Security Centre for every full 100 colonists after the
first 50 to prevent social unrest.
See [Security and Morale](security-and-morale.html).

### "Protected" buildings

In addition to the laser turret attached to the
Protected Resiblock, Protected Solar Matrix, and Protected Environment Control,
these buildings have higher hit points than their non-protected counterparts
(see [Building Hitpoints](building-hitpoints.html)). Protected Storage Tower does not.
