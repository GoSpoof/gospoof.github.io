# Verbose Option (-v)

The `-v` option enables detailed output for debugging and monitoring purposes.

## Usage

```bash
./goSpoof -v
```

## Description

- No default value (disabled by default)
- Enables detailed logging of all activities
- Shows connection attempts and responses
- Useful for debugging and testing configurations

## Examples

```bash
# Basic verbose mode
./goSpoof -v

# Verbose with port binding
./goSpoof -v -p 4444

# Verbose with honeypot mode
./goSpoof -v -honey Y
```

[Back to Options Overview](../Options%20overview.md) 