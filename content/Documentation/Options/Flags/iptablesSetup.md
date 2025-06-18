---
title: iptables Setup (-sT)
---
The `-sT` option configures iptables to redirect traffic to a specified port.

## Usage

```bash
./goSpoof -sT 4444
```

## Description

- No default value
- Requires root/sudo privileges
- Sets up iptables rules to redirect traffic
- Must be used with `-p` to specify the target port
- Can be combined with `-r` for port range redirection

## Examples

```bash
# Basic iptables setup
./goSpoof -sT 4444 -p 4444

# Setup with port range
./goSpoof -sT 4444 -p 4444 -r "1:1000"

# Full setup with logging
./goSpoof -sT 4444 -p 4444 -l /var/log/gospoof.log
```

[Back to Options Overview](../Options%20overview.md) 