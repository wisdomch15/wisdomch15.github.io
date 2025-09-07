# Password Hashing & Cracking 

##  TOOLS USED
- Kali Linux
- Hashcat
- Wordlists

##  INTRODUCTION
In this lab, I explored how password hashing and cracking works using Hashcat   
The objective was to:
- Generate hashes using weak and strong passwords (MD5, SHA-256).
- Attempt to crack them using dictionary attacks
- Compare the resilience of weak vs strong passwords.

## STEPS 

### Step 1: 
I created a working directory for the lab:

```bash
cd ~
mkdir hashlab && cd hashlab
```

I also created a password list with both weak and strong passwords:

```bash
cat > passwords.txt <<'EOF'
123456
password
letmein
password123
P@ssw0rd!
S3cureP@55w0rd2025!
correcthorsebatterystaple
EOF
```


### Step 2: 
I generated the hashes.

#### MD5 Hashes
```bash
while read -r pw; do
  echo -n "$pw" | md5sum | awk '{print $1}'
done < passwords.txt > hashes_md5.txt
```

#### SHA-256 Hashes
```bash
while read -r pw; do
  echo -n "$pw" | sha256sum | awk '{print $1}'
done < passwords.txt > hashes_sha256.txt
```


### Step 3: 
I cracked the hashes with hashcat.

#### MD5 Example
```bash
hashcat -m 0 -a 0 hashes_md5.txt /usr/share/wordlists/rockyou.txt
hashcat --show -m 0 hashes_md5.txt
```

#### SHA-256 Example
```bash
hashcat -m 1400 -a 0 hashes_sha256.txt /usr/share/wordlists/rockyou.txt
hashcat --show -m 1400 hashes_sha256.txt
```


## 📸 Step 4: Screenshots

(Add screenshots here showing successful cracks and failed attempts)

Example:
- Screenshot 1: Hashcat cracking weak MD5 password.
- Screenshot 2: John the Ripper cracking SHA-256 weak password.
- Screenshot 3: Attempt on strong password showing "Exhausted" (not cracked).


## FINDINGS

- Weak passwords (`123456`, `password`, `letmein`, `password123`) were cracked easily using `rockyou.txt`.  
- Strong passwords (`S3cureP@55w0rd2025!`, `correcthorsebatterystaple`) resisted cracking within reasonable time.  
- MD5 is very fast and easily brute-forced while SHA-256 is stronger but still crackable with weak inputs if unsalted.
- The best defense is to use long, complex and unique passwords and store them with slow, salted hashing algorithms (e.g., bcrypt, Argon2).

## CONCLUSION

Weak passwords were cracked instantly with a dictionary attack, while strong ones resisted both dictionary and brute-force attempts. MD5 and SHA-256 without salting are insecure for password storage. Strong, unique passwords combined with modern hashing algorithms (bcrypt, Argon2) provide far better security.
