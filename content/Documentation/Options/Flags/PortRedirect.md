---
title: Port Range Redirect (-r)
---
The `-r` option sets the range of ports that iptables should redirect from when using `-sT`.

## Usage

```bash
./goSpoof -r "1:1000"
```

## Description

- Default value: "1:65535" (all ports)
- Must be used with `-sT` option
- Format: "low:high" (e.g., "1:1000")
- Requires root/sudo privileges
- Ports must be valid (1-65535)

## Examples

```bash
# Redirect first 1000 ports
./goSpoof -sT 4444 -r "1:1000" -p 4444

# Redirect common ports
./goSpoof -sT 4444 -r "20:25" -p 4444

# Redirect high ports
./goSpoof -sT 4444 -r "49152:65535" -p 4444
```

[[Documentation/Options/Options overview|Back to Options Overview]] 