# 1. Encoding
Encoding ek process hai jisme computer ke digital data, yani 0 aur 1 ko signal mein convert kiya jata hai, taaki us data ko communication system ke through transmit, receive aur correctly interpret kiya ja sake.

# 2. Categories of Encoding
## 1. Line Coding
Line coding ek technique hai jisme digital bits (0 aur 1) ko predefined voltage/signal levels ya transitions ke pattern mein represent kiya jata hai, taaki un bits ko physical medium par transmit kiya ja sake.
- **Internal Mechansm**
  1. Sender ke paas original data 0 aur 1 ke form mein hota hai.
  2. Line coding technique ek fixed rule choose karti hai ki 0 aur 1 ko physical signal mein kaise represent karna hai.
  3. Is rule ke according har bit ke liye ek particular voltage level ya signal transition decide hota hai.
  4. Example ke liye, kisi technique mein 1 = high voltage aur 0 = low voltage ho sakta hai.
  5. Sender ka physical hardware, jaise NIC ka PHY, in rules ke according actual electrical ya optical signal generate karta hai.
  6. Ye signal cable ya kisi doosre physical medium ke through receiver ki taraf travel karta hai.
  7. Signal travel karte waqt weak, noisy ya distorted ho sakta hai, lekin receiver us signal ko detect karne ki koshish karta hai.
  8. Receiver signal ke voltage level ya transition ko dekhta hai aur identify karta hai ki sender ne 0 bheja tha ya 1.
  9. Receiver ko pehle se pata hota hai ki sender ne kaunsi line-coding technique use ki hai, isliye woh usi rule ke according signal ko interpret karta hai.
  10. Is process ke end mein receiver ko original binary data 0 aur 1 ke form mein mil jata hai.

  - **Categories of Line Coding**
     1. Unipolar - Unipolar Line Coding ek line-coding technique hai jisme 0 aur 1 ko represent karne ke liye signal ki sirf ek polarity (positive ya negative) use hoti hai, aur doosre bit ke liye usually zero-voltage level use hota hai.
      
     2. Polar - Polar encoding ek digital line-encoding technique hai jisme binary bits (0 aur 1) ko represent karne ke liye do opposite voltage polarity levels, yani ek positive level aur ek negative level, use kiye jate hain.
    3. Bipolar - Bipolar Line Coding ek line-coding technique hai jisme 0 aur 1 ko represent karne ke liye +V, 0V aur −V — teeno voltage levels use kiye ja sakte hain.
    4. Multilevel - Multilevel Line Coding ek technique hai jisme sirf 0 aur 1 ko ek-ek voltage level se represent karne ke bajay, multiple voltage/signal levels ko use karke zyada information ko efficiently represent kiya jata hai.
## 2. Block Coding
Block Coding ek encoding technique hai jisme original bits ko chhote fixed-size blocks mein divide karke, har block ko ek predefined naye bit-pattern/block mein convert kiya jata hai, taaki transmission ke dauran synchronization aur data reliability improve ho sake.
Important: Block coding mein bits ko voltage/signal mein directly convert nahi kiya ja raha; pehle bits ke blocks ko ek naye bit pattern mein map kiya ja raha hai, jise baad mein line coding/modulation ke through physical signal banaya ja sakta hai.

  - **Internal Mechanism**
    1. Sender ke paas original binary data bits hoti hain.
    2. Encoder original bits ko ek fixed size ke blocks mein divide karta hai.
    3. Har block mein fixed number of bits hote hain, jaise 4 bits.
    4. Encoder ek time par ek block ko input ke roop mein leta hai.
    5. Encoder us input block ke according ek specific codeword generate karta hai.
    6. Codeword mein original data bits ke saath kuch extra bits add ki ja sakti hain.
    7. Ye extra bits redundancy provide karti hain.
    8. Is process ke baad original chhota block ek comparatively bada encoded block ban jata hai.
    9. Encoder isi tarah har input block ko separately encode karta hai.
    10. Saare encoded blocks milkar encoded binary data banate hain.
    11. Ye encoded bits transmission ke liye aage physical layer ke transmission process mein bheji jati hain.
    12. Receiver side par encoded bits receive hoti hain.
    13. Receiver encoded bits ko wahi fixed-size blocks mein divide karta hai.
    14. Decoder har received block ko check karta hai.
    15. Decoder check karta hai ki received block valid codeword hai ya nahi.
    16. Agar block valid hai, to decoder us codeword se original data block ko identify karta hai.
    17. Agar block mein transmission ke wajah se error hua hai, to code ki capability ke according decoder error ko detect ya correct kar sakta hai.
    18. Decoder original data blocks ko recover karta hai.
    19. Saare recovered blocks ko original order mein combine kiya jata hai.
    20. Is tarah sender ki original binary data receiver ko recover ho jati hai.
  - **Encoding Techniques**
        1. 4B/5B - Isme original data ke 4 bits ko 5-bit codeword mein convert kiya jata hai, jisme extra 1 bit redundancy ke roop mein hoti hai aur aise bit patterns choose kiye jaate hain jo transmission mein required signal transitions maintain karne mein help karein.
        2. 8B/10B - Isme original data ke 8 bits ko 10-bit codeword mein convert kiya jata hai, jisme 2 extra bits ki help se balanced bit patterns maintain kiye jaate hain, taaki signal mein excessive DC component na bane aur receiver ko reliable synchronization mile.
        3. 64B/66B - 64B/66B: Isme original data ke 64 bits ko 66-bit block mein convert kiya jata hai, jisme 2 additional bits header ke roop mein use hote hain jo receiver ko batate hain ki block mein data kis type ka hai aur block boundary identify karne mein help karte hain.
        4. 128B/130B - Isme original data ke 128 bits ko 130-bit block mein convert kiya jata hai, jisme 2-bit synchronization/header information add hoti hai jo receiver ko block boundary identify karne aur data/control block ko distinguish karne mein help karti hai.
