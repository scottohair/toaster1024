# Enterprise Deployment Architecture

## Overview
The Toaster1024 enterprise deployment includes:

- Rust TCP Orchestrator running in Kubernetes
- SCADA (Node.js + Web) served via ingress
- TimescaleDB for telemetry
- MQTT broker for lane + SM messaging
- Prometheus for metrics
- Grafana dashboards
- OTA Firmware delivery to SM modules

## Microservices
- tcp-api: Rust gRPC/REST controller
- telemetry-ingest: MQTT → TimescaleDB
- firmware-server: signed firmware delivery
- scada-ui: Node/React dashboard

## Networking
- Industrial Ethernet per rack
- Redundant 48V power distribution
- Control-plane VLANs
