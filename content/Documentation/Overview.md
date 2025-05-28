---
title: GoSpoof Overview
---
GoSpoof is a cyber deception tool designed to protect your systems from port scanning and reconnaissance activities. It works by creating deceptive responses to port scans, making it difficult for attackers to accurately map your network.

## What is GoSpoof?

GoSpoof is a Go-based implementation of port spoofing technology, inspired by the original portspoof tool. It provides a more modern, efficient, and feature-rich approach to port spoofing.

## Key Concepts

### Port Spoofing
Port spoofing is a defensive technique that responds to port scans with deceptive information. Instead of revealing the true state of your ports, GoSpoof provides false responses that can mislead attackers.

### Deception

GoSpoof uses various deception techniques to:
- Provide false service banners
- Create fake open ports
- Generate realistic but fake responses
- Track and log scanning attempts

## Real World Example

To see GoSpoof in action, you can scan bhis.tech:
```bash
nmap -p1-100 bhis.tech
```

This will demonstrate how GoSpoof makes all ports appear open with fake service banners, effectively wasting an attacker's time and forcing them to be more aggressive in their scanning attempts.

## Use Cases

GoSpoof is particularly useful for:
- Defending against reconnaissance by making all ports appear open
- Forcing attackers to be more aggressive and visible in their scanning attempts
- Wasting attacker time and resources with deceptive responses
- Gathering intelligence about scanning patterns and techniques

## Next Steps

To get started with GoSpoof:
1. Follow the [[Installation/Installation Guide|Installation Guide]]
2. Try the [[Walkthrough/Quick Start|Quick Start Guide]]
3. Learn [[Walkthrough/Basic Usage|Basic Usage]] patterns

## Additional Reading

- [[Documentation/Options/Options overview|Command Line Options]] for all available flags
- [[Documentation/Configuration|Configuration Guide]] for YAML setup

