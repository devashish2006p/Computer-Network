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
        1. Data ko smjhe bina sabhi ports par broadcast kar deta ha.
        2. Sabhi devices same collision domain share karta hai, isiliye collisions zyada hota hai.
        3. Sabhi connected devices ek hi bandwidth share karte hai, jisshe performance kam ho jata hai.
      - **Advantages**
        1. Structure aur working bahut simple hota hai, isiliye samjhana aur use karna aasan hota hai.
        2. Switch ka comparision ma sasta networking device hota hai.
        3. Configuration ki jarurat nahi parti. 
    2. Patch Panel - Patch Panel ek passive Physical Layer (Layer 1) ka cable management aur connectivity device hai jo permanent network cables ko terminate aur organize karta hai, aur unhe short patch cords ke through switches ya anya network devices se aasani se connect, disconnect ya reconfigure karne ki suvidha deta hai.
      - **Internal Components**
        1. RJ45 Ports (Front Interface) – Jahan patch cords connect hote hain.
        2. IDC / Punch-Down Terminals (Back Interface) – Jahan permanent LAN cables terminate ki jati hain.
        3. Internal Conductive Contacts (Copper Traces/Contacts) – Front RJ45 ports ko back IDC terminals se electrically connect karte hain.
        4. Patch Panel Frame / Chassis – Metal ya plastic body jo sabhi ports aur components ko hold aur protect karti hai.
        5. Port Numbering & Label Strip – Har port ko identify aur organize karne ke liye numbering/labeling provide karti hai.
        6. Cable Management Bar / Strain Relief (Model dependent) – Permanent cables ko support deta hai aur cable par tension (strain) kam karta hai.
      - **Internal Mechanism**
          1. Cable Termination Stage - Permanent network cable ko Patch Panel ke back side ke IDC (Punch-Down) terminals par terminate kiya jata hai.
          2. Signal Reception Stage - Jab kisi device se signal permanent cable ke through aata hai, to wo IDC terminal tak pahunchta hai.
          3. Internal Signal Path Stage - IDC terminal se signal Patch Panel ke internal copper contacts/traces ke through corresponding front RJ45 port tak pass hota hai.
          4. Patch Connection Stage - Front RJ45 port me lagi patch cord us signal ko receive karti hai aur use Switch, Hub ya kisi doosre network device tak le jati hai.
          5. Bidirectional Communication Stage - Yehi process reverse direction me bhi hota hai; signal dono directions me pass ho sakta hai bina kisi processing ke.
          6. Passive Operation Stage - Pure process ke dauran Patch Panel signal ko na amplify karta hai, na regenerate karta hai, na filter karta hai aur na hi interpret karta hai; ye sirf ek organized physical path provide karta hai.
        - **Advantages**
          1. Organized Cabling – Network cables ko systematic aur neatly organize karta hai.
          2. Easy Maintenance – Cable faults ko identify aur replace karna aasaan ho jata hai.
          3. Easy Reconfiguration – Patch cords badalkar connections ko bina permanent cabling badle aasani se change kiya ja sakta hai.
          4. Protects Permanent Cables – Permanent building cables ko baar-baar unplug karne ki zarurat nahi padti, isliye unki life badh jati hai.
          5. Simplifies Troubleshooting – Network connections ko trace aur troubleshoot karna easy ho jata hai.
          6. Scalable – Naye devices aur network expansions ko efficiently manage kiya ja sakta hai.
        - **Disadvantages**
          1. Signal Processing nahi karta – Signal ko amplify, regenerate ya filter nahi karta.
          2. Additional Hardware Required – Kaam karne ke liye patch cords aur active devices (jaise Switch) ki zarurat hoti hai.
          3. Installation Skill Required – IDC terminals par sahi cable termination ke liye proper tools aur technique chahiye.
          4. Extra Cost – Network infrastructure me additional hardware cost add karta hai.
          5. Space Required – Rack ya wall mounting ke liye extra physical space ki zarurat hoti hai.
          6. Wrong Termination Issues – Agar cables galat terminate ho jayein to connectivity problems aa sakti hain.
    3. Passive Splitter - Passive Splitter ek passive Physical Layer (Layer 1) ka device hai jo bina kisi power ya signal processing ke ek incoming signal ko do ya adhik output paths me distribute (split) karta hai.
        - **Internal Components**
          1. Input Port – Jahan se original signal splitter me enter karta hai.
          2. Signal Splitting Network – Internal passive conductive path/optical splitter jo signal ko multiple outputs me divide karta hai.
          3. Output Ports – Split hue signal ko alag-alag cables ya devices tak bhejte hain.
          4. Protective Housing (Enclosure) – Internal components ko hold aur protect karta hai.
          5. Connectors (Model dependent) – RJ45, BNC, SC, LC ya anya connector types, medium ke hisaab se.
        - **Internal Mechanism**
          1. Signal Reception Stage – Incoming electrical, optical ya RF signal Input Port ke through Passive Splitter me enter karta hai.
          2. Signal Distribution Stage – Internal passive conductive path ya optical splitting element signal ko bina process kiye multiple branches me divide karta hai.
          3. Signal Forwarding Stage – Split hua signal corresponding Output Ports tak pahunchaya jata hai.
          4. Signal Transmission Stage – Output Ports split signal ko connected cables ya devices tak forward kar dete hain.
          5. Passive Operation Stage – Pure process ke dauran Passive Splitter signal ko na amplify karta hai, na regenerate karta hai, na filter karta hai aur na hi interpret karta hai; ye sirf signal ko physically divide karke multiple paths me distribute karta hai.
        - **Advantage**
          1. Simple Design – Structure bahut simple hota hai aur configuration ki zarurat nahi hoti.
          2. No External Power Required – Bina electricity ke kaam karta hai.
          3. Low Cost – Active signal distribution devices ke comparison me sasta hota hai.
          4. Easy Installation – Install aur use karna bahut aasaan hota hai.
          5. Signal Distribution – Ek incoming signal ko multiple output paths me distribute kar sakta hai.
        - **Disadvantage**
          1. Signal Loss – Signal split hone ki wajah se har output par signal strength kam ho jati hai.
          2. No Signal Regeneration – Weak signal ko restore ya regenerate nahi karta.
          3. No Signal Amplification – Signal ki power increase nahi karta.
          4. No Intelligent Processing – Data ya signal ko analyze, filter ya route nahi karta.
          5. Limited Distance Support – Signal loss ki wajah se long-distance communication ke liye suitable nahi hota.
          6. Performance Depends on Input Signal – Agar input signal weak ho, to output signals aur bhi weak ho jate hain.
    4. Passive Coupler - Passive Coupler ek passive Physical Layer (Layer 1) ka device hai jo bina kisi power ya signal processing ke do physical cables ya network links ko aapas me connect (couple) karta hai, taki signal ek cable se doosri cable tak pass ho sake.
        - **Internal Components**
          1. Input/Output Connectors (Ports) – Do physical cables ya links ko connect karne ke liye connectors provide karte hain.
          2. Internal Conductive/Optical Coupling Path – Signal ko ek connector se doosre connector tak bina process kiye pass karne wala internal path.
          3. Alignment Mechanism (Medium dependent) – Copper ya fiber conductors ko accurately align karta hai taki signal efficiently pass ho sake.
          4. Protective Housing (Enclosure) – Internal parts ko hold aur physical damage se protect karta hai.
          5. Locking/Fixing Mechanism (Model dependent) – Connected cables ko securely hold karta hai aur accidental disconnection se bachata hai.
        - **Internal Mechanism**
          1. Signal Reception Stage – Signal pehli cable se Coupler ke first connector ke through enter karta hai.
          2. Physical Coupling Stage – Coupler ka internal conductive/optical path dono connectors ko physically aur electrically/optically connect karta hai.
          3. Signal Transfer Stage – Signal bina kisi processing, amplification ya regeneration ke internal path se doosre connector tak pass ho jata hai.
          4. Signal Transmission Stage – Doosre connector se signal connected cable ya device tak continue travel karta hai.
          5. Passive Operation Stage – Pure process ke dauran Passive Coupler signal ko na amplify karta hai, na regenerate karta hai, na filter karta hai aur na hi interpret karta hai; ye sirf do physical links ke beech ek continuous transmission path provide karta hai.
        - **Advantages**
          1. Simple Design – Structure bahut simple hota hai aur use karna aasaan hota hai.
          2. No External Power Required – Bina kisi electrical power ke kaam karta hai.
          3. Low Cost – Active networking devices ke comparison me kaafi sasta hota hai.
          4. Easy Cable Extension – Do compatible cables ya links ko aasani se connect karke cable length badhane me madad karta hai.
          5. No Configuration Required – Kisi software ya network configuration ki zarurat nahi hoti.
        - **Disadvantages**
          1. Signal Loss – Connector aur connection point ki wajah se thoda signal attenuation ho sakta hai.
          2. No Signal Regeneration – Weak signal ko restore ya regenerate nahi karta.
          3. No Signal Amplification – Signal ki strength increase nahi karta.
          4. No Intelligent Processing – Signal ya data ko analyze, filter ya route nahi karta.
          5. Compatible Connectors Required – Sirf same type ke compatible cables/connectors ko connect kar sakta hai.
          6. Not Suitable for Long Distances – Long cable extensions me signal degradation ki problem ho sakti hai kyunki Coupler signal quality improve nahi karta.
