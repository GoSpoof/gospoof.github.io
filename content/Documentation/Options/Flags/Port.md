---
title: Port (-p)
---
The `-p` option specifies the port that GoSpoof will listen on for all redirected traffic.

## Usage

```bash
./goSpoof -p 4444
```

## Description

- Default value: 4444
- Must be a valid port number (1-65535)
- Cannot be used with `-rg` option

## Examples

```bash
# Basic port setup
./goSpoof -p 4444

# Port with iptables redirection
./goSpoof -p 4444 -sT 4444

# Port with range redirection
./goSpoof -p 4444 -sT 4444 -r "1:1000"
```

[[Documentation/Options/Options overview|Back to Options Overview]] 