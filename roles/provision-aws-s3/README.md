## My Orchestration playbooks and roles

_SUMMARY_: Configures simple configs for s3 buckets.  Lots to do here

Sample structure needed:
```
s3_buckets:
  demo_rileyschuit_com:
    bucket_name: demo.rileyschuit.com
    policy_type: "web_hosting"
    policy_details: >
      { "Version":"2012-10-17",
        "Statement":[
          {
            "Sid":"PublicRead",
            "Effect":"Allow",
            "Principal": "*",
            "Action":[
              "s3:GetObject"],
              "Resource":[
                "arn:aws:s3:::demo.rileyschuit.com/*"
              ]
          }
        ]
      }
  rileyschuit_com_buildbucket:
    bucket_name: rileyschuit.com-buildbucket
```

