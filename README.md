# Focus Peaking for Canon EOS 6D Mark II

An experimental Magic Lantern fork exploring Live View focus peaking on the Canon EOS 6D Mark II (EOS 6D Mark II firmware 1.1.1).

This is community work based on [magiclantern_simplified](https://github.com/reticulatedpines/magiclantern_simplified). It is not an official Magic Lantern release and is not affiliated with Canon.

## Current status

Focus peaking has been observed working on a physical EOS 6D Mark II running firmware 1.1.1. A previous tested revision displayed peaking marks in Live View, and the camera owner reported faster photo saving after a performance change.

The latest source revision increases the density of the marks and adds a uniform translucent red option. That exact revision still needs to be rebuilt and checked on the camera, including its effect on photo saving. Treat this branch as experimental.

## Changes explored

- Reads a selectable candidate Live View buffer on the 6D Mark II.
- Adds denser Live View marks intended to form more connected contours.
- Keeps peaking marks monochrome; the user can choose a fixed color, including translucent red.
- Skips the full-resolution playback scan on the 6D Mark II to reduce unnecessary work after a shot.

Focus peaking responds to local image contrast and sharpness. It is a visual aid, not a guarantee that a marked area is in focus.

## Build

Build from Ubuntu or WSL with the Magic Lantern toolchain installed:

```bash
cd platform/6D2.111
make -j"$(nproc)"
```

The package is generated at:

```text
platform/6D2.111/build/magiclantern.zip
```

## Camera setup

1. Start Live View.
2. Enable Global Draw and Focus Peak in the Magic Lantern Overlay menu.
3. Select one of the fixed colors, or **Soft red** for a uniform translucent red overlay.
4. Adjust Filter bias and Threshold to taste. A higher threshold target displays more marks; lower it if too many edges are highlighted.
5. If the build exposes **LV buffer source**, select the source that has been confirmed to work on your camera.

## Test evidence

Add representative camera photos to the `images/` folder next to this README, then link them here. Include examples of the overlay and, if possible, a comparison of photo-saving time before and after the performance change. Avoid posting personal or location-sensitive images.

## Scope and reporting issues

Please include the exact camera model, Canon firmware version, Magic Lantern commit or build, selected LV buffer source, Focus Peak settings, and whether the issue happened in Live View or during photo review. Reports from other cameras should identify their exact model and firmware.

## License

Magic Lantern is licensed under GPL-2.0. Keep the upstream license and copyright notices when redistributing this fork. See the repository's `COPYING` file.
