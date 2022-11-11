# Elastic Search @ LS_09_02_20221105_10:00PM
## Task: Create EC2 Instance and Attach Admin Role to it, then install Client Side POSTManAPI in local machine ##

### Creating Linux EC2 Instance ###
```
 Go to Main Menu > Click on EC2 > Click on the Launch Instances
  In the < Launch an instance > Section
   Name and tags < yir-ec2-instance-putty-connect >
   Application and OS Image < Amazon Linux AWS > ( ami-09d3b3274b6c5d4aa )
   Key pair (login), Click on < Create New Key Pair >
    Key Pair Name < yirec2connet-keypair > 
    Key Pair Type < RSA >
    Private Key File Format < .pem >
```
_Menu Selection for EC2 Instance_
![image](https://user-images.githubusercontent.com/111234771/201269519-1798b6c3-3088-4bbf-b2e5-99de7751fbba.png)

_Creating the Key Pair from Key Pair Login Section_
![image](https://user-images.githubusercontent.com/111234771/201270275-3fde04d8-bd78-4821-ba9c-d9d27ab1137e.png)


__Download Postman from the below link__
```
https://www.postman.com/downloads/
```

__AWS Configuring__
```
aws configure
```

```
aws --version
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/201251801-2f46a427-f3a5-4027-b65a-b9b28fa27e50.png)

_Download the AWS Version 2 file_
```
 curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
 unzip awscliv2.zip
```
![image](https://user-images.githubusercontent.com/111234771/201251853-3b9e3949-ae99-4780-8887-3614e025806f.png)

```
sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin
```
_Follow on screen instruction_
![image](https://user-images.githubusercontent.com/111234771/201252201-d1138f6f-eacb-4ae0-a8ad-dbd4a54f6393.png)


***Colect the AWS Account ID***
```
951345542826
```

***Create a Open Search using CLI***
```
/usr/local/bin/aws opensearch create-domain --domain-name my-transcribe-test --engine-version OpenSearch_1.0 --cluster-config  InstanceType=t2.medium.search,InstanceCount=1 --ebs-options EBSEnabled=true,VolumeType=standard,VolumeSize=10 --access-policies '{"Version":"2012-10-17","Statement":[{"Effect":"Allow","Principal":{"AWS":"arn:aws:iam:: 951345542826:root"},"Action":"es:*","Resource":"arn:aws:es:us-west-2: 951345542826:domain/my-transcribe-test/*"}]}' --region us-east-1
```


__Verify Amazonopensearch in AWS Concole__
