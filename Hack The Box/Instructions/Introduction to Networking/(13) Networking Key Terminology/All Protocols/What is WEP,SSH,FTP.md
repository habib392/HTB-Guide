# WEP, FTP, aur SSH Notes

## **WEP (Wired Equivalent Privacy)**
- **Kya Hai?** Wireless networks ko secure karne ka purana protocol. Data encrypt karta hai, lekin ab kam secure hai, isliye WPA/WPA2/WPA3 ne jagah le li.
- **Use?** Pehle Wi-Fi networks ke liye use hota tha, lekin ab avoid kiya jata hai kyunki aasani se hack ho sakta hai.
- **Example**: Coffee shop mein free Wi-Fi ke liye WEP set kiya jata tha, lekin hacker uske weak encryption ko break kar sakta tha.
- **Internet ya Local?** Zyadatar internet ke saath, lekin local Wi-Fi network pe bhi kaam kar sakta hai bina internet ke.

---

## **FTP (File Transfer Protocol)**
- **Kya Hai?** Files ko ek computer se doosre tak transfer karne ka protocol. Client-server model pe kaam karta hai. Insecure hai, isliye SFTP/FTPS zyada use hote hain.
- **Use?** Website files (HTML, CSS, JS, images, videos) ya server pe data (backups, software) transfer karne ke liye.
- **Examples**: 
  - Website developer FileZilla se server pe files upload karta hai (jaise images, CSS).
  - Office mein ek computer se doosre pe large files transfer karna.
  - Video editor 5GB video client ke server pe upload karta hai.
- **Internet ya Local?** Internet ke zariye (website files upload) ya local network mein (office ke computers ke beech) dono tarah se kaam karta hai.
- **Vs HTTP/HTTPS**: HTTP/HTTPS web pages browser mein dikhane ke liye, FTP raw files transfer ke liye. HTTP/HTTPS user-friendly, FTP technical.
- **Vs WhatsApp**: WhatsApp FTP use nahi karta, woh HTTPS aur proprietary protocols use karta hai jo secure aur fast hain.
- **Cyber Security**: FTP ke weak security (jaise insecure passwords) ko hackers target karte hain, isliye penetration testing mein iski vulnerabilities check karna zaroori hai.

---

## **SSH (Secure Shell)**
- **Kya Hai?** Remote computer ya server ko securely control karne ka protocol. Data encrypt karta hai, bohat secure hai.
- **Use?** Server pe login karna, commands chalana (jaise software update, file edit), ya server manage karna.
- **Examples**: 
  - IT admin Lahore se Dubai ke server pe SSH se login karke software update karta hai (commands jaise `sudo apt update`).
  - Linux home server pe files manage karna.
  - Website ke server pe plugin fix karna ya database backup lena.
- **Internet ya Local?** Internet ke zariye (remote servers ke liye) ya local network mein (ghar ke Linux computer ke liye) dono tarah se kaam karta hai.
- **Vs WhatsApp**: WhatsApp mein server control nahi hota, sirf client app use hota hai. SSH server control ke liye hai.
- **Cloudflare Case**: Cloudflare ek CDN hai, uske settings dashboard se change hote hain, lekin linked server ko SSH se manage kiya jata hai (jaise AWS server pe PHP update).
- **Cyber Security**: SSH ke misconfigurations (jaise weak keys) hackers target karte hain, isliye penetration testing mein iski security check karna zaroori hai.

---

## **Key Differences**
- **FTP**: Files transfer ke liye (website files, backups). Insecure, isliye SFTP/FTPS better.
- **SSH**: Server control ke liye (edit, update, commands). Secure protocol.

---

## **Famous Platforms aur FTP/SSH**
- **WordPress**: 
  - FTP: Themes, plugins, images upload karne ke liye.
  - SSH: Server management (backups, updates) ke liye.
  - Zyadatar internet pe, lekin local testing possible.
- **AWS**: 
  - FTP: Files (media, code) S3 pe upload (SFTP zyada common).
  - SSH: EC2 servers manage karne ke liye.
  - Internet zaroori.
- **GitHub**: 
  - FTP: Code ko hosting server pe deploy karne ke liye.
  - SSH: Code push/pull aur repository management ke liye.
  - Internet zaroori.

---

## **Cyber Security Relevance**
- **FTP**: Weak security (insecure passwords) ko hackers target karte hain. Penetration testing mein vulnerabilities check karna zaroori.
- **SSH**: Misconfigurations (weak keys) ko hackers exploit karte hain. Security testing mein SSH ka audit must hai.

