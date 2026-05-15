# Automated AWS Cost Optimizer

## 📌 Project Overview

This project demonstrates how to automatically reduce AWS costs using AWS Lambda, CloudWatch, and Amazon EC2.

The system automatically stops unused or non-essential EC2 instances on a scheduled basis to help optimize cloud resource usage and reduce unnecessary billing.

---

## 🧰 AWS Services Used

- AWS Lambda
- Amazon CloudWatch
- Amazon EC2
- IAM Roles

---

## 🚀 Implementation Steps

### 1. Create EC2 Instance

Created EC2 instances that will be monitored and automatically stopped.

---

### 2. Create IAM Role

Configured IAM role with permissions for:
- EC2 management
- Lambda execution

Attached policies:
- AmazonEC2FullAccess
- AWSLambdaBasicExecutionRole

---

### 3. Create Lambda Function

Created a Lambda function using Python runtime to stop EC2 instances automatically.

Example logic:

```python
import boto3

ec2 = boto3.client('ec2')

def lambda_handler(event, context):

    instances = ['INSTANCE-ID']

    ec2.stop_instances(InstanceIds=instances)

    return {
        'statusCode': 200,
        'body': 'EC2 instance stopped successfully'
    }
```

---

### 4. Configure CloudWatch Trigger

Created a CloudWatch scheduled rule to automatically trigger the Lambda function at specific intervals.

Example:
- Daily
- Hourly
- Fixed schedule

---

### 5. Test Automation

Verified that the EC2 instance automatically stopped when the CloudWatch event triggered the Lambda function.

---

## 🎯 Features

- Automated Cost Optimization
- Serverless Automation
- Scheduled EC2 Management
- Reduced AWS Billing
- Efficient Resource Utilization

---

## 📸 Output

The Lambda function successfully stopped EC2 instances automatically based on the configured CloudWatch schedule.

---

## 🎓 Learning Outcomes

- AWS Lambda automation
- CloudWatch scheduling
- EC2 management using Boto3
- IAM role configuration
- Cost optimization techniques

---

## ✅ Conclusion

This project successfully implemented an automated AWS cost optimization solution using Lambda and CloudWatch to manage EC2 instances efficiently and reduce unnecessary cloud expenses.
