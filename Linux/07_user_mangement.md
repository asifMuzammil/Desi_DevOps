# Desi DevOps — Linux User Management Notes

Linux mein user management ka matlab hota hai:

* new users banana
* passwords manage karna
* groups banana
* permissions aur ownership control karna
* inactive ya unnecessary users remove karna

### Aam zindagi ki misaal

Jaise school admin:

* naye students add karta hai
* classes assign karta hai
* ID cards manage karta hai
* section change karta hai
* aur jab koi student chala jaye to record remove karta hai

Linux admin bhi users ke sath yehi kaam karta hai.

---

# 1) `useradd`

## Kya karta hai?

New user create karta hai.

## Syntax

```bash
sudo useradd username
```

## Examples

```bash
sudo useradd ali
sudo useradd -m ahmed
sudo useradd -m -s /bin/bash sara
```

### Useful options

* `-m` = home directory banao
* `-s` = shell set karo
* `-u` = custom UID do

---

# 2) `adduser`

## Kya karta hai?

New user interactive tareeqay se create karta hai.

## Syntax

```bash
sudo adduser username
```

## Examples

```bash
sudo adduser bilal
sudo adduser hina
```

### Note

`adduser` beginner-friendly hota hai, kyun ke ye step by step details poochta hai.

---

# 3) `passwd`

## Kya karta hai?

User ka password set ya change karta hai.

## Syntax

```bash
sudo passwd username
```

## Examples

```bash
sudo passwd ali
passwd
sudo passwd -l ali
```

### Useful options

* `-l` = account password lock
* `-u` = password unlock

### Aam zindagi ki misaal

Jaise student ka naya locker code set karna.

---

# 4) `chage`

## Kya karta hai?

Password expiry aur aging policy manage karta hai.

## Syntax

```bash
sudo chage [option] username
```

## Examples

```bash
sudo chage -l ali
sudo chage -M 30 ali
sudo chage -W 5 ali
```

### Useful options

* `-l` = current password policy dekho
* `-M` = max days
* `-W` = warning days
* `-d` = last password change date

### Aam zindagi ki misaal

Jaise ID card ki expiry date set karna.

---

# 5) `usermod`

## Kya karta hai?

Existing user ko modify karta hai.

## Syntax

```bash
sudo usermod [option] username
```

## Examples

```bash
sudo usermod -aG sudo ali
sudo usermod -s /bin/bash ali
sudo usermod -d /home/newali -m ali
```

### Useful options

* `-aG` = group mein add karo
* `-s` = shell change karo
* `-d` = home directory change
* `-m` = home data move bhi karo
* `-l` = username rename

### Aam zindagi ki misaal

Jaise school mein student ka section ya record update karna.

---

# 6) `userdel`

## Kya karta hai?

User ko delete karta hai.

## Syntax

```bash
sudo userdel username
```

## Examples

```bash
sudo userdel ali
sudo userdel -r ali
```

### Useful options

* `-r` = user ki home directory bhi delete karo

### Aam zindagi ki misaal

Jaise school register se student ka naam hata dena.

---

# 7) `groupadd`

## Kya karta hai?

New group banata hai.

## Syntax

```bash
sudo groupadd groupname
```

## Examples

```bash
sudo groupadd developers
sudo groupadd interns
```

### Aam zindagi ki misaal

Jaise school mein naya section banana.

---

# 8) `groupmod`

## Kya karta hai?

Existing group ko modify karta hai.

## Syntax

```bash
sudo groupmod [option] groupname
```

## Example

```bash
sudo groupmod -n devteam developers
```

### Useful option

* `-n` = group ka naam change karo

---

# 9) `groupdel`

## Kya karta hai?

Group delete karta hai.

## Syntax

```bash
sudo groupdel groupname
```

## Example

```bash
sudo groupdel interns
```

---

# 10) `groups`

## Kya karta hai?

Batata hai user kin groups ka member hai.

## Syntax

```bash
groups username
```

## Examples

```bash
groups ali
groups
```

### Aam zindagi ki misaal

Jaise check karna student kaunsa class section aur clubs join kiye hue hain.

---

# 11) `id`

## Kya karta hai?

User ka UID, GID aur groups show karta hai.

## Syntax

```bash
id username
```

## Examples

```bash
id ali
id
```

### Aam zindagi ki misaal

Jaise school ID card details dekhna.

---

# 12) `who`

## Kya karta hai?

System mein abhi kaun login hai, ye dikhata hai.

## Syntax

```bash
who
```

## Example

```bash
who
```

---

# 13) `whoami`

## Kya karta hai?

Batata hai ke current user kaun hai.

## Syntax

```bash
whoami
```

## Example

```bash
whoami
```

---

# 14) `su`

## Kya karta hai?

Dusre user mein switch karta hai, mostly root user mein.

## Syntax

```bash
su - username
```

## Examples

```bash
su - root
su - ali
```

### Aam zindagi ki misaal

Jaise reception desk se manager desk par temporarily shift hona.

---

# 15) `sudo`

## Kya karta hai?

Temporary admin privileges ke sath command run karta hai.

## Syntax

```bash
sudo command
```

## Examples

```bash
sudo apt update
sudo usermod -aG sudo ali
sudo -l
```

