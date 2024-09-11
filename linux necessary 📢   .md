# **Linux commands** 

* Command1;command2  
* Date   
* Passwd  
* Cat file1 file2  
* Head /etc/passwd  
* Tail /etc/passwd   
* du \-sh /apps/services/\*/\*/nohup.out\* | grep G (to delete nohup files)  
* hostname \-I | awk '{print $1}' (to find your ip )  
* Wc /etc/passwd (count line,words, characters )  
  * Wc \-l /etc/passwd ; wc \-l /etc/group

* File-system 	

* tree \-p /xyz (list file with their permissions)  
  * tree \-fpughD 

* cd  
  * . (current directory)  
  * ..(parent directory)  
  * cd \- (previous directory )

Chsh –shell /bin/bash *username*

* Cp present destination (copy)  
* Cp \-r pres des (copy directory and it content)  
* Mv existingname newname (change name)  
* Mv pres des (move files)  
  * Mv \*txt /dest  
  * Mv the\* /dest  
* Rm file (remove file )  
* Rm \-r directory (remove directory containing files )  
* Rm \-f file (forcefully remove file)  
* Rm \-rf directory (forcefully remove directory containing files)

	

* Ls \-l (for file)(to view owner of a file)  
* Ls \-ld (for directory) (to view owner of directory)   
* Lsblk  
  * lsblk \-Tpl  
* Df \-th (Show information about the file system)  
* Du \-sh (to check the disk usage of a specific directory and its contents)  
* Ln \-s from dest (soft link)  
    
* Command substitution allows the output of a command to replace the command itself on the command line  
    
* The $(command) form can nest multiple command expansions  
* inside each other.  
  * echo Today is $(date \+%A)  
  * echo ${USERNAME}

* Id username(information about currently logged user )  
* Top


  * PID: Shows task’s unique process id.  
  * PR: The process’s priority. The lower the number, the higher the priority.  
  * VIRT: Total virtual memory used by the task.  
  * USER: User name of owner of task.  
  * %CPU: Represents the CPU usage.  
  * TIME+: CPU Time, the same as ‘TIME’, but reflecting more granularity through hundredths of a second.  
  * SHR: Represents the Shared Memory size (kb) used by a task.  
  * NI: Represents a Nice Value of task. A Negative nice value implies higher priority, and positive Nice value means lower priority.  
  * %MEM: Shows the Memory usage of task.  
  * RES: How much physical RAM the process is using, measured in kilobytes.  
  * COMMAND: The name of the command that started the process.  
      
* Ps (only show current shell process)  
* cat /etc/os-release (check os version )  
  * Ps \-au 


