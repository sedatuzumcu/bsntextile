# 🛠️ BSN Textile — Geliştirici API ve Form Entegrasyon Spesifikasyonu (Developer Handover)

Bu döküman, **BSN Textile (bsntextile.com)** küresel B2B hazır giyim ve fason üretim platformunda yer alan tüm formların, API uç noktalarının (endpoints), veri şemalarının (payloads), çok dilli altyapının ve üçüncü taraf servis entegrasyonlarının frontend ve backend ekiplerince hayata geçirilmesi için hazırlanmıştır.

---

## 📌 1. Mimari Genel Bakış ve Temel Standartlar

- **Protokol:** HTTPS / RESTful JSON API (İsteğe bağlı GraphQL desteği)
- **Base URL:** `https://api.bsntextile.com/v1`
- **Yetkilendirme:** 
  - Genel Ziyaretçi / Form Gönderimleri: `X-API-KEY` (Public Client Token) & Cloudflare Turnstile / reCAPTCHA v3 Token
  - Yönetim & CRM Webhookları: `Bearer <JWT_TOKEN>`
- **Veri Tipleri & Karakter Seti:** `application/json`, `UTF-8` (Çok dilli AR/FA RTL desteği için zorunlu)
- **Hız Sınırı (Rate Limiting):** IP başına dakikada maksimum 10 form gönderim isteği (Spam ve bot önleme).

---

## 📋 2. Form ve API Uç Noktaları (Endpoints)

### 2.1. Hızlı RFQ & Teklif Sihirbazı API
Masaüstü ve mobil ekranlarda yer alan 5 adımlı interaktif fiyat teklifi ve numune talep sihirbazını yönetir.

- **Endpoint:** `POST /rfq/submit`
- **Content-Type:** `multipart/form-data` (Tech-Pack & Referans görsel yüklemeleri için)
- **Açıklama:** Kullanıcının seçtiği kategori, tahmini adet, kumaş gramajı ve teknik çizim dosyasını alır.

#### Request Payload (Şema):
```json
{
  "locale": "tr", // "tr" | "en" | "ar" | "ru" | "fa"
  "category_id": "streetwear_heavyweight", // "streetwear_heavyweight" | "swim_shorts" | "knit_pants" | "women_dresses"
  "target_quantity": 500, // Sayısal değer (Asgari 500)
  "fabric_preference": {
    "fabric_type": "French Terry",
    "gsm": 450,
    "pantone_code": "19-4052 TCX",
    "organic_cert_required": true // GOTS / OEKO-TEX
  },
  "custom_notes": "Oversize fit, asit yıkama ve ön göğüste 3D puff baskı numunesi istiyoruz.",
  "target_delivery_date": "2025-09-30",
  "company_details": {
    "company_name": "Studio Sartorialist Ltd.",
    "contact_name": "Kerem Yılmaz",
    "position": "Satın Alma Direktörü",
    "email": "purchasing@studiosartorialist.com",
    "phone_country_code": "+90",
    "phone_number": "5320000000",
    "country": "TR"
  },
  "nda_agreed": true,
  "captcha_token": "0x4AAAAAAABcdEF123..."
}
```
*Not: `tech_pack_file` alanı çok parçalı dosya (multipart file: `.pdf`, `.ai`, `.dxf`, `.zip` max 50MB) olarak iletilir.*

#### Response (201 Created):
```json
{
  "status": "success",
  "data": {
    "rfq_tracking_code": "BSN-RFQ-2025-8841",
    "created_at": "2025-05-14T10:30:00Z",
    "lead_status": "PENDING_TECHNICAL_REVIEW",
    "assigned_rep": {
      "name": "Sedat Üzümcü",
      "email": "sedatuzumcu@bsntextile.com",
      "phone": "+90 535 233 6073"
    },
    "sla_guarantee": "24 hours",
    "estimated_sample_dispatch_days": "5-7 business days"
  }
}
```

---

### 2.2. Showroom & Çevrimiçi Toplantı Randevu API
İletişim sayfasındaki Koza Plaza İstanbul Showroom ziyareti veya Zoom/Teams teknik toplantı taleplerini işler.

- **Endpoint:** `POST /appointments/book`
- **Request Payload:**
```json
{
  "locale": "en",
  "appointment_type": "physical_showroom", // "physical_showroom" | "online_video_call"
  "location": "koza_plaza_istanbul", // "koza_plaza_istanbul" | "van_integrated_facility"
  "preferred_date": "2025-06-15",
  "preferred_time_slot": "14:00-15:30",
  "company_name": "Nordic Retail Group",
  "full_name": "Selin Karaca",
  "email": "selin@nordicretail.com",
  "phone": "+46 70 123 4567",
  "interests": ["luxury_knitwear", "french_seam_dresses"],
  "estimated_order_volume": "2500_plus",
  "nda_required": true
}
```

---

### 2.3. Doğrudan WhatsApp Hızlı Başlatma Yönlendiricisi (Click-to-Chat)
Mobil ve masaüstü arayüzlerdeki dinamik WhatsApp yönlendirmeleri için standartlaştırılmış URL formatı:

- **Format:** `https://api.whatsapp.com/send?phone=905352336073&text={ENCODED_MESSAGE}`
- **Örnek Mesaj Şablonları:**
  - *Ürün Detay Sayfası için:*  
    `Merhaba Sedat Bey, BSN Textile web sitenizden [Ürün Adı: BSN-HD500 500 GSM Hoodie] için 500 adetlik numune ve fiyat teklifi almak istiyorum.`
  - *Genel RFQ için:*  
    `Merhaba, B2B hazır giyim fason üretim hattınız hakkında tech-pack dosyamız ile ilgili görüşmek istiyoruz.`

