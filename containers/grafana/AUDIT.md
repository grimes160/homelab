
## 2026-05-05: Expanded monitoring to all homelab hosts

Installed prometheus-node-exporter on the Proxmox hypervisor and on
CT100 (Pi-hole), CT101 (Unbound), CT102 (Tailscale). Updated
prometheus.yml to scrape all five hosts under a single 'node' job
with friendly host and role labels.

Architecture now:
- Hypervisor tier: proxmox-host (192.168.50.10)
- DNS tier: pihole (50.20), unbound (50.21)
- VPN tier: tailscale (50.22)
- Monitoring tier: grafana (50.23)

Imported Grafana dashboard 1860 (Node Exporter Full) for unified
visibility across all hosts. Adjusted dashboard variables to use
the 'host' label for human-readable target selection.

Result: single-host monitoring stack extended into a multi-target
observability platform covering hypervisor, DNS infrastructure, and
VPN tier. Pi-hole application metrics continue to flow via the
existing pihole-exporter on the dedicated 'pihole' job.
