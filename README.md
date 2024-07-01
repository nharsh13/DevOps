# DevOps
To create a user in aws
    aws iam create-user --user-name Bob

To give admin access to user.
    aws iam attach-user-policy --user-name <username> --policy-arn arn:aws:iam::aws:policy/AdministratorAccess

To create IAM Role
    aws iam create-role --role-name Tester-Role --assume-role-policy-document file://role.json
    
    role.json
    
      {
  "Version": "2012-10-17",
  "Statement": 
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::322495901908:user/Test" 
      },
      "Action": "sts:AssumeRole"
    }
}



TO create policy
    aws iam create-policy --policy-name tester-policy --policy-document test_access_policy.json


    json file
    {
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:Get*",
        "s3:List*",
        "s3:Describe*",
        "s3-object-lambda:Get*",
        "s3-object-lambda:List*"
      ],
      "Resource": "*"
    }
  ]
}






