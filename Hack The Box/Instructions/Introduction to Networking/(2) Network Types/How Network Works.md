### 📡 **Internet Kaise Kaam Karta Hai – Simple Explanation**

Bhai dekho, jab main apne computer ya mobile se **facebook.com** open karta hoon, toh sabse pehle:

1. **Mera device** — jo router se connected hota hai — ek request bhejta hai router ko.
2. Mera router — jiske paas meri **private IP** hoti hai — Internet pe jaane ke liye **public IP** maangta hai.
3. Yeh public IP **ISP (Internet Service Provider)** deta hai, jaise Nayatel, PTCL, waghaira.
4. Phir yeh request **packets** ki form mein Facebook ke server tak jaati hai.
5. Facebook.com ek **website** hai jo **internet pe publicly available** hai — isliye iske paas bhi ek **public IP** hoti hai.
6. Mera packet **Facebook ke server** tak **WAN (Wide Area Network)** ke zariye jaata hai — kyun ke WAN mein public IPs ka use hota hai aur data long distance travel karta hai.
7. Jab meri request Facebook ke server tak pahunchti hai, toh woh server mujhe **response** bhejta hai (jaise newsfeed, login page waghaira).
8. Yeh poora system jo **poori duniya ke servers aur ISPs** ko connect karta hai — usse kehte hain **GAN (Global Area Network)**.
9. GAN basically woh backbone hai jo **Facebook jaise servers, Cloudflare, Google DNS, etc.** ko connect aur manage karta hai — yeh hamare liye **internet ka brain** hai.

Aur bhai yeh sara data transfer **TCP/IP ya UDP protocols** ki madad se hota hai — jo ensure karte hain ke data sahi tareeke se bheja aur receive ho.

---

### 💡 Example:

> "Internet ka kaam simple hai bhai — mera router request bhejta hai, ISP usko public IP deta hai, phir woh request WAN ke zariye Facebook ke server tak jaati hai. Aur yeh poora global system jo manage karta hai, usse kehte hain GAN."
