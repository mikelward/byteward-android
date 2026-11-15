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

The horizontal logo uses `@color/byteward_logo` (`app/src/main/res/values*/byteward_colors.xml`),
which is black on the light theme and white on the dark one.

All Byteward resources live in the `:app` module, which overrides the `:ui`
module's resources of the same name when they are merged. The `:ui` module
keeps upstream's files untouched (so upstream merges don't conflict, and the
Authenticator app, which also uses `:ui`, keeps Bitwarden's branding). That
includes `app/src/main/res/values*/byteward_strings*.xml`, which hold the
Byteward wording for the `:ui` strings where the app refers to itself.
