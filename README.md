# rawi-strings

Over-the-air (OTA) localization overrides for [Rawi](https://rawiapp.xyz) — served via jsDelivr, managed by **Rilyo**.

## Structure
```
rawi/manifest.json        # { appId, version, languages[], kill_switch, min_app_build, base }
rawi/v/<n>/<lang>.json    # immutable, flat canonicalKey -> value (only overridden keys)
```

`version: 0` is the safe initial state — the app runtime treats it as "no update" and uses bundled strings. Rilyo bumps the version and writes a new immutable `v/<n>/` on each publish, then purges the manifest from the CDN.

Contract: `ayahapp/docs/REMOTE_STRINGS_PLAN.md`. Do not hand-edit — publish from Rilyo.
