This repository contains GitHub Actions workflows that automate tasks such as validating files, deploying to AWS S3, and managing Nginx on EC2 instances.

🚀 Workflows
1. First Workflow (First_workflow.yml)

Triggered on:

Push events to the main branch

Manual workflow dispatch

What it does:

Clones the repository.

Checks if index.html exists in the root directory.

Marks the workflow as failed if the file is missing.

Proceeds with success steps only if the file exists.

2. Second Workflow (second_workflow.yml)

Triggered on:

Manual workflow dispatch

What it does:

Clones the repository.

Configures AWS credentials using repository secrets.

Uploads index.html to an S3 bucket (homework-1212).

Uses AWS SSM (Systems Manager) to:

Install and start Nginx on an EC2 instance.

Copy index.html from the S3 bucket to /usr/share/nginx/html/ on the EC2 instance.

Serve the file via Nginx.

🔑 Secrets Required

Make sure to configure the following GitHub Secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_REGION

EC2_INSTANCE_ID

📂 Files

First_workflow.yml → Validates index.html presence.

second_workflow.yml → Deploys the file to AWS S3 & EC2.
