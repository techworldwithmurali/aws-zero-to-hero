#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### What is AWS CloudWatch 
- AWS CloudWatch is a powerful monitoring and observability service designed to provide comprehensive insights into your AWS resources and applications.
- By collecting and tracking metrics, monitoring log files, and setting alarms, CloudWatch enables you to maintain the health and performance of your infrastructure and applications.

### Key Features of CloudWatch

#### 1. **Metrics**
- **Resource Monitoring**: CloudWatch can monitor various AWS resources such as EC2 instances, RDS databases, ELB load balancers, and more.
- **Custom Metrics**: You can also monitor custom metrics generated by your applications.
- **Real-Time Metrics**: It provides real-time metrics that can help troubleshoot issues and optimize resource utilization.
  
#### Examples:
- **EC2 Instance Metrics**: CPU utilization, disk reads/writes, network traffic.
- **RDS Metrics**: Database connections, read/write IOPS, free storage space.

#### 2. **Logs**
- **Log Collection**: CloudWatch can collect log data from AWS resources and on-premises servers.
- **Log Insights**: Users can search, filter, and analyze log data to gain insights into application health and performance.
  
#### Examples:
- **Application Logs**: Errors, warnings, and informational messages from your applications.
- **System Logs**: Operating system logs, such as `/var/log/messages` on Linux or Event Viewer logs on Windows.

#### 3. **Alarms**
- **Threshold-Based Alarms**: Set alarms to trigger actions based on specific metric thresholds.
- **Notifications and Actions**: Alarms can send notifications via SNS or trigger actions like auto-scaling or Lambda functions.
  
#### Examples:
- **CPU Utilization Alarm**: Notify when CPU utilization exceeds 80% for an extended period.
- **Error Log Alarm**: Alert when a specific error message appears in the application logs.

#### 4. **Dashboards**
- **Customizable Dashboards**: CloudWatch provides dashboards that can be customized to display metrics and logs.
- **Unified View**: Dashboards offer a unified view of your AWS resources and applications, making it easier to monitor and understand their health and performance.
  
#### Examples:
- **Resource Utilization Dashboard**: Visualize CPU, memory, and network usage for EC2 instances.
- **Application Performance Dashboard**: Track response times, error rates, and throughput for web applications.

### Benefits of Using AWS CloudWatch

- **Enhanced Visibility**: Gain comprehensive insights into your AWS resources and applications.
- **Proactive Monitoring**: Set up alarms to detect and respond to potential issues before they impact your operations.
- **Cost Optimization**: Monitor resource utilization to identify and eliminate underused resources, reducing costs.
- **Operational Efficiency**: Use logs and metrics to troubleshoot and resolve issues quickly, minimizing downtime.

### Example Use Case

Suppose you have a web application hosted on EC2 instances behind an ELB load balancer. You want to ensure the application performs optimally and respond quickly to any issues. Here’s how you can use CloudWatch:

1. **Monitor EC2 Metrics**: Track CPU utilization, memory usage, and disk I/O to ensure the instances are performing well.
2. **Collect Application Logs**: Use CloudWatch Logs to gather and analyze application logs for errors and performance bottlenecks.
3. **Set Alarms**: Create alarms to notify you if CPU utilization exceeds 80% or if specific error messages appear in the logs.
4. **Create Dashboards**: Build a dashboard to visualize EC2 instance metrics, application performance, and log insights in one place.

By leveraging AWS CloudWatch, you can maintain a high level of operational excellence, quickly detect and resolve issues, and optimize the performance and cost of your AWS resources.

----
### Creating a Log Group via AWS Management Console

1. **Navigate to CloudWatch**:
   - Sign in to the AWS Management Console.
   - Open the CloudWatch console at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).

2. **Access Logs**:
   - In the left-hand navigation pane, click on **Logs**.

3. **Create Log Group**:
   - Click the **Create log group** button.
   - Enter a name for your log group in the **Log group name** field.
   - Optionally, you can add tags to your log group for better resource management and tracking.
   - Click the **Create log group** button.

