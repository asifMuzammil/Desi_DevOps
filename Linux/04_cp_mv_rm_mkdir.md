# Desi DevOps — Path & Basic File Commands

## Path kya hota hai?

Path ka matlab hota hai **file ya folder ka address**.

### Asaan misaal:

Jaise hotel mein room number, school mein class number, ya Building mein flat Numbers hotay hain — har cheez ki location hoti hai.
Linux mein us location ko **path** kehte hain.

---

# 1) Absolute Path

## Kya hota hai?

Absolute path wo hota hai jo **root `/` se start** hota hai.
Ye poora exact address hota hai.

## Example

```bash
/home/aadil/Documents/file.txt
```

### Example:

Jaise poora address:

> Karachi > Gulshan > School > 1st floor > Class 5

Yani full location.

---

# 2) Relative Path

## Kya hota hai?

Relative path wo hota hai jo **current location** ke hisaab se hota hai.
Ye poora address nahi, bas yahan se aagay ka rasta hota hai.

## Example

```bash
Documents/file.txt
```

ya

```bash
file.txt
```

### Example:

Jaise Ammi kahen:

> “Fridge se juice le aao”

Ghar ke andar ho, is liye full address ki zaroorat nahi.

---

# Quick difference

* **Absolute path** = poora address
* **Relative path** = current jagah se address

---

# `pwd`

## Kya karta hai?

`pwd` batata hai ke aap **abhi kis folder mein kharay ho**.

### Asaan misaal:

Jaise school mein poochna:

> “Main abhi kis class ke bahar khara hun?”

## Example

```bash
pwd
```

---

# `cp`

## Kya karta hai?

`cp` ka matlab **copy**.
Ye file ya folder ki duplicate copy banata hai.

### Asaan misaal:

Jaise teacher worksheet ki photocopy nikalwa dein.

## Syntax

```bash
cp source destination
```

## Example 1

```bash
cp notes.txt backup.txt
```

## Example 2

```bash
cp bill.txt /home/aadil/Documents/
```

### Useful option: `-r`

Folder ko copy karne ke liye

```bash
cp -r projects backup_projects
```

### Example:

Jaise poori restaurant file almari se nikal kar doosri almari mein same copy rakh dena.

---

# `mv`

## Kya karta hai?

`mv` ka matlab **move**.
Ye file ko ek jagah se doosri jagah le jata hai, ya rename bhi karta hai.

### Asaan misaal:

Jaise Abu car ko office se ghar mein le aayen.

## Syntax

```bash
mv source destination
```

## Example 1: move

```bash
mv file.txt /home/aadil/Desktop/
```

## Example 2: rename

```bash
mv oldname.txt newname.txt
```

### Example:

Jaise hotel mein room change kar dena, ya student ka naam register mein update kar dena.

---

# `rm`

## Be Careful Jab bhi **` rm `** command ko use karin khas kar kay -f ka option ya appka saray system ko remove kar sakta hai !

## Kya karta hai?

`rm` file ko delete karta hai.

### Asaan misaal:

Jaise purani grocery slip phenk dena.

## Syntax

```bash
rm file.txt
```

## Example 1

```bash
rm notes.txt
```

## Example 2: folder delete

```bash
rm -r old_folder
```

### Useful option: `-r`

Folder aur us ke andar ka content delete karta hai.

### Useful option: `-f`

Force delete

```bash
rm -f file.txt
```

### Example:

Jaise fridge se expired cheez nikal kar seedha dustbin mein phenk dena.

---

# `mkdir`

## Kya karta hai?

`mkdir` naya folder banata hai.

### Asaan misaal:

Jaise school mein nayi class ya restaurant mein naya storage rack banana.

## Syntax

```bash
mkdir foldername
```

## Example 1

```bash
mkdir projects
```

## Example 2

```bash
mkdir notes
```

### Useful option: `-p`

Nested folders banata hai

```bash
mkdir -p work/design/logo
```

### Example:

Jaise almari ke andar chhota box, us ke andar aur box banana.

---

# `rmdir`

## Kya karta hai?

`rmdir` **empty folder** delete karta hai.

### Asaan misaal:

Jaise khali dabba hata dena.

## Syntax

```bash
rmdir foldername
```

## Example 1

```bash
rmdir oldnotes
```

## Example 2

```bash
rmdir temp
```

### Important:

Agar folder ke andar content hoga, `rmdir` kaam nahi karega.

### Example:

Jaise Ammi kahen:

> “Khali jar hata do”

Agar jar ke andar achar hai, pehle woh nikalna parega.

---

# Quick recap

* `pwd` = main abhi kahan hun
* `cp` = copy banao
* `mv` = move ya rename karo
* `rm` = file delete karo
* `mkdir` = naya folder banao
* `rmdir` = khali folder delete karo

---

# One-line definitions

* **Path** = file/folder ka address
* **Absolute path** = poora address
* **Relative path** = current jagah se address
* **`pwd`** = current folder batata hai
* **`cp`** = copy banata hai
* **`mv`** = move ya rename karta hai
* **`rm`** = file/folder delete karta hai
* **`mkdir`** = folder banata hai
* **`rmdir`** = empty folder delete karta hai

---