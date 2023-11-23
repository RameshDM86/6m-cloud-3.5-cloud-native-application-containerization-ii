# 6m-cloud-3.5-cloud-native-application-containerization-ii

## Docker Image Deployment to AWS ECR ## 
This repository demonstrates how to create a Docker image and deploy it to Amazon Elastic Container Registry (ECR).

<div>Prerequisites:</div>

<b>Docker installed locally.</b>

<b>AWS CLI configured with appropriate permissions to access ECR.</b>

<b>Steps:</b>

<b>Clone the Repository:</b>

bash

Copy code

git clone https://github.com/your-username/your-repo.git

cd your-repo

Build the Docker Image:

Create a Dockerfile in your project directory specifying your image configuration.

Build the Docker image locally:

bash

Copy code

docker build -t your-image-name .

Authenticate Docker to ECR:

Run the AWS CLI command to authenticate Docker with your ECR registry:
bash
Copy code
aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com
Create a Repository in ECR:

If not already created, create an ECR repository using AWS Management Console or AWS CLI.
Tag the Docker Image:

Tag your locally built Docker image with the ECR repository URI:
bash
Copy code
docker tag your-image-name:tag your-account-id.dkr.ecr.your-region.amazonaws.com/repository-name:tag
Push the Docker Image to ECR:

Push the Docker image to your ECR repository:
bash
Copy code
docker push your-account-id.dkr.ecr.your-region.amazonaws.com/repository-name:tag
Verify the Image in ECR:

Check the AWS Management Console or use AWS CLI to confirm the successful image push to your ECR repository.
