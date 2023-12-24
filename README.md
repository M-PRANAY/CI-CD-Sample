## CodeBuild

### Building and Pushing Docker Image

**BuildSpec.yaml:**

```yaml
phases:
  install:
    runtime-versions:
      python: 3.11
    # Install dependencies
    pre_build:
      commands:
        - pip install -r requirements.txt
  build:
    commands:
      - cd folder/folder/  # Navigate to the Dockerfile directory
      - docker login -u <username> -p <password>  # Login to Docker registry
      - docker build -t "<username>/<nameofdockerimage>" .  # Build the image
      - docker push <username>/<nameofdockerimage>  # Push the image
  post_build:
    commands:
      - echo "Build Successful"  # Indicate successful completion


```

## CODEDEPLOY


Create EC2 instance with Commands : 
- sudo apt update
- sudo apt install ruby-full
- sudo apt install wget
- wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
- chmod +x ./install
- sudo ./install auto
- sudo service codedeploy-agent status


Create Application in CodeDeploy and then Deployements


Role for EC2:
  Use Case : EC2
  Policies : AmazonEC2RoleforAWSCodeDeploy
              AmazonSSMManagedInstanceCore


Role for CodeDeploy:
  Use Case : CodeDeploy
  Policies : AWSCodeDeployRole

  
