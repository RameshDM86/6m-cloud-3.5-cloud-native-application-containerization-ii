# 6m-cloud-3.5-cloud-native-application-containerization-ii

## Docker Image Deployment to AWS ECR ## 
This repository demonstrates how to create a Docker image and deploy it to Amazon Elastic Container Registry (ECR).

<div>Prerequisites:</div>

**Docker installed locally.**

<b>AWS CLI configured with appropriate permissions to access ECR.</b>

<b>Steps:</b>

Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:

<code> aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com </code>

<b>Clone the Repository:</b>

<b> Insert bash command </b> 

<code> git clone <url>https://github.com/your-username/your-repo.git </url></code>

<b> cd into your-repo </b>

<b> Create a Dockerfile in your project directory specifying your image configuration. </b>

<b> Build the Docker image locally: </b>

<b> Insert bash command </b>

<code> docker build -t ramesh_ecr . </code> 

<b> Authenticate Docker to ECR: </b>

<b> Run the AWS CLI command to authenticate Docker with your ECR registry: </b>

<b> Insert bash command  </b>

<code> aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com </code>

Create a Repository in ECR: 

<b> If not already created, create an ECR repository using AWS Management Console or AWS CLI. </b>

<b> Tag the Docker Image: </b>

<b> Tag your locally built Docker image with the ECR repository URI: </b>

<b> bash command </b>

<code> docker tag ramesh_ecr:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/ramesh_ecr:latest </code>


<b> Push the Docker image to your ECR repository: </b>

<b> Insert bash command </b>

<code> docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/ramesh_ecr:latest  </code>

<b>Verify the Image in AWS ECR:</b>

<b>Check the AWS Management Console or use AWS CLI to confirm the successful image push to your ECR repository.</b>