## 3. Transmission Medium Devices 
Transmission Medium Devices wo components hote hain jo data signals ko ek device se dusre device tak travel karne ke liye physical ya wireless path provide karte hain.
- **There are two broad categories of Transmission Medium Devices**
### 1. Guided (wired) Transmission Media
1. Twisted Pair Cable - Twisted Pair Cable ek guided (wired) transmission medium hai jisme do insulated copper wires ko electromagnetic interference (EMI) aur crosstalk kam karne ke liye ek-dusre ke around twist kiya jata hai, taki data signals reliably transmit ho saken.
  - **Basic Types of Twisted Pair Cable**
    1. UTP (Unshielded Twisted Pair) - Ishme ksi extra metallic shielding ka use nahi hota.
      - **Basic Core Components**
        1. Copper Conductors - Electrical signals ko carry karne wale copper wires.
        2. Insulation Layer - Har copper conductor ko electrically isolate aur protect karta hai.
        3. Twisted Wire pairs - Do insulated conductors ko ek pair banakar twist kiya jata hai, jissa EMI aur crosstalk kam hota hai.
        4. Outer jacket (PVC/LSZH) - Puri cable ko mechanical protection aur enviromental protection deta hai. 
      - **Advantage**
        1. Low Cost – Fiber aur STP cable ke comparison me sasti hoti hai.
        2. Easy Installation – Install, terminate aur maintain karna aasaan hota hai.
        3. Flexible – Cable patli aur flexible hoti hai, isliye routing aasaan hoti hai.
        4. Good Performance – Short aur medium distances par reliable high-speed data transmission provide karti hai.
        5. Widely Available – LAN networks me sabse zyada use hone wali cable hai.
        6. Lightweight – Weight kam hone ki wajah se handling aur cable management aasaan hota hai.
      - **Disadvantage**
        1. EMI Sensitive – Strong electromagnetic interference se signal quality affect ho sakti hai.
        2. Crosstalk – Adjacent wire pairs ke beech unwanted signal interference ho sakta hai.
        3. Limited Distance – Ethernet me generally 100 meters tak hi recommended hoti hai.
        4. Less Secure Physically – Electrical signal carry karne ki wajah se specialized equipment se signal tapping ka risk fiber ke comparison me zyada hota hai.
        5. Lower Noise Protection – Shielding na hone ki wajah se noisy industrial environments ke liye ideal nahi hoti.
    2. STP (Shielded Twisted Pair) - Ishme electromagnetic Interference (EMI) sa bachne ka lia metallic shielding hoti hai. 
      - **Core Components**
        1. Copper Conductors – Electrical signals ko carry karne wale copper wires.
        2. Insulation Layer – Har copper conductor ko electrically isolate aur protect karti hai.
        3. Twisted Wire Pairs – Do insulated conductors ko ek pair banakar twist kiya jata hai, jisse crosstalk kam hota hai.
        4. Metallic Shield (Foil/Braided Shield) – External electromagnetic interference (EMI) aur noise se signal ko protect karta hai.
        5. Outer Jacket (PVC/LSZH) – Puri cable ko mechanical aur environmental protection deta hai.
      - **Advantage**
        1. High EMI Protection – Metallic shielding external electromagnetic interference (EMI) se signal ko protect karti hai.
        2. Reduced Crosstalk – Shielding aur twisted pairs unwanted interference ko aur kam karte hain.
        3. Better Signal Quality – Noisy environments me bhi stable aur reliable data transmission provide karti hai.
        4. Suitable for Industrial Environments – Factories, data centers aur high-electrical-noise areas ke liye adhik suitable hoti hai.
        5. Higher Reliability – Interference kam hone ki wajah se communication errors ki sambhavna kam hoti hai.
      - **Limitations**
        1. Higher Cost – UTP ke comparison me zyada mehengi hoti hai.
        2. Difficult Installation – Shielding ki wajah se installation aur termination thodi complex hoti hai.
        3. Less Flexible – Additional shielding ke karan cable comparatively rigid hoti hai.
        4. Proper Grounding Required – Shielding ka effective protection tabhi milta hai jab cable sahi tarike se grounded ho.
        5. Heavier Cable – Shield ki wajah se weight UTP se zyada hota hai.
           
