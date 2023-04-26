# Create an AWS Config rule and remediation - removes any SG rules that have 0.0.0.0/0 as a source unless they use TCP port 80

1. Create an IAM role with a custom trust policy for Systems Manager and add the `AmazonSSMAutomationRole` policy

2. Add an inline policy to the role with the JSON from the `policy.json` document

3. Create a config rule using the `pc-sg-open-only-to-authorized-ports` managed rule

4. Add port 80 next to `authorizedTcpPorts`

