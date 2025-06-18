---
title: Log File (-l)
---
The `-l` option specifies a file to log port scanning alerts and activities.

## Usage

```bash
./goSpoof -l /path/to/log.log
```

## Description

- No default value
- Creates the log file if it doesn't exist
- Requires write permissions in the target directory
- Logs all activity including connections and responses
- Useful for monitoring and debugging

## Examples

```bash
# Basic logging
./goSpoof -l /var/log/gospoof.log

# Log in current directory
./goSpoof -l gospoof.log

# Log with honeypot mode
./goSpoof -honey -l /var/log/gospoof.log
```

[Back to Options Overview](../Options%20overview.md) 