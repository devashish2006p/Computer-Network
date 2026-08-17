# 1. About
Transmission & Reception Process woh poora process hai jisme sender ke data ko physical signal mein convert karke transmission medium se receiver tak bheja jata hai, aur receiver us signal ko detect karke wapas original data/bits mein convert karta hai.

# 2. Data Prepration 
Data Preparation ka matlab hai sender ke paas jo data hota hai, usko physical transmission ke liye suitable digital bitstream aur proper timing ke form mein ready karna.

## Data Source
Data source woh jagah hoti hai jahan se transmit kiya jaane wala original information/data sender system ko milta hai. 

- **Application/User sa sender system tak data kaisa aata hai?**
  1. User koi action karta hai, jaise browser mein message type karke Send karta hai.
  2. Application us user input ko receive karti hai aur usko apne required data format mein rakhti hai.
  3. Application OS ke networking interface (socket/API) ko data deti hai, kyunki application directly network hardware se normally baat nahi karti.
  4. OS/networking stack application se ye data receive karta hai aur usko network par bhejne ke liye process karta hai.
  5. Data gradually network protocols ke through process hota hai, jahan different layers apna required information add karti hain.
  6. End mein Network/Link layers ke paas bhejne layak digital data/frames aa jate hain, jise NIC/PHY further physical transmission ke liye process karta hai.

## Binary Representation of Data
Binary representation ka matlab hai kisi bhi digital data ko 0 aur 1 ke form mein represent karna, taaki computer us data ko digitally process aur transmit kar sake.

- **Data ka Binary representation kaisa hota hai?**
  1. Sabse pehle computer ko koi information milti hai, jaise character A, number 25, image ka pixel, ya audio ka sample.
  2. Computer us information ke type ko identify karta hai, kyunki text, number, image, audio etc. ko represent karne ke rules alag hote hain.
  3. Us information ke liye ek predefined representation/encoding rule use hota hai.
  4. Rule information ko numerical values mein map karta hai.
  Example: character A → ASCII value 65.
  5. Ye numerical value computer ke binary number system mein convert hoti hai.
  Example: 65 → 01000001.
  6. Is binary representation ka har 0 ya 1 ek bit hota hai.
  7. Multiple bits milkar larger data values represent karte hain, jaise 01000001 ek 8-bit value hai.
  8. Hardware in bits ko actual physical states ke through represent karta hai, jaise memory mein electrical charge ki state ya digital circuit mein voltage range.
  9. Isliye software level par hume 0 aur 1 dikhte hain, jabki hardware level par actually physical states/signals exist karte hain.
  10. Transmission ke case mein ye binary bitstream baad mein Physical Layer ke encoding/modulation mechanism ke through transmission signal mein represent kiya jata hai.
 

## Bit Stream
Bitstream ka matlab hai 0 aur 1 bits ka ek ordered sequence, jisme bits ek particular order mein continuously arranged hote hain, jaise 101100101.

- **Bits Sequence ma kaisa arrange hote hai?**
  1. Sabse pehle sender ke paas original data hota hai, jaise text, image, file ya koi aur digital information.
  2. Data ko uske representation/encoding rule ke according binary values mein convert kiya jata hai.
  Example: A → 01000001.
  3. Agar data mein multiple values/characters hain, to unki binary representations unke original order mein rakhi jaati hain.
  Example: AB → 01000001 01000010.
  4. In binary groups ko sequence mein concatenate kiya jata hai, yani unke beech ka separation hata kar ek continuous bit sequence ban jata hai:
  0100000101000010.
  5. Is sequence mein har bit ki position important hoti hai, kyunki receiver ko bits same order mein milne chahiye.
  6. Data ko transmit karte waqt sender is sequence ko transmission order mein one-by-one process karta hai, jaise pehle bit 0, phir 1, phir 0, phir 0 etc.
  7. Har bit ko ek fixed timing/bit period ke according process kiya ja sakta hai, taaki sender ko pata ho ki next bit kab transmit karni hai.
  8. Ye ordered sequence hi bitstream hai, jise aage encoding/line coding ya modulation ke mechanism ke through physical signal mein represent kiya jata hai.
 
## Bit Timing
Bit timing ka matlab hai har bit ko transmit/represent karne ke liye ek fixed amount of time dena, taaki sender aur receiver dono ko pata rahe ki ek bit kab start hoti hai aur kab khatam hoti hai. Agr bit timing na ho to receiver ko ya pta he nhi chalega ki signal ko kis point par read karke ek bit mana jaye.

