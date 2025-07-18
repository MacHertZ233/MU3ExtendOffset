# MU3-ViciousOptimizers
[English](README.md)\
[简体中文](README_zh-hans.md)

A collection of mods for the game codename MU3, made purely to maximize the rhythm gaming experience.

Evil enough, and useful enough.

So far, the collection includes:
+ ***ExtendOffset***: Extends the adjustment range of offset A & B from ±2.0 to ±10.0.
+ ***ShiftSECount***: Makes the cue ticks before the music more aligned with the music rhythm (if the dev team doesn't screw up the audio alignment).
+ ***MuteEnemySound***: Eliminates enemies' vocals as well as sound effects that prompt defeat of the enemies, so that the music is never obscured.
    + ***MuteEnemySoundLite***: Eliminates enemies' vocals only. For those who want to get their battle progress on audio.

## Dependencies

+ [BepInEx](https://github.com/BepInEx/BepInEx) 5
+ [BepInEx.MonoMod.Loader](https://github.com/BepInEx/BepInEx.MonoMod.Loader) (optional, required for MonoMod method)

## Installation
There are 2 ways to install each mod. Just choose between one of them.
+ **Plugin Method**: Put `<ModName>_plugin.dll` into `BepInEx\plugins` folder.
+ **MonoMod Method**: Put `Assembly-CSharp.<ModName>.mm.dll` into `BepInEx\monomod` folder.

For *ExtendOffset*, there is also a final solution, which is to replace `package\mu3_Data\Managed\Assembly-CSharp.dll` with `Assembly-CSharp-offset10.dll`. BEWARE: Use this method if and only if neither of the above methods is feasible.

## Supported Game Versions

+ 1.50

## Known Issues

+ The MonoMod version of *ExtendOffset* is currently incompatible with [*MoreProfileOptions*](https://www.rainycolor.org/package/7EVENDAYSHOLIDAYS/MoreProfileOptions/).
    + The Plugin version released lately is expected to address this issue, but still lacks more testing.
    + A modded `Assembly-CSharp-offset10.dll` will be provided as a final workaround. 

+ When offset A is adjusted to a larger value, the cue ticks before the music starts will noticeably deviate from the music.
    + Using *ShiftSECount* will mitigate the situation in most cases. But we don't know how well the devs are doing with the audio alignment.

## Build from Source

1. Put the following files into `.\lib` folder. They can be retrieved from `<MU3_game_path>\package\mu3_Data\Managed` and `BepInEx\core`. 
```
AMDaemon.NET.dll
Assembly-CSharp.dll
Assembly-CSharp-firstpass.dll
UnityEngine.dll
UnityEngine.UI.dll

BepInEx.dll
0Harmony.dll
```

2. Open the solution with Visual Studio (preferably VS2022) and build all projects.

## Credit

+ [mu3-mods](https://gitea.tendokyu.moe/akanyan/mu3-mods), for providing inspiration and reference for my mods.