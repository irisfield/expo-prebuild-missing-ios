# `npx expo prebuild` crashes when app.config.js returns no `ios` field

This project has an `app.json` that contains an `ios` section and a function `app.config.js` that spreads `config` but returns no `ios` field.

## Steps

1. Run `npm install`.
2. Run `npx expo prebuild --platform ios --no-install`.
3. Press Enter at the bundle identifier prompt.

## Actual

Prebuild crashes with this error:

```
TypeError: Cannot read properties of undefined (reading 'bundleIdentifier')
```

After the crash, `app.json` has a new `ios.bundleIdentifier` value.

## Expected

Prebuild prints `Cannot automatically write to dynamic config at: app.config.js` and `app.json` stays unchanged.
