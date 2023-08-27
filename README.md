# Setting up EMR with AWS Cli

## Create Key DescribeKeyPairs


```bash
aws ec2 create-key-pair --key-name MyKeyPair
```


## give access to everything for EMR
```
aws emr create-default-roles
```


## output
```bash


[
    {
        "Role": {
            "Path": "/",
            "RoleName": "EMR_EC2_DefaultRole",
            "RoleId": "AROAQSZULC42WHD2J57H4",
            "Arn": "arn:aws:iam::040375097141:role/EMR_EC2_DefaultRole",
            "CreateDate": "2023-08-26T20:42:40Z",
            "AssumeRolePolicyDocument": {
                "Version": "2008-10-17",
                "Statement": [
                    {
                        "Sid": "",
                        "Effect": "Allow",
                        "Principal": {
                            "Service": "ec2.amazonaws.com"
                        },
                        "Action": "sts:AssumeRole"
                    }
                ]
            }
        },
        "RolePolicy": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Resource": "*",
                    "Action": [
                        "cloudwatch:*",
                        "dynamodb:*",
                        "ec2:Describe*",
                        "elasticmapreduce:Describe*",
                        "elasticmapreduce:ListBootstrapActions",
                        "elasticmapreduce:ListClusters",
                        "elasticmapreduce:ListInstanceGroups",
                        "elasticmapreduce:ListInstances",
                        "elasticmapreduce:ListSteps",
                        "kinesis:CreateStream",
                        "kinesis:DeleteStream",
                        "kinesis:DescribeStream",
                        "kinesis:GetRecords",
                        "kinesis:GetShardIterator",
                        "kinesis:MergeShards",
                        "kinesis:PutRecord",
                        "kinesis:SplitShard",
                        "rds:Describe*",
                        "s3:*",
                        "sdb:*",
                        "sns:*",
                        "sqs:*",
                        "glue:CreateDatabase",
                        "glue:UpdateDatabase",
                        "glue:DeleteDatabase",
                        "glue:GetDatabase",
                        "glue:GetDatabases",
                        "glue:CreateTable",
                        "glue:UpdateTable",
                        "glue:DeleteTable",
                        "glue:GetTable",
                        "glue:GetTables",
                        "glue:GetTableVersions",
                        "glue:CreatePartition",
                        "glue:BatchCreatePartition",
                        "glue:UpdatePartition",
                        "glue:DeletePartition",
                        "glue:BatchDeletePartition",
                        "glue:GetPartition",
                        "glue:GetPartitions",
                        "glue:BatchGetPartition",
                        "glue:CreateUserDefinedFunction",
                        "glue:UpdateUserDefinedFunction",
                        "glue:DeleteUserDefinedFunction",
                        "glue:GetUserDefinedFunction",
                        "glue:GetUserDefinedFunctions"
                    ]
                }
            ]
        }
    },
    {
        "Role": {
            "Path": "/",
            "RoleName": "EMR_DefaultRole",
            "RoleId": "AROAQSZULC42RUMT3P4NZ",
            "Arn": "arn:aws:iam::040375097141:role/EMR_DefaultRole",
            "CreateDate": "2023-08-26T20:42:42Z",
            "AssumeRolePolicyDocument": {
                "Version": "2008-10-17",
                "Statement": [
                    {
                        "Sid": "",
                        "Effect": "Allow",
                        "Principal": {
                            "Service": "elasticmapreduce.amazonaws.com"
                        },
                        "Action": "sts:AssumeRole"
                    }
                ]
            }
        },
        "RolePolicy": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Resource": "*",
                    "Action": [
                        "ec2:AuthorizeSecurityGroupEgress",
                        "ec2:AuthorizeSecurityGroupIngress",
                        "ec2:CancelSpotInstanceRequests",
                        "ec2:CreateFleet",
                        "ec2:CreateLaunchTemplate",
                        "ec2:CreateNetworkInterface",
                        "ec2:CreateSecurityGroup",
                        "ec2:CreateTags",
                        "ec2:DeleteLaunchTemplate",
                        "ec2:DeleteNetworkInterface",
                        "ec2:DeleteSecurityGroup",
                        "ec2:DeleteTags",
                        "ec2:DescribeAvailabilityZones",
                        "ec2:DescribeAccountAttributes",
                        "ec2:DescribeDhcpOptions",
                        "ec2:DescribeImages",
                        "ec2:DescribeInstanceStatus",
                        "ec2:DescribeInstances",
                        "ec2:DescribeKeyPairs",
                        "ec2:DescribeLaunchTemplates",
                        "ec2:DescribeNetworkAcls",
                        "ec2:DescribeNetworkInterfaces",
                        "ec2:DescribePrefixLists",
                        "ec2:DescribeRouteTables",
                        "ec2:DescribeSecurityGroups",
                        "ec2:DescribeSpotInstanceRequests",
                        "ec2:DescribeSpotPriceHistory",
                        "ec2:DescribeSubnets",
                        "ec2:DescribeTags",
                        "ec2:DescribeVpcAttribute",
                        "ec2:DescribeVpcEndpoints",
                        "ec2:DescribeVpcEndpointServices",
                        "ec2:DescribeVpcs",
                        "ec2:DetachNetworkInterface",
                        "ec2:ModifyImageAttribute",
                        "ec2:ModifyInstanceAttribute",
                        "ec2:RequestSpotInstances",
                        "ec2:RevokeSecurityGroupEgress",
                        "ec2:RunInstances",
                        "ec2:TerminateInstances",
                        "ec2:DeleteVolume",
                        "ec2:DescribeVolumeStatus",
                        "ec2:DescribeVolumes",
                        "ec2:DetachVolume",
                        "iam:GetRole",
                        "iam:GetRolePolicy",
                        "iam:ListInstanceProfiles",
                        "iam:ListRolePolicies",
                        "iam:PassRole",
                        "s3:CreateBucket",
                        "s3:Get*",
                        "s3:List*",
                        "sdb:BatchPutAttributes",
                        "sdb:Select",
                        "sqs:CreateQueue",
                        "sqs:Delete*",
                        "sqs:GetQueue*",
                        "sqs:PurgeQueue",
                        "sqs:ReceiveMessage",
                        "cloudwatch:PutMetricAlarm",
                        "cloudwatch:DescribeAlarms",
                        "cloudwatch:DeleteAlarms",
                        "application-autoscaling:RegisterScalableTarget",
                        "application-autoscaling:DeregisterScalableTarget",
                        "application-autoscaling:PutScalingPolicy",
                        "application-autoscaling:DeleteScalingPolicy",
                        "application-autoscaling:Describe*"
                    ]
                },
                {
                    "Effect": "Allow",
                    "Action": "iam:CreateServiceLinkedRole",
                    "Resource": "arn:aws:iam::*:role/aws-service-role/spot.amazonaws.com/AWSServiceRoleForEC2Spot*",
                    "Condition": {
                        "StringLike": {
                            "iam:AWSServiceName": "spot.amazonaws.com"
                        }
                    }
                }
            ]
        }
    },
    {
        "Role": {
            "Path": "/",
            "RoleName": "EMR_AutoScaling_DefaultRole",
            "RoleId": "AROAQSZULC42UD7HAHJFO",
            "Arn": "arn:aws:iam::040375097141:role/EMR_AutoScaling_DefaultRole",
            "CreateDate": "2023-08-26T20:42:43Z",
            "AssumeRolePolicyDocument": {
                "Version": "2008-10-17",
                "Statement": [
                    {
                        "Sid": "",
                        "Effect": "Allow",
                        "Principal": {
                            "Service": [
                                "elasticmapreduce.amazonaws.com",
                                "application-autoscaling.amazonaws.com"
                            ]
                        },
                        "Action": "sts:AssumeRole"
                    }
                ]
            }
        },
        "RolePolicy": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Action": [
                        "cloudwatch:DescribeAlarms",
                        "elasticmapreduce:ListInstanceGroups",
                        "elasticmapreduce:ModifyInstanceGroups"
                    ],
                    "Effect": "Allow",
                    "Resource": "*"
                }
            ]
        }
    }
]



```




