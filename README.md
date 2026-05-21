<h1 align="center">
  <br>
  <a href="https://hypercall.net"><img src="https://i.imgur.com/9vQOK3e.png" alt="logo" width="200"></a>
  <br>
  Gepard Bypass
  <br>
</h1>

<h4 align="center">Research code for understanding legacy Gepard anti-cheat hooks.</h4>

## Project status (as of May 21, 2026)

This repository is a legacy Visual Studio C++ project that targets Win32/x64 and uses inline assembly and API detours.

### Up-to-date check

- The bundled `detours.h` is **Microsoft Detours 3.0 Build 316**.
- The current upstream Detours release is **4.0.1** (GitHub releases page).
- Result: this repository is **not fully up to date** with upstream Detours.

## What this code does

At a high level, the loader:

- snapshots original bytes of selected APIs,
- loads `gepard_o.dll`,
- patches checks that are hard-coded at fixed offsets,
- hooks network send/recv paths,
- and logs packet buffers in a console.

## Build requirements

- Windows 10/11
- Visual Studio 2022 with **Desktop development with C++** workload
- MSVC **v143** toolset
- Windows SDK 10.0+

## Building

1. Open `Gepard.sln` in Visual Studio 2022.
2. Choose `Debug|Win32`, `Release|Win32`, `Debug|x64`, or `Release|x64`.
3. Build the `Gepard` project.

## Notes

- This project contains many hard-coded offsets tied to a specific target binary layout.
- If target binaries change, offsets and hooks must be re-validated before use.
- This repository is provided for reverse-engineering and defensive research discussion.

## License

MIT.
