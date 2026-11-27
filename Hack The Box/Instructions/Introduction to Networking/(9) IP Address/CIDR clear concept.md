**Pehly Ip address find hota hai phir ip a, ifconfig ya ipconfig jaisi commands sy subnet mask find kiya jata hai or phir CIDR**

## My Question 

Ab tumny yeh misal di

"Agar tumhe subnet mask pata ho, to tum 1 bits gin kar CIDR nikaal sakte ho. Maslan 255.255.255.0 mein 24 1 bits hotay hain (har 255 mein 8 1 bits: 8 + 8 + 8 = 24), isliye wo /24 hai." Too phir btao inn subnets
255.255.0.0 or 255.0.0.0 ka kya calculation hogi yani kaisy bits hongy kaisy calculate kiya jaye ga 


Isky ilawa dosra sawal agar mujy network ko 4 ya 5 groups main divide krna hoo too kaisy karon ga?

## Answer

Chalo pehle **255.255.0.0** aur **255.0.0.0** ki calculation bilkul step-by-step karte hain, aur phir dekhte hain ke aik network ko **4 ya 5 groups** mein kaise divide kiya jata hai.
### 1. Subnet Mask Se CIDR Bits Kaise Calculate Hotay Hain?
IPv4 ke har octet (har hisse) mein **8 bits** hotay hain:
 * Jab kisi octet ki value **255** hoti hai, to uske saare 8 bits **1** hotay hain (11111111 = **8 bits**).
 * Jab kisi octet ki value **0** hoti hai, to uske saare 8 bits **0** hotay hain (00000000 = **0 bits**).
 * CIDR nikalne ke liye hum sirf **1 bits ko jama (add)** karte hain:
 1. **255.255.0.0 ki calculation:**
   * Binary: 11111111 . 11111111 . 00000000 . 00000000
   * 1 bits gin lo: 8 + 8 + 0 + 0 = 16
   * **CIDR:** **/16**
 2. **255.0.0.0 ki calculation:**
   * Binary: 11111111 . 00000000 . 00000000 . 00000000
   * 1 bits gin lo: 8 + 0 + 0 + 0 = 8
   * **CIDR:** **/8**
*(Aur agar beech mein koi value ho—maslan 255.255.255.128—to 128 binary mein 10000000 hota hai, yani 1 bit 1 hai: 8 + 8 + 8 + 1 = 25 \rightarrow **/25**).*
### 2. Aik Network Ko 4 Ya 5 Groups Mein Kaise Divide Karein?
Networking mein subnetting **2 ki power (2^n)** ke hisaab se chalti hai (2, 4, 8, 16...), isliye **exact 5 barabar hissay** nahi bantay—agar tumhe **4 ya 5 groups** chahiye, to **4 groups** ke liye /26 aur **5 groups** ke liye **8 hissay (/27)** bana kar unmein se 5 use karte hain (aur 3 future ke liye bach jatay hain).
Maan lo hamare paas 192.168.1.0/24 hai (total **256** addresses):
#### A) Agar 4 Groups Chahiye (\rightarrow /26 Use Karo)
 * Hum host bits mein se **2 bits** udhaar (borrow) lete hain (2^2 = 4 groups), to /24 ban jata hai **/26** (subnet mask 255.255.255.192).
 * Har group mein 256 \div 4 = 64 addresses (jinmein se **62 usable hosts** hotay hain):
   * **Group 1:** 192.168.1.0/26 (.0 se .63 — usable .1 se .62)
   * **Group 2:** 192.168.1.64/26 (.64 se .127 — usable .65 se .126)
   * **Group 3:** 192.168.1.128/26 (.128 se .191 — usable .129 se .190)
   * **Group 4:** 192.168.1.192/26 (.192 se .255 — usable .193 se .254)
#### B) Agar 5 Groups Chahiye (\rightarrow /27 Use Karo)
 * 4 groups kam par jayenge, isliye hum **3 bits** borrow karte hain (2^3 = 8 groups), to /24 ban jata hai **/27** (subnet mask 255.255.255.224).
 * Har group mein 256 \div 8 = 32 addresses (jinmein se **30 usable hosts** hotay hain):
   * **Group 1:** 192.168.1.0/27 (.0 se .31)
   * **Group 2:** 192.168.1.32/27 (.32 se .63)
   * **Group 3:** 192.168.1.64/27 (.64 se .95)
   * **Group 4:** 192.168.1.96/27 (.96 se .127)
   * **Group 5:** 192.168.1.128/27 (.128 se .159)
   * *(Aur baqi 3 subnets .160/27, .192/27, .224/27 reserve mein rehte hain).*
