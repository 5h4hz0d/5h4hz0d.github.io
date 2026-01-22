---
title: "Web Security: Reflected XSS"
date: 2026-01-12
draft: false
description: "Cross-Site Scripting (XSS) zaifligini topish."
tags: ["Web", "XSS", "Javascript"]
---

# XSS (Cross-Site Scripting)

Agar sayt foydalanuvchi kiritgan ma'lumotni filtrlamasa, quyidagi kod ishga tushishi mumkin:

```javascript
<script>alert('Hacked!');</script>
```

Bu cookie o'g'irlash uchun ishlatilishi mumkin.
