# lamda-ips
This is simple python code that automates network access list creation by reading the content of AWS guardduty alert. This script supports only two types of alerts; PortProbeUnprotectedPort and SSHBruteForce alerts. 

# Deployment
Create a lambda function with python runtime (>v3.7), copy and paste the content of "main.py" file.
Assign necessary IAM permission to the lambda function (assinged policy should be able to create NACL ingress rule and cloudwatch put log)
enable GuardDuty and configure AWS eventBridge to deliver Guarduty findings to SNS
Subscribe the lambda function to the SNS created above
Optionally, create a slack group and perform email SNS subscription using the slack group email address to deliver alerts to slack (IDS)