----
### Lab Session - Sending VPC Flow Logs to a CloudWatch Log Group

### Step 1: Create a CloudWatch Log Group

If you haven't already created a CloudWatch Log Group, follow these steps:

1. **Navigate to CloudWatch**:
   - Sign in to the AWS Management Console.
   - Open the CloudWatch console at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).

2. **Access Logs**:
   - In the left-hand navigation pane, click on **Logs**.

3. **Create Log Group**:
   - Click the **Create log group** button.
   - Enter a name for your log group, such as `VPCFlowLogs`.
   - Optionally, you can add tags to your log group.
   - Click the **Create log group** button.

### Step 2: Create an IAM Role

You need an IAM role that has the necessary permissions to publish flow logs to CloudWatch Logs.

1. **Navigate to IAM**:
   - Open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/).

2. **Create Role**:
   - In the left-hand navigation pane, click on **Roles** and then **Create role**.
   - Select **AWS Service** and then **EC2**.
   - Click **Next: Permissions**.

3. **Attach Policies**:
   - Attach the following policies:
     - `CloudWatchLogsFullAccess`
     - `AmazonEC2FullAccess`

4. **Create Role**:
   - Click **Next: Tags**, then **Next: Review**.
   - Enter a role name, such as `VPCFlowLogsRole`.
   - Click **Create role**.

### Step 3: Create VPC Flow Logs

1. **Navigate to VPC**:
   - Open the VPC console at [https://console.aws.amazon.com/vpc/](https://console.aws.amazon.com/vpc/).

2. **Access Flow Logs**:
   - In the left-hand navigation pane, click on **Your VPCs**.
   - Select the VPC for which you want to create a flow log.
   - In the **Actions** dropdown menu, select **Create flow log**.

3. **Configure Flow Log**:
   - **Filter**: Choose the type of traffic to capture (e.g., All, Reject, or Accept).
   - **Destination**: Select **Send to CloudWatch Logs**.
   - **Log Group**: Enter the name of the CloudWatch Log Group you created (`VPCFlowLogs`).
   - **IAM Role**: Select the IAM role you created (`VPCFlowLogsRole`).

4. **Create Flow Log**:
   - Click the **Create flow log** button.

### Verifying Flow Logs

1. **Navigate to CloudWatch Logs**:
   - Go to the CloudWatch console and select **Logs** from the left-hand navigation pane.

2. **Check Log Streams**:
   - Find and select the log group `VPCFlowLogs`.
   - You should see log streams corresponding to the network interfaces within your VPC, containing the flow log records.

----
### Lab Session - Setting Up a CloudWatch Alarm for an EC2 Instance

1. **Navigate to CloudWatch**:
   - Sign in to the AWS Management Console.
   - Open the CloudWatch console at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).

2. **Create Alarm**:
   - In the left-hand navigation pane, click on **Alarms**.
   - Click the **Create alarm** button.

3. **Select Metric**:
   - Click **Select metric**.
   - Choose **EC2 metrics**.
   - Select **Per-Instance Metrics**.
   - Choose the EC2 instance and the metric you want to monitor (e.g., **CPUUtilization**).

4. **Configure Metric and Conditions**:
   - Specify the conditions for the alarm (e.g., CPU utilization > 80% for 5 minutes).
   - Click **Next**.

5. **Configure Actions**:
   - Specify what actions to take when the alarm state is triggered (e.g., send a notification to an SNS topic).
   - Click **Next**.

6. **Add Notification**:
   - If you don't have an SNS topic, you can create one and subscribe to it with your email or SMS.
   - Select an existing SNS topic or create a new one for alarm notifications.

7. **Configure Alarm Name and Description**:
   - Provide a name and an optional description for the alarm.
   - Click **Next**.

8. **Review and Create Alarm**:
   - Review the alarm settings.
   - Click **Create alarm**.

### Verifying the Alarm

1. **Navigate to CloudWatch Alarms**:
   - Go to the CloudWatch console and select **Alarms** from the left-hand navigation pane.

