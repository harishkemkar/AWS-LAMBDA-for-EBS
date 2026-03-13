🛡️ CloudStandard EBS
An event-driven AWS Lambda function designed to automatically enforce infrastructure standards. This tool intercepts EBS creation events via Amazon EventBridge to ensure all volumes adhere to predefined configurations (e.g., gp2 type and 200GB size), preventing cost overruns and performance inconsistencies.
________________________________________
🚀 Features
•	Automated Remediation: Instantly updates volume type and size upon resource creation.
•	Intelligent ARN Parsing: Custom logic to extract VolumeId from complex AWS Amazon Resource Names.
•	Boto3 Orchestration: Leverages the AWS SDK for Python for high-performance resource management.
🛠️ How It Works
1.	Trigger: An EventBridge rule detects a CreateVolume or ModifyVolume API call.
2.	Lambda Execution: The event metadata (JSON) is passed to the function.
3.	Optimization: The script parses the resource ID and invokes the modify_volume API to enforce compliance.
📂 Project Structure
•	get_volume_id_from_arm: Utility function to isolate unique IDs from AWS ARN strings.
•	lambda_handler: Main entry point that manages the EC2 client initialization and logic execution.
📋 Prerequisites
•	Runtime: Python 3.x
•	IAM Permissions: The Lambda execution role requires the following policy:
