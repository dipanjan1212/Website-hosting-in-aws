# Hosting a Static Website on AWS using S3, CloudFront, ACM, and Route 53

This guide will walk you through the steps to host a static website on AWS using Amazon S3 for storage, Amazon CloudFront for content delivery, AWS Certificate Manager (ACM) for SSL/TLS certificates, and Route 53 for DNS management.

## Prerequisites
- AWS Account
- Domain Name (optional, but recommended for custom domains)

## Steps

### 1. Upload Your Website to Amazon S3
- Create an S3 bucket and upload your static website files to the bucket.
- Make sure to enable public read access to your S3 bucket and its objects.

### 2. Configure Amazon CloudFront
- Create a new CloudFront distribution.
- Set the origin domain name to your S3 bucket endpoint (e.g., `your-bucket-name.s3.amazonaws.com`).
- Configure behaviors and settings as needed (e.g., SSL/TLS settings, caching behavior).

### 3. Request an SSL/TLS Certificate from ACM
- Open ACM in the AWS Management Console.
- Request a new certificate for your domain (e.g., `www.yourdomain.com`).

### 4. Configure Route 53
- In Route 53, create a new hosted zone for your domain if one doesn't exist.
- Add an A record alias to point to your CloudFront distribution.

### 5. Set Up DNS for Your Domain
- Update your domain's DNS settings at your domain registrar to use the Route 53 name servers.
- Ensure your domain is properly configured to point to your CloudFront distribution.

### 6. Test Your Website
- Once DNS changes propagate (which can take some time), test your website using your domain name (e.g., `https://www.yourdomain.com`).

### Additional Considerations
- **Security:** Ensure proper bucket policies and CloudFront settings to secure your content.
- **Performance:** Optimize CloudFront caching and distribution settings for better performance.
- **Monitoring:** Set up CloudFront logging and monitoring to track usage and performance metrics.

## Resources
- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
- [Amazon CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [AWS Certificate Manager Documentation](https://docs.aws.amazon.com/acm/)
- [Route 53 Documentation](https://docs.aws.amazon.com/route53/)
