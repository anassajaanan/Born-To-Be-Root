# Born To Be Root

---

### what is virtualization ?

Virtualization is the process of creating a virtual or simulated version of a computer system or resource. It allows you to run multiple virtual machines (VMs) or operating systems on a single physical machine. By doing so, virtualization enables better utilization of hardware resources, improves efficiency, and provides flexibility in managing and deploying applications.

Virtualization is commonly used in server environments, where multiple virtual servers can be created and managed on a single physical server. It also finds applications in desktop virtualization, network virtualization, and storage virtualization, among others.

The key benefits of virtualization include:

1. Consolidation: Virtualization allows you to consolidate multiple physical servers into fewer or even a single physical server, reducing hardware costs and simplifying management.
2. Resource optimization: By sharing and dynamically allocating resources among virtual machines, virtualization maximizes the utilization of CPU, memory, storage, and network capabilities.
3. Flexibility and scalability: Virtual machines can be easily created, cloned, moved, or scaled up/down as per the requirements. This flexibility allows for efficient resource allocation and adapts to changing business needs.
4. Improved disaster recovery and high availability: Virtual machines can be backed up, replicated, and restored more easily, enabling faster disaster recovery and providing high availability options for critical applications.
5. Testing and development: Virtualization provides a sandboxed environment for testing and development, allowing software engineers to isolate their work and experiment without impacting the production environment.

Overall, virtualization simplifies IT infrastructure management, optimizes resource utilization, and enhances agility in deploying and managing applications.

---

### What is a virtual machine ?

A virtual machine (VM) is a software emulation of a physical computer system. It behaves like a complete computer with its own operating system (OS) and applications, running within a host computer.

In simple terms, a virtual machine is a self-contained, isolated environment that runs on a physical server or a host machine. It abstracts the underlying hardware resources and provides a virtualized set of resources to the operating system and applications running inside it.

Each virtual machine has its own virtual CPU, memory, storage, and network interfaces. It operates independently of other virtual machines running on the same host, allowing multiple VMs to coexist on a single physical server.

Virtual machines are created using virtualization software, also known as a hypervisor. The hypervisor manages the allocation and sharing of physical resources among the virtual machines, ensuring they run efficiently and securely.

Virtual machines are commonly used for various purposes, including:

1. Server virtualization: Multiple virtual servers can be hosted on a single physical server, allowing better resource utilization and simplifying server management.
2. Desktop virtualization: Virtual machines can be used to create virtual desktop environments, enabling users to access their desktops remotely or run different operating systems on their computers.
3. Software development and testing: Virtual machines provide a controlled and isolated environment for developers to test software and applications without affecting their production systems.
4. Legacy application support: Virtual machines can run older or incompatible applications within a modern operating system, ensuring compatibility and avoiding the need for dedicated hardware.

Virtual machines offer several benefits, such as improved hardware utilization, easier management, faster deployment of new systems, and enhanced security through isolation. They have become an integral part of modern IT infrastructure, enabling efficient utilization of resources and greater flexibility in managing and deploying applications.

---

### What is Debian ?

Certainly! Debian is a popular open-source operating system known for its stability, security, and large community support. It is one of the oldest and most respected Linux distributions available. Here are some key points about Debian:

