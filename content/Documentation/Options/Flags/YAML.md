---
title: YAML Config (-Y)
---
The `-Y` option loads configuration settings from a YAML file for complex setups.

## Usage

```bash
./goSpoof -Y config.yaml
```

## Description

- No default value
- Loads configuration from specified YAML file
- Supports complex service configurations
- Can override command line options

## Examples

```bash
# Basic YAML config
./goSpoof -Y config.yaml

# With daemon mode
./goSpoof -Y config.yaml -D

# Advanced configuration
./goSpoof -Y config.yaml -D -l /var/log/gospoof.log
```

[[Documentation/Options/Options overview|Back to Options Overview]] 
