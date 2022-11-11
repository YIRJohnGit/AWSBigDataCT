
# Creating EC2 Instances @ LS_02_02_20221002_09:45PM


### Process for Creating Windows Instance ###
```
  Go to Main Menus, Sear and Select Launch Instance, 
    In Launch an Instance Tab
      In < Name and Tags > Section, Name < WindowsServer >,Then
      Select < Windows > from the < Quick Start Session > 
      Select Different type of Insnace < Windows Server 2022 >
      Instance Type < t2.micro > free Tier
      
      In the < Key Pair (login) > Section
        Click on the Key Pair Name < ec2keyFreshPair >
        Click on the Private Key File Format < .pem > (Windows Need .PEM File Format)
        Click on < Create Key Pair >
      
      Retain Rest Same Default Setting
    Click on < Launch Instance >
```

```
  In the EC2 Instance
    Select the EC2 Instance < WindowsServer > , 
      Click on < Actions > Menu, 
      Click on < Security > Submenu,
      Click on Get < Windows Password... >,
      Moved on to < Get Windows Password > Section tab
```

```
   In < Get Windows Password > Section tab,
    Click on < Browse > Button, Select the File Name with .PEM key (Private Key)
    Click on < Decrypt > Button to get the User Name and Password
    Note Down the Login Credentials for the futhre use
```

