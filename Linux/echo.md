# **Desi DevOps**


# `echo` command

### `echo` hota kya hai?

Simple lafzon mein, **`echo` ka kaam hota hai koi bhi text ya value screen par print karna**.

Matlab Linux ko bolo:

> “Bhai ye line dikhao”

aur Linux foran woh line terminal par dikha deta hai.

---

## Real life desi example

Socho aap restaurant mein waiter ko bolte ho:

> “Table no 5 par bolo: Biryani ready hai”

Waiter ja kar woh message loudly bol deta hai.

Linux mein `echo` bhi bilkul waiter ki tarah hai.
Jo text aap doge, woh screen par bol dega.

---

## Basic syntax

```bash
echo Hello
```

### Output:

```bash
Hello
```

Yani Linux ne bas wohi cheez repeat kar di jo aap ne boli.

---

## Example 1: Normal text print karna

```bash
echo Assalamualaikum Desi DevOps
```

### Output:

```bash
Assalamualaikum Desi DevOps
```

---

## Example 2: Quotes ke sath

```bash
echo "Aaj hum Linux seekh rahay hain"
```

### Output:

```bash
 Aaj hum Linux seekh rahay hain
```


Quotes lagana best practice hai, specially jab sentence lamba ho ya Space dana ho words ka darmiyan.

Isko aise samjho:

Car par sticker lagaya hua ho:

> “Papa ki pari nahi, DevOps ka khiladi”

Sticker poora ek message hai, is liye quotes useful hotay hain.

---


## Example 3: Variables ke sath `echo`

Linux mein hum variable bhi bana saktay hain:

```bash
name="Ahmed"  # Variable Created 
echo $name
```

### Output:

```bash
Ahmed
```

Yahan `name` aik dabba hai, aur us dabbe ke andar value hai `Ahmed`.

### Fridge example:

Socho fridge mein ek box rakha hai jis par label laga hai:

> `juice`

Andar actual mein Mango Juice hai.

Jab aap `echo $name` likhtay ho, to Linux kehta hai:

> “Theek hai, dabba nahi, andar wali cheez dikhata hun”

---

## Example 5: Sentence ke andar variable

```bash
name="Ahmed"
echo "Mera naam $name hai"
```

### Output:

```bash
Mera naam Ahmed hai
```

---

## Example 6: Special characters bhi print hotay hain

```bash
echo "Rs. 5000"
echo "@desidevops"
echo "Car number: KHI-1234"
```

### Output:

```bash
Rs. 5000
@desidevops
Car number: KHI-1234
```

Matlab `echo` simple announcer hai.
Jo do gay, woh dikha dega.

---

## Example 7: File ke andar text bhejna

```bash
echo "Hello Desi DevOps" > file.txt
```

Ye screen par print nahi karega, balkay `file.txt` ke andar likh dega.

### Real life example:

Socho Ammi ne kaha:

> “Ye baat sab ko mat bolo, diary mein likh do”

To aap ne diary mein note kar li.

Yahan:

* `echo` = baat likh raha hai
* `>` = screen ki jagah file mein bhej raha hai
* `file.txt` = diary

---

## Example 8: File mein aur text add karna

```bash
echo "Second line" >> file.txt
```

Ye purani file ko overwrite nahi karega, bas new line add karega.

### Restaurant example:

Socho order pad par pehle likha hua hai:

* 1 Biryani

Ab new order aya:

* 1 Cold Drink

To purana nahi mita rahe, bas neeche add kar rahe ho.

`>>` ka yehi kaam hai.

---

## Example 9: Escape characters ke sath

Kabhi kabhi humein new line ya tab space chahiye hota hai:

```bash
echo -e "Tea\nCoffee\nJuice"
```

### Output:

```bash
Tea
Coffee
Juice
```

### Samjho:

Jaise hotel menu ko aik hi line mein nahi likhte:

* Tea
* Coffee
* Juice

alag alag line mein likhte ho.

Yahan:

* `-e` Linux ko bolta hai: “special cheezon ko samajh”
* `\n` ka matlab: new line

---

## Example 10: Tab spacing

```bash
echo -e "Name\tAge\tCity"
```

### Output:

```bash
Name    Age    City
```

Ye bilkul school register ya restaurant bill ki tarah aligned data dikhata hai.

---

# Common use cases of `echo`

## 1. Testing

```bash
echo "Script chal rahi hai"
```

Jab script banate ho to check karte ho ke kahan tak pohanchi hai.

## 2. Variables check karna

```bash
echo $USER
echo $HOME
```

## 3. File mein content likhna

```bash
echo "Backup complete" > log.txt
```

## 4. Fancy output

```bash
echo "Welcome to Desi DevOps"
```

---

# Ek choti si warning

Agar aap ye likho:

```bash
echo "Hello" > file.txt
```

to file ka purana content ura sakta hai.

Lekin agar likho:

```bash
echo "Hello" >> file.txt
```

to content add hoga, delete nahi hoga.

### Car service example:

* `>` = purana oil nikaal ke naya daal diya
* `>>` = tank mein aur petrol add kar diya
