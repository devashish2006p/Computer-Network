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
       - **Encoding Techniques**
         1. Non-Return-to-Zero (NRZ) - Isme ek bit interval ke poore duration mein 1 ko ek fixed non-zero voltage aur 0 ko 0V se represent kiya jata hai, aur signal bit ke beech mein automatically 0V par return nahi karta.
            - **Internal Mechanism**
              1. Sabse pehle sender ke paas digital data 0 aur 1 ke sequence ke form mein hota hai, jaise 10110.
              2. Sender ka physical-layer hardware (PHY/transmitter) is binary data ko bits ke sequence ke roop mein process karta hai.
              3. Har bit ka ek fixed time duration hota hai, jise hum bit period kehte hain; isi fixed timing ke according bits one-by-one transmit hote hain.
              4. NRZ ek predefined rule provide karta hai ki har bit ko physical signal ke kis level se represent karna hai.
              5. Unipolar NRZ ke example mein 1 ko +V aur 0 ko 0V se represent kiya ja sakta hai.
              6. Transmitter pehle bit ko dekhta hai aur us bit ke corresponding voltage level ko physical transmission line par generate karta hai.
              7. Agar bit 1 hai, to transmitter +V signal ko poore bit period tak maintain karta hai.
              8. Agar next bit 0 hai, to transmitter signal ko 0V par change karta hai aur poore next bit period tak 0V maintain karta hai.
              9. Agar consecutive bits same hain, jaise 111, to signal bhi un teeno bit periods ke dauran same voltage level par continuously bana reh sakta hai.
              10. Agar bit change hota hai, jaise 1 → 0, to transmitter corresponding signal level ko +V → 0V change karta hai.
              11. NRZ mein signal ek bit period ke beech mein automatically zero level par return nahi karta, isi property ki wajah se iska naam Non-Return-to-Zero hai.
              12. process se binary data ka ek electrical signal waveform/pattern ban jata hai, jaise 1010 ke liye +V → 0V → +V → 0V.
              13. Ye electrical signal transmission medium, jaise copper cable, ke through receiver ki taraf travel karta hai.
              14. Signal receiver tak pahunchne par receiver us incoming electrical signal ke voltage level ko detect karta hai.
              15. Receiver ko pata hota hai ki kaunsi NRZ scheme use hui hai, isliye woh received signal level ko corresponding bit ke roop mein interpret karta hai.
              16. Unipolar NRZ mein receiver +V ko 1 aur 0V ko 0 interpret karega, aur is tarah original binary sequence recover karega.
                  
         2. Return-to-Zero (RZ) - RZ ek line-coding technique hai jisme har bit ko represent karne ke baad signal, usi bit ke time interval ke andar, 0V par return kar jata hai.
            - **Internal Mechanism**
              1. Sender ke paas binary data 0 aur 1 ke form mein hota hai, jaise 101.
              2. RZ technique har bit ke liye ek fixed time period rakhti hai, jise bit period kehte hain.
              3. RZ mein ek rule hota hai ki 1 ko signal dekar represent kiya jayega, lekin signal ko poore bit period tak maintain nahi kiya jayega.
              4. Unipolar RZ ke example mein 1 ke liye pehle half bit period mein +V signal diya jata hai.
              5. Usi 1 ke second half mein signal automatically 0V par return kar jata hai.
              6. Isliye ek 1 ke andar hi signal ka transition +V → 0V ho jata hai.
              7. 0 ko 0V se represent kiya jata hai, isliye 0 ke poore bit period mein signal 0V rehta hai.
              8. Agar data 101 hai, to transmitter pehle 1 ke liye +V → 0V, phir 0 ke liye 0V → 0V, aur phir 1 ke liye dobara +V → 0V generate karega.
              9. Is tarah binary data ek electrical/physical signal pattern mein convert ho jata hai.
              10. Ye signal transmission medium ke through receiver tak travel karta hai.
              11. Receiver incoming signal ko observe karta hai aur signal ke presence/absence aur timing ke according original 0 aur 1 ko identify karta hai.
              12. Har 1 ke andar signal ka zero par return hona receiver ko regular timing information provide karta hai, jisse synchronization/clock recovery easier hoti hai.
              13. Iska disadvantage ye hai ki signal mein NRZ ke comparison mein zyada transitions hote hain, isliye RZ ko generally zyada bandwidth chahiye hoti hai.
                  
     2. Polar - Unipolar Line Coding ek line-coding technique hai jisme 0 aur 1 ko represent karne ke liye signal ki sirf ek polarity (positive ya negative) use hoti hai, aur doosre bit ke liye usually zero-voltage level use hota hai.
    3. Bipolar - Bipolar Line Coding ek line-coding technique hai jisme 0 aur 1 ko represent karne ke liye +V, 0V aur −V — teeno voltage levels use kiye ja sakte hain.
    4. Multilevel - Multilevel Line Coding ek technique hai jisme sirf 0 aur 1 ko ek-ek voltage level se represent karne ke bajay, multiple voltage/signal levels ko use karke zyada information ko efficiently represent kiya jata hai.
## 2. Block Coding
Block Coding ek encoding technique hai jisme original bits ko chhote fixed-size blocks mein divide karke, har block ko ek predefined naye bit-pattern/block mein convert kiya jata hai, taaki transmission ke dauran synchronization aur data reliability improve ho sake.
Important: Block coding mein bits ko voltage/signal mein directly convert nahi kiya ja raha; pehle bits ke blocks ko ek naye bit pattern mein map kiya ja raha hai, jise baad mein line coding/modulation ke through physical signal banaya ja sakta hai.

## 3. Scrambling

## 4. Pulse Encoding

## 5. Modulation
