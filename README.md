#GamingStation OS 16.04.3 LTS

Turn any old computer into a powerful retro gaming station.

Screenshots: https://imgur.com/gallery/PP1o3

Video: https://youtu.be/bOemjGi2H2I

To turn on auto login run:

    sudo auto-login

This remembers the last session used. So to be able to boot directly into EmulationStation you must first restart the system within EmulationStation Xsession.

To update the Libretro Cores run:

    sudo retroarch-cores

This will compile the cores from the latest source and may take awhile. Make sure you have at least 5GBs free on ~Home.

This will also backup the current cores before writing over them. This way you can restore a working old core if the new one doesn't work or failed to compile. The backups can be found in the libretro folder in the 'backup' folder.

    Folder: /usr/lib/x86_64-linux-gnu/libretro/

Some systems need BIOS files before they will work. 

Default BIOS folder for RetroArch: ~/Games/bios

Default BIOS folder for PS2 (also have to select the BIOS in the PCSX2 app): ~/.config/PCSX2/bios

Bugs:

Some USB writers will add the option to run the installer directly. Don't. It has permission issues. It will get to the stage where its copied everything to the disk and just about to install, and it will crash. Run the installer from the desktop in the Live Session.

The other bug is after its installed and wants to restart. The boot logo doesn't show text so you can't see messages. You need to hit enter to eject the media before it reboots. If you don't it may seem like its hanged.

EmulationStation doesn't seem to like PS3 controllers. To map controller hold and keep holding R2 while you enter the inputs. The only ones that matter are the D-pad, Start, A & B. The rest don't matter as they are not used in EmulationStation.

Fix OverScan on HDMI HDTV (Screen not fitting TV)

This seems to only effect a few older TVs and if you are running the Open-Source graphics driver.
To fix, under 'Preferences >> Personal >> Startup applications' there is a option called 'FixRes'.
This will fix it after you logout and back in. 

To fix the issue in the EmulationStation session.

    Open: /usr/bin/emulationstation-standalone

And uncomment the first command. The second is to set the resolution to 720p. Helpful if you have performance issues with dolphin-emu & pcsx2.

Version 3.3 change log:

* Included RPCS3 - PlayStation 3 Emulator. No entry in EmulationStation.
* Added Attract-Mode PPA for easy installation.
* Updated PCSX2 to latest version. May have to turn up Speedhacks---EE Cyclerat if FMV is slow.
* Vulkan support for intel and radeon GPU. If you have issues turn on Oibaf PPA and run: sudo ppa-purge ppa:oibaf/graphics-drivers

Version 3.2 change log:

* jpegoptim & optipng all the images
* Updated all the Libretro Cores from latest sources
* Compiled SDL2 and SDL1.2 HG from source.

Version 3.1 change log:

* Updated kernel to 4.4.0-116
* Steam installed with an entry in EmulationStation to launch it in "Big Picture Mode"
* dolphin-emu & pcsx2 installed
* Bluetooth Controllers working in both xsessions (must be first setup in MATE)
* Added a Fix for OverScan issues
* Fixed audio issues
* Images & Meta-data stored within the ROMs folder when scraped with EmulationStation.
* Fixed RetroArch not saving current config.
* Fixed RetroArch not having the correct resolution.
* Created a better way to detect active display.

By default EmulationStation uses dolphin libretro. To use dolphin-emu edit ~/.emulationstation/es_systems.cfg
There is a comment in the file on how to change it.

To quit out of dolphin-emu: ALT+F4
To quit out of pcsx2: ESC

Both emulators need configuring before use.

SteamOS repo is installed so you can grab the latest version of steam from there, but you may have some issues launching it.

To install run

    sudo apt-get purge steam
    sudo apt install steam-launcher

If you do have issues launching it, see here: https://askubuntu.com/questions/771032/steam-not-opening-in-ubuntu-16-04-lts
