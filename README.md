<p align="center">
  <img src="https://github.com/CinemaMod/mcef/assets/30220598/938896d7-2589-49df-8f82-29266c64dfb7" alt="MCEF Logo" style="width:66px;height:66px;">
</p>

# MCEF (Minecraft Chromium Embedded Framework)
MCEF is a mod and library for adding the Chromium web browser into Minecraft.

MCEF is based on java-cef (Java Chromium Embedded Framework), which is based on CEF (Chromium Embedded Framework), which is based on Chromium. It was originally created by montoyo. It was rewritten and currently maintained by the CinemaMod Group.

MCEF contains a downloader system for downloading the java-cef & CEF binaries required by the Chromium browser. This requires a connection to https://mcef-download.cinemamod.com.

Discussion: https://discord.gg/rNrh5kW8Ty

Current Chromium version: `116.0.5845.190`

## Supported Platforms
- Windows 10/11 (x86_64, arm64)*
- macOS 11 or greater (Intel, Apple Silicon)
- GNU Linux glibc 2.31 or greater (x86_64, arm64)**

*Some antivirus software may prevent MCEF from initializing. You may have to disable your antivirus or whitelist the mod files for MCEF to work properly.

**This mod will not work on Android.

## For Players
This is the source code for MCEF.

Download the mod for Fabric or Forge on either:
- CurseForge: https://www.curseforge.com/minecraft/mc-mods/mcef
- Modrinth: https://modrinth.com/mod/mcef

## For Modders
MCEF is LGPL, as long as your project doesn't modify or include MCEF source code, you can choose a different license. Read the full license in the LICENSE file in this directory.

### Using MCEF in Your Project
```
repositories {
    maven { url 'https://jitpack.io' }
}
```
#### Fabric
```
dependencies {
    modCompileOnly 'com.github.polvallverdu.MCEF-PolCinematics:mcef:{version or commit hash}'
    modRuntimeOnly 'com.github.polvallverdu.MCEF-PolCinematics:mcef-fabric:{version or commit hash}'
}
```
See the [mcef-fabric-example-mod](https://github.com/CinemaMod/mcef-fabric-example-mod) for a complete example Fabric project.

#### Forge
```
dependencies {
    compileOnly fg.deobf('com.github.polvallverdu.MCEF-PolCinematics:mcef:{version or commit hash}')
    runtimeOnly fg.deobf('com.github.polvallverdu.MCEF-PolCinematics:mcef-forge:{version or commit hash}')
}
```
### Building & Modifying MCEF
After cloning this repo, you will need to clone the java-cef git submodule. There is a gradle task for this: `./gradlew cloneJcef`.

To run the Fabric client: `./gradlew fabricClient`
To run the Forge client: `./gradlew forgeClient`

In-game, there is a demo browser if you press F10 after you're loaded into a world (the demo browser only exists when you're running from a development environment).
