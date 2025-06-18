---
title: Start on Boot (-boot)
---
The `--boot` option saves the current configuration and sets up GoSpoof to start automatically on system boot.

## Usage

```bash
./goSpoof [other_flags] --boot
```

## Description

- No default value
- Saves all specified flags to configuration
- Creates systemd service (gospoof.service)
- Enables automatic startup on boot
- Requires root/sudo privileges

## Examples

```bash
# Basic boot setup
./goSpoof -p 4444 -sT 4444 --boot

# Boot with honeypot and logging
./goSpoof -p 4444 -honey Y -l /var/log/gospoof.log --boot

# Boot with throttling
./goSpoof -p 4444 -sT 4444 -t 3 --boot
```

[[Documentation/Options/Options overview|Back to Options Overview]] 