# Package Manager kya hota hai?

## Intro

Package manager Linux ka woh tool hota hai jo software ko **install, update, remove aur manage** karta hai.

Simple lafzon mein:

> Linux mein app store jaisa system

### Aam zindagi ki misaal

Jaise restaurant ka store manager:

* naya saman mangwata hai
* purana replace karta hai
* extra saman hata deta hai

Package manager bhi software ke sath yehi karta hai.

---

# Package kya hota hai?

Package asal mein software ka bundle hota hai.
Is mein aam tor par hota hai:

* program files
* dependencies
* config files
* version info

### Aam zindagi ki misaal

Jaise biryani ka poora parcel:

* chawal
* masala
* chicken
* packing

Sab aik sath.

---

# Common Linux Package Managers

Different Linux distros ke apne package managers hotay hain.

## 1. Debian / Ubuntu

### Package manager:

* `apt`

### Example:

```bash
sudo apt update
sudo apt install nginx
```

---

## 2. RHEL / CentOS / Rocky / AlmaLinux

### Package manager:

* `yum`
* `dnf` (newer systems mein zyada common)

### Example:

```bash
sudo dnf install nginx
```

ya

```bash
sudo yum install nginx
```

---

## 3. Arch Linux

### Package manager:

* `pacman`

### Example:

```bash
sudo pacman -S nginx
```

---

## 4. openSUSE

### Package manager:

* `zypper`

### Example:

```bash
sudo zypper install nginx
```

---

# Quick distro map

* **Ubuntu / Debian** → `apt`
* **CentOS / RHEL / Rocky** → `yum` / `dnf`
* **Arch** → `pacman`
* **openSUSE** → `zypper`

---

# Package manager kya kya karta hai?

## 1. Package install karna

```bash
sudo apt install git
```

## 2. Package update karna

```bash
sudo apt update
```

## 3. Installed packages upgrade karna

```bash
sudo apt upgrade
```

## 4. Package remove karna

```bash
sudo apt remove git
```

---

# Important term: Dependency

Dependency woh extra package hota hai jo kisi software ko chalane ke liye chahiye hota hai.

### Aam zindagi ki misaal

Jaise car chalane ke liye:

* petrol
* battery
* engine oil

Sirf steering se gaari nahi chalti.

Package manager dependency bhi automatically install kar deta hai.

---

# 2) `sudo` kya hota hai?

## Intro

`sudo` ka matlab hota hai:

**Super User Do**

Yani normal user ko temporary admin power dena taake woh special command chala sake.

### Aam zindagi ki misaal

Jaise school mein student normally staff room ki almari nahi khol sakta,
magar principal temporary ijazat de de to khol sakta hai.

Linux mein ye temporary admin ijazat `sudo` deti hai.

---

# `sudo` ki zaroorat kyun hoti hai?

Kuch kaam sensitive hotay hain, jaise:

* software install karna
* system update karna
* service restart karna
* config files edit karna
* users manage karna

Ye kaam normal user direct nahi kar sakta.

---

# Basic syntax

```bash
sudo command
```

## Example

```bash
sudo apt install curl
```

Yani:
“Ye command admin authority ke sath chalao.”

---

# Normal user aur root user ka farq

## Normal user

* limited permissions
* safe daily use
* system files direct change nahi kar sakta

## Root user

* full control
* kuch bhi install / delete / modify kar sakta hai

### Aam zindagi ki misaal

* normal user = hotel receptionist
* root = hotel owner

---

# User ko sudo access kaise dete hain?

User ko sudo dene ka matlab hai usay **sudoers policy** mein allow karna.

---

## Method 1: Ubuntu/Debian mein `sudo` group mein add karna

```bash
sudo usermod -aG sudo username
```

## Example

```bash
sudo usermod -aG sudo ahmed
```

### Meaning

* `usermod` = user modify karo
* `-aG` = group mein add karo
* `sudo` = sudo group
* `ahmed` = user name

### Important

Naya group apply karne ke liye user ko logout/login karna parta hai.

---

## Method 2: RHEL/CentOS mein `wheel` group

Bohat si distros mein sudo access `wheel` group se milta hai.

