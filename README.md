# AWS Cloud Cost Optimization Using Lambda Function

This repository contains the code and instructions for an AWS Lambda function that automatically identifies and deletes EBS snapshots not associated with any existing EC2 instances or volumes. This helps ensure cost savings by avoiding unnecessary AWS charges.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Architecture](#architecture)
- [Setup](#setup)
  - [Step 1: AWS IAM Role](#step-1-aws-iam-role)
  - [Step 2: AWS Lambda Function](#step-2-aws-lambda-function)
  - [Step 3: Test the Lambda Function](#step-3-test-the-lambda-function)
  - [Step 4: Schedule the Lambda Function](#step-4-schedule-the-lambda-function)
- [Conclusion](#conclusion)
- [License](#license)

## Introduction

AWS offers a variety of services that help businesses scale and grow. However, it's crucial to manage these resources effectively to avoid unnecessary costs. One such area is managing EBS snapshots. This project demonstrates how to use an AWS Lambda function to automatically identify and delete unused EBS snapshots, optimizing cloud costs.

For a detailed explanation, you can read the full blog post [here](https://sujith08.hashnode.dev/aws-cloud-cost-optimization-using-lambda-function).

## Prerequisites

Before you begin, ensure you have the following:

- An AWS account with appropriate permissions
- Basic knowledge of AWS Lambda and IAM
- AWS CLI installed and configured
- Python 3.x installed

## Architecture

The architecture for this solution is straightforward:

1. An AWS Lambda function written in Python
2. An IAM Role with necessary permissions
3. Scheduled CloudWatch Events to trigger the Lambda function

## Setup

### Step 1: AWS IAM Role

1. Navigate to the IAM console in AWS.
2. Create a new role with the following permissions:
   - `AWSLambdaBasicExecutionRole`
   - `AmazonEC2ReadOnlyAccess`
   - `AmazonEC2FullAccess`
3. Attach the policy to the role.

### Step 2: AWS Lambda Function

1. Navigate to the Lambda console.
2. Create a new Lambda function.
3. Choose Python 3.x as the runtime.
4. Attach the IAM role created in Step 1 to the Lambda function.
5. Copy and paste the code from the `lambda_function.py` file in this repository into the Lambda code editor.
6. Save the function.

### Step 3: Test the Lambda Function

1. In the Lambda console, create a new test event with a dummy payload.
2. Test the Lambda function to ensure it executes without errors.

### Step 4: Schedule the Lambda Function

1. Navigate to the CloudWatch console.
2. Create a new rule to trigger the Lambda function on a schedule (e.g., daily).
3. Set the target to the Lambda function created in Step 2.
4. Save the rule.

## Conclusion

By using this Lambda function, you can automate the process of identifying and deleting unused EBS snapshots, leading to significant cost savings in your AWS environment.

For more information and a step-by-step guide, please visit the [blog post](https://sujith08.hashnode.dev/aws-cloud-cost-optimization-using-lambda-function).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
