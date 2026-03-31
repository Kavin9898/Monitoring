## 1. Download Promtail
```SH
wget https://github.com/grafana/loki/releases/download/v2.9.8/promtail-linux-amd64.zip
unzip promtail-linux-amd64.zip
chmod +x promtail-linux-amd64
sudo mv promtail-linux-amd64 /usr/local/bin/promtail
```

## 2. Create Promtail Config File
```SH
nano promtail-config.yml
```
```SH
server:
  http_listen_port: 9080  # Promtail’s local API, does NOT affect Loki forwarding
  grpc_listen_port: 0

positions:
  filename: /tmp/positions.yaml

clients:
  - url: http://54.165.147.35:3100/loki/api/v1/push  # CHANGE THE IP

scrape_configs:
- job_name: system
  static_configs:
  - targets:
      - localhost
    labels:
      job: varlogs
      __path__: /var/log/*.log
      logtype: system

- job_name: log-gen
  static_configs:
  - targets:
      - localhost  # Keep it localhost if logs are on the same node
    labels:
      job: applog
      __path__: /opt/*.log                       ## (OUTPUT PATH FILE (PWD))
      logtype: application
```
