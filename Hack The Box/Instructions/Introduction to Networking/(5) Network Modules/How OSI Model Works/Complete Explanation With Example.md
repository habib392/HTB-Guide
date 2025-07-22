## 📶 OSI Model ka Real Life Example – Facebook.com Open Karne Par

Jab main apne ghar ke WiFi se connect hota hoon aur mobile ke Chrome browser mein **facebook.com** likhta hoon, to OSI Model ke **7 layers** kis tarah kaam karti hain? Chalo step-by-step samajhtay hain:

---

### ✅ Layer 1 – Application Layer 

* Yeh layer btati hai ky request kis application sy jaa rahi hai.

Example iss main Chrome sy
---

### ✅ Layer 2 – Presentation Layer

* Yeh data ko **encrypt/decrypt** karti hai.
* Facebook pe HTTPS use hota hai, to yahan SSL/TLS encryption lagta hai.
* Data ko readable format se encoded format mein convert karti hai.

> 🧠 *Matlab mere Facebook ka password encrypt ho kar neeche bheja jata hai.*

---

### ✅ Layer 3 – Session Layer

* Yeh layer **session manage** karti hai.
* Jaise browser aur Facebook server ke darmiyan **session create** hota hai.
* Session maintain rakhti hai jab tak browser band nahi hota ya logout nahi karte.

> 🧠 *Matlab Facebook ke sath meri connection line open rakhti hai.*

---

### ✅ Layer 4 – Transport Layer

* Yeh **TCP** ya **UDP** protocol use karti hai.
* Facebook HTTPS use karta hai, isliye **TCP** use hota hai.
* **Port 443** pe data bheja ja raha hota hai.
* **Reliability + Error checking** hoti hai.

> 🧠 *Yahan se data packets ban ke proper sequence mein jate hain.*

---

### ✅ Layer 5 – Network Layer

* Yeh **IP address assign** karti hai.
* Mera device ka IP aur Facebook server ka IP yahan decide hota hai.
* Data ko **routing** ke zariye server tak bhejti hai.

> 🧠 *Matlab mera mobile aur Facebook ka server ek doosray ko locate karte hain.*

---

### ✅ Layer 6 – Data Link Layer

* Yeh layer **MAC address** handle karti hai.
* WiFi router aur mobile ke darmiyan **frames** transfer hoti hain.
* **ARP protocol** ke zariye IP se MAC address nikaala jata hai.

> 🧠 *Yahan se mere router ko pata chalta hai ke packet mere mobile ka hai.*

---

### ✅ Layer 7 – Physical Layer

* Yeh layer **actual signal transmission** karti hai.
* WiFi ke zariye **radio waves** ke form mein data bheja jata hai.
* Wires hotay to electric signals use hotay, lekin WiFi mein wireless transmission hoti hai.

> 🧠 *Yahan se mere ghar ka router Facebook ka data hawa mein bhejta hai.*

---

## OSI Model Summary

| Layer # | Layer Name   | Facebook.com Use Case Description                      |
| ------- | ------------ | ------------------------------------------------------ |
| 7       | Application  | Facebook URL likhna, browser request banana            |
| 6       | Presentation | HTTPS encryption (SSL/TLS)                             |
| 5       | Session      | Facebook session create & maintain                     |
| 4       | Transport    | TCP handshake + Port 443 pe packets bhejna             |
| 3       | Network      | IP address decide karna aur routing                    |
| 2       | Data Link    | MAC address se local delivery (WiFi router tak)        |
| 1       | Physical     | Actual radio signal WiFi ke zariye hawa mein send hona |
