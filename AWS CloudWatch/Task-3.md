# Launch instances with a tag

```bash
aws ec2 run-instances --image-id ami-0dfcb1ef8550277af --count 2 --instance-type t2.micro --tag-specifications 'ResourceType=instance,Tags=[{Key=Department,Value=Operations}]'
```
