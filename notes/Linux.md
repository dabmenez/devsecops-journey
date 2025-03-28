# 🐧 Linux Course Notes

## 🔐 File Permissions

Linux uses a permission system to control access to files and directories. Each file or directory has:
- **Type**: `d` for directory, `-` for file, `l` for symbolic link, etc.
- **Owner permissions**: read (r), write (w), execute (x)
- **Group permissions**: read (r), write (w), execute (x)
- **Others (Public) permissions**: read (r), write (w), execute (x)

Example:
```
drwxr-xr-x
```
- `d`: directory
- `rwx`: owner can read, write, execute
- `r-x`: group can read and execute
- `r-x`: others can read and execute

## 🔧 Changing Permissions

Use the `chmod` command:
```bash
chmod 777 filename
```

Permission values:
- Read (r) = 4 📖
- Write (w) = 2 ✏️
- Execute (x) = 1 🚀

Example: `rwxrwxrwx` = 777

## 👥 Changing Ownership

Use the `chown` command:
```bash
chown owner:group filename
chown ubuntu:ubuntu tmp
```

## 📁 Important System Files

### 📄 /etc/passwd

Contains user account information:
```
username:x:userid:groupid:info:homedir:shell
```

### 🔒 /etc/shadow

Contains password hashes and policies:
```
username:encrypted-password:last-change:min-age:max-age:warn:inactive:expire:
```

Password hash format:
```
$id$salt$hash
$1$ = MD5
$2a$, $2y$ = Blowfish
$5$ = SHA-256
$6$ = SHA-512
```

Configured with PAM in:
```
/etc/pam.d/common-password
```

### 👨‍👩‍👧 /etc/group

Contains group information:
```
groupname:password:groupid:groupmembers
```

## 🔐 sudo

- Allows users/groups to escalate privileges.
- Maintains accountability and enables access segregation.
- Avoids the need for shared root accounts.

### ⚙️ /etc/sudoers

View with:
```bash
cat /etc/sudoers
```

Edit safely with:
```bash
visudo
```

Add a user to sudo group:
```bash
sudo usermod -aG sudo username
```

## 🚀 Privilege Escalation

Gaining elevated privileges from a low-privilege account.

Common techniques:
- Kernel exploits
- Service misconfigurations
- Weak/plaintext passwords
- World writable files/scripts
- Cron job misconfigurations

Popular enumeration tools:
- LinEnum
- linPEAS
- unix-privesc-check
- linprivchecker

## 📦 apt / apt-get

Package managers used in Debian-based systems.

### 🖐️ apt (manual usage) / apt-get (scripted usage)

Commands:
```bash
apt update           # Update package lists
apt upgrade          # Upgrade all packages
apt dist-upgrade     # Handle dependencies
apt install pkg      # Install a package
apt remove pkg       # Remove a package
apt autoremove       # Clean unused packages
apt autoclean        # Clean cache
```

### 🔄 Alternatives:
- `yum` for RHEL/CentOS
- `apk` for Alpine

## 🔄 Automatic Updates

Use `unattended-upgrades` on Ubuntu to automate security updates.

## 🔐 SSH

### ℹ️ Overview

- Stands for **Secure Shell**
- Enables secure remote shell access
- Default port: TCP 22
- Used for tunneling, forwarding, SCP, SFTP

### 🛠️ Tools

- Server: OpenSSH, others
- Clients: SSH, PuTTY

### 🧑‍💻 Usage

```bash
ssh username@hostname
```

### 🛡️ Security Best Practices

- Use SSHv2
- Prefer key-based auth (ED25519 recommended)
- Enable MFA
- Restrict port 22 to IP ranges
- Harden configs (ciphers, MACs, algorithms)
- Disable root login
- Use brute-force protection (e.g., fail2ban)
- Do not confuse with telnet
- Follow Mozilla recommendations

## 🧰 Useful Commands

- `cat`: concatenate and display file contents
- `grep`: search text using patterns
- `man`: display manual pages
- Choose your shell (bash recommended) and get comfortable using it day-to-day
- Leverage command-line expertise to automate tasks via scripting