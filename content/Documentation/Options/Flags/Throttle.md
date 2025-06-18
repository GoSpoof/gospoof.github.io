---
title: Throttle (-t)
---
The `-t` option controls scan throttling with increasing delays based on level (1-5).

## Usage

```bash
./goSpoof -t 3
```

## Description

- No default value
- Levels 1-5 with increasing delays:
  - Level 1: 5 minutes
  - Level 2: 20 minutes
  - Level 3: 40 minutes
  - Level 4: 60 minutes
  - Level 5: 80 minutes
- Can be combined with `-w` for additional delays

## Examples

```bash
# Moderate delay
./goSpoof -t 3

# Maximum delay
./goSpoof -t 5

# Maximum throttling with wait and honeypot
./goSpoof -t 5 -w 10 -honey Y
```

[Back to Options Overview](../Options%20overview.md) 