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
  - **Categories of Block Coding**
    1. Fixed Length Block Coding - Isme har input block ko fixed number of bits wale output codeword mein convert kiya jata hai.
      - **Encoding Techniques**
        1. 4B/5B - Isme original data ke 4 bits ko 5-bit codeword mein convert kiya jata hai, jisme extra 1 bit redundancy ke roop mein hoti hai aur aise bit patterns choose kiye jaate hain jo transmission mein required signal transitions maintain karne mein help karein.
        2. 8B/10B - Isme original data ke 8 bits ko 10-bit codeword mein convert kiya jata hai, jisme 2 extra bits ki help se balanced bit patterns maintain kiye jaate hain, taaki signal mein excessive DC component na bane aur receiver ko reliable synchronization mile.
        3. 64B/66B - 64B/66B: Isme original data ke 64 bits ko 66-bit block mein convert kiya jata hai, jisme 2 additional bits header ke roop mein use hote hain jo receiver ko batate hain ki block mein data kis type ka hai aur block boundary identify karne mein help karte hain.
        4. 128B/130B - Isme original data ke 128 bits ko 130-bit block mein convert kiya jata hai, jisme 2-bit synchronization/header information add hoti hai jo receiver ko block boundary identify karne aur data/control block ko distinguish karne mein help karti hai.
    2. Variable Length Block Coding - Isme different input data patterns ko different length ke output codewords mein convert kiya ja sakta hai.
       - **Encoding Techniques**
         1. Huffman Coding - Isme data ke symbols ki frequency ko dekha jata hai, aur jo symbol zyada baar aata hai usko chhota bit code aur jo kam baar aata hai usko bada bit code diya jata hai, jisse overall data ka size kam ho sake.
         2. Run Length Encoding (RLE) - Isme ek hi bit ya symbol ke continuously repeat hone wale sequence ko count ke saath represent kiya jata hai, jaise AAAAA ko 5A ke form mein represent karke data ko compact kiya jata hai.
## 3. Scrambling
Scrambling ek technique hai jisme  data ke bit pattern ko controlled tarike se change kiya jata hai, taaki long sequence of same bits (000000... ya 111111...) na aaye aur signal mein sufficient transitions bane rahein.
  - **Internal Mechanism**
  
## 4. Pulse Encoding

## 5. Modulation
