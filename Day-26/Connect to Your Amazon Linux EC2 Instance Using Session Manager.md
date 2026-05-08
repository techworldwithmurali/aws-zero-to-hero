# Connect to Your Amazon Linux EC2 Instance Using Session Manager

- **SSM Session Manager** is a feature of AWS Systems Manager that allows you to securely connect to and manage EC2 instances without needing SSH, RDP, or open inbound ports.
- It provides encrypted, auditable access to your instances through the AWS Management Console.

**Key Benefits:**
- **Secure**: No need for SSH keys or open ports.
- **Auditable**: All sessions are logged.
- **Simple**: Access via the AWS Console without third-party tools.
- **Cost-effective**: Eliminates the need for bastion hosts.

Reference link : https://docs.aws.amazon.com/systems-manager/latest/userguide/agent-install-al2.html
## Pre-requisites

### AWS Systems Manager Agent (SSM Agent)
Ensure the SSM Agent is installed and running on your EC2 instance.

- The agent is pre-installed on Amazon Linux, Amazon Linux 2, Amazon Linux 2023, and Ubuntu AMIs provided by AWS.
- For other OS types, you'll need to manually install the SSM Agent.

### For Amazon Linux 2
#### Step 1: Update the System
Run the following command to ensure your system is up-to-date:

```bash
sudo yum update -y
```

#### Step 2: Install the SSM Agent
Use the `yum` package manager to install the SSM Agent:

```bash
sudo yum install -y amazon-ssm-agent
```

#### Step 3: Start and Enable the SSM Agent
Start the Agent:

```bash
sudo systemctl start amazon-ssm-agent
```

Enable it to Start on Boot:

```bash
sudo systemctl enable amazon-ssm-agent
```

#### Step 4: Verify Installation
Check the agent's status and version:

```bash
sudo systemctl status amazon-ssm-agent
amazon-ssm-agent --version
```

### For Amazon Linux 2023
#### Step 1: Update the System
Ensure your system packages are up-to-date:

```bash
sudo dnf update -y
```

#### Step 2: Install the SSM Agent
Use the `dnf` package manager to install the SSM Agent:

```bash
sudo dnf install -y amazon-ssm-agent
```

#### Step 3: Start and Enable the SSM Agent
Start the Agent:

```bash
sudo systemctl start amazon-ssm-agent
```

Enable it to Start on Boot:

```bash
sudo systemctl enable amazon-ssm-agent
```

#### Step 4: Verify Installation
Check the agent's status and version:

```bash
sudo systemctl status amazon-ssm-agent
amazon-ssm-agent --version
```

## IAM Role with Session Manager Permissions
Attach an IAM role to the EC2 instance that includes permissions for Session Manager.
Use the `AmazonSSMManagedInstanceCore` (AWS Managed Policy).

### Minimum permissions:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ssm:StartSession",
        "ssm:DescribeInstanceInformation",
        "ssm:GetCommandInvocation",
        "ssm:ListCommandInvocations",
        "ssm:SendCommand",
        "ssmmessages:*"
      ],
      "Resource": "*"
    }
  ]
}
```

## Enable Session Manager
Ensure Session Manager is enabled in the AWS Systems Manager console. Navigate to Session Manager settings and enable it.

## Steps to Connect

### 1. Log in to the AWS Management Console:
- Go to the AWS EC2 Console.

### 2. Navigate to Session Manager:
- Open the AWS Systems Manager service.
- Under Session Manager, click on **Start session**.

### 3. Select Your Instance:
- You'll see a list of instances managed by Systems Manager.
- Choose the instance you want to connect to, and click **Start session**.

If you encounter issues, check the agent logs:

```bash
sudo cat /var/log/amazon/ssm/amazon-ssm-agent.log
```
