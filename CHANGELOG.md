# LumixCamera

## 1.2.1.0
- **Colour live view.** The live-view JPEG from the camera is re-mosaiced into a synthetic RGGB
  Bayer frame and handed to N.I.N.A. as bayered, so its normal debayer step produces a colour
  preview instead of the previous 16-bit grayscale conversion.
- The **Prefer JPEG** capture fallback uses the same path, so JPEG captures are also shown in colour.
- Fixed the release workflow: package the renamed `LumixPlugin.dll` (the 1.2.0.0 build packaged the
  old assembly name and failed).

## 1.2.0.0
- Optional **LUMIX Tether extended mode**: when enabled in the plugin options the driver
  loads the DLL from a local install of Panasonic's free LUMIX Tether application (never
  bundled) to unlock features the public SDK does not expose.
- Extended mode enables **BULB / exposures beyond the 60 s public-SDK cap**, RAW/JPEG image-quality
  selection, battery information, and live camera-state reporting.
- **Sub-second and full-range shutter speeds**: exposures snap to the nearest supported speed so
  N.I.N.A.'s Flat Wizard converges (previously non-listed and sub-second times failed or stuck).
- **Camera mode** is read (including the C1-C3 custom presets); the driver warns — but never
  blocks — when the dial is not in a manual-capable mode.
- **Save destination** option: SD card, PC (cardless), or both.
- Real capture-completion event replaces the previous SD-card-file workaround; fixes the
  first-capture error.
- **Prefer JPEG** option: forces JPEG capture as a workaround for cameras whose RAW (.RW2)
  N.I.N.A. cannot decode (e.g. GH7).
- Standard (public-SDK) mode is unchanged and remains the default; the public DLL now deploys
  alongside the plugin assembly.

## 1.0.0.1
- Initial release