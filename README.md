# CRTPi-Project Presents: CRTPi-RCA
*A Vanilla+ experience for 15Khz Analog Output over Composite!*
_____

Thank you very much to Mike V, Sakitoshi, Mike Chi, the guys at Arcadeforge, Artemio Urbina, Ruckage, ChipsnBlip, Gabriel, kitty666cats, and anyone I've missed! Thank you for the input, support, resources, and help along the way!

**Major Changelogs and Features can be viewed in the pinned posts here:**

    https://reddit.com/r/u_erantyint

**User Photo Galleries (Photos from Historical Versions):**

* RCA: https://photos.google.com/share/AF1QipO8q3LzMQIlexAD0kgEGIArp5Ax8Y9SMxCqoiaouZKDKbcJO3AN-YS7YuaykX1J7A?key=LXJMbWZheG8yamxNOGwxLVRXOWlwRzRia2R6a2FB

**Required Hardware:**

    Raspberry Pi 3B or 3B+
    Compatible 3.5mm to RCA (Zune A/V or XBOX 360-E) Cable
    5v 2.5A Micro USB power supply (Element14 recommended)
    4GB+ SD Card
    
_____

**Optional Prerequisites: Install these prior to installing the CRTPi zips!** 

	Install the following theme: /ruckage/snes-mini/
	Install the following opt packages: scummvm, lr-beetle-wswan, lr-fbalpha2012, lr-mame2000, lr-mame2010, lr-nxengine, lr-ppsspp, lr-prboom, lr-snes9x2002, lr-tgbdual, lr-tyrquake, scraper, skyscraper
	Install the following experimental packages: lr-mame2003-plus
	Install libxpm-dev and libx11-dev: "sudo apt-get install libxpm-dev && sudo apt-get install libx11-dev"
	Install MUNT (MT-32 Emulation) using this guide: https://retropie.org.uk/forum/topic/12549/tutorial-installing-munt-mt-32-emulation-on-rpi-3 (Remove 'qtmobility-dev' from step 1) (mt32roms.zip in master is for step 10)

_____

**Instructions: This is recommended to be installed on a fresh Retropie install on a 3B or 3B+ using the 4.6 offical image (Or 4.5.1 updated to 4.6). Anything you overwrite is your own fault at this point!**

*RCA: For Composite-Out from the Pi's 3.5mm Port to a 15khz Display*

    Install Retropie and configure your desired content
    Connect to WiFi or Ethernet with internet access
    NTSC: Download the CRTPi-RCA_NTSC.zip into your root folder (cd /) with the command "sudo wget https://github.com/crtpi/CRTPi-RCA/raw/master/CRTPi-RCA_NTSC.zip"
    PAL: Download the CRTPi-RCA_PAL.zip into your root folder (cd /) with the command "sudo wget https://github.com/crtpi/CRTPi-RCA/raw/master/CRTPi-RCA_PAL.zip"
    ***WARNING: THE NEXT STEP WILL OVERWRITE GAMELIST.XML FILES AS SHOWN IN THE REPRO! BACK UP ACCORDINGLY!!***
    Unzip and overwrite files with the command "sudo unzip -o -q CRTPi-RCA_NTSC.zip" [OR "sudo unzip -o -q CRTPi-RCA_PAL.zip"]
    Remove the zip with the command "sudo rm CRTPi-RCA_NTSC.zip" [OR "sudo rm CRTPi-RCA_PAL.zip"]
    Reboot the Pi with the command "sudo reboot" and wait for it to return to Emulationstation
    Drop to the command line or connect via SSH
    Restore read/write access to the files you have overwritten with the command  "sudo chmod a+rw -R /opt/retropie/configs/"
    Restore execute access to the runcommand scripts with the command "sudo chmod a+rwx /opt/retropie/configs/all/*.sh"
	Launch into RetroPie-Setup with the command "sudo ~/RetroPie-Setup/retropie_setup.sh"
	Go to "Configuration/Tools > resetromdirs" and run it
	Choose "Perform Reboot" from the menu to reboot your Pi.
    
*OPTIONAL: RCA Arcade Config Pack*

    Download the CRTPi-RCA_ArcadePack.zip into your root folder (cd /) with the command "sudo wget https://github.com/crtpi/CRTPi-RCA/raw/master/CRTPi-RCA_ArcadePack.zip"
    Unzip and overwrite files with the command "sudo unzip -o -q CRTPi-RCA_ArcadePack.zip"
    Remove the zip with the command "sudo rm CRTPi-RCA_ArcadePack.zip"
    Restore read/write access to the files you have overwritten with the command  "sudo chmod a+rw -R /opt/retropie/configs/ && sudo chmod a+rwx /opt/retropie/configs/all/*.sh"
	
_____

The VGA fork is now utilizing Snap-Shader, plus a newly-enhanced runcommand-onstart script, with provision for *user-specified per-game configuration*! 

**Here's the new script:**

    https://github.com/crtpi/CRTPi-VGA/blob/master/VGA-to_opt/retropie/configs/all/runcommand-onstart.sh

**Here's information about Snap-Shader:**

    https://github.com/ektgit/snap-shader-240p

**Here's a quick rundown on how Sakitoshi's 240p/480i Script works :**

To force 480i for a system or game, you can create a '480i.txt' file inside the configuration folder of the system with a list of the file names (case insensitive, extension optional but recommended) you want to force. 

If you wish to force 480i for a whole system, you can write "all" inside the '480i.txt' file. 

Alternatively you can create a "240p.txt" file to force 480i to all games *except for* the ones inside the list.

You can read more about the script functionality [here](https://github.com/Sakitoshi/retropie-crt-tvout).

*Examples:*

    /opt/retropie/configs/psx/480i.txt containing "Bloody Roar 2.PBP" to force 480i for the file "Bloody Roar 2.PBP"
    /opt/retropie/configs/psx/480i.txt containing "all" to force 480i for all the PlayStation games.
    /opt/retropie/configs/ports/kodi/480i.txt containing "all" to force 480i on Kodi.
	
_____

**Final Thoughts:**

If you have any questions, comments, concerns, or issues -- please PM me or DM me on Reddit or post on one of the threads. Chances are, it's a "feature" not a "bug." :)
_____
