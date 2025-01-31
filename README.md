# Configure AWS CLI on Your Local Machine

A step-by-step guide to install, configure, and verify the AWS CLI for interacting with AWS services from your local machine.

---

## Table of Contents
- [Prerequisites](#prerequisites)
- [Install AWS CLI](#install-aws-cli)
  - [macOS](#macos)
  - [Linux](#linux)
  - [Windows](#windows)
- [Configure AWS CLI](#configure-aws-cli)
- [Verify Configuration](#verify-configuration)
- [Basic Usage Examples](#basic-usage-examples)
- [Troubleshooting](#troubleshooting)
- [Security Best Practices](#security-best-practices)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Prerequisites

1. **AWS Account**: Sign up at [AWS Free Tier](https://aws.amazon.com/free/) if you don’t have one.
2. **IAM User**: Create an IAM user with programmatic access and required permissions (e.g., `AdministratorAccess`).
3. **Access Keys**: Note the **Access Key ID** and **Secret Access Key** from the IAM user’s security credentials.

---

## Install AWS CLI

### macOS
1. **Install via Homebrew**:
   ```bash
   brew install awscli

Verify Installation:

bash
Copy
aws --version
# Example output: aws-cli/2.13.0 Python/3.11.4 Darwin/22.5.0 source/arm64
Linux
Download and Install:

bash
Copy
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
Verify Installation:

bash
Copy
aws --version
Windows
Download the MSI Installer from AWS CLI Website.

Run the Installer and follow the prompts.

Verify Installation:

powershell
Copy
aws --version
Configure AWS CLI
Run the configuration wizard:

bash
Copy
aws configure
Enter the following details:

Copy
AWS Access Key ID [None]: AKIAXXXXXXXXXXXXXXXX  # Replace with your Access Key
AWS Secret Access Key [None]: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  # Replace with your Secret Key
Default region name [None]: us-east-1  # Preferred AWS region
Default output format [None]: json  # Output format (json/text/table)
Verify Configuration
Check your AWS identity:

bash
Copy
aws sts get-caller-identity
# Example output:
# {
#   "UserId": "AIDAXXXXXXXXXXXXXXXX",
#   "Account": "123456789012",
#   "Arn": "arn:aws:iam::123456789012:user/your-iam-username"
# }
Test S3 access:

bash
Copy
aws s3 ls
# Lists all S3 buckets in your account
Basic Usage Examples
S3 Operations
List buckets:

bash
Copy
aws s3 ls
Create a bucket:

bash
Copy
aws s3 mb s3://your-unique-bucket-name
Upload a file:

bash
Copy
aws s3 cp my-file.txt s3://your-bucket-name/
EC2 Operations
List EC2 instances:

bash
Copy
aws ec2 describe-instances
Start/Stop an instance:

bash
Copy
aws ec2 start-instances --instance-ids i-1234567890abcdef0
aws ec2 stop-instances --instance-ids i-1234567890abcdef0
IAM Operations
List IAM users:

bash
Copy
aws iam list-users
Create a policy:

bash
Copy
aws iam create-policy --policy-name MyPolicy --policy-document file://policy.json
Troubleshooting
Issue	Solution
aws: command not found	Reinstall AWS CLI or add it to your system PATH.
InvalidClientTokenId	Verify your Access Key and Secret Key.
AccessDenied	Check IAM user permissions in the AWS Console.
NoRegionError	Run aws configure to set a default region.
Security Best Practices
🔒 Never commit AWS credentials to version control (e.g., .aws/credentials file).

🔄 Rotate access keys every 90 days via the AWS IAM Console.

🛡️ Use IAM roles for EC2 instances instead of long-term credentials.

Contributing
Fork this repository.

Create a feature branch:

bash
Copy
git checkout -b feature/your-feature
Commit changes:

bash
Copy
git commit -m "Add your feature"
Push and open a Pull Request.

License
This project is licensed under the MIT License.

Contact
For questions or feedback:
📧 Email: your.email@example.com
🐙 GitHub: your-username