### Useful option

* `-l` = sudo permissions check karo

---

# 16) `chown`

## Kya karta hai?

File ya folder ka owner change karta hai.

## Syntax

```bash
sudo chown user file
```

## Examples

```bash
sudo chown ali notes.txt
sudo chown ali:developers project.txt
sudo chown -R ali:developers myfolder
```

### Useful options

* `-R` = recursively sab par apply karo

### Aam zindagi ki misaal

Jaise file ek student se doosre student ke naam transfer karna.

---

# 17) `chgrp`

## Kya karta hai?

File ya folder ka group change karta hai.

## Syntax

```bash
sudo chgrp group file
```

## Examples

```bash
sudo chgrp developers project.txt
sudo chgrp -R developers myfolder
```

### Aam zindagi ki misaal

Jaise class assignment ko ek section se doosre section mein transfer karna.

---

# 18) `chmod`

## Kya karta hai?

File ya folder ki permissions change karta hai.

## Syntax

```bash
chmod permissions file
```

## Examples

```bash
chmod 755 script.sh
chmod 644 notes.txt
chmod +x deploy.sh
```

### Useful forms

* `755` = owner full, others limited
* `644` = owner write, others read
* `+x` = executable banao

### Aam zindagi ki misaal

Jaise kaun copy dekh sakta hai, kaun edit kar sakta hai, ye decide karna.

---

# 19) `gpasswd`

## Kya karta hai?

Group passwords aur group membership manage karta hai.

## Syntax

```bash
sudo gpasswd [option] groupname
```

## Examples

```bash
sudo gpasswd -a ali developers
sudo gpasswd -d ali developers
sudo gpasswd developers
```

### Useful options

* `-a` = user ko group mein add karo
* `-d` = user ko group se remove karo

### Aam zindagi ki misaal

Jaise student ko class mein add ya remove karna.

---

# 20) `newgrp`

## Kya karta hai?

Temporary current group change karta hai.

## Syntax

```bash
newgrp groupname
```

## Example

```bash
newgrp developers
```

---

# 21) `last`

## Kya karta hai?

Previous login history show karta hai.

## Syntax

```bash
last
```

## Example

```bash
last
```

### Aam zindagi ki misaal

Jaise school attendance ka old record dekhna.

---

# 22) `finger`

## Kya karta hai?

User ki basic info show karta hai, agar installed ho.

## Example

```bash
finger ali
```

### Note

Har system mein installed nahi hota.

---

# 23) `/etc/passwd`

## Kya hai?

Ye command nahi, magar important file hai.
System ke users ki basic info yahan hoti hai.

## Example

```bash
cat /etc/passwd
```

---

# 24) `/etc/shadow`

## Kya hai?

Encrypted passwords aur password policy info yahan hoti hai.

## Example

```bash
sudo cat /etc/shadow
```

### Important

Sensitive file hoti hai.

---

# 25) `/etc/group`

## Kya hai?

System groups ki info yahan hoti hai.

## Example

```bash
cat /etc/group
```

---

# User management ke liye bohat important commands shortlist

Agar sirf most important yaad rakhni hon to ye rakh lo:

* `useradd`
* `adduser`
* `passwd`
* `usermod`
* `userdel`
* `groupadd`
* `groupdel`
* `groups`
* `id`
* `sudo`
* `chown`
* `chgrp`
* `chmod`
* `gpasswd`
* `chage`

---

# Quick difference section

## `useradd` vs `adduser`

* `useradd` = low-level
* `adduser` = friendly / interactive

## `userdel` vs `rm`

* `userdel` = user account remove
* `rm` = file remove

## `chown` vs `chmod`

* `chown` = owner change
* `chmod` = permission change

## `chown` vs `chgrp`

* `chown` = owner ya owner:group dono
* `chgrp` = sirf group change

---

# Mini command block

```bash
sudo adduser ali
sudo passwd ali
sudo usermod -aG sudo ali
sudo groupadd developers
sudo gpasswd -a ali developers
sudo chown ali:developers project.txt
sudo chgrp developers shared.txt
chmod 755 script.sh
sudo chage -l ali
sudo userdel -r ali
```

---

# Quick admin workflow example

## New user create karna

```bash
sudo adduser ali
```

## Password set karna

```bash
sudo passwd ali
```

## Group mein add karna

```bash
sudo groupadd developers
sudo usermod -aG developers ali
```

## Sudo dena

```bash
sudo usermod -aG sudo ali
```

## Ownership set karna

```bash
sudo chown ali:developers project.txt
```

---

# One-line definitions

* **`passwd`** = password set/change karta hai
* **`usermod`** = existing user modify karta hai
* **`userdel`** = user delete karta hai
* **`groupadd`** = naya group banata hai
* **`chgrp`** = file ka group change karta hai
* **`gpasswd`** = group membership manage karta hai
* **`chown`** = owner change karta hai
* **`chmod`** = permissions change karta hai

---

# Final note

Linux system admin ke liye user management ka strong hona bohat zaroori hai, kyun ke isi se decide hota hai:

* kaun system use karega
* kaun kya access karega
* kaun admin hoga
* kaun kis group ka member hoga
* kaun si files kis ki hongi

---
