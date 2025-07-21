# ✅ Task 1: CI/CD Pipeline Example for AI Application Deployment

**Project Name:** AI-Based CLI Assistant Deployment  
**Platform:** AWS  
**Tools Used:** GitHub Actions, Docker, AWS EC2, CodeDeploy

## Pipeline Steps:
1. **Code Push:** Developer pushes code to GitHub repository.
2. **CI Stage:**
   - GitHub Actions triggers on `main` branch push.
   - Runs linting, unit tests (PyTest), and model validation.
   - Builds Docker image.
3. **Artifact Upload:**
   - Docker image pushed to Amazon ECR.
4. **CD Stage:**
   - AWS CodeDeploy triggered.
   - Pulls latest image from ECR.
   - Deploys container on EC2 instance using a deployment script.

## AI-Specific Considerations:
- Model weights and config are version-controlled separately.
- During deploy, the container fetches the latest model from S3.
