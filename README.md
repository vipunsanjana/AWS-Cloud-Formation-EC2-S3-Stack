# AWS CloudFormation: EC2 + S3 Deployment Template

A reusable CloudFormation template to create:
- ✅ A versioned Amazon S3 bucket
- ✅ A basic EC2 instance (Amazon Linux 2)

This infrastructure is provisioned in a secure, consistent, and repeatable manner.

---

## 🚀 Features

- Create an **S3 bucket** with versioning enabled
- Launch an **EC2 t2.micro instance** (free-tier eligible)
- Uses **CloudFormation Parameters** to customize bucket name
- Includes **outputs** like EC2 Instance ID and S3 Bucket ARN

---

## 📄 Template Metadata

- **Author**: Vipun Sanjana  
- **Version**: 1.1  
- **Purpose**: Basic AWS infrastructure deployment using IaC  
- **Resources**: `AWS::S3::Bucket`, `AWS::EC2::Instance`

---

## 🔧 Parameters

| Name        | Type   | Description                             | Constraints                             |
|-------------|--------|-----------------------------------------|-----------------------------------------|
| BucketName  | String | Name of the S3 bucket to be created     | 3–63 chars, lowercase letters, `.` or `-`|

---

## 📤 Outputs

| Output Name       | Description                          |
|-------------------|--------------------------------------|
| `BucketName`      | The name of the created S3 bucket    |
| `BucketArn`       | The ARN of the S3 bucket             |
| `BucketDomainName`| The S3 bucket domain name            |
| `EC2InstanceId`   | The ID of the launched EC2 instance  |

---

## 📦 How to Deploy

### 1. Deploy using AWS Console
- Go to [CloudFormation Console](https://console.aws.amazon.com/cloudformation)
- Click **Create stack**
- Upload this template
- Provide a valid **BucketName** parameter
- Launch the stack

### 2. Deploy using AWS CLI

```bash
aws cloudformation create-stack \
  --stack-name my-basic-infra \
  --template-body file://template.yaml \
  --parameters ParameterKey=BucketName,ParameterValue=my-app-bucket
```

## 🧠 Notes

- `t2.micro` is eligible under AWS Free Tier.
- Make sure the `BucketName` is globally unique.
- You can extend this template to include VPC, IAM, Security Groups, etc.

---

## 👨‍💻 Author

**Vipun Sanjana**  
Intern - Software Engineer (Cloud Security Operations Center, WSO2)  
Former Intern - Software Engineer, WSO2  
[GitHub](https://github.com/vipunsanjana) • [LinkedIn](https://www.linkedin.com/in/vipunsanjana)

