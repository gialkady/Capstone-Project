
## Cloud Deployment 

- Open AWS console -> lambda -> container image
- Publish container image in Amason ECR (Elastic Container Registry):
    - pip install awscli
    - create repistory in Amason ECR
    - Push Docker image to repo in AWS 
- Create function for container image in AWS
- Test model in AWS repo
- Expose the lambda function via API Gateway
- Finally, you will have a public endpoint url through which the model can be tested.
