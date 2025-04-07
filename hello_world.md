# 3. "Hello World" dasturidan boshlaylik

Bu dasturlashdagi birinchi qadam. Har doimgidek, lekin bu safar siz bilan, biz "[Hello World](https://uz.wikipedia.org/wiki/Hello,_World!)" dasturini birgalikda o'rganishdan boshlashimiz kerak. Biroq, Pygame Zero dasturlash tilining o'zi emas, balki kutubxona bo'lgani uchun biz tanish bo'lgan Hello World dasturini yaratmaymiz. Buning o'rniga, avvalgi Hello World dasturiga nisbatan Pygame Zero kutubxonasi bilan kodlashda zarur bo'lgan minimal koddan iborat eng kichik dastur misolini ko'rib chiqamiz.

Birinchidan, Mu Editorni ochaylik. Faylni ochish va birinchi kodlashni boshlash uchun menyu panelidagi **Yangi fayl** tugmasini bosing. Quyidagi bitta chiziqli kodni yozamiz.

```python
TITLE = 'Hello World!' 
```

Kodlash amalga oshirildi. Ajoyib! Bu juda oddiy emasmi? Ha, shunday. Shuning uchun _Pygame Zero Python kodlash orqali o'yin yaratishni soddalashtiradi, xuddi bizning Entry-Pythondagi Python kodlash tajribamiz kabi. Shunday qilib, Pygame Zero orqali Python dasturashni o'rganish matnli dasturlashni yangi o'rganayotganlar uchun juda mos tanlov bo'lishi mumkin._

Faqat bitta qator kod bilan biz 'Hello World' nomli juda oddiy bo'sh oyna dasturini yaratdik.

Endi kodni **hello\_world** nomi bilan faylga saqlash uchun menyu panelidagi **Saqlash** tugmasini bosamiz. Keyin, uni bajarish uchun menyu panelidagi **Boshlash** tugmasini bosing va qanday ishlashini tekshiring. **hello\_world** nomli bo'sh oyna ilovasi biz kutgandek to'g'ri ishladimi?

<figure><img src=".gitbook/assets/Screenshot 2024-03-11 at 11.51.32.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption><p>"Hello World" nomli ijro ekrani</p></figcaption></figure>

Kodlashga qaytish uchun biz hozirgina bajarilgan dasturni yopishimiz kerak. Ishga tushrilgan dastur o'zi oynasidagi 'x' tugmasini (dastur o'chirish tugmasi) bosish orqali o'yin ilovasini yopish mumkin bo'lsa-da, **Mu editorida kodlashni davom etish uchun har doim to'g'ri chiqish uchun Menyu panelidagi To'xtatish tugmasini bosishni unutmang**.

<figure><img src=".gitbook/assets/Screenshot 2024-03-11 at 12.06.22.png" alt=""><figcaption></figcaption></figure>

Biroq, bitta qatorli kod bo'lishiga qaramay, keling, uni tushunish uchun kodni tahlil qilaylik. Biz ilova nomini **TITLE** deb nomlangan o'zgaruvchida saqladik. O'zgaruvchining nomi nega TITLE ekanligini intuitiv ravishda taxmin qilishingiz mumkin, u biz yaratmoqchi bo'lgan ilovaning nomini (sarlavhasini) ko'rsatish uchun ishlatiladi. Lekin nima uchun o'zgaruvchining nomi TITLE bo'lishi kerak? Nima uchun o'zgaruvchi kichik harflarda bo'lishi mumkin emas yoki nega men uni shunchaki xohlaganimdek APPNAME deb nomlay olmayman deb o'ylashingiz mumkin. Afsuski, bu tarzda ishlamaydi. Agar siz bu haqiqat yoki yo'qligini tekshirmoqchi bo'lsangiz, o'zgaruvchining nomini boshqa narsaga o'zgartirib, tajriba o'tkazishingiz va kerakli natijaga erishganingizni bilish uchun ilovani qayta ishga tushirishingiz mumkin. Siz kerakli natijaga erisha olmasligingizni bilib olasiz.

Pythonni birinchi marta o'rganganimizda biz avval o'rgangan [**oldindan o'rnatilgan funksiyalar**](https://roboticsware.gitbook.io/entry-python/boshlash/kiritish_chiqarish) va **ldindan o'rnatilgan o'zgaruvchilar** kabi tushunchalarni eslaysizmi? Ushbu o'zgaruvchi shu tushunchalarga o'xshaydi. Agar kutubxonalar haqida avvalgi darslarimizdan eslasangiz, [**kutubxona**](https://roboticsware.gitbook.io/entry-python/boshlash/hello_world#kutubxona-nima)**dan foydalanish kutubxona yaratuvchisi tomonidan belgilangan qoidalarni o'rganish va shu qoidalarga muvofiq kodlashni anglatadi**. Xuddi shunday, _Pygame Zerodan foydalanish Pygame Zero yaratuvchisi tomonidan belgilangan qoidalarni o'rganish va shunga mos ravishda kodlashni anglatadi. Biz o'rgangan TITLE o'zgaruvchisi yaratuvchi tomonidan allaqachon belgilangan to'g'ri ismga o'xshaydi. Ilova nomini o'zgaruvchida saqlash uchun faqat shu o'zgaruvchi nomidan foydalanish ilova bajarilganda ilova nomi to'g'ri ko'rsatilishini ta'minlaydi._

Endi o'yin ilovamizni biroz kengaytiraylik. Endi quyidagi 2 qator kodlarni qo'shib, bizda jami 3 qator kod mavjud. Ushbu 3ta qatorli kod yordamida biz ilova nomi asosida 'Hello World' nomli 400 x 300 piksel o'lchamdagi bo'sh ekranli juda oddiy dastur yaratdik. Boshlash tugmasini bosib, uni ishga tushiramiz.

```python
TITLE = 'Hello World!' 
WIDTH = 400 
HEIGHT = 300
```

<figure><img src=".gitbook/assets/image (43).png" alt=""><figcaption><p>Gorizontal ravishda 400 piksel va vertikal ravishda 300 piksel o'lchamdagi ilovani ishga tushirish oynasi</p></figcaption></figure>

Xo'sh, biz dastlab yaratgan birinchi bitta qatorli dastur va ushbu dastur o'rtasidagi farq nima? Ha, biz mos ravishda **WIDTH** va **HEIGHT** ya'ni kenglik va balandlik nomli o'zgaruvchilar yordamida qo'shimcha kodlashni qo'shdik. Siz intuitiv ravishda his qilganingizdek, xuddi o'zgaruvchi TITLE kabi, bu o'zgaruvchi nomlari Pygame Zero kutubxonasida oldindan belgilangan o'zgaruvchilar bo'lib, ilova hajmini aniqlaydi. Ulardan foydalanish tufayli biz endi kerakli o'lchamdagi ilovalarni yaratishimiz mumkin.

Hello World dasturini yaratish tugagani uchun, keling, haqiqiy o'yinlarni birma-bir yaratish orqali Python dasturlahni o'rganishdan zavqlanaylik!
