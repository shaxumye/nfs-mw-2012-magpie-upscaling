# NFS Most Wanted (2012) - 720p to 1080p with Magpie

This repository contains a Magpie scaling-mode preset and the settings I use as a starting point for running Need for Speed: Most Wanted (2012) at 1280x720 on a 1920x1080 display.

The game renders at 720p. Magpie captures the game window and scales it to the display. It is not native 1080p rendering.

## What is included

```text
nfs-mw-2012-magpie-upscaling/
├── README.md
├── LICENSE
├── .gitignore
├── magpie/
│   └── ScaleModels-NFS-Additions.json
└── settings/
    └── game-settings.txt
```

`ScaleModels-NFS-Additions.json` contains three scaling modes:
- **NFS FSR** - FSR upscaling with a moderate sharpening pass.
- **NFS Lanczos** - Lanczos scaling with light sharpening.
- **NFS Linear** - a lightweight fallback.

These are Magpie scaling modes, not a complete Magpie settings file or a per-game profile. Magpie's hotkeys and capture options are still set in the app.

## Requirements

- Windows 10 or Windows 11
- Need for Speed: Most Wanted (2012)
- [Magpie](https://github.com/Blinue/Magpie/releases)

## Install the scaling modes

1. Download and install Magpie from its official releases page.
2. Close Magpie completely.
3. Open the folder containing `Magpie.exe`.
4. Find `ScaleModels.json`.
   - If it does not exist, start Magpie once and close it so Magpie can generate its default file.
5. Make a backup copy of `ScaleModels.json` before editing it.
6. Open `ScaleModels.json` and `magpie/ScaleModels-NFS-Additions.json` in a text editor.
7. Copy the three objects from `ScaleModels-NFS-Additions.json` into the main `ScaleModels.json` array. Add a comma between the existing last object and the first new object. Do not add a second pair of outer square brackets.
8. Save the file and start Magpie again.
9. The three NFS modes should appear in the scaling-mode list.

If you only want these three modes, you can use the additions file as `ScaleModels.json`, but this replaces Magpie's existing mode list. Back up the original first.

## Game and display setup

Set Windows to 1920x1080, then set the game to:

| Setting | Value |
|---|---|
| Resolution | 1280x720 |
| Aspect ratio | 16:9 |
| Display mode | Windowed |
| Graphics quality | Start with Low; adjust if performance allows |

If the game does not offer a windowed option in its menu, check its launcher or in-game display settings before trying third-party forcing tools.

## Run the game with Magpie

1. Start Magpie.
2. Launch the game at 1280x720 in windowed mode.
3. Select `NFS FSR` in Magpie. If it looks too sharp or costs too much performance, try `NFS Lanczos` or `NFS Linear`.
4. Set or check Magpie's scaling shortcut in Magpie settings.
5. Focus the game window and activate scaling with the shortcut.
6. Use the shortcut again or Magpie's stop control to exit scaling.

With a 16:9 1280x720 game window on a 1920x1080 display, fitting the image to the screen produces a 1.5x scale in both directions.

## Which mode should I use?

| Mode | Use it when |
|---|---|
| NFS FSR | First one to try for a balance of detail and sharpness |
| NFS Lanczos | FSR is too heavy or you prefer a conventional filter |
| NFS Linear | You want a simple, lightweight fallback |

Scaling performance depends on the GPU and capture method. Magpie uses GPU resources too, so this does not guarantee a higher frame rate on every PC.

## Troubleshooting

**The NFS modes do not appear**
- Check that the file is named `ScaleModels.json` in the same folder as `Magpie.exe`.
- Confirm the new objects were added inside the existing JSON array.
- Check for missing commas or brackets.
- Restart Magpie after editing.

**The shortcut does nothing**
- Check the shortcut shown in Magpie's own settings.
- Make sure the game window is focused.
- If one app is running as administrator, try running the other at the same privilege level.

**The image is stretched or cropped**
- Confirm the game is 1280x720 and Windows is 1920x1080.
- Keep the game at 16:9.
- Check Magpie's scaling/capture options.

**Performance is worse**
- Try `NFS Linear` or `NFS Lanczos`.
- Close overlays and other GPU-heavy applications.
- Lower the game's graphics settings.
- Compare frame rate with Magpie off and on; scaling adds its own workload.

## How the scaling preset works

Magpie's scaling configuration uses an array of scaling modes, each made from effects applied in sequence. The `scale` value `[-1, -1]` tells supported effects to use the largest ratio that fits the available screen area. With a 16:9 720p source and a 16:9 1080p target, that is 1.5x.

See Magpie's documentation:
- [Magpie repository and releases](https://github.com/Blinue/Magpie)
- [Customizing scaling configurations](https://github.com/Blinue/Magpie/wiki/Customizing_Scaling_Configurations)

## Notes

This repository only contains the preset and setup instructions. It does not include Magpie, the game, game executables, or copyrighted game assets.
