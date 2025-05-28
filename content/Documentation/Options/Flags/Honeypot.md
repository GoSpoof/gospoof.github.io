# Honeypot Mode Option (-honey)

The `-honey` option enables honeypot mode to track and log potential attackers.

## Usage

```bash
./goSpoof -honey Y
```

## Description

- Default value: Off
- Logs attacker IP addresses
- Records timestamps of attacks
- Saves payloads to honeypot.log

## Examples

```bash
# Basic honeypot mode
./goSpoof -honey Y

# Honeypot with port binding
./goSpoof -honey Y -p 4444

# Honeypot with daemon and logging
./goSpoof -honey Y -D -l /var/log/gospoof.log
```
[Back to Options Overview](../Options%20overview.md) 
