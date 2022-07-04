# Google Maps Swift Package

## Notes
* This repository is a raw copy of https://github.com/vfn/GoogleMaps-SP/tree/5.0.0-M1
* Forking was not an option, I had to copy it since SPM do not support adding forked github repos to Xcode projects as swift packages... Thank you SPM...

# Original README content

## Requirements
* [iOS 10.0](https://wikipedia.org/wiki/IOS_10) or later.
* [Xcode 12.0](https://developer.apple.com/xcode) or later.

## Installation
- Add the following dependency to your project's `Package.swift`.

```swift
dependencies: [
    .package(url: "https://github.com/YAtechnologies/GoogleMaps-SP.git", .upToNextMinor(from: "5.0.0"))
]
```

### Known Issues
- If you use a Google Maps Swift package in an app with extensions, the build system incorrectly embeds the binary dependencies alongside the extension in the PlugIns directory, causing validation of the archived app to fail. (69834549) (FB8761306)

    **Workaround:** Add a scheme post-build action which removes the embedded binaries from the PlugIns directory after the build, e.g. `rm -rf "${TARGET_BUILD_DIR}/${TARGET_NAME}.app"/PlugIns/*.framework`.

## Sponsor
If you find this package useful please consider **[STARRING 🌟](https://github.com/YAtechnologies/GoogleMaps-SP/stargazers)** this repository.

## License
The **Google Maps iOS SDK** and **Google Places iOS SDK** libraries are the property of Google and are subject to *Google's Terms of Service*. See [LICENSE.google](https://github.com/YAtechnologies/GoogleMaps-SP/blob/main/LICENSE.google) for details.
