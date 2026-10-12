# TreeMapView framework (Apple Silicon build)

Cocoa framework that draws cushion treemaps, used by [Disk Inventory X](https://github.com/letzzar/disk-inventory-x).

**This is the original framework by Tjark Derlien**, unchanged except for the minimum needed to build
it on current macOS / Xcode for Apple Silicon:

  * deployment target macOS 12.0, universal arm64 + x86_64 build;
  * shift key detection through `NSEvent` instead of an OmniAppKit hook;
  * deprecated color space and compositing APIs replaced by their current equivalents;
  * `NSViewToolTipOwner` conformance, current header search settings.

See the commit history for the exact patch. Original repository: https://gitlab.com/tderlien/treemapview-framework

## License notice

The original repository does not state a license: the sources only say
"Copyright Tjark Derlien. All rights reserved.". The framework is a component of Disk Inventory X,
which its author publishes under the **GNU General Public License v3**, so we believe the license was
simply forgotten here, and this fork is distributed on the assumption that the same GPL v3 terms apply.

**If the author decides to apply a different, restrictive license to TreeMapView, this repository will be
taken down and the treemap view will be rewritten from scratch** for Disk Inventory X.
The author can reach us through the issues of this repository or of
[letzzar/disk-inventory-x](https://github.com/letzzar/disk-inventory-x).

## Building

```sh
xcodebuild -project TreeMapView.xcodeproj -configuration Release ARCHS="arm64 x86_64" ONLY_ACTIVE_ARCH=NO
```

Disk Inventory X builds it automatically through its Xcode workspace (both repositories side by side).

## Credits

  * TreeMapView: © 2003-2019 Tjark Derlien
  * Apple Silicon build: © 2026 letzzar and Claude (Anthropic)
