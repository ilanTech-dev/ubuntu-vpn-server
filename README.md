# Ubuntu VPN Server

> Building a professional home network using repurposed hardware and open-source software.

---

![Watchman](/images/Watchman.jpg)

## Overview

This repository documents the design, implementation, operation, and ongoing evolution of a professional home network built around **Watchman**, an Ubuntu-based gateway providing VPN services, intelligent routing, DNS management, and network monitoring.

Rather than presenting a collection of configuration files, this project explains the engineering decisions, design trade-offs, and practical lessons learned while designing a secure, maintainable, enterprise-inspired home infrastructure using repurposed hardware and open-source software.

The aim is not simply to explain *what* was built, but *why* each technical decision was made and what was learned along the way.

## Why this project?

Like many people, I had an ageing gaming laptop that no longer met my performance requirements.

Rather than replacing it with dedicated networking hardware, I challenged myself to see how far a repurposed Linux system could go.

The result is Watchman—a gateway that now sits at the heart of my home network.

It provides:

- Router-level VPN for the entire LAN
- Policy-based routing
- Starlink connectivity
- LTE routing for corporate devices
- Local DNS and ad-blocking
- System monitoring and health checks
- A platform for continued learning and experimentationv

## Project Goals

- Build a secure, reliable and maintainable home network.
- Centralise VPN management.
- Secure every LAN device without per-device configuration.
- Support multiple internet connections.
- Route corporate devices independently of the household VPN.
- Repurpose existing hardware.
- Document every significant engineering decision.
-
## Guiding Principles

This project is guided by a small number of engineering principles:

- Prefer open-source software.
- Reuse existing hardware where practical.
- Keep the architecture understandable.
- Document the reasons behind technical decisions.
- Optimise for reliability rather than unnecessary complexity.
- Continuously improve through experimentation.

## Roadmap

The repository is currently being documented and expanded.

Planned topics include:

- Network architecture diagrams
- Complete installation walkthroughs
- WireGuard configuration
- Policy-based routing
- Pi-hole and DNS configuration
- Monitoring and maintenance
- Troubleshooting guides
