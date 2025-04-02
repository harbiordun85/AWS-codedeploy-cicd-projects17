
# Installing the CodeDeploy agent on EC2
```
sudo yum update -y
sudo yum install -y ruby wget
wget https://aws-codedeploy-eu-west-1.s3.eu-west-1.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
sudo service codedeploy-agent status
```


# create a bucket and enable versioning
```
aws s3 mb s3://aws-devops-course-sameer-new --region us-east-1
aws s3api put-bucket-versioning --bucket demo-bucket-30-jan  --versioning-configuration Status=Enabled --region us-east-1 
```

# deploy the files into S3
```
aws deploy push --application-name demo-deploy-30-jan --s3-location s3://demo-bucket-30-jan/codedeploy-demo/app.zip --ignore-hidden-files --region us-east-1 



Buildspec.yml```

artifacts:
  files:
    - '**/*'