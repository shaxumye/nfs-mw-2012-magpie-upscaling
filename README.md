# NFS Most Wanted (2012) - Magpie Upscaling

A setup for running Need for Speed: Most Wanted (2012) at 1280x720 and scaling the game window to fit a 1920x1080 display with Magpie.

The game keeps rendering at 720p. Magpie enlarges the window to the monitor resolution.

## Target settings

| Setting | Value |
|---|---|
| Game resolution | 1280x720 |
| Monitor resolution | 1920x1080 |
| Scaling factor | 1.5x |
| Aspect ratio | 16:9 |
| Scaling software | Magpie |
| Scaling mode | FSR (try another mode if needed) |
| Game display mode | Windowed |

## Requirements

- Need for Speed: Most Wanted (2012)
- Windows 10 or Windows 11
- [Magpie](https://github.com/Blinue/Magpie)

Get Magpie from its [releases page](https://github.com/Blinue/Magpie/releases).

## Setup

1. Set the Windows desktop resolution to 1920x1080.
2. Open the game and set its resolution to 1280x720.
3. Set the game to windowed mode.
4. Open Magpie and choose FSR in its scaling settings. If the result is too soft or performance is poor, try another available scaling mode.
5. Create a Magpie profile for the game if you want to keep the settings together.
6. Check Magpie's settings for the scaling shortcut and set one that does not conflict with another app.
7. Run the game, focus its window and activate Magpie scaling.

To stop scaling, use Magpie's shortcut again or its stop control.

## Files

- `settings/game-settings.txt` contains the target values for manual setup.
- Magpie profiles and shortcuts are configured in Magpie itself.

## Notes

- This does not change the game's internal resolution to 1080p. It renders at 1280x720 and scales the image to 1920x1080.
- 720p contains 921,600 pixels; 1080p contains 2,073,600 pixels.
- Upscaling can reduce the game's rendering workload compared with native 1080p, but Magpie also uses GPU resources. FPS gains are not guaranteed.
- Windowed mode is recommended. If the game only runs properly in exclusive fullscreen, this method may not work as expected.
- The exact Magpie options and profile interface can vary by version.

## Troubleshooting

**The shortcut does nothing**
- Check the shortcut shown in Magpie's settings.
- Make sure the game window is focused.
- If the game and Magpie run with different permissions, try running them at the same privilege level.

**The image does not fill the screen**
- Confirm the Windows desktop is set to 1920x1080.
- Confirm the game window is 1280x720 and uses a 16:9 aspect ratio.
- Try another scaling mode in Magpie.

**Performance drops**
- Try a lighter scaling mode.
- Close overlays and other GPU-heavy applications.
- Lower the game's graphics settings.

## Credits

[Magpie](https://github.com/Blinue/Magpie) is a separate open-source project. This repository is a setup guide and does not include Magpie or any game files.
