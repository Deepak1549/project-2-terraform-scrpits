# RevHire Frontend Deployment using Terraform (AWS S3 Static Hosting)

## Project Overview

This project is part of the RevHire application, a web-based platform designed to connect job seekers with employers.

In this project, our team implemented cloud-based deployment for the frontend using AWS S3 static website hosting, fully automated with Terraform Infrastructure as Code (IaC).

---

## Team Structure

This project was developed by a team of 4 members, where each member contributed to different components of the system:

* Frontend Development
* Backend Development
* Database Management
* Cloud Deployment (My Role)

### My Contribution

I was responsible for:

* Designing and implementing static website hosting using AWS S3
* Writing Terraform code to automate infrastructure setup
* Configuring:

  * S3 bucket creation
  * Public access policies
  * Website hosting configuration
  * Automated file upload using AWS CLI

---

## Architecture

The frontend application is deployed using:

* AWS S3 → Static website hosting
* Terraform → Infrastructure automation
* AWS CLI → File synchronization

Flow:

```
User → S3 Static Website → Frontend Application
```

---

## Technologies Used

* AWS S3
* Terraform
* AWS CLI
* HTML / CSS / JavaScript (Frontend build)

---

## Terraform Configuration Details

### 1. Provider Configuration

* AWS provider configured for region: `us-east-1`

### 2. S3 Bucket Creation

* Bucket name: `revhire-frontend-application-using-terraform-s3`
* Used for hosting frontend files

### 3. Ownership & Access Control

* Bucket ownership set to `BucketOwnerPreferred`
* Public access block disabled to allow website hosting

### 4. Bucket Policy

* Allows public read access:

  * `s3:GetObject` permission for all users

### 5. Static Website Hosting

* Configured with:

  * `index.html` as entry point

### 6. Automated Deployment

* Used `null_resource` with `local-exec`:

```bash
aws s3 sync ./dist s3://<bucket-name>
```

* Automatically uploads frontend build files to S3

---

## Deployment Steps

### Step 1: Initialize Terraform

```bash
terraform init
```

### Step 2: Plan the Infrastructure

```bash
terraform plan
```

### Step 3: Apply the Configuration

```bash
terraform apply
```

### Step 4: Upload Frontend Files

* Ensure your build files are inside the `dist/` folder
* Terraform will automatically sync files to S3

---

## Accessing the Application

After deployment, access the application using:

```
http://<bucket-name>.s3-website-us-east-1.amazonaws.com
```

---

## Important Notes

* Ensure AWS CLI is configured:

```bash
aws configure
```

* The bucket is publicly accessible for hosting purposes
* This setup is suitable for:

  * Static frontend applications
  * Demo and project deployments

---

## Future Enhancements

* Integrate CloudFront (CDN) for faster delivery
* Add HTTPS using ACM and CloudFront
* Use CI/CD pipeline (Jenkins or GitHub Actions)
* Enable versioning and lifecycle policies

---

## Key Learning Outcomes

* Hands-on experience with Terraform IaC
* Understanding of AWS S3 static hosting
* Automating deployments using AWS CLI and Terraform
* Working in a team-based cloud project environment

---

## Contact

For any queries regarding this project:

* Name: Deepak Pali
* Role: Cloud / DevOps Engineer (Deployment)
* Email:

---

This project demonstrates practical implementa
