---
title: "Internet aslida nima?"
date: 2026-02-07
draft: false
description: "Internetning 'boshi' qayerda? Ma'lumotlar nega aralashib ketmaydi va elektr nima uchun kerak?"
tags: ["Infrastructure", "Internet", "Hardware", "Network Basics"]
---

# Internet — bu "Bulut" emas, bu yer ostidagi kabellar

Biz ko'pincha "Internetga kirdim" yoki "Faylni bulutga (Cloud) yukladim" deymiz. Bu so'zlar odamlarda Internet xuddi havodagi ko'rinmas to'lqin, deb o'ylashiga sabab bo'ladi.

Haqiqat shundaki: **Internet — bu yer osti va suv ostida yotgan millionlab kilometr kabellar.**

Agar hozir shu maqolani o'qiyotgan bo'lsangiz, demak ma'lumotlar telefoningizga havoda uchib kelgani yo'q. Ular uzoq masofadan, aniq fizik yo'llar orqali yetib keldi. Keling, bu tizim qanday ishlashini savol-javob tarzida ko'rib chiqamiz.

---

# 1. Internetning boshi qayerda? Uni kim yoqib o'chiradi?

Ko'pchilik Internetni bitta katta markazdan boshqariladi deb o'ylaydi. Go'yoki qayerdadir "Bosh kompyuter" bor va u o'chsa, hamma narsa o'chadi.

**Javob:** Internetning boshi ham, oxiri ham yo'q. Uning markazi mavjud emas.

Internet — bu **o'rgimchak to'ri**. Agar to'rning bir ipi uzilsa, o'rgimchak boshqa ip orqali yuraveradi.
* Agar AQShdagi kabellar uzilsa, biz Yevropa orqali ulanamiz.
* Agar Yevropa uzilsa, Osiyo orqali yo'l topamiz.

Shuning uchun Internetni butunlay o'chirib qo'yadigan "bitta tugma" mavjud emas. U minglab mustaqil tarmoqlarning bir-biriga ulanishidan hosil bo'lgan.

---

# 2. Internet elektr talab qiladimi?

Albatta. Internet — bu shunchaki sim emas, u **aktiv** ishlaydigan tizimdir.

Ma'lumotlar (videolar, rasmlar) kabellar ichidan **yorug'lik** yoki **elektr signali** ko'rinishida o'tadi. Lekin signal masofa uzoqlashgani sari so'nib boradi (xuddi baqirganda ovoz uzoqqa bormagani kabi).

Shuning uchun okean tubidagi kabellarda har 50-100 kilometrda **Repeater (Kuchaytirgich)** qurilmalari o'rnatilgan.
* Bu qurilmalar suv ostida yotadi.
* Ular so'nayotgan signalni tutib olib, qaytadan kuchaytirib, keyingi manzilga otadi.
* Bu qurilmalar ishlashi uchun qirg'oqdan kabel ichi orqali minglab voltli elektr toki yuborib turiladi.

Agar elektr o'chsa, kuchaytirgichlar to'xtaydi va signal yo'qoladi. Internet ham o'chadi.



---

# 3. Millionlab odamlar bir vaqtda kirganda, nega ma'lumot aralashib ketmaydi?

Bu eng qiziq savol. Bitta kabeldan millionlab odamning videosi, o'yini va rasmlari o'tadi. Nega mening videoyim qo'shnimning telefoniga borib qolmaydi?

**Javob:** Ma'lumotlar butunligicha emas, **Paketlar**ga bo'linib va markalanib yuboriladi.

**Oddiy misol:**
Tasavvur qiling, katta konveyer lentasi (Kabel) ketyapti. Unda minglab qutilar bor.
* Sizning videongiz 1000 ta mayda qutiga (paketga) bo'lingan. Har bir qutining ustiga **"Bu Ali uchun, IP manzili: 192.168.1.5"** deb yozilgan.
* Qo'shningizning o'yini ham 1000 ta qutiga bo'lingan. Ustiga **"Bu Vali uchun, IP manzili: 192.168.1.6"** deb yozilgan.

Bu qutilar kabelda aralashib ketaveradi. Lekin ular manzilga (Routerga) yetib kelganda, Router har bir qutini (paketni) o'qiydi:
* *"Bu Ali uchun ekan"* — deb sizning telefoningizga uzatadi.
* *"Bu Vali uchun ekan"* — deb qo'shnining kompyuteriga yuboradi.

Bu jarayon soniyasiga millionlab marta sodir bo'ladi, shuning uchun biz uzilishni sezmaymiz.



---

# 4. Router va Radioto'lqinlar:

Ma'lumotlar okean tubidan, chegaradan va shahar ko'chalaridan o'tib, uyingizgacha **Kabel** orqali keldi. Uyingizga kirgan kabel **Router** (Wi-Fi qutisi)ga ulandi.

Router ikki ishni bajaradi:
1.  **Tarjimonlik:** Kabeldan kelayotgan elektr yoki yorug'lik signallarini oladi va ularni **Radioto'lqinga** aylantiradi.
2.  **Antenna:** Bu to'lqinlarni havoga tarqatadi.

**Radioto'lqin nima?**
Bu ko'zga ko'rinmas yorug'likka o'xshaydi. Routerlar asosan ikkita chastotada ishlaydi:
* **2.4 GHz:** To'lqinlar uzun, devorlardan yaxshi o'tadi, lekin sekinroq.
* **5 GHz:** To'lqinlar qisqa va tez, lekin devorlardan o'tishi qiyin.

Telefoningizda "Wi-Fi antennasi" bor. U havodagi shu to'lqinlarni tutib oladi va qaytadan videoga aylantirib, ekraningizda ko'rsatadi.

---

# 5. Keling, jarayonni to'liq ko'ramiz

Siz telefonda youtube'ga kirib biror videoni ko'rish uchun "Play" tugmasini bosganingizda nima sodir bo'lishini ko'z oldingizga keltiring:

1.  **Siz:** Ekranni bosdingiz. Telefoningiz buni radioto'lqinga aylantirib, Routerga yubordi.
2.  **Router:** To'lqinni qabul qilib, kabel signaliga aylantirdi va ko'chaga uzatdi.
3.  **Provayder:** Signalni shahardan olib chiqib, xalqaro magistralga uladi.
4.  **Okean:** Signal suv osti kabelidagi kuchaytirgichlar (Repeater) yordamida elektr bilan quvvatlanib, boshqa qit'adagi Data Centerga yetib bordi.
5.  **Server:** Videoni topdi, uni mayda **Paket**larga bo'ldi, har biriga sizning **IP manzilingizni** yozib, ortga jo'natdi.
6.  **Qaytish:** Paketlar millionlab boshqa ma'lumotlar bilan birga aralashib keldi, lekin Router ularni ajratib olib, aynan sizga radioto'lqin orqali uzatdi.

Bu borib-kelish jarayoni atigi **bir necha millisoniyada** sodir bo'ladi.

---

# Xulosa

Internet — bu insoniyat qurgan eng murakkab fizik tizimdir. U ishlashi uchun doimiy elektr energiyasi, butun dunyo bo'ylab yotqizilgan simlar va millionlab tonna temir uskunalar kerak bo'ladi.

Keyingi safar video ko'rayotganingizda, bu tasvirlar sizga yetib kelishi uchun okean tubidagi qorong'ulikdan yorug'lik tezligida o'tib kelganini eslang.