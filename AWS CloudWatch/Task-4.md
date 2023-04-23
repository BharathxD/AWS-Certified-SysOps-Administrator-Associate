# Install Apache and Configure Logging

1. If not already installed, install the CloudWatch agent

```bash
sudo yum install amazon-cloudwatch-agent
```

2. Also, install collectd

```bash
sudo amazon-linux-extras install collectd
```

3. Install and enable Apache

```bash
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
```

4. If the config file exists, delete it

```bash
sudo rm -rf /opt/aws/amazon-cloudwatch-agent/bin/config.json
```

5. Create the config.json

```bash
sudo nano /opt/aws/amazon-cloudwatch-agent/bin/config.json
```
