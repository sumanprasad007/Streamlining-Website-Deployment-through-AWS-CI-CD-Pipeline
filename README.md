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

1. Static Hosting:
  Static hosting refers to hosting a website that consists of only static content, such as HTML, CSS, and JavaScript files. Static hosting provides a simple and cost-   effective way to host a website, and it can be easily scaled to handle traffic spikes.

2. Bucket with Public Access:
   Bucket is a term used in cloud storage services like Amazon S3 to refer to a container for storing files. To host a static website, the bucket must have public        access enabled. This means that anyone with the URL of a file stored in the bucket can access it without any authentication.

3. Access Control List (ACL) Permission:
   An Access Control List (ACL) is a set of rules that specify who has access to a particular resource, such as a bucket in Amazon S3. The ACL defines the permissions    that are assigned to the bucket owner, such as read, write, and execute permissions. Providing the ACL permission to the owner ensures that they have the necessary    access to manage the files stored in the bucket, such as uploading and deleting files.

In summary, to host a static website using a cloud storage service like Amazon S3, it is necessary to enable Static Hosting, provide public access to the bucket, and provide the ACL permission to the owner. These steps ensure that the website is hosted correctly and that the owner has the necessary access to manage the files stored in the bucket.

# BuildSpce file Details

Its the file which, AWS CodeBuild directly access and according to the steps of commands defined in the file CodeBuild starts the execution. This commands can be any AWS CLI based command, Linux based commands. It's more like, launch a Linux OS installing all the dependencies and running as a container, where provides root privileged based terminal to execute the commands and get the work done! 

![image](https://user-images.githubusercontent.com/55047333/215684406-55f2b4b7-7173-4d78-aae6-198146eae346.png)
