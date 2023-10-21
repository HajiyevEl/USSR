# Unity Splash Screen Remover

## Table of Contents

- [Announcement](#announcement)
- [Overview](#overview)
- [Requirements](#requirements)
- [Usages](#usages)
  - [Android](#android)
  - [iOS](#ios)
- [Supported Platforms](#supported-platforms)
- [Supported Unity Versions](#supported-unity-versions)
- [Contribute](#contribute)
- [Credits](#credits)
- [License](#license)
- [Disclaimer](#disclaimer)
- [FAQs](#faqs)

## Announcement

On the latest updated policy for Unity Runtime Fee on 22 September 2023 (<https://unity.com/pricing-updates>), one of the key updates is Unity has decided to make the splash screen optional. Starting with Unity 2024 LTS (currently referred to as the 2023 LTS) or later.

> ...and we will remove the requirement to use the Made with Unity splash screen (starting with the LTS version releasing in 2024, currently referred to as the 2023 LTS, or later).

If you developing a new game, you may want to switch to those Unity version.

## Overview

The Unity Splash Screen Remover (USSR) is a Command-Line Interface (CLI) tool designed to remove the Unity splash screen logo & [watermark](https://forum.unity.com/threads/i-am-using-personal-but-there-is-trial-version-water-mark-after-build.591610/#post-3975343) from Unity-built games.

The tool is an implementation of the guide available at <https://github.com/kiraio-moe/remove-unity-splash-screen>. By utilizing this tool, you can easily remove Unity splash screen logo from your games and keep your own logo displayed.

## Requirements

- [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0 ".NET 6.0 SDK") or [.NET 7.0 SDK](https://dotnet.microsoft.com/download/dotnet/7.0 ".NET 7.0 SDK")
- Splash screen `Draw Mode` have been set to `All Sequential` in `Player Settings`.

## Usages

- Download USSR from [Releases](https://github.com/kiraio-moe/USSR/releases) page.
- Run `USSR.exe` and follow the instructions.

### Android

- Make sure you already have [`JDK`](https://www.openlogic.com/openjdk-downloads?field_java_parent_version_target_id=416&field_operating_system_target_id=All&field_architecture_target_id=All&field_java_package_target_id=All "OpenJDK") & [`SDK`](https://androidsdkoffline.blogspot.com/p/all-android-sdk-latest-stable-versions.html) installed. In another word, you can build your game in Unity Editor.
- [Android Studio](https://developer.android.com/studio "Android Studio") installed. Make sure to set the `JDK` and `SDK` path to the one you used for Unity Editor.
- Follow these steps:

  - **Check** `Export Project` in `Build Settings` then export.
  - After exported, **remove** the splash screen at `<export_result>/unityLibrary/src/main/assets/bin/Data/`.
  - **Remove** the backup file (`*.bak`) generated by USSR or **move** to somewhere else outside of `<export_result>`.
  - **Import** the exported project to `Android Studio`.
  - **Build** the project.
  - If you want to upload your game to app store (e.g. Google Play Store), you can `sign` your game with `keystore` and build the project as app bundle (`.aab`).  
  I won't cover those steps here, because you can find them pretty much on the internet.

### iOS

> [!WARNING]
> This section may have some incorrect information. Feel free to create Issue/Pull Request if there's mistake.

- [Xcode](https://developer.apple.com/xcode/ "Xcode") installed.
- There's no fancy settings to be checked, just **Build** (export) the project.
- **Remove** the splash screen at `<export_result>/Data/`.
- **Remove** the backup file (`*.bak`) generated by USSR or **move** to somewhere else outside of `<export_result>`.
- **Open** `Unity-iPhone.xcodeproj` with Xcode, then proceed to build.  
  If you're an iOS developer, you know what to do next, right?

## Supported Platforms

USSR support the following platforms:

- PC, Mac, Linux Standalone (Support Default, LZ4 & LZ4HC compression)
- Android (Support Default, LZ4 & LZ4HC compression)
- iOS (Support Default, LZ4 & LZ4HC compression)
- WebGL (Support Default, Brotli & GZip compression)

## Supported Unity Versions

> [!IMPORTANT]
> Some minor Unity versions is not supported and can caused crash.

- Unity 5 ~ Unity 2023

## Contribute

If you found any bugs or have suggestions, feel free to make an Issue/Pull Request.

## Credits

- Special thanks to @nesrak1 for the @nesrak1/AssetsTools.NET library, which was instrumental in the development of this tool.
- @arti4ikmin for the guide on Android platform.

## License

This project is licensed under GNU GPL 3.0.

For more information about the GNU General Public License version 3.0 (GNU GPL 3.0), please refer to the official GNU website: <https://www.gnu.org/licenses/gpl-3.0.html>

## Disclaimer

By using this tool, you're intentionally violates the Unity End User License Agreement (EULA). Use the tool at your own risk (DWYOR - Do What You Own Risk).

## FAQs

**Q: Is using this tool safe?**  
A: Yes, the tool is designed to safely remove the Unity splash screen from your game without causing any harm.

**Q: Can I upload my game to game stores and not get banned?**  
A: Yes, you can upload your games to various game stores without facing any bans. However, it's important to note that by removing the Unity splash screen, you are violating the Unity EULA, and there is always a risk of potential consequences. Be aware of the risks before proceeding.

---

Please note that using this tool is at your own discretion and responsibility. Always make sure to backup your game files before using any third-party tools or modifying game assets.
