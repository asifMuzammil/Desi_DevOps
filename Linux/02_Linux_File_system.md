---

# Desi DevOps — Linux File System

## Linux file system kya hota hai?

Linux file system woh nizaam hai jo files aur folders ko **store, organize aur manage**karta hai.

Simple lafzon mein:

* file = data
* folder = file rakhne ki jagah
* path = us jagah ka address

### Aam zindagi ki misaal

Jaise ek school ya hotel ka poora setup ho:

* main building
* us mein floors
* floors mein rooms
* rooms mein cupboards
* cupboards mein files

Linux bhi isi tarah kaam karta hai.

---

# Linux hierarchical system kya hota hai?

Linux ka file system **hierarchical** hota hai.
Matlab sab cheezen aik **tree structure** mein hoti hain.

Yani:

* sab se upar aik main point hota hai
* us ke neeche folders
* un ke neeche subfolders
* un ke neeche files

Ye bilkul family tree ya school building map ki tarah hota hai.

---

## Root `/`

Linux mein sab kuch `/` se start hota hai.
Isay **root directory** kehte hain.

Ye poore system ka **starting point** hota hai.

### Aam zindagi ki misaal

Jaise kisi shopping mall ka **main gate**.
Andar jitni shops hain, sab usi gate ke baad aati hain.

---

# Tree ko simple tarah samjho

```bash
/
|-- home
|-- etc
|-- var
|-- usr
|-- bin
|-- tmp
|-- dev
|-- proc
|-- boot
|-- root
```

Yani `/` sab se upar hai, aur baqi sab us ke neeche.

---

# Important concept

Linux mein **everything is treated like a file** ka concept bohat common hai.

Matlab:

* normal text files
* folders
* devices
* process info

ye sab file-system style structure mein mil sakte hain.

Isi liye Linux powerful lagta hai.

---

# Absolute aur Relative Path recap

## Absolute path

Poora address jo `/` se start ho.

```bash
/home/ahmed/file.txt
```

## Relative path

Current location se address.

```bash
Documents/file.txt
```

### Aam zindagi ki misaal

* Absolute = poora hotel address + floor + room number
* Relative = “yahan se left wala room”

---

# Common Linux Folders — Complete Intro

Ab important folders ko samjhtay hain.

---

## 1) `/home`

### Kya hota hai?

Ye normal users ka personal area hota hai.
Har user ka apna folder hota hai.

### Example

```bash
/home/ahmed
```

### Is mein kya hota hai?

* personal files
* downloads
* documents
* desktop files

### Aam zindagi ki misaal

Jaise ghar mein har family member ka apna room.

---

## 2) `/root`

### Kya hota hai?

Ye **root user** ka home folder hota hai.
Ye normal `/home` se alag hota hai.

### Important

`root` user admin hota hai.

### Aam zindagi ki misaal

Jaise school principal ka private office.

---

## 3) `/bin`

### Kya hota hai?

Yahan basic important commands hoti hain jo system ko chalane ke liye zaroori hoti hain.

### Examples

* `ls`
* `cp`
* `mv`
* `cat`

### Aam zindagi ki misaal

Jaise garage mein roz use honay wale basic tools:

* wrench
* screwdriver
* hammer

---

## 4) `/sbin`

### Kya hota hai?

Yahan system administration wali commands hoti hain.
Mostly admin ya root use karta hai.

### Aam zindagi ki misaal

Jaise hotel maintenance room ke special tools jo sirf manager use karta hai.

---

## 5) `/etc`

### Kya hota hai?

Ye configuration files ka folder hota hai.
System ki settings zyada tar yahin hoti hain.

### Is mein kya hota hai?

* network config
* users config
* services config

### Aam zindagi ki misaal

Jaise school office ki policy files ya restaurant ki recipe/settings register.

---

## 6) `/var`

### Kya hota hai?

Ye variable data ke liye hota hai, yani aisi cheezen jo bar bar change hoti rehti hain.

### Is mein kya hota hai?

* logs
* cache
* mail
* spool files

### Aam zindagi ki misaal

Jaise hotel reception register jahan entries roz change hoti rehti hain.

---

## 7) `/tmp`

### Kya hota hai?

Temporary files ke liye hota hai.

### Is mein kya hota hai?

* short-term data
* temporary app files

### Aam zindagi ki misaal

Jaise kitchen counter par thori dair ke liye rakha hua saman.

