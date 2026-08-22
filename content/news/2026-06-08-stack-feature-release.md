---
url: https://www.ethernexion.com/news/stack-feature-release
title: "Stack Feature release"
type: Press Release
date: 2026-06-08
cover: https://www.ethernexion.com:8001/media/images/BinaryStarShiFouWeiDanCi.width-640.png
fetched: 2026-08-22
---

[← Back to News](https://www.ethernexion.com/news)

Stacking feature technology combines multiple physical switches into a single logical entity, enabling centralized management through unified configuration, enhanced reliability via cross-device redundancy with automatic failover, and flexible scalability through linear port/bandwidth expansion—all while maintaining synchronized forwarding tables (MAC/IP) and streamlined operations.

### Key Benefits of Stacking:

✔ Cost-effective – No need for expensive chassis switches

✔ Highly available – Redundant architecture with fast failover

✔ Scalable – Expand ports/bandwidth by adding members

✔ Simplified management – Unified control plane for the entire stack

Ethernexion launched this stacking functionality in Q2 2025, now supported in the new E-NOS version V3.0.18 for both S5 and S7 series products.

#### Technical Background

Ethernet switches come in two form factors: box-style and chassis-style.

- Box-style switches offer low cost but lack high availability and uninterrupted service protection, making them unsuitable for critical scenarios.
- Chassis-style switches deliver high performance, high port density, and high availability, making them ideal for mission-critical deployments—but they come with high upfront costs and elevated per-port pricing.

Stacking technology bridges these two approaches by combining their advantages.

By connecting multiple devices through stacking ports, stacking creates a single virtual logical device. Managing this virtual device allows centralized control of all stack members. This hybrid solution retains the cost efficiency of box-style switches while delivering the scalability and high reliability of chassis-style distributed systems.

![](https://www.ethernexion.com:8001/media/original_images/Centralized.webp)

#### How to implement

Stacking Implementation Process

1. Physical Connection:

   - Member switches are interconnected via dedicated stacking ports using either:

     - Daisy-chain (linear) topology
     - Ring topology (recommended for higher reliability)

1. Role Assignment:

   - The system automatically elects one device as the Master (manages the entire stack) and others as Slaves (execute control-plane commands).
   - Role election is dynamic and adjusts upon topology changes (e.g., Master failure triggers re-election).

1. Data Forwarding:

   - Traffic flows through logical stacking links, with deterministic forwarding paths based on the topology.
   - Ring topologies enable bidirectional traffic for higher bandwidth utilization.

![](https://www.ethernexion.com:8001/media/original_images/Virtualized-switches.png)

#### How to configure

The following network example shows a ring stack system

- Devices: Access switches Switch1-Switch5 form a 100G ring topology via uplink optical ports.
- Purpose: Ensures high reliability for access-layer networks through stacking.
- Stacking Roles:

  - Master: Switch1 (priority 200)
  - Backup Masters: Switch2 (190), Switch3 (180), Switch4 (170), Switch5 (160)
- Stacking Ports: eth-0-23 to eth-0-26 on each switch.

![](https://www.ethernexion.com:8001/media/original_images/Topo_Example.webp)

![](https://www.ethernexion.com:8001/media/original_images/c6a9d7e844e5812f4ea9923531bae8d2_citF5BJ.png)

Stack Feature release · EtherNexion
