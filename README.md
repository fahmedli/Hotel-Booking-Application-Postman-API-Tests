# Hotel-Booking-Application-Postman-API-Tests
# 🧪 Restful Booker API Testləri (Postman)

## 📌 Layihə Haqqında

Bu layihə **Restful Booker** tətbiqi üçün Postman vasitəsilə hazırlanmış API test ssenarilərini əhatə edir.
Məqsəd rezervasiya (booking) funksionallıqlarını yoxlamaqdır: autentifikasiya, rezervasiya yaratma, məlumatları əldə etmə, yeniləmə və silmə.

---

## 🚀 İstifadə olunan texnologiyalar

* Postman
* REST API
* JSON
* HTTP metodları (GET, POST, PUT, PATCH, DELETE)

---

## 🔗 Əsas URL

```id="v07vry"
https://restful-booker.herokuapp.com
```

---

## 📂 Layihə strukturu

* **Auth**

  * Token yaratma

* **Booking**

  * Bütün booking ID-lərin alınması
  * ID ilə booking əldə etmə
  * Yeni booking yaratma
  * Booking yeniləmə (PUT)
  * Qismən yeniləmə (PATCH)
  * Booking silmə

* **Health Check**

  * API vəziyyətinin yoxlanması (Ping)

---

## 🔐 Autentifikasiya

Yeniləmə və silmə əməliyyatları üçün token tələb olunur.

### Sorğu:

```id="o8l4o1"
POST /auth
```

### Body:

```json id="3qv7bi"
{
  "username": "admin",
  "password": "password123"
}
```

### Cavab:

```json id="k9xv6f"
{
  "token": "abc123"
}
```

Token istifadə olunur:

```id="y2c8hr"
Cookie: token=your_token
```

---

## 📋 Test ssenariləri

### ✅ Müsbət testlər

* Uğurlu token yaradılması
* Bütün booking ID-lərin alınması
* Düzgün ID ilə booking əldə edilməsi
* Yeni booking yaradılması
* Token ilə booking yenilənməsi
* Token ilə booking silinməsi

### ❌ Mənfi testlər

* Yanlış login məlumatları
* Yanlış ID ilə booking sorğusu
* Token olmadan update cəhdi
* Authorization olmadan delete cəhdi
* Yanlış body göndərilməsi

---

## 🧾 Nümunə sorğu (Booking yaratma)

```json id="g7l5f3"
{
  "firstname": "Jim",
  "lastname": "Brown",
  "totalprice": 111,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2018-01-01",
    "checkout": "2019-01-01"
  },
  "additionalneeds": "Breakfast"
}
```

---

## ▶️ Necə işə salınır

1. Postman aç
2. Collection JSON faylını import et
3. (İstəyə bağlı) environment faylını əlavə et
4. Sorğuları tək-tək və ya Collection Runner ilə işə sal

---

## 📊 Yoxlama nöqtələri

* Status kodların yoxlanması (200, 201)
* Response body-nin doğrulanması
* Token yaradılması və istifadəsi
* Update və delete sonrası məlumatın düzgünlüyü

---

## 💡 Qeydlər

* API açıqdır və məlumatlar reset ola bilər
* Booking ID-lər dinamik dəyişə bilər

---

## 📎 Müəllif

Junior QA Engineer – API Testing Practice Project
