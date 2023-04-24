# Create private subnets and NAT gateway

1. Create a private subnet in us-east-1a

```bash
aws ec2 create-subnet --vpc-id <INSERT_DEFAULT_VPCID> --cidr-block 172.31.96.0/20 --availability-zone us-east-1a --tag-specifications 'ResourceType=subnet,Tags=[{Key=Name,Value=private-1a}]'
```

2. Create a private subnet in us-east-1b

```bash
aws ec2 create-subnet --vpc-id <INSERT_DEFAULT_VPCID> --cidr-block 172.31.112.0/20 --availability-zone us-east-1b --tag-specifications 'ResourceType=subnet,Tags=[{key=Name,Value=private-1b}]'
```

3. Create a route table in the default VPC

```bash
aws ec2 create-route-table --vpc-id <INSERT_DEFAULT_VPCID> --tag-specifications 'ResourceType=route-table=Tags=[{Key=Name,Value=PivateRT}]'
```

4. Associate private subnets to the route table

```bash
aws ec2 associate-route-table --route-table-id <route-table-id> --subnet-id <private-subnet-id-1a>
aws ec2 associate-route-table --route-table-id <route-table-id> --subnet-id <private-subnet-id-1b>
```

5. Create an Elastic IP

```bash
aws ec2 allocate-address
```

6. Create a NAT gateway

```bash
aws ec2 create-nat-gateway --subnet-id <public-subnet-id> --allocation-id <eip-allocation-id>
```

