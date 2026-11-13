# openFA Preview

**Public preview builds and community feedback for openFA.**

openFA is a reconstruction of the 1996 strategy game **Fragile Allegiance**, focused on reproducing the behavior and experience of the original game on modern systems.

The project supports and preserves *Fragile Allegiance*. It is intended as a companion to the original game, not a competing game or a replacement for owning it.

## About this repository

This repository is the public preview area for openFA.

It is used to:

- publish development and nightly builds,
- collect bug reports,
- collect reports about differences from the original *Fragile Allegiance*,
- collect ideas for mods and improvements,
- gather feedback from people testing the current implementation.

The source repository is currently private while the initial reconstruction milestones are being completed. The project is intended to be made public afterwards.

## Download

Preview builds are available from the **[Releases](https://github.com/ender-dev-pl/openfa-preview/releases)** section of this repository. Open a release and expand **Assets** to download a package for your platform:

| Platform | Package |
| --- | --- |
| Windows x64 | `OpenFA-<version>-win-x64-self-contained.zip` |
| Linux x64 | `OpenFA-<version>-linux-x64-self-contained.tar.gz` |
| macOS Apple Silicon (ARM64) | `OpenFA-<version>-osx-arm64-self-contained.tar.gz` |
| Android | The release's `.apk` file |

Desktop self-contained packages include the .NET runtime; a separate .NET installation is not required. Available platforms vary between older releases. Download the application package, rather than GitHub's automatically generated **Source code** archives.

These builds represent the current development state of openFA. They are provided for testing and may contain:

- incomplete features,
- known and unknown bugs,
- regressions,
- partially reconstructed game mechanics,
- changes that break compatibility with previous preview builds or save files.

There is no guarantee that a particular nightly build will be playable from start to finish.

## Original game files

openFA does **not** distribute the original *Fragile Allegiance* game assets.

Owning a legally obtained copy of the original game remains a premise of this project. Configure openFA to use that installation for the full *Fragile Allegiance* experience.

The original files provide Classic graphics and the original audio. openFA does not include the original sounds, and there are no plans to create a separate replacement set of the sounds used in *Fragile Allegiance*. A legally obtained release, such as the GOG version, can supply these files.

OpenFA3D supplies an alternative 3D presentation and can start without importing the original files. This does not provide the original soundscape or change the project's purpose: supporting the original game and its owners.

Use the installed game directory containing `FRAGILE.EXE` and data folders such as `_MS` and `_TEXT`. Keep the directory structure intact; the installer alone is not the game data.

## How to run

Extract the complete desktop archive into a writable folder and keep its files together, including the `.ofapkg` packages. Run the first-run configuration once for a fresh installation; existing configurations do not need to be recreated for every update.

### Windows x64

1. Extract the Windows ZIP.
2. Open PowerShell in the extracted folder and run:

   ```powershell
   powershell -NoProfile -ExecutionPolicy Bypass -File .\First-Run.ps1
   ```

3. Select your installed *Fragile Allegiance* directory when prompted. Alternatively, supply it explicitly:

   ```powershell
   powershell -NoProfile -ExecutionPolicy Bypass -File .\First-Run.ps1 -LegacyInstallationDirectory "C:\Games\Fragile Allegiance"
   ```

4. Launch `OpenFA.Client.exe` from the extracted folder. `OpenFA.PackageEditor.exe` is the separate package-editing tool.

The setup script writes `openfa.json` beside the game executable. The execution-policy option above applies only to that PowerShell process.

### Linux x64

1. Extract the Linux tar.gz, preserving executable permissions.
2. Open a terminal in the extracted folder and configure the original installation:

   ```sh
   ./First-Run.sh "/path/to/Fragile Allegiance"
   ```

   Without an argument, the script asks for the directory interactively.

3. Start the game:

   ```sh
   ./OpenFA.Client
   ```

Configuration is stored in `openfa.json` in the extracted folder. The included `OpenFA.PackageEditor` executable starts the package editor. The original game's DOS/Windows data files are used on Linux too; a native Linux edition of *Fragile Allegiance* is not required.

### macOS Apple Silicon

The macOS package targets Apple Silicon (M1 or newer) and macOS 11 or newer; it is not an Intel Mac package.

1. Extract the complete macOS tar.gz.
2. Open Terminal in the extracted folder and run:

   ```sh
   ./First-Run.command "/path/to/Fragile Allegiance"
   ```

   Without an argument, the script asks for the directory interactively.

3. Open `OpenFA.app`. `OpenFA.PackageEditor.app` is included separately.

Configuration is stored at `~/Library/Application Support/OpenFA/openfa.json`. The original game's DOS/Windows data files are used on macOS too.

Current macOS preview packages are unsigned and not notarized. If macOS blocks a downloaded preview you trust, use its per-app **Open Anyway** option in System Settings. Do not disable Gatekeeper globally.

### Android

1. Install the `.apk` from the chosen GitHub release, or install through Google Play if you have access to the applicable testing track. An `.aab` is a Play publishing bundle, not a directly installable APK.
2. When installing an APK manually, Android may ask you to allow installation from the browser or file manager used to open it.
3. Launch openFA. To import original files, copy the installed *Fragile Allegiance* directory or a ZIP containing it to the phone, keeping the game directory structure intact.
4. Open **Game Options → Misc**, select **Graphics Assets: Legacy**, then choose **Import Game Files** and select the folder or ZIP using Android's file picker.
5. Select the graphics and audio sets you want. Choose **Audio Assets: Legacy** for the original audio. You can use that audio with **Graphics Assets: OpenFA3D** as well as Classic graphics.
6. Close and reopen the app after changing asset sets, as indicated by **Restart to apply**.

Android releases are also distributed through Google Play. Available versions depend on the testing track you have access to and may differ from the GitHub downloads.

### Choosing graphics and audio

In **Game Options → Misc**, **Graphics Assets** selects OpenFA3D or the legacy Classic presentation. **Audio Assets** is a separate selection. Importing or configuring the original installation lets you retain its soundscape while using the 3D renderer. Original sounds are unavailable until the original files have been supplied.

## Release history

The following versions have been published in this repository. Each link opens its downloads and release notes; the date is the GitHub publication date in UTC.

| Version | Published | Distribution |
| --- | --- | --- |
| [0.4.2](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.4.2-dev) | 2026-11-13 | Windows x64, Linux x64, macOS ARM64, Android APK |
| [0.4.1](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.4.1-dev) | 2026-11-07 | Windows x64, Linux x64, macOS ARM64, Android APK |
| [0.3.0](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.3.0-dev) | 2026-11-03 | See release assets |
| [0.751.9](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.751.9-dev) | 2026-10-21 | Historical preview; see release assets |
| [0.740.1](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.740.1-dev) | 2026-10-18 | Historical preview; see release assets |
| [0.658.6](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.658.6-dev) | 2026-10-07 | Historical preview; see release assets |
| [0.597.22](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.597.22-dev) | 2026-09-23 | Historical preview; see release assets |
| [0.525.2](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.525.2-dev) | 2026-09-15 | Historical preview; see release assets |
| [0.495.2](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.495.2-dev) | 2026-09-13 | Historical preview; see release assets |
| [0.478.1](https://github.com/ender-dev-pl/openfa-preview/releases/tag/0.478.1-dev) | 2026-09-10 | Historical preview; see release assets |

The historical `0.xxx.x` previews used an earlier version-numbering scheme and predate the current `0.3.x` and `0.4.x` release lines. All listed GitHub releases are previews.

**0.4.2** has also been published to Google Play **internal testing**. See [all GitHub releases](https://github.com/ender-dev-pl/openfa-preview/releases) for downloadable packages and release notes.

## Documentation

The project description, reconstruction notes, technical findings, and development log are available in the **[openFA documentation](https://ender-dev-pl.github.io/openfa-docs/)**.

## Reporting problems

Feedback is very welcome.

Please use the **Issues** section of this repository to report:

- bugs and crashes,
- incorrect game behavior,
- differences between openFA and the original *Fragile Allegiance*,
- problems running the game,
- other reproducible problems found while testing a preview build.

When reporting a problem, please include the preview build version, operating system or Android device, graphics renderer (OpenFA3D or Classic), active extension packages, and enough information to reproduce it. For crashes, attach the relevant log if available. Do not upload the original game's copyrighted files.

For differences from the original game, screenshots, recordings, save files, or a description of how *Fragile Allegiance* behaves in the same situation can be especially useful.

## Suggesting mods and improvements

Use the **[Mod or improvement idea form](https://github.com/ender-dev-pl/openfa-preview/issues/new?template=mod-improvement-idea.yml)** to propose new mods, features, or improvements. Describe the motivation, how the idea would work, and whether it preserves original gameplay or should be optional.

Please submit one idea per issue and search existing suggestions first.

## Before opening an issue

openFA is still under active development.

Some areas may be incomplete or not yet implemented. Search existing issues first and add reproducible evidence to an existing report where appropriate. If a missing feature or behavior is not already tracked, it can still be reported; explain what you expected and, where relevant, how the original game behaves.

The preview builds exist primarily to test functionality that has already been reconstructed and to help identify cases where openFA behaves differently from the original game.

## Project status

openFA is an independent preservation and reconstruction project and is not affiliated with the original developers or publishers of *Fragile Allegiance*.

Development is ongoing.

The current goal is to reproduce the original game's mechanics and behavior as faithfully as practical while making it possible to run and maintain the game on modern systems.

---

*Fragile Allegiance* and its original assets belong to their respective rights holders. No original game assets are distributed through this repository.