2. Coaxial Cable - Coaxial Cable ek guided (wired) transmission medium hai jisme ek central copper conductor, insulating dielectric layer, metallic shield aur outer jacket concentric layers me arranged hote hain, jisse electrical signals reliably transmit kiye ja saken aur external interference kam ho.
   - **Core Components**
    1. Central Conductor – Usually copper/copper-clad conductor jo electrical signal carry karta hai.
    2. Dielectric Insulator – Central conductor ko surrounding shield se electrically isolate karta hai aur conductor ki position maintain karta hai.
    3. Metallic Shield / Outer Conductor – Signal ko contain karta hai aur external EMI/noise se protection provide karta hai.
    4. Outer Jacket – Puri cable ko mechanical damage, moisture aur environmental effects se protect karta hai.
   - **Advantages**
    1. Good EMI Protection – Metallic shield external electromagnetic interference ko significantly reduce karta hai.
    2. Reliable Signal Transmission – Shielding aur controlled structure ki wajah se signal relatively stable rehta hai.
    3. Higher Noise Resistance – UTP ke comparison me noisy environments me better perform kar sakta hai.
    4. Longer Reach – Common twisted-pair Ethernet deployments ke comparison me kuch coaxial applications longer cable runs support kar sakti hain.
    5. Durable Construction – Multiple protective layers cable ko mechanical damage se relatively better protect karti hain.
    6. Wide Frequency Support – Suitable coaxial designs high-frequency signals aur multiple channels carry kar sakte hain.
   - **Disadvantages**
    1. More Expensive – UTP ke comparison me generally cable aur associated connectors zyada costly ho sakte hain.
    2. Less Flexible – Thick construction ki wajah se UTP ke comparison me bend aur route karna difficult hota hai.
    3. More Difficult Installation – Termination aur connector installation comparatively complex hoti hai.
    4. Higher Weight – Metallic shield aur thicker construction ki wajah se UTP se heavier hota hai.
    5. Physical Tapping Risk – Copper-based medium hone ki wajah se physical access milne par signal interception possible hai.
    6. Not as High-Capacity as Fiber – High-bandwidth, very-long-distance applications me fiber optic generally superior hota hai.
