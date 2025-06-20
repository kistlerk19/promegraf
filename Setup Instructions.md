## Setup Instructions

This project can be implemented on any Linux-based Server. However, this instruction assumes that the server is an AWS EC2 instance running on ubuntu 24.04

### Prerequisite

i) AWS EC2 instance running on ubuntu with git and docker installed.
ii) Basic knowledge of docker, linux cli, prometheus, and grafana

### Sever Setup (Containerized Prometheus, Grafana, and Node Exporter)

- ssh into your EC2 instance
- run ```git clone https://github.com/kistlerk19/promegraf.git```
- run ```sudo docker compose up -d```
- Verify that your containers are running by ```sudo docker compose ps``` You will see a results similar to this:

```bash
 sudo docker ps
CONTAINER ID   IMAGE                        COMMAND                  CREATED          STATUS                          PORTS                                         NAMES
4b7459b15d3a   grafana/grafana-oss:latest   "/run.sh"                45 minutes ago   Up 45 minutes                   0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp   grafana
13ce856d471f   prom/prometheus:latest       "/bin/prometheus --c…"   45 minutes ago   Up 45 minutes                   0.0.0.0:9090->9090/tcp, [::]:9090->9090/tcp   prometheus
adefa567a275   prom/alertmanager:latest     "/bin/alertmanager -…"   45 minutes ago   Restarting (1) 43 seconds ago                                                 alertmanager
cb0f99ad1b0a   prom/node-exporter:latest    "/bin/node_exporter …"   45 minutes ago   Up 45 minutes                   0.0.0.0:9100->9100/tcp, [::]:9100->9100/tcp   node-exporter
```

  - Enter ```admin``` as both the username and password.
  - Update your password when prompted.

### Building the Dashboards

[Follow this blog](https://betterstack.com/community/guides/monitoring/visualize-prometheus-metrics-grafana/#configuring-the-prometheus-data-source) to for a step-by-step guide on building the dashboard.

