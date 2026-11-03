
# Automated CI/CD Deployment on AWS Using GitHub Actions

## Project Overview

This project demonstrates an automated CI/CD pipeline that deploys a static website to Amazon S3 using GitHub Actions and AWS IAM OIDC authentication.

The objective is to automate website deployment while following AWS security best practices and avoiding long-lived AWS access keys.

## Architecture

Developer → GitHub Repository → GitHub Actions → AWS OIDC → IAM Role → Amazon S3

## Technologies Used

- Amazon Web Services (AWS)
- Amazon S3
- AWS IAM
- OpenID Connect (OIDC)
- GitHub Actions
- Git and GitHub
- HTML and CSS

## How It Works

1. Website source files are maintained in GitHub.
2. A developer pushes changes to the main branch.
3. GitHub Actions automatically starts the deployment workflow.
4. GitHub authenticates with AWS using OIDC.
5. AWS STS allows the workflow to assume a restricted IAM role.
6. GitHub Actions uploads website files to the S3 bucket.
7. The deployment result is visible in GitHub Actions.

## Security Implementation

- Used AWS IAM role-based authentication.
- Configured GitHub OIDC federation.
- Avoided storing permanent AWS access keys in GitHub.
- Applied least-privilege S3 permissions.
- Kept S3 Block Public Access enabled.

## Repository Structure

```text
aws-github-actions-cicd/
├── website/
│   ├── index.html
│   └── style.css
├── .github/
│   └── workflows/
│       └── deploy.yml
└── README.md
```

## Deployment

The deployment workflow is located at:

`.github/workflows/deploy.yml`

It runs automatically when relevant website files are pushed to the main branch.

## Learning Outcomes

- Configuring AWS IAM roles and permissions.
- Understanding OIDC authentication.
- Automating deployments with GitHub Actions.
- Working with Amazon S3.
- Understanding CI/CD pipeline execution.

## Future Enhancements

- Configure Amazon CloudFront.
- Implement Origin Access Control (OAC).
- Add a custom domain and HTTPS.
- Add deployment verification and troubleshooting documentation.

## Project Status

S3 deployment automation successfully tested using GitHub Actions.

CloudFront integration is planned.


## Project Screenshots

### 1. GitHub Actions Deployment
![GitHub Actions Success](screenshots/GitHub%20Action%20Success.png)

### 2. AWS IAM Role
![AWS IAM Role](screenshots/IAM%20Role.png)

### 3. Amazon S3 Bucket
![S3 Objects](screenshots/S3%20Objects.png)

### 4. CloudFront Distribution
![CloudFront Distribution](screenshots/CloudFront%20Distribution.png)

### 5. CloudFront Origin Configuration
![CloudFront Origin](screenshots/CloudFront%20Origin.png)

### 6. S3 Security Configuration
![S3 Security](screenshots/S3%20Security.png)

### 7. Live Website
![Live Website](screenshots/Cloudfront%20URL.png)





## Live Website

The website is deployed on Amazon CloudFront:

https://dspopw8ykxfic.cloudfront.net

## Deployment Architecture

GitHub → GitHub Actions → AWS OIDC → IAM Role → Amazon S3 → Amazon CloudFront

## Live Demo

**Visit the deployed website:**

https://dspopw8ykxfic.cloudfront.net

## Architecture

GitHub → GitHub Actions → AWS OIDC → IAM Role → Amazon S3 → Amazon CloudFront
