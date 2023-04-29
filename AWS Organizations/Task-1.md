# Create SCP for Restricting EC2 Instance Types

1. In AWS Organizations, enable Service Control Policies (SCPs)

2. Create a policy called "RequireT2Micro"

3. Enter the following JSON code:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "RequireMicroInstanceType",
      "Effect": "Deny",
      "Action": "ec2:RunInstances",
      "Resource": "arn:aws:ec2:*:*:instance/*",
      "Condition": {
        "StringNotEquals": {
          "ec2:InstanceType": "t2.micro"
        }
      }
    }
  ]
}
```