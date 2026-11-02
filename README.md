# Resolve Fusion Fuses: Tint & Color Vibrance

Two free, GPU-accelerated Fuses for DaVinci Resolve's Fusion page (and Fusion Studio) that make quick, flexible colorizing easy, which is especially handy for smoke, fire, glows and other luminance-based elements.

| Tool | What it does |
|---|---|
| **Tint** | Maps image luminance onto a Black → White color pair. |
| **Color Vibrance** | Colorizes footage along a Black → *Color* → White ramp, so shadows stay dark and highlights burn out to white. |

Stack them (Tint → Color Vibrance) for a classic colorize look.

## Inspiration

These tools are **inspired by** the Tint effect in Adobe After Effects and the Color Vibrance plugin by Video Copilot. They are independent, from-scratch implementations written for Fusion. They contain no code from those products and are not affiliated with, endorsed by, or sponsored by Adobe or Video Copilot. Product names belong to their respective owners.

The math is an approximation of the look, not a copy of either product's algorithm, so results may differ slightly.

## Install

1. Download `Tint.fuse` and `ColorVibrance.fuse`.
2. Copy them into your Fuses folder:
   - **Windows:** `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Fusion\Fuses`
   - **macOS:** `~/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Fuses`
   - **Linux:** `~/.local/share/DaVinciResolve/Fusion/Fuses`
3. Restart DaVinci Resolve.
4. On the Fusion page, add the tools from **Effects Library → Fuses → Color** (or press `Shift+Space` and search "Tint" or "Color Vibrance").

Tested on DaVinci Resolve Studio 21.1.2.

## Controls

### Tint
- **Map Black To**: color that black maps to.
- **Map White To**: color that white maps to.
- **Amount to Tint**: blend between the original (0) and the tinted result (1).
- **Swap Colors**: swaps the black and white colors.

### Color Vibrance
- **Color**: the midtone color of the ramp.
- **Vibrance**: saturation of the colorized result.
- **Preserve Luminance**: how closely the result keeps the source's brightness.
- **Brightness**: overall output multiplier.
- **Gamma**: shifts where the color sits between shadows and highlights.
- **Fill Empty BG**: composites the result over the colorized black, filling transparent areas and making the output opaque.
- **Invert**: flips the luminance before colorizing.
- **Matte Alpha**: *Off*, *Luminance*, or *Inverted Luminance*. Builds alpha from the result's brightness, so smoke or fire can sit directly over a plate without a separate key.
- **Alpha Boost**: strengthens the matte (active when Matte Alpha is on).

## Tips

- Very high **Vibrance** on saturated colors can push a channel below zero, which then clips. If the look gets harsh, lower Vibrance.
- The tools work in the image's current color space; they don't do any color management of their own.

## License

[MIT](LICENSE). Free for anyone to use, modify, redistribute, and sell, including inside other software packages. Attribution (keeping the copyright notice) is all that's required.