## Clock ka basic role
1. Digital system mein clock ek regular timing signal hota hai, jo fixed intervals par repeat hota hai.
2. Clock ka har cycle transmitter ko ek timing reference deta hai, yani transmitter ko pata hota hai ki data processing/transmission ka next timing point kab hai.
3. Maan lo clock ki frequency 1 MHz hai; iska matlab clock 1 second mein 10 lakh cycles karta hai.
4. Agar system design mein 1 clock cycle = 1 bit period hai, to transmitter har clock cycle mein ek bit ko transmission ke liye process karega.
```
Example:
Clock:  ↑    ↑    ↑    ↑
        |----|----|----|
Bit:     1    0    1    1
```
5. Pehle clock event par transmitter first bit 1 process karta hai.
6. Agle clock event par transmitter second bit 0 process karta hai.
7. Isi tarah har timing interval par next bit process hoti hai.
8. Isse sender ke paas ek regular rhythm hota hai, jiske according bits ko signal mein represent karke transmit kiya jata hai.

---

# 3. Encoding & Signal Generation

**I hade already compleated this topic in previous file so click on this link to access that file -> [04. Encoding](04_Encoding.md)**

---

# 4. Transmitter/PHY Operation

## PHY kya hai
PHY (Physical Layer Transceiver) ek hardware component/circuit hota hai jo digital data/bits ko physical signal (electrical, optical ya RF) mein convert karke medium par transmit karta hai aur receive hone wale physical signal ko wapas digital data mein convert karta hai.
### Purpose of PHY
  1. PHY digital data/bits ko physical signal mein convert karta hai, taaki data transmission medium par bheja ja sake.
  2. PHY appropriate signal generate karta hai, jaise copper ke liye electrical, fiber ke liye optical aur wireless ke liye RF signal.
  3. PHY transmitted signal ko medium ke according suitable banata hai, taaki woh required physical medium par properly travel kar sake.
  4. PHY received physical signal ko detect aur interpret karke digital data/bits mein convert karta hai.
  5. PHY transmitter aur receiver ke beech physical communication establish karne mein help karta hai, yani actual physical link par data transmission possible banata hai.
     
### PHY bits ko physical signal ma kaisa convert karta hai?
  1. PHY ko MAC/Data link layer sa digital bitstream milta hai jaisa 1010.
  2. PHY transmitter pehle bits ko apne transmission format ka according process karta hai, yani required encoding, scrambling ya modulation rules apply karta hai.
  3. Bits ko signal states/symbols ma map kiya jata hai. Ex - NRZ ma 1 -> +v and 0 -> 0v.
  4. PHY ka digital circuitry decide karta hai ki har particular time interval ma transmitter ko kya signal output karna hai.
  5. Ya digital decision transmitter ka analog/output circuitry ko control karta hai. Mtlb circuitry ko instruction   milta hai ki ab output ko kis current level ya waveform par rakhna hai.
  6. Transmitter circuitry required electrical waveform generate karta hai.
  7. Signal conditioning circuitry signal ko transmission ka liye suitable banati hai, jaisa required amplitude aur waveform characteristics maintain karna.
  8. Phir PHY ka physical interface signal ko transmission medium tak deliver karta hai. Copper main electrical signal connector par aate hai.
  9. Copper cable ma voltage/current ka changing pattern propagate karta hai, aur receiver side par wahi changing physical signal detect hota hai. 

### PHY physical signal ko data ma kaisa convert karta hai?
1. Medium se physical signal receiver PHY tak aata hai.
2. Receiver circuitry incoming signal ko detect karti hai, yani signal mein actual changes/levels ko measure karti hai.
3. Signal conditioning ki ja sakti hai, taaki noise/distortion ke bawajood signal ko properly interpret kiya ja sake.
4. Receiver timing/clock ko recover karta hai, taaki usse pata chale ki signal ko kis timing par read karna hai.
5. Demodulation/decoding rule apply hota hai, jisse physical signal ko corresponding symbols/bits mein convert kiya jata hai.
6. Is tarah receiver ko original bitstream 1010 recover ho jata hai.
7. Ye bits phir PHY se MAC/Data Link layer ko pass hote hain.