3. Fiber Optic Cable - Fiber Optic Cable ek guided (wired) transmission medium hai jisme glass ya plastic ke extremely thin optical fibers ke through electrical signals ki jagah light pulses transmit karke high-speed, long-distance aur low-loss data communication ki jati hai.
  - **Types of Fiber Optic Cable**
    1. Single Mode Fiber (SMF) - SMF ek fiber-optic cable type hai jisme bahut chhota core hota hai, jiske andar light ka essentially ek propagation mode travel karta hai, isliye light pulses ke spread (dispersion) ko bahut kam rakhkar ye very long-distance aur high-speed communication ke liye suitable hota hai.
    2. Multi Mode Fiber (MMF) - MMF ek fiber-optic cable type hai jisme SMF se comparatively bada core hota hai, jiske andar light multiple propagation modes/paths se travel karti hai, jiski wajah se dispersion zyada hota hai aur ye generally shorter-distance, high-speed communication jaise LAN aur data-center links ke liye suitable hota hai.
  - **Core Components**
    1. Core – Glass/plastic ka central optical region jisme light signals travel karte hain.
    2. Cladding – Core ke around glass layer hoti hai jiska refractive index lower hota hai, jo light ko core ke andar guide karne me help karti hai.
    3. Coating / Buffer – Fiber ko moisture, bending aur mechanical stress se protect karti hai.
    4. Strength Member – Tensile strength provide karta hai taki cable ko kheenchne par fiber damage na ho.
    5. Outer Jacket – Puri cable ko physical aur environmental damage se protect karta hai.
  - **Advantages**
    1. Very High Bandwidth – Copper cables ke comparison me bahut high data rates support kar sakti hai.
    2. Long-Distance Transmission – Signal ko relatively long distances tak low attenuation ke saath transmit kar sakti hai.
    3. EMI Immune – Fiber glass/plastic se bani hoti hai, isliye electromagnetic interference se practically unaffected hoti hai.
    4. Low Signal Loss – Long-distance communication me signal attenuation copper ke comparison me bahut kam hota hai.
    5. High Security – Electrical signal na hone ki wajah se conventional electromagnetic tapping difficult hoti hai, although physical tapping still possible hai.
    6. Lightweight – High-capacity communication ke liye copper cabling ke comparison me lightweight ho sakti hai.
    7. Electrical Isolation – Do endpoints ke beech electrical current conduct nahi karti, isliye ground loops aur electrical interference ka risk nahi hota.
  - **Disadvantages**
    1. High Cost – Cable, optical transceivers aur installation equipment copper ke comparison me generally expensive hote hain.
    2. Fragile Fiber – Glass fiber excessive bending, crushing ya pulling se damage ho sakti hai.
    3. Difficult Installation – Splicing, termination aur testing ke liye specialized tools aur skills chahiye.
    4. Specialized Hardware Required – Electrical-to-optical aur optical-to-electrical conversion ke liye optical transceivers/receivers required hote hain.
    5. Repair Complexity – Fiber break hone par fault locate aur repair karna copper cable ke comparison me comparatively difficult hota hai.
    6. Physical Tapping Possible – Fiber highly secure hai, lekin specialized equipment aur physical access ke saath optical tapping theoretically possible hai.
