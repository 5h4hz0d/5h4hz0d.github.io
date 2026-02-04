---
title: "Foremost: O'chirilgan fayllarni qayta tiklash"
date: 2026-02-04
draft: false
description: "Linux muhitida foremost yordamida o'chib ketgan ma'lumotlarni tiklash bo'yicha qo'llanma."
tags: ["Forensics", "Recovery", "Kali Linux", "Manual"]
---

# "Delete" tugmasi faylni to'liq o'chirmaydi

Ko'pchilik foydalanuvchilar faylni "Savat"dan (Recycle Bin) o'chirib yuborganda, u butunlay yo'qoladi deb o'ylashadi.

Aslida jarayon biroz boshqacha. Operatsion tizim faylni darhol o'chirib yubormaydi. U shunchaki diskdagi o'sha fayl joylashgan sektorlarni "bo'sh" deb belgilab qo'yadi. Agar o'sha joyga yangi ma'lumot yozilmasa, eski fayl uzoq vaqt davomida saqlanib turishi mumkin.

Bugun Kali Linux tizimidagi **Foremost** vositasi yordamida o'chirilgan fayllarni qanday tiklash mumkinligini ko'rib chiqamiz.

---

# 1. Vaziyat: Fayl yo'qolganda nima qilish kerak?

Tasavvur qiling, sizda fleshka (USB Drive) bor va undagi muhim rasm yoki hujjat tasodifan o'chirib yuborildi.

Bunday holatda eng muhim qoida: **Diskka hech narsa yozmang.** Agar fleshkaga yangi fayl tashlasangiz, u eski faylning ustiga yozilib ketishi mumkin va uni tiklash imkonsiz bo'lib qoladi.

Biz hozir `foremost` yordamida o'sha o'chgan faylni qidirib ko'ramiz.

---

# 2. Disk nomini aniqlash

Avvalo, tizim fleshkani qaysi nom bilan ko'rayotganini aniqlab olishimiz kerak. Buning uchun terminalda quyidagi buyruqni ishlatamiz:

```bash
lsblk
```

Bu buyruq barcha ulangan disklarni ro'yxat qiladi. Odatda asosiy xotira `sda`, qo'shimcha ulangan fleshkalar esa `sdb` yoki `sdc` bo'ladi. Hajmiga qarab (masalan, 16GB) o'z fleshkangizni topib oling.

*Qo'llanma uchun biz fleshkani: `/dev/sdb` deb hisoblaymiz.*

---

# 3. Fayllarni tiklash jarayoni

Endi `foremost` dasturini ishga tushiramiz. Bu dastur disk xotirasini skaner qiladi va fayl formatlariga qarab (Header/Footer) ma'lumotlarni tiklaydi.

Misol uchun, bizga faqat **JPG** formatidagi rasmlar kerak bo'lsa, quyidagi buyruqni kiritamiz:

```bash
sudo foremost -t jpg -i /dev/sdb -o tiklangan_fayllar
```

Buyruqning tahlili:
* **`-t jpg`**: Qidirilayotgan fayl turi. (Barcha turlarni qidirish uchun `all` deb yozish mumkin).
* **`-i /dev/sdb`**: Tekshiriladigan disk (Input).
* **`-o tiklangan_fayllar`**: Natijalar saqlanadigan papka nomi (Output).

Buyruq ishga tushgach, jarayon disk hajmidan kelib chiqib biroz vaqt olishi mumkin.

---

# 4. Natijani tekshirish

Jarayon tugagach, biz ko'rsatgan papka ichini tekshiramiz:

```bash
ls tiklangan_fayllar/jpg/
```

Agar fayllar ustiga boshqa ma'lumot yozilib ketmagan bo'lsa, papka ichida o'chirilgan rasmlar paydo bo'ladi. Tiklangan fayllarning nomi odatda o'zgarib qoladi (masalan, `00015.jpg`), lekin faylning o'zi va sifati saqlanib qoladi.

---

# Xulosa

Ushbu amaliyot orqali quyidagilarni bilib oldik:

1.  **Faylni tiklash imkoniyati:** Muhim ma'lumot o'chib ketganda, maxsus vositalar yordamida uni qaytarish mumkin.
2.  **Ma'lumot xavfsizligi:** Shaxsiy qurilmalarni (telefon, noutbuk, fleshka) birovga berish yoki sotishdan oldin oddiy "Format" qilish yetarli emas. Mutaxassislar undagi ma'lumotlarni tiklab olishi mumkin.

Foremost — bu tizim ma'murlari va kiberxavfsizlik mutaxassislari uchun oddiy lekin foydali vositadir.