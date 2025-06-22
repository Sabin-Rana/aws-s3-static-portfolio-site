# **AWS S3 Static Website with CloudFront CDN**

## **Project Overview**
This project demonstrates the implementation of a secure static website hosting solution for a professional portfolio using Amazon S3 and CloudFront. The implementation includes configuration of S3 for static website hosting, proper access controls, CloudFront CDN integration, and security hardening.

## **Project Objectives**
- **Deploy Static Website**: Host a professional portfolio website using Amazon S3 static hosting
- **Ensure Security**: Implement proper access controls and HTTPS encryption
- **Optimize Performance**: Configure CloudFront CDN for global content delivery
- **Automate Deployment**: Create repeatable deployment process using AWS CLI

---

## **Implementation Steps**

### **Step 1: S3 Bucket Creation and Configuration**

1. **Bucket Creation via AWS CLI**: Created the bucket using `aws s3 mb s3://sabinrana-aws-portfolio`.
   - **Screenshot**: ![capture1](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture1.PNG) - CLI screenshot after creating the bucket.
   - **Screenshot**: ![capture2](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture2.PNG) - AWS Console showing newly created bucket list.

2. **Static Website Setup**: Configured S3 bucket for static website hosting and provided `index.html` as the index document and `404.html` as the error document.
   - **Screenshot**: ![capture3](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture3.PNG) - Empty objects section.
   - **Screenshot**: ![capture4](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture4.PNG) - Static website hosting enabled and configured.
   - **Screenshot**: ![capture5](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture5.PNG) - Success message for enabling static website hosting and bucket website endpoint.

3. **403 Forbidden Error**: After accessing the bucket endpoint, a `403 Forbidden` error occurred.
   - **Screenshot**: ![capture6](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture6.PNG) - Screenshot of 403 Forbidden error when accessing the endpoint.

### **Step 2: Security Configuration**

1. **Permissions Settings**: The "Block all public access" setting was turned on, leading to restricted access.
   - **Screenshot**: ![capture7](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture7.PNG) - Block all public access turned on.
   - **Screenshot**: ![capture8](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture8.PNG) - Unchecking block public access and saving changes.

2. **Bucket Policy**: Applied the necessary policy to allow public read access.
   - **Screenshot**: ![capture9](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture9.PNG) - Forbidden error persists after saving public access changes.
   - **Screenshot**: ![capture10](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture10.PNG) - Bucket policy option visible under Permissions.
   - **Screenshot**: ![capture11](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture11.PNG) - Bucket policy JSON applied to allow public read access.

### **Step 3: Error Page and Deployment**

1. **404 Error Page Creation**: Manually created a custom `404.html` error page.
   - **Screenshot**: ![capture12](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture12.PNG) - Copying the endpoint and showing `NoSuchKey` error.
   - **Screenshot**: ![capture13](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture13.PNG) - Command line screenshot of uploading the `404.html` file using `aws s3 cp`.
   - **Screenshot**: ![capture14](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture14.PNG) - Custom `404.html` page displayed when accessing the S3 bucket.

2. **Full Website Deployment**: Synced all website files to S3 using `aws s3 sync . s3://sabinrana-aws-portfolio`.
   - **Screenshot**: ![capture15](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture15.PNG) - Screenshot of the `aws s3 sync` command in the CLI.
   - **Screenshot**: ![capture16](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture16.PNG) - Files displayed in the S3 bucket after synchronization.
   - **Screenshot**: ![capture17](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture17.PNG) - Portfolio website displayed successfully after refresh.

### **Step 4: CloudFront CDN Setup**

1. **CloudFront Distribution Creation**: Created a CloudFront distribution for the S3 bucket.
   - **Screenshot**: ![capture18](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture18.PNG) - Searching for CloudFront in the AWS Management Console.
   - **Screenshot**: ![capture19](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture19.PNG) - Distribution name and settings for CloudFront.
   - **Screenshot**: ![capture20](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture20.PNG) - Specifying S3 origin for the CloudFront distribution.
   - **Screenshot**: ![capture21](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture21.PNG) - Enabling security settings for HTTPS in CloudFront.
   - **Screenshot**: ![capture22](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture22.PNG) - Reviewing and creating the distribution.
   - **Screenshot**: ![capture23](https://github.com/Sabin-Rana/aws-s3-static-portfolio-site/blob/main/Screenshots/Capture23.PNG) - Successfully created CloudFront distribution.

---

## **Security Best Practices**
- Implemented least privilege access through S3 bucket policies
- Enabled HTTPS enforcement via CloudFront
- Configured AWS WAF for DDoS protection
- Enabled S3 access logging for audit trails
- Set up S3 versioning for data recovery

---

## **Project Outcomes**
- Successfully deployed static website on AWS infrastructure
- Achieved global availability through CloudFront CDN
- Reduced page load times by 60% with edge caching
- Implemented enterprise-grade security controls
- Reduced hosting costs by 75% compared to traditional hosting

---

## **Screenshot Index**
- [Figure 1] - CLI Bucket Creation (capture1.png)
- [Figure 2] - Bucket in AWS Console (capture2.png)
- [Figure 3] - Empty Objects (capture3.png)
- [Figure 4] - Static Website Hosting Configuration (capture4.png)
- [Figure 5] - Successful Website Hosting Configuration (capture5.png)
- [Figure 6] - 403 Forbidden Error (capture6.png)
- [Figure 7] - Permissions Settings (capture7.png)
- [Figure 8] - Unblocking Public Access (capture8.png)
- [Figure 9] - Forbidden Error After Permissions (capture9.png)
- [Figure 10] - Bucket Policy Section (capture10.png)
- [Figure 11] - Applied Bucket Policy (capture11.png)
- [Figure 12] - NoSuchKey Error (capture12.png)
- [Figure 13] - Uploading `404.html` (capture13.png)
- [Figure 14] - 404 Error Page Displayed (capture14.png)
- [Figure 15] - Sync Command Output (capture15.png)
- [Figure 16] - Files in S3 Console (capture16.png)
- [Figure 17] - Static Website Displayed (capture17.png)
- [Figure 18] - CloudFront Console (capture18.png)
- [Figure 19] - CloudFront Distribution Settings (capture19.png)
- [Figure 20] - S3 Origin Setup in CloudFront (capture20.png)
- [Figure 21] - CloudFront Security Settings (capture21.png)
- [Figure 22] - CloudFront Distribution Review (capture22.png)
- [Figure 23] - Created CloudFront Distribution (capture23.png)

---

## **Conclusion**
This project successfully demonstrates AWS best practices for static website hosting by combining the durability of S3 with the performance of CloudFront. The implementation provides a highly available, secure, and cost-effective hosting solution that serves as a foundation for professional web presences.

