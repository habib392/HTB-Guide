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

## ✅ Step-by-Step Tarika: `/26` mein kitni IP addresses hain

### Step 1: Total bits in IPv4 address

IPv4 address = **32 bits**

### Step 2: /26 ka matlab?

`/26` ka matlab:

* 26 bits = **Network portion**
* Baqi `32 - 26 = 6 bits` = **Host portion**

### Step 3: Formula lagao

👉 IPs calculate karne ka formula:

```
2^host_bits = total IPs
```

`2^6 = 64 IP addresses`
➡️ Iska matlab: **/26 subnet mein 64 IPs total available hoti hain**

---

## ❗Important: Usable IPs kitni hoti hain?

Lekin 64 mein se:

* 1 IP = Network address (pehla IP)
* 1 IP = Broadcast address (last IP)

**Usable = 64 - 2 = 62 IPs**

---

### 🧠 IPv6 mein:

* Total bits = **128**
* Agar likha ho: `2001:0db8::/64`
  → iska matlab: **64 bits = Network**, baqi \`128 - 64 = 64 bits = Hosts\*\*

### Ab formula:

```
2^64 = Host IPs in subnet
```

Yeh number bohot bara hota hai — **18,446,744,073,709,551,616** usable IPs 😱


### ⚡ Extra Tip for PenTest:

* IPv6 itna bara hota hai ke brute force scanning impossible hai
* Isliye attackers mostly IPv4 pe focus karte hain
* IPv6 mein attacker ko pehle **active device ka exact address ya MAC-based hint chahiye hota hai**

---

## ✅ **Q: Recon mein CIDR kaise milta hai? Kya yeh public hota hai?**

**Jawab:**
Nahi, har jagah IP ke sath `/26`, `/24` waqaira **publicly available nahi hota**.
CIDR notation mostly **aapko recon ya scanning** karne ke baad milta hai.

### 🔎 Example:

* Jab aap kisi **company ka domain scan** karte ho (`example.com`)
* Aapko `IP address` milta hai e.g., `192.168.1.101`
* Lekin yeh nahi batata ke yeh IP **kis range (subnet)** ka part hai

#### Toh CIDR kaise milta hai?

* **Reverse DNS Lookup**
* **Whois Lookup**
* **Shodan.io**, **Censys.io** tools
* **Nmap Scan** (`nmap -sn 192.168.1.0/24`)
* Ya **network admin tools** jaise Netdiscover, arp-scan

---
