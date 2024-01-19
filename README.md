# Onion OS overrides

This repository contains a list of config files and tips for Onion OS, specifically aimed to the Miyoo Mini Plus console.

All modifications proposed here are for Onion OS 4.2. Instructions for other versions may vary.

## ARCADE

### Goals

* To be able to use FinalBurn Neo as the default emulator core for arcade games. It works fine with most of the arcade games supported by MAME 2003 Plus, but uses a more modern romset and provides a more accurate emulation (take into account that the MAME 2003 Plus core it is more than 20 years old)
* To be able to play vertical games in vertical format, remapping controls accordingly.
* To have all arcade games under the `ARCADE` section (No CPS1, CPS2, CPS3 sections under `Games`)

### Change default emulator core

Change default emulator in `emu/ARCADE/launch.sh` by replacing the line:

`HOME=/mnt/SDCARD/RetroArch/ $progdir/../../RetroArch/retroarch -v -L $progdir/../../RetroArch/.retroarch/cores/mame2003_plus_libretro.so "$1"`

to:

`HOME=/mnt/SDCARD/RetroArch/ $progdir/../../RetroArch/retroarch -v -L $progdir/../../RetroArch/.retroarch/cores/fbneo_libretro.so "$1"`

### Vertical games overrides

The configs contained under the `FinalBurn Neo` folder contain configurations to enable playing those games in TATE (vertical) mode, with adapted controls. Copy it to `Saves/CurrentProfile/config`.

* `Saves/CurrentProfile/config/FinalBurn Neo/*.opt` Game specific options
* `Saves/CurrentProfile/config/remaps/FinalBurn Neo/*.rmp` Game specific button remaps

Note that these overrides are intended for right-handed players.

### Show only ARCADE section under games

Remove CPS1, CPS2 and CPS3 folders from `Emu`.

### Change emulator core in specific games

Some CPS2 and CPS3 are harder to emulate and results in slowdowns in the Miyoo Mini Plus. This can be sorted out by using an older, less demanding and accurate core than Final Burn Neo. To do that, copy the configs contained in `game_config` to `Roms/ARCADE/.game_config` (Note that the target folder is hidden), which will replace Final Burn Neo core by Final Burn Alpha 2012 or Mame 2003 Plus.
