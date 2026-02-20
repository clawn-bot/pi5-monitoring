# Pi 5 Monitoring & Health Stack

Standalone monitoring and SSD health stack for the Pi 5.

## 📁 Infrastructure Compliance
- **Compose/Config Location:** `/mnt/pinas1/docker/pi5-monitoring`
- **Bulk Data (Prometheus/Grafana/Scrutiny):** `/mnt/pinas2/monitoring-data`

## 📦 Services Included
1. **Prometheus (9090):** Metrics time-series database.
2. **Node Exporter (9100):** Hardware metrics (CPU, Temp, RAM).
3. **Grafana (3001):** Visualization dashboard.
4. **Scrutiny (8081):** S.M.A.R.T. SSD Health Monitoring.

## 🚀 One-Command Deployment
```bash
# SSH to Pi 5
cd /mnt/pinas1/docker/
# Ensure you've created a git repo from this folder or copy the files
cd pi5-monitoring
docker compose up -d
```

## 🛡️ SSD Health (Scrutiny)
The omnibus container monitors `/dev/sda` and `/dev/sdb` (your two SSDs) and provides a dashboard at `http://<pi-ip>:8081`.

## 📊 Dashboard Recommendation
After logging into Grafana (`admin`/`admin` at port 3001), add Prometheus (`http://prometheus:9090`) as a data source and import **Dashboard ID: 1860** (Node Exporter Full) for a professional Pi 5 overview.
