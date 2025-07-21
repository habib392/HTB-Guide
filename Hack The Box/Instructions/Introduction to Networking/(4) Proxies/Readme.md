### 🧠 Proxy Types

#### 🔰 Basic Definition

**Proxy** ka matlab hota hai ek beech wala banda (middleman) jo client (humara browser) aur server (website) ky darmiyan hota hai. Ye traffic ko aage bhejta hai, filter karta hai ya record karta hai.

---

### 🔄 **Forward Proxy** (Client Side Proxy)

**Ham isko use kar saktay hain.**

📌 **Use:**

* IP address chhupana
* BurpSuite mein interception
* Anonymous browsing (via Tor, VPN)

📌 **Examples:**

* BurpSuite
* FoxyProxy
* Tor browser
* VPNs

📌 **Penetration Testing Use:**

* Request ko capture karna
* Modify karna
* Malicious request send karna

📌 **Types:**

1. **Transparent Proxy**

   * User ko pata nahi hota
   * Mostly school/workplaces use karte hain
2. **Non-Transparent Proxy**

   * User manually set karta hai (e.g., BurpSuite)

➡️ FoxyProxy ke through hum BurpSuite ka manual proxy set kar saktay hain. Transparent/non-transparent dono handle hotay hain lekin hum mostly non-transparent use karte hain (kyunki ham control chahte hain).

---

### 🔁 **Reverse Proxy** (Server Side Proxy)

**Ham isko directly access nahi kar saktay.**

📌 **Use:**

* Server traffic ko manage karna
* Load balancing
* Caching
* SSL termination
* Request filtering

📌 **Examples:**

* Cloudflare
* Nginx reverse proxy
* AWS ALB (Application Load Balancer)

📌 **Penetration Testing View:**

* Ye humari actual target site ko chhupata hai
* Server-level security and filtering karta hai
* BurpSuite isko bypass nahi kar sakta unless koi misconfiguration ho

➡️ Isliye **humara reverse proxy se koi lena dena nahi**. Ye server ka kaam hai.

---

### 🔄 Inspect & SSH kya hotay hain?

**Inspect:**

* Browser ka Developer Tool hota hai
* Isse HTML, CSS, JS, network requests dekh saktay hain
* XSS, CSRF, APIs inspect karne mein kaam aata hai

**SSH (Secure Shell):**

* Remote server ko access karne ka secure tareeqa
* Mostly server admins use karte hain
* Pentester tab use karta hai jab shell mil jaye ya pivoting karni ho

📌 **Command Example:**

```bash
ssh user@ip_address
```

---

### 🔍 Summary (Seedhi Baat)

✅ Forward Proxy hum use karte hain (BurpSuite, FoxyProxy)
✅ Transparent Proxy hidden hoti hai, Non-transparent user sets manually
❌ Reverse Proxy server ka kaam hai, hum dekh nahi saktay
✅ Inspect tool se browser code analyze hota hai
✅ SSH remote access ke liye hota hai (agar shell mil jaye)

---

🧠 **Note for Pentesting:**

* Hamesha apna Burp proxy non-transparent set karo (manual proxy config)
* FoxyProxy use karo har website ka traffic intercept karne ke liye
* Reverse proxy se direct access ka chance nahi hota
* Target pe hone wale protections samajhne ke liye response headers dekhte raho (e.g., `via`, `x-forwarded-for`, etc)