1. Philosophy: Debian is built on a philosophy of free software and community-driven development. It emphasizes open-source principles, offering users the freedom to use, modify, and distribute the software as they wish.
2. Package Management: Debian uses the Advanced Package Tool (APT) for package management. APT simplifies software installation, updates, and removals by resolving dependencies automatically. It provides a vast repository of software packages, ensuring easy access to a wide range of applications.
3. Release Model: Debian follows a stable release model. It focuses on long-term stability and reliability by thoroughly testing software before including it in a stable release. This approach is favored by users and organizations that prioritize stability over having the latest features.
4. Package Stability: Debian stable releases tend to have older versions of software packages. While this may mean slower adoption of cutting-edge features, it results in a highly reliable and secure operating system.
5. Multiple Architectures: Debian supports multiple hardware architectures, including x86, ARM, PowerPC, and more. This flexibility allows Debian to be used on various devices, from personal computers to servers and embedded systems.
6. Package Variants: Debian offers multiple editions or "flavors" to cater to different user needs. The main editions include Debian Stable, Debian Testing, and Debian Unstable. Additionally, there are specific versions like Debian for ARM processors or specialized editions like Debian Edu for educational institutions.
7. Community and Collaboration: Debian has a large and vibrant community of developers and users. It follows an open development process, allowing anyone to contribute to the project. This collaborative approach has contributed to Debian's reputation for stability and reliability.
8. Derivative Distributions: Many popular Linux distributions, such as Ubuntu, Linux Mint, and Kali Linux, are based on Debian. These distributions build upon Debian, adding their own features and customization while benefiting from Debian's solid foundation.

Overall, Debian provides a robust, versatile, and reliable operating system that is suitable for a wide range of users, from beginners to advanced users and from personal use to enterprise-level deployments. Its commitment to open-source principles and community-driven development has made it a cornerstone of the Linux ecosystem.

---

### What is the difference between apt and o ?

APT (Advanced Package Tool) and Aptitude are both package management tools in Debian-based systems. APT has a command-line interface, while Aptitude offers a text-based graphical interface along with a command-line interface. 

If you consider only the command-line interfaces of each, they are quite similar as each of them offers you different ways to manage your packages. Therefore, there are a few differences that we can list:

- Apt offers a command-line interface, while aptitude offers a visual interface
- When facing a package conflict, `apt` will not fix the issue while `aptitude` will suggest a resolution that can do the job
- aptitude can interactively retrieve and displays the Debian changelog of all available official packages

Apt requires the user to have a solid knowledge of Linux systems and package management as you are running everything in the command line. It can be difficult for a novice to handle.

On the other hand, aptitude with its interface is more user-friendly as it offers a layer of abstraction regarding the different sub-commands to use for installation, upgrades, etc.

---

### What’t the difference between AppArmor and SElinux ?

AppArmor is much easier to learn and use, AppArmor is often considered the safer choice. However, admins that need more control should use SELinux.

- SELinux defines access controls for applications, processes and files on a system with security policies. Those policies define what users can or cannot access. Unless a policy is defined for a process, app or directory, SELinux won't allow access to it. This system is built into the kernel of the system.
- AppArmor uses profiles to determine what files and permissions an application requires. Each system also uses certain features differently.

### Access control

