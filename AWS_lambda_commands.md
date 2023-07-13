
## To upload the image to Amazon ECR and create the Lambda function

### Run the get-login-password command to authenticate the Docker CLI to your Amazon ECR registry.  
aws ecr get-login-password --region {us-east-1} | docker login --username AWS --password-stdin {AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com

### Create a repository in Amazon ECR using the create-repository command.
aws ecr create-repository --repository-name {hello-world} --image-scanning-configuration scanOnPush=true --image-tag-mutability MUTABLE

### Run the docker tag command to tag your local image into your Amazon ECR repository as the latest version.
docker tag {my_lambda_app:latest} {AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com/{hello-world:latest}

### Run the docker push command to deploy your local image to the Amazon ECR repository. Make sure to include :latest at the end of the repository URI.
docker push {AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com/{hello-world:latest}

### Create the Lambda function including modify the timeout and maxium memory limitation.
aws lambda create-function --function-name {hello-world} --package-type Image --code ImageUri={AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com/{hello-world:latest} --role arn:aws:iam::{AWS account ID}:role/{lambda-ex} --timeout {100} --memory-size {3008}

#### update the existed function configuration etc., timeout->100
aws lambda update-function-configuration --function-name {hello-world} --timeout {100}
#### update the existed function code etc., modified docker image
aws lambda update-function-code --function-name {hello-world} --image-uri {AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com/{hello-world:latest}


## Test the image locally 

1. Using an AWS base image for Python
docker run -p 9000:8080 {my_lambda_function:latest}

2. Using an alternative base image with the runtime interface client
docker run -d -v C:\Users\Yao\.aws-lambda-rie:/aws-lambda -p 9000:8080 --entrypoint /aws-lambda/aws-lambda-rie {my_lambda_function:latest} /usr/local/bin/python -m awslambdaric lambda_function.handler

### This command invokes the function with an empty event and returns a response.(using PowerShell)
Invoke-RestMethod -Uri "http://localhost:9000/2015-03-31/functions/function/invocations" -Method POST -Body '{}'

aws lambda create-function \
  --function-name {hello-world} \
  --package-type Image \
  --code ImageUri={AWS account ID}.dkr.ecr.{us-east-1}.amazonaws.com/{my_lambda_function:latest} \
  --role arn:aws:iam::{AWS account ID}:role/{lambda-ex}


