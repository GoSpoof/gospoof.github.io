# Rubber Glue Option (-rg)

The `-rg` option enables rubber glue mode to redirect attacks back to the intruder.

## Usage

```bash
./goSpoof -rg
```

## Description

- Default value: Off
- Tunnels attacks back to the attacker
- Must be used as a standalone flag
- Cannot be combined with any other options
- Saves the hash and plain text in a captures directory
- Requires careful consideration before use

## Examples

```bash
# Basic rubber glue mode
./goSpoof -rg

# Note: Do not combine with other flags
# Incorrect usage examples:
# ./goSpoof -rg -p 4444
# ./goSpoof -rg -i 192.168.1.100
# ./goSpoof -rg -honey Y
```

[Back to Options Overview](../Options%20overview.md) 