## 3. Scrambling
Scrambling ek technique hai jisme  data ke bit pattern ko controlled tarike se change kiya jata hai, taaki long sequence of same bits (000000... ya 111111...) na aaye aur signal mein sufficient transitions bane rahein.
  - **Internal Mechanism**
    1. Sender ke paas original binary data bits hoti hain.
    2. Ye bits scrambler ke input mein jaati hain.
    3. Scrambler bits ko ek predefined scrambling rule ke according process karta hai.
    4. Agar data mein bahut saari same bits continuously aa rahi hain, to scrambler unka pattern modify karta hai.
    5. Scrambler ke andar ek scrambling sequence/rule hota hai jo decide karta hai ki output bits kaise generate hongi.
    6. Is process mein input bits ke basis par scrambled output bits generate hoti hain.
    7. Scrambled output mein long continuous 0s ya 1s ko avoid karne ki koshish ki jati hai.
    8. Scrambled bits ko aage line coding/signal generation ke process mein bheja jata hai.
    9. Signal transmission ke baad receiver ko scrambled data receive hota hai.
    10. Receiver ke paas corresponding descrambler hota hai.
    11. Descrambler same predefined rule ka use karke scrambled bits ko process karta hai.
    12. Descrambler original bit pattern ko recover karta hai.
    13. Finally receiver ko original binary data mil jata hai.
  - **Encoding Techniques**
    1. B8ZS - Jab bipolar AMI signal mein 8 consecutive zeros (00000000) aate hain, to B8ZS un 8 zeros ko ek predefined violation pattern se replace karta hai, taaki signal mein transitions bane rahein aur receiver synchronization maintain kar sake.
    2. HDB3 - Jab bipolar AMI signal mein 4 consecutive zeros (0000) aate hain, to HDB3 un zeros ko predefined substitution pattern se replace karta hai, jisme bipolar violation use karke long zero sequence ko avoid kiya jata hai.
