# Contributing

Thanks for taking a look at Netex iOS.

Please keep changes focused on the iOS companion app unless a shared issue has been reproduced separately in Netex or Three.js. Vendored files under `Resources/NetexAssets/threejs-devtools/` should stay isolated from app-specific edits; iOS-specific behavior belongs in Swift, panel code, or the chrome shims around those assets.

Before opening a pull request, run:

```sh
xcodegen generate
xcodebuild test -project NetexIOS.xcodeproj -scheme NetexIOS -destination 'platform=iOS Simulator,name=iPhone 17 Pro' CODE_SIGNING_ALLOWED=NO
node --check Resources/NetexAssets/panel.js
```

Do not commit personal signing values, provisioning profiles, device IDs, or local Xcode user data. For physical-device builds, use environment overrides with `Scripts/build_device.sh`.
