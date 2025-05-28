# iptables Reset Option (-fT)

The `-fT` option removes all GoSpoof-related iptables rules from the system.

## Usage

```bash
./goSpoof -fT
```

## Description

- No default value
- Requires root/sudo privileges
- Removes all GoSpoof iptables rules
- Should be used before setting up new rules
- Can be used to clean up after testing

## Examples

```bash
# Basic reset
./goSpoof -fT

# Reset after testing
./goSpoof -sT 4444 -p 4444
./goSpoof -fT

# Reset before new configuration
./goSpoof -fT
./goSpoof -sT 4444 -p 4444 -r "1:1000"
```

[Back to Options Overview](../Options%20overview.md) 