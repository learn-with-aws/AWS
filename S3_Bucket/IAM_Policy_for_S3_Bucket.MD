## IAM policy for Specific Bucket permission


            {
              "version": "2012-10-17",
              "Statement": [
                {
                  "Effect": "Allow",
                  "Action": [
                    "s3:ListAllMyBuckets",
                    "s3:GetBucketLocation"
                  ],
                  "resource": "arn:aws:s3:::*"
                },
                {
                  "Effect": "Allow",
                  "Action": ["s3:*"],
                  "Resource": ["arn:aws:s3:::gateway-tech"]
                },
                {
                  "Effect": "Allow",
                  "Action": [
                    "s3:GetObject",
                    "s3:PutObject",
                    "s3:DeleteObject"
                  ],
                  "Resource": ["arn:aws:s3:::gateway-tech"]
                }
              ]
            }
