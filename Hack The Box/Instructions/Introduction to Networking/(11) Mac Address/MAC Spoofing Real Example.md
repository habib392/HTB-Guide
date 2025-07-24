## 🏡 Scenario:

* Tum **mamo ke ghar** jaate ho.
* Unka WiFi router sirf **known MAC addresses** ko internet deta hai (MAC filtering on hai).
* Tumhara **laptop Kali Linux wala hai**.
* Tum connect karna chahte ho bina unse password liye.

---

## 🔐 Pehle Samajh Lo — MAC Filtering Kya Hai?

Router mein ek feature hota hai jisko **MAC address filtering** kehte hain:

> “Sirf unhi devices ko internet milega jo mere whitelist mein hain (unke MAC addresses mujhe pehle se pata hain).”

---

## 🧠 Real Life Attack Flow (MAC Spoofing se Bypass)

### 🔧 Step 1: Sniff Karo — Kisi Connected Device ka MAC Uthao

1. Kali Linux start karo.
2. Terminal kholo aur yeh commands daalo:

```bash
sudo airmon-ng start wlan0
sudo airodump-ng wlan0mon
```

➡ Yeh tumhe dikhayega:
* Available WiFi networks.
* Har network pe kaunse devices connected hain (Client MAC addresses).

📌 **Kisi ek connected device ka MAC address choose karo** (jaise mamo ka mobile).

---

### 🌀 Step 2: Apna MAC Address Uske MAC se Replace Karo

```bash
sudo ifconfig wlan0 down
sudo macchanger -m <mamo-ka-MAC> wlan0
sudo ifconfig wlan0 up
```

➡ Ab router sochega ke tumhari device wohi hai jo pehle se whitelist mein hai.

---

### 📶 Step 3: WiFi se Connect Karo

Ab `Network Manager` ya `nmcli` se WiFi se connect karo:

```bash
nmcli dev wifi connect <SSID-Name> password <WiFi-Password> ifname wlan0
```

➡ Agar password nahi pata, to:
* Tumhe **WPA handshake capture karna hoga** aur usay crack karna hoga.
* Ya phir **WPS vulnerability** check karni hogi.

---

## 🔥 Zaroori Baat:

MAC spoofing sirf **MAC filtering ko bypass** karta hai. Agar WiFi **password protected** hai, to:
* Tumhe **password chahiye** hoga.
* Ya phir **WPA handshake sniff karke** brute-force ya dictionary attack karna hoga.

Agar router **open network** hai aur sirf MAC filtering on hai, to MAC spoofing se asaani se connect ho jaoge.

---

## 🤖 Real World Tip (Penetration Testing Ke Liye):

Penetration testers yehi method use karte hain:
* Kisi client ka MAC address spoof karke network mein dakhil hona.
* Phir tools jaise Wireshark ya Ettercap se sniffing ya MITM attacks karna.

---

## 🧠 Final Samajh:

| Condition                      | Result                                 |
|--------------------------------|----------------------------------------|
| MAC Filtering ON, Password OFF | ✅ MAC Spoofing = Internet Access      |
| MAC Filtering ON, Password ON  | ❌ Password Chahiye ya Crack Karna Hoga |
| MAC Filtering OFF, Password ON | ✅ Agar Password Pata Hai              |
