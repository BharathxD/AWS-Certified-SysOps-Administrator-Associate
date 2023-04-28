# Create ASG and ELB using Command Line Interface

## Create a security group

```bash
aws ec2 create-security-group --group-name ALB-EC2-Access --description "Route 53 Policy Test" --region us-east-1
```

```bash
aws ec2 authorize-security-group-ingress --group-name ALB-EC2-Access --protocol tcp --port 22 --cidr 0.0.0.0/0 --region us-east-1
```

```bash
aws ec2 authorize-security-group-ingress --group-name ALB-EC2-Access --protocol tcp --port 80 --cidr 0.0.0.0/0 --region us-east-1
```

## create auto scaling group

```bash
aws autoscaling create-auto-scaling-group --auto-scaling-group-name ASG1 --launch-template "LaunchTemplateName=LT1" --min-size 1 --max-size 3 --desired-capacity 2 --availability-zones "us-east-1a" "us-east-1b" --vpc-zone-identifier "<subnet-id>, <subnet-id>"
```
