# Redshift Clustering @ LS_09_01_20221105_07:15PM

## Prerequisite ##
_Required Download workbench-build127_

```
https://github.com/YIRJohnGit/my_learning_AWSBigDataCertificationTraining/raw/main/Workbench-Build127.zip
```
### Process for Creating RedShift ###
```
Go to Redshift; Select Cluster from the Main menu
  In < Cluster Configuration > Session
    Amazon Redshift > Cluster > Create Cluster
    Cluster identifier < redshift-cluster-1 >
    Cluster Plan < Free Trail > 
```

### Step 1 - Creating IAM Role in Another New Tab ###
#### Process Creating IAM Role ####
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

#### Process Creating IAM Role ####
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
![image](https://user-images.githubusercontent.com/111234771/201219974-90d76acb-f435-4074-9211-219603b1e620.png)

![image](https://user-images.githubusercontent.com/111234771/201220607-ab594a26-0d49-4685-873c-17446f459ed0.png)

_Enable Publically Accessable_
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
  Download SQLWorkBench and Extract on your local machine
  Download the JDBC Jar File
```

***Note:*** _If you dont Have the SQLWorkbench,Download from the below Link_
```
https://github.com/YIRJohnGit/my_learning_AWSBigDataCertificationTraining/raw/main/Workbench-Build127.zip
```
_Download the JDBC Driver from Redshift Cluster_
![image](https://user-images.githubusercontent.com/111234771/200316833-163bcb44-c829-4016-811f-37ebbe98d45c.png)

***Start SQLWorkbench Based on your system, and i am using 64bit***
_Extracted File Location_
![image](https://user-images.githubusercontent.com/111234771/200317549-4e5fc875-eec0-44bf-9a1d-0563b23fd7e6.png)

***For Configuring the Manager Driver***
```
  Click on File Menu
    Click on Manager Driver
      Click on the Amazon Redshift from the Left Side List Menu
        Name < Amazon Redshift >
        Library <redshift-jdbc42-2.0.0.4.jar>
```
![image](https://user-images.githubusercontent.com/111234771/200317870-9b6d196a-4f94-4d92-9c34-9ee61f087807.png)

![image](https://user-images.githubusercontent.com/111234771/200318121-1d39badf-abb5-4137-ba62-3410a13654ea.png)

_Update the JDBC JAR Library_
![image](https://user-images.githubusercontent.com/111234771/200318515-bd2fbc79-49e6-45a3-ae79-7dff6bd12c53.png)


***For Connecting to the JDBC***
```
Go to File Menu, Select < Connect Window > from the Menu
  Update the Profile Name < yir_redshift_v01 >
  Select the < Drive > from the List < Amazon Redshift (com.amazon.redshift.Driver) > 
  Paste the < URL > < jdbc:redshift://redshift-cluster-1.c9oapnrco4q2.us-east-1.redshift.amazonaws.com:5439/dev >
  Update the Username < awsuser >
  UPdate the Password < ******** >
  Click on < OK > Button 
```
![image](https://user-images.githubusercontent.com/111234771/200318622-dc27d95e-e746-4347-b605-1c40e2bad1d2.png)

_Connected Window_
![image](https://user-images.githubusercontent.com/111234771/200319103-ca9445e0-ae20-4596-bfb0-9e923e69642f.png)


__Once the Connectin Established you will get result on the url bar__

![image](https://user-images.githubusercontent.com/111234771/200322117-2bc2976e-ae76-4024-92fe-cccc04f59104.png)



### Step 4 - Creating S3 Bucket and Uploading the Files ###
***...For Downloading the Data Files from AWS URL***
```
https://docs.aws.amazon.com/redshift/latest/dg/tutorial-loading-data-download-files.html
```
_Sample View Download the Data Files_
![image](https://user-images.githubusercontent.com/111234771/200324206-2dc2d558-b962-4bea-bc07-312ce99d03d7.png)


***...For Creating the S3 Buckets***
```
Go to, Amazon S3 from the AWS Search Console
  Click on < Create Bucket > Button 
  Next Moves to < Create Bucket > Tab 
```

_Search Result for S3 Bucket_
![image](https://user-images.githubusercontent.com/111234771/200325410-04241214-8e50-47ba-8e3a-809531e1e9f8.png)

***In Create Bucket***
```
  In < General Configuration > Session 
    Bucket Name < yirsmbucketredshiftv01 >
    AWS Region < us-east-1 >
    Click on < Create Bucket >
```
![image](https://user-images.githubusercontent.com/111234771/200331363-10de6656-0dc7-445d-8286-725bb592f74b.png)
![image](https://user-images.githubusercontent.com/111234771/200332437-f9c1d6c6-f06d-4046-ae52-aaacacf62d80.png)

***...For Uploading the Files in S3 Bucket***
```
Click on < yirsmbucketredshift> Bucket
  Crate a New Folder in the Bucket Tab < load > and Click on the Create Button
  Click on the load Folder which is created
    Click on Upload Button 
    Click on Add Files <>
      Click on Upload Button to add All the Files
```

![image](https://user-images.githubusercontent.com/111234771/200332747-1fcc727c-26ff-4621-83d1-151de8a45202.png)

_Creating Load Folder_
![image](https://user-images.githubusercontent.com/111234771/200332975-b40b1a9f-e607-46b5-90f8-38d5c3c99c8e.png)

_Get Inside the Load folder Create for Uploading Files_
![image](https://user-images.githubusercontent.com/111234771/200334007-8609cb75-9a0f-4276-88cb-5837cb8f9220.png)

_Add Multiple Files_
![image](https://user-images.githubusercontent.com/111234771/200333263-8e37af84-de7d-4b5c-80a7-4d4ba39e794f.png)
![image](https://user-images.githubusercontent.com/111234771/200333427-f7fb2720-2638-4d38-8773-cfa22fec1368.png)
![image](https://user-images.githubusercontent.com/111234771/200333498-73e0d396-1969-4132-a240-f7e8d87855be.png)

_Verify the Files_
![image](https://user-images.githubusercontent.com/111234771/200333680-4e1f150d-0d03-462e-8c4d-3d5e044e2485.png)



### Step 5 - Creating the Tables in RedShift usin SQLWorkBench ###
***Start the SQLWorkbench follow the Step 3***
***Deleting Tables***
```
drop table IF EXISTS part cascade;
drop table IF EXISTS  supplier;
drop table IF EXISTS  customer;
drop table IF EXISTS  dwdate;
drop table IF EXISTS  lineorder;
```

***Creating Tables***
```
CREATE TABLE part 
(
  p_partkey     INTEGER NOT NULL,
  p_name        VARCHAR(22) NOT NULL,
  p_mfgr        VARCHAR(6),
  p_category    VARCHAR(7) NOT NULL,
  p_brand1      VARCHAR(9) NOT NULL,
  p_color       VARCHAR(11) NOT NULL,
  p_type        VARCHAR(25) NOT NULL,
  p_size        INTEGER NOT NULL,
  p_container   VARCHAR(10) NOT NULL
);
```
_Confirmation Result for Creating Table_
![image](https://user-images.githubusercontent.com/111234771/200336141-0e6d3d7b-f02e-4211-a3b9-eb1cc6285ab0.png)


```
CREATE TABLE supplier 
(
  s_suppkey   INTEGER NOT NULL,
  s_name      VARCHAR(25) NOT NULL,
  s_address   VARCHAR(25) NOT NULL,
  s_city      VARCHAR(10) NOT NULL,
  s_nation    VARCHAR(15) NOT NULL,
  s_region    VARCHAR(12) NOT NULL,
  s_phone     VARCHAR(15) NOT NULL
);
```

```
CREATE TABLE customer 
(
  c_custkey      INTEGER NOT NULL,
  c_name         VARCHAR(25) NOT NULL,
  c_address      VARCHAR(25) NOT NULL,
  c_city         VARCHAR(10) NOT NULL,
  c_nation       VARCHAR(15) NOT NULL,
  c_region       VARCHAR(12) NOT NULL,
  c_phone        VARCHAR(15) NOT NULL,
  c_mktsegment   VARCHAR(10) NOT NULL
);
```

```
CREATE TABLE dwdate 
(
  d_datekey            INTEGER NOT NULL,
  d_date               VARCHAR(19) NOT NULL,
  d_dayofweek          VARCHAR(10) NOT NULL,
  d_month              VARCHAR(10) NOT NULL,
  d_year               INTEGER NOT NULL,
  d_yearmonthnum       INTEGER NOT NULL,
  d_yearmonth          VARCHAR(8) NOT NULL,
  d_daynuminweek       INTEGER NOT NULL,
  d_daynuminmonth      INTEGER NOT NULL,
  d_daynuminyear       INTEGER NOT NULL,
  d_monthnuminyear     INTEGER NOT NULL,
  d_weeknuminyear      INTEGER NOT NULL,
  d_sellingseason      VARCHAR(13) NOT NULL,
  d_lastdayinweekfl    VARCHAR(1) NOT NULL,
  d_lastdayinmonthfl   VARCHAR(1) NOT NULL,
  d_holidayfl          VARCHAR(1) NOT NULL,
  d_weekdayfl          VARCHAR(1) NOT NULL
);
```

```
CREATE TABLE lineorder 
(
  lo_orderkey          INTEGER NOT NULL,
  lo_linenumber        INTEGER NOT NULL,
  lo_custkey           INTEGER NOT NULL,
  lo_partkey           INTEGER NOT NULL,
  lo_suppkey           INTEGER NOT NULL,
  lo_orderdate         INTEGER NOT NULL,
  lo_orderpriority     VARCHAR(15) NOT NULL,
  lo_shippriority      VARCHAR(1) NOT NULL,
  lo_quantity          INTEGER NOT NULL,
  lo_extendedprice     INTEGER NOT NULL,
  lo_ordertotalprice   INTEGER NOT NULL,
  lo_discount          INTEGER NOT NULL,
  lo_revenue           INTEGER NOT NULL,
  lo_supplycost        INTEGER NOT NULL,
  lo_tax               INTEGER NOT NULL,
  lo_commitdate        INTEGER NOT NULL,
  lo_shipmode          VARCHAR(10) NOT NULL
);
```

***To Verify the Table List***
```
  Go to < File > Menu Select  Reconnect, 
  After Successfull reconnect run the below
```
```
SELECT DISTINCT tablename FROM pg_table_def WHERE schemaname = 'public' ORDER BY tablename;
```
_Reconnect_

![image](https://user-images.githubusercontent.com/111234771/200338879-626597e0-549b-44e4-ab71-f5aebf2a4818.png)

_Displays List of all the Tables created _

![image](https://user-images.githubusercontent.com/111234771/200339110-77bec461-d61a-4743-8a59-9902a72696c7.png)

***Copying the casecade table from S3 Bucket to the table***
***Part 1 - Collect the S3 Bucket Name***
![image](https://user-images.githubusercontent.com/111234771/200343366-37e384f5-732c-4d5f-bf8d-fe7fa9f5c614.png)

***Part 2 - Collect the IAM Role's ARN Details***
![image](https://user-images.githubusercontent.com/111234771/200343628-a12c94fa-04ee-400a-95c1-4a1b8a527f67.png)

***Part 3 - Compose the COPY Part from template and replace with credential***
__Note:-__ _Befor going ahead make sure all your files are uploaded in the S3 Bucket_
__Template View__
```
copy part from 's3://<your-bucket-name>/load/part-csv.tbl' credentials 'aws_iam_role=arn:aws:iam::<aws-account-id>:role/<role-name>' csv;
```
__TO__
```
copy part 
  from 's3://yirsmbucketredshiftv01/load/part-csv.tbl' 
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole' 
  csv;
```
_Reconnect and Execute the Above Command in SQLWorkBench_
![image](https://user-images.githubusercontent.com/111234771/200342933-96a039a0-f3cb-48ae-ab9b-fcbe2f8fa95f.png)

***Part 4 - Verify the Records in SQLWorkBench***
```
select * from part limit 10;
```

_List of Part Records_
![image](https://user-images.githubusercontent.com/111234771/201224895-29c9d994-5260-4c38-bf15-000d89981d0f.png)

```
copy supplier from 's3://awssampledb/ssbgz/supplier.tbl' 
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole'
  delimiter '|' 
  gzip
  region 'us-east-1';
```

![image](https://user-images.githubusercontent.com/111234771/201225962-009c3426-c72c-41ec-b8a9-885e623112b8.png)

```
  select * from supplier limit 10 ;
```
![image](https://user-images.githubusercontent.com/111234771/201226082-59b37d95-4368-474d-9b0c-5d13b35bb401.png)


```
copy customer 
  from 's3://yirsmbucketredshiftv01/load/customer-fw.tbl' 
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole'
  fixedwidth 'c_custkey:10, c_name:25, c_address:25, c_city:10, c_nation:15, c_region :12, c_phone:15,c_mktsegment:10'
  maxerror 10;
```

```
select * from customer limit 10;
```

_List of Customer Records_
![image](https://user-images.githubusercontent.com/111234771/201225108-ff48ee96-4098-44b8-9193-72bc1ecb98c6.png)

```
copy dwdate from 's3://yirsmbucketredshiftv01/load/dwdate-tab.tbl'
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole'
  delimiter '\t' 
  dateformat 'auto';
```
![image](https://user-images.githubusercontent.com/111234771/201226524-765c32f7-5550-4116-8116-db6273d41b47.png)

```
select * from dwdate limit 10;
```
![image](https://user-images.githubusercontent.com/111234771/201226584-2d958633-6b83-4134-bf4a-0198ccf438d6.png)

***Loading Single File***
```
copy lineorder from 's3://awssampledb/load/lo/lineorder-single.tbl' 
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole'
  gzip
  compupdate off
  region 'us-east-1';
```
***Loading Multiple Files***
```
copy lineorder from 's3://awssampledb/load/lo/lineorder-multi.tbl' 
  credentials 'aws_iam_role=arn:aws:iam::951345542826:role/yirredshiftIAMrole'
  gzip
  compupdate off
  region 'us-east-1';
```
![image](https://user-images.githubusercontent.com/111234771/201227187-c60a8658-f432-456b-be70-e7b1abac92a6.png)

### Cleaning Up ###
```
drop table part;
drop table supplier;
drop table customer;
drop table dwdate;
drop table lineorder;
```