### Launch Cluster


```bash


aws emr create-cluster \
--name "<My First EMR Cluster>" \
--release-label emr-5.36.1 \
--applications Name=Spark \
--ec2-attributes KeyName=MyKeyPair \
--instance-type m5.xlarge \
--instance-count 3 \
--use-default-roles




```


#### output


```bash
{
"ClusterId": "<cluser_id>",
"ClusterArn": "arn:aws:elasticmapreduce:us-east-2:040375097141:cluster/<cluser_id>"
}


```


### Launch Cluster with logs
```
aws emr create-cluster \
--name "<My First EMR Cluster>" \
--release-label emr-5.36.1 \
--applications Name=Spark \
--ec2-attributes KeyName=MyKeyPair \
--instance-type m5.xlarge \
--instance-count 3 \
--use-default-roles \
--log-uri s3://eliemrlogs/logs/
```


### check cluser status


```bash
aws emr describe-cluster --cluster-id <cluser_id>


```






## Check waiting clusters to find our cluser id
The State value changes from
- STARTING
- RUNNING
- to WAITING as Amazon EMR provisions the cluster.**




```bash
aws emr list-clusters --cluster-states WAITING
```


```
{
"Clusters": [
{
"Id": "<cluser_id>",
"Name": "<My First EMR Cluster>",
"Status": {
"State": "WAITING",
"StateChangeReason": {
"Message": "Cluster ready to run steps."
},
"Timeline": {
"CreationDateTime": "2023-08-26T22:27:48.590000+00:00",
"ReadyDateTime": "2023-08-26T22:32:16.197000+00:00"
}
},
"NormalizedInstanceHours": 24,
"ClusterArn": "arn:aws:elasticmapreduce:us-east-2:040375097141:cluster/<cluser_id>"
}
]
}


```








