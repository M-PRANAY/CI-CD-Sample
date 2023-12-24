Create EC2 instance with Commands : 
- sudo apt update
- sudo apt install ruby-full
- sudo apt install wget
- wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
- chmod +x ./install
- sudo ./install auto
- sudo service codedeploy-agent status



Role for EC2:
  Use Case : EC2
  Policies : AmazonEC2RoleforAWSCodeDeploy
              AmazonSSMManagedInstanceCore


Role for CodeDeploy:
  Use Case : CodeDeploy
  Policies : AWSCodeDeployRole

  
