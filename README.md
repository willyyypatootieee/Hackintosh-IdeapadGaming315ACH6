# Ryzentosh — Lenovo IdeaPad Gaming 3 (15ACH6) EFI
### I no longer use this Hackintosh
This build was created for experimental purposes and I no longer use it. Contributions are welcome — open a pull request if you need changes.

A curated OpenCore EFI for running macOS on the Lenovo IdeaPad Gaming 3 (15ACH6) with AMD Ryzen processors.

### Laptop configuration

| Hardware  | Details |
|---|---|
| CPU | AMD Ryzen 7 5800H — 8 cores / 16 threads |
| Memory | 32 GB SO‑DIMM DDR4 3200 MHz |
| Storage | PCIe M.2 NVMe 1 TB + 512 GB SSD |
| Graphics | Vega 8 (iGPU). NVIDIA dGPU disabled via ACPI |
| Display | FHD 1920×1080 IPS, 250 nits, 144 Hz |
| Network | MediaTek Wi‑Fi 6 MT7921 — not supported |
| Audio jack | Functional |

### Working

- Camera
- Speakers
- Microphone
- Ethernet
- 144Hz Display
- USB Type C
- HDMI ( Works because the hdmi scheme is not connected through egpu.)
- Power management
- RGB Keyboard

### Known issues / TODO

- WLAN (MT7921)
- Brightness control
- Bluetooth
- dGPU (NVIDIA) — work in progress. Possible workarounds: install an Intel Wi‑Fi card or use a USB Wi‑Fi adapter.

### Requirements

- Lenovo IdeaPad Gaming 3 (15ACH6) with Ryzen 7 5800H (other Ryzen variants may work with tweaks)
- A Mac or an existing Hackintosh (or Windows/Linux to create the installer)
- A USB drive (at least 32 GB)
- Time, patience, and internet access (Ethernet or USB tethering can be used during installation)
- A copy of macOS (Big Sur, Monterey, Ventura, Sonoma reported to be compatible)

### Installation (summary)

1. Create a macOS USB installer using Apple’s createinstallmedia tool.
2. Insert the USB drive and run diskutil list to identify the installer volume.
3. Mount the USB EFI partition, e.g.:
```bash
sudo diskutil mount diskXsY   # replace diskXsY with your USB EFI partition (example: disk2s1)
```
4. Copy the repository’s EFI folder to the USB EFI partition (the USB’s EFI, not the internal drive).
5. Eject USB, plug it into the laptop, and enter BIOS/UEFI.

Recommended BIOS changes:
- Disable Secure Boot
- Disable the NVIDIA dGPU through bios if u want the laptop stay silent.
- Set integrated graphics memory to 1-4 GB
- Set USB drive as the first boot device

6. Boot the USB installer and install macOS. The first boot after stage two can be slow (1 Hour during optimizations) — be patient.

### Post-install

1. Mount the internal EFI partition and copy the EFI folder to it:
```bash
sudo diskutil mount disk0s1
```
2. Copy the EFI folder to the mounted partition (adjust paths as needed).
3. Install required kexts/drivers (for audio, consider AppleALC with the appropriate layout/patches or alternatives per kext docs).
4. Follow an OpenCore guide to create a proper SMBIOS for your system.

### Screenshots

Below are screenshots from this build/installer:

![Screenshot 2025-11-01 at 17.15.17](./Screenshot%202025-11-01%20at%2017.15.17.png)

![Screenshot 2025-11-01 at 17.15.21](./Screenshot%202025-11-01%20at%2017.15.21.png)

