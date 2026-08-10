Light Host Reforge
---

English|[简体中文](readme_zh.md)

A fork of [LightHost](https://github.com/opencma/LightHost) with the following changes:

- Ported to JUCE8
- Added support for Waves plugins (tested with Waves V15)
- Added effect chain preset system
- Added plugin window toolbar
- Added Loopback audio device type, capable of capturing desktop audio into the effect chain (Windows only, no output support)
- Added MIDI input support for hosted instrument plugins
- Support for resizing plugin windows, partial HiDPI support
- Support for keeping plugin windows on top
- Added plugin bypass status display
- Added fade-in/fade-out transition when audio chain changes
- Added display of plugin latency and total chain latency
- Changed to CMake build system
- Added release builds for Windows x64, macOS Apple Silicon, and macOS Intel

Notes:

- VST2 hosting is currently disabled
- AU hosting is enabled on macOS; VST3 hosting is enabled on Windows and macOS
- Windows loopback capture remains Windows-only
- macOS release artifacts are currently unsigned and unnotarized

## Build

Windows (using VS2022 + vcpkg):

```bash
vcpkg install juce asiosdk
mkdir build
cd build
cmake -DCMAKE_TOOLCHAIN_FILE=path\to\vcpkg.cmake ..
MSBuild .\LightHostReforge.sln /p:Configuration=Release
```

macOS (using CMake + vcpkg):

```bash
vcpkg install juce
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release \
  -DCMAKE_TOOLCHAIN_FILE=path/to/vcpkg/scripts/buildsystems/vcpkg.cmake
cmake --build build --config Release
```

Pushing a tag matching `v*` runs the release workflow and publishes packaged Windows and macOS builds.

### Screenshot

![Light Host Reforge](Resources/LightHostReforge.png)

---

# Light Host

---

A simple VST/AU host for OS X, Windows, and Linux that sits in the menu/task bar.

### Features

See [#1](https://github.com/rolandoislas/LightHost/issues/1)

### Screenshot

![Light Host 1.2](http://i.imgur.com/UF9SWfC.jpg)
