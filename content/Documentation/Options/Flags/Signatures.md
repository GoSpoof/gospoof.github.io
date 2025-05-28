---
title: Signatures Option (-s)
---
The `-s` option allows loading custom service signature patterns from a file.

## Usage

```bash
./goSpoof -s signatures.txt
```

## Description

- No default value
- Loads custom service signatures
- Supports regex patterns
- Customizes service responses
- Useful for advanced configurations

## Examples

```bash
# Basic signature file
./goSpoof -s signatures.txt

# With port binding
./goSpoof -s signatures.txt -p 4444

# Full configuration
./goSpoof -s signatures.txt -Y config.yaml -l /var/log/gospoof.log
```

[Back to Options Overview](../Options%20overview.md) 