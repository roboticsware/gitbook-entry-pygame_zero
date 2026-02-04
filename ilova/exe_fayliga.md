# Dasturimizni EXE fayliga aylantirish

**Avvalo shuni ma'lum qilmoqchimanki, bu xususiyat umumiy rasmiy Mu editorida mavjud emas va faqat** [**muallif tomonidan ishlab chiqilayotgan Mu editorining maxsus versiyasi**](https://github.com/roboticsware/mu/releases)**da mavjud.**

Foydalanish usuli oddiy. Birinchidan, _agar siz yaratgan o'yin boshqalarga tarqatilishi uchun yetarli darajada to'liq deb hisoblasangiz, barcha manbalarni to'plash orqali o'yinni avtomatik ravishda bitta bajariladigan fayl (Windows platformasi uchun exe fayli) sifatida yaratish uchun editor o'ziga o'rnatilgan funksiyadan foydalanishingiz mumkin. Bu funksiya manba kodi fayllarni, qo'shimcha modullarni va o'yin dasturlari chiqarish uchun zarur bo'lgan resurslarni (rasmlar, ovozlar, fontlar va boshqalar) bitta faylga aylantiradi. Bu sizning o'yiningizni boshqalarga tarqatishni osonlashtiradi va o'yin foydalanuvchilari uchun bitta bajariladigan faylni ikki marta bosish orqali o'yindan zavq olishlari ham qulay._

Misol uchun, keling, [keyingi darajali kitobi](https://roboticsware.gitbook.io/python-pygame_zero)da 4-bobda birgalikda yaratgan "Flappy Bird" o'yinini qadoqlab ko'raylik. Birinchi, siz qadoqlamoqchi bo'lgan o'yin manba kodi faylining joylashuvini ko'rib chiqaik. Editorni o'rnatishda u Pygame Zero uchun editor o'zi tomonidan o'rnatilgan standart papka bo'lgan "akkauntingiz nomi/mu\_code" da joylashgan bo'lishi mumkin va albatta, siz uni bu holatda bo'lgani kabi qadoqlab ko'rishingiz mumkin. Biroq, **o'yin bilan bir-biriga bog'liq bo'lmagan fayllarni qadoqlashdan boshqa foyda yo'qligi sababli, bu faqat keraksiz hajmni oshiradi, iloji bo'lsa, faqat o'yin uchun zarur bo'lgan fayllar va resurslarni qadoqlash eng tejamkor usuli bo'ladi.** _Agar siz o'yinni yasashdan boshidanoq tegishli fayllarni alohida papkaga joylashtirgan bo'lsangiz va o'sha joyida dasturlashni boshlagan bo'lsangiz, uni oson qadoqlashga urinib ko'rishingiz mumkin, bo'lmasa, ularni hozir alohida tashkil qilishingiz mumkin._ Quyidagi misol faqat Flappy Bird o'yinida ishlatiladigan manba kodi fayllari va resurslarini alohida papkada tashkil qiladi.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Papkalarni tartibga solishda yodda tutish kerak bo'lgan narsa shundaki, [5.1.1-bo'lim](../kodlash_boshlash/kuchuk-mushuk_1.md#pygame-zeroda-resurlarni-boshqarish)da o'rganib olgandek resurslarni (rasmlar, fontlar, ovozli effektlari, fon musiqasi) o'z ichiga olgan pastki papkalar nomlari Pygame Zeroning asosiy cheklovlariga muvofiq yaratilishi kerak. Bu ular faqat oldindan belgilangan nomlar (images, fonts, sounds, music) bilan yaratilishi kerakligini bildiradi.

Endi siz tayyor bo'lsangiz, jarayon juda oddiy. _Agar sizda editor ichida bir nechta fayllar ochiq bo‘lsa, qadoqlamoqchi bo'lgan o'yinning manba kodi fayl yorlig'ini bosib kiring va quyidagi rasmda ko'rsatilganidek, "**Exe fayliga**" deb nomlangan menyu belgisini bosing._

<figure><img src="../.gitbook/assets/Screenshot 2024-07-08 at 11.39.20.png" alt=""><figcaption></figcaption></figure>

Tugmani bosganingizdan qadoqlash jarayoni boshlanadi va rasmda ko'rsatilgandek, qadoqlash **"... completed successfully"** xabari bilan muvaffaqiyatli tamomlansa, manba fayllari saqlangan joyda **dist** nomli papka yaratilganini ko'rasiz. Uning ichida Flappy Bird o'yini bitta bajariladigan **flappy\_bird.exe** fayliga qadoqlanganini ko'rasiz.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-08 at 11.44.23.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
