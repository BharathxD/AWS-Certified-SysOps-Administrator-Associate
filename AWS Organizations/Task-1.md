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

4. Attach the SCP to the OU that contains the dev account (OU1)

5. Switch roles to administer the dev account

## Switch role using:

Account number of the dev account
Role: `OrganizationAccountAccess`

