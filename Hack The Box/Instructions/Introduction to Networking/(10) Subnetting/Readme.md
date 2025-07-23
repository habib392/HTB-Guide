## 1. **Subnetting kya hai?**

**Seedhi baat:**
Subnetting ka matlab hota hai **aik bade network ko chhote chhote tukro mein divide karna**.
Ye is liye kiya jata hai taake:

* Har department ya group ko alag IP range mil jaye
* Network secure aur manageable ho jaye
* IPs waste na ho

**Example:**
192.168.1.0/24 = 256 IPs
Agar humein sirf 50, 30, 20 walay groups bananay hain to hum isay 3 subnet mein divide karenge (jaise /26, /27, /28)

---

## 2. **Network IP Address kya hota hai?**

**Seedhi baat:**
Ye **aik subnet ka pehla IP** hota hai jo network ko represent karta hai.
**Is IP ko kisi device ko assign nahi karte.**

**Example:**
192.168.1.0/24
→ Yahan `192.168.1.0` hai **network address**

---

## 3. **Broadcast IP Address kya hota hai?**

**Seedhi baat:**
Ye **aik subnet ka aakhri IP** hota hai, jo **sab devices ko ek sath message bhejnay** ke liye use hota hai.

**Is IP ko bhi kisi device ko assign nahi karte.**

**Example:**
192.168.1.0/24 → Broadcast = `192.168.1.255`

---

## 4. **Host IPs kya hoti hain?**

**Seedhi baat:**
Ye **wo IPs hoti hain jo devices ko di jati hain** — jaise PC, mobile, server etc.

**Inka range hota hai:**
(Network+1) se (Broadcast–1) tak

**Example:**
192.168.1.0/24
→ Host IPs = `192.168.1.1` to `192.168.1.254`

---

## 5. **CIDR kya hai?**

**Seedhi baat:**
CIDR ka matlab hota hai **Classless Inter-Domain Routing**
Ye IP ke sath **slash / ke baad value** hoti hai jo batati hai **kitne bits network ke liye reserve hain**

**Example:**
192.168.1.0/24 → Yani pehle 24 bits network ke liye
Baaki (32–24=) **8 bits host** ke liye

---

## 6. **/24, /27, /28 ka kya matlab hai?**

Ye **CIDR Notation** hai jiska matlab hai:

| CIDR | Host Bits | Total IPs | Assignable Hosts | Subnet Mask     |
| ---- | --------- | --------- | ---------------- | --------------- |
| /24  | 8         | 256       | 254              | 255.255.255.0   |
| /27  | 5         | 32        | 30               | 255.255.255.224 |
| /28  | 4         | 16        | 14               | 255.255.255.240 |

**Formula:**

* Total IPs = 2^HostBits
* Assignable Hosts = Total – 2 (network + broadcast)

---

## 7. **Subnetting ghalat kaise hoti hai?**

**Galtiyan:**

* Agar kisi group ko chhoti range wali subnet de di (e.g. 50 devices hain aur /28 de diya jisme sirf 14 hosts bante hain)
* IPs overlap karwa dena (e.g. ek hi IP do subnets ko de dena)
* Incorrect subnet mask assign karna

**Penetration testing point:**
Agar subnetting ghalat ho to attacker ko **IP conflicts, unauthenticated access**, ya **network scanning** ka faida milta hai. Wo dosray subnet mein ghus sakta hai.

---

### 🔸 **Private IP kya hai?**

Local use ke liye IPs — internet par directly access nahi hoti.
Examples:

* 10.0.0.0/8
* 172.16.0.0/12
* 192.168.0.0/16

### 🔸 **Public IP kya hai?**

Internet par access hoti hai — server, website, etc.

### 🔸 **Subnet Mask kya hai?**

Batata hai ke IP ka kitna hissa network ka hai aur kitna host ka
Example:
/24 = 255.255.255.0
/27 = 255.255.255.224

### 🔸 **IP classes kya hain?**

Old system tha:

* Class A: /8 (up to 16M hosts)
* Class B: /16 (up to 65K hosts)
* Class C: /24 (up to 254 hosts)

Lekin ab mostly **CIDR** hi use hota hai.

---

Agar ab tujh se interview mein koi bhi sawal poocha jaaye subnetting ya IPs se related — to tu araam se samjha sakta hai.

---

**Next Step:**
Chahie to main in sab ko aik proper **GitHub note style** mein likh deta hoon teri zuban mein — bas keh dena.
Ya chahie to main 5 MCQs bhi bana deta hoon practice ke liye.

Batao ab kya chahie?


---

### 🔢 **Yeh Table Yaad Rakh:**

| Remainder | IPs | Math | Divide 256 by...    |
| --------- | --- | ---- | ------------------- |
| 0         | 256 | 2^8  | 256                 |
| 1         | 128 | 2^7  | 256 ÷ 2             |
| 2         | 64  | 2^6  | 256 ÷ 2 ÷ 2         |
| 3         | 32  | 2^5  | 256 ÷ 2 ÷ 2 ÷ 2     |
| 4         | 16  | 2^4  | 256 ÷ 2 ÷ 2 ÷ 2 ÷ 2 |
| 5         | 8   | 2^3  | 256 ÷ 2^5           |
| 6         | 4   | 2^2  | 256 ÷ 2^6           |
| 7         | 2   | 2^1  | 256 ÷ 2^7           |

---

