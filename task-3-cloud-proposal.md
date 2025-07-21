# ✅ Task 3: Proposal – Migrating Open-Source AI CLI Tool to Scalable Cloud Infrastructure

## Objective:
Deploy a CLI-based AI Assistant (like Cursor) to a scalable, reliable cloud environment.

## Recommended Stack:
- **Cloud:** AWS
- **Compute:** AWS ECS Fargate (scalable + cost-efficient)
- **Storage:** Amazon S3 (for model artifacts)
- **CI/CD:** GitHub Actions + AWS CodePipeline + CodeDeploy
- **IaC:** Terraform
- **Monitoring:** CloudWatch + Prometheus (optional)
- **Secrets Management:** AWS Secrets Manager

## Deployment Flow:
1. Code pushed to GitHub triggers GitHub Actions.
2. Docker image built and pushed to Amazon ECR.
3. AWS CodePipeline deploys to ECS Fargate.
4. Running container pulls the latest model from S3.

## Why This Stack?
- Serverless compute (Fargate) reduces overhead.
- S3 provides reliable, cheap storage.
- Fully automated pipeline improves deployment speed.
