---
title: Configuration Guide
---
This guide covers all configuration options available in GoSpoof, from basic setup to advanced customization.

## Basic Configuration

For a complete list of command line options, see [[Documentation/Options/Options overview|Command Line Options]].

For a quick start guide, see [[Walkthrough/Quick Start|Quick Start]].

## YAML Configuration

GoSpoof supports configuration through YAML files. Here's an example configuration:

```yaml
# Basic Configuration
port: 4444
ip: "192.168.1.100"
verbose: true

# Port Range Configuration
port_range:
  start: 1
  end: 65535

# Honeypot Settings
honeypot:
  enabled: true
  log_file: "/var/log/gospoof/honeypot.log"

# Logging Configuration
logging:
  enabled: true
  file: "/var/log/gospoof/gospoof.log"
  level: "info"

# Service Responses
services:
  - port: 22
    banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"
  - port: 80
    banner: "HTTP/1.1 200 OK\r\nServer: nginx/1.18.0"
```

## Advanced Configuration

### Custom Service Responses

You can customize the responses for specific ports:

```yaml
services:
  - port: 22
    banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"
    response_delay: 0.5
  - port: 80
    banner: "HTTP/1.1 200 OK\r\nServer: nginx/1.18.0"
    response_delay: 0.2
```

### Logging Configuration

Configure detailed logging:

```yaml
logging:
  enabled: true
  file: "/var/log/gospoof/gospoof.log"
  level: "info"
  rotation:
    max_size: 100MB
    max_backups: 5
    max_age: 30
```

## Environment Variables

GoSpoof also supports configuration through environment variables:

```bash
export GOSPOOF_PORT=4444
export GOSPOOF_IP=192.168.1.100
export GOSPOOF_CONFIG=/path/to/config.yaml
```

## Next Steps

- Apply configurations with [[Documentation/Options/Options overview|Command Line Options]]
- See configuration examples in [[Walkthrough/Advanced Usage|Advanced Usage]]
- Test your setup with [[Walkthrough/Basic Usage|Basic Usage]] patterns

## Additional Reading

- [[Documentation/Options/Flags/YAML|YAML Flag Documentation]] for `-Y` option details
- [[Documentation/Troubleshooting|Troubleshooting Guide]] for configuration issues
