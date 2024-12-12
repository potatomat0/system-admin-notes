---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 25
creation date: 2024-03-25 00:02
modification date: Monday 25th March 2024 00:02:26
---

#internetContent  #computerScience/computerBasic 
## Article link:
[What is SSH? SSH Meaning in Linux](https://www.freecodecamp.org/news/ssh-meaning-in-linux/)
related notes: 
- [[Linux - SSl, TLS and HTTPS]]
_____
## Content


Secure Shell (SSH) is a widely used network protocol that provides a secure way to access remote servers and computers.

In Linux, SSH is an essential tool for remote administration and file transfer. In this article, we will go over the meaning of SSH in Linux, its history, features, configuration, and use cases.

## What is SSH?

SSH is a cryptographic network protocol that allows secure communication between networked devices. It was developed as a replacement for [Telnet](https://en.wikipedia.org/wiki/Telnet), which sends all data, including passwords, in clear text, making it susceptible to eavesdropping and interception.

SSH provides encryption and authentication mechanisms to protect the confidentiality and integrity of network communications.

## Brief History of SSH

The first version of SSH, SSH-1, was developed by [Tatu Ylönen in 1995](https://www.usenix.org/conference/lisa13/speaker-or-organizer/tatu-yl%C3%B6nen-ssh-communications-security) as a response to the insecurity of Telnet and FTP.

In 1996, SSH Communications Security released a commercial version of SSH-1, which became widely used in the industry.

But SSH-1 had some security vulnerabilities, and in 1998, Ylönen developed SSH-2, which addressed these issues and became the most widely used version of SSH.

## How SSH Works

SSH uses a client-server architecture, where the client initiates a connection to the server and requests a secure communication channel. The server responds by generating a pair of cryptographic keys, one public and one private.

The public key is sent to the client, while the private key is kept securely on the server. The client then encrypts a random session key using the server's public key and sends it back to the server. The server decrypts the session key using its private key and sends an acknowledgement to the client. From this point on, all data transmitted between the client and server is encrypted using the session key.

## SSH Features

- **Encryption**: SSH uses strong encryption algorithms, such as AES, to protect the confidentiality and integrity of data transmitted over the network.
- **Secure file transfer**: It provides secure file transfer (SFTP) capabilities, which allow users to transfer files between remote servers securely.
- **Remote login**: SSH provides a secure way to login to remote servers and computers, without exposing login credentials to attackers.
- **Port forwarding**: It provides port forwarding capabilities, which allow users to access restricted services on remote servers through a secure communication channel.
- **X11 forwarding**: SSH provides X11 forwarding capabilities, which allow users to run graphical applications remotely, without having to install them locally.
- **Agent forwarding**: It also provides agent forwarding capabilities, which allow users to use SSH keys for authentication on remote servers, without having to enter their password every time.

## SSH Configuration

SSH configuration involves various settings and options that can be customized to optimize the SSH connection and improve security. Here are some common SSH configuration tasks:

- **Generating SSH keys**: Before using SSH, users must generate a pair of cryptographic keys, one public and one private. The public key is shared with the server, while the private key is kept securely on the user's computer.
- **Editing configuration files**: Users can create and edit SSH configuration files to customize their SSH settings, such as specifying the preferred encryption algorithm or setting up port forwarding. The SSH configuration files are usually located in the `/etc/ssh/` directory.
- **Authentication methods**: SSH supports various authentication methods, such as password authentication, public key authentication, and multi-factor authentication. Users can choose the most suitable authentication method based on their security needs.
- **Secure SSH configuration**: To ensure maximum security, users should follow best practices for secure SSH configuration, such as disabling root login, enforcing strong passwords, and limiting the number of failed login attempts. Users can also use tools like Fail2Ban to prevent brute-force attacks on SSH.
- **Enabling X11 forwarding**: SSH provides X11 forwarding capabilities, which allow users to run graphical applications remotely, without having to install them locally. To enable X11 forwarding, users can add the -X or -Y flag when connecting to the remote server.
- **Port forwarding**: SSH allows users to set up port forwarding, which can be useful for accessing restricted services on remote servers through a secure communication channel. Users can set up local or remote port forwarding, depending on their needs.
- **Compression**: SSH supports data compression, which can improve the performance of the SSH connection, especially when transferring large files or running resource-intensive applications. Users can enable compression by adding the `-C` flag when connecting to the remote server.

## SSH Examples 

- **Remote server administration**: SSH is commonly used for remote server administration, allowing users to execute commands and manage servers from a remote location.
- **Secure file transfer**: provides a secure way to transfer files between remote servers, without exposing the files or login credentials to attackers.
- **Running graphical applications remotely**: allows users to run graphical applications remotely, without having to install them locally, which can be useful for resource-intensive applications or when using a low-power device.
- **Port forwarding for accessing restricted services**: allows users to access restricted services on remote servers through a secure communication channel, by setting up port forwarding.
- **Tunneling for secure communication**: SSH allows users to set up encrypted tunnels for secure communication between two networked devices, which can be useful for accessing resources on a private network.

## actual use case 

Here are some commands assuming the person is new to SSH and you want to share your `dotfiles` folder on another machine:

### **Preparation:**

1. **Generate SSH key pair (on local machine):**
    
    - Open your terminal and type: `ssh-keygen`
    - Press Enter to accept the default file location (`~/.ssh/id_rsa`).
    - Optionally, enter a secure passphrase for additional security (twice when prompted).
2. **Copy the public key (local machine):**
    
    - Use this command to display the public key: `cat ~/.ssh/id_rsa.pub`
    - Copy the entire output. You'll need this on the other machine.

**Sharing the project folder (local machine):**

### **Method 1: Using password authentication (less secure):**

1. **Establish SSH connection:**
    
    - Replace `username` with the actual username on the remote machine and `remote_machine_address` with its IP address or hostname:
        
        Bash
        
        ```
        ssh username@remote_machine_address
        ```
        
    - When prompted, enter the password for the `username` on the remote machine.
2. **Create the destination folder (on remote machine):**
    
    - Type: `mkdir remote_dotfiles` (replace `remote_dotfiles` with your desired folder name on the remote machine).
3. **Copy the project folder (local machine):**
    
    - Replace `~/personal/dotfiles` with your actual project folder path:
        
        Bash
        
        ```
        scp -r ~/personal/dotfiles username@remote_machine_address:remote_dotfiles
        ```

### **Method 2: Using SSH key authentication (more secure):**

1. **Copy the public key to remote machine:**
    
    - Paste the copied public key (from step 2.1 in Preparation) into a terminal window on the remote machine.
    - **On the remote machine:**
    - Create the directory to store your SSH key: `mkdir ~/.ssh` (if it doesn't exist).
    - Use a text editor (like `nano`) to create a file named `authorized_keys` inside the `~/.ssh` folder: `nano ~/.ssh/authorized_keys`
    - Paste the copied public key into the file and save it (Ctrl+O, then Enter, then Ctrl+X).
    - Set permissions for the `authorized_keys` file: `chmod 600 ~/.ssh/authorized_keys`
2. **Establish SSH connection (without password):**
    
    - Use the same command as in Method 1.1, but you won't be prompted for a password this time.
3. **Create the destination folder (on remote machine) - Same as Method 1.2**
    
4. **Copy the project folder (local machine) - Same as Method 1.3**
    

**Important Notes:**

- These are basic commands for getting started.
- Be cautious when sharing your SSH key, especially the private key file (`id_rsa`).
- Consider using a version control system like Git for more robust project management.
- For further details and security best practices, refer to SSH documentation [https://man7.org/linux/man-pages/man1/ssh.1.html](https://man7.org/linux/man-pages/man1/ssh.1.html).
___

## Remote action between machines

### **1. Remote Command Execution:**

- **Example:** Imagine you forgot to start a web server on Machine B. You can connect to it via SSH and execute the start-up command directly:

Bash

```
ssh username@machine_b_address "service apache2 start"  # Replace username and address
```


This command uses SSH to connect to Machine B as the user "username" and then executes the quoted command (`service apache2 start`) on the remote machine.

### **2. Server Management:**

- **Example:** You can manage and install packages on Machine B remotely. Let's say you need to install a new Node.js version:

Bash

```
ssh username@machine_b_address "sudo apt update && sudo apt install nodejs"  # Replace username and address (assuming Debian/Ubuntu)
```

This command updates package lists, then installs Node.js using the `sudo` command for administrator privileges (enter your password on Machine B when prompted).

### **3. Secure Tunneling:**

- **Example:** You can create a secure tunnel to access a web service running on Machine B from your local machine. Imagine a local development server on Machine B at port 8080. You can create a tunnel to access it on your local machine's port 3000:

Bash

```
ssh -L 3000:localhost:8080 username@machine_b_address  # Replace username and address
```

This command creates a tunnel where traffic on your local port 3000 gets securely forwarded to port 8080 on Machine B. Now, you can access the web service by going to `http://localhost:3000` in your local browser.


## File transfering 

having the SSH port running alone doesn't enable real-time file transfer and modification. SSH provides a secure connection for remote access, but it's not designed for constant, two-way file synchronization.

Here's why:

- **Focus of SSH:** SSH primarily focuses on establishing a secure shell session. This allows you to execute commands on the remote machine and see the output in real-time.
- **File Transfer Protocols:** File transfer over SSH usually involves separate protocols like SCP (Secure Copy) or SFTP (SSH File Transfer Protocol). These protocols initiate file transfers on demand, not continuously.

However, there are tools for real-time file synchronization, but they often work on top of SSH connections:

- **Real-time sync tools:** Tools like rsync (remote sync) can be configured to monitor folders and automatically transfer changes in near real-time. These tools establish an SSH connection, then use their own logic for detecting and transferring changes.

**Here's a breakdown of the functionalities:**

- **SSH Port:** Open for secure communication.
- **SCP/SFTP:** Initiate file transfer sessions when needed.
- **Real-time sync tools:** Utilize SSH connection and monitor folders for changes, triggering transfers for near real-time synchronization.

If you need real-time file collaboration, consider cloud-based solutions like Dropbox or Google Drive that offer continuous synchronization features.

### Example 

a file named `foo.md` has just been created on the remote machine.

`foo.md` would **not automatically appear on the host machine** simply by having SSH enabled. There are two main scenarios for getting `foo.md` from the client to the host machine:

1. **Manual Transfer:** You would need to use a separate file transfer protocol like SCP or SFTP to manually copy the file from the client to the host. Here's an example using SCP:
    
    Bash
    
    ```
    # On the client machine:
    scp ~/foo.md username@host_machine_address:/desired/location/on/host
    ```
    
    Use code [with caution.](https://gemini.google.com/faq#coding)
    
    content_copy
    
    Replace `username` with the actual username on the host, `host_machine_address` with its IP address or hostname, and `/desired/location/on/host` with the directory path where you want the file to be copied on the host machine.