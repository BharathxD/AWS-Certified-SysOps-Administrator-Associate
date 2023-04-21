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
aws iam attach-role-policy --role-name "CloudWatch-Role" --policy-arn "arn:aws:iam::821711655051:policy/CloudWatch-Put-Metric-Data"
```
