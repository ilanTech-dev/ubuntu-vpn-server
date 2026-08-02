# Project Vision

---

## Why this project exists

Watchman began as a simple idea:

Can an ageing gaming laptop be transformed into the heart of a reliable, secure, and maintainable home network?

The answer turned out to be yes.

What started as an experiment in running a router-level VPN gradually evolved into something much larger: a complete home infrastructure platform responsible for internet connectivity, secure routing, DNS services, network monitoring, and future automation.

This repository documents that journey.

It is not intended to be the definitive guide to Linux networking, nor does it claim to present the only or "best" solution.

Instead, it explains the engineering decisions, practical trade-offs, mistakes, and lessons learned while designing and operating a home network inspired by professional infrastructure principles.

---

## The Problem

Modern homes often contain dozens of internet-connected devices.

Installing and maintaining VPN software, DNS filtering, and security settings individually across every device quickly becomes difficult to manage.

At the same time, reliable internet access has become essential for both work and everyday life.

Watchman was designed to centralise those responsibilities into a single Linux gateway that could provide secure, flexible, and resilient networking for the entire household.

---

## Project Objectives

The project has several primary objectives:

- Build a secure, reliable, and maintainable home network.
- Centralise VPN management at the network level.
- Route all LAN traffic through a secure VPN by default.
- Allow selected devices to bypass the VPN when required.
- Support multiple internet connections and intelligent routing.
- Reuse existing hardware wherever practical.
- Minimise operating costs through open-source software.
- Document every significant engineering decision.

---

## Design Principles

Every design decision within this project is guided by a small number of principles.

### Simplicity

Complexity is introduced only when it provides a clear benefit.

Whenever possible, solutions should be understandable, maintainable, and easy to troubleshoot.

### Reliability

A solution that works consistently is preferable to one that is technically clever but difficult to support.

### Transparency

Every major technical decision should be documented together with the reasoning behind it.

Future readers—including my future self—should understand not only *what* was done, but *why*.

### Open Source

Where practical, open-source software is preferred over proprietary alternatives.

This provides flexibility, transparency, and long-term sustainability.

### Continuous Improvement

This project is not considered "finished."

As new ideas emerge and new technologies become available, Watchman will continue to evolve.

---

## Current Scope

At the time of writing, Watchman provides:

- Router-level WireGuard VPN
- Policy-based routing
- Starlink internet connectivity
- LTE routing for selected devices
- Local DNS services
- Network-wide ad blocking
- Network monitoring and health checks
- A platform for future home automation services

---

## What this repository is

This repository is intended to be:

- Documentation
- A learning resource
- An engineering journal
- A reference for future deployments

It deliberately focuses on design decisions as much as implementation details.

Configuration files are important.

Understanding *why* they exist is even more important.

---

## Future Direction

Watchman will continue to evolve alongside the home network it supports.

Future areas of exploration may include:

- Infrastructure monitoring
- Automated backups
- Containerised services
- Network visualisation
- High availability
- IPv6
- Additional security hardening

As the project grows, this repository will grow with it.

The goal is not merely to build a VPN server.

The goal is to build a home network that is reliable, understandable, maintainable, and enjoyable to engineer.
