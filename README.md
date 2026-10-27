# Eon

DOWNLOAD: https://github.com/TheEonProject/eon/releases/latest/download/welcome-to-eon.exe


A Minecraft: Java Edition launcher built with Electron.

- Instances with their own name, icon, loader (Vanilla, Fabric, NeoForge, Forge, Quilt), game version (1.17 to the newest 26.x, plus 1.12.2 and 1.8.9) and loader version.
- Discover: modpacks, mods, resource packs, data packs, shaders and servers from Modrinth and CurseForge.
- Instance page with Content, Files, Worlds (and saved servers) and Logs.
- Skins, capes, several Microsoft accounts, duplicate and transfer between instances, import from other launchers.
- Java is downloaded from Mojang automatically for each game version.
- Updates itself (installer version).

## Build

Needs Node.js 18+ on Windows. Double-click `build-windows.bat`, or:

```bat
npm install
node node_modules\electron\install.js
npm run dist
```

Output in `dist\`: `Eon-Setup-<version>.exe`, `Eon-Portable-<version>.exe`, and `latest.yml`.

## Publishing updates

Eon checks the URL in `package.json` → `build.publish[0].url` for a `latest.yml` file. It points at the latest release of the public repo https://github.com/TheEonProject/eon:

```
https://github.com/TheEonProject/eon/releases/latest/download
```

1. Raise `"version"` in `package.json` (for example 1.1.0 → 1.1.1) and run the build.
2. Create a GitHub release tagged `v<version>` (not a pre-release) and upload `Eon-Setup-<version>.exe`, `Eon-Setup-<version>.exe.blockmap` and `latest.yml` from `dist\`.

Installed copies find the update within a few hours (or straight away from Settings → Updates), download it in the background and install it when the user clicks **Restart to update**. Instances, worlds and accounts are kept. The portable `.exe` can't update itself.

## Notes

- Game data lives in `%APPDATA%\.eon` (changeable in Settings → Resources). Data from Crowned Client (`%APPDATA%\.crowned`) is moved over automatically on first start.
- CurseForge browsing needs a free API key from console.curseforge.com, pasted in Settings → Features.
- Not affiliated with Mojang or Microsoft.
