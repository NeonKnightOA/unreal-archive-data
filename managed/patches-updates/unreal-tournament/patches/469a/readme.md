# OldUnreal Patch for Unreal Tournament (99)

OldUnreal took over maintenance of the Unreal Tournament code base after reaching an agreement with [Epic Games](https://www.epicgames.com) in 2019.

Our patches fix hundreds of stability, security and performance problems in the game client, the server, and in Unreal Editor. They also add support for modern platforms and operating systems (such as macOS Catalina), and add new 3d renderers, audio drivers and minor features (such as raw input and high-resolution font/GUI scaling) to better leverage the capabilities of modern gaming systems.

Patch releases hosted here are considered stable enough for widespread use, but they are by no means a finished product. We still release updates on a regular basis.

**Legal Disclaimer:** This project was approved by Epic Games, but it is not an official Epic project, nor has it been reviewed or tested by Epic.

## Installation

This repository contains development snapshots as well as official releases.

### Development Snapshots

If you are a modder or beta tester and you would like to test our latest changes, then simply use git to check out this repository. Note, however, that our development snapshots are generally not suitable for online play, as they might not be recognized by various anti-cheat solutions. Development snapshots may also be less stable than the official releases.

### Official Releases

Our official patch releases can be found on the [Releases Page](https://github.com/OldUnreal/UnrealTournamentPatches/releases). If you are a regular player or if you want to play online, then please use official releases only.

Our official Windows and Linux releases are distributed as file archives. They are meant to be unpacked **on top of an existing installation** of Unreal Tournament. If you want to test out our patches, but maintain the possibility to uninstall them, we strongly urge you to create a backup of your entire UT folder before installing the patch.

The macOS version of our patch comes as an application bundle. You should drag this bundle into your applications library. If you're installing our macOS patch for the first time, you will also need to copy the data files from an existing UT installation into the bundle. You can do this by right clicking the bundle in Finder and by selecting the "Show Package Contents" option. Next, you should navigate to the Contents>MacOS folder. Finally, you should drag the Maps, Sounds, Textures, and Music folders from an existing UT installation into this folder.

## System Requirements

Our patches should work on any fairly modern x86 desktop and server.

Windows systems will need to run Windows XP or later. Some features (e.g., Cluster and ALAudio) are only available on systems running Windows Vista or later.

Linux systems will need GNU libc 2.19 or later.

macOS systems will need a 64-bit x86 CPU and Mac OS X Mavericks (10.9) or later. Some rendering features may be unavaiable on macOS.

## Features

Besides fixing hundreds of bugs, the OldUnreal UT patches also add features such as:
* Raw input support and full mouse smoothing control
* OldUnreal's latest OpenGL 4-based 3d renderer (XOpenGLDrv)
* OldUnreal's latest OpenAL-based audio driver (ALAudio)
* Han's latest FMOD-based audio driver (Cluster)
* SDL2-based window management for the Linux and macOS clients
* The latest Demo Manager
* Unreal 227's Unreal Editor 2.2 (with some UT-specific enhancements)
* PNG support for screenshots
* Scaling control for in-game fonts and the game menu
* UTF-8 support for game ini, int, and log files
* Faster server downloads (even without redirect servers)
* Mouse wheel scrolling support for the game menu
* High-DPI awareness for the game and Unreal Editor

A full list of patch features and changes is available in the [Release Notes](https://github.com/OldUnreal/UnrealTournamentPatches/blob/master/ReleaseNotes.md). 

## Compatibility

While the OldUnreal patches preserve compatibility with the original game as well as most mods made for the original game, there are a couple of compatibility issues people should be aware of.

### For Players

All UnrealScript mods for UT v451b or lower will continue to work in OldUnreal's v469 or later. The following native (C++) mods for older UT versions will not work in v469:

* XC_Engine v24 or below: A v469-compatible update for XC_Engine is coming soon
* Demo Manager 3.4 or below: Our patches include an updated Demo Manager so there is no need to downgrade to an older version
* D3D8Drv: D3D8Drv will crash in v469. We are not planning to fix this
* D3D10Drv: D3D10Drv has some rendering glitches and does not work in Unreal Editor 2.2

### For Server Admins

Most UnrealScript mods for UT v451b or lower will continue to work on OldUnreal's v469 or later servers. Some old anti-cheat mods such as CSHP4 and AnthChecker will reject v469 clients, however.

The following native (C++) server mods will not work in v469:
* ServerCrashFix: there is no need to install this mods as all of its fixes have been integrated into the OldUnreal patches
* ACE v1.1f or below: will continue to work on Windows servers but not on Linux servers. Server admins who wish to run ACE on their Linux servers must upgrade to ACE v1.2 or later
* XC_Engine v24 or below: Most of the bug fixes in XC_Engine have been integrated into the OldUnreal patches. Server admins who rely on XC_Engine for its advanced features must upgrade to XC_Engine v25 or later

### For Developers

OldUnreal's patches add some new UnrealScript features which should not be used in mods that target compatibility with UT v451b or below. We are working on a document that lists the new features and that describes best practices for developers.

Native mod developers may want to use our updated UT SDK, which will be hosted in this repository.

## Donations

We are all volunteers who work on Unreal and Unreal Tournament in our spare time. If you like our work, then please consider making a small donation [here](https://www.oldunreal.com/donate.html). Please make sure to mention Unreal Tournament in your donation note!

## Other Contributions

We are more than happy to accept other contributions too. Some of the things we could use help with are:

* Installers: The Linux and Mac versions of the patch currently lack an installer script/program. We would gladly accept 3rd party installers contributed by community members.
* Documentation: Likewise, the Linux and Mac patches have little to no documentation. We assume that the installation process is self-explanatory. If you disagree, then please help us write some documentation.
* Missing localizations: the new patches include several new in-game menu options as well as new 3D renderers and audio drivers. The text displayed by these new components is currently available in English only (although Spanish translations will be added soon). If you want to contribute text localizations, then please post them in our issue tracker.
* Hardware: If you have any decent hardware that you want to donate, then please send a direct message to Smirftsch or anth through the OldUnreal forum. We are especially looking for more macOS development systems (we currently only have one 2012 MacBook Pro for 5 developers).

## Bug Reports

You can use our [issue tracker](https://github.com/OldUnreal/UnrealTournamentPatches/issues) to file bug reports. Reasonable feature requests for Unreal Editor can also be posted there. Please do not ask for new features in the game itself as these are out of the scope of our project.

When filing a bug report, please include relevant details about your setup (i.e., your operating system and version, your UT version and build date, mods you are using) and describe how we can reproduce the problem.

## Credits

The primary developers for the OldUnreal patches were: Smirftsch, Dots, Han, Higor, and [AnthraX](https://github.com/stijn-volckaert).

We also want to recognize the hard work of the many beta testers and contributors in our community:
* Chamberly, Casey: for the many internal bug reports and mental support
* Ooper: for catching a lot of the early bugs
* Feralidragon, Berserker, Che, Sizzl: for extensive testing and feedback on Unreal Editor
* Neon_Knight: for the updated English and Spanish localizations
* Lightning: for the new HD UMenu textures
* Sizzl, batonix, ue, Zim: for extensive testing and feedback on the game server
* uZi, batonix, zkyp, and the members of the UTCTF.pug community: for helping us debug the invisible weapon/flag problem
* Sp0ngeb0b, proasm, Deepu: for extensive testing and feedback on UnrealScript-related issues
* Buggie: for extremely thorough testing and for the record number of bug reports

Finally, we want to express our sincerest gratitude to the following people:
* Stacey Conley (aka "Flak"): this project would not have happened without her. Thank you Stacey, you are amazing!
* Ryan C. Gordon (aka "icculus"): for his hard work on UT over the years and for SDL2. If you like Ryan's work, then please consider [supporting him](https://www.patreon.com/icculus).
* Chris Dohnal: for contributing the UTGLR OpenGL and Direct3D 9 renderers.

---

# Release Notes

## General Information

### Official Unreal Tournament Web Sites

* [Unreal Tournament Home Page](https://www.unrealtournament.com)
* [Epic Games Home Page](https://epicgames.com)
* [Unreal Engine Technology Page](https://www.unrealengine.com)

### Independent Unreal Tournament Web Sites

* [UT99.org - Unreal Tournament Community](https://ut99.org)
* [OldUnreal](https://www.oldunreal.com)

## Unreal Tournament Version 469 Release Notes

Version 469 is completely network compatible with all previous public releases of UT (down to 432).
The UTPG and OldUnreal teams worked hard to maintain binary compatibility with older native mods.
Most of these mods will continue to work in version 469. However, some mods may need some trivial updates.
If you are a native mod author, and you are having trouble updating your mod for version 469, then please reach out to us at [the OldUnreal forums](https://www.oldunreal.com/cgi-bin/yabb2/YaBB.pl?board=nativemods).
**Note:** This patch disables older versions of ACE.
Server admins should upgrade ACE to version 1.1e or later to check 469 clients.

### Stability Improvements

#### Unreal Editor

* Fixed an issue that caused UnrealEd to crash if the EditPackages list did not contain any packages with meshes in them.
* Fixed an issue that caused UnrealEd to crash when opening large UnrealScript files.
* Fixed an issue that caused UnrealEd to crash when opening packages with array variables in them.
* Fixed an issue that caused UnrealEd to crash during shutdown. This issue likely only affected Windows 10 users.
* Fixed an issue that caused UnrealEd to crash when reloading a map after rebuilding several packages.
* Fixed an issue that caused UnrealEd to crash while editing maps with lots of dynamic lights.
* Fixed an issue that caused UnrealEd to crash when docking/undocking one of the browser windows.
* Fixed an issue that caused certain commandlets to crash because the garbage collector decided to destroy them while they were still running.
* Fixed an issue that caused the ucc batchexport commandlet to crash when exporting textures from a package containing scripted textures.

#### Game Client

* Fixed an issue that caused the game to crash when running the "GET" consolecommand to read an array property.
* Fixed an issue that caused the game to occasionally crash on shutdown.
* Fixed an issue that caused the game to crash when calling certain canvas functions with an invalid font or texture argument.
* Fixed an issue that caused the game to crash if the player deleted the [Engine.GameEngine] group from the UT.ini file.
* Fixed an issue that caused the game to crash when resetting properties to their default values in the preferences window.
* Fixed an issue that caused the game to crash when attempting to call an unrealscript function that has the same name as a global variable within the same class.
* Fixed dozens of issues that caused the game to crash when exporting properties in textual format (e.g., through GetPropertyText).
* Fixed various issues that caused the game to crash after destroying objects containing dynamic arrays.
* Fixed various issues that caused the game to crash when rendering scenes with lots of actors/dynamic sprites in them.
* Fixed an infinite recursion crash bug triggered when picking up an invisibility powerup while already invisible.
* Fixed an issue that caused certain maps to crash the game due to duplicate actors in the map.
* The game now properly nullifies references to all destroyed actors. This change fixes the garbage collector crashes that triggered when an Actor was referred to by an Actor in a different level, or when a non-Actor object kept an implicit or explicit reference to a destroyed Actor.
* Fixed a bug that caused the game to crash when using the "QUIT" or "EXIT" command during demo playback.
* Fixed a bug that could cause the game to crash while recording a demo on a server that generates excessive amounts of traffic on single actor channels. One of the mods that often triggers this bug is Nexgen.
* Fixed a bug that caused the game to crash when calling an iterator function in a null context.
* Fixed a bug that caused the game to crash in maps that had brushes with bStatic and bNoDelete set to false.

#### Game Server

* Fixed aluigi's unrealfp Remote Server DoS bug.
* Fixed an issue that caused the server to crash in AActor::execPlayerCanSeeMe in games with bots in them.

### Bug Fixes

#### Unreal Editor

* Fixed an UnrealEd issue that caused vertices/brushes to become invisible while zooming in in vertex edit mode.
* Fixed an UnrealEd issue that caused brush clips to snap to the nearest grid location when clicking a vertex.
* Fixed an UnrealEd issue where Actors could not be placed/deleted/edited if an Actor with the same name already existed elsewhere in the class hierarchy.
* Fixed an UnrealEd issue where the 3D viewports used incorrect lightmaps after rebuilding lighting/bsps.
* Fixed an issue that caused incorrect brush stretching/scaling on non-builder brushes.
* Fixed an issue that caused UnrealEd to show all textures in the game when selecting a font group in the Texture Browser.
* Fixed an issue that caused erratic mouse cursor behavior when dragging in an orthogonal zoom viewport.
* Fixed an issue that caused MyLevel resources to become corrupted after loading a new map in UnrealEd.
* Fixed an bug that caused the texture browser scrollbar to reset when scrolling down a long list of textures.
* Fixed various text clipping bugs in the texture browser window.
* Fixed a bug that caused v436-v451 to crash when rendering LOD meshes imported with UT v440 or later.
* Fixed a bug that made UnrealEd truncate large files in the code editor window.

#### Physics and Player Movement

* Fixed an issue where the game would speed up dramatically when rendering more than 200 frames per second.
* Fixed a bug that could cause dodge moves to be delayed.
* Fixed a bug that caused the server to constantly and incorrectly adjust the client's in-game position. This caused choppy movement when rendering more than 90 frames per second.
* Fixed a bug that caused players to get stuck in walls or slopes when playing with high frame rates. This bugfix will only work on v469 servers.
* Fixed a bug that caused extremely large position adjustments when walking sideways into sloped brushes. This bugfix will only work on v469 servers.
* Fixed several bugs that allowed certain projectiles to ignore collision with level geometry.

#### Input and Windowing

* Fixed a bug that caused the scrolling animation in the preferences window to play in the opposite direction.
* Fixed an issue where you could not select property values containing spaces in the preferences menu.
* Fixed an issue where the mouse would get stuck in the middle of the game window on Linux and Mac.
* Fixed an issue where the in-game windowing system would sometimes show a wait cursor instead of a west-east window resizing cursor.

#### Networking and Netcode

* Fixed a bug that could cause carried weapons and flags to become invisible in online games.
* Fixed a bug that caused XC_Engine servers to reject connections from players who had just watched a demo.
* Fixed several issues that caused network connections to be terminated unexpectedly on Linux and Mac.

#### Audio and 3D Rendering

* Fixed an issue where the game would only show part of the player model in the player setup menu.
* Fixed an issue where the game would shut down when a non-fatal rendering anomaly occurred.
* Fixed a bug that caused the game viewport to have the wrong dimensions after resizing the game window on Linux or Mac.
* Fixed several bugs that caused sounds not to update or to play from the wrong location.
* Fixed a bug that caused the game to crash at extremely high resolutions (such as 8K).
* Fixed an issue where the game would not update stale actor lighting data in the engine cache. As a result, many actors would be renderered in pitch black even when they should be lit. This issue especially affected people playing with large cache sizes or high frame rates.
* Fixed a bug that caused CTF Flags to become dark after being returned to their flag base.
* Fixed an issue where certain sounds would play at double the intended volume while recording a demo.
* Fixed an issue where screenshots would not get rendered correctly if you had your vertical screen resolution set to an odd number of pixels.
* Fixed a bug that caused all decorations in skyboxes to be invisible.
* Fixed a bug that caused the game to stop rendering after changing your FOV in a game type that had its MinFOV and MaxFOV settings set to 0.

#### Miscellaneous

* Fixed an issue where the game would hang for a long time (and sometimes even crash) when opening a maplist with lots of maps.	
* Restored the ability to kick players and bots from local games.
* Fixed an issue where bots considered human players invisible even after their invisibility pickup had expired.
* Fixed several bugs that could cause weapons to instantly switch between fire and alt fire animations.
* Fixed a bug that allowed players to interact with the level and pick up items before the match started after giving up admin privileges via AdminLogout command.
* Team games now properly end when one of the teams scores in overtime.
* The 1024 character limit on conversions between ANSI and Unicode strings is gone.
* Fixed an engine bug that could cause Demo Manager to freeze the game after using the seekto command.
* Eliminated many "Accessed None" warnings.
* Pawns that get destroyed while they have the Destroyed probe function disabled should now get unlinked from the Level Pawnlist.

### Enhancements

#### Unreal Editor

* Merged most of Unreal 227's Unreal Editor enhancements.
* UnrealEd's viewport window allows you to select any of your renderdevices now (not just SoftDrv and D3DDrv).
* UnrealEd's button bar and texture browser now have mouse wheel support.
* UnrealEd's 2D Shape Editor now properly calculates the vertex positions while dragging at zoom levels other than 100 pct.
* UnrealEd now supports mouse wheel scrolling in the 2D viewports.
* UnrealEd now has an "Add PlayerStart" item in the surface popup menu. This item only shows if your level does not have a PlayerStart yet.
* UnrealEd viewports can now render up to 200 frames per second. This framerate was previously capped at 30.
* UnrealEd's vertex editor now properly accumulates small vertex adjustments. Previously, small adjustments could get discarded due to grid snapping.
* Added texture format conversion support to the texture browser.
* Added an option to remove the compressed mips from a texture in the texture browser.
* All UnrealEd viewports now support renderdevice switching.
* Added texture import support for various new image formats.
* The ucc make commandlet now works on Linux and Mac.
* The ucc compress commandlet can now skip compression if an up-to-date .uz file already exists. To use this new feature, add the "update" command line parameter to your ucc compress invocation.
* S3TC/DXT1 texture compression should now be available in the ucc tools for Linux and Mac (though obviously not in UnrealEd).

#### High-resolution Support

* UnrealEd, Setup, and the game client are now high-DPI aware on Windows. This eliminates the bluriness a lot of people with big monitors were seeing. It also improves input precision in the game and the editor.
* Added automatic scaling of the game menu. The scaling factor and behavior can be controlled using the new settings in the menu.
* Added crosshair scaling to the standard HUD. You can configure the crosshair scaling settings in the menu. NOTE: A lot of mods will likely ignore the crosshair scaling. Mod authors should update their mods so they call the regular ChallengeHUD.DrawCrosshair function.
* Added in-game font scaling. When enabled, fonts scale automatically with your desktop DPI. Scaling can be turned on and off in the in-game menu.
* UWindow now supports higher resolution textures for LookAndFeels. This enables LookAndFeels to scale better for people playing at higher resolutions and higher GUI scales. The UMenu LookAndFeels have been (partially) updated to use this new feature.

#### Input and Windowing

* Fixed mouse acceleration issues for players using DirectInput on Windows 10.
* Added raw mouse input support. This feature can be enabled by setting the UseRawHIDInput to true in the WinDrv.WindowsClient section of the game ini.
* Added enhanced pointer precision control. By default, the game enables enhanced pointer precision while in the menu and restores the old precision settings when in game. However, you can now set the NoEnhancedPointerPrecision option in the WinDrv.WindowsClient section to true if you do not want the game to change the system pointer precision settings at all.
* Added new menu options to control the mouse input and smoothing behavior.
* Improved support for mouse side buttons.
* Added mouse wheel scrolling support to the in-game windowing system.
* Added clipboard paste support to the quick console.
* The Linux and Mac clients now have clipboard support.

#### UnrealScript

* Console commands that are over 1024 bytes in length, or that return over 1024 bytes of data should now be safe to use.
* Added a new primitive type called "pointer". Pointer variables automatically adjust to the word width on the target platform. Native mod authors should use pointer variables to mirror a pointer type in C++.
* Added new Canvas functions to create arbitrarily-sized fonts on the fly. Please do not use these functions directly as they will cause your mod to be incompatible with earlier versions of UT. Instead, use the BotPack.FontInfo class to retrieve fonts that are appropriate for the client's screen size.
* Added the "TEXTURE MERGECOMPRESSED NAME=MergeWith FILE=HiResFile.PNG GROUP= " exec command. This command allows you to import and compress hi-res textures and merge them into an existing texture's compressed mipmaps.
* Added HandlePauseRequest to the mutator system, allows modders to modify the behaviour of players' pause button in servers.

#### Security

* Fixed several arbitrary code execution vulnerabilities.
* The Windows version of the game now has several security enhancements including (but not limited to) Data Execution Prevention (can be disabled with the -nodep command line parameter), SafeSEH, and ASLR support.

#### Anti-Cheat

* Revamped the UT v468 MD5 code. Older clients can connect to v469 servers now even if they don't support the MD5 extension. The server now also marks which files it wants MD5 checks for.
* MD5 checking is now disabled by default. To enable, set MD5Enable to True under [Engine.GameEngine] in the server's ini file.
* Added an auto-updater for the Packages.md5 list. The auto-updater will check for list updates once an hour if you have MD5Enable and MD5AutoUpdate both set to true under [Engine.GameEngine].

#### Networking and Netcode

* Restored demo compatibility with UT v436.
* Added workarounds for bugs that could cause player animations to break in demos or online play after installing high-resolution S3TC textures.
* Made improvements to the networking code to eliminate the infamous texture skating problem (in nearly all cases).
* The game no longer disables Download Managers if they encounter a non-critical error while attempting to download a file from the server. Previously, the game would stop attempting to download from redirect servers after encountering an HTTP error (such as HTTP 404).
* The game now shows the number of remaining packages while downloading from a server.
* Clients are far less likely to encounter package mismatch errors when connecting to servers, now a UT client can have multiple packages with the same name and the loader will select the right one (if present).
* Added bandwidth control for file downloads from the gameserver. The bandwidth control option overrides the MaxClientRate. It can be controlled in the server.ini file as follows:
```
[IpDrv.TcpNetDriver]
MaxFileDownloadRate=0   Maximum download speed in bytes per second

; Possible values for MaxFileDownloadRate:
; -1                    Send files at the maximum speed possible
;  0                    Limit the file download speed to MaxClientRate bytes per second. This is what UT did by default in versions 468 and below
;  any positive number  Allow download speeds of up to this amount of bytes per second.
```

#### Audio and 3D Rendering

* Screenshots now get stored in the "System/Screenshots" folder. UT will automatically create this folder if it does not already exist. We also removed the limit on the number of screenshots you can have in this folder and we now save screenshots in PNG format rather than BMP.
* Decals are now visible in fog zones.
* Integrated Cluster, a new FMOD-based audio driver with superior sound quality and hyper-realistic sound effects (Thanks han!).
* Integrated enhanced versions of Chris Dohnal's UTGLR OpenGLDrv and D3D9Drv. 
* Integrated OldUnreal's latest XOpenGLDrv. 
* Galaxy Audio is now considered deprecated. On Windows Vista and later, the game launcher will do an automatic one-time upgrade your audio subsystem to the latest version of the OldUnreal Cluster driver.
* Revamped the underlying audio code for sounds played using TournamentPlayer.ClientPlaySound. The revamped code should make playback volumes more consistent and should eliminate audio glitches such as crackling and screeching.

#### Miscellaneous

* UnrealEd and the game client are now large address aware on Windows. This means it is far less likely that you'll run out of virtual memory.
* Removed some outdated items from the in-game menu (e.g., ngWorldStats, mplayer, heat, won, ...)
* Rewrote some of the core timing routines so the game runs more smoothly (and with less glitching) on multicore CPUs and in long-running games.
* The Linux and Mac clients finally support unicode! The most visible consequence is that player names with non-ascii characters in them will now display correctly when playing on Linux servers (provided that you use font textures with the proper unicode glyphs).
* The game now uses UTF-8 as the prefered file encoding (unless a UTF-16LE BOM is found at the start of the file).
* Added selectedcursor support to the Linux and Mac clients.
* Added the -FORCELOGFLUSH command line option. This option makes the game/server flush the log file every time it is written to.
* Added the -SETHOMEDIR= command line option. Normally, the game looks for the UnrealTournament.ini and User.ini files in \~/.utpg/System (on Linux), \~/Library/Application Support/Unreal Tournament/System (on Mac), or in UnrealTournament\System (on Windows). With this option, you can override the preferences path (e.g., ./ut-bin-x86 -sethomedir=\~/.loki/ut/System).
* Added a menu option to control the Translocator's weapon switching behavior when pressing fire and alt-fire simultaneously.
* Made pulsegun and minigun lockdown a configurable option that is disabled by default.
* UnrealI and UnrealShare decorations can no longer be destroyed if they have bStatic set.
* Merged Unreal 227's UnrealI and UnrealShare AI fixes.

## Old Release Notes

The release notes for older patches released by Epic and UTPG can be found in the Help/ReleaseNotes.htm file which is included in the patch.