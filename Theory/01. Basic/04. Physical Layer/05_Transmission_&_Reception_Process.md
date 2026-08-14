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

### Transmitter bits ko signal representation mein kaisa convert karta hai? 

## Signal Conditioning

## Complete Transmitter Path