### 2. Unguided (Wireless) Transmission Media 
1. Radio Waves - Radio waves electromagnetic waves hoti hain jo rapidly changing electric aur magnetic fields ke through space me travel karti hain aur wireless communication me information (data, voice, video) ko carry karne ke liye use hoti hain.
  - **Working Mechanism**
    1. Data generate hota hai – Computer/phone se digital data (0 aur 1) generate hota hai.
    2. Data electrical signal me hota hai – Device ka communication hardware is data ko electrical signal ke form me process karta hai.
    3. Carrier wave generate hoti hai – Transmitter ek high-frequency electromagnetic carrier signal generate karta hai.
    4. Data carrier par modulate hota hai – Data ke according carrier ki amplitude, frequency ya phase ko change kiya jata hai; isi process ko modulation kehte hain.
    5. Antenna electrical energy ko electromagnetic wave me convert karta hai – Transmitter antenna me rapidly changing electrical current electromagnetic field create karta hai, aur ye energy radio wave ke form me space me propagate hoti hai.
    6. Radio wave space me travel karti hai – Radio wave ke electric field aur magnetic field ek-dusre ke perpendicular hote hain aur dono propagation direction ke bhi perpendicular hote hain.
    7. Environment wave ko affect karta hai – Buildings, walls, trees aur terrain se radio wave reflect, diffract, refract ya scatter ho sakti hai, jiski wajah se signal weak ya distorted ho sakta hai.
    8. Receiver antenna wave detect karta hai – Jab radio wave receiver antenna tak pahunchti hai, uska electromagnetic field antenna me ek very small electrical signal induce karta hai.
    9. Receiver desired signal ko filter karta hai – Receiver unwanted frequencies/noise ko remove karke required frequency band ko select karta hai.
    10. Demodulation hoti hai – Receiver carrier se original information ko extract karta hai; is process ko demodulation kehte hain.
    11. Original data recover hota hai – Extracted signal ko receiver ka digital circuitry process karke original 0s aur 1s me recover karta hai.
  - **Advantages**
    1. Wireless Communication – Physical cable ki zarurat nahi hoti, isliye devices ko wirelessly connect kiya ja sakta hai.
    2. Wide Coverage – Suitable frequency aur power ke saath radio signals relatively large areas cover kar sakte hain.
    3. Mobility – Devices move karte hue bhi communication maintain kar sakte hain, jaise mobile phones aur Wi-Fi devices.
    4. Easy Deployment – Remote ya difficult locations me cable bichane ke comparison me wireless infrastructure deploy karna easier ho sakta hai.
    5. Broadcast Capability – Ek transmitter ka signal multiple receivers simultaneously receive kar sakte hain.
    6. Supports Many Technologies – Wi-Fi, Bluetooth, cellular, radio communication etc. radio-frequency electromagnetic waves ka use karte hain.
  - **Disadvantages**
    1. Interference – Other radio signals aur electromagnetic sources unwanted interference create kar sakte hain.
    2. Shared Medium – Same frequency/channel ko multiple devices use kar sakte hain, jisse congestion aur collisions/interference ho sakta hai.
    3. Security Risk – Signal air me propagate karta hai, isliye nearby attacker compatible equipment se signal capture karne ki koshish kar sakta hai.
    4. Signal Attenuation – Distance badhne par radio signal generally weak hota jata hai.
    5. Obstacles ka Effect – Walls, buildings, trees aur terrain signal ko reflect, absorb, diffract ya scatter kar sakte hain.
    6. Jamming Risk – Deliberate interference create karke wireless communication ko disrupt kiya ja sakta hai.
    7. Limited Spectrum – Available radio-frequency spectrum limited hai, isliye frequencies ko efficiently manage/share karna padta hai.
