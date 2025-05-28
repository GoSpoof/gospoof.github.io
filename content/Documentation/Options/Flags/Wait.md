---
title: Wait Option (-w)
---
The `-w` option adds a delay between sending signatures to slow down scanning tools.

## Usage

```bash
./goSpoof -w 5
```

## Description

- No default value
- Specifies seconds to wait between signatures
- Can be combined with `-t` for maximum delay
- Useful for slowing down automated scans

## Examples

```bash
# 5 second delay
./goSpoof -w 5

# 10 second delay
./goSpoof -w 10

# Combined with throttle
./goSpoof -w 10 -t 5
```

[Back to Options Overview](../Options%20overview.md) 