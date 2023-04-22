# Create the IAM role for SSM/CloudWatch

1. Create an IAM role with an EC2 trust policy
2. Add the following managed policies

`CloudWatchAgentServerPolicy` `AmazonSSMManagedInstanceCore`

3. Name the IAM role as below and create

`CloudWatchAgentServerRole`

4. Launch an EC2 instance and attach the role
