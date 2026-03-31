## Step 1: Add Grafana Repository

```sh
sudo vi /etc/yum.repos.d/grafana.repo
```
📄 Paste the following:
[grafana]
name=Grafana
baseurl=https://rpm.grafana.com
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://rpm.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
📥 Step 2: Install Required Packages
sudo yum install -y wget ca-certificates
🔄 Step 3: Update Certificates
sudo update-ca-trust
🔐 Step 4: Import Grafana GPG Key
wget -q -O gpg.key https://rpm.grafana.com/gpg.key
sudo rpm --import gpg.key
⚙️ Step 5: Install Grafana
sudo yum install grafana -y
▶️ Step 6: Start Grafana Service
sudo systemctl daemon-reexec
sudo systemctl enable grafana-server
sudo systemctl start grafana-server
sudo systemctl status grafana-server
🌐 Access Grafana
http://<your-server-ip>:3000

Default Login:

Username: admin
Password: admin
