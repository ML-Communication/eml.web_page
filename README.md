# Easy Music Learning website

This project contains a static website for Easy Music Learning.

## Deployment target
This site can be hosted on AWS S3 and served through CloudFront.

## CI/CD deployment
A GitHub Actions workflow is included at .github/workflows/deploy-s3.yml.
It deploys the website to AWS S3 whenever changes are pushed to the main branch.

### Required GitHub settings
Add one of these authentication methods:
- Recommended: repository secret AWS_ROLE_TO_ASSUME for an IAM role using OIDC
- Or: repository secrets AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY

Also add:
- Repository variable AWS_S3_BUCKET with your S3 bucket name
- Repository variable AWS_REGION (optional, defaults to us-east-1)
- Repository variable AWS_CLOUDFRONT_DISTRIBUTION_ID (optional, for cache invalidation)

### AWS IAM setup
Use the sample policies in the aws folder:
- aws/iam-trust-policy.json
- aws/iam-permissions-policy.json

For OIDC, create an IAM role in AWS and add the ARN as the AWS_ROLE_TO_ASSUME GitHub secret.

## Files
- index.html
- styles.css
