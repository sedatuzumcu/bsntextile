# BSN Textile - 5 Dilli Tam Entegrasyon & Kod İmplementasyon Kılavuzu

Bu belge, BSN Textile web platformunun **5 dilli (TR, EN, AR, RU, FA)** tam entegrasyonu, frontend ve backend dil yönetimi, dinamik dil değiştirici (Language Switcher) ve RTL/LTR mekanizmasını eksiksiz olarak açıklamaktadır.

---

## 1. Dil Mimarisi & Pazar Eşleşmesi

| Dil Kodu | Dil Adı | Yönelim (Dir) | Hedef İhracat Pazarı | Varsayılan Font |
| :--- | :--- | :--- | :--- | :--- |
| **TR** | Türkçe | `ltr` | Türkiye (Genel Merkez, Yerel Tedarik) | Inter, Playfair Display |
| **EN** | English | `ltr` | Global, Avrupa Birliği, Birleşik Krallık, ABD | Inter, Playfair Display |
| **AR** | العربية | `rtl` | Körfez Ülkeleri (KSA, BAE, Kuveyt, Katar), MENA | Cairo, IBM Plex Sans Arabic |
| **RU** | Русский | `ltr` | Rusya Federasyonu, BDT Ülkeleri, Doğu Avrupa | Inter Cyrillic, Playfair Display |
| **FA** | فارسی | `rtl` | İran, Kafkaslar & Bölgesel Ticaret | Vazirmatn, Shabnam |

---

## 2. URL Yönlendirme & Routing Yapısı

Çok dilli SEO ve B2B indeksleme standartlarına uygun URL yapısı:

- **Türkçe (Varsayılan):** `https://bsntextile.com/` veya `https://bsntextile.com/tr/`
  - `/tr/yuzme-sort`
  - `/tr/pantolon`
  - `/tr/bayan-elbise`
  - `/tr/sokak-giyim`
  - `/tr/katalog-rfq`
  - `/tr/iletisim`

- **İngilizce (Global B2B):** `https://bsntextile.com/en/`
  - `/en/swim-shorts`
  - `/en/knit-pants`
  - `/en/womens-dresses`
  - `/en/streetwear`
  - `/en/catalogue-rfq`
  - `/en/contact`

- **Arapça (Körfez & MENA - RTL):** `https://bsntextile.com/ar/`
  - `/ar/swim-shorts`
  - `/ar/knit-pants`
  - `/ar/womens-dresses`
  - `/ar/streetwear`
  - `/ar/catalogue-rfq`
  - `/ar/contact`

- **Rusça (BDT & Doğu Avrupa):** `https://bsntextile.com/ru/`
  - `/ru/swim-shorts`
  - `/ru/knit-pants`
  - `/ru/womens-dresses`
  - `/ru/streetwear`
  - `/ru/catalogue-rfq`
  - `/ru/contact`

- **Farsça (Bölgesel İhracat - RTL):** `https://bsntextile.com/fa/`
  - `/fa/swim-shorts`
  - `/fa/knit-pants`
  - `/fa/womens-dresses`
  - `/fa/streetwear`
  - `/fa/catalogue-rfq`
  - `/fa/contact`

---

## 3. RTL (Sağdan Sola) Dinamik Çevrim Kuralları

Arapça (`ar`) ve Farsça (`fa`) dillerinde sayfa render edildiğinde:
1. `<html>` etiketi: `<html lang="ar" dir="rtl">` veya `<html lang="fa" dir="rtl">` olarak atanır.
2. Grid ve Flexbox düzenleri mantıksal yönelim (`flex-row-reverse` veya CSS logical properties) ile otomatik aynalanır.
3. İkonlar: Geri/İleri ok ikonları (`fa-arrow-right` / `fa-arrow-left`) yönelime göre ters çevrilir; WhatsApp, telefon ve logo orijinalliğini korur.
4. Tipografi: Arapça için Google Fonts `Cairo:wght@400;600;700` veya `IBM Plex Sans Arabic`, Farsça için `Vazirmatn` CSS `@import` ile yüklenir.

---

## 4. İletişim & Fabrika Sabitleri (Tüm Dillerde Ortak)

- **Merkez Ofis:** Avrasya Plaza, Bağcılar / İstanbul
- **Fabrika 1 & 2:** Van Tekstilkent (1009 Sk. No:3I & 123 Sk. No:440) Edremit / Van
- **Doğrudan İhracat Hattı & WhatsApp:** `+90 535 233 6073`
- **Kurumsal E-posta:** `sedatuzumcu@bsntextile.com` / `info@bsntextile.com`
- **Sipariş Standartları:** MOQ: 500 Adet/Model | Termin: 3-4 Hafta | Numune: 5-7 İş Günü | Kalite: AQL 1.5 Seviye II
