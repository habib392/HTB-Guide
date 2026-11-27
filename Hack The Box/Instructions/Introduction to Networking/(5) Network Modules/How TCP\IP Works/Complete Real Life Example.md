#### How Facebook.com website open from my Mobile Complete Explanation With TCP/IP Model

- Sub sy pehly **Application layer** yeh btata hai ky kis application sy mane Facebook.com access krny ki koshish ki jaisy yahan mane chrome sy Facebook.com open kiya agr main Facebook app sy on krta too mera application layer facebook hota kiun ky yahan sy hi request gayi hai meri 

- Isky baad aata hai **Transport Layer** matlab meri jo request hai jo Facebook ky server tk gyi hai woh kis tareeqay sy travel kr ky gyi hai or yeh traveling packets ky zariye hoti hai choty choty hazaron packets mil kr aik request generate krty hain or phir server tk bhejty hain 

- Isky baad aata hai **Internet Layer** iss main yeh hua ky ham kis jagah request bhej rahy hain ius ka address bhi too hona zaroori hai na hamary liye isi liye hamara ip address jata hai or DNS sy kehta hai mujy Facebook.com ka ip address doo takay main ius sy connect hoo sakon phir DNS facbook ky server sy Facebook.com ka ip address mangta hai or hum connect hoo jaty hain

- Phir aata hai last **Network Layer** ky hamary jo signal thy woh kaisy Facebook.com ky server tk pohanchy iss main yeh tareeqa tha ky meray wifi signal meray mobile sy nikal kr router tk gye or phir ius request ny aagy ISP ko request ki phir ius ny aagy Facebook.com ky server ko request ki phir wahan sy saara response bhi iusi tarah aaya jaisy Facebook.com ky server ny kaha **(Thek hai ap open kr loo hamari website)** phir request ISP tk pohanchi phir router tk or phir meray mobile pr or finally Facebook.com ki website on hoo gyi meray phone main

---

### 1. TCP/IP Model Ki 4 Layers Ka Asal Kaam
TCP/IP model mein aam taur par **4 layers** hoti hain (bhejte waqt upar se neeche):
 1. **Application Layer:**
   * Tumhari baat bilkul sahi hai ke yahan **Chrome** (ya **Facebook app**) se request bhejne ka kaam shuru hota hai (HTTPS request banti hai).
   * *Chhoti si baat:* **DNS** bhi darasal Application layer ka protocol hota hai jo facebook.com ka IP address dhoondhne mein madad karta hai, taake aage IP level par connection ban sake.
 2. **Transport Layer:**
   * Yeh decide karta hai ke data **TCP** se jayega ya **UDP** se (Facebook ke liye TCP aur port 443 use hota hai).
   * Data ko chhotay hisson (**segments**) mein toora jata hai aur sequence/reliability ka khayal rakha jata hai taake koi hissa gum ho ya ulta-pulta pohnche to sambhala ja sake.
 3. **Internet Layer:**
   * Yahan **Source IP** (tumhara/NAT IP) aur **Destination IP** (Facebook server ki IP) lagti hai.
   * Routers isi IP ki madad se packet ko aage se aage bhejte hain.
 4. **Network Access / Link Layer (Jise tumne last "Network Layer" likha):**
   * TCP/IP model mein is aakhri layer ko aksar **Network Access** ya **Link Layer** kehte hain (is mein MAC address/frames aur Wi-Fi radio waves / cables / signals ka kaam aata hai).
   * Yahan tumhare mobile se Wi-Fi ke zariye data **router** tak jata hai, phir **ISP** aur internet ke raastay **Facebook server** tak pohanchta hai, aur wahan se **response** wapas aakar browser mein page render kar deta hai.
### 2. Aik Chhoti Si Baat Response Ke Baare Mein
Jab Facebook server response bhejta hai, to wo sirf *"Thek hai open kar lo"* nahi hota, balkay poora **HTML, CSS, JavaScript, images, aur data** packets ki shakal mein wapas aata hai aur tumhara browser unhe jor kar screen par dikhata hai.
