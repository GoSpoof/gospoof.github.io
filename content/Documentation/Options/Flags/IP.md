---
title: IP (-i)
---
The `-i` option binds GoSpoof to a specific IP address instead of all available interfaces.

## Usage

```bash
./goSpoof -i 192.168.1.100
```

## Description

- Default value: System IP (all interfaces)
- Binds GoSpoof to listen only on the specified IP address
- Must be a valid IP address on the system
- Can be combined with `-p` for specific port binding

## Examples

```bash
# Bind to specific IP
./goSpoof -i 192.168.1.100

# Bind to localhost
./goSpoof -i 127.0.0.1

# Bind to specific IP and port
./goSpoof -i 192.168.1.100 -p 4444
```

[Back to Options Overview](../Options%20overview.md) 