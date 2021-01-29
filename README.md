# AWS-CodeDeploy-Proj
Automated deployment of simple webpage project using CodeDeploy

## Description
Through bash commands and [appspec.yaml](https://github.com/mchadds/AWS-CodeDeploy-Proj/blob/main/appspec.yaml) automated deployment of a simple webpage project was achieved

## Deplyment Instructions
Detailed deployment template found in [appspec.yaml](https://github.com/mchadds/AWS-CodeDeploy-Proj/blob/main/appspec.yaml): 
```yaml
version: 0.0
os: linux
files:
  - source: /
    destination: /revision
permissions:
  - object: /var/www
    owner: ec2-user
    group: ec2-user
hooks: 
  AfterInstall:
    - location: update_app.sh
      timeout: 6
      runas: ec2-user
  ApplicationStart: 
    - location: restart_app.sh
      timeout: 6
      runas: ec2-user
```

## Tools
- [Cloud9](https://aws.amazon.com/cloud9/) Cloud IDE
- [CodeDeploy](https://aws.amazon.com/codedeploy/) Automated code deployments
- [EC2](https://aws.amazon.com/ec2/?ec2-whats-new.sort-by=item.additionalFields.postDateTime&ec2-whats-new.sort-order=desc) Secure and resizable compute capacity
- [S3](https://aws.amazon.com/s3/) Cloud storage



