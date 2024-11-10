---
title: "AWS S3 conditional writes"
published: true
---

**Amazon S3** now supports conditional writes

## Introduction

Posted on: Aug 20, 2024

Amazon S3 adds support for conditional writes that can check for the existence of an object before creating it. This capability ... More on:

Link to AWS post: [Click here](https://aws.amazon.com/about-aws/whats-new/2024/08/amazon-s3-conditional-writes/)
Link to AWS doc: [Click here](https://docs.aws.amazon.com/AmazonS3/latest/userguide/conditional-requests.html)

---

### Example Usage

- How to prevent object overwrites with conditional writes
- The following S3 APIs support using conditional writes:

1. PutObject

```
aws s3api put-object --bucket amzn-s3-demo-bucket --key dir-1/my_images.tar.bz2 --body my_images.tar.bz2 --if-none-match "*"    
```

2. CompleteMultipartUpload

```
aws s3api complete-multipart-upload --multipart-upload file://mpustruct --bucket amzn-s3-demo-bucket --key dir-1/my_images.tar.bz2 --upload-id uploadID --if-none-match "*"      
```
