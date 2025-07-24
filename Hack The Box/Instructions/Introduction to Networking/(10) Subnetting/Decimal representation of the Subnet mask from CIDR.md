### 🎯 Question:

**"Submit the decimal representation of the subnet mask from the following CIDR: 10.200.20.0/27"**

---

### ✅ Step-by-Step Solution

#### 1️⃣ CIDR ko Binary Subnet Mask mein Convert karo:

* IP addresses total **32 bits** ke hote hain.
* `/27` ka matlab: 27 bits **1** (network) + 5 bits **0** (host)

**Binary Subnet Mask:**

```
11111111.11111111.11111111.11100000
```

#### 2️⃣ Har Octet ko Alag Karo:

```
11111111 = ?
11111111 = ?
11111111 = ?
11100000 = ?
```

---

### 🔁 3️⃣ Binary to Decimal Conversion

#### 🔹 Octet 1: `11111111`

→ 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = **255**

#### 🔹 Octet 2: `11111111`

→ Same = **255**

#### 🔹 Octet 3: `11111111`

→ Same = **255**

#### 🔹 Octet 4: `11100000`

→ 128 + 64 + 32 = **224**

---

### ✅ Final Subnet Mask (Decimal):

```
255.255.255.224
```

---

## 📚 Binary to Decimal Shortcut Table

| Binary   | Decimal |
| -------- | ------- |
| 10000000 | 128     |
| 11000000 | 192     |
| 11100000 | 224     |
| 11110000 | 240     |
| 11111000 | 248     |
| 11111100 | 252     |
| 11111110 | 254     |
| 11111111 | 255     |

---

## 💡 Penetration Testing Tip:

Jab aap internal network reconnaissance (jaise Nmap scan) karte ho to CIDR batata hai kitne IPs scan karne hain.
**/27** ka matlab hota hai **32 IPs total**, jin mein se 30 usable hosts hote hain.
Yeh aapko targeted scanning mein help karta hai time bachane ke liye.
