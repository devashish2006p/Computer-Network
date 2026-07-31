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
  - **Limitations**
    1. Sirf Digital signals ka lia suitable hota hai.
    2. Data ko understand nahi karta hai.
    3. MAC address aur IP address process nahi karta.
    4. Security Filtering Provide nahi karta.
    5. Compatible Signal format ki zarurat hoti hai. 

3. Amplifier - Amplifier ek Physical Layer device hai jo weak electrical, optical ya radio signal ki power (amplitude) ko increase karke usse longer distance tak bhejne layak banata hai; ye Repeater aur Regenerator se isliye alag hai kyunki ye signal ko clean, reshape ya retime nahi karta, balki sirf uski strength badhata hai aur noise ko bhi amplify kar sakta hai.
   - **Internal Mechanism**
    1. Amplifier transmission medium sa aane wale weak electrical, optical ya RF signal ko receive karta hai aur input circuit ka through accept karta hai.
    2. Amplifier signal ki strength ko detect karta hai taki pata chal sake ki kitna amplification required hai.
    3. Internal electronic/optical amplification circuit signal ki power (amplitude) ko increase karta hai, lekin signal ka data ya content ko process nahi karta.
    4. Agr incoming signal ma noise ya interference maujood ho to amplifier us noise ko bhi signal ka sath amplify kar deta hai, isiliye ya signal ko clean nahi karta hai.
    5. Amplified signal ko output interface ka through dobara transmission medium par bhej diya jata hai, jisshe signal zyada distance tak travel kar sake.
   - **Limitations**
     1. Signal ko clean ya regenerate nahi karta.
     2. Noise ko bhi amplify karta hai.
     3. Data ko understand nahi karta.
     4. MAC address aur IP address process nahi karta.
     5. Security filtering provide nahi karta.
     6. Over amplification ka risk
## 2. Physical Connetivity Devices 
Physical Connectivity Devices wo hardware components hote hain jo network devices ko physically connect karne aur communication ke liye physical path provide karne ka kaam karte hain.
  - **Basic Devices**
    1. Hub - Hub ek Physical Layer (Layer 1) ka networking device hai jo multiple devices ko physically connect karta hai aur kisi ek port se receive hue bits ko bina samjhe ya filter kiye apne sabhi doosre ports par broadcast kar deta hai.
      - Internal Components
        1. Ports - Hub ka port ek physical interface hota hai jahan network cable connect ki jati hai, jiske through devices hub se judte hain aur bits receive aur transmit hote hain; hub me ports ki koi fixed sankhya nahi hoti, balki model ke hisaab se aam taur par 4, 5, 8, 16, 24 ya 48 ports hote hain.
        2. Physical Layer Transceiver - Physical Layer Transceiver (PHY) ek Physical Layer (Layer 1) ka hardware circuit/IC hota hai jo network cable se aane wale electrical/optical/radio signals ko receive karta hai, unhe transmit karta hai, aur digital bits (0s aur 1s) aur physical signals ke beech conversion ka kaam karta hai.
        3. Repeater/Multiport Repeater IC - Repeater / Multiport Repeater IC Hub ka main processing chip hota hai jo PHY se aane wale bits ko receive karta hai, unhe regenerate (clean/restore) karta hai aur phir ek input port ko chhodkar sabhi baaki ports par simultaneously broadcast kar deta hai.
        4. Internal Backplane/Signal Distribution Bus - Internal Backplane (Signal Distribution Bus) Hub ke andar ka high-speed internal electrical pathway (PCB traces/bus) hota hai jo Multiport Repeater IC se regenerate hue bits ko sabhi PHY circuits/ports tak distribute karta hai.
        5. Power Supply Circuit - Power Supply Circuit (PSU) Hub ka internal electrical circuit hota hai jo external power source (AC adapter ya DC input) se electricity receive karke use required DC voltages me convert aur regulate karta hai, phir Hub ke sabhi internal components (PHY, Multiport Repeater IC, LEDs, Backplane, etc.) ko stable power provide karta hai.
        6. Led indicator Circuit - LED Indicator Circuit Hub ka internal monitoring circuit hota hai jo Hub ke different hardware components se status information lekar LEDs ko control karta hai, taaki user ko Power, Link, Activity, Collision (old hubs) aur kabhi-kabhi Speed ki real-time status visually dikh sake.
        7. Clock/Oscillator Circuit - Clock / Oscillator Circuit Hub ka internal timing circuit hota hai jo ek stable clock signal (electrical pulses) generate karta hai, jisse PHY, Multiport Repeater IC aur doosre digital circuits synchronized timing ke saath sahi tarike se operate karte hain.
      - **Internal Workflow**
        1. Ksi connected device sa aane wale electrical signals port ka through Hub ma enter hote hai.
        2. Physical Layer Transceiver incoming electrical signal ko receive karke usshe internal digital bit stream me convert karta hai aur transmission ka time bits ko wapas electrical signal ma convert karta hai.
        3. Multiport Repeater IC received bits ko regenerate karta hai taki signal quality maintain rahe.
        4. Regenerated bits internal Backplane/Signal Distribution Bus ka through Hub ka sabhi connected PHY Circuits tak distribute kiya jate hai.
        5. Sabhi output PHY circuits bits ko dobara electrical signals ma convert karta hai aur Hub unmhe input port ko chodkar sabhi bakki ports par simultaneously broadcast kar deta hai.
        6. Communication ka dauran LED indicator circuit power, link, activity aur collision leds ko update karta hai.
        7. Poore process ka dauran power supply circuit sabhi internal components ko required aur stable DC power provide karta rehta hai.
        8. Clock/Oscillator Circuit sabhi digital circuits ko common timing pulses provide karta hai taki synchronized operation maintain rahe.
      - **Limitations**
      
    2. Patch Panel
    3. Passive Splitter/Coupler
## 3. Transmission Medium Devices 
Transmission Medium Devices wo components hote hain jo data signals ko ek device se dusre device tak travel karne ke liye physical ya wireless path provide karte hain.
## 4. Media Conversion Devices 
Media Conversion Devices wo devices hote hain jo ek type ke signal ya transmission medium ko dusre type ke signal ya medium me convert karte hain taki different networks communicate kar saken.
## 5. Interface Devices 
Interface Devices wo hardware components hote hain jo end devices (computer, server etc.) aur network medium ke beech communication interface provide karte hain.