* Useradd uname  
* Usermod  
  * Usermod \-g gname uname (change a user's primary group.)  
  * Usermod \-aG gname uname (add a user to a supplementary group)  
* Userdel uname  
* Yum install pwgen  
  * Pwgen \-c 15   
  * Pwgen \-c 25  
  * Pwgen \-s 15


* Tail /etc/passwd (users list )  
* Tail /etc/groups (group list )  
* cron log check  tail \-10 /var/log/cron  
    
* Groupadd gname   
  * Groupadd \-g *gid* gname  
* Groupmod  
  * Groupmod \-n newname oldname  
* Groupdel gname 

* Chmod *ugx+-=rwx*  file | directory  
* chmod u+rwx \[file\_name\]  
* Chown  
  * Chown username file(change owner of file)  
  * Chown \-R username dir (change owner of directory)  
  * Chown user:group file|dir   
  


* Kill  
  * kill \-9 PID (This option sends a signal that forces the process to terminate immediately)  
  * kill \-15 PID ()


* systemctl list-units \--type=service(list only the service units with active activation states.)  
* systemctl list-units \--type=service \--all (all service units regardless of the  
  activation states)  
* systemctl list-unit-files \--type=service (xcelTo see the state of all unit ﬁles installed)  
* ssh uname@ip/host

* Public keys are stored in the /etc/ssh/ssh\_known\_hosts  
* Each remote SSH server that you connect to stores its public key in the 

/etc/ssh directory in ﬁles with the extension .pub.

ssh-keygen (to create private key)

* your private and public keys are saved in your  \~/.ssh/id\_rsa  
* ssh-copy-id  \-i  .ssh/key-with-pass.pub user@remotehost

* Netstat \-tulpn (use sockets as end points for communication and are made up of an IP address, protocol, and port number. Services typically listen on standard ports)  
* nmcli (utility is used to create and edit connection ﬁles from the command line)  
  * Nmcli dev status (displays the status of all network devices)  
  * Nmcli con show (show all connections )  
  * Nmcli con show –active  
* Unzip  
* Node location (ln \-s /root/.nvm/versions/node/vxx/bin/node /usr/bin/node)  
* Rsync  
  * rsync \-av /var/log remotehost:/tmp  
  * (example)rsync \-avzP /apps/code/common/service-ifp-msme vijay.chauhan@10.80.5.95:/apps/code/common/service-ifp-msme

* Scp \-i key file user@ip/host:dest  
  * scp \-i PSB\_DEV\_APP.pem /root/app/services/sewa/sewa.zip ec2-user@10.60.6.253:/home/ec2-user/   (ec2-ec2)  
* Locate (ﬁnds ﬁles based on the name or path to the ﬁle)  
* Find (locates ﬁles by performing a real-time search in the ﬁle-system hierarchy. It is slower than locate, but more accurate.)  
  * find / \-iname '\*messages\*'  
  * find / \-name sshd\_config  
  * find \-user user (Search for ﬁles owned by user in the /home/user directory on host.)  
  * find \-size 10M (ﬁles with a size of 10 megabytes)  
  * find \-size \+10G (more then 10 GB )  
  * Find \-sizw \-10G (less then 10 GB)  
    

Script strts with \#\!/bin/bash

* **If else**:  
    
  \#\!/bin/bash  
    
  echo \-n "Enter a number: "  
  read VAR  
    
  if \[\[ $VAR \-gt 10 \]\]  
  then  
    echo "The variable is greater than 10."  
  else  
    echo "The variable is equal or less than 10."  
  Fi  
    
* **If \-elif:**  
  	  
  \#\!/bin/bash  
    
  echo \-n "Enter a number: "  
  read VAR  
    
  if \[\[ $VAR \-gt 10 \]\]  
  then  
    echo "The variable is greater than 10."  
  elif \[\[ $VAR \-eq 10 \]\]  
  then  
    echo "The variable is equal to 10."  
  else  
    echo "The variable is less than 10."  
  Fi

	

* To search at the beginning of a line, use the caret character (^). To search at the end of a line, use the dollar sign ($).  
    
* grep '^computer' /usr/share/dict/words ()  
* Atq or at \-l (To get an overview of the pending jobs for the current use)  
  * echo "date \>\> /home/student/myjob.txt" | at now \+3min  
* Atrm jobnumber (remove job number)  
* Crontab \-l (list the job for current user )  
* Crontab \-r (remove al jobs for current user )  
* Crontab \-e uname(edit job for current user )

![][image1]

* \* for “Do not Care”/always.  
* Recurring system jobs are defined in two locations: the /etc/crontab file, and files within the /etc/cron.d/ directory. You should always create your custom crontab files under the /etc/cron.d directory to schedule recurring system jobs  
* The crontab system also includes repositories for scripts that need to run every hour, day,week, and month. These repositories are directories called /etc/cron.hourly/, /etc/cron.daily/, /etc/cron.weekly/, and /etc/cron.monthly/  
    
* Getfacl (To display ACL settings on a file)  
* setfacl \-m u:name:rX file (to give ACL permission to file )  
* setfacl \-R \-m u:name:rX directory (to give acl permission to directory )  
* setfacl \-x u:name,g:name file (to delete acl permission )  
  * Setfacl \-b file  
      
* setfacl \-m d:u:name:rx directory (set default permission )

* chcon \-t httpd\_sys\_content\_t /virtual (to change the file context)  
* restorecon \-v /virtual (restore file context)  
* ls \-Zd /virtual (to view file context)  
* nslookup tecmint.com ( the utility finds name server information for domains by querying DNS)  
    
* nslookup \-query=mx tecmint.com (Query Mail Exchanger Record)  
* nslookup \-type=ns tecmint.com(Query Name Server)  
* nslookup \-type=any tecmint.com (Query DNS Record)  
* nslookup \-type=soa tecmint.com(Query Start of Authority)  
* nslookup \-port 56 tecmint.com (Query Port Number)

* dig tecmint.com (dig is a tool for querying DNS nameservers for information about host addresses, mail exchanges, nameservers, and related information.)  
* Free \-h (Keeping track of memory and resources is as much important, as any other task performed by an administrator)  
* Curl \-0 https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885\_960\_720.jpg  
  (save remote file in current working directory)  
* wget downloads the files from the server  
* traceroute ubuntu.com (traceroute command displays the routes, IP addresses, and hostnames of routers over the network.)  
*  stat (command displays the status of a file or file system.)  
* Sort (this command will sort the lines in alphabetical order, from A to Z.)  
* Nc \-lv port   
  * nc \-zv 10.0.2.4 1234  
  * nc \-zv google.com 443  
* Ufw   
  * sudo ufw status  
  * sudo ufw enable/disable   
  * sudo ufw deny from 203.0.113.100		  
  * sudo ufw allow from 203.0.113.101  
  * sudo ufw delete allow from 203.0.113.101  
  * sudo ufw allow OpenSSH  
  * sudo ufw allow 22		


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  

# **User Management Commands:** 

1\. Create User: useradd username 

2\. Set Password: passwd username 

3\. Delete User: userdel username 

4\. Modify User Details: usermod \-option value username 

5\. Assign User to Group: usermod \-aG groupname username 

6\. Remove User from Group: gpasswd \-d username groupname 

7\. List Users: cut \-d: \-f1 /etc/passwd 

8\. List User Details: id username 

9\. Lock User Account: passwd \-l username 

10\. Unlock User Account: passwd \-u username 

11\. Display Last Login: last username 

12\. Set User Expiry: chage \-E YYYY-MM-DD username 

13\. Force User to Change Password on Next Login: chage \-d 0 username 14\. Display User’s Groups: groups username 

15\. Grant Sudo Access: usermod \-aG sudo username 

16\. Revoke Sudo Access: deluser username sudo 

17\. Show Users Logged In: who 

18\. Show Currently Logged-In Users: who \-u 

19\. Kill User’s Active Session: pkill \-KILL \-u username 

20\. Assign Home Directory: usermod \-m \-d /path/to/directory username 

21\. Change Default Shell: chsh \-s /bin/bash username 

22\. Display User Quotas: repquota \-a 

23\. Limit User Logins: usermod \-L username 

24\. Allow User Logins: usermod \-U username 

25\. Set Default User Skeleton: useradd \-D \-b /path/to/skeleton

26\. View User’s Login Shell: echo $SHELL 

27\. Set User Environment Variables: export VARNAME=value 

28\. Display Expired Users: chage \-l username 

29\. Create Group: groupadd groupname 

30\. Delete Group: groupdel groupname 

31\. Modify Group Name: groupmod \-n newgroupname oldgroupname 

32\. List Groups: cut \-d: \-f1 /etc/group 

33\. Display Group Details: getent group groupname 

34\. Assign Primary Group: usermod \-g groupname username 

35\. Change Group Ownership of a File: chgrp groupname filename 

36\. Set Group ID (SGID) on a Directory: chmod g+s directory 

37\. Set Default File Creation Group: umask 002 

38\. List User Processes: ps \-u username 

39\. Show System Users: awk \-F: '$3 \>= 1000 && $1 \!= "nobody" {print $1}'  /etc/passwd 

40\. Display User Activity: ac \-d 

41\. Set Default Password Aging Policy: chage \-m MIN\_DAYS \-M MAX\_DAYS \-I  INACTIVE\_DAYS \-W WARN\_DAYS username 

42\. Restrict Users from Changing Password: chage \-M 99999 username 

43\. Change Password Aging Information: chage \-l username 

44\. Display Group Memberships: getent passwd | grep \-E  

':(username|groupname):' 

45\. Show Group Password Aging Policy: chage \-l groupname 

46\. Limit Simultaneous User Logins: usermod \-L \-f 0 username 

47\. Allow Simultaneous User Logins: usermod \-U \-f \-1 username 

48\. Display Group Password Details: getent group groupname 

49\. Create User with Specific UID: useradd \-u UID username 

50\. Set User’s Default Login Shell: usermod \-s /path/to/shell username 

51\. Display Current User’s Groups:  
groups 

52\. Change User’s Primary Group: newgrp groupname 

53\. Change Group Password: 

gpasswd groupname 

54\. List Group Members: 

getent group groupname 

55\. List All Users and Their Details: getent passwd 

56\. List All Groups and Their Members: getent group 

57\. Set User’s Login Shell: 

chsh \-s /path/to/shell username 

58\. Set User’s Real Name:

chfn \-f "Full Name" username 

59\. Show Files Owned by User: 

find / \-user username 

60\. Show Files Owned by Group: 

find / \-group groupname 

61\. Display User Resource Limits: 

ulimit \-a 

62\. Change User’s Home Directory: 

usermod \-d /new/path/to/home username 63\. Change Default User Shell for All Users: sed \-i 's/oldshell/newshell/' /etc/passwd 

64\. Limit Core Dumps for User: 

ulimit \-c 0 

65\. View User’s Login History:  
lastlog username 

66\. Display Last Failed Login Attempts: 

grep \-i "failed" /var/log/auth.log 

67\. Show Expired Passwords: 

chage \-l | grep "Password expires" 

68\. Set Maximum Password Age: 

chage \-M MAX\_DAYS username 

69\. Set Minimum Password Age: 

chage \-m MIN\_DAYS username 

70\. Set Warning Days before Password Expiry: chage \-W WARN\_DAYS username 

71\. Display Last Password Change Date: chage \-l username | grep "Last password change" 72\. Check Password Complexity Requirements:  
pam\_pwquality \--test 

73\. Lock User Account After Failed Login Attempts: pam\_tally2 \-u username \-l 

74\. Unlock User Account: 

pam\_tally2 \-u username \-r 

75\. Display User’s Privileges: 

sudo \-l \-U username 

76\. List Sudo Rules: 

sudo grep \-E '^\[^\#\]\*\\s+\\w+\\s+=' /etc/sudoers /etc/sudoers.d/\* 77\. Change Group Ownership Recursively: 

chown \-R groupname /path/to/directory 

78\. Add User to Multiple Groups: 

usermod \-aG group1,group2,group3 username 79\. Check User’s Login Shell:  
echo $SHELL 

80\. Display User’s Default Umask: umask 

81\. Set Default Umask: 

umask new\_umask 

82\. List Groups a User is a Member of: groups username 

83\. Remove User from Multiple Groups: userdel \-G group1,group2,group3 username 84\. Set User’s Password Expiry Date: chage \-M MAX\_DAYS \-I INACTIVE\_DAYS username 85\. Display System Users: 

awk \-F: '$3 \< 1000 {print $1}' /etc/passwd 86\. Show System Groups:  
awk \-F: '$3 \< 1000 {print $1}' /etc/group 

87\. Create User with Specific GID: 

useradd \-g GID username 

88\. Set User’s GID: 

usermod \-g GID username 

89\. Set GID for New Files in a Directory: 

chmod g+s /path/to/directory 

90\. List Sudo Rules for a Specific User: 

sudo \-l \-U username 

91\. Display Home Directory Permissions: 

ls \-ld /home/username 

92\. List All Users in a Group: 

getent passwd | awk \-F: \-v group="groupname" '$4 \== group {print $1}' 93\. Add User to Sudoers File:  
echo "username ALL=(ALL) ALL" | sudo tee \-a /etc/sudoers 94\. Remove User from Sudoers File: 

sudo visudo 

95\. Display Account Expiry Information: 

chage \-l username 

96\. Check if a User Exists: 

id username 

97\. Check if a Group Exists: 

getent group groupname 

98\. Display User Login Records: 

last username 

99\. Show Processes Owned by User: 

ps \-u username 

100\. Show Total Disk Usage for a User:  
bash du \-sh /home/username  

Certainly\! Here are more user management commands: 

101\. \*\*Display User's Current Shell:\*\* 

 \`\`\`bash 

 echo $SHELL 

 \`\`\` 

102\. \*\*Set User's Login Shell:\*\* 

 \`\`\`bash 

 chsh \-s /path/to/shell username 

 \`\`\` 

103\. \*\*List Users' Home Directories:\*\* 

 \`\`\`bash 

 awk \-F: '{print $6}' /etc/passwd 

 \`\`\` 

104\. \*\*Display User's Home Directory Size:\*\*  \`\`\`bash 

 du \-sh /home/username 

 \`\`\` 

105\. \*\*Create User with Custom Expiry Date:\*\*  \`\`\`bash 

 useradd \-e YYYY-MM-DD username 

 \`\`\`  
106\. \*\*Display Files Modified by User:\*\* 

 \`\`\`bash 

 find / \-user username \-exec ls \-l {} \\; 

 \`\`\` 

107\. \*\*Set User's UID:\*\* 

 \`\`\`bash 

 usermod \-u UID username 

 \`\`\` 

108\. \*\*Change Group Ownership of User's Files:\*\*  \`\`\`bash 

 find /path/to/files \-user username \-exec chown newgroup '{}' \\;  \`\`\` 

109\. \*\*Display User's Last Password Change Time:\*\*  \`\`\`bash 

 chage \-l username | grep "Last password change"  \`\`\` 

110\. \*\*List All Users and Their Groups:\*\* 

 \`\`\`bash 

 getent passwd | awk \-F: '{print $1, $4}' 

 \`\`\` 

111\. \*\*Display Group Password Details:\*\* 

 \`\`\`bash  
 getent group groupname 

 \`\`\` 

112\. \*\*Modify User's GECOS (General Electric Comprehensive Operating System)  Information:\*\* 

 \`\`\`bash 

 usermod \-c "New GECOS" username 

 \`\`\` 

113\. \*\*Show Files Owned by User and Larger Than a Specific Size:\*\*  \`\`\`bash 

 find / \-user username \-size \+1M \-exec ls \-lh {} \\; 

 \`\`\` 

114\. \*\*Set User's Default umask:\*\* 

 \`\`\`bash 

 echo "umask new\_umask" \>\> /etc/bash.bashrc 

 \`\`\` 

115\. \*\*Display User Processes and Resource Usage:\*\* 

 \`\`\`bash 

 ps \-u username \-o pid,%cpu,%mem,cmd 

 \`\`\` 

116\. \*\*Create User and Assign Multiple Secondary Groups:\*\* 

 \`\`\`bash 

 useradd \-G group1,group2,group3 username 

 \`\`\`  
117\. \*\*Display User's Most Recently Used Files:\*\*  \`\`\`bash 

 find /home/username \-type f \-atime \-7 

 \`\`\` 

118\. \*\*Set User's Default umask in Profile:\*\*  \`\`\`bash 

 echo "umask new\_umask" \>\> /home/username/.bashrc  \`\`\` 

119\. \*\*Display User's Group Membership Details:\*\*  \`\`\`bash 

 id username 

 \`\`\` 

120\. \*\*Change User's Password Non-Interactively:\*\*  \`\`\`bash 

 echo "newpassword" | passwd \--stdin username  \`\`\` 

121\. \*\*Display Total Disk Usage for a User:\*\*  \`\`\`bash 

 du \-sh /home/username 

 \`\`\` 

122\. \*\*Set User's Account to Expire:\*\* 

 \`\`\`bash  
 usermod \-e YYYY-MM-DD username 

 \`\`\` 

123\. \*\*Set User's Login Shell Interactively:\*\*  \`\`\`bash 

 chsh username 

 \`\`\` 

124\. \*\*Display Users with Expiring Passwords:\*\*  \`\`\`bash 

 chage \-l | grep "Password expires" | awk '$NF \< 7'  \`\`\` 

125\. \*\*Change User's Primary Group Interactively:\*\*  \`\`\`bash 

 newgrp groupname 

 \`\`\` 

126\. \*\*Show Processes Running as a Specific User:\*\*  \`\`\`bash 

 ps \-U username 

 \`\`\` 

127\. \*\*Display User's Last Login Details:\*\*  \`\`\`bash 

 lastlog \-u username 

 \`\`\`  
128\. \*\*Check if a User is Logged In:\*\* 

 \`\`\`bash 

 who | grep \-w username 

 \`\`\` 

129\. \*\*Show Group Password Details:\*\* 

 \`\`\`bash 

 getent group groupname 

 \`\`\` 

130\. \*\*Create User with a Specific Shell:\*\*  \`\`\`bash 

 useradd \-s /path/to/shell username 

 \`\`\` 

131\. \*\*Change User's Home Directory Interactively:\*\*  \`\`\`bash 

 usermod \-d /new/path/to/home username  \`\`\` 

132\. \*\*Display Last Login Details for All Users:\*\*  \`\`\`bash 

 lastlog 

 \`\`\` 

133\. \*\*Display Users with No Password:\*\*  \`\`\`bash 

 awk \-F: '$2 \== "" {print $1}' /etc/shadow  
 \`\`\` 

134\. \*\*Set User's Password Non-Interactively:\*\* 

 \`\`\`bash 

 echo "username:newpassword" | chpasswd 

 \`\`\` 

135\. \*\*List All Users in Multiple Groups:\*\* 

 \`\`\`bash 

 getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  \`\`\` 

136\. \*\*Display User's Current Group Memberships:\*\* 

 \`\`\`bash 

 id \-Gn username 

 \`\`\` 

137\. \*\*Create User with Custom Home Directory:\*\* 

 \`\`\`bash 

 useradd \-m \-d /path/to/custom/home username 

 \`\`\` 

138\. \*\*Display Users with UID Less Than 1000:\*\* 

 \`\`\`bash 

 awk \-F: '$3 \< 1000 {print $1}' /etc/passwd 

 \`\`\` 

139\. \*\*Set Password Expiry Warning Days:\*\*  
 \`\`\`bash 

 chage \-W WARN\_DAYS username 

 \`\`\` 

140\. \*\*Display Number of Failed Login Attempts:\*\* 

 \`\`\`bash 

 pam\_tally2 \-u username 

 \`\`\` 

141\. \*\*Create User with UID and GID:\*\* 

 \`\`\`bash 

 useradd \-u UID \-g GID username 

 \`\`\` 

142\. \*\*Set GID for New Files in a Directory Interactively:\*\*  \`\`\`bash 

 chmod g+s directory 

 \`\`\` 

143\. \*\*List Users with No Shell Access:\*\* 

 \`\`\`bash 

 awk \-F: '$NF \!\~ "/bin/(sh|bash)" {print $1}' /etc/passwd  \`\`\` 

144\. \*\*Display User's Last Password Change Time in Epoch Format:\*\*  \`\`\`bash 

 chage \-l username | grep "Last password change" | awk '{print $5}'  \`\`\`  
145\. \*\*List Users with UID Greater Than 1000:\*\* 

 \`\`\`bash 

 awk \-F: '$3 \>= 1000 {print $1}' /etc/passwd 

 \`\`\` 

146\. \*\*Display User's Full Name:\*\* 

 \`\`\`bash 

 finger username 

 \`\`\` 

147\. \*\*List Users with No Home Directory:\*\* 

 \`\`\`bash 

 awk \-F: '$6 \== "" {print $1}' /etc/passwd 

 \`\`\` 

148\. \*\*Set Default Password Aging Policy Interactively:\*\* 

 \`\`\`bash 

 chage username 

 \`\`\` 

149\. \*\*Show Users with No Shell Access in /etc/passwd:\*\* 

 \`\`\`bash 

 awk \-F: '$7 \!\~ "/bin/(sh|bash)" {print $1}' /etc/passwd 

150\. Display User’s Last Password Change in Human-Readable Format: bash chage \-l username | grep "Last password change" | awk \-F: '{print $2}'  151\. Set User’s Shell to nologin:  
bash usermod \-s /usr/sbin/nologin username  

152\. Display User’s Group Membership Details: 

bash id \-Gn username  

153\. Set User’s Password Expiry Date: 

bash chage \-M MAX\_DAYS \-I INACTIVE\_DAYS username  

154\. Show Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

155\. Display Users in Secondary Groups: 

bash getent passwd | awk \-F: '{print $1, $4}' | grep "groupname"  156\. Set Default Password Aging Policy in Days: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  157\. List Users with Expired Passwords: 

bash chage \-l | grep "Password expires" | awk '$NF \< 0'  

158\. Show Users in Group Recursively: 

bash find / \-group groupname \-exec ls \-l {} \\;  

159\. Set User’s Default Group Interactively: 

bash usermod \-g groupname username  

160\. Check if a Group is Empty: 

bash getent passwd | awk \-F: \-v group="groupname" '$4 \== group {print $1}' | wc \-l  161\. Set Default GID for New Files: 

bash umask \-g GID  

162\. Display Users with No Password Aging: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Password expires:  never"  

163\. Show Users in a Group with Details: 

bash getent passwd | awk \-F: \-v group="groupname" '$4 \== group {print $1, $3, $6}'  164\. Set Default Shell for New Users: 

bash useradd \-D \-s /path/to/shell   
165\. Display Groups a User is Not a Member of: 

bash getent group | awk \-F: \-v user="username" '$NF \!\~ user {print $1}'  166\. Set Maximum Inactivity Days for User: 

bash chage \-I INACTIVE\_DAYS username  

167\. Display Number of Users Logged In: 

bash who | wc \-l  

168\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  169\. Set User’s Login Shell to Bash: 

bash usermod \-s /bin/bash username  

170\. Show Users with No Valid Shell: 

bash awk \-F: '$NF \!\~ "/bin/(sh|bash)" {print $1}' /etc/passwd  171\. Set User’s Home Directory Permissions: 

bash chmod 700 /home/username  

172\. List Users with Specific UID Range: 

bash awk \-F: '$3 \>= MIN\_UID && $3 \<= MAX\_UID {print $1}' /etc/passwd  173\. Display System Users with No Login Shell: 

bash awk \-F: '$3 \< 1000 && $7 \== "/sbin/nologin" {print $1}' /etc/passwd  174\. Set User’s Shell to nologin Interactively: 

bash chsh \-s /sbin/nologin username  

175\. List Users Excluded from Password Aging: 

bash awk \-F: '$8 \== "\!" {print $1}' /etc/shadow  

176\. Show Users with No Home Directory Permissions: bash find /home \-maxdepth 1 \-type d \-not \-executable  

177\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

178\. List Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root   
179\. Display Users with No Shell Access in /etc/passwd: 

bash awk \-F: '$7 \!\~ "/bin/(sh|bash)" {print $1}' /etc/passwd  

180\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  181\. Show Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

182\. Set Group Password Expiry Date: 

bash chage \-M MAX\_DAYS groupname  

183\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  184\. Set Password Complexity Requirements: 

bash pam\_pwquality \--test  

185\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

186\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

187\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

188\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

189\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  

190\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

191\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

192\. Set Maximum Password Age for Group:  
bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

193\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

194\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

195\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  196\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

197\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

198\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

199\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

200\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

201\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

202\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

203\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  204\. Set Default Password Aging Policy in Days for All Users: bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  205\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd   
206\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

207\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  208\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  209\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

210\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

211\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  212\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

213\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

214\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

215\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

216\. Set Default Shell for All Users Non-Interactively: 

\`\`\`bash 

sed \-i ‘s/oldshell/newshell/’ /etc/passwd 

\`\` 

217\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root   
218\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

219\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  220\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

221\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

222\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

223\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

224\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

225\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  226\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

227\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

228\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

229\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

230\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

231\. Display Users with UID and GID Matching:  
bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

232\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

233\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  234\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  235\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

236\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

237\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  238\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  239\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

240\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

241\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  242\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

243\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

244\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname   
245\. Display Users with No Login Shell in /etc/passwd: 

\`\`\`bash 

awk \-F: ’$7 \== “/sbin/nologin” {print $1}’ /etc/passwd 

246\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

247\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  248\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

249\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

250\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

251\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

252\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

253\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

254\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

255\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  256\. Set Default Password Aging Policy in Days for All Users: bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  257\. Display Users with UID and GID Matching:  
bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

258\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

259\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  260\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  261\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

262\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

263\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  264\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

265\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

266\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

267\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

268\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

269\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  270\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username   
271\. Display Users with UID and GID Mismatch: 

\`\`\`bash 

awk \-F: ‘$3 \!= $4 {print $1}’ /etc/passwd 

272\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

273\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

274\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

275\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

276\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

277\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  278\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  279\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

280\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

281\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  282\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  283\. Display Users with No Home Directory Ownership:  
bash find /home \-maxdepth 1 \-type d \-not \-user root  

284\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

285\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  286\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

287\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

288\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

289\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

290\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

291\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  292\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

293\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

294\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

295\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

296\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname   
297\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

298\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

299\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  300\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  301\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

302\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

303\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  304\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  305\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

306\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

307\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  308\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

309\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

310\. Set Maximum Password Age for Group:  
bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

311\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

312\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

313\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  314\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

315\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

316\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

317\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

318\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

319\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

320\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

321\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  322\. Set Default Password Aging Policy in Days for All Users: bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  323\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd   
324\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

325\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  326\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  327\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

328\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

329\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  330\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

331\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

332\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

333\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

334\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

335\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  336\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

337\. Display Users with UID and GID Mismatch:  
bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

338\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

339\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

340\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

341\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

342\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

343\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  344\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  345\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

346\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

347\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  348\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  349\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

350\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell   
351\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  352\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

353\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

354\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

355\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

356\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

357\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  358\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

359\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

360\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

361\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

362\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

363\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

364\. Set Password Expiry Warning Days for Group:  
bash chage \-W WARN\_DAYS groupname  

365\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  366\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  367\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

368\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

369\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  370\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  371\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

372\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

373\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  374\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

375\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

376\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

377\. Display Users with No Login Shell in /etc/passwd: 

\`\`\`bash  
awk \-F: ‘$7 \== “/sbin/nologin” {print $1}’ /etc/passwd 

\`\` 

378\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

379\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  380\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

381\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

382\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

383\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

384\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

385\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

386\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

387\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  388\. Set Default Password Aging Policy in Days for All Users: bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  389\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd   
390\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

391\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  392\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  393\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

394\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell  

395\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  396\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

397\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

398\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

399\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

400\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

401\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  402\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

403\. Display Users with UID and GID Mismatch:  
bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

404\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

405\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

406\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

407\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

408\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

409\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  410\. Set Default Password Aging Policy in Days for All Users: 

\`\`\`bash 

chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username 

411\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

412\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

413\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  414\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  415\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

416\. Set Default Shell for All Users Interactively:  
bash chsh \-s /path/to/shell  

417\. List Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  418\. Set Default Password Aging Policy Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

419\. Display Users with No Home Directory: 

bash awk \-F: '$6 \== "" {print $1}' /etc/passwd  

420\. Set Maximum Password Age for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS groupname  

421\. Display Users with No Login Shell in /etc/passwd: 

bash awk \-F: '$7 \== "/sbin/nologin" {print $1}' /etc/passwd  

422\. Set Default Shell for All Users Non-Interactively: 

bash sed \-i 's/oldshell/newshell/' /etc/passwd  

423\. Show Users in Multiple Groups: 

bash getent passwd | awk \-F: \-v groups="group1,group2" '$4 \~ groups {print $1}'  424\. Set Default Password Aging Policy Non-Interactively: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS \-I INACTIVE\_DAYS  username  

425\. Display Users with UID and GID Mismatch: 

bash awk \-F: '$3 \!= $4 {print $1}' /etc/passwd  

426\. Set Default Password Aging Policy for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS \-E  EXPIRY\_DATE username  

427\. List Users with No Password Aging: 

bash awk \-F: '$8 \== "" {print $1}' /etc/shadow  

428\. Set Maximum Inactivity Days for Group: 

bash chage \-I INACTIVE\_DAYS groupname  

429\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd   
430\. Set Password Expiry Warning Days for Group: 

bash chage \-W WARN\_DAYS groupname  

431\. List Users with Specific Shell: 

bash awk \-F: \-v shell="/path/to/shell" '$NF \== shell {print $1}' /etc/passwd  432\. Set Default Password Aging Policy in Days for All Users: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-W WARN\_DAYS username  433\. Display Users with UID and GID Matching: 

bash awk \-F: '$3 \== $4 {print $1}' /etc/passwd  

434\. Set Default Password Aging Policy for Group: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS \-W WARN\_DAYS  groupname  

435\. List Users with Expired Accounts: 

bash awk \-F: '{print $1}' /etc/passwd | xargs \-I {} chage \-l {} | grep "Account expires"  436\. Set Group Password Aging Policy: 

bash chage \-M MAX\_DAYS \-m MIN\_DAYS \-I INACTIVE\_DAYS groupname  437\. Display Users with No Home Directory Ownership: 

bash find /home \-maxdepth 1 \-type d \-not \-user root  

438\. Set Default Shell for All Users Interactively: 

bash chsh \-s /path/to/shell   


[image1]: <data:image/png;base64,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>