SELinux [uses security policies](https://www.techtarget.com/searchsecurity/feature/How-to-implement-Linux-security-best-practices) based on file labels, whereas AppArmor uses policies that are based on paths.

AppArmor provides mandatory access control to supplement traditional discretionary access control.

---

### How to change the host name of VM ?

To change the hostname of your Debian virtual machine (VM) in the command-line interface (CLI), you can follow these steps:

Check the current hostname by running the following command:

```bash
hostname
```

1. To change the hostname, you can use the `hostnamectl` command. Run the following command, replacing "newhostname" with the desired hostname:

```
sudo hostnamectl set-hostname newhostname
```

1. The hostname change takes effect immediately, but you also need to update the hostname in the `/etc/hosts` file. Open the file using a text editor such as `nano` or `vi`:

```
sudo nano /etc/hosts
```

1. Locate the line that contains the old hostname and update it with the new hostname. For example, if the line looks like this:

```
127.0.0.1   oldhostname
```

Change it to:

```
127.0.0.1   newhostname
```

1. Save the changes and exit the text editor.
2. Finally, reboot your virtual machine for the changes to take full effect:

```
sudo reboot
```

After the reboot, your Debian virtual machine will have the new hostname you specified. You can confirm the change by running the `hostname` command again:

```
hostname
```

Make sure to update any relevant configuration files or applications that rely on the hostname to avoid any potential issues.

### How to create a new user and assign it to a group ?

To create a new user, use the `adduser` command followed by the desired username. For example, to create a user named "myuser", you would run:

```
sudo adduser myuser
```

You will be prompted to set a password for the new user and provide additional information like full name, phone number, etc. You can fill in these details or leave them blank by pressing Enter.

1. After setting the password and providing the optional details, the new user will be created.
2. To assign the user to a specific group, use the `usermod` command. For example, to assign the user "myuser" to the group "mygroup", you would run:

```
sudo usermod -aG mygroup myuser
```

The `-aG` option ensures that the user is added to the specified group without removing them from any existing groups.

Note: Replace "mygroup" with the actual name of the group you want to assign the user to.

That's it! You have successfully created a new user in Debian and assigned them to a specific group. The user can now log in using their username and password and will have the group permissions associated with the assigned group.

### How to create a group and assign a user to it ?

To create a new group, use the `addgroup` command followed by the desired group name. For example, to create a group named "mygroup", run the command:

```
sudo addgroup mygroup
```

1. After creating the group, use the `usermod` command with the `aG` option to add a user to the group. Run the following command, replacing "myuser" with the desired username and "mygroup" with the name of the group you created:

```
sudo usermod -aG mygroup myuser
```

That's it! You have successfully created a group and assigned a user to it. The user will now be a member of the specified group and have the associated group permissions.

### SSH

Sure! Here are concise answers to your questions:

- SSH (Secure Shell) is a protocol that provides secure remote access to systems over an unsecured network. It allows for encrypted communication and secure management of remote systems.
- To install SSH in Debian, run the command:

```
sudo apt update
sudo apt install openssh-server
```

- To make SSH run on a specific port, edit the SSH server configuration file:

```
sudo nano /etc/ssh/sshd_config
```

Find the line that says `#Port 22` and change it to your desired port number. Remove the `#` symbol to uncomment the line. Save the changes and restart the SSH service:

```
sudo systemctl restart ssh
```

- To prevent SSH access as root, edit the SSH server configuration file:

```
sudo nano /etc/ssh/sshd_config
```

Find the line that says `PermitRootLogin yes` and change it to `PermitRootLogin no`. Save the changes and restart the SSH service:

```
sudo systemctl restart ssh
```

These steps will install SSH, configure it to run on a specific port, and prevent root login via SSH.

### UFW

- UFW (Uncomplicated Firewall) is a user-friendly command-line tool used to manage firewall rules in Debian and Ubuntu.
- To install UFW in Debian, run the command:

```
sudo apt update
sudo apt install ufw
```

- To configure UFW and allow only port 4242, run the following commands:

```
sudo ufw default deny incoming
sudo ufw allow 4242
sudo ufw enable
```

The first command denies all incoming connections by default. The third command allows incoming connections on port 4242. The last command enables UFW and activates the firewall with the configured rules.

After executing these commands, the firewall will be configured to allow incoming connections only on port 4242, while blocking other incoming traffic.

### ****Set password policy****

This setting enforces how many classes, i.e upper-case, lower-case, and other characters, should be in a password, also the length of the password.

> “To set up a strong password policy, you have to comply with the following requirements:
> 
> - *Your password must be at least 10 characters long. It must contain an uppercase letter and a number. Also, it must not contain more than 3 consecutive identical characters. 6 Born2beRoot*
> 
> *Your password has to expire every 30 days.*
> 
> - *The minimum number of days allowed before the modification of a password will be set to 2.*
> - *The user has to receive a warning message 7 days before their password expires.*
> - *The password must not include the name of the user.*
> - *The following rule does not apply to the root password: The password must have at least 7 characters that are not part of the former password.*
> - *Of course, your root password has to comply with this policy.”*

Installing password quality checking library (libpam-pwquality):

```
$ sudo apt-get install libpam-pwquality
```

Change the length

```
$ sudo nano /etc/pam.d/common-password
```

Find the following line:

```
password [success=2 default=ignore] pam_unix.so obscure sha512
```

And add an extra word: minlen=10 at the end.

```
password [success=2 default=ignore] pam_unix.so obscure sha512 minlen=10
```

To set at least one upper-case letter in the password, add a word ‘**ucredit=-1**’ at the end of the following line.

Find this line:

```
password    requisite         pam_pwquality.so retry=3
```

Add these values (min lower-case 1 letter, min upper-case 1 letter, min digit 1, max same letter repetition 3, whether to check if the password contains the user name in some form (enabled if the value is not 0), the minimum number of characters that must be different from the old password=7, enforce_for_root: same policy for root users):

```
password    requisite         pam_pwquality.so retry=3lcredit =-1ucredit=-1 dcredit=-1 maxrepeat=3 usercheck=0 difok=7 enforce_for_root
```

Password expiration:

```
$ sudo nano /etc/login.defs
```

Find this part

```
PASS_MAX_DAYS 9999
PASS_MIN_DAYS 0
PASS_WARN_AGE 7
```

Change it like this:(max 30 days, min number of days(2) allowed before the modification, receive a notification before expiration at least 7 days before)

```bash
PASS_MAX_DAYS 30
PASS_MIN_DAYS 2
PASS_WARN_AGE 7
```

Reboot the change affects:

```bash
$ sudo reboot
```

### ****Configuring sudoers group****

Go to file:

```bash
$ sudo nano /etc/sudoers
```

Add following for authentication using sudo has to be limited to 3 attempts in the event of an incorrect password:

```bash
Defaults     secure_path="..."
Defaults     passwd_tries=3
```

For wrong password warning message, add:

```bash
Defaults     badpass_message="Password is wrong, please try again!"
```

Each action log file has to be saved in the /var/log/sudo/ folder:

(If there is no “/var/log/sudo” folder, create the sudo folder inside of “/var/log”)

```bash
Defaults	logfile="/var/log/sudo/sudo.log"
Defaults	log_input,log_output
```

Require tty: (*Why use tty? If some non-root code is exploited (a PHP script, for example), the `requiretty` option means that the exploit code won't be able to directly upgrade its privileges by running `sudo`.*)

```bash
Defaults        requiretty
```

For security reasons too, the paths that can be used by sudo must be restricted. Example : /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin

(It was already set there)

```bash
Defaultssecure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
```

### **Crontab Configuation**

1. Then type `apt-get install -y net-tools` to install the netstat tools
2. Then type `cd /usr/local/bin/`
3. Then type `touch monitoring.sh`
4. Lastly type `chmod 777 monitoring.sh`

monitoring.sh

```bash
#!/bin/bash
arc=$(uname -a)
pcpu=$(grep "physical id" /proc/cpuinfo | sort | uniq | wc -l)
vcpu=$(grep "^processor" /proc/cpuinfo | wc -l)
fram=$(free -m | awk '$1 == "Mem:" {print $2}')
uram=$(free -m | awk '$1 == "Mem:" {print $3}')
pram=$(free | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')
fdisk=$(df -BG | grep '^/dev/' | grep -v '/boot$' | awk '{ft += $2} END {print ft}')
udisk=$(df -BM | grep '^/dev/' | grep -v '/boot$' | awk '{ut += $3} END {print ut}')
pdisk=$(df -BM | grep '^/dev/' | grep -v '/boot$' | awk '{ut += $3} {ft+= $2} END {printf("%d"), ut/ft*100}')
cpul=$(top -bn1 | grep '^%Cpu' | cut -c 9- | xargs | awk '{printf("%.1f%%"), $1 + $3}')
lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')
lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -eq 0 ]; then echo no; else echo yes; fi)
ctcp=$(ss -neopt state established | wc -l)
ulog=$(users | wc -w)
ip=$(hostname -I)
mac=$(ip link show | grep "ether" | awk '{print $2}')
cmds=$(journalctl _COMM=sudo | grep COMMAND | wc -l)
wall "	#Architecture: $arc
	#CPU physical: $pcpu
	#vCPU: $vcpu
	#Memory Usage: $uram/${fram}MB ($pram%)
	#Disk Usage: $udisk/${fdisk}Gb ($pdisk%)
	#CPU load: $cpul
	#Last boot: $lb
	#LVM use: $lvmu
	#Connections TCP: $ctcp ESTABLISHED
	#User log: $ulog
	#Network: IP $ip ($mac)
	#Sudo: $cmds cmd"
```

1. 
2. Then type `sudo visudo` to open your sudoers file
3. Add in this line `your_username ALL=(ALL) NOPASSWD: /usr/local/bin/monitoring.sh` under where its written %sudo ALL=(ALL:ALL) ALL
4. It should look like this
    
    !https://user-images.githubusercontent.com/58959408/174727595-11dbb2f9-9c34-4d11-870b-f832ea4a9224.png
    
5. Then exit and save your sudoers file
6. Now type `sudo reboot` in your Virtual Machine to reboot sudo
7. Type `sudo /usr/local/bin/monitoring.sh` to execute your script as su (super user)
8. Type `sudo crontab -u root -e` to open the crontab and add the rule
9. Lastly at the end of the crontab, type the following :
    
    `*/10 * * * * /usr/local/bin/monitoring.sh` this means that every 10 mins, this script will show
    

### Linux Lighttpd MariaDB PHP (LLMP) Stack

### Lighttpd

- Install lighttpd: `sudo apt install lighttpd`
- Verify installation: `dpkg -l | grep lighttpd`
- Allow incoming connections using port 80: `sudo ufw allow 80`
- Configure Lighttpd: Enable below modules

```bash
$ sudo lighty-enable-mod fastcgi
$ sudo lighty-enable-mod fastcgi-php
$ sudo service lighttpd force-reload

```

- Check the lighty status: `systemctl status lighttpd.service`
- In case it failed to activate/start use: `sudo apt install --reinstall lighttpd`

### MariaDB

- install mariadb: `sudo apt install mariadb-server`
- verify installation: `dpkg -l | grep mariadb-server`
- start intractive script to remove insecure default settings:

```bash
$ sudo mysql_secure_installation
Enter current password for root (enter for none): #Just press Enter (do not confuse database root with system root)
Set root password? [Y/n] n
Remove anonymous users? [Y/n] Y
Disallow root login remotely? [Y/n] Y
Remove test database and access to it? [Y/n] Y
Reload privilege tables now? [Y/n] Y

```

- Log in to MariaDB console: `sudo mariadb`
- Create new database: `CREATE DATABASE userDB;`
- Create new database user and grant them full privileges on the newly-created database:  `GRANT ALL PRIVILEGES ON userDB.* to 'aajaanan'@'localhost' IDENTIFIED BY 'password';`
- Flush the privileges: `FLUSH PRIVILEGES;`
- Exit MariaDB shell: `exit`
- Verify whether database user was successfully created: `mariadb -u userDB -p` (then enter the password from previous step)
- Confirm whether database user has access to the database: `SHOW DATABASES;`

```bash
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| userDB             |
| information_schema |
+--------------------+

```

- Exit the MariaDB shell: `exit`
- Note: In case you want to remove MariaDB -> https://askubuntu.com/questions/806107/remove-mariadb-mysql-databases/806441#806441

### PHP

- Install: `sudo apt install php-cgi php-mysql php8.2`
- Verify installation: `dpkg -l | grep php`

### WordPress

- Install wget: `sudo apt install wget`
- Download WordPress to `/var/www/html`: `sudo wget http://wordpress.org/latest.tar.gz -P /var/www/html`
- Extract downloaded content: `sudo tar -xzvf /var/www/html/latest.tar.gz`
- Remove tarball: `sudo rm /var/www/html/latest.tar.gz`
- Copy content of `/var/www/html/wordpress` to `/var/www/html`:
- `sudo cp -r /var/www/html/wordpress/* /var/www/html`
- Remove wordpress directory: `sudo rm -rf /var/www/html/wordpress`
- Create WordPress configuration file from its sample:
- `sudo cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php`
- Configure WordPress to reference previously-created MariaDB database & user:
- `sudo vim /var/www/html/wp-config.php`
- Add your prevously created database:

`23 define( 'DB_NAME', 'userDB' );
26 define( 'DB_USER', 'aajaanan' );
29 define( 'DB_PASSWORD', 'password' );`

### Set up NextCloud

install the required dependencies:

- PHP modules: **`sudo apt install php-xml php-mbstring php-curl php-gd php-zip php-intl php-imagick`**
1. go to this path : `cd /var/www/html`
2. Download the Nextcloud package using **`wget`**:
    
    ```bash
    sudo wget https://download.nextcloud.com/server/releases/latest.tar.bz2
    ```
    
3. Extract the downloaded package:
    
    ```bash
    sudo tar -xf latest.tar.bz2
    ```
    
4. Set the correct permissions:
    - Change the ownership of the Nextcloud directory to the web server user:
    - **`sudo chown -R www-data:www-data /var/www/html/nextcloud`**
    - Set the correct file permissions: **`sudo chmod 750 /var/www/html/nextcloud`**
5. Create a database for Nextcloud:
    - Log in to the MariaDB shell: **`sudo mariadb`**
    - Create a new database: **`CREATE DATABASE nextcloud;`**
    - Create a new database user and grant privileges:
        
        ```sql
        GRANT ALL ON nextcloud.* TO 'nextclouduser'@'localhost' IDENTIFIED BY 'password';
        FLUSH PRIVILEGES;
        ```
        
    - Exit the MariaDB shell: **`exit`**
    1.  Configure port forwarding :
        
        Follow these steps to configure port forwarding in VirtualBox:
        
        1. Shut down the Debian virtual machine if it's currently running.
        2. Open VirtualBox and select the Debian virtual machine from the list.
        3. Click on the "Settings" button to open the settings for the virtual machine.
        4. In the settings window, select the "Network" tab.
        5. Under the "Adapter 1" tab, click on the "Port Forwarding" button.
        6. In the Port Forwarding Rules dialog, click on the "+" button to add a new rule.
        7. Enter the following details for the port forwarding rule:
            - Name: Nextcloud
            - Protocol: TCP
            - Host IP: Leave it blank or enter the IP address of your host OS.
            - Host Port: Choose a port number on your host OS (e.g., 8888).
            - Guest IP: Leave it blank.
            - Guest Port: Enter the port on which Nextcloud is running inside the guest OS (e.g., 81).
    2. Update the lighttpd.conf file locates at /etc/lihttpd/lighttpd.conf to be :
        
        ```bash
         server.modules = (
            "mod_access",
            "mod_alias",
            "mod_rewrite",
            "mod_redirect",
        )
        
        server.document-root        = "/var/www/html/nextcloud"
        server.upload-dirs          = ( "/var/cache/lighttpd/uploads" )
        server.errorlog             = "/var/log/lighttpd/error.log"
        server.pid-file             = "/var/run/lighttpd.pid"
        server.username             = "www-data"
        server.groupname            = "www-data"
        server.port                 = 81
        
        index-file.names            = ( "index.php", "index.html" )
        url.access-deny             = ( "~", ".inc" )
        static-file.exclude-extensions = ( ".php", ".pl", ".fcgi" )
        
        include_shell "/usr/share/lighttpd/use-ipv6.pl " + server.port
        include_shell "/usr/share/lighttpd/create-mime.conf.pl"
        include "/etc/lighttpd/conf-enabled/*.conf"
        
        $SERVER["socket"] == ":80" {
        server.document-root = "/var/www/html/"
        }
        ```
        
    
    8. Then execute :
    
    ```bash
    sudo service lighttpd restart
    ```
