# VSFTPD
To Install vsftpd
 ```sh
 $ yum install vsftpd
 $ yum install ftp 
 ```
 To Configure vsftp
 ```sh
 $ vi /etc/vsftpd/vsftpd.conf
 ```
 and edit the following changes
 
 ```sh
 anonymous_enable=YES
 local_enable=YES
 ```
 and in the end of the file check the following is present
 
 ```sh
listen_ipv6=YES
pam_service_name=vsftpd
userlist_enable=YES
tcp_wrappers=YES


dirlist_enable=YES
download_enable=YES
write_enable=YES
pasv_promiscuous=YES

 ```
 Now Save the file. 
 Now change the SELinux Config. to do this, just execute the following command
 ```sh
 setenforce 1
 ```
 And check for the following  
 ```sh
 $ getsebool -a |grep ftp
 ```
 if ftpd_full_access = off then
 ```sh
 $ setsebool -P ftpd_full_access on
 ```
 Now restart the vsftpd 
 ```sh
 $ systemctl restart vsftpd
 ```
 --------------
 In the client machine install ftp
```sh
$ yum install ftp
```
---------------
For Reference


Installations [digitalocean](https://www.digitalocean.com/community/tutorials/how-to-set-up-vsftpd-on-centos-6--2)


Forum [Linux_forum](https://www.linuxquestions.org/questions/linux-newbie-8/vsftpd-problem-with-425-security-bad-ip-connecting-120158/), [Linux_forum](https://serverfault.com/questions/300782/ftp-not-showing-files-or-directories)

 
