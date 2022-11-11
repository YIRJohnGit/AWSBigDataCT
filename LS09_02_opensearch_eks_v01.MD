# Elastic Search / Amazon OpenSearch Service @ LS_09_02_20221105_10:00PM
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
    Click on the < Create Key Pair > button
   In < Network settings > Section
    Network < vpc-01a17e1bfddb0384d >
    Check the tick btton < Allow SSH traffic from >
    Click on < Launch Instance >
```
_Menu Selection for EC2 Instance_
![image](https://user-images.githubusercontent.com/111234771/201269519-1798b6c3-3088-4bbf-b2e5-99de7751fbba.png)

_Creating the Key Pair from Key Pair Login Section_
![image](https://user-images.githubusercontent.com/111234771/201270275-3fde04d8-bd78-4821-ba9c-d9d27ab1137e.png)

_IN The Network Section_
![image](https://user-images.githubusercontent.com/111234771/201272469-3fe59711-10de-45f5-b6d0-0080b0c8f693.png)

### Creating and Connecting IAM Admin Role to EC2 Instances ###
```
  Click on to the EC2 Instance
   Go to < Action > Drop Down Menu, Click on the < Security > Sub Menu, Click on < Modify IAM Role >
    Click on < Create New IAM Role > new Tab Menu
     Click on < Create Role > in the Role Tab
      In IAM > Roles > Create Role, Select Trusted Entity Tab
       Trusted Entity Type < AWS Service >
       Use Case, Click on the Radio button < EC2 >
       Click on the < Next > Button 
        In the < Add Permission > Section
         Search and Select the Policy Name  < AdministratorAccess >
         Click on < Next > Button 
          On the < Role Details > Section
           Role Name < yir-ec2-admin-iam-role >
           Click on < Create Role > Button and Wait for Creating Role
       Come Back previous < Modify the IAM role > tab
       Reload and Select the IAM Role in < Modify IAM role > View
       IAM role < yir-ec2-admin-iam-role >
       Click on < Update IAM Role > 
```
_Selection of Modify IAM Role_
![image](https://user-images.githubusercontent.com/111234771/201274196-a6f71c54-09cd-40b6-b7bd-117781618885.png)

_Create New IAM Role View_
![image](https://user-images.githubusercontent.com/111234771/201274474-e3c32595-94d1-4a8d-9177-30c439832e12.png)

_Add Permission View_
![image](https://user-images.githubusercontent.com/111234771/201275176-c792890d-1c85-4c61-ba2b-1b1c97e57979.png)

_Role Details View_
![image](https://user-images.githubusercontent.com/111234771/201275484-4fab0068-65b3-4646-b75e-b0289b6d7eb3.png)

_In Modify IAM Role_
![image](https://user-images.githubusercontent.com/111234771/201276095-5543c673-f4eb-4b8b-824a-660fda6a9fa8.png)

_Verify on EC2 Instance View_
![image](https://user-images.githubusercontent.com/111234771/201276184-6a46066d-9517-4229-9e4c-fbed562b8f5e.png)

### Connecting to Putty .ppk ###
```
 Go to Putty, Select the Session, Update thte Publich IP Address < 44.201.213.26 > 
```
_Collect the Public IP Address from the EC2 Instance_
![image](https://user-images.githubusercontent.com/111234771/201277193-8be68d3f-dca2-4bde-84eb-aa33f2fe156e.png)

_Putty_
![image](https://user-images.githubusercontent.com/111234771/201277028-d6a439ac-6d0a-4fae-b2c5-765d5c673ead.png)

_Accept the _
![image](https://user-images.githubusercontent.com/111234771/201277486-758fb45d-be85-4481-ad13-0b26421d1f16.png)

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

```
sudo ./aws/install --update
```
### Amazon OpenSearch Service Create Using CLI ###

***Colect the AWS Account ID***
```
951345542826
```

***Create a Open Search using CLI***
```
/usr/local/bin/aws opensearch create-domain --domain-name my-transcribe-test --engine-version OpenSearch_1.0 --cluster-config  InstanceType=t2.medium.search,InstanceCount=1 --ebs-options EBSEnabled=true,VolumeType=standard,VolumeSize=10 --access-policies '{"Version":"2012-10-17","Statement":[{"Effect":"Allow","Principal":{"AWS":"arn:aws:iam::951345542826:root"},"Action":"es:*","Resource":"arn:aws:es:us-west-2:951345542826:domain/my-transcribe-test/*"}]}' --region us-east-1
```

_Create Open Search Using CLI_
![image](https://user-images.githubusercontent.com/111234771/201401829-440c5fa8-e231-4238-b62d-a2807f0bdbd2.png)
![image](https://user-images.githubusercontent.com/111234771/201401987-c54185eb-174e-4217-adb4-f15908ca5d80.png)

![image](https://user-images.githubusercontent.com/111234771/201401930-8d957faa-e677-476d-8c3d-3ab4fef93cba.png)



__Verify Amazon opensearch in AWS Concole__
![image](https://user-images.githubusercontent.com/111234771/201402613-81fb85cf-f54a-4b43-9716-f81889b45fdb.png)

_In Ready Stat (Will take Time 5 to 10 Min based on your net speed)_
![image](https://user-images.githubusercontent.com/111234771/201404451-3591a62f-efa9-4812-a239-b9f1d8bd330f.png)

```
 Get Inside the the Amazon OpenSearch SERVICE >> dOMAIN >> < my-transcribe-test >
  Click on the Link
```
![image](https://user-images.githubusercontent.com/111234771/201408013-4b5a9296-e5cf-4b79-8842-4142ffc94b62.png)

_Resule:- (Anonymous is not authorized)_
![image](https://user-images.githubusercontent.com/111234771/201408313-3078dd89-8960-4ff3-af23-e1a39ead2497.png)

