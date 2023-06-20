```
{
    "Version": "2012-10-17",
    "Id": "S3PolicyIPRestrict",
    "Statement": [
        {
            "Sid": "IPAllow",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::use-s3-gateway-prd/*",
            "Condition" : {
                "IpAddress" : {
                    "aws:SourceIp": "18.232.162.0/24"
                },
                "NotIpAddress" : {
                    "aws:SourceIp": ["192.168.0.105/32,"172.18.50.193/32","192.168.165.145/32"]
                }
            }
        }
    ]
}
```

```
{
  "Id": "Policy1512590315712",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1512590314407",
      "Effect": "Deny",
      "Principal": {
        "AWS": "*"
      },
      "Action": "*",
      "Resource": [
        "arn:aws:s3:::use-s3-gateway-prd",
        "arn:aws:s3:::use-s3-gateway-prd/*"
      ],
      "Condition": {
        "NotIpAddress": {
          "aws:SourceIp": ["192.168.0.105/32,"172.18.50.193/32","192.168.165.145/32"]
        }
      }
    }
  ]
}
```
