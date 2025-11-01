Ryzentosh Lenovo Ideapad gaming 3 (15ach6) EFI
What works and what doesn't

Working: Camera, brightness, speakers, mic, ethernet, power managment

Broken: WLAN, Bluetooth, dGPU ( Will Try To Fix ASAP Using Intel WLAN Card )
What's required?

    Lenovo ideapad gaming 3 - With AMD Ryzen 7 5800H (others may work, but will need some configurations)
    Mac / Hackintosh // You can use Windows / Linux PC to create a web installer
    Atleast 32 GB USB stick
    A lot of time and patience
    Ethernet cable or Android phone with internet over USB.
    macOS BigSur, Monterey, Ventura, Sonoma ( Should Be Work )
    A brain


Installation

    Create macOS installer using 'createinstallmedia'
    Open terminal and type "diskutil list" find your USB that installer has been copied to.
    Type "sudo disktutil mount diskXsX" replace diskXsX with your USB ID for ex. disk2s1
    Copy whole EFI folder you can download it here onto EFI partiton of the USB DRIVE NOT YOUR PC's
    Eject usb plug it into your laptop
    Enter BIOS and:

    disable: secure boot, dedicated GPU
    Change integrated graphics memory to 2GB
    Set USB drive as first boot device

    Reboot your pc with usb inserted

    Boot macOS installer

    Wipe your hardrive with drive utility

    Install macOS Note: after 2nd part of the installer 1st boot may take 30 minutes+ so be patient!

    Configure macOS

    Download the EFI again

    Open termial and type: "sudo diskutil mount disk0s1"

    Copy EFI folder onto EFI partiton OF YOUR COMPUTER NOT YOUR USB DRIVE

    Download VooDooHDA here and follow the instructions there.

    Use Open Core tutorial above to generate a SMBIOS

    DONE
