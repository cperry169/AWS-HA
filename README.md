# AWS-HA

# AWS-HA

1.3 Overview of this project
<br/>
Launch a simple API utilizing automation and AWS best practices.

1.4 REQUIREMENTS

### DynamoDB table
- Must contain multiple unique records (sample structure provided below, you may
determine your own schema as desired) 

### Lambda Function
- Must be written in language supported natively by AWS (Node.js, Java, C#, Go, Python – NO SHIMS)
- Must log execution output to CloudWatch Logs
- API Gateway with two stages (dev and prod) exposing endpoints for the Lambda function
- Must have a path to expose all DynamoDB records as well as a single record § Example:
- /id should return a list of all records
* 1
* 2
* 3
* 4
* 5
-  /id/5 should return the details of record #5 in DynamoDB
```html {
“id”: “5”,
“details” {
“firstName”: “<VALUE>”,
“lastName”: “<VALUE>” }
}
```  

### CloudWatch Logs
- Must have a retention policy of 30 days
- IAM roles and policies must be created in a least permissive model (AVOID USING AWS MANAGED POLICIES)
- All AWS resources must be created using Serverless Framework, Terraform, or CloudFormation
- No resources may be created or managed by hand other than EC2 SSH keys
