### Connect to Your Amazon Windows EC2 Instance Using Session Manager

- **SSM Session Manager** is a feature of AWS Systems Manager that allows you to securely connect to and manage EC2 instances without needing SSH, RDP, or open inbound ports.
- It provides encrypted, auditable access to your instances through the AWS Management Console or CLI.

**Key Benefits:**
- **Secure**: No need for SSH keys or open ports.
- **Auditable**: All sessions are logged.
- **Simple**: Access via the AWS Console or CLI without third-party tools.
- **Cost-effective**: Eliminates the need for bastion hosts.

## Pre-requisites

### AWS Systems Manager Agent (SSM Agent)
Ensure the SSM Agent is installed and running on your EC2 instance.

AWS Systems Manager Agent (SSM Agent) is preinstalled, by default, on the following Amazon Machine Images (AMIs) for Windows Server provided by Amazon:

- Windows Server 2008-2012 R2 AMIs published in November 2016 or later
- Windows Server 2016, 2019, and 2022 (excluding Nano versions)

For other OS types, you'll need to manually install the SSM Agent.

#### Direct download
Download the latest version of SSM Agent to your instance by using the following link. If you want, update this URL with an AWS Region-specific URL.

[Download AmazonSSMAgentSetup.exe](https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/windows_amd64/AmazonSSMAgentSetup.exe)

Run the downloaded `AmazonSSMAgentSetup.exe` file to install SSM Agent.

Start or restart SSM Agent by sending the following command in PowerShell:

```powershell
Restart-Service AmazonSSMAgent
```

To check the status of the SSM Agent service:

```powershell
Get-Service AmazonSSMAgent
```
This command will show you the current status (running or stopped) of the AmazonSSMAgent service.

To start the service, you can use:

```powershell
Start-Service AmazonSSMAgent
```

To stop the service, use:

```powershell
Stop-Service AmazonSSMAgent
```

To check the version of the SSM Agent:

```powershell
amazon-ssm-agent --version
```

#### Check the Agent Logs (if needed):
If you encounter issues, check the agent logs for more details:

```powershell
Get-Content "C:\ProgramData\Amazon\SSM\Logs\amazon-ssm-agent.log" -Tail 50
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

## Steps to Connect

### 1. Log in to the AWS Management Console:
- Go to the AWS EC2 Console.

### 2. Navigate to Session Manager:
- Open the AWS Systems Manager service.
- Under Session Manager, click on **Start session**.

### 3. Select Your Instance:
- You'll see a list of instances managed by Systems Manager.
- Choose the instance you want to connect to, and click **Start session**.
