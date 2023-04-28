# Create a Lifecycle Action using Command Line Interface

1. Create an SNS Topic

```bash
aws sns create-topic --name my-lifecycle-topic
```

2. Create a lifecycle hook

```bash
aws autoscaling put-lifecycle-hook --auto-scaling-group-name ASG1 --lifecycle-hook-name my-lifecycle-hook --lifecycle-transition autoscaling:EC2_INSTANCE_TERMINATING --notification-target-arn <sns-topic-arn> --role-arn arn:aws:iam::821711655051:role/aws-service-role/autoscaling.amazonaws.com/AWSServiceRoleForAutoScaling --heartbeat-timeout 300
```

3. Create a role that can be assumed by Lambda with the permissions in the permission.json file