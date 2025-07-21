# ✅ Task 2: Infrastructure as Code (IaC) for AI Model Deployment

**Tool:** Terraform  
**Cloud:** AWS

## Terraform Code:
```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "ai_cli_server" {
  ami           = "ami-0c55b159cbfafe1f0"  # Ubuntu 20.04
  instance_type = "t2.medium"
  tags = {
    Name = "ai-cli-app"
  }
}

resource "aws_s3_bucket" "model_bucket" {
  bucket = "ai-model-storage-cli"
  acl    = "private"
}

resource "aws_iam_role" "ec2_role" {
  name = "ec2-s3-access-role"
  assume_role_policy = <<EOF
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
EOF
}
```

## Summary:
- Deploys EC2 for CLI app
- S3 bucket to store model files
- IAM Role to allow EC2 access to S3