### Relationship between PHY and MAC/Data Link Layer 
MAC/Data Link Layer ka kaam hota hai data ko network frame ke form mein prepare/manage karna, jabki PHY ka kaam us frame ke digital bits ko actual physical signal mein transmit karna aur received signal ko wapas bits mein recover karna hota hai.

## Transmitter 
Transmitter ek hardware circuitry/system ka part hota hai jo digital bits ko process karke unki encoding/modulation ke according actual physical signal generate karta hai aur us signal ko transmission medium par bhejta hai.

### Basic Role of Transmitter
  1. Transmitter PHY se digital bits/data receive karta hai.
  2. Ye bits ko required encoding ya modulation scheme ke according signal representation mein map karta hai.
  3. Transmitter circuitry us representation ke according actual physical signal generate karti hai.
  4. Generated signal ko transmission medium ke suitable form mein prepare karta hai, jaise electrical signal, optical signal ya RF signal.
  5. Finally, transmitter generated physical signal ko cable, fiber ya wireless medium par send karta hai.
     
### Transmitter ko digital data kaha sa milta hai
Transmitter ko digital data normally MAC/Data Link Layer se milta hai, jo network frame ke data ko digital bitstream ke form mein PHY ko handoff karta hai.


## Signal Conditioning
Signal conditioning ka matlab hai generated physical signal ko transmission medium par bhejne se pehle uski physical characteristics ko suitable banana, taaki signal medium mein reliably travel kar sake aur receiver usse correctly detect kar sake.
### Basic Mechanism
  1. Transmitter signal generate karta hai.
  2. Signal conditioning circuitry signal ko modify/prepare karti hai.
  3. Signal ka amplitude/level appropriate kiya ja sakta hai.
  4. Signal ki waveform/shape ko suitable banaya ja sakta hai.
  5. Unwanted frequency components ko filter kiya ja sakta hai.
  6. Phir conditioned signal ko physical medium par transmit kiya jata hai.
## Complete Transmitter Path
  1. MAC / Data Link Layer → frame prepare karke PHY ko digital bits deta hai.
  2. Digital Bitstream → 101100... jaise ordered bits PHY transmitter ke input mein aate hain.
  3. Encoding / Modulation → bits ko defined signal representation/symbols mein map kiya jata hai.
  4. Signal Generation → transmitter circuitry us representation ke according actual electrical/optical/RF signal generate karti hai.
  5. Signal Conditioning → signal ko transmission ke liye suitable characteristics mein prepare kiya jata hai.
  6. Physical Interface / Driver → generated signal ko required physical output level par medium/interface tak drive karta hai.
  7. Connector → signal ko actual cable/fiber interface se connect karta hai.
  8. Transmission Medium → electrical signal copper mein, optical signal fiber mein, ya RF signal wireless medium mein travel karta hai.
     
---
# 5. Signal Transmission in Medium
## Signal Propagation
Signal propagation ka matlab hai transmitter se generate hua physical signal transmission medium ke through receiver ki taraf travel/spread karna, jiske dauran signal medium ki physical properties ke according behave karta hai.

### Transmitter sa receiver tak signal kaisa travel karta hai?
1. Transmitter physical signal generate karta hai, jaise copper ke liye changing voltage/current pattern.
2. Transmitter signal ko transmission medium mein launch karta hai, jaise electrical signal copper cable ke conductor par apply hota hai.
3. Medium ki physical properties signal ko propagate karne deti hain, yani signal ki energy/information transmitter se receiver ki direction mein travel karti hai.
4. Signal medium ke andar continuously propagate karta hai, lekin ye ideal vacuum jaisa perfectly unchanged travel nahi karta.
5. Travel karte waqt signal ki strength gradually reduce ho sakti hai, jise attenuation kehte hain.
6. Medium aur external environment ki wajah se unwanted energy signal mein add ho sakti hai, jise broadly noise/interference kehte hain.
7. Long distance ya medium ki characteristics ki wajah se signal ka original shape bhi change ho sakta hai, jise distortion kehte hain.
8. Signal ko transmitter se receiver tak pahunchne mein finite time lagta hai, jise propagation delay kehte hain.
9. Receiver side par incoming physical signal PHY receive circuitry tak pahunchta hai.
10. Receiver signal ko detect, condition aur interpret karke usmein represented bits recover karta hai.
    
