---
title: Installation Guide
---
This guide will walk you through the process of installing and setting up GoSpoof on your system.

## Prerequisites

Before installing GoSpoof, ensure you have:
- Go 1.16 or later installed
- Root/Administrator privileges
- Basic understanding of networking concepts

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/blackhillsinfosec/GoSpoof.git
cd GoSpoof
```

### 2. Build GoSpoof

Navigate to the source directory and build the executable:

```bash
cd src
go build -o goSpoof
```

### 3. Setup iptables (Linux)

To redirect traffic to GoSpoof, run either:

```bash
./goSpoof -sT 4444
```

Or manually:

```bash
sudo iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1:65535 -j REDIRECT --to-ports 4444
```

### 4. Move to Bin Directory

```bash
cp ./goSpoof /usr/local/bin/
```

## Configuration

After installation, you'll need to configure GoSpoof. See the [[Documentation/Configuration|Configuration Guide]] for detailed instructions.

## Verification

To verify your installation:

1. Start GoSpoof:
```bash
./goSpoof
```

2. Test with a port scan (must be done from a separate machine):
```bash
nmap IP
```

## Common Issues

If you encounter any issues during installation, check the [[Documentation/Troubleshooting|Troubleshooting Guide]].

## Next Steps

- Try the [[Walkthrough/Quick Start|Quick Start Guide]] for immediate testing
- Learn [[Walkthrough/Basic Usage|Basic Usage]] commands and workflows
- Set up [[Documentation/Configuration|YAML Configuration]] for custom deployments

## Additional Reading
- [[Documentation/Troubleshooting|Troubleshooting Guide]] for installation issues
- [[Documentation/Options/Options overview|Command Line Options]] for all available flags