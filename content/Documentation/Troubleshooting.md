# Troubleshooting Guide

This guide covers common issues and their solutions when using GoSpoof.

## Common Issues

### 1. Port Binding Issues

#### Error: "Address already in use"
```bash
Error: listen tcp :4444: bind: address already in use
```

**Solution:**
1. Check if another process is using the port:
```bash
sudo lsof -i :4444
```
2. Kill the process or choose a different port:
```bash
./goSpoof -p 4445
```

### 2. iptables Configuration

#### Error: "Permission denied"
```bash
Error: permission denied when setting up iptables
```

**Solution:**
1. Run with sudo:
```bash
sudo ./goSpoof -sT 4444
```
2. Or manually configure iptables:
```bash
sudo iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1:65535 -j REDIRECT --to-ports 4444
```

#### Error: "Traffic not redirecting"
**Solution:**
1. Reset iptables:
```bash
./goSpoof -fT
```
2. Reconfigure iptables:
```bash
./goSpoof -sT 4444
```

### 3. Logging Issues

#### Error: "Cannot write to log file"
```bash
Error: cannot write to log file: permission denied
```

**Solution:**
1. Check file permissions:
```bash
sudo chown $USER:$USER /path/to/logfile.log
```
2. Ensure directory exists:
```bash
sudo mkdir -p /var/log/gospoof
sudo chown $USER:$USER /var/log/gospoof
```

### 4. Honeypot Mode Issues

#### Error: "Honeypot mode not working"
**Solution:**
1. Ensure correct flag usage:
```bash
./goSpoof -honey Y
```
2. Check log file permissions if using `-l`:
```bash
./goSpoof -honey Y -l /var/log/gospoof/honeypot.log
```

### 5. Port Range Configuration

#### Error: "Invalid port range"
**Solution:**
1. Check port range format:
```bash
# Correct format
./goSpoof -sP "1-1000"
./goSpoof -sP "22,80,443"

# Incorrect format
./goSpoof -sP "1 to 1000"
./goSpoof -sP "22 80 443"
```

2. Verify iptables port range format:
```bash
# Correct format
./goSpoof -sT 4444 -r "1:1000"

# Incorrect format
./goSpoof -sT 4444 -r "1-1000"
```

### 6. Rubber Glue Mode

#### Error: "Rubber glue mode not working"
**Solution:**
1. Ensure it's used as a standalone flag:
```bash
# Correct usage
./goSpoof -rg

# Incorrect usage
./goSpoof -rg -honey Y
```

## Configuration Issues

### 1. YAML Configuration Errors

**Symptoms:**
- Configuration not loading
- Invalid configuration errors

**Solutions:**
1. Validate YAML syntax:
```bash
yamllint config.yaml
```

2. Check configuration format:
```yaml
# Correct format
services:
  - port: 22
    banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"

# Incorrect format
services:
  port: 22
  banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"
```

### 2. Service Response Issues

**Symptoms:**
- Incorrect service banners
- Missing responses

**Solutions:**
1. Verify service configuration:
```yaml
services:
  - port: 22
    banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"
```

2. Test individual services:
```bash
nc -v localhost 22
```

## Network Issues

### 1. Connection Problems

**Symptoms:**
- Can't connect to GoSpoof
- Port not responding

**Solutions:**
1. Check firewall rules:
```bash
sudo iptables -L
```

2. Verify port binding:
```bash
netstat -tulpn | grep goSpoof
```

## Getting Help

If you're still experiencing issues:

1. Check the [[Documentation/Configuration|Configuration Guide]]
2. Review [[Walkthrough/Basic Usage|Basic Usage]]
3. Visit the [GitHub Issues](https://github.com/blackhillsinfosec/GoSpoof/issues)
4. Join the [Black Hills InfoSec Discord](https://discord.gg/blackhillsinfosec)

## Additional Reading

- [[Documentation/Options/Options overview|Command Line Options]]
- [[Walkthrough/Advanced Usage|Advanced Usage Guide]]
- [[Documentation/Configuration|Configuration Guide]]
