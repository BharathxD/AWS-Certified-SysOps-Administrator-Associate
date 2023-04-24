# Create private subnets and NAT gateway

1. Create a private subnet in us-east-1a

```bash
aws ec2 create-subnet --vpc-id <INSERT_DEFAULT_VPCID> --cidr-block 172.31.96.0/20 --availability-zone us-east-1a --tag-specifications 'ResourceType=subnet,Tags=[{Key=Name,Value=private-1a}]'
```

## Create a private subnet in us-east-1b

```bash
aws ec2 create-subnet --vpc-id <INSERT_DEFAULT_VPCID> --cidr-block 172.31.112.0/20 --availability-zone us-east-1b --tag-specifications 'ResourceType=subnet,Tags=[{Key=Name,Value=private-1b}]'
```
