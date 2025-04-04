# Dasturmizni EXE fayliga aylantirish

**Avvalo shuni ma'lum qilmoqchimanki, bu xususiyat umumiy rasmiy Mu Editorida mavjud emas va faqat** [**muallif tomonidan ishlab chiqilayotgan Mu muharririning maxsus versiyasi**](https://github.com/roboticsware/mu/releases)**da mavjud.**

Foydalanish usuli oddiy. Birinchidan, _agar siz yaratgan o'yin boshqalarga tarqatilishi uchun yetarli darajada to'liq deb hisoblasangiz, barcha manbalarni to'plash orqali o'yinni avtomatik ravishda bitta bajariladigan fayl (Windows platformasi uchun exe fayli) sifatida yaratish uchun muharrirga o'rnatilgan funksiyadan foydalanishingiz mumkin. Bu funksiya fayllarni, qo'shimcha modullarni va o'yin dasturlash chiqarish uchun zarur bo'lgan resurslarni (rasmlar, ovozlar, fontlar va boshqalar) bitta faylga aylantiradi. Bu sizning o'yiningizni boshqalarga tarqatishni osonlashtiradi va o'yin foydalanuvchilari uchun bitta bajariladigan faylni ikki marta bosish orqali o'yindan zavq olishlari ham qulay._

Misol uchun, keling, 4-bobda birgalikda yaratgan Flappy Bird o'yinini qadoqlab ko'raylik. Birinchi, siz qadoqlamoqchi bo'lgan o'yin manba faylining joylashuvini ko'rib chiqaylik. Muharrirni o'rnatishda u Pygame Zero uchun muharrir tomonidan o'rnatilgan standart papka bo'lgan "akkaunt nomi/mu\_code" da joylashgan bo'lishi mumkin va, albatta, siz uni bu holatda bo'lgani kabi qadoqlab ko'rishingiz mumkin. Biroq, **o'yin bilan bir-biriga bog'liq bo'lmagan fayllarni qadoqlashdan boshqa foyda yo'qligi sababli, bu faqat keraksiz hajmni oshiradi, iloji bo'lsa, faqat o'yin uchun zarur bo'lgan fayllar va resurslarni qadoqlash eng kam isrof usuli bo'ladi.** _Agar siz o'yinni yasashdan boshidanoq tegishli fayllarni alohida papkaga joylashtirgan bo'lsangiz va dasturlashni boshlagan bo'lsangiz, uni avvalgidek qadoqlashga urinib ko'rishingiz mumkin, bo'lmasa, ularni hozir alohida tashkil qilishingiz mumkin._ Quyidagi misol faqat Flappy Bird o'yinida ishlatiladigan manba fayllari va resurslarini alohida papkada tashkil qiladi.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Papkalarni tartibga solishda yodda tutish kerak bo'lgan narsa shundaki, 4.1-bo'limdagi havolada ko'rsatilgan resurslarni (rasmlar, fontlar, ovoz effektlari, fon musiqasi) o'z ichiga olgan pastki papkalar nomlari PygameZero-ning asosiy cheklovlariga muvofiq yaratilishi kerak. Bu ular faqat oldindan belgilangan nomlar bilan yaratilishi kerakligini bildiradi (images, fonts, sounds, music, old tomondan shu tartibda).

Endi siz tayyor bo'lsangiz, jarayon juda oddiy. _Qadoqlamoqchi bo'lgan o'yinning manba fayl yorlig'ini bosib kiring (agar sizda bir nechta fayllar ochiq bo'lsa) va quyidagi rasmda ko'rsatilganidek, "**Exe faylga**" deb nomlangan menyu belgisini bosing._

<figure><img src="../.gitbook/assets/Screenshot 2024-07-08 at 11.39.20.png" alt=""><figcaption></figcaption></figure>

Tugmani bosganingizdan qadoqlash jarayoni boshlanadi va, rasmda ko'rsatilgandek, qadoqlash **"... completed successfully"** xabari bilan muvaffaqiyatli tamomlansa, manba fayllari saqlangan joyda dist nomli papka yaratilganini ko'rasiz. Uning ichida Flappy Bird o'yini bittan bajariladigan (exe) faylga qadoqlanganini ko'rasiz.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-08 at 11.44.23.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
