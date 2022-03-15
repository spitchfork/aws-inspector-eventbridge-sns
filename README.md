# AWS Inspector Eventbridge Sample
A sample project demonstrating publishing AWS Inspector vulnerability findings to SNS topics.

## Summary
Installs an old version of Apache httpd (v2.4.33 - latest is v2.4.53) with known vulnerabilities to demonstrate Inspector automated vulnerability scanning.  
Inspector vulnerability findings are routed to an email via Eventbridge and SNS.

## Pre-Requisites
AWS Inspector is enabled in your account/org - note this is a paid service but a trial is available: https://aws.amazon.com/inspector/pricing/

##Usage
`aws cloudformation create-stack --stack-name inspector-test --template-body file://example-stack.json --parameters ParameterKey=AdminIP,ParameterValue=<your IP>/32 ParameterKey=Owner,ParameterValue=<your name> ParameterKey=KeyName,ParameterValue=<your key> ParameterKey=AssociatePublicIP,ParameterValue=true ParameterKey=EmailSubscriptionEndpoint,ParameterValue=<your email> --capabilities CAPABILITY_IAM`