# SkateIV
GTA IV x Skate 3 passthrough mod (WIP, needs some love) 
https://youtu.be/vaBxI5LtyzI?si=TfkvPwRg7Jb7ueRS
# GTA IV Skate — v0.8.11 experimental preview

See DISTRIBUTION.md for credits and distribution information.

This mod hosts the Skate 3 Rust engine inside GTA IV. GTA owns the world, current player model, clothing, lighting, and traffic. Skate supplies skating physics and animations. This is a development preview; collision, grind transfers, shadows, and performance still have known issues.

## Requirements

- Windows 10/11, 64-bit.
- Your own working GTA IV **1.0.8.0** installation and a compatible ASI loader. The current Steam Complete Edition executable is not supported. Setup does not downgrade, patch, or replace the game executable.
- Your own extracted **Xbox 360 Skate 3** files: `default.xex` with the complete `data` folder beside it. PS3 files are not supported. Game files are not included or downloaded.
- Microsoft **.NET 8 x64 runtime**: https://dotnet.microsoft.com/en-us/download/dotnet/8.0
- Python 3.11 or later with NumPy. Setup checks PATH, registered Python installations, the Python launcher, and Codex's bundled Python, skipping Microsoft Store shortcuts. It offers a file picker if needed. Install Python from https://www.python.org/downloads/windows/ if none is available. If NumPy is missing, setup prints the install command for the selected Python.
- Internet access during setup to download the pinned upstream converter and vgmstream decoder. Their archive hashes are checked.
- Plenty of free disk space. The full city extraction can use tens of GB and take a long time; keep the setup console open.

## Install

1. Extract this entire folder to a writable location. Close GTA IV.
2. Run **Setup.cmd**. Choose `GTAIV.exe`, then your Skate 3 `default.xex`.
3. Setup converts your Skate assets and board sounds, extracts your GTA map, and builds grind candidates locally. It installs the mod only after conversion succeeds. Windows may request permission if the game is in Program Files; run Setup.cmd as administrator when needed.
4. Launch GTA IV using your existing compatible ASI loader. **F10** toggles Skate mode. **F9** toggles grind candidate lines. A line is a candidate, not a guarantee that every approach will grind successfully.

The engine begins loading automatically once the game world is ready. The ready notification is intended to be an in-game phone text, but the phone text currently does not work. A first load can take time.

Existing files replaced by setup are backed up under `GTAIV/Skate3Rust/backups/public-setup-<date>`. Saves are not modified. To disable the mod, close GTA IV and run **Disable.cmd**, then select GTAIV.exe. To restore an earlier mod version, copy its backed-up files to their original locations while the game is closed.

## Troubleshooting and feedback

- Setup logs and generated intermediate files: `%LOCALAPPDATA%/GTAIV-Skate/setup-<id>/setup.log`.
- Runtime log: `skate3rust_passthrough.log` beside GTAIV.exe. Logs can contain personal installation paths; review before sharing.
- Report the game version, mod version, a short clip, and the matching runtime log. Include the time in the clip where the issue occurs.
- Do not run multiple skating mods or install this alongside another version of this ASI.
- Clothes and DLC players use the game's current native player mesh. The legacy preconverted Niko mesh is not included.
