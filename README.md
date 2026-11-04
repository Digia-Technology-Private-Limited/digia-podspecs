# Digia Engage CocoaPods specs

This is the CocoaPods spec repo for the Digia Engage iOS SDK and its CEP plugins. CocoaPods
trunk becomes read-only on 2026-12-02, so new Digia Engage pod versions are published here.

## Use it in a Podfile

Add both sources at the top of your `Podfile`. Keep this order: Digia first, then the CocoaPods
CDN for every other pod.

```ruby
source 'https://github.com/Digia-Technology-Private-Limited/digia-podspecs.git'
source 'https://cdn.cocoapods.org/'
```

Then run `pod install`. To pick up a newer version later, run `pod repo update` and then
`pod update DigiaEngage`.

### React Native (Expo)

Expo regenerates the `Podfile` on every prebuild, so add the `@digia-engage/core` config plugin
instead of editing it by hand:

```json
{ "expo": { "plugins": ["@digia-engage/core"] } }
```

### React Native (bare)

Add the two `source` lines above to `ios/Podfile`.

## Pods

| Pod | What it is |
|---|---|
| `DigiaEngage` | Core SDK (binary XCFramework) |
| `DigiaEngageCleverTap` | CleverTap plugin |
| `DigiaEngageWebEngage` | WebEngage plugin |
| `DigiaMoEngage` | MoEngage plugin |

This repo contains every published version, including those released before the move, so a
pinned older version still resolves.

## Publishing

Each SDK repo's release script publishes here with `pod repo push digia`. Don't edit specs by
hand.
