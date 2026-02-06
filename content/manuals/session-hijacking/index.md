---
title: "Session Hijacking: Xakerga parolingiz kerak emas"
date: 2026-02-06
draft: false
description: "Cookie fayllarini o'g'irlash orqali akkauntga parolsiz kirish qanday amalga oshiriladi?"
tags: ["Session Hijacking", "Cookies", "Web Security", "Manual"]
---

# Parol — eng muhim narsa emas

Ko'pchilik foydalanuvchilar o'z akkauntlarini himoya qilish uchun uzun va murakkab parollar o'ylab topishadi. "Menda 2 bosqichli himoya (2FA) bor, hech kim buzolmaydi", deb xotirjam yurishadi.

Lekin achchiq haqiqat shundaki: **Agar xaker sizning "Cookie" fayllaringizni qo'lga kiritsa, unga na loginingiz, na parolingiz va na SMS kodingiz kerak bo'ladi.** U to'g'ridan-to'g'ri sizning profilingizga kirib boradi.

Bugun biz "Session Hijacking" (Sessiyani o'g'irlash) qanday ishlashini va nima uchun havola (link) bosish bu jarayonning kaliti ekanligini ko'rib chiqamiz.

---

# 1. Cookie va Sessiya o'zi nima?

Keling, oddiy hayotiy misol keltiramiz.

Tasavvur qiling, siz qimmat mehmonxonaga keldingiz.
1.  **Ro'yxatdan o'tish (Login):** Reception'ga pasportingizni berasiz va kimligingizni tasdiqlaysiz.
2.  **Kalit karta (Cookie):** Xodim sizga xona eshigini ochadigan plastik karta beradi.

Endi diqqat qiling: Siz har safar xonangizga kirayotganda pasportingizni ko'rsatmaysiz-ku? Shunchaki kartani ishlatasiz. Mehmonxona tizimi uchun **Karta = Siz**.

Internetda ham xuddi shunday:
1.  Siz Facebookga log-parol terasiz.
2.  Facebook serveri tekshiradi va brauzeringizga **"Session Cookie"** (raqamli kalit) yuboradi.
3.  Keyingi safar saytga kirganingizda, Facebook sizdan parol so'ramaydi, u shunchaki brauzeringizdagi o'sha "Cookie"ni tekshiradi.

---

# 2. O'g'irlik qanday sodir bo'ladi?

Xakerning maqsadi — sizning parolingizni buzish emas, balki "Mehmonxona kartangizni" (Cookie) o'g'irlashdir.

Bu jarayon odatda quyidagicha kechadi:

### 1-bosqich: Qopqon
Xaker sizga zararli havola yuboradi (masalan: *"Ajoyib aksiya! Ko'rish uchun bosing"*).

### 2-bosqich: Skript ishlashi
Siz havolani bosishingiz bilan, sahifaga yashirilgan maxsus JavaScript kodi (`document.cookie`) ishga tushadi. Bu kod brauzeringiz xotirasidagi barcha faol sessiya kalitlarini nusxalab oladi.

### 3-bosqich: Uzatish
Skript o'g'irlangan "Cookie"larni xakerning serveriga yuboradi. Bularning barchasi soniyaning ulushida sodir bo'ladi, siz hech narsani sezmaysiz.

---

# 3. Xaker akkauntga qanday kiradi?

Endi xakerning qo'lida sizning "kalit kartangiz" bor. U nima qiladi?

1.  U o'z kompyuterida Facebookni ochadi (u yerda Login so'rab turibdi).
2.  U brauzerning dasturchilar bo'limini ochib, o'g'irlangan "Cookie"larni o'z brauzeriga joylashtiradi.
3.  Sahifani yangilaydi (Refresh).

**Natija:** Facebook serveri xakerni "Bu o'sha foydalanuvchi-ku, mana kaliti bor ekan" deb o'ylaydi va uni to'g'ridan-to'g'ri sizning sahifangizga kiritib yuboradi. Parol so'ralmaydi, SMS kelmaydi. Chunki tizim uchun u — sizsiz.

---

# 4. Qanday himoyalanish kerak?

Bu hujumdan saqlanishning texnik yo'llari bor, lekin eng asosiysi — foydalanuvchi madaniyatidir.

1.  **Linklarni bosmang:** Yuqorida aytganimizdek, har qanday shubhali havola — bu skript.
2.  **Saytlardan chiqib keting (Log out):** Agar begona kompyuterda (internet kafe, ishxona) Facebook yoki Emailga kirsangiz, ish tugagach shunchaki oynani yopmang. Albatta **"Chiqish" (Log out)** tugmasini bosing. Bu "kalit karta"ni yo'q qilish bilan barobar.
3.  **HTTPS:** Faqat qulf belgisi (🔒) bor saytlardan foydalaning. Ochiq Wi-Fi tarmoqlarida (kafelarda) "Cookie"larni havodan tutib olish osonroq.

# Xulosa

Eslab qoling: Parolingiz — bu uyingiz kaliti. Cookie — bu sizning vaqtinchalik ruxsatnomangiz. O'g'ri uchun qaysi biri orqali kirishning farqi yo'q.

Raqamli gigiena qoidalariga amal qiling va shubhali havolalarni **VirusTotal** orqali tekshirishni unutmang.