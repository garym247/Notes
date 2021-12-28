# Installing Linux On Windows

```wsl --install -d <Linux distribution>```
* Need to run in Administrator mode.
* e.g. ```wsl --install -d Ununtu```

```wsl --list --online```
* Lists all the Linux distributions available for installation

# Handy Terminal Shortcuts

```Ctrl+L```     Clear screen

# Directory Structure

# Handy Files
```/etc/issue``` indicates what version of Linux you are running.

```/proc/cpuinfo``` contains cpu informion

```grep -c ^processor /proc/cpuinfo```
* counts the number of processors
* ```-c``` returns the count of string patterns matched.

```/etc/hosts```
* acts as a local DNS lookup.
* this is checked before the external DNS.
* when browsing for a web url, it allows you to redirect the web url request to another IP address.
* has 3 columns
    a.  ip addess
    b.  url
    c.  alias (optional, can type this directly into the web browser to goto a website)


# FileSystem Commands
```ls -a```
* Lists all the hidden files, i.e. files beginning with ```.```

```mkdir -p <dir>/<subdir>/<subdir>```
* Allows us to create nested folders.

```touch <filename 1> <filename 2> ... <filename n>```
* if <filename> doesn't exist touch will create it
* if <filename> does exist, then it will create it  

```rm```
* can delete files and directories
* by default only deletes a directory if it is empty
* can delete files or directories
* ```-v``` option is a nice way to confirm what was deleted
* ```-i``` interactive mode, asks for confirmation of each directory/file to delete
  
```xdg-open```

```head <filename>```
by default it prints out the top 10 lines of the file

```tail```


```apropos <search string>```
* returns all the Linux commands related to the search string 

```gedit <filename>```
* use gedit when you have a graphical interface                                   

```nano <filename```
* nice console text editor  

```ssh localhost```
* to determine if the ssh service is running on the local machine

```history```
* lists the previous 1000 commands executed by the user
* .bash_history contains your bash command history

```source ~/.bashrc```
* to reload the bash login script without having to logout and login

```alias```
* lists all the aliases
  
```grep```
* stands for Global Regular Expression Print
* -i : ignore case
* -n : returns the line number
* grep "word1 word2" to search for multiple words
  