---

## 8) `/usr`

### Kya hota hai?

Ye bohat important folder hai.
Is mein installed software, libraries aur shared files hoti hain.

### Is ke andar aam tor par:

* `/usr/bin`
* `/usr/lib`
* `/usr/share`

### Aam zindagi ki misaal

Jaise school ka main academic block jahan books, teaching material aur common tools rakhe hon.

---

## 9) `/boot`

### Kya hota hai?

System boot honay ke liye jo files chahiye hoti hain woh yahan hoti hain.

### Is mein kya hota hai?

* bootloader files
* kernel files

### Aam zindagi ki misaal

Jaise car ka ignition system — gaari start karne ke liye zaroori.

---

## 10) `/dev`

### Kya hota hai?

Yahan devices ko file ki tarah represent kiya jata hai.

### Examples

* hard drive
* USB
* terminal devices

### Aam zindagi ki misaal

Jaise workshop mein har machine ka ek label aur connection point ho.

---

## 11) `/proc`

### Kya hota hai?

Ye virtual folder hota hai jo running system aur processes ki information show karta hai.

### Is mein kya hota hai?

* process info
* CPU info
* memory info

### Important

Ye normal stored data nahi hota, ye live system info hoti hai.

### Aam zindagi ki misaal

Jaise hospital monitor jo live heartbeat dikhata hai.

---

## 12) `/lib`

### Kya hota hai?

Yahan important libraries hoti hain jo commands aur programs ko chalane ke liye chahiye hoti hain.

### Aam zindagi ki misaal

Jaise car ke andar engine oil ya battery — directly nazar nahi aati, magar un ke bina system nahi chalta.

---

## 13) `/media`

### Kya hota hai?

Removable media ke liye use hota hai.

### Examples

* USB drives
* CD/DVD

### Aam zindagi ki misaal

Jaise school mein guest teacher aaye aur un ka temporary desk allocate ho.

---

## 14) `/mnt`

### Kya hota hai?

Temporary mounting ke liye use hota hai.
Admin yahan manually drives waghera mount kar sakta hai.

### Aam zindagi ki misaal

Jaise temporary parking area.

---

## 15) `/opt`

### Kya hota hai?

Optional ya third-party software yahan install hota hai.

### Aam zindagi ki misaal

Jaise mall mein branded outlet jo main building ka part hai, magar special category mein hai.

---

## 16) `/srv`

### Kya hota hai?

Server-related data ke liye use hota hai.

### Aam zindagi ki misaal

Jaise restaurant ka delivery section jahan service ka actual kaam chal raha ho.

---

# Linux File System ko yaad rakhne ka easy formula

## 3-level soch

### 1. Root `/`

Sab ka starting point

### 2. Main folders

Jaise:

* `/home`
* `/etc`
* `/var`
* `/usr`

### 3. Un ke andar subfolders/files

Actual data, configs, logs, commands

---

# Short map in simple words

* `/` = main gate
* `/home` = users ke rooms
* `/root` = admin ka office
* `/bin` = basic tools
* `/sbin` = admin tools
* `/etc` = settings files
* `/var` = changing data/logs
* `/tmp` = temporary files
* `/usr` = installed software
* `/boot` = startup files
* `/dev` = devices
* `/proc` = live system info
* `/lib` = support libraries
* `/media` = USB waghera
* `/mnt` = temporary mount point
* `/opt` = extra software
* `/srv` = service data

---

# Simple commands to explore file system

## Root dekhna

```bash
ls /
```

## Apna current folder dekhna

```bash
pwd
```

## Home folder jana

```bash
cd /home
```

## Config files dekhna

```bash
ls /etc
```

## Logs wali jagah dekhna

```bash
ls /var
```

## Running process info dekhna

```bash
ls /proc
```

---

# Important note

Har folder ko bina samjhay change ya delete nahi karna chahiye, specially:

* `/etc`
* `/boot`
* `/bin`
* `/root`
* `/proc`

Ye sensitive areas hote hain.

---

# Quick recap

* Linux file system aik **tree structure** hota hai
* Sab kuch `/` root se start hota hai
* Har file/folder ka apna path hota hai
* Har system folder ka apna specific role hota hai
* Linux mein bohat si cheezen file-style structure mein organized hoti hain

---

# One-line definition

**Linux file system aik hierarchical structure hai jahan files aur folders root `/` ke neeche organized hotay hain.**

---