## 4. Pulse Encoding
Pulse Encoding ek technique hai jisme binary/digital data ko specific pulses (signal waveforms) ke form mein represent kiya jata hai, taaki un pulses ko communication medium ke through transmit kiya ja sake.
  - **Internal Mechanism**
    1. Sender ke paas digital data bits hoti hain, jaise 10110.
    2. Ye digital data pulse encoder ke input mein jaati hai.
    3. Encoder data ko ek-ek bit ya defined group ke according process karta hai.
    4. Encoder har input bit ko ek specific pulse representation deta hai.
    5. Ye representation predefined rule ke according decide hoti hai, jaise pulse ka amplitude, width, position ya presence/absence.
    6. Is process se original bits ka pulse pattern generate hota hai.
    7. Ye generated pulses physical medium ke according suitable transmission signal ke roop mein bheje jaate hain.
    8. Channel ke through ye pulses receiver tak pahunchte hain.
    9. Receiver received pulse ka amplitude, width, position ya presence/absence observe karta hai.
    10. Receiver predefined rule ke according pulse ko corresponding bit/value mein interpret karta hai.
    11. Is process se receiver original binary data ko recover karta hai.
  - **Encoding Techniques**
    1. PAM (Pulse Amplitude Modulation) - Isme har pulse ki amplitude yani signal ki strength/height ko information ke according change kiya jata hai, jabki pulse ka time position aur basic width fixed reh sakti hai.
    2. PWM (Pulse Width Modulation) - Isme pulse ki width yani pulse kitne time tak HIGH/active rahega usko information ke according change kiya jata hai, jabki pulse ki amplitude generally fixed rakhi jati hai.
    3. PPM (Pulse Position Modulation) - Isme pulse ki position yani pulse time-axis par exactly kab appear hoga usko information ke according change kiya jata hai, jabki pulse ki amplitude aur width generally fixed rakhi jati hai.
    4. PCM (Pulse Code Modulation)  - Isme kisi analog signal ko sample karke, har sample ki amplitude ko quantize karke, phir us quantized value ko binary bits mein encode kiya jata hai, jisse analog information digital data ke form mein transmit ki ja sake.
## 5. Modulation
Modulation ek process hai jisme information/data ko ek carrier signal ke kisi physical property ko change karke us carrier par represent kiya jata hai, taaki information ko communication medium ke through efficiently transmit kiya ja sake.
  - **Internal Mechanism**
    1. Sender ke paas information/data signal hota hai, jo transmit karna hota hai.
    2. Sender ek carrier signal generate karta hai, jo generally higher frequency ka periodic signal hota hai.
    3. Carrier signal khud information contain nahi karta; iska purpose information ko transmission ke liye carry karna hota hai.
    4. Modulator data signal aur carrier signal ko input ke roop mein leta hai.
    5. Modulator data ke according carrier signal ki kisi physical property ko change karta hai.
    6. Carrier ki mainly amplitude, frequency ya phase ko change kiya ja sakta hai.
    7. Agar amplitude change ki ja rahi hai, to Amplitude Modulation (AM) hota hai.
    8. Agar frequency change ki ja rahi hai, to Frequency Modulation (FM) hota hai.
    9. Agar phase change ki ja rahi hai, to Phase Modulation (PM) hota hai.
    10. Is process ke baad carrier modulated signal ban jata hai, jisme original information encoded hoti hai.
    11. Modulated signal ko communication channel ke through receiver tak transmit kiya jata hai.
    12. Receiver par demodulator modulated signal ko receive karta hai.
    13. Demodulator carrier mein kiye gaye changes ko detect karta hai.
    14. In changes ke basis par demodulator original information/data ko recover karta hai.
    15. Final mein receiver ko original information/data mil jata hai.

  - **Encoding Techniques**
    1. AM (Amplitude Modulation) - Isme carrier signal ki amplitude (strength/height) ko information ke according change kiya jata hai, jabki carrier ki frequency generally same rakhi jati hai.
   
    2. FM (Frequency Modulation) - Isme carrier signal ki frequency ko information ke according change kiya jata hai, jabki carrier ki amplitude generally same rakhi jati hai.
   
    3. PM (Phase Modulation) - Isme carrier signal ki phase/position ko information ke according change kiya jata hai, jabki carrier ki amplitude generally same rakhi jati hai.
   
    4. ASK (Amplitude Shift Keying) - Isme digital 0 aur 1 ko represent karne ke liye carrier signal ki amplitude ko different levels par shift kiya jata hai.
   
    5. FSK (Frequency Shift Keying) - Isme digital 0 aur 1 ko represent karne ke liye carrier signal ki frequency ko different frequencies ke beech shift kiya jata hai.
   
    6. PSK (Phase Shift Keying) - Isme digital 0 aur 1 ko represent karne ke liye carrier signal ki phase ko predefined phase states ke beech shift kiya jata hai.
   
    7. QAM (Quadrature Amplitude Modulation) - Isme ek saath amplitude aur phase ko change karke ek symbol mein multiple bits represent kiye ja sakte hain, jisse limited bandwidth mein zyada data transmit kiya ja sakta hai.
