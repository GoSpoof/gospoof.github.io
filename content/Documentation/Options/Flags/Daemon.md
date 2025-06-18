---
title: Daemon (-D)
---
The `-D` option runs GoSpoof as a background process.

## Usage

```bash
./goSpoof -D
```

## Description

- No default value (runs in foreground by default)
- Runs GoSpoof as a background process
- Can be combined with other options

## Examples

```bash
# Basic daemon mode
./goSpoof -D

# Daemon with port binding
./goSpoof -D -p 4444

# Daemon with configuration and logging
./goSpoof -D -Y config.yaml -l /var/log/gospoof.log
```

[Back to Options Overview](../Options%20overview.md)