---

## 🌐 3. Çok Dilli (5 Dil) Form Validasyon ve Hata Kodları

Tüm API yanıtları, gelen `locale` başlığına (`Accept-Language` veya payload `locale`) göre yerelleştirilmiş hata mesajları döndürmelidir:

| Hata Kodu | TR | EN | AR (RTL) | RU | FA (RTL) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `ERR_MIN_MOQ` | Asgari sipariş adedi 500 adettir. | Minimum order quantity is 500 pcs. | الحد الأدنى للطلب هو 500 قطعة. | Минимальный объем заказа 500 шт. | حداقل سفارش ۵۰۰ عدد می‌باشد. |
| `ERR_INVALID_EMAIL` | Lütfen geçerli bir kurumsal e-posta girin. | Please enter a valid corporate email. | يرجى إدخال بريد إلكتروني رسمي صالح. | Введите действующий корпоративный email. | لطفاً یک ایمیل سازمانی معتبر وارد کنید. |
| `ERR_TECHPACK_SIZE` | Dosya boyutu 50MB sınırını aşamaz. | File size cannot exceed 50MB. | حجم الملف لا يمكن أن يتجاوز 50 ميغابايت. | Размер файла не может превышать 50 МБ. | حجم فایل نمی‌تواند از ۵۰ مگابایت تجاوز کند. |
| `ERR_REQUIRED_FIELD` | Bu alanın doldurulması zorunludur. | This field is required. | هذا الحقل مطلوب. | Это поле обязательно для заполнения. | این فیلد الزامی است. |

---

## 🔒 4. Güvenlik, NDA ve KVKK / GDPR Uyum Protokolü

1. **Tech-Pack Şifreleme ve Depolama:**
   - Yüklenen CAD, Gerber (`.dxf`), CLO 3D (`.zprj`) ve PDF dosyaları doğrudan S3/GCS uyumlu nesne deposuna `AES-256` şifrelemeyle kaydedilir.
   - Dosyalara erişim yalnızca yetkilendirilmiş ihracat mühendislerinin tek kullanımlık imzalı URL'leri (Signed URLs, TTL: 15 dk) ile mümkündür.
2. **Dijital NDA (Gizlilik Sözleşmesi) Loglaması:**
   - `nda_agreed: true` gönderildiğinde veritabanına kullanıcının IP adresi, zaman damgası ve şirket adı ile birlikte bir dijital sözleşme referansı işlenir.
3. **Spam & Bot Güvenliği:**
   - Cloudflare Turnstile veya Google reCAPTCHA v3 score-based denetimi (Skor < 0.5 durumunda SMS OTP veya ek doğrulama).

---

## 🔄 5. Webhook & CRM Entegrasyonları

Yeni bir RFQ veya iletişim talebi geldiğinde sistemin tetiklediği dış servis entegrasyonları:

```
[Kullanıcı Formu Gönderir]
         │
         ▼
[API Gateway /api/v1/rfq/submit]
         │
         ├──► 1. Veritabanına Kayıt (PostgreSQL / MongoDB)
         ├──► 2. Dosyaları S3 Bucket'a Yükleme (Encrypted Tech-Packs)
         ├──► 3. Webhook: Şirket İçi CRM (HubSpot / Salesforce / Zoho)
         ├──► 4. Bildirim: Satış Masasına Anlık Slack / Telegram / E-posta Bildirimi
         └──► 5. Kullanıcıya Otomatik E-Posta: "RFQ Dosyanız Alındı (BSN-RFQ-XXXX)"
```

### Örnek CRM Webhook Payload:
```json
{
  "event": "lead.rfq_created",
  "lead_id": "BSN-RFQ-2025-8841",
  "customer": {
    "name": "Kerem Yılmaz",
    "company": "Studio Sartorialist Ltd.",
    "email": "purchasing@studiosartorialist.com",
    "phone": "+905320000000",
    "country": "TR"
  },
  "rfq_details": {
    "category": "streetwear_heavyweight",
    "quantity": 500,
    "gsm": 450,
    "file_url": "https://storage.bsntextile.com/secure-techpacks/BSN-RFQ-8841.zip?signature=..."
  },
  "assigned_manager": "Sedat Üzümcü"
}
```

---

## 💻 6. Frontend Geliştirici İçin Entegrasyon İpuçları

1. **State Management (Çok Adımlı RFQ):**
   - Form adımları (`step1` - `step5`) tarayıcıda `sessionStorage` veya React Hook Form / Zustand üzerinde tutulmalı, kullanıcı geri gittiğinde veriler kaybolmamalıdır.
2. **RTL Desteği:**
   - Arapça (`ar`) ve Farsça (`fa`) dillerinde `<html dir="rtl">` etiketi otomatik ayarlanmalı, CSS flex/grid hizalamaları `space-x-reverse` ve mantıksal özelliklerle (`margin-inline-start`) yönetilmelidir.
3. **Görsel ve Dosya Sürükle-Bırak:**
   - Sürükle-bırak alanında drag-enter, drag-over animasyonları ve dosya seçildiğinde dosya adı + boyut rozeti gösterimi aktiftir.

---
*BSN Textile Global B2B Teknik Entegrasyon Ekibi tarafından hazırlanmıştır.*