echo        echo -e \${PATH//:/\\\\n}                   |
* displays the directories in the PATH separated by newlines
* -n : suppresses the newline                 |

```!!```
* repeats the last command (might need to do sudo !!, if it requires su
privileges)

```<command> ```wc -l```
* to count the number of lines output by a command.

```make -n```
* performs a dry run to show what commands will be executed.


# IO Redirection

```<command> > <filename>```
* to write to a file (not sure if it will overwrite an existing file)

```<command> >> <filename>```
* to append to a file

```<program> [arguments...] 2>&1 | tee <output file>```
* ```2>&1``` directs output channel 2 (```stderr```) to channel 1 (```stdout```)
* ```tee``` allows viewing and storing of program output.
* ```tee -a``` to append to a file rather than overwrite.

```<command> > /dev/null 2>&1```
* redirects the output of your program to ```/dev/null```. Include both the ```stderr``` and ```stdout```.


# User Management

```passwd```
* to change a users password

```groups```
* lists the groups that a user belongs to

# File management


```file <filename> ```displays a brief summary about the file

```touch            ```if the file doesn't exist it will be created      |

```<filename>      ```                   

```less <filename> ```less +F <filename> to poll contents of a file    |


```rm```
* ```rm <dir name>``` delete all the files contained within a directory, it does not delete the directories.                       |
                   
1.  rm -rf \<dir name> (-r = recursive -f =       |
    force) to delete a directory and all its      |
    contents.      

```rmdir \<dir      ```rmdir -rf \<dir name> to recursively delete a     |
```name>            ```directory          

```which            ```returns the path to the filename                  |
```\<filename>      ```                   
(note: equivalent on windows is \"where\")        |

```find             ```Peforms a recursive search.                       |
                   
Finds files and directories.                      |
                   
-name \<filename> : searches for filename         |
                   
-iname \<filname> : ignores case                  |
                   
-type f : only searches for files.                |
                   
-size +1M : only files over 1 megabyte            |
                   
-maxdepth 1 : only search 1 directory deep        |
                   
-exec grep \<options> {}+: performs the grep on   |
the files returned from the find. {}+ terminates  |
the -exec option.  

```locate           ```1.  searches a database rather than the file      |
```\<filename>      ```    system         
                   
2.  the database can manually updated via sudo    |
    updatedb       
                   
3.  if the file is not present in the site        |
    database, then \"locate\" won\'t find it      |
                   
4.  some Linux systems automatically update the   |
    database daily 

```ls               ```stands for \"list storage\"                       |
                   
ls -a includes the hidden files (i.e. those       |
prefixed with a \".\")  
                   
It is handy to setup up the following aliases
* ```alias ll='ls -l'```
* ```alias la='ls -a'```
* ```alias l='ls -CF'```


Three ways to display the contents of a file:

\- cat \<filename>

\- more \<filename> \<- very old, don\'t bother using it

\- less \<filename> \<- better, less is more

file permissions

b \-\-- \-\-- \-\-- b = clock special file

c \-\-- \-\-- \-\-- c = character special file

chmod 777 \<directory or file>

chmod -R 777 \<directory or file>

chmod ugo+x \<directory or file>

chmod a+x \<directory or file>

chgrp \<group name> \<filename> changes the group ownership of a file(s)

sudo chown gary:gary -R ./

chown gary:gary -R ./

# Processes
```ps```
* ps -aux
  pgrep \<app name>    

  kill \<process id>   

  ldd \<executable>    lets you see what .so files an executable uses

  systemctl            lists all the background services running on the host machine

# Networking

```hostname```
* Displays name the host

```ifconfig```
* Configure Network Interface
* displays ip addresses of all the machines network cards.
* ```sudo ifconfig \<name> \<ipaddress> netmask 255.255.255.0 up``` reports packets sent/received for each network interface

```netstat ```
* stands for Network Statistics
* netstat -i display usage of each interface
* netstat -ta prints status of active socket connections (t= tcp, -a = all)            
* netstat -nr (n = ip address, r = routing table)

```ping    ```
* Uses ICMP, not TCP or UDP 
* Implemented as a ICMP echo request and echo reply message
* ICMP = internet control message protocol

```tcpdump ```
* ```tcpdump``` is a packet sniffer                             
* ```tcpdump -C 10``` captures 10 packets
* ```tcpdump -A``` print packets in ASCII
* ```tcpdump -XX``` print packets in Hex 
* ```tcpdump ip proto \\\\icmp``` : to monitor ping commands
* ```tcpdump -i \<interface>``` to monitor traffic on a particular interface card              
* ```tcpdump -i \<interface> -p \<port number>``` to monitor traffic on a particular interface card port
* NOTE : use ifconfig to determine valid interface values.

```curl```
* stands for Client URL                            
* curl                                                
```http://ipinfo.io/ip]```{.underline}](http://ipinfo.io/ip)
*     will return the ip address of the host machine as seen by the web server       


To set up a static ip address (CentOS):

Edit /etc/sysconfig/network-scripts/ifcfg-\<if name>, e.g. ifcfg-enp0s3

# Firewall (iptables)

You need to sudo or be logged in as a root to run iptables.

There are 3 types of chains
* INPUT
* FORWARD
* OUTPUT

iptables -V : displays the version of the firewall

iptables -L \```grep policy : displays the policy chains

iptables \--policy \<policy chain> \<policy permission>

where policy chain = INPUT, OUTPUT or FORWARD

policy permission = ACCEPT, DROP or REJECT

To drop incoming traffic from an ip address/address range

iptables -A INPUT -s 10.10.10.10 -j DROP

iptables -A INPUT -s 10.10.10.0/24 -j DROP

iptables can be set up to log ICMP (ping) packets.

To drop incoming traffic from a specific port and ip address

iptables -A INPUT -p tcp \--dport ssh -s 10.10.10.10 -j DROP

To allow a remote machine to establish a SSH connection to your machine,

but prohibit a SSH connection from your machine to it:

iptables -A INPUT -p tcp \--dport ssh -s 10.10.10.10 -m state \--state
NEW,ESTABLISHED -j ACCEPT

iptables -A OUTPUT -p tcp \--sport 22 -d 10.10.10.10 -m state \--state
ESTABLISHED -j ACCEPT

This says that NEW connections are allowed from 10.10.10.10 to your
machine,

however only ESTABLISHED (not NEW) connections are allowed from the host
to

10.10.10.10

Can use the reply from ping to see the difference between the NEW,
ESTABLISHED permissions.

To save changes you made to the firewall

/sbin/service iptables save

# Environment Variables

set prints out all the environment variables

export LD_LIBRARY_PATH=\<path>

export LD_LIBRARY_PATH=\$LD_LIBRARY_PATH:\<path>

echo \$LD_LIBRARY_PATH

# Disk management

+-----------+----------------------------------------------------------+
```mount     ```provides details on the NFS (Network File System) setup  |
```          ```                          
```          ```Also see /etc/fstab       
+===========+==========================================================+
```df        ```(disk free) lists all the mounted drives and their free  |
```          ```space                     
```          ```                          
```          ```df -h shows the free space in a human readable form      |
```          ```(i.e. the units are in MB or GB)                         |
+-----------+----------------------------------------------------------+
```showmount ```showmount -e \<server> lists all the available drives    |
```          ```that a server has available for mounting                 |
+-----------+----------------------------------------------------------+
```parted    ```partition editor (requires sudo)                         |
+-----------+----------------------------------------------------------+

# Installing Tools and Applications

yum = Yellowdog Updater Modified

+----------------------------+-----------------------------------------+
```yum install \<package      ```         
```name>                      ```         
+============================+=========================================+
```yum remove \<package name> ```         
+----------------------------+-----------------------------------------+
```yum update \<package name> ```         
+----------------------------+-----------------------------------------+
```yum info \<package name>   ```         
+----------------------------+-----------------------------------------+
```yum search \<string        ```list all the available packages from    |
```pattern>                   ```the yum repo that match the string      |
```                           ```pattern  
+----------------------------+-----------------------------------------+
```yum list                   ```lists all the packages available in the |
```                           ```yum repo 
```yum list installed         ```         
```                           ```lists all the installed packages        |
+----------------------------+-----------------------------------------+

# Handy Linux Tools

nano : really handy console text editor (yum install nano)

nano <filename>

(VNC = Virtual Network Computing)

vncstart is an alias for \'vncserver :21 -depth 16 -geometry 1920x1080\'

# Compilers

gcc = gnu compiler collection

g++ = gnu c++ compiler

# To sort out

To continuosly ping a host:

*ping \<ip address> -w \<timeout in ms> -t*

To poll the end of a log file:

*tail -f \<filename>*

this can also be fed into a grep, so that only lines containing a
certain word are display, e.g.

*tail -f \<filename> \```grep \<word to look for>*

