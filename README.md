# Real-Time Smart Machine Monitoring & Alert System (IoT + Analytics POC)

A Dockerized Industrial IoT proof-of-concept that simulates machine sensor readings (temperature & vibration), streams them via MQTT, stores time-series data in InfluxDB, and visualizes real-time analytics using Grafana dashboards with anomaly alerts.

## Architecture / Data Flow
Node-RED (Simulator) ➝ MQTT (Mosquitto) ➝ Node-RED (Subscriber/Processor) ➝ InfluxDB ➝ Grafana

## Features
- Simulated multi-machine sensor data (M1, M2, M3)
- Real-time dashboard (Refresh: 5s, Time range: last 5 minutes)
- Temperature & vibration gauges per machine
- Overall trend graphs for all machines
- OK / ALERT status LED panel per machine
- Alerts table (High Temperature / High Vibration)

## Tech Stack
Node-RED • MQTT (Mosquitto) • InfluxDB • Grafana • Docker

## Run Locally
```bash
docker-compose up -d


✅ Now **paste this below it**:

```md
## URLs
- Node-RED: http://localhost:1880  
- Grafana: http://localhost:3000 *(default: admin/admin)*  
- InfluxDB: http://localhost:8086  

## Import Files

### Node-RED
Menu → Import → Clipboard → paste `node_red_flow.json` → Deploy  

### Grafana
Dashboards → New → Import → Upload `grafana_dashboard.json`  

## InfluxDB Measurements (Database: iot_data)
- `machine_metrics`: temperature, vibration, status *(for all machines)*
- `machine_alerts`: issue, temperature, vibration, status *(only alerts)*
