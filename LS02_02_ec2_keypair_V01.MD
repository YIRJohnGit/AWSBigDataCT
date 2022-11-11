
# Creating EC2 Instances @ LS_02_02_20221002_09:45PM


### Process for Creating Windows Instance ###
```
  Go to Main Menus, Sear and Select < Launch Instance >, 
    In Launch an Instance Tab
      In < Name and Tags > Section, Name < WindowsServer >,Then
      Select < Windows > from the < Quick Start Session > 
      Select Different type of Insnace < Windows Server 2022 >
      Instance Type < t2.micro > free Tier
```
_Launch Instance Section_
![image](https://user-images.githubusercontent.com/111234771/201285861-6e9363f4-5ee4-40bc-b9a1-59b3e52ade43.png)

_Quick Start Section_
![image](https://user-images.githubusercontent.com/111234771/201286270-b8b4aed5-c6cd-40b5-961c-415470c36cbb.png)

```
      In the < Key Pair (login) > Section
        Click on the Key Pair Name < ec2keyFreshPair >
        Click on the Private Key File Format < .pem > (Windows Need .PEM File Format)
        Click on < Create Key Pair >
      
      Retain Rest Same Default Setting
    Click on < Launch Instance >
```
_Create Key Pair Section_
![image](https://user-images.githubusercontent.com/111234771/201286421-68c5a07f-464e-4a1e-b772-523dc962e8b1.png)

_Launch Summary Section_
![image](https://user-images.githubusercontent.com/111234771/201286960-474f067d-0856-4abb-87f7-b32ae930be70.png)

_Verify EC2 Instance and Collect_
```
Public IPv4 address < 44.202.81.240 >
Public IPv4 DNS < ec2-44-202-81-240.compute-1.amazonaws.com >
```
![image](https://user-images.githubusercontent.com/111234771/201289310-7077da0e-c399-41ae-a834-6549a07715c5.png)


```
  In the EC2 Instance
    Select the EC2 Instance < WindowsServer > , 
      Click on < Actions > Menu, 
      Click on < Security > Submenu,
      Click on Get < Windows Password... >,
      Moved on to < Get Windows Password > Section tab
```
***Note:- Wait for the Status Check to < 2/2 checks passed >***

### Setting up for Remote Windows Connections ###
_Generating User Details for Windows using .PEM File Format_
![image](https://user-images.githubusercontent.com/111234771/201287198-c0c7fa98-702a-4ede-a713-041ea42c3fdd.png)

```
   In < Get Windows Password > Section tab,
    Click on < Browse > Button, Select the File Name with .PEM key (Private Key)
    Click on < Decrypt > Button to get the User Name and Password
    Note Down the Login Credentials for the futhre use
    
    User Name < Administrator >
    Password < 9p5k?u$91%Wg%gx2q50knoj6OA&X!Gdn > 
    Click on Ok button to return to <Instance Dashboard View >
```
_In Get Windows Password_
![image](https://user-images.githubusercontent.com/111234771/201290243-5581b5c7-3c85-430d-b6d5-d7d84d190afa.png)
![image](https://user-images.githubusercontent.com/111234771/201290548-755d1951-4984-47f8-a069-3a0650473fc2.png)

### Connecting to Remote ###
```
  Go to Windows  < Remote Desktop Connection >
```
_Remote Desktopn Connection View_
![image](https://user-images.githubusercontent.com/111234771/201292304-9775f4ad-71b9-478f-b039-bdad72fa6dfa.png)

_Login with User Credential_
![image](https://user-images.githubusercontent.com/111234771/201292478-24602684-2940-4926-b73b-df6ebebc3ee5.png)


### Connecting to Linux Machine using Putty from .pem file ###
```
  Go To < Launch an instance > View
    In the Name and Tags Section < linuxServer >
    In Quick Start < Amazon Linux >
    Select the KeyPair < ec2keyFeshPair >
    Click on < Launch Instance >
```

_Launch an Instance Section_
![image](https://user-images.githubusercontent.com/111234771/201302591-dfd6efc3-e098-4b71-bb65-a0a6cdbb57f2.png)


_Quick Start_
![image](https://user-images.githubusercontent.com/111234771/201302639-38f21346-5bf1-4e4a-8ef4-da6b3d76beec.png)

_Key Pair Section_
![image](https://user-images.githubusercontent.com/111234771/201302718-fe2c7731-9357-4a67-ae02-1d5b007dba47.png)

_Launch Summary View_
![image](https://user-images.githubusercontent.com/111234771/201302797-f0965ba6-5238-499d-ba79-aacd6b66d417.png)

### Converting .pem File to .ppk for Linux Connection ###

#### Converting .pem to PPK using PuTTYKeyGen ####
```
  Go to Putty Gen
    Click on load Button
      Select the .pem File
      Click ON < Save Private Key > button
      Provide the file name < ec2keyFeshPair >
      Close the puTTYGen Dialog Window
```

_.pem File Select Views_
![image](https://user-images.githubusercontent.com/111234771/201305126-ab109759-7537-432d-8735-3da3d424699a.png)

_Save the file to .ppk_
![image](https://user-images.githubusercontent.com/111234771/201305835-3491e885-c83f-4991-9a20-15d6acc0cf47.png)

#### Connting using PuTTy ####
```
  Go to Instance and Collect Public IPV4 Address < 3.88.34.177 >
  
  Select PuTTy
    Go to < Session > Tree Structure , Select Host Name (IP Address)  < 3.88.34.177 >
    Go to < Connection >> SSH >> Auth >> Credentials >> Select Browse Button >
    Select The .PPK File and Click < Open >
    
```

_Linux Instance View_
![image](https://user-images.githubusercontent.com/111234771/201306292-beaba701-29f8-480f-b147-fa4d411e0760.png)

_Putty Windows_
![image](https://user-images.githubusercontent.com/111234771/201307725-614455ab-44bb-4723-964f-6559c6e31dfe.png)

