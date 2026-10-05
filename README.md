# dictate-releases

This repository holds Codictate release artifacts for the `jmulla/dictate` fork, and nothing else. There is no source code here.

The fork's source repository is private. Codictate's in-app updater (Electrobun) downloads `{channel}-{os}-{arch}-update.json` and its archives anonymously from:

```
https://github.com/jmulla/dictate-releases/releases/latest/download
```

GitHub only serves release assets without a token from a public repository, so releases are published here.

That URL always resolves to the latest stable release. After every publish, the release workflow copies the newest canary's `canary-*` updater assets (macOS and Windows) onto the latest stable release, so the one URL serves both channels.

**Bootstrap:** a canary release needs a stable release to ride on. Until the first stable release is published here, canary releases are refused before anything is built or tagged.

## Installing

Download from [Releases](https://github.com/jmulla/dictate-releases/releases):

- **macOS (Apple Silicon, macOS 13+):** `stable-macos-arm64-Codictate.dmg`
- **Windows (x64, Windows 10+):** `stable-windows-x64-Codictate-Setup.exe`

Full install steps live in `docs/INSTALL.md` in the source repository ([link](https://github.com/jmulla/dictate/blob/main/docs/INSTALL.md); it needs access to the private repo). The release process is in `docs/RELEASING.md`, under "Private source, public releases".

Fork builds without Apple signing credentials are unsigned and run only on the Mac that built them.
