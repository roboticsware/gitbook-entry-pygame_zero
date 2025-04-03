# 5.1.3 Kuchuk va mushuk Salom aytadi3 (Ketma-ketlik)

Bu safar, Mushuk obyektini yaratish va uni ekranda ko'rsatish vaqti keldi. Kuchuk obyekti bilan allaqachon kod yozganimiz uchun bu juda qiyin bo'lmasligi kerak. Biroq, quyidagi 11-qatorda biz ilgari ko'rmagan kod paydo bo'ldi. Biz buni **flip\_x** xususiyat nomidan intuitiv ravishda taxmin qilishimiz mumkin va agar Mushuk obyektini Kuchuk obyektiga qarashi uchun maxsus qo'shilgan blokli kodlashdagi blokni (shaklni chapga va o'ngga aylantirish) eslasak, uning o'sha blok bilan bir xil rol o'ynashini ko'rishimiz mumkin. Boshqacha qilib aytganda, x yo'nalishida (gorizontal yo'nalish) tasvirni aylantirish uchun xususiyatga **True** qiymatini berish orqali tasvir ekranda chizilishidan oldin aylantiriladi.

<pre class="language-python" data-line-numbers><code class="lang-python">from pgzhelper import *

TITLE = 'Kuchuk va Mushuk salom aytadi'
WIDTH = 480
HEIGHT = 270

dog = Actor('dog', (100, 150))
dog.scale = 0.5
cat = Actor('cat', (350, 150))
<strong>cat.scale = 0.5
</strong>cat.flip_x = True

def draw():
    screen.fill('white')
    dog.draw()
    cat.draw()
</code></pre>

Endi faqat kuchuk va mushuk navbatma-navbat bir-biri bilan salomlashishi va xayrlashishi qoldi. Agar biz buni kodda ifodalasak, u 18 dan 21 gacha bo'lgan to'rt qator kod bo'ladi.

{% code lineNumbers="true" fullWidth="false" %}
```python
from pgzhelper import *

TITLE = 'Kuchuk va Mushuk salom aytadi'
WIDTH = 480
HEIGHT = 270

dog = Actor('dog', (100, 150))
dog.scale = 0.5
cat = Actor('cat', (350, 150))
cat.scale = 0.5
cat.flip_x = True

def draw():
    screen.fill('white')
    dog.draw()
    cat.draw()
    
    dog.say_for_sec("Vov-vov!", 2)
    cat.say_for_sec("Miyov~", 2)
    dog.say_for_sec("Xayr~", 2)
    cat.say_for_sec("Yaxshi boring!", 2)
```
{% endcode %}

Ushbu kodni tushunish ham intuitivdir. Obyekt amalga oshirishi mumkin bo'lgan harakatlardan biri bu obyekt ichidagi **say\_for\_sec** funksiyasidan (usulidan) foydalanish, uninig vazifasi ma'lum soniyalar davomida biror narsa aytishda.

<figure><img src="../.gitbook/assets/Kapture 2024-07-17 at 17.11.31.gif" alt=""><figcaption></figcaption></figure>

Shu bilan Pygame Zerodan foydalangan holda Entry boshlang'ich kitobidagi birinchi misolni kodlashni yakunlandi. Nihoyat, 4-bobda “O‘yin tsiklini tushunish”da aytib o‘tganimdek, Pygame Zero yordamida matn kodlash va Entry blokli kodlash o‘rtasidagi farq shundan iboratki, Entryda kuchuk va mushuk obyektlari har biri mustaqil ravishda mavjud bo‘lgan va obyektlarga mos keladigan kodlash ham mustaqil ravishda har biri uchun mavjud bo‘lgan, lekin Pygame Zero hali bunday parallel/sinxronlikni qo'llab-quvvatlamaydi ([batafsil ma'lumot uchun oldingi kitobga qarang](https://roboticsware.gitbook.io/entry-python/dasturlash_paradigma/ketma_ketlik-parallel)). Agar siz hozirgacha o'yin siklining asosiy tamoyillarini va obyektlarning asosiy tushunchalarini yaxshi tushunsangiz, qolgan misollarni kodlash qiyin bo'lmaydi.
