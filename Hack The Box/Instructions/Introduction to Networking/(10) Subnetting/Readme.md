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

### 🔹 **/26 ka Matlab Kya Hai?**

`/26` matlab **first 26 bits fix hain**, aur baaki **6 bits host ke liye available** hain.
Toh 2^6 = **64 IPs** total milengi.

Lekin:

* 1 IP Network Address ke liye
* 1 IP Broadcast ke liye

👉 **Total valid hosts = 62**

---

### 🔹 **Subnet ke Important Addresses:**

* **Network Address**: `192.168.12.128`
* **Broadcast Address**: `192.168.12.191`
* **First Host**: `192.168.12.129`
* **Last Host**: `192.168.12.190`
* **Total Hosts**: `62`

---

### 🔹 **Gateway ka Role:**

Agar koi device dusre subnet mein data bhejna chahe, toh woh **default gateway** ke through jayega.
Aur agar source aur destination dono same subnet mein hon, toh **direct bhej diya jata hai**.

---

### 🔚 **Short Recap:**

Subnetting ka matlab hota hai **IP range ko logical parts mein divide karna**.
Har subnet ka apna network address, range of hosts, aur ek broadcast address hota hai.
Subnet mask aur CIDR batate hain ke kis hisse ko hum change kar sakte hain aur kis ko nahi.

---

### 📘 Ab Tere Liye 5 MCQs:

1. What does a `/26` CIDR mean?
   A) 26 IPs total
   B) 26 bits are for the host
   C) 26 bits are for the network
   D) 26 subnets exist

2. How many **valid hosts** are available in a `/26` subnet?
   A) 64
   B) 62
   C) 60
   D) 32

3. Which of the following is the **network address** for `192.168.12.160/26`?
   A) `192.168.12.128`
   B) `192.168.12.160`
   C) `192.168.12.192`
   D) `192.168.12.0`

4. Why is subnetting used?
   A) To increase internet speed
   B) To divide a big network into smaller logical parts
   C) To hide IP addresses
   D) To assign MAC addresses

5. Which address delivers data to **all devices in the subnet**?
   A) Network address
   B) First host
   C) Last host
   D) Broadcast address

---

Tayyari kar lo in MCQs ki — agar jawab dena chaho toh bhej dena, check kar dun 😎
Aur haan, koi angrezi word galat use kiya ho toh zaroor btao.
