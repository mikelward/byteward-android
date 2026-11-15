# Byteward brand assets

The Android launcher icons and logo drawables are generated from code:

- `marks.mjs`, `wordmark.json`, `SpaceGrotesk-OFL.txt`: copies of the files
  in byteward-clients' `scripts/byteward`, where the portcullis mark and the
  "byteward" wordmark are designed. Copy them across when they change.
- `generate-icons.mjs`: writes the adaptive launcher icon layers, splash icon,
  app icon, small tinted icon and horizontal logo as vector drawables.

```sh
node scripts/byteward/generate-icons.mjs
```

The horizontal logo uses `@color/byteward_logo` (`ui/src/main/res/values*/byteward_colors.xml`),
which is black on the light theme and white on the dark one.
