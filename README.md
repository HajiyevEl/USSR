# Unity Splash Screen Remover

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Usages](#usages)
- [Supported Platforms](#supported-platforms)
- [Supported Unity Versions](#supported-unity-versions)
- [Todo List](#todo-list)
- [Contribute](#contribute)
- [Credits](#credits)
- [License](#license)
- [Disclaimer](#disclaimer)
- [FAQs](#faqs)

## Overview

The Unity Splash Screen Remover is a Command-Line Interface (CLI) tool designed to remove the Unity splash screen logo from Unity-built games.

The tool is an implementation of the guide available at <https://github.com/kiraio-moe/remove-unity-splash-screen>. By utilizing this tool, you can easily remove Unity splash screen logo from your games and keep your own logo displayed.

## Requirements

- [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0 ".NET 6.0 SDK") or [.NET 7.0 SDK](https://dotnet.microsoft.com/download/dotnet/7.0 ".NET 7.0 SDK")
- Splash screen `Draw Mode` have been set to `All Sequential` in `Player Settings`.

## Usages

To use the tool, follow the steps below:

1. Download USSR from [Releases](https://github.com/kiraio-moe/USSR/releases) page.
2. There's many ways to use USSR. Choose which one you feel most comfortable with.

    - Drag and drop your game executable `(*.exe|*.x86|*.dmg|index.html)` to `USSR.exe`.
    - Drag and drop `globalgamemanagers` or `data.unity3d` file (_`WebGL.data` currently not supported_) to `USSR.exe`.
    - Execute USSR on CLI:

        ```bash
        USSR.exe <path/to/(*.exe|*.x86|*.x86_64|*.dmg|index.html|globalgamemanagers|data.unity3d|WebGL.data)>
        ```

3. For Android platform, there's extra work for it. You doesn't need to do **Decompile** and **Recompile** process as done in the [guide](https://github.com/kiraio-moe/remove-unity-splash-screen "remove-unity-splash-screen guide").

    - Make sure you already have [`JDK`](https://www.openlogic.com/openjdk-downloads?field_java_parent_version_target_id=416&field_operating_system_target_id=All&field_architecture_target_id=All&field_java_package_target_id=All "OpenJDK") & [`SDK`](https://androidsdkoffline.blogspot.com/p/all-android-sdk-latest-stable-versions.html) installed. In another word, you can build your game in Unity Editor.
    - [Android Studio](https://developer.android.com/studio "Android Studio") installed. Make sure to set the `JDK` and `SDK` path to the one you used for Unity Editor.
    - Follow these steps:

      - **Check** `Export Project` in `Build Settings` when you want to build.
      - After it has been exported, **remove** the splash screen by drag & drop `globalgamemanagers` or `data.unity3d` file in `<export_result>/unityLibrary/src/main/assets/bin/Data/` or from CLI:

        ```bash
        USSR.exe <path/to/<export_result>/unityLibrary/src/main/assets/bin/Data/(globalgamemanagers|data.unity3d)>
        ```

      - **Remove** the backup file (`*.bak`) generated by USSR or **move** to somewhere else outside of `<export_result>`.

      - After successfully removing the splash screen, **import** the project to `Android Studio`.
      - **Build** the project.
      - If you want to upload your game to app store (e.g. Google Play Store), you can `sign` your game with `keystore` and build the project as app bundle (`.aab`). I won't cover those steps here because you can find them pretty much on the internet.

## Supported Platforms

USSR support the following platforms:

- PC, Mac, Linux Standalone (Support Default, LZ4 & LZ4HC compression)
- Android (Support Default, LZ4 & LZ4HC compression)
- WebGL (Support Default, Brotli & GZip compression)

## Supported Unity Versions

- Unity 5 ~ Unity 2023

## Todo List

- ~~Add support for WebGL platform~~ ✔️
  - ~~Decompress WebGL.data~~ ✔️
  - ~~Compress back to WebGL.data~~ ✔️
  - ~~Support Brotli compression~~ ✔️
  - ~~Support GZip compression~~ ✔️
- ~~Support compressed build~~ ✔️
- ~~Add support for Android~~ ✔️
- Refactor code 🚧

## Contribute

If you found any bugs or have suggestions to make USSR more better, feel free to make an Issue. Pull Request even better.

## Credits

Special thanks to [nesrak1](https://github.com/nesrak1) for the [AssetsTools.NET](https://github.com/nesrak1/AssetsTools.NET "AssetsTools.NET") library, which was instrumental in the development of this tool.

- [arti4ikmin](https://youtube.com/@arti4ikmin "arti4ikmin on YouTube") for the instruction for Android platform.

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
