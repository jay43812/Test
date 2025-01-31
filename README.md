# Configure AWS CLI on Your Local Machine

A step-by-step guide to install, configure, and verify the AWS CLI for interacting with AWS services from your local machine.

---

## Table of Contents
- [Prerequisites](#prerequisites)
- [Install AWS CLI](#install-aws-cli)
  - [macOS](#macos)
  - [Linux](#linux)
  - [Windows](#windows)
- [How to Get AWS Access Key and Secret Access Key](#how-to-get-aws-access-and-secret-key)
- [Configure AWS CLI](#configure-aws-cli)
- [Verify Configuration](#verify-configuration)
- [Basic Usage Examples](#basic-usage-examples)


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
   # Example output: aws-cli/2.13.0 Python/3.11.4 Darwin/22.5.0 source/arm64
   
### Windows

### Step 1: Download the Installer
1. Visit the [AWS CLI Website](https://aws.amazon.com/cli/).
2. Download the **Windows MSI Installer**.

### Step 2: Run the Installer
1. Double-click the downloaded `.msi` file.
2. Follow the on-screen prompts to complete the installation.

### Step 3: Verify Installation
1. Open **Command Prompt**.
2. Run the following command to check the installed version:
   ```cmd
   aws --version
   # Example output: aws-cli/2.13.0 Python/3.11.4 Windows/10 exe/AMD64

# How to Get AWS Access Key and Secret Access Key

Follow these steps to create and retrieve your AWS Access Key and Secret Access Key.

---

## Step 1: Sign in to the AWS Management Console
1. Go to the [AWS Management Console](https://aws.amazon.com/console/).
2. Sign in with your AWS account credentials.

---

## Step 2: Open the IAM Console
1. In the AWS Management Console, search for **IAM** (Identity and Access Management) in the search bar.
2. Click on **IAM** to open the IAM console.

---

## Step 3: Create an IAM User (if you don’t have one)
1. In the IAM console, navigate to **Users** in the left-hand menu.
2. Click **Add users**.
3. Enter a **User name** (e.g., `my-iam-user`).
4. Under **Select AWS access type**, check **Programmatic access**.
5. Click **Next: Permissions**.

---

## Step 4: Attach Permissions to the User
1. Choose how to assign permissions:
   - **Add user to group**: Attach the user to an existing group with permissions.
   - **Copy permissions from existing user**: Copy permissions from another user.
   - **Attach policies directly**: Attach policies directly to the user (e.g., `AdministratorAccess` for full access).
2. Click **Next: Tags** (optional).
3. Click **Next: Review**.

---

## Step 5: Review and Create the User
1. Review the user details and permissions.
2. Click **Create user**.

---

## Step 6: Retrieve Access Key and Secret Access Key
1. After creating the user, you’ll see a confirmation screen.
2. Click **Download .csv** to save the credentials to your computer.
   - The `.csv` file contains:
     - **Access Key ID**: `AKIAXXXXXXXXXXXXXXXX`
     - **Secret Access Key**: `xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`
3. **Important**: Store the `.csv` file securely. You won’t be able to retrieve the Secret Access Key again.

---

## Step 7: Use the Credentials
1. Use the **Access Key ID** and **Secret Access Key** to configure AWS CLI or SDKs.
2. Example AWS CLI configuration:
   ```bash
   aws configure


Contact
For questions or feedback:
📧 Email: your.email@example.com
🐙 GitHub: your-username

