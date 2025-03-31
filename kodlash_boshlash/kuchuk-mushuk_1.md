# 5.1.1 Kuchuk va mushuk Salom aytadi1 (Ketma-ketlik)

Oldingi bobda biz Entry blokli kodlash va Pygame Zeroda dasturlashning asosiy tuzilish farqini tushunib oldik. Shu asoslda, Entry asosiy kitobidan yettita misolni Entry-Python emas, balki haqiqiy Python dasturlash orqali yaratib ko'ramiz. Ammo buni amalga oshilrish uchun faqat Pygame Zero kutubxonasi funksional jihatdan yetarli emas. Shuning uchun qo'shimcha foydalanuvchi kutubxonasi kerak bo'ladi, va biz ushbu foydalanuvchi **pgzhelper kutubxonasi** (user library, ya'ni odatda oldindan o'rnatilmagan va ehtiyojga ko'ra foydalanuvchi tomonidan yaratilgan kutubxona) chaqirishdan boshlaymiz.

{% hint style="info" %}
pgzhelper birinchi bo'lib **Cort**, Singapurdagi dasturchi, Scratch blokli kodlashni Pygame Zeroga o'tkazishda(porting) Pygame Zero cheklovlari tufayli yuzaga kelgan qiyinchiliklarni(o'xshash funksiyalarni bajarishni) yaxshilash uchun yaratgan. Shunga o'xshash sabablarga ko'ra [Roboticsware ](https://roboticsware.uz)ham Pygame Zeroga Entry bloklarini python kodga aylantirishni osonlashtirish uchun mavjud kutubxonaning funktsiyalarini to'ldirdi va buni ochiq kodlar GitHub sayti ( [https://github.com/roboticsware/pgzhelper ](https://github.com/roboticsware/pgzhelper)) orqali ommaga tarqatmoqda.
{% endhint %}

```python
from pgzhelper import *
```

Kodning birinchi qatori pgzhelper kutubxonasini chaqiradigan qismdir. Kutubxonani chaqirishning ikki asosiy usuli mavjud. Odatda siz _import pgzhelper_ deb ishlatishga odatlangan bo'lsangiz kerak, lekin bu holda kutubxonani yangi sintaksis yordamida chaqirish kerak bo'ladi.

> **from** kutubxona nomi **import** \*

Uni shunday chaqirishning afzalligi **avval siz kutubxona ichidagi funktsiyani chaqirish uchun doimo <\<kutubxona nomi.funksiya nomi>> sintaksisidan foydalanishingiz kerak bo'lgan bo'lsa, endi siz uni avvalgidek, xuddi shu tarzda ishlatishingiz mumkin, faqat funktsiya nomi yordamida, old tomonda kutubxona nomi ko'rsatmasdan.**

### Entry koordinatalari tizimi va Pygame koordinatalari tizimini taqqoslash

Biz yaxshi bilganimizdek, Entrydagi koordinatalar tizimi quyidagi chapdagi rasmda ko'rsatilgan va uning xususiyati shundaki, ekranning belgilangan o‘lchami (kengligi 480 piksel, balandligi 270 piksel) bor va ekranning markazi x va y koordinatalarining boshlanish nuqtasi (0, 0) hisoblanadi. Boshqa tomondan, **Pygame koordinatalar tizimida ekranning umumiy o'lchamini foydalanuvchi o'zi belgilashi mumkin, ammo bu holda koordinatalarning boshlanish nuqtasi (0, 0) yuqori chap burchakda joylashgan bo'ladi va o'ngga va pastga qarab qiymatlar oshib boradi.**

<table><thead><tr><th align="center">Entry</th><th align="center">Pygame</th><th data-hidden></th></tr></thead><tbody><tr><td align="center"><img src="../.gitbook/assets/image (33).png" alt="" data-size="original"></td><td align="center"><img src="../.gitbook/assets/image (32).png" alt="" data-size="original"></td><td></td></tr></tbody></table>

Keling, hozircha Entryning bajarish ekrani hajmini taqlid qilaylik. Shuning uchun ekranning kengligi va balandligi mos ravishda 480 va 270 pikselni tashkil qiladi va shunga asoslanib, kod quyidagicha bo'ladi:

{% code lineNumbers="true" %}
```python
from pgzhelper import *

TITLE = 'Kuchuk va Mushuk salom aytadi'
WIDTH = 480
HEIGHT = 270
```
{% endcode %}

O‘yinda alohida fon rasmi mavjud emas. Entryda fon rangi avtomatik ravishda oq rangda bo‘ladi, ammo Pygame Zeroda bu avtomatik ravishda bo‘lib o‘tmaydi. Shuning uchun, bizning ehtiyojimizga ko‘ra fonni oq rangda bo‘yash kerak bo‘ladi. Buni kodlashning uchta usuli mavjud:

#### Oldindan belgilangan rang qiymati kalit so'zlari yordamida kodlash

```python
def draw():
    screen.fill('white')
```

_**draw** funksiyasi oldingi bobda ko'rganimizdek, Pygame Zero o'yin siklida mavjud bo'lgan oldindan belgilangan kolbek funksiyasi._ Ekranda biror narsa chizmoqchi bo'lganimizda, u avtomatik ravishda chaqiriladi. Ekranni rangga to'dirish uchun kod ushbu funktsiya ichida yozilishi kerak va ekranni to'ldirish uchun biz oq rangni [argument](https://roboticsware.gitbook.io/entry-python/boshlash/hello_world#funksiyani-qanday-yaratish-tariflash) sifatida o'tkazib, **fill** deb nomlangan funktsiyadan foydalanamiz. **fill** funksiyasi "**screen.**" yordamida chaqiriladi, chunki **fill** funksiyasi Pygame Zero kutubxonasining **screen** obyektida mavjud. Obyektlar haqida keyingi bobda batafsil yoritilganligi sababli, hozircha yetarli.

**Ekranni to'ldirish uchun rang qiymatini o'tkazishning uchta usuli mavjud. Ulardan biri til o'rnatilgan kalit so'zlar kabi oldindan belgilangan qiymatlardan foydalanish, ikkinchisi esa RGB (Red / Green / Blue) vakolatxonasidan foydalanishdir.** Oldindan belgilangan rang kalit so'zlarini quyidagi rang qiymatlari jadvalida topish mumkin.

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

Keyin rangni RGBning uchta asosiy rangi (qizil, yashil, ko'k) kombinatsiyasi orqali ifodalash mumkin, bu yerda har bir asosiy rang maksimal qiymati 256 tadir. Istalgan rangni ifodalash uchun har bir asosiy rangni o'nlik (0 dan 255 gacha) yoki o'n oltili (00 dan FF gacha) sanoq sistemasida ifodalash usullari mavjud.

<table><thead><tr><th width="356"></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><img src="../.gitbook/assets/image (28).png" alt="" data-size="original"></td><td><img src="../.gitbook/assets/image (27).png" alt="" data-size="original"></td><td></td></tr></tbody></table>

#### RGB rang qiymatlarining o'nlik ko'rinishida oq rangni kodlash

```python
def draw():
    screen.fill((255, 255, 255))
```

#### RGB rang qiymatlarining o'nlik oltilik ko'rinishida oq rangni kodlash

```python
def draw():
    screen.fill('#FFFFFF')
```

Ranglarning ifodasiga kelsak, internetda juda ko'p manbalar mavjud, shuning uchun har bir kishi ushbu materiallar bilan to'g'ridan-to'g'ri tanishib chiqishi yaxshiroqdir. Ma'lumot uchun, nega ranglarni ifodalash uchun RGBning uchta asosiy ranglari ishlatilishi [haqidagi blog](https://phominator.tistory.com/42)ni tekshiring.

Keling, shu vaqtgacha yozilgan kodni ishga tushirib, u kutilganidek ishlashini tekshirib ko‘raylik. Ishga tushirish uchun avvalo dastur kodini faylga saqlash kerak. Dastur kodi (source code) saqlanishi lozim bo‘lgan asosiy joy — bu _**\[foydalanuvchi nomi]\mu\_code**_**\\.** (quyidagi rasmga qarang).

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
_**Yozilgan dastur kodini saqlaganda, saqlash joyi, albatta, qat’iy belgilanmagan bo‘lib, foydalanuvchi uni istagan joyiga saqlashi mumkin. Biroq, ushbu kitobdagi misol amaliyotlarini bajarishda kerak bo‘ladigan resurslar (rasmlar, shriftlar, effekt ovozlari, fon musiqasi)dan foydalanish uchun fayllarni yuqorida aytib o'tilgan Mu Editor-ning asosiy kod saqlash joyi (\[foydalanuvchi nomi]\mu\_code)ga saqlashingizni so‘raymiz.**_ Nega bunday qilish kerakligi haqida keyingi bo‘limlarda batafsil tushuntiriladi.
{% endhint %}

Dastur kodini saqlab bo‘lganingizdan so‘ng, endi F5 tugmasini bosib, uni ishga tushiring. Ekran oq rang bilan to‘g‘ri bo‘yalgan bo‘ladi. Ekran rangini yuqorida o‘rgangan uchta usulni qo‘llab o‘zgartirib ko‘rish sizga amaliyot uchun topshiriq sifatida qoldiriladi.

{% code lineNumbers="true" %}
```python
from pgzhelper import *

TITLE = 'Kuchuk va mushuk Salom aytadi'
WIDTH = 480
HEIGHT = 270

def draw():
    screen.fill('white')
```
{% endcode %}

Endi keyingi qadam — o‘yin qahramonlari bo‘lgan «Kuchukcha» va «Mushukcha» obyektlarini chaqirib, ularni ekranga joylashtirishdir. Buni kodlash uchun har bir obyektning tashqi ko‘rinishini ifodalovchi rasm fayllari kerak bo‘ladi.

Entry blokli kodlashdagi tajribangizni eslang. O‘yinni yaratishda birinchi qilgan ishingiz nima edi? Ehtimol, siz o‘yinda ishtirok etadigan obyektlarni ekranga joylashtirish bilan boshlagansiz. Matnli kodlashda ham shunga o‘xshash. Biz ham qahramon obyektlarini ekranga chiqarishdan boshlaymiz.

Biroq, Entry-da bo‘lgani kabi, agar o‘yinda foydalaniladigan obyektlar dasturga oldindan kiritilmagan bo‘lsa, o‘yin uchun kerak bo‘lgan rasm fayllarini kiritib, keyin kodlashni boshlashingiz kerak edi. Xuddi shunday, agar kodlashda foydalaniladigan rasmlar oldindan kiritilgan rasmlar bo‘lmasa, ularni alohida saqlash kerak bo‘ladi. Saqlash yo‘li — bu Mu Editori o‘rnatilganda avtomatik ravishda yaratiladigan _**\[foydalanuvchi nomi]\mu\_code\images**_ papkasi (direktoriyasi) va rasmlar shu papkada joylashishi kerak bo‘ladi.

Ushbu papkaning joylashuvini osongina topmoqchi bo‘lsangiz, Mu muharriridagi menyu panelidagi **"Rasmlar" tugmasi**ni bosing. Bu tugma siz foydalanayotgan rasmlar saqlangan papkani darhol ochib beradi. Papka ichida ushbu kitobda foydalaniladigan rasmlar sizning qulayligingiz uchun oldindan saqlanganini ko‘rishingiz mumkin. Manba kodini asosiy saqlash joyiga saqlashingizni so‘raganimizning sababi, biz ushbu oldindan saqlangan rasmlardan foydalanib, qo‘shimcha resurslar bilan bog‘liq ishlarni chetlab o‘tib, faqat kodlashga e'tibor qaratishingiz uchun edi.

<figure><img src="../.gitbook/assets/Screenshot 2024-10-21 at 16.28.41.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/imageaa.avif" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Aytgancha, **o'yinni dasturlashda zarur bo'lgan resurslarni (rasmlar, shriftlar, ovoz effektlari, fon musiqasi) saqlaydigan papkalarni yaratish uchun siz Pygame Zero kutubxonasining asosiy cheklovlarida o'rnatilgan ushbu pastki papkalar uchun oldindan belgilangan nomlarga (tartibda: rasmlar, shriftlar, tovushlar, musiqa) rioya qilishingiz kerak**. Ushbu muvofiqlik Mu editordagi menyu tugmalarining nomlari aytib o'tilgan papkalarning nomlariga mos kelishi bilan bog'liq. Shuning uchun, tegishli tugmalarni bosish orqali resurs turiga mos papkalarni avtomatik ravishda ochishga qaratilgan dasturlash, resurslarni topa olmaslik bilan bog'liq ish vaqtida xatolar ehtimolini kamaytiradigan qulay usuldir.

\
Shunga tegishli Mu editorning qo'llanmasiga qarang:

[https://codewith.mu/en/howto/1.2/pgzero\_sounds\_images](https://codewith.mu/en/howto/1.2/pgzero_sounds_images)
{% endhint %}

Keyingi keltiriladigan ma’lumotlar siz bilishingiz kerak bo'lgani uchun berilgan. Biz foydalanayotgan maxsus Mu Editori holatida, kodlashda kerak bo‘ladigan barcha resurslar (rasmlar, ovozlar va hokazo) sizning qulayligingiz uchun oldindan kiritib qo‘yilgan, shuning uchun bunday qo‘shimcha ishlar talab qilinmaydi. Biroq, bu izoh Entry-da har bir obyektning rasmlarini qanday olib kirish mumkinligi bilan qiziqadiganlar uchun qo‘shimcha tushuntirishdir.

#### Entry dan rasm obyektini import qilish

Entry dagi "kuchuk" va "mushuk" obyektlarining rasmlaridan foydalanish uchun Entry-ni oching va kerakli obyektlarning rasm fayllarini import qiling. Import qilish uchun "shakl" yorlig'ini bosing, import qilmoqchi bo'lgan shaklni o'ng sichqon tugmasi bilan bosing va paydo bo'lgan menyudan "kompyuterga yuklab olish" ni tanlang. Uni Pygame Zero uchun yuqorida aytib o'tilgan "images" papkasiga saqlang.

<figure><img src="../.gitbook/assets/Screenshot 2024-03-20 at 12.14.25 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Ushbu kitobdagi misollar uchun zarur bo'lgan barcha rasmlarni [bu yer](https://github.com/roboticsware/python-pygame_zero-samples/tree/main/entry_basic/images_ko)dan yuklab olishingiz mumkin.
{% endhint %}

Endi har bir obyektni («Kuchukcha» va «Mushukcha») ekranda aks ettirishga o‘tamiz va keyingi bo‘limda ularning o‘zaro salomlashishini kodlashni yakunlaymiz.
