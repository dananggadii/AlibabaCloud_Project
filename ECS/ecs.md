# ECS Fundamental

### 1. Create VPC

- Search VPC, click VPCs on left panel > click create vpc

![alt text](image/image-10.png)

- Make sure your region, type vpc name

![alt text](image/image-11.png)

- Select default or custom IPv4 CIDR for VPC

![alt text](image/image-12.png)

- Select resource group

![alt text](image/image-13.png)

- Type vSwitch name & select zone > Type IPv4 CIDR > Click add to another vSwitch

![alt text](image/image-14.png)

- Type another vSwitch name & select zone > Type IPv4 CIDR > Click add to another vSwitch

![alt text](image/image-15.png)

- Click create

### 2. Create EIP

- Search VPC, click Elastic IP Address on left panel > click create

![alt text](image/image-17.png)

- Select billing method

![alt text](image/image-18.png)

- Select region > Select network traffic (by traffic / by bandwidth) > Type name

![alt text](image/image-19.png)

- Click buy now

### 3. Create ECS

- Search ECS, and click elastic computing

![alt text](image/image.png)

- Click Instances on left panel

![alt text](image/image-1.png)

- Make sure your region, and click create instance

![alt text](image/image-2.png)

- Select billing method

![alt text](image/image-3.png)

- Select region and zone

![alt text](image/image-4.png)

- Select instance type family

![alt text](image/image-5.png)

- Select Image > Select OS & version

![alt text](image/image-6.png)

- Select system disk > Type size disk

![alt text](image/image-7.png)

- Set default backup period or create new backup schedule > Select data source

![alt text](image/image-8.png)

- Click Next

- On network type, select VPC & vSwitch (subnet)

![alt text](image/image-9.png)

- Uncheck if you have an EIP

![alt text](image/image-16.png)

- If you need to custom security group, click create a security group

![alt text](image/image-20.png)

- Search ECS, scroll down to find security groups on left panel

![alt text](image/image-21.png)

- Click create security group

![alt text](image/image-22.png)

- Type security group name

![alt text](image/image-23.png)

- Type description > Select security group type > Select VPC for network type > Choose VPC name > Select resource group > Cek inbound rules > click OK

![alt text](image/image-24.png)

- Select Security group name

![alt text](image/image-25.png)

- Set default configurations > Click next

![alt text](image/image-26.png)

- Select logon credential (recommendation : password) > Set logon password > confirm password

![alt text](image/image-27.png)

- Type instance name > Type hostname

![alt text](image/image-28.png)

- Set default configurations > Click next

![alt text](image/image-29.png)

- Select resource group > Set default configurations > Click next

![alt text](image/image-30.png)

- Create instance

### 4. Bind EIP to Instance

- click EIP name > Click `Bind Resource` button

![alt text](image/image-31.png)

- Select instance type

![alt text](image/image-32.png)

- Choose instance & click OK

![alt text](image/image-33.png)

### 5. SSh Remote Instance

- Open terminal > Type `ssh root@[EIP/public IP instance]` > Type password

![alt text](image/image-34.png)

### 6. Add Another Inbound rules

- Search ECS, scroll down to find security groups on left panel
- Click security group name
- Click Add security group rule

![alt text](image/image-35.png)

- Select `Rule Direction`
- Select `Action`
- Select `Protocol Type`
- Select `Port Range & Priority`
- Select `Authorization Object` & Click OK

![alt text](image/image-36.png)

### 7. Create Snapshot ECS

- Search ECS, and click elastic computing
- Select ECS name > Select disks on left panel > Click create snapshot

![alt text](image/image-37.png)

- Type name and click create

![alt text](image/image-38.png)

### 8. Create AMI from Snapshot

- Search ECS, and click elastic computing
- Select ECS name > Select snapshot on left panel > Click create custom image/image

![alt text](image/image-39.png)

- Type custom image/image name & custom image/image description > Select resource group
- Click create

![alt text](image/image-40.png)

- When you create new instance > On image/image, select custom image/image > select AMI

![alt text](image/image-41.png)
