---
title: Command Line Options
---
This guide provides a comprehensive list of all command line options available in GoSpoof.

## Basic Options

| Option | Description | Default | Example |
|--------|-------------|---------|---------|
| `-p` | Bind to a particular PORT number | "4444" | `-p 4444` |
| `-i` | Bind to a particular IP address | System IP | `-i 192.168.1.100` |
| `-v` | Enable verbose mode | None | `-v` |
| `-D` | Run as daemon process | None | `-D` |

## Port Configuration

| Option | Description | Default | Example |
|--------|-------------|---------|---------|
| `-sP` | Provide a range of ports (1-10), list (1,9,32), or single port | "1-65535" | `-sP "1-1000"` |
| `-sT` | Setup iptables to bind to a single port | None | `-sT 4444` |
| `-r` | Port range for iptables to redirect from (format: low:high) | "1:65535" | `-r "1:1000"` |
| `-fT` | Reset iptables | None | `-fT` |

## Advanced Features

| Option | Description | Default | Example |
|--------|-------------|---------|---------|
| `-honey` | Activate Honeypot Mode (use -honey Y) | Off | `-honey Y` |
| `-t` | Throttle time for scan (1-5, where 1=5min, 5=80min) | None | `-t 3` |
| `-w` | Seconds to wait between sending signatures | None | `-w 5` |
| `-rg` | Rubber glue mode (tunnels attacks back at intruder) | Off | `-rg` |

## Configuration and Logging

| Option | Description | Default | Example |
|--------|-------------|---------|---------|
| `-Y` | Load configuration from YAML file | None | `-Y config.yaml` |
| `-l` | Log port scanning alerts to a file | None | `-l /path/to/log.log` |
| `-s` | Go-spoof service signature regex file | None | `-s signatures.txt` |

## Option Details

### Port Configuration
- `-p`: Specifies the port that GoSpoof will listen on. This is the port where all redirected traffic will be received.
- `-sP`: Allows you to specify which ports GoSpoof should respond to. Can be a range (1-1000), a list (1,9,32), or a single port.
- `-sT`: Sets up iptables to redirect traffic to a single port. Must be used with `-p` to specify the target port.
- `-r`: When used with `-sT`, specifies the range of ports that iptables should redirect from.

### Advanced Features
- `-honey`: Enables honeypot mode, which logs attacker IPs, timestamps, and payloads to honeypot.log.
- `-t`: Controls scan throttling, with levels 1-5 providing increasing delays (1=5min, 5=80min).
- `-w`: Adds a delay between sending signatures, useful for slowing down scanning tools.
- `-rg`: Enables rubber glue mode, which tunnels attacks back at the intruder.

### Configuration
- `-Y`: Loads configuration from a YAML file, allowing for more complex setups.
- `-l`: Specifies a file to log port scanning alerts.
- `-s`: Allows loading custom service signature patterns from a file.

## Common Usage Examples

### Basic Setup
```bash
# Start with default settings
./goSpoof

# Start on specific port
./goSpoof -p 4444

# Bind to specific IP
./goSpoof -i 192.168.1.100
```

### iptables Configuration
```bash
# Setup iptables redirection
./goSpoof -sT 4444 -p 4444

# Setup with custom port range
./goSpoof -sT 4444 -r "1:1000" -p 4444

# Reset iptables rules
./goSpoof -fT
```

### Port Range Configuration
```bash
# Custom port range
./goSpoof -sP "1-1000" -p 4444

# Specific ports only
./goSpoof -sP "22,80,443" -p 4444
```

### Advanced Configuration
```bash
# Full feature deployment
./goSpoof -D -Y config.yaml -l /var/log/gospoof.log -honey Y

# Maximum throttling
./goSpoof -t 5 -w 10 -honey Y

```

### Specialized Modes
```bash
# Honeypot mode only
./goSpoof -honey Y

# Rubber glue mode (standalone)
./goSpoof -rg

# Verbose debugging
./goSpoof -v -p 4444

# Custom signatures
./goSpoof -s signatures.txt -p 4444
```

## Individual Flag Documentation

For detailed information about each flag, see the individual documentation pages:

### Basic Options
- [[Documentation/Options/Flags/Port|Port (-p)]] - Bind to specific port
- [[Documentation/Options/Flags/IP|IP (-i)]] - Bind to specific IP address  
- [[Documentation/Options/Flags/Verbose|Verbose (-v)]] - Enable verbose mode
- [[Documentation/Options/Flags/Daemon|Daemon (-D)]] - Run as daemon process

### Port Configuration
- [[Documentation/Options/Flags/PortRange|Port Range (-sP)]] - Specify port ranges or lists
- [[Documentation/Options/Flags/iptablesSetup|iptables Setup (-sT)]] - Setup iptables redirection
- [[Documentation/Options/Flags/PortRedirect|Port Redirect (-r)]] - Port range for iptables redirect
- [[Documentation/Options/Flags/iptablesReset|iptables Reset (-fT)]] - Reset iptables rules

### Advanced Features  
- [[Documentation/Options/Flags/Honeypot|Honeypot (-honey)]] - Enable honeypot mode
- [[Documentation/Options/Flags/Throttle|Throttle (-t)]] - Control scan throttling
- [[Documentation/Options/Flags/Wait|Wait (-w)]] - Delay between signatures
- [[Documentation/Options/Flags/RubberGlue|Rubber Glue (-rg)]] - Tunnel attacks back

### Configuration and Logging
- [[Documentation/Options/Flags/YAML|YAML (-Y)]] - Load YAML configuration
- [[Documentation/Options/Flags/LogFile|Log File (-l)]] - Log scanning alerts
- [[Documentation/Options/Flags/Signatures|Signatures (-s)]] - Custom service signatures

## Next Steps

- Try the commands with [[Walkthrough/Basic Usage|Basic Usage workflows]]
- Set up complex configurations with [[Documentation/Configuration|YAML Configuration]]
- Explore advanced combinations in [[Walkthrough/Advanced Usage|Advanced Usage]]

## Additional Reading

- [[Documentation/Troubleshooting|Troubleshooting Guide]] for command issues 