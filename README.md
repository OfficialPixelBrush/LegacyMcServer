> [!NOTE]
> LegacyMcServer development has been completely halted, as I've shifted my
> focus towards [Betrock++](https://github.com/OpenBetaGroup/BetrockPlusPlus).
>
> [Betrock++](https://github.com/OpenBetaGroup/BetrockPlusPlus)
> reuses a lot of the work that was done for LegacyMcServer,
> just reworked to be more performant, readable and modular.
>
> It intends to be a more complete and actually thought out package.
> There're even plans to use the code to make a client too!
> 
> Check out the [OpenBeta project page](https://openbetagroup.github.io) for info on other related projects.

[![Discord](https://img.shields.io/badge/Join%20the-Discord-7289DA)](https://discord.gg/JHTz2HSKrf)
![C#](https://img.shields.io/badge/Language-C%2B%2B23-5E96CF)
![Issues](https://img.shields.io/github/issues/OfficialPixelBrush/LegacyMcServer)
![Pull requests](https://img.shields.io/github/issues-pr/OfficialPixelBrush/LegacyMcServer)

A Minecraft Beta 1.7.3 Server written in C++23. The goal being to have a semi-modern Beta 1.7.3 server that people can muck about with however they like, and to not have to deal with plugins that're over a decade old.

## Features
(as of 0.3.0)
- Players can connect, chat, build and explore
- Lots of Commands
- (very) accurate Beta 1.7.3 Terrain
- Lua-driven World Generation
- World saving and loading (**not** in McRegion format yet)
- Extensive multi-threading

## Discord
We have a [Discord Server](
https://discord.gg/JHTz2HSKrf)!

## Screenshots

| Glacier | pack.png | Gargamel |
|--- | --- |--- |
| ![](media/screenshots/gameplay.png) | ![](media/screenshots/pack.png) | ![](media/screenshots/gargamel.png) |

## Getting Started
How do you run your own LegacyMcServer instance?

If you're on Linux, simply follow the steps listed below. If you're on Windows, please follow these same steps only after installing [Windows Subsystem for Linux (WSL2)](https://learn.microsoft.com/en-us/windows/wsl/install).

## Option 1 - Download
Check the releases page for the latest binary of LegacyMcServer. Then simply run the executable.

If it complains about lacking a `scripts` folder, download the `src/scripts` folder from the repository and place it alongside the executable.

Downloading can be unreliable, since certain libraries, such as `libdeflate`, may not necessarily be installed. Compiling is honestly the easier and more robust option.

## Option 2 - Compiling
This section is written to be as accessible as possible, so anyone can compile LegacyMcServer.

### Install Dependencies
**Debian/Ubuntu**
```bash
sudo apt install git cmake build-essential libdeflate-dev liblua5.4-dev
```
**Arch**
```bash
sudo pacman -Syu git cmake make gcc lua libdeflate
```
**Fedora**
```bash
sudo dnf install git cmake make gcc lua-devel libdeflate libasan
```
This installs all the necessary libraries that LegacyMcServer needs.

### Clone
```bash
git clone --recurse-submodules https://github.com/OfficialPixelBrush/LegacyMcServer.git
cd LegacyMcServer
```
This downloads the repository onto your computer.
```bash
cmake -S . -B build
cd build
```
This configures the development environment.

### Build
```bash
cmake --build .
```
This turns the source code into an executable binary file.

### Running
```bash
./LegacyMcServer
```
This runs the built executable and generates a new world,
if one isn't already present.

### Packing (For Releasing)
```bash
cpack --config CPackConfig.cmake -G TGZ
```

## Issues
If you encounter **any** issues, inaccuracies to the base game or simply want to provide an idea that may make LegacyMcServer better,
please report them on the [Issues tab](https://github.com/OfficialPixelBrush/LegacyMcServer/issues).

Please check if the issue you've found has already been reported or even been solved already.

If not, create a **new issue** and fill out all the necessary information according to the `Bug Report` template to the best of your abilities.

## Misc
- [PixNBT](https://github.com/OfficialPixelBrush/pixnbt) - A C++ native NBT parsing library
- [BetaPacketPlainTextifier](https://github.com/OfficialPixelBrush/BetaPacketPlainTextifier) - A utility for turning WireShark captures of Minecraft Client-Server data into Markdown files for easy decoding
- [Beta Wiki](https://officialpixelbrush.github.io/beta-wiki)

# Contributing
Please read the [CONTRIBUTING](https://github.com/OfficialPixelBrush/LegacyMcServer/blob/main/CONTRIBUTING.md) page.

# Resources
For further reading, to aid development and sources for where certain info has been gotten from.

Some stuff can be found on the [LegacyMcServer Wiki](https://github.com/OfficialPixelBrush/LegacyMcServer/wiki),
especially if you're interested in developing your own [World Generator](https://github.com/OfficialPixelBrush/LegacyMcServer/wiki/World-Generation) or [Plugin](https://github.com/OfficialPixelBrush/LegacyMcServer/wiki/Plugins).

If you're more interested in the in-depth technical stuff of Beta 1.7.3, check out [my extended fork of mudkipdev's Beta Wiki](https://officialpixelbrush.github.io/beta-wiki)!

- GitHub
    - [beta-wiki (fork)](https://officialpixelbrush.github.io/beta-wiki) by [OfficialPixelBrush](https://github.com/OfficialPixelBrush/beta-wiki)
    - [beta-wiki (og)](https://github.com/mudkipdev/beta-wiki) by [mudkipdev](https://github.com/mudkipdev)
- Wiki.vg (Now part of the Minecraft Wiki)
    - [Protocol](https://minecraft.wiki/w/Minecraft_Wiki:Projects/wiki.vg_merge/Protocol?oldid=2769758)
    - [Region Files](https://minecraft.wiki/w/Minecraft_Wiki:Projects/wiki.vg_merge/Region_Files)
- Minecraft Wiki
    - [NBT Format](https://minecraft.wiki/w/NBT_format)
    - [Region File Format](https://minecraft.wiki/w/Region_file_format)
    - [Help:Isometric Renders](https://minecraft.wiki/w/Help:Isometric_renders) (Used for the Logo)

# Stats
![Contributors](https://img.shields.io/github/contributors/OfficialPixelBrush/LegacyMcServer)

| Issues | PRs |
| - | - |
| ![Open Issues](https://img.shields.io/github/issues/OfficialPixelBrush/LegacyMcServer) | ![Open PRs](https://img.shields.io/github/issues-pr/OfficialPixelBrush/LegacyMcServer) |
| ![Closed Issues](https://img.shields.io/github/issues-closed/OfficialPixelBrush/LegacyMcServer) | ![Closed PRs](https://img.shields.io/github/issues-pr-closed/OfficialPixelBrush/LegacyMcServer) |

| Branch | Commits |
| - | - |
| main | ![Commits (main)](https://img.shields.io/github/commit-activity/t/OfficialPixelBrush/LegacyMcServer/main) |
| latest | ![Commits (latest)](https://img.shields.io/github/commit-activity/t/OfficialPixelBrush/LegacyMcServer/latest) |
                        
## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=OfficialPixelBrush/LegacyMcServer&type=Date)](https://www.star-history.com/#OfficialPixelBrush/LegacyMcServer&Date)