## Submitting work to the cluster






### work is submitted in steps
- step is a unit of work
- we're submitting the file created as a step


```bash
aws emr add-steps --cluster-id <cluser_id> --steps Type=Spark,Name="<My Spark Application>",ActionOnFailure=CONTINUE,Args=[s3://eli-emr/health_violations.py,--data_source,s3://eli-emr/Food_Establishment_Inspection_Data.csv,--output_uri,s3://eli-emr-output/health/]
```


```bash
aws emr add-steps \
--cluster-id <myClusterId> \
--steps Type=Spark,Name="<My Spark Application>",ActionOnFailure=CONTINUE,Args=[<s3://DOC-EXAMPLE-BUCKET/health_violations.py>,--data_source,<s3://DOC-EXAMPLE-BUCKET/food_establishment_data.csv>,--output_uri,<s3://DOC-EXAMPLE-BUCKET/MyOutputFolder>]
```


#### It returns Step Id


```bash
{
"StepIds": [
"<step-id>"
]
```


## Check status of check


```bash
aws emr describe-step --cluster-id <cluser_id> --step-id <step-id>


```




## Delete Cluster
```bash
aws emr terminate-clusters --cluster-ids <cluser_id>
```


### check steps for cluser
```
aws emr list-steps --cluster-id j-3SD91U2E1L2QX
```
09

## stop step


```
aws emr cancel-steps --cluster-id <cluser_id> \
--step-ids <step_id> \
--step-cancellation-option SEND_INTERRUPT
```


## Delete Cluster
```bash
aws emr terminate-clusters --cluster-ids <cluser_id>
```




## ERROR YOU'LL GET IF EC2 KEY ISN'T SET UP
```
"Market": "ON_DEMAND",
"InstanceGroupType": "CORE",
"InstanceType": "m5.xlarge",
"RequestedInstanceCount": 2,
"RunningInstanceCount": 0,
"Status": {
"State": "TERMINATED",
"StateChangeReason": {
"Code": "CLUSTER_TERMINATED",
"Message": "Job flow terminated"
},
"Timeline": {
"CreationDateTime": "2023-08-26T21:09:43.733000+00:00",
"EndDateTime": "2023-08-26T21:10:06.002000+00:00"
}
},
"Configurations": [],
"ConfigurationsVersion": 0,
"EbsBlockDevices": [
{
"VolumeSpecification": {
"VolumeType": "gp2",
"SizeInGB": 32
},
"Device": "/dev/sdb"
},
{
"VolumeSpecification": {
"VolumeType": "gp2",
"SizeInGB": 32
},
"Device": "/dev/sdc"
}
],
"ShrinkPolicy": {}
}
]
}
}
```

