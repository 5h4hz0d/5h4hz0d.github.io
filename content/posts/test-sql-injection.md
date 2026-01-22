---
title: "Web Security: SQL Injection Basics"
date: 2026-01-14
draft: false
description: "SQL Injection hujumini tushunish va himoyalanish."
tags: ["Web", "SQLi", "OWASP"]
---

# SQL Injection nima?

Bu veb-saytning ma'lumotlar bazasiga ruxsatsiz so'rov yuborish usulidir.

### Payload misoli:

```sql
' OR 1=1 --
```

Bu so'rov orqali admin panelga parolsiz kirish mumkin bo'lishi mumkin.
