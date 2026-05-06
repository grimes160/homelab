# Homelab

A self-hosted infrastructure project built for hands-on DevOps and
platform engineering practice.

**Goals:** 

Build production-style discipline across IaC, monitoring,
CI/CD, and AI/automation tooling. 

---

## Hardware

| Device | Role | Specs |
|---|---|---|
| HP EliteDesk G6 Mini | Hypervisor | i5 10th gen / 16GB RAM / 256GB SSD + 10TB HDD |
| ASUS ZenWiFi XT9 | Router / Mesh AP | Gateway: 192.168.50.1 |
| TP-Link SG108 | Unmanaged switch | 8-port, 1 GbE |
| TP-Link SG108PE | PoE switch | 8-port, powers IoT devices |
| Philips Hue Bridge V1 | Zigbee coordinator | Smart home / IoT segment |

---

## Stack

**Hypervisor:** Proxmox VE 8 — `192.168.50.10`

| Container | Service | IP | Role |
|---|---|---|---|
| CT100 | Pi-hole | 192.168.50.20 | Network-wide DNS filtering + ad-block |
| CT101 | Unbound | 192.168.50.21:5335 | Recursive DNS resolver (no upstream dependency) |
| CT102 | Tailscale | 192.168.50.22 | Zero-trust VPN / subnet router for remote access |
| CT103 | Grafana + Prometheus | 192.168.50.23:3000 | Observability stack — metrics for all hosts |

---

## Architecture

See [`diagrams/network-architecture.mmd`](diagrams/network-architecture.mmd)
for the full network topology in Mermaid format (renders on GitHub).

## About Me

Technology consultant with 10+ years bridging engineering teams and
business stakeholders — delivery, sprint execution, process optimization.
Building this lab to move from adjacent-to-engineering into hands-on
DevOps and platform engineering roles.

Target: DevOps Engineer / Platform Engineer / AI-Ops
