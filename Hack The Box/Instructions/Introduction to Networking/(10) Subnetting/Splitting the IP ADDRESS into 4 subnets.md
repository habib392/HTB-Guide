## 🧠 Question:

**Split `10.200.20.0/27` into 4 subnets**
👉 **Submit the network address of the 3rd subnet**

---

## 🎯 Step-by-Step Tareeqa:

### 1️⃣ Original Network Info:

* **Network:** `10.200.20.0/27`
* **Subnet mask:** `255.255.255.224`
* **Total IPs in /27:**
  $2^{(32-27)} = 32$ IPs

---

### 2️⃣ Split into 4 Equal Subnets:

**32 IPs ÷ 4 = 8 IPs per subnet**
→ So har subnet hoga `/30` se bada, lekin `/30` sirf 4 IP deta hai.

Lekin yahan hum manually **8 IP per subnet** se subnet divide karenge.

---

### 🔢 Subnets:

| Subnet # | Network Address | Range                       | Broadcast    |
| -------- | --------------- | --------------------------- | ------------ |
| 1st      | `10.200.20.0`   | 10.200.20.0 – 10.200.20.7   | 10.200.20.7  |
| 2nd      | `10.200.20.8`   | 10.200.20.8 – 10.200.20.15  | 10.200.20.15 |
| 3rd      | `10.200.20.16`  | 10.200.20.16 – 10.200.20.23 | 10.200.20.23 |
| 4th      | `10.200.20.24`  | 10.200.20.24 – 10.200.20.31 | 10.200.20.31 |

---

### ✅ Final Answer:

```
3rd Subnet ka Network Address = 10.200.20.16
```
