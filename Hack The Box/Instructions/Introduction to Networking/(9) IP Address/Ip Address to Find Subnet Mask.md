# 🌐 IP Address Classes & Subnet Mask

---

## 📌 IP Address ka Subnet Mask Kahan Se Pata Chalta Hai?

**2 tareeqay hain:**

1. **CIDR diya ho (jaise /24):**

   * Example: `56.23.13.52/24` → Subnet mask = `255.255.255.0`

2. **CIDR na ho, sirf IP mile:**

   * Toh pehla octet dekho (IP ka pehla number)
   * Usse class ka pata chalta hai → us class ka default subnet mask lagta hai

---

## 🔓 Public IP Classes & Unka Subnet Mask

| Class | Range (First Octet) | Subnet Mask   | CIDR | Hosts (Approx) |
| ----- | ------------------- | ------------- | ---- | -------------- |
| A     | 1 – 126             | 255.0.0.0     | /8   | 16 Million+    |
| B     | 128 – 191           | 255.255.0.0   | /16  | 65,534         |
| C     | 192 – 223           | 255.255.255.0 | /24  | 254            |

📌 Class D (224–239) multicast ke liye hoti hai,
📌 Class E (240–255) experimental ke liye hoti hai
📌 127.0.0.1 → loopback hoti hai

---

## 🔐 Private IP Classes & Unki Ranges

| Class | Private Range                 | Subnet Mask   | CIDR | Hosts Approx |
| ----- | ----------------------------- | ------------- | ---- | ------------ |
| A     | 10.0.0.0 – 10.255.255.255     | 255.0.0.0     | /8   | 16 Million+  |
| B     | 172.16.0.0 – 172.31.255.255   | 255.255.0.0   | /12  | 1 Million+   |
| C     | 192.168.0.0 – 192.168.255.255 | 255.255.255.0 | /16  | 65K ya 254   |

📌 Yeh private IPs sirf local use ke liye hoti hain — jaise ghar ke Wi-Fi, office LAN, VPN etc.

---

### ✔️ Public aur Private dono mein Class system same hota hai

* Dono mein A, B, C class hoti hai
* Bas farq yeh hai ke **public IP internet pe hoti hai**, **private IP local network ke liye hoti hai**

### ✔️ Class ka pata pehle octet se chalta hai

* Jaise: `56.x.x.x` → Class A (because 56 is between 1-126)

### ✔️ Private IP ranges fix hoti hain

* Sirf 3 ranges hoti hain:

  * 10.0.0.0/8
  * 172.16.0.0/12
  * 192.168.0.0/16

### ❌ Subnet mask sirf network dikhane ke liye nahi hota

* ✅ **Subnet mask ka kaam hota hai:**

  * Network bits aur host bits ko separate karna
  * Bataana ke total kitne usable IPs hain ek network mein
* Jaise:

  * `255.255.255.0` → 254 usable IPs
  * `255.0.0.0` → 16 million+ IPs

---

## 🧠 Important Concepts:

* **Zyada host bits = Zyada IPs**
* **Zyada network bits = Kam IPs per subnet, lekin zyada subnets**
* Subnet mask = IPs divide karne ka tool hota hai, dikhane ka nahi

---

## ⚡ Penetration Testing Mein Use:

1. Recon ke waqt tum subnet mask aur IP range se yeh samajh sakte ho:

   * Target ka network kitna bara hai
   * Kitni machines hain scan karne layak
2. `nmap`, `whois`, `netdiscover` jaise tools subnet info reveal karte hain
3. Private IPs hone ka matlab tum LAN ke andar ho — direct internet access nahi

