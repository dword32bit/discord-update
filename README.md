# Discord Auto-Updater Script

## Overview
-
This Bash script automates the process of downloading, installing, and launching Discord on Linux. It ensures that Discord is always updated before launching by modifying the `.desktop` file and adding an update script.
-
Installation from GitHub only once, the rest will run without having to modify, because it has been modified after the update

## Features
- Automatically downloads the latest Discord `.deb` package.
- Installs the latest version before launching Discord.
- Restores the original `.desktop` file after the update.
- Handles failed downloads or installations gracefully.

## Installation
1. Clone this repo.
   ```bash
   git clone https://github.com/dword32bit/discord-update
   ```
3. Get in the cloned directory.
   ```bash
   cd discord-update
   ```
5. Give execution permission:
   ```bash
   sudo chmod +x discord
   ```
6. Run the script with sudo:
   ```bash
   sudo ./discord
   ```

## How It Works
1. The script modifies the Discord `.desktop` file to launch an update script before Discord.
2. The update script:
   - Downloads the latest `.deb` package.
   - Installs it using `dpkg`.
   - Restores the original `.desktop` file.
   - Launches Discord.
3. If the update fails, Discord will still launch normally.

## Notes
- The update script is stored in `/usr/local/bin/discord-updater`.
- The modified `.desktop` file is located at `/usr/share/applications/discord.desktop`.
- A backup of the original `.desktop` file is stored at `/usr/share/applications/discord.desktop.bak`.

## Uninstallation
To restore the original behavior:
```bash
sudo cp /usr/share/applications/discord.desktop.bak /usr/share/applications/discord.desktop
sudo rm /usr/local/bin/discord-updater
```

## Disclaimer
Use this script at your own risk. Ensure you have backups before modifying system files.

