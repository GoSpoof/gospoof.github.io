# Basic Usage

This guide covers the basic usage of GoSpoof, including common commands and examples.

## Starting GoSpoof

### Basic Start
Start GoSpoof with default settings (port 4444).
```bash
./goSpoof
```

### Specify Port
Bind GoSpoof to a specific port number.
```bash
./goSpoof -p 4444
```

### Bind to Specific IP
Bind GoSpoof to a specific IP address.
```bash
./goSpoof -i 192.168.1.100
```

## Common Commands

GoSpoof offers many command line options for different use cases. Here are the most commonly used commands:

- **Setup iptables** (`-sT`): Configure traffic redirection 
- **Port configuration** (`-sP`): Define port ranges and specific ports
- **Configuration files** (`-Y`): Load YAML configuration files
- **Logging** (`-l`, `-v`): Enable detailed logging and verbose output
- **Background operation** (`-D`): Run as daemon process
- **Security features** (`-honey`): Enable honeypot mode for tracking
- **Performance tuning** (`-w`, `-t`): Add delays and throttling
- **Special modes** (`-rg`): Use rubber glue mode for attack redirection

For complete command examples and usage patterns, see the [[Documentation/Options/Options overview#Common Usage Examples|Command Line Options Examples]] section.

## Basic Scenarios

This section covers common usage patterns. For specific command examples, see the [[Documentation/Options/Options overview#Common Usage Examples|Command Line Options Examples]].

### 1. Simple Port Scanning Defense
Start GoSpoof to defend against basic port scans by making all ports appear open with fake services. Use basic options like `-p` for port binding and `-i` for IP binding.

### 2. Advanced Deployment (`-D`, `-Y`, `-l`, `-honey`)
Combine multiple features like daemon mode, configuration files, logging, and honeypot tracking for comprehensive deployment.

### 3. Maximum Delay Configuration (`-t`, `-w`, `-honey`)
Use throttling and wait delays to significantly slow down scanning tools and waste attacker time.

## Logging

Record port scanning alerts to a file.
```bash
./goSpoof -l /path/to/logfile.log
```

## Next Steps

- Progress to [[Walkthrough/Advanced Usage|Advanced Usage]] for complex scenarios
- Set up [[Documentation/Configuration|YAML Configuration]] for custom services
- Reference [[Documentation/Options/Options overview|Command Line Options]] for detailed examples

## Additional Reading

- [[Documentation/Troubleshooting|Troubleshooting Guide]] for common issues
- [[Installation/Installation Guide|Installation Guide]] if you need setup help
