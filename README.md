# GTA VI Data Dumps

<img src="https://img.shields.io/badge/game%20build-1.0.2.1-1f6feb" alt="Game build 1.0.2.1"> <a href="#data-dumps"><img src="https://img.shields.io/badge/data%20dumps-18-2ea44f" alt="18 data dumps"></a> <a href="#data-dumps"><img src="https://img.shields.io/badge/records-285%2C693-8250df" alt="285,693 records"></a> <a href="https://github.com/DurtyFree/gta-vi-data-dumps/commits"><img src="https://img.shields.io/github/last-commit/DurtyFree/gta-vi-data-dumps?label=updated" alt="Last update"></a> <a href="https://discord.plebmasters.de"><img src="https://img.shields.io/badge/Discord-Pleb%20Masters-5865F2?logo=discord&logoColor=white" alt="Pleb Masters Discord"></a>

Dodo's Rising, and so is everything the community will build on top of Leonida.

This repository is a collection of clean, ready-to-use data sets for Grand Theft Auto VI. It is here to help enhance the game through custom content, to help content creators understand the game better, and to give everyone easy, reliable and accessible data to build on.

The dumps are kept up to date: expect refreshed and new files with future game updates, DLCs, an online mode and whatever else comes next.

Looking for another game? See the [GTA V data dumps](https://github.com/DurtyFree/gta-v-data-dumps) and the [RDR 3 data dumps (Red Dead Redemption 2)](https://github.com/DurtyFree/rdr-3-data-dumps).

> **Join the Pleb Masters community Discord to share, discuss and collaborate:** https://discord.plebmasters.de

## Data dumps

### 🚗 Vehicles

| Dump | File | Count | Good for |
| --- | --- | --- | --- |
| **Vehicles** | [vehicles.json](vehicles.json) | 327 vehicles | Every vehicle model: type, class, plate type, wheel type, flags, handling name, spawn frequency, body health, dirt levels and detail distances |
| **Vehicle colours** | [vehicleColors.json](vehicleColors.json) | 151 colours, names not known yet | The paint colours vehicles can carry: colour value |
| **Vehicle plates** | [vehiclePlates.json](vehiclePlates.json) | 14 plate styles, names not known yet | Licence plate styles: letter count, font extents, font colour and outline colour |

### 🎯 Weapons

| Dump | File | Count | Good for |
| --- | --- | --- | --- |
| **Weapons** | [weapons.json](weapons.json) | 112 weapons | Every weapon: weapon type, caliber, clip sizes, ranges, forces, reload times, time between shots, head shot distances, camera and recoil shake, AI attack modes, accuracy profile and pickup |
| **Ammo** | [ammo.json](ammo.json) | 79 ammo types, 13 with a known name | Bullets and other ammo: penetration, life time, launch speed, ricochet tolerance, gravity factor, explosion tags, light settings and seeking and sticking tuning |
| **Weapon accuracy profiles** | [weaponAccuracies.json](weaponAccuracies.json) | 100 accuracy profiles, names not known yet | Accuracy profiles that weapons share: spread, accuracy fall-off, recoil and run-and-gun modifiers |
| **Weapon damage modifiers** | [weaponDamageModifiers.json](weaponDamageModifiers.json) | 116 damage modifier sets, names not known yet | Damage multiplier sets: head shot, limb, light armour, vehicle, player against AI and critical hit chance |
| **Pickups** | [pickups.json](pickups.json) | 768 pickups, 14 with a known name | Every pickup: collection radius, regeneration time, scale, attachment offset and rotation and what happens in a car or when shot |

### 🧍 Peds and animals

| Dump | File | Count | Good for |
| --- | --- | --- | --- |
| **Peds** | [peds.json](peds.json) | 2,714 peds, 331 with a known name | Every ped: physical model, size, scale, age group, affluence, spawn preference and range, capsule, navigation capabilities, motion task data set, brawling style, facial clip set group and viseme clip set |
| **Ped capsules** | [pedCapsules.json](pedCapsules.json) | 108 capsules, 57 with a known name | The collision capsules of humans, quadrupeds, birds and fish: radius, mass, probe radius, ground offset, flatten limits and ragdoll switches |
| **Ped navigation capabilities** | [pedNavCapabilities.json](pedNavCapabilities.json) | 22 capability sets, 9 with a known name | What a ped type can path over: climb height, drop height, path-find radius and capability flags |
| **Animal tunings** | [animalTunings.json](animalTunings.json) | 211 animal tunings, 3 with a known name | Behaviour per animal: combat, fleeing, flocking, fear range and threat response |

### 🌍 World

| Dump | File | Count | Good for |
| --- | --- | --- | --- |
| **Explosion types** | [explosions.json](explosions.json) | 68 explosion types, 41 with a known name | Every explosion tag: damage, radius, force, camera shake and behaviour switches |
| **Door tunings** | [doorTunings.json](doorTunings.json) | 21 door tunings | The named door presets: auto-open, locking, breaking and mass |

### 📚 Names and reference

| Dump | File | Count | Good for |
| --- | --- | --- | --- |
| **Enums and flags** | [enums.json](enums.json) | 116 enums, 3,306 values | Every named enum and flag set with its value names and numbers, as the records above use them |
| **Animation dictionaries** | [animDicts.json](animDicts.json) | 70,119 animation dictionaries | The names of the animation (clip) dictionaries |
| **Drawables** | [DrawableList.ini](DrawableList.ini) | 180,121 models | The names of the static models: props, buildings, map pieces, clothing and weapon parts |
| **Fragments** | [FragmentList.ini](FragmentList.ini) | 30,526 models | The names of the physical and breakable models: vehicles and their parts, ped bodies, physical props |

## Reading the files

- Records start with `Name`, `Hash` and `HexHash`. Where a name is not known yet, `Name` is `null` and the hashes identify the record; names are filled in as they are found.
- Explosion types are numbered by the game: these records start with `Name` and `Index`, and the number identifies the record.
- A field is left out when its value is not known yet or is not set. An empty list `[]` is a list that really is empty.
- Enum and flag values are written by name; `enums.json` has the numbers behind them.
- Colours are written as `#AARRGGBB`.
- Some fields point at a record of another file. They hold that record's `Name`, or its `HexHash` where the name is not known yet:
  - `PedCapsuleName` in [peds.json](peds.json) → [pedCapsules.json](pedCapsules.json)
  - `NavCapabilitiesName` in [peds.json](peds.json) → [pedNavCapabilities.json](pedNavCapabilities.json)
  - `AccuracyInfo` in [weapons.json](weapons.json) → [weaponAccuracies.json](weaponAccuracies.json)
  - `PickupHash` in [weapons.json](weapons.json) → [pickups.json](pickups.json)
  - `PickupHash` in [ammo.json](ammo.json) → [pickups.json](pickups.json)
  - `WeaponType` in [ammo.json](ammo.json) → [weapons.json](weapons.json)
  - `Explosion.Default` in [ammo.json](ammo.json) → [explosions.json](explosions.json)

## Something wrong, or something missing?

Spotted a value that looks off, or is there a dump you would love to see here? Open an issue. Reports and wishes are both welcome, and they are how this collection gets better.

## Related data dumps

The same kind of collection exists for the other games:

| Repository | What is in it |
| --- | --- |
| **[GTA V data dumps](https://github.com/DurtyFree/gta-v-data-dumps)** | Vehicles, peds, weapons, objects and much more for Grand Theft Auto V |
| **[RDR 3 data dumps (Red Dead Redemption 2)](https://github.com/DurtyFree/rdr-3-data-dumps)** | Data sets for Red Dead Redemption 2 |

## More from Pleb Masters

<table>
  <tr>
    <td align="center"><a href="https://cloth.durty.dev/"><img src="https://i.imgur.com/ZINtfW8.png" alt="Durty Cloth Tool" height="64"></a><br><a href="https://cloth.durty.dev/"><b>Durty Cloth Tool</b></a><br><sub>Create addon clothing packs for GTA V</sub></td>
    <td align="center"><a href="https://forge.plebmasters.de"><img src="https://i.imgur.com/hotlSPf.png" alt="Pleb Masters Forge" height="64"></a><br><a href="https://forge.plebmasters.de"><b>Pleb Masters Forge</b></a><br><sub>Browse GTA V vehicles, peds, objects, clothes and more</sub></td>
  </tr>
</table>

## Disclaimer

This project is not affiliated with, endorsed by or connected to the publisher or the developer of the game. It is research for educational purposes. It contains no game files; all trademarks belong to their owners.
