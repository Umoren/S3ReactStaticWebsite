# Static Website with React, Amazon S3, and Amazon CloudFront

This AWS CloudFormation template creates the necessary resources to host and deploy a static React website using Amazon S3 and Amazon CloudFront.

## Overview

This template sets up the following resources:

- An Amazon S3 bucket to store and serve the static files for the React app.
- An Amazon CloudFront distribution to act as a content delivery network (CDN), caching and serving the static files from edge locations closer to users.
- An S3 bucket policy to allow public access to the files in the bucket.

## Prerequisites

- An AWS account.
- AWS CLI installed and configured with the necessary credentials.
- A React app created using create-react-app.

Usage

1. Clone or download this repository.
2. In the AWS Management Console, navigate to the CloudFormation service.
3. Click "Create stack" and choose "With new resources (standard)".
4. In the "Create stack" wizard, choose "Upload a template file" and click "Choose file" to select the cloudformation-template.yaml file.
5. Click "Next" and enter a unique stack name.
6. Click "Next" again, and optionally configure any stack options, tags, or permissions.
7. Click "Next" one more time to review your settings, then click "Create stack" to start the stack creation process.
8. Wait for the stack creation to complete. This may take a few minutes.
9. After the stack has been created, navigate to the "Outputs" tab to find the S3 bucket name and CloudFront distribution domain name.

## Deploying the React app

10. In your terminal, navigate to your React app's root directory and run npm run build to create a production build of your app.
11. Use the AWS CLI or the AWS Management Console to upload the contents of the build folder to the S3 bucket created by the CloudFormation template.
12. Your React static website should now be accessible through the CloudFront distribution URL found in the "Outputs" section of your CloudFormation stack.

## Cleanup

To delete the resources created by this CloudFormation template, simply delete the stack from the AWS Management Console. This will automatically remove the S3 bucket, CloudFront distribution, and associated resources.

***Note: Make sure to empty the S3 bucket before deleting the stack, as CloudFormation cannot delete non-empty buckets.***