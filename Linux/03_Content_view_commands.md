# Desi DevOps — Content View Commands

Ye commands files ka content **dekhne** ke liye use hoti hain.
Jaise ghar mein fridge ya koi Box khol kar dekhna kya rakha hai, waise Linux mein file khol kar dekhte hain kay file kay andar content kiya hai.

---

# 1) `cat`

## Intro

`cat` file ka poora content terminal par dikha deta hai.
Ye sab se basic aur common command hai content dekhne ke liye.

### Desi touch:

Jaise Ammi ki grocery list uthao aur seedha poori parh lo.

## Basic syntax

```bash
cat file.txt
```

## Example 1

```bash
cat menu.txt
```

Ye `menu.txt` ka sara content dikha dega.

## Example 2

```bash
cat notes.txt
```

Jaise restaurant ka poora order pad aik sath dekhna.

## Example 3: line numbers ke sath

```bash
cat -n file.txt
```

### `-n`

Har line ke sath number show karta hai.

### Desi example:

Jaise Abu bolen:
“List parho, aur line number bhi batao.”

---

# 2) `head`

## Intro

`head` file ki **starting lines** dikhata hai.
Jab poori file nahi, sirf upar ka hissa dekhna ho to `head` use hota hai.

### Desi touch:

Jaise newspaper ki sirf top headlines dekhna.

## Basic syntax

```bash
head file.txt
```

## Example 1

```bash
head report.txt
```

Ye starting ki lines dikhayega.

## Example 2: specific lines

```bash
head -n 5 report.txt
```

### `-n 5`

Sirf first 5 lines show karega.

---

# 3) `tail`

## Intro

`tail` file ki **last lines** dikhata hai.
Ye bohat useful hai jab file ke end mein latest data ya logs dekhne hon.

### Desi touch:

Jaise WhatsApp chat scroll karke seedha last messages dekhna.

## Basic syntax

```bash
tail file.txt
```

## Example 1

```bash
tail log.txt
```

Ye file ki last lines show karega.

## Example 2: specific lines

```bash
tail -n 5 log.txt
```

### `-n 5`

Sirf last 5 lines show karega.

### Desi example:

Jaise hotel register ki bas last 5 entries dekhni hon.

## Example 3: live updates

```bash
tail -f log.txt
```

### `-f`

File ko live monitor karta hai.
Nayi line aati rahe to terminal mein show hoti rehti hai.

### Desi touch:

Jaise kitchen ke bahar kharay ho kar dekhna ke kaunsa naya order nikal raha hai.

---

# 4) `more`

## Intro

`more` file ko **page by page** dikhata hai.
Large file ho to ek screen bhar content dikha kar ruk jata hai.

### Desi touch:

Jaise kitab aik aik safha karke parhna.

## Example 1

```bash
more file.txt
```

## Example 2

```bash
more longfile.txt
```

Space press karo to next page aayega.

---

# 5) `less`

## Intro

`less` bhi large file dekhne ke liye hota hai, lekin `more` se better hai.
Is mein aap aagay bhi ja saktay ho aur peeche bhi.

### Desi touch:

Jaise kitab parhte waqt aagay bhi palto aur peechay bhi.

## Example 1

```bash
less file.txt
```

## Example 2

```bash
less log.txt
```

`q` press karke bahar nikal saktay ho.

---

# Quick difference

* `cat` = poori file aik sath dikhao
* `head` = file ka start dikhao
* `tail` = file ka end dikhao
* `more` = page by page dikhao
* `less` = better page view, aagay peeche dono

---

# Sab se useful yaad rakhne wali baat

## `cat`

Jab file chhoti ho aur poora content dekhna ho.

## `tail`

Jab latest lines ya logs dekhne hon.

---

# One-line definitions

* **`cat`** = file ka poora content show karta hai
* **`head`** = file ki shuru ki lines show karta hai
* **`tail`** = file ki last lines show karta hai
* **`more`** = file page by page show karta hai
* **`less`** = file ko flexible way mein view karta hai

---