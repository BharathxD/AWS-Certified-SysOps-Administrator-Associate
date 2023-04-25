# Create a role in the target account

1. Select 'another account' as the trusted entity
2. Enter the account ID and check the 'Require external ID' checkbox
3. Enter the external ID
4. Attach the following policy to the role:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowBucketAccess",
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:PutObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::<bucket-name>",
                "arn:aws:s3:::<bucket-name>/*"
            ]
        }
    ]
}

