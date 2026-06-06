# Project Topology

![Project topology](topology.png)

# [Using OpenSSH Legacy algorithm on Ubuntu (Ansible-Control Node)](https://www.openssh.org/legacy.html)

### 1. OPEN /etc/ssh/ssh_config file

```bash
sudo vi /etc/ssh/ssh_config
```

### 2. ADD and SAVE this two lines to the file

```bash
KexAlgorithms diffie-hellman-group1-sha1,curve25519-sha256@libssh.org,ecdh-sha2-nistp256,ecdh-sha2-nistp384,ecdh-sha2-nistp521,diffie-hellman-group-exchange-sha256,diffie-hellman-group14-sha1
HostKeyAlgorithms +ssh-rsa
```

### 3. CHANGE `HashKnownHosts` from "YES" to "NO"

```bash
HashKnownHosts no
```

- With HashKnownHosts yes (Default): The hostnames and IP addresses are encrypted using a one-way SHA-1 hash.

- With HashKnownHosts no: The hostnames and IP addresses are stored in plain, human-readable text.

### Lab Environment & Software Inventory

| Item | Value |
|------|-------|
| Based-OS | Windows 11 Pro |
| Emulator | EVE-NG |
| IOS images | viosl2-adventerprisek9-m.03.2017 |
| Ansible Host | ubuntu-22.04.5 |
| Ansible Version | Ansible community version 10.7.0 |
| Cisco IOS collection version | 11.4.1 |