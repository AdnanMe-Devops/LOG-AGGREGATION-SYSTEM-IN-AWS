# LOG-AGGREGATION-SYSTEM-IN-AWS
Monitor Like a DevOps Pro: Build A Log Aggregation System in AWS

A sophisticated tool called a log  aggregation system gathers operational  information and logs from across your entire cloud. The log aggregation system is an advanced DevOps technique that enables you to quickly search your logs and graph any trends arising from structured logs.

In this project will create a distributed, scalable log aggregation system within AWS running on Amazon OpenSearch Service. This Log Aggregation System will ingest as much 

of your CloudWatch log stream events as you want, events generated from AWS EC2 Instances, Lambda functions, Databases, and anything else you want to submit 

log events from.Please note, this proj involves creating  Amazon OpenSearch Service domain, which can take up to twenty minutes to finish setting up. 

Compare and contrast the log analysis 
capabilities in CloudWatch Logs and 
Elastic Stack, particularly OpenSearch and Kibana Subscribe the Amazon OpenSearch Service to CloudWatch and automatically stream 
log events to OpenSearch
Search and discover log events using Kibana
Create Kibana visualizations and dashboards to monitor the state of your 

cloud avigating to  Cloud's Lambda Function will use cloudformation stack to built resourses for us ill be using a simple AWS Lambda 

function to generate logs that  will aggregate. In t a CloudFormation stack has built the 

resources for us i.e RDS,lAMDA ,Cloudwatch. Stack Present State.Note that a Log inspector is looking at 

the logs in CloudWatch Logs manually after the Lambdas publish logs into the CloudWatch Log Groups. This is very 

manual and time-consuming - we can't perform the careful searches you would want, can't search certain event fields, and can't do anything other 

than reading time-ordered logs! Furthermore, if we have more than one Lambda or source for CloudWatch Logs, like EC2 instances, reading all the logs across many systems would get complicated very quickly.so we need a system which really has the ability to search lots of logs from many different locations in one place and across any 
field through an intuitive user interface (UI). we have  log aggregation system as solution . AWS makes it easy with the AWS OpenSearch Service. It 

runs Kibana, a log aggregation and visualization tool.

Before getting to Kibana,  will create logs and inspect them using CloudWatch Logs to understand its shortcomings. In this  Step,  will inspect the Cloudformation stack 

to open a link to the Lambda function that generates the logs.
 Creating Some Logs Using AWS Lambdaand will execute the Lambda function that has been created to automatically have logs sent to CloudWatch Logs in 

this  Step. Manually Viewing Logs in Amazon CloudWatch
in this  step, will viewed the log filtering capabilities in CloudWatch Logs. 
Group Stream and Event Model While we actually can search in a log stream using the text filter, you cannot search across multiple streams  a log group at once from the 
Console. This is a serious problem because each machine, database, Lambda function, or even independent process within EC2 instances or Docker containers might have their own 

streams!we also have a problem if WE are looking for events that happened at a specific time - while streams are ordered by time, the system does not 

make sure this order is maintained across multiple streams in a log group.so we need a system that lets us:See all events for a system or logical component in one place
Maintain order across multiple streams, groups, and logical parts
Search for text or fields in events 
across our entire system
This is what a log aggregation system 
offers us. 
Launching the OpenSearch Domain
The first thing we need is an Amazon OpenSearch cluster/domain and will use 
OpenSearch because:
It's distributed
It supports aggregations
It supports free-text search
It's managed and takes care of most of the operational complexities of operating a cluster
In 2021 AWS renamed Amazon ElasticSearch Service to Amazon 
OpenSearch Service. 

Sending CloudWatch Logs to OpenSearch
Now that an Amazon OpenSearch Service domain for the log aggregation system is running, the last remaining part of the setup is to publish the logs from 
the CloudWatch Logs Group into OpenSearch. The following diagram highlights the part you are about to 

configure:


Discovering and Searching Events
Before testing out the log aggregation and log streaming we just configured, we will first create a few more test events. The stream will only pick up events from after the streaming started so OpenSearch won't be aware of the earlier events. Afterward, you will explore the discovery and search 
functionality in Kibana.Visualizing Aggregated Events
Kibana also has powerful visualization capabilities and will explore a subset of the capabilities in this project Step to 
visualize the log data streaming into 
Amazon OpenSearch from Amazon CloudWatch.

Creating a Kibana Dashboard
Kibana dashboards allow you to combine visualization to quickly get an overview of the state of an entire system. You can also filter dashboards to filter each of the individual 
visualizations that are part of the dashboard. will make a simple 
dashboard using the area chart created previously.
 
