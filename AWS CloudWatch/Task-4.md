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

6. Add the contents from the cw-config.json file provided

7. Run the following commmand

```bash
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s
```

8. Then make sure the agent is started

```bash
sudo systemctl start amazon-cloudwatch-agent
```

9. Generate some traffic to Apache including some 404s
