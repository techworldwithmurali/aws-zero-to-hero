#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


### What is SSM
AWS Systems Manager (SSM) is a management service provided by Amazon Web Services (AWS) that helps you automate tasks across your AWS resources and on-premises environments. It provides a unified user interface that allows you to view operational data from multiple AWS services and automate operational tasks across AWS resources.

### Key Features of AWS Systems Manager:

1. **Automation**:
   - AWS Systems Manager Automation allows you to automate common maintenance and deployment tasks such as patching, updating agents, and executing workflows across multiple instances.

2. **Run Command**:
   - Run Command enables you to remotely execute commands on your Amazon EC2 instances and on-premises servers. This can include tasks such as running PowerShell scripts or shell commands.

3. **Parameter Store**:
   - Parameter Store provides secure storage for configuration and secrets management, such as database credentials, API keys, and configuration strings. Parameters can be encrypted with AWS KMS (Key Management Service) for added security.

4. **Session Manager**:
   - Session Manager allows you to securely connect to your instances without the need for SSH/RDP access. It provides interactive shell access to instances through the AWS Management Console, CLI, or SDK.

5. **Patch Manager**:
   - Patch Manager automates the process of patching Amazon EC2 instances and on-premises servers with security patches provided by AWS or custom patches defined by you.

6. **State Manager**:
   - State Manager allows you to define and enforce system configurations for your instances. It ensures instances are in a consistent state, applying configuration changes and maintaining compliance.

7. **OpsCenter**:
   - OpsCenter provides a central location to view, investigate, and resolve operational issues related to AWS resources, including EC2 instances, Systems Manager documents, and OpsItems (operational tasks and issues).

8. **Maintenance Windows**:
   - Maintenance Windows allow you to define a schedule for performing administrative tasks, such as patching and updates, across your instances and resources.
----
### Benefits of AWS Systems Manager:

- **Automation and Standardization**: Systems Manager helps you automate operational tasks, enforce configurations, and maintain consistency across your environment.

- **Security and Compliance**: It provides secure parameter storage, integrates with AWS KMS for encryption, and helps enforce security best practices through automated patching and configuration management.

- **Operational Insights**: Systems Manager provides operational data and insights into your AWS resources, helping you monitor and troubleshoot issues proactively.

- **Cost Optimization**: By automating tasks and improving operational efficiency, Systems Manager can help reduce operational costs associated with managing and maintaining infrastructure.
----
### Supported Operating Systems and Machine Types

AWS Systems Manager supports a wide range of operating systems, including:
- Amazon Linux
- Amazon Linux 2
- Ubuntu
- CentOS
- Red Hat Enterprise Linux (RHEL)
- Microsoft Windows Server (2008 R2 and later)

It is compatible with various machine types, including Amazon EC2 instances, on-premises servers, and virtual machines in other cloud environments.

----
### What is SSM Agent?

- **SSM Agent** is a software agent installed and configured on Amazon EC2 instances, on-premises servers, or virtual machines that are managed by AWS Systems Manager.
- The SSM Agent processes requests from Systems Manager services and securely communicates with the Systems Manager API.

### Working with SSM Agent

SSM Agent enables the following capabilities:
- **Managed Instances:** Enables Systems Manager to manage your instances, including installing or removing software, running scripts, and configuring applications.
- **Run Command:** Allows you to remotely execute scripts or commands on your instances without needing to SSH into them.
- **State Manager:** Ensures your instances are configured per your desired state, enforcing configurations and applying updates automatically.
- **Inventory and Patch Management:** Collects metadata about your instances, installed applications, and patches, facilitating inventory management and patch deployments.
----
### Install SSM Agent on EC2 Instance:
To install SSM Agent on an EC2 instance, you typically follow these steps:

### Prerequisites:
- Your EC2 instance must have an IAM role attached that grants it permissions to communicate with AWS Systems Manager (SSM). Ensure the IAM role has the necessary policies attached (e.g., AmazonSSMManagedInstanceCore).

### Installation Steps:

1. **Connect to Your EC2 Instance**:
   You can connect to your EC2 instance using SSH (for Linux) or RDP (for Windows). Ensure you have administrative privileges on the instance.

2. **Download and Install SSM Agent**:
   
   - For **Amazon Linux 2** or **Ubuntu Server**:

     ```bash
     sudo yum install -y amazon-ssm-agent  # Amazon Linux 2
     sudo apt-get install -y amazon-ssm-agent  # Ubuntu Server
     ```

   - For **Amazon Linux** or **RHEL**:

     ```bash
     sudo yum install -y https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm
     ```

   - For **Windows Server**:
     - Download the SSM Agent installer package from the AWS SSM documentation or use the Systems Manager console.
     - Run the installer package and follow the installation prompts.

3. **Start and Enable SSM Agent**:
   
   - For **Amazon Linux 2** or **Ubuntu Server**:

     ```bash
     sudo systemctl start amazon-ssm-agent
     sudo systemctl enable amazon-ssm-agent
     ```

   - For **Amazon Linux** or **RHEL**:

     ```bash
     sudo start amazon-ssm-agent
     sudo chkconfig amazon-ssm-agent on
     ```

   - For **Windows Server**:
     - The installer typically starts the service automatically. Ensure it's running from the Services management console (`services.msc`).

4. **Verify SSM Agent Installation**:
   - Check the status of SSM Agent to ensure it's running without errors:

     ```bash
     sudo systemctl status amazon-ssm-agent  # Linux
     Get-Service AmazonSSMAgent -ComputerName "."  # Windows
     ```

5. **Verify Connectivity**:
   - Go to the AWS Systems Manager console and navigate to "Managed Instances". Verify that your EC2 instance appears and shows as "Online".

Once installed and configured, your EC2 instance is ready to use with AWS Systems Manager, allowing you to manage it using various Systems Manager capabilities such as Run Command, Patch Manager, and Session Manager.

----
### What is Parameter Store?

- **Parameter Store** is a secure AWS service that provides hierarchical storage for configuration data and secrets management.
- It allows you to store and manage configuration data such as database strings, passwords, API keys, and other sensitive information.

### Creating the Parameter Store

To create a parameter in Parameter Store:
1. **Sign in to AWS Management Console:**
   - Navigate to the Parameter Store section of AWS Systems Manager.

2. **Create a Parameter:**
   - Click on "Create Parameter."
   - Enter a name and value for the parameter.
   - Choose the type of parameter (e.g., SecureString for sensitive data).
   - Configure any additional options such as encryption and tags.
   - Click "Create Parameter" to create the parameter.
----
### What is Secrets Manager?

**Secrets Manager** is an AWS service that helps you securely store, manage, and access sensitive information such as API keys, database passwords, and other credentials. It enables you to rotate, manage access, and audit usage of secrets throughout their lifecycle.

### Working with Secrets Manager

Secrets Manager allows you to:
- **Store Secrets:** Securely store sensitive information in Secrets Manager using key encryption.
- **Rotate Secrets:** Automatically rotate secrets periodically or manually to enhance security.
- **Access Controls:** Define fine-grained access policies to control who can access and manage secrets.
- **Integration:** Integrate with AWS services and third-party applications securely using secrets.

**Creating and Managing Secrets:**
   - Navigate to AWS Secrets Manager.
   - Click on "Store a new secret."
   - Enter the secret details (e.g., key-value pairs, secrets).
   - Configure rotation settings if needed.
   - Click "Next" and review the settings.
   - Click "Store" to create the secret.

