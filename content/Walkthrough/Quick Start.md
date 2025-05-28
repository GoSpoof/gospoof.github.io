# Quick Start Guide

This guide will help you get up and running with GoSpoof quickly.

## Basic Setup

1. Setup iptables to redirect traffic:
```bash
sudo iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1:65535 -j REDIRECT --to-ports 4444
```

2. Start GoSpoof:
```bash
./goSpoof
```

3. Test your setup with nmap:
```bash
nmap localhost
```

## What to Expect

When you run nmap against your system, you should see:
- All ports appearing as open
- Fake service banners for each port
- Delayed responses to slow down scanning
- Logs of the scanning attempts

## Next Steps

- Learn more commands in [[Walkthrough/Basic Usage|Basic Usage]]
- Explore [[Documentation/Options/Options overview|Command Line Options]] for more examples
- Set up [[Documentation/Configuration|YAML Configuration]] for custom services

## Additional Reading

- [[Installation/Installation Guide|Installation Guide]] for complete setup
- [[Documentation/Troubleshooting|Troubleshooting Guide]] if you encounter issues