```bash
sudo usermod -aG wheel username
```

## Example

```bash
sudo usermod -aG wheel ahmed
```

---

# Kaise check karein user kis groups mein hai?

```bash
groups username
```

## Example

```bash
groups ahmed
```

ya current user ke liye:

```bash
groups
```

---

# Sudoers file kya hoti hai?

`sudoers` woh policy file hoti hai jo decide karti hai:

* kaun sudo use kar sakta hai
* kis level tak kar sakta hai
* password lagega ya nahi

Usually file hoti hai:

```bash
/etc/sudoers
```

---

# Sudoers file ko edit kaise karte hain?

Direct file edit karna risky hota hai.
Best practice:

```bash
sudo visudo
```

## `visudo` kyun?

Ye file ko safe mode mein open karta hai aur syntax check bhi karta hai.

### Aam zindagi ki misaal

Jaise important school register ko direct pen se nahi, principal ke saamne carefully edit karna.

---

# User ko direct sudo permission kaise den?

`visudo` mein aisi line add ki ja sakti hai:

```bash
ahmed ALL=(ALL:ALL) ALL
```

## Is line ka matlab

* `ahmed` = user
* `ALL` = sab hosts
* `(ALL:ALL)` = sab users aur groups ke taur par command chala sakta hai
* `ALL` = sab commands allowed

Yani user ko full sudo access mil gaya.

---

# Password ke baghair sudo

Agar password ke bina sudo allow karna ho:

```bash
ahmed ALL=(ALL:ALL) NOPASSWD: ALL
```

### Warning

Ye convenient hai, magar security risk ho sakta hai.

---

# Specific command ki permission dena

Agar sirf aik khaas command allow karni ho:

```bash
ahmed ALL=(ALL) /usr/bin/systemctl restart nginx
```

Yani user sirf ye specific command sudo ke sath chala sakta hai.

### Aam zindagi ki misaal

Jaise Ammi kahen:

> “Fridge khol saktay ho, magar freezer nahi”

Yani limited permission.

---

# Sudo access test kaise karein?

```bash
sudo -l
```

Ye show karega ke user ko kaunsi sudo permissions mili hui hain.

---

# Important permission concepts

## 1. Full sudo access

User sab admin commands chala sakta hai.

## 2. Group-based access

User ko `sudo` ya `wheel` group mein add kar dete hain.

## 3. Command-specific access

Sirf selected commands allow ki jati hain.

## 4. Passwordless sudo

Password ke baghair sudo.

---

# Best practice

## Safe method

Zyada tar cases mein user ko group mein add karna best hota hai:

### Ubuntu/Debian

```bash
sudo usermod -aG sudo ahmed
```

### RHEL/CentOS

```bash
sudo usermod -aG wheel ahmed
```

## Advanced method

Agar specific rules chahiye hon to `visudo` use karo.

---

# Quick recap

## Package Manager

Software ko install, update, remove aur manage karta hai.

## Common examples

* Ubuntu/Debian → `apt`
* RHEL/CentOS → `yum`, `dnf`
* Arch → `pacman`
* openSUSE → `zypper`

## `sudo`

Temporary admin rights ke sath command chalata hai.

## User ko sudo dena

* Ubuntu: `sudo` group
* RHEL: `wheel` group
* Advanced: `visudo`

---

# One-line definitions

## Package manager

**Linux ka tool jo software packages ko install, update aur remove karta hai.**

## sudo

**Aisi command jo normal user ko temporary admin permissions ke sath command run karne deti hai.**

## sudoers

**Policy file jo define karti hai ke kaun sudo use kar sakta hai aur kis tarhan.**

---

# Important commands summary

## Ubuntu/Debian

```bash
sudo apt update
sudo apt install nginx
sudo usermod -aG sudo ahmed
```

## RHEL/CentOS

```bash
sudo dnf install nginx
sudo usermod -aG wheel ahmed
```

## Sudo rules check

```bash
sudo -l
```

## Sudoers file edit

```bash
sudo visudo
```

---

Agar chaho to next topic mein main isi style mein **`systemctl`** kar deta hun, kyun ke woh `sudo` ke baad naturally flow banata hai.
