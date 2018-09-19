# Yum Repo Local (Client Server)

Step 1: Install vsftpd and ftp on server machine (Refer My Github for Installation)

Step 2: change the following

```sh
anonymous_enable=YES
local_enable=YES
anon_upload_enable=YES
anon_mkdir_write_enable=YES

chown_uploads=YES
chown_username=daemon
```


step 3:
- Move to /etc/yum.repo.d/
- Backup all repo file
- create a new repo file
```sh
[localrepo]
name=Local Repository
baseurl=ftp://34.221.201.9/pub
enabled=1
gpgcheck=0
```

step 5:
 - install createrepo
 ```sh
 $ yum install createrepo
 ```
 - move to /vaw/ftp/pub
 - create a repo directory 'local_repo'
 - Execute the command to make the directory as yum repo dir
 ```sh
 $ createrepo local_repo
 ```
 step 5: Execute the following command
 ```sh
 $ yum clean all
 $ yum list all
 ```
 -----------
 
 # On client Machine
 
 Step 1: Install ftp
 
 Perform the step 3 as explained above and step 5 to check and validate
 
