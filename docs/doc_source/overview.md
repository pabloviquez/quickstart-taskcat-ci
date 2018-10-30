# Overview<a name="overview"></a>

 TaskCat is an open\-source tool that tests AWS CloudFormation templates\. TaskCat tests your templates by creating a stack in multiple AWS Regions simultaneously, and generates a report with a pass/fail grade for each region\. You can specify the regions, indicate the number of Availability Zones you want to include in the test, and pass in the AWS CloudFormation parameter values you want to test\. TaskCat is implemented in Python and is available in two formats: as a **pip** module and in a Docker container\. 

**Note**  
 TaskCat was developed by the AWS Quick Start team as an internal tool, to automatically test the AWS CloudFormation templates for Quick Starts\. It is now available as an [open\-source tool in GitHub](https://github.com/aws-quickstart/taskcat), and you can use this Quick Start to easily deploy TaskCat into your AWS account\. 

 The AWS Cloud makes it easy for developers to code, build, and deploy software\. AWS has a continuous integration \(CI\) orchestration service called AWS CodePipeline and multiple deployment options to help developers quickly deploy and manage their software\. Using AWS CodePipeline with TaskCat makes it easy to continuously build and test your AWS CloudFormation templates whenever you change them\. 

 You can use this Quick Start to test any AWS CloudFormation templates, including nested templates\. Your templates must be available in a GitHub repository, which you set up by following the instructions in the [Prerequisites](deployment.md#prerequisites) section\. 

 This guide provides infrastructure and configuration information for planning and deploying a continuous CI/CD pipeline for AWS CloudFormation templates on the AWS Cloud\. It doesn’t cover the TaskCat tool in detail\. For general guidance and best practices for TaskCat, see the [TaskCat documentation](https://aws-quickstart.github.io/auto-testing.html)\. 

## Cost and Licenses<a name="cost"></a>

 You are responsible for the cost of the AWS services used while running this Quick Start reference deployment\. There is no additional cost for using the Quick Start\. 

 The AWS CloudFormation template for this Quick Start includes configuration parameters that you can customize\. For cost estimates, see the pricing pages for each AWS service you will be using\. Prices are subject to change\. 

**Tip**  
 After you deploy the Quick Start, we recommend that you enable the [AWS Cost and Usage Report](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-gettingstarted-turnonreports.html) to track costs associated with the Quick Start\. This report delivers billing metrics to an S3 bucket in your account\. It provides cost estimates based on usage throughout each month, and finalizes the data at the end of the month\. For more information about the report, see the [AWS documentation](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage.html)\. 

 This Quick Start deploys AWS TaskCat, which is open source and free to use under the Apache 2\.0 license\. 

## AWS Services<a name="services"></a>

 The core AWS components used by this Quick Start includes the following services\. \(If you are new to AWS, see [Getting Started with AWS](https://aws.amazon.com/getting-started/)\.\) 

 For information about how the Quick Start uses these services, see the [Pipeline Workflow](pipeline.md) section later in this guide\. 
+  [Amazon S3](https://aws.amazon.com/s3/) – Amazon Simple Storage Service \(Amazon S3\) provides developers and IT teams with secure, durable, highly\-scalable cloud storage\. Amazon S3 offers easy\-to\-use object storage, and includes a simple web interface so you can store and retrieve any amount of data from anywhere on the web\. With Amazon S3, you pay only for the storage you actually use\. There is no minimum fee and no setup cost\. 
+  [AWS CodePipeline](https://aws.amazon.com/codepipeline/) – AWS CodePipeline is a continuous delivery service for fast and reliable application updates\. CodePipeline builds, tests, and deploys your code every time there is a code change, based on the release process models you define\. You can rapidly and reliably deliver features and updates\. You can easily build an end\-to\-end solution by using our pre\-built plugins for popular third\-party services like GitHub, or by integrating your own custom plugins into any stage of your release process\. With CodePipeline, you pay only for what you use\. There are no upfront fees or long\-term commitments\. 
+  [AWS CodeBuild](https://aws.amazon.com/codebuild/) – AWS CodeBuild is a fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy\. With CodeBuild, you don’t need to provision, manage, and scale your own build servers\. CodeBuild scales continuously and processes multiple builds concurrently, so your builds are not left waiting in a queue\. You can get started quickly by using prepackaged build environments, or you can create custom build environments that use your own build tools\. With CodeBuild, you are charged by the minute for the compute resources you use\. 
+  [AWS CodeDeploy](https://aws.amazon.com/codedeploy/) – AWS CodeDeploy automates code deployments to any instance, including Amazon Elastic Compute Cloud \(Amazon EC2\) instances and instances running on premises\. CodeDeploy makes it easier for you to rapidly release new features, helps you avoid downtime during application deployment, and handles the complexity of updating your applications\. You can use CodeDeploy to automate your software deployments, and to eliminate the need for error\-prone manual operations\. The service scales with your infrastructure so you can easily deploy to one instance or to thousands of instances\. 
+  [AWS Lambda](https://aws.amazon.com/lambda/) – AWS Lambda lets you run code without provisioning or managing servers\. You pay only for the compute time you consume─there is no charge when your code isn’t running\. With Lambda, you can run code for virtually any type of application or backend service—all with zero administration\. Upload your code and Lambda takes care of requirements for running and scaling your code with high availability\. You can set up your code to automatically trigger from other AWS services or call it directly from any web or mobile app\. 
+  [AWS CloudFormation](https://aws.amazon.com/documentation/cloudformation/) – AWS CloudFormation gives you an easy way to create and manage a collection of related AWS resources, and provision and update them in an orderly and predictable way\. You use a template to describe all the AWS resources \(e\.g\., EC2 instances\) that you want\. You don't have to individually create and configure the resources or figure out dependencies—AWS CloudFormation handles all of that\. 