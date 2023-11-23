## 6m-cloud-3.5-cloud-native-application-containerization-ii

### Docker Image Deployment to AWS ECR 

<b>Prerequisites:Docker installed locally </b>

<b>AWS CLI configured with appropriate permissions to access ECR.</b>

<img width="707" alt="Untitled" src="https://github.com/RameshDM86/6m-cloud-3.5-cloud-native-application-containerization-ii/assets/137069406/17f03905-5e2d-449d-95a0-7e5f4ea66a99">

<b>Steps:</b>

<b>Retrieve an authentication token and authenticate your Docker client to your registry.</b>

<b>Use the command on AWS CLI/Ternimal in visual studio:</b>

<b><code>aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com</code></b>

<b>Clone the Repository with bash command:</b> 

<b><code> git clone <url>https://github.com/RameshDM86/6m-cloud-3.5-cloud-native-application-containerization-ii.git</url></code></b>

<b> cd into your-repo </b>

<b> Create a Dockerfile in your project directory specifying your image configuration. 

<b> Build the Docker image locally: with bash command </b>

<code>docker build -t ramesh_ecr .</code> 

<b> Authenticate Docker to ECR: </b>

<b>Run the AWS CLI command to authenticate Docker with your ECR registry: </b>

<code>aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com</code>

<b>Create a Repository in ECR:</b> 

<b>If not already created, create an ECR repository using AWS Management Console or AWS CLI.</b>

<b>Tag your locally built Docker image with the ECR repository URI:</b>

<code>docker tag ramesh_ecr:latest 255945442255.dkr.ecr.us-east-1.amazonaws.com/ramesh_ecr:latest </code>

<b>Push the Docker image to your ECR repository with following bash command</b>

<code>docker push 255945442255.dkr.ecr.us-east-1.amazonaws.com/ramesh_ecr:latest</code>

<b>Verify the Image in AWS ECR:</b>

<b>Check the AWS Management Console or use AWS CLI to confirm the successful image push to your ECR repository.</b>
