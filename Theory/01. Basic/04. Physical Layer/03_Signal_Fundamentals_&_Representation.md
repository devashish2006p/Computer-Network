# 1. Signal 
Signal ek physical/electrical/optical/electromagnetic form me represent hone wala changing quantity/pattern hai jo information ko ek point se doosre point tak carry karta hai.

# 2. Types of Signal 
## 1. Analog Signal 
Analog signal ek aisa physical signal hai jo information ko represent karne ke liye time ke saath continuously aur smoothly vary karta hai, yani signal ki instantaneous value ek range ke andar bahut saari possible values le sakti hai.

## 2. Digital Signal 
Digital signal ek aisa physical signal hai jo information ko represent karne ke liye continuously change hone ke bajay kuch predefined/discrete signal levels use karta hai, jaise computer ke 0 aur 1 ko different voltage levels, light levels ya electromagnetic states ke through represent karke transmit kiya jata hai.

# 3. Signal's Fundamental Parameters
1. Amplitude → Signal ki amplitude uski strength/magnitude batati hai, yani signal apne reference/normal level se kitna maximum upar ya neeche vary kar raha hai.
2. Frequency (f) → Frequency batati hai ki signal 1 second me kitne complete cycles repeat karta hai, jise Hertz (Hz) me measure kiya jata hai.
3. Time Period (T) → Time period batata hai ki signal ko ek complete cycle repeat karne me kitna time lagta hai, aur ise seconds me measure kiya jata hai.
4. Phase (φ) → Phase batata hai ki kisi particular time par signal ka cycle reference waveform ke comparison me kitna aage ya peeche shifted hai.
5. Wavelength (λ) → Wavelength batati hai ki wave ke ek complete cycle ke corresponding pattern ki space me length kitni hai, aur ise meter me measure kiya jata hai.

## Relation among them
1. Amplitude ↔ Frequency → Dono independent parameters hain; amplitude badalne se frequency necessarily change nahi hoti.
2. Frequency ↔ Time Period → Frequency aur time period inversely related hain; frequency badhe to period ghatega aur frequency ghate to period badhega.
3. Frequency ↔ Wavelength → Same wave speed par frequency badhne se wavelength ghatti hai, aur frequency ghatne se wavelength badhti hai.
4. Time Period ↔ Wavelength → Same wave speed par period badhne se wavelength badhti hai, aur period ghatne se wavelength ghatti hai.
5. Phase ↔ Frequency/Period → Phase signal ki cycle-position batata hai, jabki frequency aur period cycle ke repeat hone ki rate batate hain; phase change hone se frequency ya period necessarily change nahi hota.
6. Amplitude ↔ Phase → Amplitude signal ki strength aur phase cycle ki position batata hai, isliye dono fundamentally independent characteristics hain.
7. Wavelength ↔ Wave Speed → Same frequency par wave speed badhne se wavelength badhti hai, aur wave speed ghatne se wavelength ghatti hai.

# 4. Time Domain Representation
Time-domain representation me hum signal ki value ko time ke saath plot/represent karte hain, jisse pata chalta hai ki signal different moments par kaise change ho raha hai.

## Waveform
Time domain graph ma signal ka jo shape/pattern dekhai deta hai use waveform kehte hai. 

### Time domain representation  of Analog Signal
Analog signal time ke saath continuously vary karta hai, isliye uska waveform generally smooth/continuous variation dikha sakta hai. Like -> ~~~~~~~~~~~~~~. Yani har movement par signal ki value change ho shakti hai. 

### Time domain representation of Digital Signal 
Digital signal predefined signal levels ka beech change karta hai, isiliye time domain graph ma generally distinct levels dekhai dete hai. Like -> ___|‾‾‾|___|‾‾‾‾|___

### Periodic Signal
Agar signal ka waveform regular interval ke baad exactly/consistently repeat hota hai, to use periodic signal kehte hain.
Time-domain graph me iska pattern repeatedly dekhai dega:
pattern → pattern → pattern → pattern

### Aperiodic Signal 
Agar signal ka waveform regularly repeat nahi hota, to use aperiodic signal kehte hain.

# 5. Frequency Domain Representation
Frequency-domain representation ka matlab hai signal ko time ke against nahi, balki usme present different frequencies ke against represent karna, jisme X-axis par frequency aur Y-axis par generally amplitude/power dikhaya jata hai, taaki pata chale ki signal ke andar kaunsi frequencies present hain aur unki strength kitni hai.

## Single Frequency Signal 
Agar signal me essentially ek dominant frequency hai, to frequency-domain representation me ek prominent component/peak us frequency par dikhega.
Matlab time-domain me tum waveform dekh rahe the, aur frequency-domain me us waveform ki frequency composition dekh rahe ho.

## Composite Signal 
Real communication signals aksar simple single-frequency signals nahi hote; unme multiple frequency components ho sakte hain.

Frequency-domain representation un components ko alag-alag frequencies ke around show kar sakta hai.

Isliye frequency domain signal ke frequency ingredients samajhne me useful hai.

## Frequency Spectrum 
Frequency-domain representation me signal ke frequency components ka distribution frequency spectrum kehlata hai.