### Propagation Path kya hota hai?
Propagation path ka matlab hai woh physical route/path jiske through transmitter se generated signal medium ke andar travel karke receiver tak pahunchta hai.
For Example :- 
  - Twisted Pair cable ke twisted conductors signal ko propagation path provide karta hai.
  - Coaxial cable ka inner coductor aur surrounding structure ka along signal propagate karta hai.
  - Fiber ka core light signal ko propagation path provide karta hai.
  - Wireless ma transmitter anteena sa receiver anteena tak air/space propagation path hota hai.
    
## Transmission Medium ka role
1. Transmission medium transmitter aur receiver ke beech physical path provide karta hai, jiske through signal travel karta hai.
2. Medium generated physical signal ko carry/propagate karta hai, jaise copper electrical signal aur fiber light signal ko carry karta hai.
3. Medium signal ke propagation characteristics ko affect karta hai, jaise signal kitni speed se travel karega aur kitni distance tak reliably ja payega.
4. Medium signal ki quality ko affect karta hai, kyunki usmein attenuation, noise, interference aur distortion ho sakte hain.
5. Medium ki physical properties maximum transmission distance aur achievable data rate ko affect karti hain.

# Differential Signaling
Differential signaling mein ek electrical signal ko ek single wire ke voltage ke reference se nahi, balki do conductors ke beech ke voltage difference ke form mein transmit kiya jata hai.
  - **Internal Mechanism**
    1. Transmitter do wires/conductors use karta hai signal ko carry karne ka lia.
    2. Same information ko dono wires par opposite electrical levels/polarities ka sath represent kiya jata hai.
    3. Receiver dono wires ka voltage measure karta hai aur unka beech ka difference calculate karta hai.
    4. Agr difference positive hai, receiver ek state/bit interpret kar shakta hai, agr negative hai, dosri state.
    5. Agr external noise dono wires par approximately same amount main add ho jaye to receiver ka differential measurement ma woh largely cancel ho jata hai.
    6. Isi wajah sa differential signaling noise immunity improve karne ma useful hota hai, especially copper communication links mein.
       
## Optical Signal 
Optical signal ek information-carrying light signal hota hai, jisme data ko light ki properties ke controlled changes ke through represent kiya jata hai aur ye signal fiber optic cable ke andar travel karta hai.

### Electrical data ko optical signal ma kaisa represent kiya jata hai?
1. Electrical/digital data PHY ko milta hai jaisa 1010.
2. Optical transmitter bits ko required optical signaling rule ka according process karta hai.
3. Ya electrical control signal optical source ko control karta hai, jaisa laser diode ya LED.
4. Optical source electrical energy ko light main convert karta hai.
5. Data ka according light ki property change karayi jati hai.
6. ```
   Electrical data
         ↓
    Control signal
         ↓
    Laser / LED
         ↓
    Light pattern
         ↓
        Fiber
   ```
7. Fiber ka ander actual light electromagnetic radiation ka form main propagate karti hai aur ushki changing property mein information encoded hota hai.
8. Receiver side par photodetector incoming light ko detect karke usse electrical signal ma convert karta hai.
9. Phir receiver us electrical signal ko process karke original bits recover karta hai. 
         
### Light pulses fiber mein kaisa travel karte hai?
Fiber mein transmitter data ke according light ko pulses/patterns ke form mein modulate karta hai, aur ye changing light signal fiber ke core ke andar guided hokar transmitter se receiver tak propagate karta hai, jahan receiver us light pattern ko detect karke original data recover karta hai.
### Core aur Cladding ka basic role
- Core fiber ka beech wala transparent part hota hai, jiske andar light signal actually propagate karta hai.
- Cladding core ke around ek layer hoti hai, jo light ko core ke andar confined/guided rakhne mein help karti hai, taaki light signal bahar na nikle.
- Core aur cladding ke different refractive indices ki wajah se light fiber ke andar guided rehti hai, mainly Total Internal Reflection (TIR) ke principle se.
  
### Total Internal Reflection (TIR) ka basic concept
TIR (Total Internal Reflection) ek optical phenomenon hai jisme light ek higher refractive index wale medium se lower refractive index wale medium ki boundary par aati hai aur certain angle se zyada angle par aane par bahar refract hone ke bajay poori tarah se wapas reflect ho jaati hai.


