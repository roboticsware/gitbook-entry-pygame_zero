# 4. O'yin siklini tushunish

To'liq miqyosli o'yin ishlab chiqarishni boshlashdan oldin, biz yaratadigan o'yin dasturining asosiy operatsion tuzilishini tushunishimiz kerak.

Keling, avvalam bor Entry blokli kodlashda umumiy kodlash qanday bo'lganini eslaylik. Odatda, birinchi navbatda, ekranda paydo bo'ladigan bir yoki bir nechta asosiy belgilar obyektlari chaqiriladi va ekranga joylashtiriladi, so'ngra har bir obyekt o'yinda bajarishi kerak bo'lgan harakatlar uchun alohida kodlanadi. Tugallangan o'yin o'ynalganda, har bir obyekt mustaqil ravishda va bir vaqtning o'zida ishga tushadi va hatto "boshlash tugmasi bosilganda" bir obyektga ikki yoki undan ko'p marta qo'yilgan bo'lsa ham, u parallel ravishda harakat qilayotgandek harakat qildi ([tafsilotlar uchun oldingi kitobga qarang](https://roboticsware.gitbook.io/entry-python/dasturlash_paradigma/ketma_ketlik-parallel)).

Pygame Zero kutubxonasi bilan Python tilida dasturlash blokli kodlashga biroz o'xshaydi, ammo sezilarli farqlar ham mavjud. Afsuski, eng katta farq shundaki, endi biz har bir asosiy obyektni mustaqil va parallel ravishda harakat qildira olmaymiz, va biz barcha asosiy obektlarning harakatlari bir joyda (o'yin sikli) boshqariladi deb hisoblab kodlashimiz kerak. Agar biz uni diagrammada ifodalasak, o'yin doimiy ravishda takrorlanib turuvchi cheksiz sikl(**o'yin sikli** deb ataladi, chunki u o'yinlar uchun maxsus ishlatiladigan davomiy taqrorlashaga o'xshash)da bajariladi:

<figure><img src=".gitbook/assets/image (44).png" alt=""><figcaption><p>Manba: <a href="https://inventwithpython.com/pygame/chapter2.html">https://inventwithpython.com/pygame/chapter2.html</a></p></figcaption></figure>

Rasmda tasvirlanganidek, **o'yin siklida uchta asosiy vazifalar(ekranda o'yin obyektini chizish, o'yin obyektlarining harakatlarini boshqarish,** [**klaviatura va sichqoncha kabi hodisalarni ishlov qilish**](https://roboticsware.gitbook.io/entry-python/dasturlash_paradigma/event-driven)**)ni doimiy ravishda qayta ishlanadi.**&#x20;

Agar biz Pygame Zero o‘rniga Pygame kutubxonasi bilan kodlayotgan bo‘lsak, ushbu o‘yin siklining tuzilishini yaratish bizning vazifamizdir va biz uni o‘zimiz kodlashimiz kerak. **Biroq, Pygame Zero ataylab yangi boshlovchilar uchun bu qismni yashiradi, va u oldindan belgilangan 3ta** [**kolbek funksiyalari**](https://roboticsware.gitbook.io/entry-python/boshlash/hello_world#kolbek-callback-funksiyasi-nima)**(draw, update on\_mouse/on\_key) tayyor. Ushbu kolbek funksiyalariga muvofiq kodlash orqali Pygame Zero yangi boshlanuvchilar uchun yanada qulay tuzilmani taklif etadi.** Yaxshiyamki, biz Pythonda Entry-Pythonda kolbek funksiyasi asosida kodlashni sinab ko‘rganimiz uchun, biz ushbu tuzilishga qiyinchiliksiz moslasha olishimiz kerak.

Keyingi mashg'ulotdan boshlab biz ushbu tushunchaga asoslangan to'liq o'yinni kodlashga harakat qilamiz.