2. Microwaves - Microwaves high-frequency electromagnetic waves hoti hain jo mainly line-of-sight wireless communication me data transmit karne ke liye use hoti hain, jaise point-to-point links, satellite communication, radar aur kuch cellular communication systems me.
  - **How it works**
    1. Data generate hota hai – Computer, router, telephone system ya kisi network device se digital data 0 aur 1 ke form me generate hota hai.
    2. Data electrical signal me process hota hai – Communication equipment is digital data ko transmission ke liye suitable electrical/baseband signal me convert aur process karta hai.
    3. Microwave carrier generate hoti hai – Transmitter ek high-frequency electromagnetic carrier signal generate karta hai jise microwave frequency range me operate karaya jata hai.
    4. Data carrier par modulate hota hai – Original data ko microwave carrier ke amplitude, frequency ya phase jaise properties me encode kiya jata hai, taki data microwave signal ke through transmit ho sake.
    5. Transmitter signal ko amplify karta hai – Required transmission distance ke according microwave signal ko suitable power level tak amplify kiya jata hai.
    6. Directional antenna signal ko focus karta hai – Special highly directional antenna microwave energy ko broad area me spread karne ke bajay ek relatively narrow beam me particular direction me focus karta hai.
    7. Microwave space me propagate karti hai – Focused electromagnetic wave air/space ke through transmitter antenna se receiver antenna ki direction me travel karti hai; terrestrial microwave links me generally clear line-of-sight required hota hai.
    8. Obstacles signal ko affect kar sakte hain – Building, mountain, trees ya doosre obstacles beam ko block, reflect ya scatter kar sakte hain, jiski wajah se signal weak ya distorted ho sakta hai.
    9. Earth curvature bhi limitation hai – Microwave generally straight-line propagation karti hai, isliye bahut long terrestrial distances par Earth ki curvature ki wajah se direct link possible nahi hota; isi liye relay towers use karke link ko multiple hops me divide kiya ja sakta hai.
    10. Receiving antenna signal capture karta hai – Doosre end ka directional antenna incoming microwave energy ko receive karke usse receiver ke electrical signal me convert karta hai.
    11. Receiver desired signal ko filter karta hai – Receiver required microwave frequency/channel ko select karta hai aur unwanted signals aur noise ko filter karta hai.
    12. Signal demodulate hota hai – Receiver microwave carrier se originally encoded information ko extract karta hai, jise demodulation kehte hain.
    13. Original data recover hota hai – Demodulated signal ko digital circuitry process karke original 0s aur 1s recover kiye jaate hain.

  - **Advantage**
    1. Wireless Transmission – Physical cable bichane ki zarurat nahi hoti, isliye difficult locations ke beech communication establish kiya ja sakta hai.
    2. High Data Capacity – High-frequency microwave bands relatively high bandwidth provide kar sakte hain, isliye high-speed data communication possible hai.
    3. Long-Distance Links – Proper line-of-sight aur relay towers ke saath long-distance communication establish kiya ja sakta hai.
    4. Fast Deployment – Fiber/copper cable infrastructure bichane ke comparison me point-to-point microwave link comparatively quickly deploy kiya ja sakta hai.
    5. Directional Transmission – High-gain directional antennas signal ko narrow beam me focus karte hain, jisse unwanted radiation aur interference ko reduce karne me help milti hai.
  - **Disadvantage**
    1. Line-of-Sight Required – Terrestrial microwave links me transmitter aur receiver ke beech generally clear path chahiye hota hai.
    2. Obstacles ka Effect – Buildings, mountains, trees etc. microwave beam ko block ya weaken kar sakte hain.
    3. Weather Sensitivity – Heavy rain aur atmospheric conditions, especially higher microwave frequencies par, signal attenuation badha sakti hain.
    4. Alignment Required – Directional antennas ko accurately align karna padta hai; misalignment se signal quality significantly degrade ho sakti hai.
    5. Relay Infrastructure Required – Very long terrestrial distances par intermediate towers/relay stations ki zarurat pad sakti hai.
3. Infrared - Infrared (IR) electromagnetic radiation ka ek range hai jo visible red light ke baad electromagnetic spectrum me aata hai, jiska wavelength visible red light se longer aur frequency lower hoti hai, aur iska use short-range wireless communication jaise remote controls aur kuch data links me kiya ja sakta hai.
  - **How it Works**
  - **Advantages**
  - **Disadvantages**
4. Satellite Communication
## 4. Media Conversion Devices 
Media Conversion Devices wo devices hote hain jo ek type ke signal ya transmission medium ko dusre type ke signal ya medium me convert karte hain taki different networks communicate kar saken.
## 5. Interface Devices 
Interface Devices wo hardware components hote hain jo end devices (computer, server etc.) aur network medium ke beech communication interface provide karte hain.
