# Create an AWS Config rule and remediation - removes any SG rules that have 0.0.0.0/0 as a source unless they use TCP port 80

1. Create an IAM role with a custom trust policy for Systems Manager and add the `AmazonSSMAutomationRole` policy
