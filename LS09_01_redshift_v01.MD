# Redshift Clustering

***Prerequisite***
_Required Download workbench-build127_

```
https://github.com/YIRJohnGit/my_learning_AWSBigDataCertificationTraining/raw/main/Workbench-Build127.zip
```
***Process for Creating RedShift***
```
Go to Redshift; Select Cluster from the Main menu
  In < Cluster Configuration > Session
    Amazon Redshift > Cluster > Create Cluster
    Cluster identifier < redshift-cluster-1 >
    Cluster Plan < Free Trail > 
```

### Step 1 - Creating IAM Role in Another New Tab ###
```
Go to Main Menu, Search on the Menu Called < IAM >
  Click on the < IAM > form the Menu
  Click on Role from the Left Side Menu < Role >
  Click on the Create Role Button from the Right Side Top Corner of the IAM > Roles > Tab
  Next: Moves on to the < Create Role Tab to Change the Entity and the use case  >
```
_Create Role Tab_
![image](https://user-images.githubusercontent.com/111234771/200304014-b25912b0-736a-46cf-94b0-254d919245d5.png)

_Select the Trusted Entity < IAM > Role > Create Role>_
![image](https://user-images.githubusercontent.com/111234771/200304895-7c512acd-a304-4137-910a-aef19907a39a.png)


```
In the < Moves on to the Create Role Tab to Change the Entity and the use case >
  Go to Down to the < Use cases for other AWS services > Session, Search and Select Red
  Click on the < Redshift - Customizable >
  Click on the Button < Next >
  <! Next Move on the < Add Permission >  Tab !>
```
_Search and Select the Redshift_
![image](https://user-images.githubusercontent.com/111234771/200305321-4715076f-cdb4-4000-aaeb-60f061628105.png)

![image](https://user-images.githubusercontent.com/111234771/200305934-d95830d4-929f-4c97-a832-114ba17ea15e.png)

```
  In the < Add Permission >  Tab
    Search and Select < AmazonS3FullAccess >
    Tick the Select the < AmazonS3FullAccess >
    Click on the < Next > Buttn
    <! Next Moves to Name, review and create! > View
```
_Add Permission_
![image](https://user-images.githubusercontent.com/111234771/200306627-85b14eeb-2974-40da-8566-8289d137a24e.png)


```
In the < Name, review and create > View
  In the < Role Details > Session
    Role Name  < yirredshiftIAMrole >
    Scroll Down Click on button < Create Role >
```
_Role Details Session_
![image](https://user-images.githubusercontent.com/111234771/200307641-d18d4fbb-cd89-4c60-b17f-cf1de01f7084.png)

_Create Role View_
![image](https://user-images.githubusercontent.com/111234771/200307824-084250f5-a916-4345-a9b0-31cccda20130.png)



### Step 2 - Creating Redshift in New Tab ###

![image](https://user-images.githubusercontent.com/111234771/200163540-ee9b4b04-0ccc-434e-b83b-d844a5934233.png)
![image](https://user-images.githubusercontent.com/111234771/200163997-466379f8-5004-4614-82fd-db85689ead59.png)
```
 In < Database configurations > Session
    Admin user name < awsuser >
    Admin user password < rootUsr321# >
    Click on the < Create Cluster > Button
```
![image](https://user-images.githubusercontent.com/111234771/200164535-316d9a57-2ab7-4ee2-a0a4-1381312092e1.png)
```
  < In My Account > Session
    Click on the Download Driver Button for < JDBC 4.2 without AWS SDK (.jar) >
```
_Download the JDBC Driver from In My Account_ 
![image](https://user-images.githubusercontent.com/111234771/200164854-16801969-bcdd-40f6-b57f-9fa597fb75b6.png)

```
  In < Cluster > Session
    Click on the Cluster Name < redshift-cluster-1 >
    Move on to < redshift-cluster-1 > tab
```
_Scroll Down to Cluster Session and Click on the Name of Cluster_ 
![image](https://user-images.githubusercontent.com/111234771/200301367-32d7f50a-d743-4012-a505-bfae76305506.png)

![image](https://user-images.githubusercontent.com/111234771/200301567-2b15f8aa-7769-440d-8f36-1dd5326f339f.png)

_Enable Pblically Accessable_
```
  In < redshift-cluster-1 > tab
    Click on the < Actions > dropdown menu and Select < Modify Publicly accessible settings >
    Tick the Checkbox < Turn on Publicly Accessible > 
    Return back to In < redshift-cluster-1 > tab
    Copy the Endpoint of < JDBC:redshift..... > URL 
```
__
![image](https://user-images.githubusercontent.com/111234771/200302060-cdab8711-aac8-4869-8dbe-60d7f8c8970e.png)
![image](https://user-images.githubusercontent.com/111234771/200302440-190b7964-8a68-4147-bb29-41624f2d0b07.png)

__Example: of JDBC__
```
jdbc:redshift://redshift-cluster-1.c9oapnrco4q2.us-east-1.redshift.amazonaws.com:5439/dev
```
_JDBC Copy COntent_
![image](https://user-images.githubusercontent.com/111234771/200303009-3f275d91-3817-43b5-8512-2b8b74c9ce05.png)

***...For Adding IAM Role to the Redshift Cluster (Ensure the redshift cluster is available) and Selected Propoerties Tab***
![image](https://user-images.githubusercontent.com/111234771/200308880-9ba146b3-8774-4241-8577-34cf9112bf15.png)

![image](https://user-images.githubusercontent.com/111234771/200309024-03ecb60c-af11-404b-b3e5-570d6c95b105.png)

```
Scroll Down to < Associated IAM roles >
  Click on the < Assoctae IAM Role utton >
  Tick the < >
```
_IAM Role Attachement_
![image](https://user-images.githubusercontent.com/111234771/200309335-1a69395c-f670-4a92-bc98-50d51607de10.png)

_View attached IAM role to the Cluster_
![image](https://user-images.githubusercontent.com/111234771/200309618-6c50c7b9-e5db-42fa-976e-549ca59bca1f.png)

***...For Adding Security Roles to the Cluster***

```
  Go to the < Network and security settings > Session in the Cluster < redshift-cluster-1 >
    Moves on to < Security Group > View
      Scroll Down and Select Inbound Rules 
        Click on the < Edit Inbound Rules > Button 
        Moves on to the < Edit Inboud Rules > Tab
```
_Network and security settings Session_
![image](https://user-images.githubusercontent.com/111234771/200309950-a7f820c4-1c9c-4a09-b4d1-135405fe91e5.png)

_Security Group View_
![image](https://user-images.githubusercontent.com/111234771/200310378-733fe2c9-b1da-4595-8026-63dcfe762bb0.png)

_Invound Rule View_
![image](https://user-images.githubusercontent.com/111234771/200311221-6ffcf885-4c42-4250-9e21-c943ae186423.png)

```
  In the < Edit inbound Rules Tab >
    Click on the < Add rule >
    Click on the Type and Change it to < Redshift>
    Click on Source and Change it to < Anywhere >
    Click on the < Save Rules > button  
```

_Edit inbound Rules_
![image](https://user-images.githubusercontent.com/111234771/200311699-0dde871c-ca32-4905-b735-8dcd65bc5fa1.png)

_Updated the Security rule_
![image](https://user-images.githubusercontent.com/111234771/200312083-93d02b65-f986-4dde-bcac-e8e98803d938.png)


### Step 3 - Testing the Connection  to SQL Workbech ###
```
  Download Work Bench
  Download the JDBC Jar File
```

***Note:*** _If you dont Have the SQLWorkbench,Download from the below Link_
```
https://github.com/YIRJohnGit/my_learning_AWSBigDataCertificationTraining/raw/main/Workbench-Build127.zip
```
_Download the JDBC_
![image](https://user-images.githubusercontent.com/111234771/200316833-163bcb44-c829-4016-811f-37ebbe98d45c.png)


### Step 4 - Creating S3 Bucket and Uploading the Files ###



