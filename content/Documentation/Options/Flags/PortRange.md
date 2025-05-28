---
title: Port Range Option (-sP)
---
The `-sP` option defines which ports GoSpoof should respond to, supporting ranges, lists, or single ports.

## Usage

```bash
./goSpoof -sP "1-1000"
```

## Description

- Default value: "1-65535" (all ports)
- Supports three formats:
  - Range: "1-1000"
  - List: "22,80,443"
  - Single: "4444"
- Must be used with `-p` to specify the listening port
- Ports must be valid (1-65535)

## Examples

```bash
# Port range
./goSpoof -sP "1-1000" -p 4444

# Specific ports
./goSpoof -sP "22,80,443" -p 4444

# Single port
./goSpoof -sP "4444" -p 4444
```

[Back to Options Overview](../Options%20overview.md) 