# Configure AWS CLI with MFA

```bash
aws sts get-session-token --serial-number arn:aws:iam::<account-id>:mfa/<user-name> --token-code <token-from-device>
```
---

#### `Note`: Use 'set' rather than 'export' for Windows

---

```bash
export AWS_ACCESS_KEY_ID=<access-key-id>
export AWS_SECRET_ACCESS_KEY=<secret-access-key>
export AWS_SESSION_TOKEN=<session-token>
```

```bash
unset AWS_ACCESS_KEY_ID
unset AWS_SECRET_ACCESS_KEY
unset AWS_SESSION_TOKEN
```
