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

### Step 1 - Creating Redshift ###

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


### Step 2 - Creating S3 Bucket and Uploading the Files ###

### Step 3 - Connecting to SQL Workbech ###
***Note:*** _If you dont Have the SQL Workbench, refer the prerequist link at the and dwnload the file_

