# Configure SonarQube


```bash
#Create a system service file for sonar
sudo vim /etc/systemd/system/sonarqube.service
```

```bash
[Unit]
Description=SonarQube service
After=syslog.target network.target

[Service]
Type=forking
ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop
User=sonarqube
Group=sonarqube
Restart=always
LimitNOFILE=131072
LimitNPROC=8192

[Install]
WantedBy=multi-user.target
```

```bash
# Reload and start the service
sudo systemctl daemon-reload
sudo systemctl start sonarqube.service
sudo systemctl enable sonarqube.service
```


```bash
# Restart the service
sudo systemctl restart sonarqube
```