2. **Check Alarm Status**:
   - Verify that your alarm is listed and check its state (e.g., OK, ALARM, INSUFFICIENT_DATA).
   - Test the alarm by creating conditions that trigger it (e.g., increase CPU utilization).

### Notifications

- **Email Notifications**: Ensure you have subscribed to the SNS topic via email and confirmed the subscription.
- **SMS Notifications**: Ensure you have subscribed to the SNS topic via SMS and confirmed the subscription.

----
### What is AWS CloudTrail?

- AWS CloudTrail is a service provided by Amazon Web Services (AWS) that enables governance, compliance, and operational and risk auditing of your AWS account.
- It records and logs all API calls made on your AWS account, whether through the AWS Management Console, AWS SDKs, command line tools, or other AWS services.

### Key Features of AWS CloudTrail:

1. **Logging AWS API Calls**:
   - CloudTrail captures detailed information about each API call made on your AWS account. This includes who made the call, the source IP address from which the call was made, when it was made, and what actions were performed.

2. **Visibility and Governance**:
   - Provides a comprehensive history of AWS API calls for auditing purposes, helping you ensure compliance with internal policies and regulatory requirements.

3. **Security Analysis and Troubleshooting**:
   - CloudTrail logs can be used for security analysis, resource change tracking, and troubleshooting operational issues.

4. **Integration with Other AWS Services**:
   - Integrates with AWS services like CloudWatch Logs for real-time log monitoring, S3 for log file storage, and AWS Lambda for automated responses to events.

5. **Event History**:
   - Maintains a history of API calls over time, allowing you to view and analyze changes in your AWS environment.

6. **Trail Configuration**:
   - You can configure CloudTrail to create a trail, which is a configuration enabling CloudTrail to deliver log files to an S3 bucket, CloudWatch Logs, or both.

7. **Log File Integrity**:
   - CloudTrail log files are cryptographically signed and stored in a specified S3 bucket, helping ensure their integrity and providing an additional layer of security.

### Use Cases for AWS CloudTrail:

- **Security and Compliance Auditing**: Helps meet compliance requirements by providing an audit trail of API calls and changes to resources.
  
- **Operational Troubleshooting**: Enables tracking and analysis of changes to resources, aiding in troubleshooting operational issues.
  
- **Change Management**: Facilitates monitoring of resource changes and configuration updates over time.

- **Security Analysis**: Provides visibility into unauthorized or unusual activity by monitoring API calls.

- **Automated Response**: Integration with AWS Lambda allows automated responses to specific events or changes detected in CloudTrail logs.

### Log Event Types in CloudTrail

1. **Management Events**:
   - **Create**: Actions related to creating AWS resources, such as launching EC2 instances, creating S3 buckets, or provisioning RDS databases.
   - **Delete**: Actions related to deleting AWS resources, such as terminating EC2 instances, deleting S3 objects or buckets, or deleting IAM roles.
   - **Update**: Actions related to updating AWS resources, such as modifying security group rules, updating IAM policies, or modifying S3 bucket policies.
   - **Describe**: Actions related to describing or retrieving information about AWS resources, such as listing EC2 instances, describing IAM roles, or fetching S3 bucket details.

2. **Data Events**:
   - **Read**: Actions related to reading data from AWS resources, such as downloading files from S3 buckets or retrieving data from DynamoDB tables.
   - **Write**: Actions related to writing data to AWS resources, such as uploading files to S3 buckets, putting objects to S3, or inserting data into DynamoDB tables.
   - **Permission Changes**: Actions related to changes in permissions or policies for AWS resources, such as updating IAM policies, modifying S3 bucket policies, or changing EC2 security group rules.

3. **Control Plane Events**:
   - **AWS Service Events**: Actions triggered by AWS services, such as automated scaling events, CloudFormation stack creation events, or AWS Lambda function executions.
   - **Account Management Events**: Actions related to AWS account management, such as IAM user login events, password changes, or changes to IAM roles.

4. **Console Sign-in Events**:
   - Events related to console sign-in activities, including successful and failed login attempts, and actions performed via the AWS Management Console.

