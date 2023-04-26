# Add a Bucket policy to restrict public access

- Add the following bucket policy

- ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Sid": "AllowPublicAccesstoObjects",
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "YOUR-BUCKET-ARN/*"
      }
    ]
  }
  ```
