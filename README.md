# Smart Home Temperature Anomaly Detection

This repository contains the implementation of an automated anomaly detection system for temperature data in a smart home environment using AWS services. The project integrates various AWS tools and services, including EC2, Kinesis, DynamoDB, SNS, S3, Lambda, and CodeDeploy, to provide a scalable and efficient solution for real-time monitoring and alerting.

## Project Overview

The goal of this project is to automate the detection of anomalies in temperature data from IoT devices. The workflow includes:
Real-time data ingestion using Kinesis.
Storage and logging of sensor data in DynamoDB.
Anomaly detection using a Lambda function.
Automated notifications through SNS.
Deployment automation using S3 and CodeDeploy.

## Architecture

The architecture consists of:
EC2 Instance: For running the Python ingestion script.
Kinesis Data Streams: For ingesting real-time sensor data.
DynamoDB: For storing and managing temperature data.
SNS: For sending email alerts upon detecting anomalies.
Lambda Function: For analyzing the data and detecting anomalies.
S3 and CodeDeploy: For automating the deployment of the application.

## Tasks

Task 1: Initial Setup

Provision EC2, Kinesis, DynamoDB, and SNS using CloudFormation.
Manually set up the Python ingestion script on the EC2 instance.
Create a Lambda function via the AWS Console and configure it to:
Analyze data for anomalies.
Send alerts via SNS.

Task 2: Deployment Automation

Use CloudFormation to provision S3 and store:
The ingestion script.
The appspec.yml file.CodeDeploy uses it to manage the application deployment on the EC2 instance.
Deploy the application from S3 to EC2 using CodeDeploy.
Keep the Lambda function manually deployed via the AWS Console.

Task 3: Full Automation

Automate the provisioning of the Lambda function using CloudFormation.
Replace the older manually deployed Lambda function with the automated one.
Update the Lambda code with new configurations (SNS ARN, DynamoDB table name).

## Usage Instructions

## Prerequisites

AWS account with access to EC2, Kinesis, DynamoDB, SNS, S3, Lambda, and CodeDeploy.
AWS CLI and CloudFormation templates.
Python installed on the local system for script development.

## Steps to Run

-SSH into the EC2 instance and set up the ingestion script.
-Configure the Lambda function through the AWS Console or CloudFormation.
-Deploy the application to EC2 using CodeDeploy.
-Monitor Kinesis streams and DynamoDB logs for incoming data.
-Test anomaly detection and verify SNS notifications.

## Files and Directories

/templates/: CloudFormation templates for provisioning AWS resources.
/scripts/: Python scripts for data ingestion and anomaly detection.
/deployment/: appspec.yml and related files for CodeDeploy.

## Results

Real-time temperature data is ingested and stored in DynamoDB.
Anomalies in temperature data are detected and notified via SNS email alerts.
Deployment is automated using S3 and CodeDeploy.
