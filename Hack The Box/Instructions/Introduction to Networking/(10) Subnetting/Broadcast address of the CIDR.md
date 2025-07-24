## 🧠 **Question:**

**Submit the broadcast address of the following CIDR: `10.200.20.0/27`**

---

## 🎯 Step-by-Step Tareeqa:

### 1️⃣ **CIDR /27 ka Analysis:**

* IP: `10.200.20.0`
* Subnet mask: `/27 = 255.255.255.224`
* **Total IPs:**
  $2^{(32 - 27)} = 2^5 = 32 IPs$

### 2️⃣ **Network Address:**

CIDR ke end pe `.0` diya gaya hai, so:

```
Network Address = 10.200.20.0
```

---

### 3️⃣ **Broadcast Address Calculation:**

**Formula:**
`Broadcast Address = Last IP of the subnet = Network Address + (Total IPs - 1)`

```
10.200.20.0 + (32 - 1) = 10.200.20.31
```

---

### ✅ **Final Answer:**

```
Broadcast Address = 10.200.20.31
```
