### 🔹 **Subnetting Kya Hai?**

Socho ek **bara ghar hai** jismein **alag-alag departments** hain, jaise HR, IT, Accounts. Har department ka apna **glass door** hai. Yehi concept internet ke address system mein bhi hota hai — isay kehte hain **subnetting**.

Jab hum ek **bari IP address range** ko **choti-choti hisson (subnets)** mein divide karte hain, toh us process ko **subnetting** kehte hain.

Har subnet ka ek **label** hota hai jise hum kehte hain:

* Network address
* Broadcast address
* First host
* Last host
* Kitne host us subnet mein ho sakte hain

---

### 🔹 **Example lein:**

IPv4 Address: `192.168.12.160`
Subnet Mask: `255.255.255.192`
CIDR Notation: `192.168.12.160/26`

---

### 🔹 **Network Part aur Host Part ka Scene:**

IP address basically do hisso mein banta hai:

* **Network part**: ye batata hai ke yeh IP kis network mein belong karta hai
* **Host part**: ye batata hai ke us network mein yeh kis device ya computer ko diya gaya hai

---

### 🔹 **Subnet Mask Ka Kaam:**

Subnet mask batata hai:

* Network part mein kitne bits **fix (1)** hain — unko hum **change nahi** kar sakte
* Baaki bits host part ke liye hoti hain — ye **changeable** hoti hain, jisse hum nayi IPs ya host assign karte hain

---


| Subnet No. | Network Address  | First Host       | Last Host        | Broadcast Address | CIDR                |
| ---------- | ---------------- | ---------------- | ---------------- | ----------------- | ------------------- |
| 1          | `192.168.12.128` | `192.168.12.129` | `192.168.12.142` | `192.168.12.143`  | `192.168.12.128/28` |
| 2          | `192.168.12.144` | `192.168.12.145` | `192.168.12.158` | `192.168.12.159`  | `192.168.12.144/28` |
| 3          | `192.168.12.160` | `192.168.12.161` | `192.168.12.174` | `192.168.12.175`  | `192.168.12.160/28` |
| 4          | `192.168.12.176` | `192.168.12.177` | `192.168.12.190` | `192.168.12.191`  | `192.168.12.176/28` |

🧠 Har subnet mein **16 IPs** hoti hain, CIDR `/28` ka matlab hota hai ke **4 bits host ke liye available** hain (2^4 = 16).

---

## 🔹 **Mental Subnetting — Fast Sochne ka Tareeqa**

### Step 1: **Identify Changing Octet**

IP address ke 4 hissey hote hain:

* 1st Octet: `/8`
* 2nd Octet: `/16`
* 3rd Octet: `/24`
* 4th Octet: `/32`

Jaise agar kisi IP ka subnet `/25` hai, toh iska matlab hai ke **sirf 4th octet change ho sakta hai**, baaki sab fix hain.

**Example:**
Network: `192.168.1.1/25`
Toh IP: `192.168.2.4` same network mein **nahi** hai, kyunke `2` third octet mein change aa gaya.

---

### Step 2: **Remainder (Modulo) Trick**

Subnet bits ka remainder nikaal: `(CIDR % 8)`
Jaise `/25 % 8 = 1`

Ab is 1 se tu pata karega ke host part mein kitni IPs banengi:

Formula: `2^(8 - remainder)`

So:

* `2^(8 - 1) = 2^7 = 128 IPs`
* Usmein se 1 Network + 1 Broadcast = **126 usable**

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

### 💡 **Important: 0 ka matlab NULL nahi hota**

Jab tu subnet bana raha hota hai toh `0` bhi **valid value** hoti hai.

### Example:

`/25` means 128 IPs:

* First subnet: `192.168.1.0 - 192.168.1.127`

  * Network: `192.168.1.0`
  * Broadcast: `192.168.1.127`
  * **Usable IPs: `192.168.1.1 - 192.168.1.126`**

* Second subnet: `192.168.1.128 - 192.168.1.255`

  * Network: `192.168.1.128`
  * Broadcast: `192.168.1.255`
  * **Usable IPs: `192.168.1.129 - 192.168.1.254`**

---

## 🔚 **Shortcut Samajh le:**

* CIDR `%` 8 se remainder nikaal
* 256 ko `2^remainder` se divide kar
* Har subnet ka size mil jaega
* First IP = Network + 1
* Last IP = Broadcast - 1

---
