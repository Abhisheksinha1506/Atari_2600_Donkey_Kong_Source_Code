# Donkey Kong (Atari 2600) - Source Code Analysis

## Overview
This repository contains the original 6502 assembly source code for the Atari 2600 port of **Donkey Kong**. The project was developed for Coleco by Garry Kitchen and others, and this specific listing is dated **February 24, 1983**. It provides a fascinating look into the highly optimized programming required to fit a complex arcade game into the Atari 2600's extremely limited memory (128 bytes of RAM) and ROM space.

## Project Details
- **Developer**: Garry Kitchen (Design/Programming)
- **Year**: 1982-1983
- **Platform**: Atari 2600 (VCS)
- **Processor**: MOS 6502 (6507 variant)
- **Assembler**: ATARI CAMAC Assembler Ver 1.0A

## Technology Stack
- **Primary Language**: 6502 Assembly.
- **Tools**: CAMAC Assembler (running on an Apple II or Atari 8-bit computer).
- **Architecture**: A hardware-driven design that relies on the "Television Interface Adaptor" (TIA) for graphics and sound, requiring the CPU to "race the beam" (timing code exactly to the TV scanlines).

## Repository Structure & Modules
- `MAIN.PRN.txt`: The primary assembly listing, containing both source code, machine code offsets, and developer comments.
- `MARIO.FNT`: Sprite data for Mario's animations.
- `KONG.FNT` / `LADY.FNT`: Sprite data for Donkey Kong and Pauline.
- `SNDTBL`: Data tables for the game's sound effects and music.
- `COLLIS`: Collision detection logic between Mario, barrels, and fireballs.
- `ELEV`: Logic for the elevator stage.
- `SCHED`: The task scheduler that manages game states and object updates.

## Key Functions & Technical Logic
- **Header (HDR)**: Defines global constants like `invinc` (invincibility), `debug`, and `rom`. The `invinc` flag is notably set to `true` in this version, suggesting it was a testing build.
- **Macros (`MACS`)**: Includes custom assembly macros like `dldi` (Double Load Immediate) to handle 16-bit address loads into 8-bit registers.
- **Main Loop**: Located in `MAIN`, it manages the VBLANK period, scanline generation via TIA registers (`COLUP0`, `GRAP0`, etc.), and overscan.
- **Sprite Generation**: Found in the `.FNT` files, these are bitmapped representations of the 4x8 or 8x8 player/missile objects used by the Atari 2600 hardware.

## Historical significance
This source code represents one of the most successful arcade-to-home ports of the early 80s. Despite the hardware's limitations (only two player sprites and three missiles), the developers used sophisticated code-timing tricks to display multiple platforms, barrels, and the titular ape.

## How to Explore
1.  **MAIN.PRN.txt**: Read this for a side-by-side view of assembly code and comments.
2.  **TODO**: A small file documenting remaining tasks or bugs from the 1983 development cycle.
3.  **MARIO.FNT**: Examine this to see how 1-bit sprites were defined for the console.
