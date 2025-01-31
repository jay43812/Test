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
   
2. **Verify Installation**:
   ```bash
   aws --version
# Example output: aws-cli/2.13.0 Python/3.11.4 Darwin/22.5.0 source/arm64

### Linux

## Step 1: Download the AWS CLI Installer  
1. Open a terminal.  
2. Run the following command to download the AWS CLI:  

   ```bash
   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
3. Unzip and install
   ```bash
   unzip awscliv2.zip
4. Install AWS CLI
   ```bash
   sudo ./aws/install

6. Verify Installation
   ```bash
   aws --version


Contact
For questions or feedback:
📧 Email: your.email@example.com
🐙 GitHub: your-username

