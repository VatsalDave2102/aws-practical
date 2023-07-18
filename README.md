# aws-practical
### Host link : http://react-practical-8.s3-website.ap-south-1.amazonaws.com/
## Description
This project provides step-by-step instructions on how to upload your project to an S3 bucket, enable it as a static site, create a CloudFront distribution for the S3 bucket.

## Prerequisites
- An AWS account with appropriate permissions to access S3, CloudFront, and IAM services.
- Basic knowledge of AWS services and console navigation.

## S3 Service
Amazon Simple Storage Service (S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. It is designed to store and retrieve any amount of data from anywhere on the web.

## CloudFront Service
Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to your viewers with low latency and high transfer speeds. It integrates with other Amazon Web Services to give you a seamless experience for both static and dynamic content.

## Steps
1. **Create an S3 Bucket**
    - Log in to the AWS Management Console.
    - Open the S3 service.
    - Click on "Create bucket" and provide a unique bucket name.
    - Choose the appropriate region and click "Create."
      ![Screenshot from 2023-07-18 16-27-13](https://github.com/VatsalDave2102/aws-practical/assets/124878757/1eededb9-3bf9-40e9-b123-29dbdf1d6e69)

2. **Upload your project to the S3 bucket**
    - In the S3 management console, select the newly created bucket.
    - Click on "Upload" and select your project files.
    - Follow the on-screen instructions to upload the files.
      ![Screenshot from 2023-07-18 16-27-44](https://github.com/VatsalDave2102/aws-practical/assets/124878757/24f29ffb-adf9-40ca-be69-08c7cc4f2d25)

      
3. **Enable the static website hosting**
     - Within the S3 bucket, select the "Properties" tab.
    - Click on "Static website hosting" and choose "Use this bucket to host a website."
    - Set the index document to index.html or the appropriate entry point for your project.
    - Optionally, configure the error document to index.html or a custom error page.
      ![Screenshot from 2023-07-18 16-27-39](https://github.com/VatsalDave2102/aws-practical/assets/124878757/d1b96704-157a-4d7c-b047-be758ef7d022)

4. **Create a CloudFront Distribution**
    - Open the CloudFront service in the AWS Management Console.
   - Click on "Create Distribution" and choose "Web."
    - Configure the following settings:
       - Origin Domain Name: Select the S3 bucket you created earlier.
        - Origin Path: Leave it empty.
        - Viewer Protocol Policy: Choose "Redirect HTTP to HTTPS" or your preferred option.
        - Default Cache Behavior Settings: Leave them as default or adjust according to your requirements.
        - SSL Certificate: Choose the appropriate certificate option.
        - Default Root Object: Enter index.html or your preferred entry point.
   - Click on "Create Distribution."

6. **Add an Error Response for 403 Status**
     - Within the CloudFront distribution, select the "Error Pages" tab.
      - Click on "Create Custom Error Response."
    - Set the following values:
      - HTTP Error Code: 403: Forbidden
      - Customize Error Response: Yes
      - Response Page Path: /index.html or your preferred error page.
      - HTTP Response Code: 200: OK
    - Click on "Create."
      ![Screenshot from 2023-07-18 16-28-49](https://github.com/VatsalDave2102/aws-practical/assets/124878757/1a183ffc-cb0a-49a2-8b10-d1319bf95842)
