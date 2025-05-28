---
title: Advanced Usage
---
This guide focuses on advanced usage scenarios and combinations of GoSpoof features. For basic command usage, see [[Documentation/Options/Options overview|Command Line Options]].

## Advanced Scenarios

For specific command examples, see the [[Documentation/Options/Options overview#Common Usage Examples|Command Line Options Examples]].

### 1. Full Feature Configuration (`-D`, `-Y`, `-l`, `-honey`)

Combine multiple features for comprehensive deployment by using daemon mode, configuration files, detailed logging, and honeypot tracking together. This approach provides:
- Background operation for continuous protection (`-D`)
- Custom service configurations for realistic deception (`-Y`)
- Comprehensive logging for analysis (`-l`)
- Attack tracking and intelligence gathering (`-honey`)

### 2. Maximum Delay Configuration (`-t`, `-w`, `-honey`)

Maximize time wasting and tracking capabilities by combining the highest throttle settings with signature delays and honeypot mode. This setup:
- Uses maximum throttle time (80 minutes for level 5) (`-t 5`)
- Adds significant delays between signatures (`-w`)
- Tracks all scanning attempts for intelligence (`-honey`)

### 3. Custom Service Deployment (`-Y`, `-sP`)

Create a configuration file (`services.yaml`):
```yaml
services:
  - port: 22
    banner: "SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5"
  - port: 3389
    banner: "RDP"
```

Deploy this configuration using the YAML file (`-Y`) with appropriate port settings (`-sP`). See the [[Documentation/Options/Options overview#Common Usage Examples|Command Line Options Examples]] for deployment commands.

## Advanced Techniques

For specific command examples, see the [[Documentation/Options/Options overview#Common Usage Examples|Command Line Options Examples]].

### 1. Port Range Management (`-sT`, `-r`, `-sP`)

Combine port range configuration with iptables redirection to control exactly which ports are monitored and how traffic is routed. This allows for targeted deception on specific services or port ranges using `-sT` for iptables setup, `-r` for redirect ranges, and `-sP` for response ports.

### 2. Time Wasting Strategies (`-t`, `-w`)

Combine throttling and signature delays to maximize the time attackers spend scanning your system. This approach forces attackers to be more aggressive and visible using `-t` for throttling levels and `-w` for signature delays.

### 3. Rubber Glue Mode (`-rg`)

Use rubber glue mode for advanced attack redirection that tunnels attacks back to the intruder. Note: This is a standalone mode (`-rg`) that cannot be combined with other options.

## Next Steps

- Create custom [[Documentation/Configuration|YAML configurations]] for your scenarios
- Reference specific [[Documentation/Options/Options overview|Command Line Options]] for implementation
- Check [[Documentation/Troubleshooting|Troubleshooting Guide]] for complex setup issues

## Additional Reading

- [[Walkthrough/Basic Usage|Basic Usage]] if you need to review fundamentals
- Individual flag documentation: [[Documentation/Options/Flags/Throttle|Throttle]], [[Documentation/Options/Flags/Wait|Wait]], [[Documentation/Options/Flags/RubberGlue|Rubber Glue]], etc.