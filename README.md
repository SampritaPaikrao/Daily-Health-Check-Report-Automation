📊 AWS CloudWatch Monitoring & Health Check Automation

This project is a serverless AWS monitoring solution built using AWS Lambda that automatically collects, analyzes, and reports EC2 and RDS performance metrics from Amazon CloudWatch.

It evaluates CPU, Memory, and Disk utilization over the last 24 hours, generates a health status, exports the data into an Excel report, uploads it to Amazon S3, and sends the report via email using Amazon SES.

A. FEATURES

 1. Monitor EC2 and RDS instances
 2. Analyze last 24 hours CloudWatch metrics
 3. Calculate Average & Maximum utilization (%)
 4. Threshold-based health status (OK / BAD)
 5. Auto-generate Excel report
 6. Upload report to Amazon S3
 7. Email report automatically using Amazon SES
 8. Fully serverless & automated


B. TECH STACK

 1. AWS Lambda (Python)
 2. Amazon CloudWatch
 3. Amazon EC2
 4. Amazon RDS
 5. Amazon S3
 6. Amazon SES
 7. OpenPyXL (Excel generation)


C. ARCHITECTURE OVERVIEW

 1. Lambda is triggered manually or via scheduler
 2. CloudWatch metrics fetched for EC2 & RDS
 3. Avg & Max utilization calculated
 4. Health status evaluated using thresholds
 5. Excel report generated
 6. Report uploaded to S3
 7. Email sent with Excel attachment


D. METRICS COLLECTED

 1. EC2
    - CPUUtilization
    - Memory Usage (%) (via CloudWatch Agent)
    - Disk Usage (%) (via CloudWatch Agent)

 2. RDS
    - CPUUtilization
    - FreeableMemory → Converted to Memory Used (%)
    - FreeStorageSpace → Converted to Disk Used (%)


E. EXCEL REPORTS INCLUDES

 1. Resource Type (EC2 / RDS)
 2. Resource Name & ID
 3. CPU Avg & Max (24h)
 4. Memory Avg & Max (24h)
 5. Disk Avg & Max (24h)
 6. Individual metric status
 7. Overall health status
 8. Timestamp


F. IAM PERMISSION REQUIRED

 1. CloudWatch: GetMetricStatistics
 2. EC2: DescribeInstances
 3. RDS: DescribeDBInstances
 4. S3: PutObject
 5. SES: SendRawEmail


G. USE CASES

 1. Daily infrastructure health checks
 2. Proactive performance monitoring
 3. Cost visibility & optimization
 4. Ops / DevOps automation
 5. Production readiness reporting


H. NOTES

 1. EC2 Memory & Disk metrics require CloudWatch Agent
 2. RDS metrics are available by default (no agent required)
 3. SES email IDs must be verified (Sandbox limitation)

I. LICENSE
 
 This project is for learning, automation, and internal monitoring purposes.
