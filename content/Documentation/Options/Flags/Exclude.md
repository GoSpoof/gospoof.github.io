---
title: Exclude Ports (-e)
---
The `-e` option excludes specific ports from GoSpoof's spoofing behavior.

## Usage

```bash
./goSpoof -e <port_list>
```

## Description

- No default value
- Comma-separated list of ports to exclude
- Excluded ports handled normally by the system
- Useful for running legitimate services
- Prevents interference with critical services

## Examples

```bash
# Exclude SSH port
./goSpoof -e 22

# Exclude multiple ports
./goSpoof -e 22,80,443

# Exclude with other options
./goSpoof -e 22,80 -p 4444 -sT 4444
```

[Back to Options Overview](../Options%20overview.md) 