# Create a Custom CloudWatch Metric

## Step - 1 | Create an IAM Role and Instance Profile

1. Create an IAM policy

```bash
aws iam create-policy --policy-name "CloudWatch-Put-Metric-Data" --policy-document '{"Version":"2012-10-17","Statement":[{"Effect":"Allow","Action":["cloudwatch:PutMetricData"],"Resource":"*"}]}'
```

2. Create an IAM role that uses the policy document

```bash
aws iam create-role --role-name "CloudWatch-Role" --assume-role-policy-document '{"Version":"2012-10-17","Statement":[{"Effect":"Allow","Principal":{"Service":"ec2.amazonaws.com"},"Action":"sts:AssumeRole"}]}'
```

3. Attach the policy to the role (update policy ARN)

```bash
aws iam attach-role-policy --role-name "CloudWatch-Role" --policy-arn "arn:aws:iam::<YOUR_ACC_NO>:policy/CloudWatch-Put-Metric-Data"
```

4. Create an instance profile

```bash
aws iam create-instance-profile --instance-profile-name "CloudWatch-Instance-Profile"
```

5. Add the role to the instance profile

```bash
aws iam add-role-to-instance-profile --instance-profile-name "CloudWatch-Instance-Profile" --role-name "CloudWatch-Role"
```

5. Add the role to the instance profile

```bash
aws iam add-role-to-instance-profile --instance-profile-name "CloudWatch-Instance-Profile" --role-name "CloudWatch-Role"
```

## Step - 2 | Launch an EC2 instance

1. Create a security group

```bash
aws ec2 create-security-group --group-name CustomMetricLab --description "Temporary SG for the Custom Metric Lab"
```

2. Add a rule for SSH inbound to the security group

```bash
aws ec2 authorize-security-group-ingress --group-name CustomMetricLab --protocol tcp --port 22 --cidr 0.0.0.0/0
```

3. Launch instance in US-EAST-1A

```bash
aws ec2 run-instances --image-id <LINUX_AMI_ID> --instance-type t2.micro --placement AvailabilityZone=us-east-1a --security-group-ids <YOUR_SG_ID> --iam-instance-profile Name="CloudWatch-Instance-Profile"
```

