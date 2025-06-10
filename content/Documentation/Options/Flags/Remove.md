---
title: Remove Boot Configuration (-rm)
---
The `-rm` option removes all saved boot configurations and provides a complete fresh start.

## Usage

```bash
./goSpoof -rm
```

## Description

- No default value
- Removes all saved boot flags and configuration
- Deletes the saved config file
- Stops and removes gospoof.service
- Requires root/sudo privileges

## Examples

```bash
# Remove boot configuration
./goSpoof -rm

# After removal, set up new configuration
./goSpoof -rm
./goSpoof -p 4444 -sT 4444 --boot

# Clean removal for troubleshooting
./goSpoof -rm
```

[Back to Options Overview](../Options%20overview.md) 