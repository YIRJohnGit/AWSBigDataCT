
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

_Verify EC2 Instance_
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

_Generating User Details for Windows using .PEM File Format_
![image](https://user-images.githubusercontent.com/111234771/201287198-c0c7fa98-702a-4ede-a713-041ea42c3fdd.png)

```
   In < Get Windows Password > Section tab,
    Click on < Browse > Button, Select the File Name with .PEM key (Private Key)
    Click on < Decrypt > Button to get the User Name and Password
    Note Down the Login Credentials for the futhre use
    
    User Name < Administrator >
    Password < 9p5k?u$91%Wg%gx2q50knoj6OA&X!Gdn > 
```
_In Get Windows Password_
![image](https://user-images.githubusercontent.com/111234771/201290243-5581b5c7-3c85-430d-b6d5-d7d84d190afa.png)
![image](https://user-images.githubusercontent.com/111234771/201290548-755d1951-4984-47f8-a069-3a0650473fc2.png)