5. **CloudTrail Insights Events**:
   - Insights events generated by CloudTrail Insights, which analyzes CloudTrail logs to identify unusual activity patterns and potential security threats.

### Example Event Types in CloudTrail:

- `CreateBucket`: Indicates the creation of an S3 bucket.
- `RunInstances`: Indicates the launching of EC2 instances.
- `DeleteObject`: Indicates the deletion of an object in an S3 bucket.
- `ModifyInstanceAttribute`: Indicates the modification of attributes for an EC2 instance.
- `PutObject`: Indicates the putting of an object into an S3 bucket.
- `DescribeInstances`: Indicates the description of EC2 instances.

----
### Lab Session - Configuring AWS CloudTrail to Send Logs to S3

#### 1. **Sign in to AWS Management Console**
   - Go to [AWS Management Console](https://aws.amazon.com/console/) and sign in with your credentials.

#### 2. **Navigate to CloudTrail**

   - Open the **CloudTrail console** at [https://console.aws.amazon.com/cloudtrail/](https://console.aws.amazon.com/cloudtrail/).

#### 3. **Create a New Trail**

   - In the CloudTrail dashboard, click on **Trails** in the left-hand navigation pane.
   - Click on **Create trail**.

#### 4. **Configure Trail Settings**

   - **Trail Name**: Enter a name for your trail (e.g., `MyCloudTrail`).
   - **Storage Location**: Choose **S3** from the drop-down menu.
   - **S3 Bucket**: Select an existing S3 bucket or create a new one to store your CloudTrail logs.
   - **Enable CloudWatch Logs**: Optionally, you can enable CloudWatch Logs for real-time monitoring of CloudTrail log file delivery.
   - **Encrypt Log Files**: Optionally, enable encryption for your log files using AWS KMS.
   - **Apply trail to all regions**: Choose whether to apply the trail to all regions or specific regions.

#### 5. **Create or Update an IAM Role**

   - If you haven't already configured a CloudTrail service-linked role or an IAM role for CloudTrail, you'll be prompted to create or update one during trail creation.
   - Ensure the IAM role has permissions to write logs to your chosen S3 bucket.

#### 6. **Specify Advanced Event Logging (Optional)**

   - **Management Events**: Choose to log management events like create, modify, and delete actions on AWS resources.
   - **Data Events**: Choose to log data events like S3 object-level activities and Lambda function executions.
   - Configure any other advanced settings as per your requirements.

#### 7. **Review and Create Trail**

   - Review all the settings you’ve configured for your trail.
   - Click **Create trail** to create your CloudTrail and start sending logs to the specified S3 bucket.

----
### Deleting CloudWatch Alarms

1. **Using the AWS Management Console:**
   - Sign in to the AWS Management Console.
   - Navigate to the **CloudWatch console** at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).
   - In the left-hand navigation pane, click on **Alarms**.
   - Select the alarm(s) you want to delete.
   - Click **Actions** and then **Delete**.
   - Confirm the deletion.
----
### Deleting CloudWatch Logs

1. **Using the AWS Management Console:**
   - Sign in to the AWS Management Console.
   - Navigate to the **CloudWatch console** at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).
   - In the left-hand navigation pane, click on **Logs**.
   - Select the log group(s) you want to delete.
   - Click **Actions** and then **Delete log group**.
   - Confirm the deletion.
----

### Deleting CloudWatch Dashboards

1. **Using the AWS Management Console:**
   - Sign in to the AWS Management Console.
   - Navigate to the **CloudWatch console** at [https://console.aws.amazon.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/).
   - In the left-hand navigation pane, click on **Dashboards**.
   - Select the dashboard(s) you want to delete.
   - Click **Actions** and then **Delete**.
   - Confirm the deletion.
----
### Lab Session - Deletion of CloudTrail

1. **Sign in to AWS Management Console:**
   - Navigate to the CloudTrail Dashboard at [AWS Management Console](https://console.aws.amazon.com/cloudtrail/).

2. **Delete CloudTrail:**
   - Select the CloudTrail trail you want to delete.
   - Click on "Actions > Delete trail."
   - Confirm the deletion.

