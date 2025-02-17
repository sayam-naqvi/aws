# AWS S3 Bucket Policy ReadMe

## Description
This document provides details about the AWS IAM policy for accessing **single ** S3 bucket. The policy allows listing the bucket contents and performing read/write operations on objects within the bucket.

## Policy Details
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::BUCKETNAME"
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:PutObject",
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::BUCKETNAME/*"
    }
  ]
}
```

## Explanation
- **s3:ListBucket**: Allows listing the contents of the specified bucket.
- **s3:PutObject**: Grants permission to upload objects to the bucket.
- **s3:GetObject**: Grants permission to read objects from the bucket.
- **Resource Specification**:
  - `arn:aws:s3:::BUCKETNAME` applies to the bucket itself.
  - `arn:aws:s3:::BUCKETNAME/*` applies to all objects inside the bucket.

## Steps to View the S3 Bucket
1. Replace `BUCKETNAME` with the actual name of your bucket in the policy.
2. To view the bucket contents, enter the following URL in your browser:
   ```
   https://s3.console.aws.amazon.com/s3/buckets/BUCKETNAME
   ```
3. Ensure you have the required AWS permissions to access the S3 console.
4. You can also use AWS CLI to list the bucket contents:
   ```sh
   aws s3 ls s3://BUCKETNAME
   ```

