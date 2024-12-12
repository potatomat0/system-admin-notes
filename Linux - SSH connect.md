---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 10
creation date: 2024-12-10 10:30
modification date: Tuesday 10th December 2024 10:30:36
---

#linux #selflearn  
_____

### links & quick notes 
- [OpenSSH - ArchWiki](https://wiki.archlinux.org/title/OpenSSH)
- [[Linux - SSH Cheat Sheet]]
- [How to Find/Get your IP Address in Linux | Linuxize](https://linuxize.com/post/how-to-find-ip-address-linux/)
- config is at: `~/.ssh/config`
- [Git - Generating Your SSH Public Key](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key) 
- [How to Install and Configure OpenSSH on Arch Linux – LinuxWays](https://linuxways.net/arch/install-configure-openssh-arch-linux/)
- [OpenSSH Made Easy: The Ultimate Step-by-Step Tutorial - YouTube](https://www.youtube.com/watch?v=YS5Zh7KExvE&t=2740s) - watch this video now 

## personal notes:

### connect without password

```bash
# suppose we are trying to connect from our machine (nhat@arch) to a machine called Server1 
ssh-keygen
# example:
#	location and file of the public and private keys:
#	~/.ssh/keysForServer1 and ~/.ssh/keysForServer1.pub 
#	password: no
#	re-type password: no

# we have created keysForServer1.pub
# now copy the content of the keyForServer1.pub to the ~/.ssh/authorized_keys of the Server1 machine 
# from now on we only have to type ssh <user>@<ip address> without ever typing password 
# usually we have to create the authorized_keys ourselves, each public keys is contained within a single line and are separated from other keys of other machines 
```
**the faster way**
```bash
# after creating the public and private key like above, simply do this:
ssh-copy-id -i ~/.ssh/keyForServer1.pub <usernameOfServer1>@<ipOfServer1>
```


## config 

the file is at: `~/.ssh/config`
```bash 
# example
Host vietnixServer
	Hostname 14.225.231.69
	Port 22 
	User vtrainnhat 

# you can also have multiple server config with the same syntax above down the file 
#...
#...
```
from now on you only have to: `ssh vietnixServer` to connect 


### trouble shooting 

change the permission for the .ssh and its file:
```bash
chmod 700 ~/.ssh 
chmod 600 ~/.ssh/id_rsa.pub 
chmod 600 ~/.ssh/authorized_keys
```

## other tricks  

```bash
# download ssh
sudo pacman -S openssh-server
# check version 
ssh -v 
# go to config file 
sudo vim /etc/ssh/sshd_config
```

```bash
# check status 
sudo systemctl status sshd  
  
sudo systemctl enable sshd  
  
sudo systemctl start sshd
```

```bash
# get your username: 

whoami 

# get your address IP with the ipv4 format  

ip addr # the ipv4 is the series of numbers next to the 'inet' on the 2. section 

# get a website ip address 

ping example.com

# get a website hostname 

nslookup <IP address>
# or 
dig -x <IP address>
```

```bash
# generate new SSH key pair 

ssh-keygen -t rsa -b 4096

# change the passphrase of an existing key 

ssh-keygen -p
```

## first steps  

your computer needs to be turned on and connected to the internet for you to access it remotely via SSH.


**1. Enable SSH on Your Linux Computer:**

- **Check if SSH is installed:** Open a terminal window and type `ssh -v`
    
    - If it says "OpenSSH_8.8p1, OpenSSL 1.1.1f 31 Mar 2023", SSH is already installed.
    - If not, install it using your package manager (e.g., `sudo apt install openssh-server` on Ubuntu/Debian)
- **Start the SSH service:**
    
    - On most systems, SSH starts automatically. If not, use `sudo systemctl start ssh`

**2. Secure Your SSH Configuration (Optional but Highly Recommended):**

- **Disable root login:** Edit the SSH configuration file (`sudo nano /etc/ssh/sshd_config`) and set `PermitRootLogin no`
- **Enable strong authentication:** Consider using public key authentication instead of passwords. This involves generating a key pair on your local computer and transferring the public key to your Linux computer.  
    
- **Change the default SSH port:** To make it harder for attackers, change the port number in the SSH config file.  
    
- **Other security measures:** Limit login attempts, use strong passwords, and keep your SSH software updated.  
    

**3. Access Your Linux Computer from Another Computer:**

- **On your other computer:**
    
    - Install an SSH client (usually included in most operating systems).
    - Open the SSH client and type: `ssh your_username@your_linux_computer_ip_address`
    - Replace `your_username` with your username on the Linux computer and `your_linux_computer_ip_address` with its IP address.
- **If you set up public key authentication:**
    
    - You'll be prompted to accept a fingerprint. Type `yes` to continue.
    - You'll be logged in without a password!

**Additional Tips:**

- **Find your Linux computer's IP address:**
    - On your Linux computer, open a terminal and type `ifconfig` or `ip addr`
- **Use a password manager:**
    - Store your SSH password securely in a password manager.
- **Consider a VPN:**
    - For an extra layer of security, use a VPN to encrypt your internet connection.

## changing wlan0 or ISP

Changing your Wi-Fi network (wlan0) or Internet Service Provider (ISP) typically won't directly affect the SSH port itself. However, it might impact your ability to access your Linux computer remotely:

**1. IP Address Change:**

- **Dynamic IP:** Most home networks use dynamic IP addresses, which can change when you switch networks or ISPs. This means the IP address you used to access your computer might no longer be valid.  
    
- **Static IP:** If you have a static IP address, it will remain the same, and you can continue to access your computer using the same IP address.  
    

**2. Firewall Rules:**

- **ISP Firewalls:** Some ISPs have firewalls that may block incoming traffic on certain ports, including port 22 (SSH). If your new ISP has such restrictions, you may need to contact them to allow access to the SSH port.
- **Router Firewall:** Your router's firewall settings can also affect incoming traffic. Ensure that your router's firewall is configured to allow incoming connections on the SSH port.

**3. Port Forwarding:**

- If your Linux computer is behind a router (which is common in home networks), you may need to configure port forwarding on your router to direct incoming traffic on port 22 to your computer. This ensures that the SSH traffic reaches your computer even if it has a private IP address.  
    

**To check if your SSH port is accessible:**

1. **Use a port scanner:** You can use online tools or software to scan your IP address and see if port 22 is open.  
    
2. **Try to connect from another device:** Attempt to connect to your Linux computer using the SSH client from another device on the same network or over the internet.

**If you're still unable to access your SSH port after making these checks, consider the following:**

- **Dynamic DNS:** Use a Dynamic DNS service to obtain a fixed domain name that points to your dynamic IP address, making it easier to access your computer remotely.  
    
- **VPN:** Set up a VPN to create a secure tunnel through the internet, bypassing potential firewall restrictions.  
    
- **SSH Tunneling:** Use SSH tunneling to create a secure connection to your computer, allowing you to access other services running on it.