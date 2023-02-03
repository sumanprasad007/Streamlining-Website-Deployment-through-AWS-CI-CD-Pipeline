# Streamlining Website Deployment through AWS CI/CD Pipeline
![Architecture of AWS CodePiple for Website deployed in S3](https://user-images.githubusercontent.com/55047333/216131323-62a967fc-0c65-4394-9864-7ec6b3de025d.png)



The HTML code you provided is a basic website template that includes a header, a section for service icons, and a subscribe section.

The header includes a logo, a title, and a brief description of the website. The section for service icons includes three boxes that display icons and brief descriptions for development, friendly support, and live support services. The subscribe section includes a form for users to subscribe to the website's newsletter. The code also includes CSS for styling and JavaScript for preloading the website. Additionally, it uses the Font Awesome library for icons and the Respond.js library for compatibility with older browsers. To streamline the deployment of this website, you can use AWS CI/CD pipeline. AWS CI/CD pipeline is a suite of tools provided by Amazon Web Services that helps you automate the process of building, testing, and deploying your code.

# Here's how you can set up the pipeline:

Store the website code in an AWS CodeCommit repository.

Use AWS CodeBuild to build and test the code.

Use AWS CodeDeploy to deploy the code to an EC2 instance or an S3 bucket.

Use AWS CloudFormation to automate the creation and management of the resources required for the pipeline.

By using this pipeline, you can automate the process of deploying your website, reducing the time and effort required to manually deploy updates. Additionally, the pipeline can be configured to automatically deploy updates whenever changes are made to the code, ensuring that your website is always up-to-date.

# CodeBuild Role should have follwoing:

1. S3FullAccess
2. CloudWatchFullAccess
3. CodeBuildAccess

# S3 Destination Bucket

It should have all the necessary permission to host the static website. Like, Static Hosting should be enable, Bucket should have public access and providing the Access Control List (ACL) permission to the owner. 

# BuildSpce file Details

Its the file which, AWS CodeBuild directly access and according to the steps of commands defined in the file CodeBuild starts the execution. This commands can be any AWS CLI based command, Linux based commands. It's more like, launch a Linux OS installing all the dependencies and running as a container, where provides root privileged based terminal to execute the commands and get the work done! 

![image](https://user-images.githubusercontent.com/55047333/215684406-55f2b4b7-7173-4d78-aae6-198146eae346.png)
