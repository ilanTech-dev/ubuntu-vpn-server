# Hardware Platform

---

## Purpose

Before selecting software, it is worth considering the platform it will run on.

This project deliberately reuses consumer hardware rather than purpose-built networking equipment.

The goal is not only to reduce cost, but also to demonstrate that reliable home infrastructure can be built using hardware that many people already own.

---

## Why a Gaming Laptop?

Watchman began life as a gaming laptop.

As newer games became more demanding, the hardware gradually reached the point where it was no longer the ideal gaming machine.

Despite this, it remained an extremely capable Linux server.

Repurposing the laptop offered several advantages over purchasing dedicated networking hardware.

![Watchman](../images/Watchman.jpg)

---

## Advantages

### Excellent processing power

Modern VPNs rely heavily on CPU performance for encryption.

Compared with most consumer routers, even an ageing gaming laptop provides significantly greater processing capability.

This allows WireGuard encryption, DNS services, monitoring, and future applications to run simultaneously without becoming CPU-bound.

---

### Built-in battery

One unexpected advantage of using a laptop is its integrated battery.

Short power interruptions do not immediately interrupt internet connectivity, providing a level of resilience normally associated with an uninterruptible power supply (UPS).

---

### Low power consumption

Although considerably more powerful than a Raspberry Pi or typical router, a laptop remains relatively efficient when running continuously.

Power management features allow the system to operate quietly and reliably 24 hours a day.

---

### Integrated display and keyboard

Unlike many small servers, initial installation and troubleshooting can be performed directly on the machine without requiring separate peripherals.

Once configured, administration is performed remotely over SSH.

---

### Storage

Consumer laptops generally include fast SSD storage.

This provides excellent reliability and ample capacity for logs, monitoring data, backups, and future services.

---

## Hardware Specification

| Component        | Specification                  |
| ---------------- | ------------------------------ |
| Hostname         | Watchman                       |
| Operating System | Ubuntu Server LTS              |
| Platform         | Repurposed Gaming Laptop       |
| CPU              | Intel Core i7-4720HQ @ 2.60GHz |
| RAM              | 8GB DDR3L 1600MHz              |
| Storage          | 128GB mSATA Solid State Drive  |
| Primary WAN      | Starlink                       |
| Secondary WAN    | LTE                            |
| VPN              | WireGuard                      |
| DNS              | Pi-hole + dnsmasq              |

---

## Evolution

Watchman was not designed in its final form.

Initially it existed solely as a WireGuard gateway.

As new requirements emerged—including policy-based routing, Pi-hole, LTE connectivity, and monitoring—the system evolved into the central infrastructure platform that it is today.

## Why not...

### Raspberry Pi?

Excellent hardware for many projects.

However, Watchman was expected to become the primary gateway for an entire household while also providing VPN encryption, DNS filtering, monitoring, and room for future expansion.

The additional processing power of the laptop provides considerably greater headroom.

---

### Consumer Router?

Most consumer routers offer VPN functionality.

However, they typically provide limited flexibility, restricted software ecosystems, and significantly less processing power than a general-purpose Linux system.

---

## Lessons Learned

- Existing hardware often has considerable useful life beyond its original purpose.
- Consumer laptops make excellent always-on Linux servers.
- Integrated batteries provide an unexpected resilience benefit.
- Designing for future expansion avoided early hardware limitations.
