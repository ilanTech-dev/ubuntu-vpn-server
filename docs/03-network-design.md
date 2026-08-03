# Network Design

---

## Purpose

A network gateway is more than a VPN server.

It becomes the point through which every device communicates with the outside world and, as such, influences the security, reliability, and maintainability of the entire network.

This chapter describes the architectural principles behind Watchman and explains how the various components of the home network work together.

Configuration details are intentionally left to later chapters. The objective here is to understand the overall design before discussing implementation.

---

## Design Philosophy

Watchman was designed around a simple philosophy:

> Move complexity away from client devices and into the network infrastructure, where it can be configured once, documented once, and maintained consistently.

Rather than configuring VPN clients, DNS servers, and routing rules on every individual device, those responsibilities are centralised within a single Linux gateway.

This approach provides:

- Consistent behaviour across the network
- Simplified administration
- Improved security
- Easier troubleshooting
- A scalable foundation for future expansion

---

## High-Level Architecture

```text
                          Internet
                               │
               ┌───────────────┴───────────────┐
               │                               │
           Starlink                        LTE Modem
         Primary WAN                    Secondary WAN
               │                               │
               └───────────────┬───────────────┘
                               │
                        ┌──────────────┐
                        │  Watchman    │
                        │ Ubuntu Linux │
                        └──────┬───────┘
                               │
                     Archer AX55 (WAP Mode)
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
    Wired LAN            Trusted WLAN            IoT Network
```

Watchman acts as the central routing, VPN, DNS, and policy engine for the entire home network.

The Archer AX55 operates purely as a wireless access point. All routing decisions are performed by Watchman.

---

## Network Roles

The home network is divided into logical groups based on function rather than physical location.

### Internet Connectivity

Two independent internet connections are available.

**Starlink**

The primary internet connection used by the household.

**LTE**

A secondary connection primarily used for policy-based routing and future resilience.

---

### Watchman Gateway

Watchman performs the core infrastructure functions of the network, including:

- Router
- WireGuard VPN gateway
- Policy-based routing
- Local DNS
- DHCP
- Network monitoring
- Platform for future infrastructure services

Every client device communicates through Watchman before reaching the internet.

---

### Wireless Infrastructure

Wireless connectivity is provided by an Archer AX55 configured in Wireless Access Point (WAP) mode.

This separates wireless networking from routing responsibilities.

Coverage throughout the property is extended using two TP-Link RE650 mesh range extenders.

One extender provides coverage within the house while the second serves the workshop.

---

## Network Segments

### Wired LAN

The wired network provides reliable connectivity for fixed infrastructure devices.

Current wired devices include:

- Samsung Smart TV
- Philips Hue Hub
- MSI Cubi workstation
- TP-Link RE650 Mesh Extenders

---

### Trusted Wireless LAN

Trusted devices are connected to the primary wireless network.

Current devices include:

- Katana Linux workstation
- MintBox workstation
- Work laptop
- Gaming PC (via OpenWRT wireless bridge)
- Samsung Galaxy S24
- Samsung Galaxy Tab A8

These devices have unrestricted access to local network resources.

---

### IoT Network

Internet of Things devices are isolated on a dedicated wireless network.

This group includes:

- Worx Landroid robotic lawn mower
- Roborock S7 robotic vacuum
- Tibber Pulse energy monitor
- Wilfa bedroom air purifier
- Electrolux living room air purifier
- Mill Socket G2 (Chicken Coop heating)
- Mill Socket G3 (Living Room heating)
- Mill Socket G3 (Dining Room heating)
- Mill Socket G3 (Basement heating)

Although these devices require internet access, they generally do not require unrestricted access to trusted computers and servers.

Separating IoT devices into their own network improves security while simplifying future access control policies.

---

## Traffic Policies

One of the primary design objectives is to centralise routing decisions.

The default policy is:

- All client devices access the internet through the WireGuard VPN.
- Selected devices may bypass the VPN where operational requirements demand it.
- Corporate devices may be routed via the LTE connection rather than the household internet connection.

These policies are implemented centrally by Watchman, requiring no VPN configuration on individual client devices.

---

## Design Trade-offs

Every engineering decision involves compromise.

Choosing a Linux gateway instead of a consumer router increases flexibility but also increases system complexity.

Similarly, maintaining separate trusted and IoT networks introduces additional administration while providing significant security benefits.

The objective throughout this project is not to eliminate complexity entirely, but to concentrate it within the infrastructure where it can be managed consistently.

---

## Lessons Learned

- Centralising network services dramatically simplifies client configuration.
- Separating infrastructure responsibilities produces a cleaner architecture.
- Consumer networking hardware performs best when dedicated to switching and wireless access.
- Linux provides a level of flexibility difficult to achieve with consumer routers.
- Designing around future expansion avoids costly architectural changes later.
