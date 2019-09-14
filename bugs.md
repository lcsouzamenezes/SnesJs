
This is a list of all the games that I have tested and notes the bugs for each one.

The following games seem to run without any obvious bugs within the first few minutes of gameplay (except not having sound, of course).

- Super Mario World
- Super Mario All-stars
- Super Mario All-stars + Super Mario World
- F-Zero
- The Legend of Zelda: A Link to the Past
- Mega Man X
- Super Castlevania IV
- Super Ghouls'n Ghosts
- R.P.M. Racing
- Tetris & Dr. Mario
- Most of PeterLemon's roms from [here](https://github.com/PeterLemon/SNES)
  - Except the ones marked below and the ones that use expansion chips.

The following games, however, have bugs.

- Super Metroid
  - Shows corrupted graphics when they load due to a full screen transition (like intro -> space colony, map -> game or title -> demo). The same graphics load fine when they load due to a (scrolling) room transition, though.
- Mohawk & Headphone Jack
  - Freezes on boot, waiting on the SPC.
- A.S.P. - Air Strike Patrol
  - Freezes on the 'Seta presents' screen, waiting on the SPC.
- Jurassic Park
  - Doesn't blank the left and right sides of the screen properly for the visible sub-screen pixels.
- Snes Burn-in Test (Rev. D)
  - Controller test doesn't color the background blue properly when it passes.
  - Sound module test gives error 76 (expected because there is no DSP emulation yet).
  - Burn-in test doesn't start, seems to be waiting on the SPC (might be different, seems like it tries to upload some data again after already having uploaded a program to the SPC).
- Snes Test Program
  - Controller test doesn't color the background blue properly when it passes.
  - Electronics test freezes on a black screen (doesn't seem SPC related, though)
- PeterLemon's roms (from [here](https://github.com/PeterLemon/SNES)):
  - CPUTest/CPU/MSC: Freezes on a black screen when resetting for the STP-test (the PPU should not be reset when resetting the SNES).
  - Games/MonsterFarmHunter: Doesn't work properly when going in-game. A small row of white pixels near the top of the screen moves when pressing left or right (in the opposite direction), but nothing else works.
  - PPU/HDMA/HiColor128PerTileRow: Shows 7 horizontal black bars over the images.
  - PPU/Mosaic/Mode5: Mosaic doesn't show up properly.
- PPUBusActivity (rev. 2) (from [here](https://forums.nesdev.com/viewtopic.php?t=14467)):
  - Mosaic when booting doesn't show up properly for the mode 5 and 6-areas.
  - Offset-per-tile is wrong for the mode 6-area (is static, should be waving like the mode 2-area).
- Op Timing Test (v2) by Sour (from [here](https://forums.nesdev.com/viewtopic.php?f=12&t=18658&start=105)):
  - Loops the first 6 tests over and over (should go from 'absolute store' to 'absolute long', but it goes back to 'absolute').