## Electromagnetic/RF Signal Transmission
Electromagnetic/RF signal transmission mein data ko electromagnetic wave ke changing properties ke form mein represent karke transmitter antenna se space/air ke through receiver antenna tak bheja jata hai.

### Electrical signal se electromagnetic/RF wave converstion
1. PHY bits ko modulation ke through ek rapidly changing electrical signal mein represent karta hai.
2. Ye alternating electrical current/voltage transmitter ke RF circuitry se antenna tak pahunchta hai.
3. Antenna mein changing current electrons ko accelerate/oscillate karwata hai.
4. Accelerating charges ke around changing electric aur magnetic fields develop hote hain.
5. Ye changing electric + magnetic fields ek doosre se coupled hokar electromagnetic wave banate hain.
6. Antenna is electromagnetic energy ko air/space mein radiate karta hai.

### Antenna ka basic role.
Antenna ka basic role electrical RF signal ko electromagnetic wave mein convert karke space/air mein radiate karna, aur receiver side par electromagnetic wave ko receive karke electrical RF signal mein convert karna hai.

### Antenna signal ko electromagnetic wave mein kaise radiate karta hai.
- **How Antenna transmit**
  1. Transmitter antenna mein rapidly changing electrical current bhejta hai.
  2. Is changing current ki wajah se antenna ke around changing electric field develop hota hai.
  3. Changing current ki wajah se changing magnetic field bhi develop hota hai.
  4. Ye changing electric aur magnetic fields ek doosre se linked hokar electromagnetic energy ko antenna se bahar propagate karte hain.
  5. Isi propagating electromagnetic energy ko hum electromagnetic/RF wave kehte hain. 
- **How Antenna Receivs**
  1. Bahar se aati hui electromagnetic wave antenna tak pahunchti hai.
  2. Wave ka changing electric field antenna ke electrons par force apply karta hai.
  3. Electrons antenna mein changing current/voltage produce karte hain.
  4. Receiver circuitry is tiny electrical signal ko detect aur amplify/process karti hai.
  5. Phir demodulation ke through original information recover hoti hai.
     
### Air/space mein wave ka basic propagation.
1. Transmitter antenna RF electromagnetic wave radiate karta hai.
2. Wave antenna se bahar ki taraf spread hoti hai aur space mein propagate karti hai.
3. Wave ke andar changing electric field aur magnetic field hote hain, jo ek doosre ke saath coupled hote hain.
4. Ye changing fields aage-aage electromagnetic energy ko propagate karte hain; isliye information transmitter se receiver ki taraf travel karti hai.
5. Air/space mein travel karte waqt wave ki strength distance badhne ke saath kam hoti hai.
6. Buildings, walls, objects etc. se wave reflect, absorb, scatter ya diffract bhi ho sakti hai.
7. Receiver antenna ke location par wave pahunchti hai aur uske changing electric field ki wajah se antenna mein electrical RF signal induce hota hai.

## Signal Attenuation
### Attenuation kya hai?
Signal attenuation ka matlab hai transmission medium mein travel karte waqt signal ki strength/energy ka gradually kam hona.

### Distance badhne par signal weak kyun hota hai?
### Copper, fiber aur wireless mein attenuation ka basic behavior.
### Signal strength ka basic concept.

## Noise aur Interface
### Noise kya hai?
### Signal mein unwanted energy kaise add hoti hai?
### EMI ka basic concept.
### Crosstalk ka basic concept.
### Signal aur noise ka basic difference.

## Signal Distortion
### Distortion kya hai?
### Signal ka original shape kyun change ho sakta hai?
### Dispersion ka basic concept.
### Copper aur fiber mein distortion/dispersion ka basic idea.

## Propagation Delay 
### Propagation delay kya hai?
### Signal ko transmitter se receiver tak pahunchne mein time kyun lagta hai?
### Distance aur propagation speed ka relationship.
### Propagation delay vs transmission time ka basic difference.

## Bandwidth aur Frequency Range 
Bandwidth kya hai?
Signal ki frequency ka basic concept.
Medium ki bandwidth transmission ko kaise affect karti hai?
Higher bandwidth ka basic meaning.

## Signal-to-Noise Ratio (SNR)
### SNR kya hai?
### Signal strength aur noise strength ka relationship.
### SNR high/low hone ka basic effect.
### Reliable communication mein SNR important kyun hai?

## Medium ki Transmission Limitations
