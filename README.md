# Family Nest — privacy policy and version policy (GitHub Pages)

Published from the public repo `novaware-studio/family-nest-privacy-policy`:

- Privacy policy: https://novaware-studio.github.io/family-nest-privacy-policy/
  (Play Console → Store listing and Data safety → Privacy policy URL)
- Version policy: https://novaware-studio.github.io/family-nest-privacy-policy/app-version.json

This folder is the source; copy changes to that repo and push (Pages
redeploys automatically). Update "Last updated" in `index.html` whenever the
policy changes.

## Forcing or recommending an update

`app-version.json`:

```json
{ "android": { "minimum": "0.9.0", "recommended": "0.9.2" } }
```

- **minimum** — installed versions below it are blocked with an "Update
  required" screen until the user updates from Google Play.
- **recommended** — versions below it get a dismissible "New version
  available" prompt; "Later" hides it until a newer recommended version is
  published.

Versions compare as `X.Y.Z` (the `+build` part is ignored). `0.0.0` means
"no requirement". The app checks at launch and when it comes back to the
foreground (at most every 30 minutes). Offline or any error means no policy,
so only a successful check can ever block anyone. Only raise `minimum` after
the new version is live on Google Play for everyone, or users get stuck.

See `lib/services/version_check_service.dart`.
