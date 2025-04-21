# 5.3 Robot changyutkich to'siqga duch kelsa nima bo'ladi? (Shart)

Bu uchinchi, "Robot changyutgich" misoli. Bu misolda biz ilgari foydalanmagan Actor ob'yektlarining qo'shimcha harakatlari(metodlari) keltirilgan, ammo oldingi boblarda o'rganilgan asosiy tamoyillar unchalik o'zganligi sababli, bu juda qiyin bo'lmasligi kerak.

{% code lineNumbers="true" %}
```python
from pgzhelper import *

WIDTH = 960
HEIGHT = 540

robot = Actor('cleaner', (WIDTH / 2, HEIGHT / 2))
robot.scale = 0.3
robot.angle = 90
robot.brush_init((WIDTH, HEIGHT), 50, 'white')

def draw():
    screen.blit('floor', (0, 0))
    robot.brush_draw()
    robot.draw()

def update():
    robot.move_forward(10)

    if robot.top < 0 or robot.right > WIDTH \
        or robot.bottom > HEIGHT or robot.left < 0:
        robot.move_back(10)
        robot.angle += 133
```
{% endcode %}

🔢 Birinchidan, 3-4 qatorlarda ekran o'lchami mavjud o'lchamdan ikki barobarga oshirildi (480 kenglik, 270 balandlik). Buning alohida sababi yo'q, bu faqat ijro natijasi ekranini kattaroq hajmda ko'rish uchundir.

🔢 6-qatorda robot changyutgichni ekranning o'rtasiga joylashtirish uchun markaziy koordinata gorizontal va vertikal uzunliklarning yarmiga o'rnatildi.

🔢 8-qatorda robot changyutgich obyekti birinchi marta ishga tushirilganda ekranda yuqoriga qarab harakatlanishi uchun uning boshlang'ich burchagi 90 darajaga o'rnatiladi.

🔢 9-qatordan robot changyutgichning harakat izlarini bo‘yashning asosiy sozlamalari **brush\_init** funksiyasi(metodi) orqali amalga oshiriladi. Uchta argument talab qilinadi: cho'tka bilan bo'yalgan umumiy maydon, qalinligi va rangi.

🔢 12-qatorda men nihoyat birinchi marta o'yin fonini chizish uchun kodni qo'lladim. **Ekran** deb nomlangan oldindan o'rnatilgan obyektda turli xil funksiyalar (metodlar) mavjud bo'lib, **ular o'yin ekraniga ishora qiladi (**[**batafsil ma'lumot**](https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen) **uchun Pygame Zero qo'llanmasiga qarang) va blit metodi** ulardan biri bo'lib, tasvirni to'g'ridan-to'g'ri ekranga chiqaradi va bizning kodda pol tasviri(rasmi)ni chiqaradi.

**🔢** 16-qatorda paydo bo'lgan **update** **kolbek funksiyasi o'yin siklini tashkil etuvchi asosiy funksiyadir. Bu o'yinda doimiy ravishda o'zgarib turadigan narsalar (masalan, Actor obyekti harakatlanayotganda) yoki doimiy tekshirilishi kerak bo'lgan narsalar (masalan, qaysi klaviatura yoki sichqoncha tugmasi bosilgan) uchun kod yozadigan qismdir.** Shuning uchun robot changyutgich har safar 10 o'lchamdagi harakatni takrorlashi uchun 17-qatorda **move\_forward(10)** ishlatilgan.

🔢 Va nihoyat, 19-qatordan so'ng, robot changyutgich o'yin ekranining oxiriga yetganda nima bo'lishi kerakligini tavsiflovchi shart bilan kod keladi. Bu Entry daturida odatiy kodlashdan biroz farq qiladi. _Entryda o'yin ekranining chegaralari "devor" deb nomlangan va obyektlar sifatida nazarga olingan. Bu devor chegarasiga tegganligini (chiqib ketganini) aniqlash uchun obyektlar orasidagi to'qnashuvni tekshirishdan foydalanilgan._ **Biroq,** **Pygame Zeroda orqa fon rasmi o'zi obyekt emas. Shuning uchun&#x20;**_**ekran chegarasiga tegganligini aniqlash uchun doimiy ravishda harakatlanadigan robot changyutgichning hozirgi holati (joylashuvi) orqali amalga oshiriladi.**_

Masalan, **robot.top** qiymatining 0 dan kichik bo‘lishi robot changyutgich obyektining o‘yin ekrani yuqori chegarasidan chiqib ketayotganini anglatadi. Shu bilan birga, **robot.right** qiymatining ekran kengligidan kattalashishi o‘yin ekrani o‘ng chetiga yetib borganini bildiradi. Ushbu holatda, robotni biroz (10 birlik miqdorida) orqaga qaytarib, keyin yo‘nalishni o‘zgartirishga urinayotganini yodda tutish kerak. Bunday algoritmning zarurati shundaki, ekranning chetiga yetganda darhol yo‘nalishni o‘zgartirishga urinish, ba’zan yo‘nalish o‘zgartirilgan paytda ham obyekt hali ham ekranning chekkasida bo‘lib qolishi mumkin. Natijada, robot doim bir joyda aylanib qolib, boshqa yo‘nalishda harakat qila olmaydi. Buning oldini olish uchun robotni bir oz orqaga qaytarib, keyin yo‘nalishni o‘zgartirishga harakat qilinadi.

Ma’lumot uchun, 19-qator oxirida joylashgan '\\' belgisiga qiziqayotganlar bo‘lishi mumkin. 19\~20-qatorlarga bo‘lingan kod aslida bitta uzun qator sifatida 19-qatorga joylashishi kerak edi. Ammo muallif bu kodni ikki qatorga ajratdi, bu esa kodni o‘qishda tez va intuitiv tarzda tushunish imkonini berish, ya’ni kodni o‘qish qulayligini oshirish uchun qilingan. Ammo, **kodlashda, agar bitta uzun qatorni bir necha qatorlarga ajratish kerak bo‘lsa, ajratilgan qatorning oxirida '\\' belgisi qo‘yilishi shart. Bu belgidan foydalanish ajratilgan qator hali tugamaganligini va keyingi qator bilan bog‘langanligini bildiradi.**

Nihoyat, biz robot changyutgichning yakuniy natijalarini ko'rib chiqish orqali ushbu bobni yakunlaymiz.

<figure><img src="../.gitbook/assets/Screen Recording 2024-07-17 at 16.59.34 (2).gif" alt=""><figcaption></figcaption></figure>
