# 1. Physical Layer Devices 
Physical Layer Devices wo hardware components hote hain jo OSI Model ki Physical Layer par kaam karte hain aur data ko physical medium (cable, fiber, wireless signals) ke through transmit, receive, regenerate ya convert karne me help karte hain.

# 2. Categories of These Devices 

## 1. Signal Regeneration Devices 
Signal Regeneration Devices wo devices hote hain jo weak ya distorted signals ko regenerate karke unki quality aur strength ko restore karte hain taki data long distance tak properly transmit ho sake.
- **Basic Deviecs**
1. Repeater - Repeater ek Physical Layer device hai jo weak ya degraded signal ko receive karke regenerate karta hai aur usse stronger form me dobara transmit karta hai taki data longer distance tak properly travel kar sake. Ya physical layer par he kaam karta hai sirf. 
  - **Internal Working Mechanism**
    1. Repeater network medium sa aane wale weak electrical/optical signal ko receive karta hai aur usshe input interface ka through accept karta hai.
    2. Repeater recieved signal ko analyze karta hai ki signal ka shape, timing aur strength kitni degredue hui hai.
    3. Repeater weak aur distorted signal ko regenerate karta hai, jisme signal ko clean, reshape aur restore kiya jata hai taki original bit pattern ka close ban sake.
    4. Digital repeater signal ka timing errors ko correct karta hai taki sender aur receiver ka beech bit synchronization maintain rahe.
    5. Regenerated signal ko output port ka through dobara transmission medium par bhej diya jata hai taki signal longer distance tak travel kar sake.
    - **Limitations**
      1. Data ko understand nahi karta - Ya sirf signal level par kaam karta hai, ishe nahi pata hota ki data kya hai ya kis device ka lia hai.
      2. MAC address aur IP address check nahi karta, ishme koi addressing intelligence nahi hoti, isiliye ya traffic ko filter ya control nahi kar shakta.
      3. Repeater firewall, access control ya packet inspection provide nahi karta, isiliye ya malicious traffic ko block nahi kar shakta.
      4. Agar signal me noise ya interference hai to wo bhi regenerate hokar aage ja sakta hai.
      5. Agar network me collision problem hai to repeater usse prevent nahi karta.
      6. Repeater signal distance badhata hai, lekin unlimited nahi; multiple repeaters lagane par delay aur signal issues aa sakte hain.
      7. Agar attacker ko repeater tak physical access mil jaye to wo network communication ko disrupt ya manipulate kar sakta hai.
2. Regenerator - Regenerator ek Physical Layer device hai jo degraded digital signal ko receive karke noise remove, reshape aur retiming ke through original bit pattern (0s aur 1s) ke close restore karta hai; ye Repeater se isliye alag hai kyunki Repeater mainly signal ko regenerate karke forward karta hai jabki Regenerator digital signal ki quality ko zyada accurately restore karta hai.
  - **Internal Mechanism**
    1. Regenerator transmission medium (mainly fiber/copper digital links) se aane wale weak aur distorted digital signal ko receive karta hai aur input circuit ke through process karne ke liye accept karta hai.
    2. Regenerator incoming signal ko analyze karta hai aur detect karta hai ki actual digital bits (0 aur 1) kya represent kar rahe hain, yani signal ke voltage/light level ko interpret karta hai.
    3. Regenerator unwanted noise aur interference ko remove karta hai taki original digital information clear ho sake.
    4. Regenerator distorted waveform ko dobara proper shape me convert karta hai taki signal clean digital pulse ke form me restore ho jaye.
    5. Regenerator clock timing ko correct karta hai taki bits correct timing ke saath transmit ho aur sender-receiver synchronization maintain rahe.
    6. Clean aur properly timed digital signal ko original bit pattern (0s aur 1s) ke close restore kiya jata hai.
    7. Restored digital signal ko output interface ke through dobara transmission medium par send kar diya jata hai taki long distance tak reliable communication ho sake.
3. Amplifier
## 2. Physical Connetivity Devices 
Physical Connectivity Devices wo hardware components hote hain jo network devices ko physically connect karne aur communication ke liye physical path provide karne ka kaam karte hain.
## 3. Transmission Medium Devices 
Transmission Medium Devices wo components hote hain jo data signals ko ek device se dusre device tak travel karne ke liye physical ya wireless path provide karte hain.
## 4. Media Conversion Devices 
Media Conversion Devices wo devices hote hain jo ek type ke signal ya transmission medium ko dusre type ke signal ya medium me convert karte hain taki different networks communicate kar saken.
## 5. Interface Devices 
Interface Devices wo hardware components hote hain jo end devices (computer, server etc.) aur network medium ke beech communication interface provide karte hain.
