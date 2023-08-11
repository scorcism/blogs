
# User and Group Management

## Create new user

**Linux daddy will guide you.**
```bash
sudo adduser username
```

![](https://imgur.com/gZne10y.png)

**You are now a daddy**
```bash
sudo useradd username
```
![useradd](https://imgur.com/ioR8VpY.png)

### Check all the users
```bash
sudo cat /etc/shadow
```
![etc shadow](https://imgur.com/aFD71Fi.png)

Consider,
 `abhishek2:!:19579:0:99999:7:::`
 
 The row is split into **9 fields** seperate by `:`
 
 Each field resembles as:
 1. **Username.**  User account and login name that exist in the system.
2.  **Encrypted password.**  Password using the format  _$type$salt$hashed_ and eight to 12 characters long.
3.  **Last password change.**  Date since Jan. 1, 1970, when the password was last changed.
4.  **Minimum password age.**  The minimum number of days that must elapse before the password can be changed by the user.
5.  **Maximum password age.** The number of days after which the password must be changed.
6.  **Warning period.**  The number of days before the password expires, during which time the user gets a warning to  [change the password](https://www.techtarget.com/searchsecurity/answer/Minimum-password-length-best-practices-Are-14-character-passwords-necessary).
7.  **Inactivity period.**  The number of days post-expiration -- since Jan. 1, 1970 -- before the user's account is disabled.
8.  **Expiration date.**  The date on which the account was disabled.
9.  **Unused.**  This field is left empty and reserved for future use
		 - [ref](https://www.techtarget.com/searchsecurity/definition/shadow-password-file)	
 ### User with custom shell
```bash
sudo useradd -s /bin/bash abhishek
```
- `/bin/bash` -> env shell 

### User with own home directory
```bash
sudo useradd -m -d /home/abhishek abhishek
```
- /home/abhishek4 -> this can be any path

### User with comment
```bash
sudo useradd -c "user name is abhishek" abhishek
```
### User with the account expiery date
```bash
useradd -e 2023-08-32 apple
```
- -e -> The date on which the user account will be disabled. The date is specified in the format _YYYY-MM-DD_.

### User with custom userId
```bash
sudo useradd -u 1822 abhishek
```

### Change default home directory of user geet
```bash
usermod -d /var/tmp/user/geet -m geet
```
### Change login name of user geet
```bash
sudo usermod -i geet GEET 
```
###  Change default shell of user geet
```bash
usermod -s /bin/fish geet
```
### Set user password
```bash
sudo passwd username
```
![add user passswd](https://imgur.com/ColJOJc.png)

### Switch user
```bash
su username
```
![](https://imgur.com/aMIUwnr.png)

###  add new group with own home directory with custom user id and group and custom comment to user geet, with login shell bash
```bash
useradd -m -d /home/geet -u 1029 -g 1822 -c "geet user" -s /bin/bash geet
```
## Create new group

### Create a new group

**Linux daddy will guide you**
```bash
sudo addgroup groupName
```
![addgroup](https://imgur.com/iFp0mSy.png)

**You are now daddy**
```bash
sudo groupadd grp1
```
![create new group](https://imgur.com/7fNs886.png)

### Create group with custom ID
```bash
sudo groupadd -g 2218 groupName
```
### Add user to group
```bash
# sudo usermod --append --groups demo user1
sudo usermod -aG groupname userName
```
![usermod](https://imgur.com/9CgUIbV.png)

### Display details about group
```bash
sudo cat /etc/gshadow
```

### Change primary group of geet to ak
```bash
sudo usermod -g ak geet
```
###  Add geet as a menber of group jeet
```bash
sudo gpasswd -M geet jeet
```
### Remove user geet from group jeet
```bash
sudo gpasswd -d geet jeet
``` 
### Make geet admin of group jeet
```bash
sudo gpasswod -A geet jeet
```

###  Set password for group jeet
```bash
sudo gpasswd jeet
```
--- 
### Delete user and group

#### Delete user
```bash
sudo userdel geet
```
#### Delelet user with all files
```bash
sudo userdel -r geet
```

#### Delete Group
```bash
sudo groupdel jeet
```

---
If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/) and [GitHub](https://github.com/scorcism).
