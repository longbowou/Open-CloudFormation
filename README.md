# Open CloudFormation

Deploy [Open](https://github.com/longbowou/open-frontend) app’s serverless backend and sleek frontend (built with React,
TypeScript, and Tailwind CSS) is a breeze
with AWS CloudFormation. In just a few simple steps, you’ll set up a fully scalable infrastructure to support user
authentication, image uploads, profile management. Here’s how to get your app running in no time.

![Screenshot 2024-10-22 at 9.43.18 PM.png](screenshots/cloudformation/Screenshot%202024-10-22%20at%209.43.18%E2%80%AFPM.png)

## Deployment Steps

### 1. Create an S3 Bucket for Source Files

Start by creating an S3 bucket that and upload at the root of the S3 bucket the app’s source files herein this folder.
Make sure versioning is enabled—this is required for AWS CodePipeline to handle the source code in the app’s build and
deploy stages. Once the bucket is created, note down its name, as you’ll need it in the next step.

### 2. Import the CloudFormation Template

Next, head over to AWS CloudFormation and upload the [template.yml](template.yml) file. When prompted, set the
SourceBucketName parameter to the name of the S3 bucket you just created. This template will automatically set up all
the backend resources needed to power your app, including API Gateway, AWS Lambda, DynamoDB, S3, and CloudFront.

### 3. Launch the Stack and Watch It Build

After importing the template, launch the CloudFormation stack and let AWS handle the heavy lifting. Once the resource
creation is complete, navigate to the Outputs tab in CloudFormation to click on the link to your CloudFront
distribution.
This URL is your live app, ready to provide blazing-fast user experiences globally, thanks to CloudFront’s content
distribution.

### 4. Clean Up Before Deleting

When it’s time to tear down the stack, remember to empty the S3 buckets (the source bucket and the media bucket
created for image uploads) before deleting the CloudFormation stack. This ensures a smooth cleanup process and
prevents residual data from lingering.

## Why CloudFormation Makes Your Deployment Effortless

By using CloudFormation, you can deploy and manage all critical AWS resources such as API Gateway, Lambda, DynamoDB, S3,
and CloudFront in just a few clicks. This approach gives you the power of a fully serverless architecture without the
hassle of manual resource setup. With automated scalability and seamless integration, your app will be ready to handle
user traffic and media uploads with zero server management.

Now, watch your React- and Tailwind-powered frontend paired with AWS Lambda and API Gateway take flight—delivering
scalable, fast, and secure user interactions.

### What's next ?

Check the [main](https://github.com/longbowou/open-frontend) repository this one is part of.

## Screenshots

![Screenshot 2024-10-22 at 9.41.38 PM.png](screenshots/cloudformation/Screenshot%202024-10-22%20at%209.41.38%E2%80%AFPM.png)
![Screenshot 2024-10-22 at 9.41.45 PM.png](screenshots/cloudformation/Screenshot%202024-10-22%20at%209.41.45%E2%80%AFPM.png)

## License

This project is licensed under the [MIT License](LICENSE).