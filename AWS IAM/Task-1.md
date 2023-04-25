# Configure AWS CLI with MFA

```bash
aws sts get-session-token --serial-number arn:aws:iam::<account-id>:mfa/<user-name> --token-code <token-from-device>
```

