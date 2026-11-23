# BSN Textile - 5 Dilli Kapsamlı Sözlük ve Lokalizasyon Mimarisi (i18n Architecture)

Bu doküman; **BSN Textile** web platformunun 5 dilli altyapısı (`TR`, `EN`, `AR`, `RU`, `FA`) için tüm terim, menü, metrik, form ve içerik sözlüğünü; frontend JSON veri şablonlarını ve RTL/LTR yönelim kurallarını içermektedir.

---

## 1. Dil Matrisi ve Genel Bilgiler

| Kod | Dil | Bölge / Pazar | Yönelim (Dir) | Yazı Tipi Ailesi |
| :--- | :--- | :--- | :--- | :--- |
| **TR** | Türkçe | Türkiye / Genel Merkez | LTR | Inter / Playfair Display |
| **EN** | English | Global, Avrupa & ABD | LTR | Inter / Playfair Display |
| **AR** | العربية (Arapça) | Körfez (KSA, BAE, Katar) & MENA | RTL | Cairo / IBM Plex Sans Arabic |
| **RU** | Русский (Rusça) | Rusya, BDT & Doğu Avrupa | LTR | Inter / Playfair Display Cyrillic |
| **FA** | فارسی (Farsça) | İran & Bölgesel İhracat | RTL | Vazirmatn / Shabnam |

---

## 2. Navigasyon, Butonlar ve Genel UI Sözlüğü

| Anahtar (Key) | Türkçe (TR) | English (EN) | العربية (AR) | Русский (RU) | فارسی (FA) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `nav.home` | Ana Sayfa | Home | الرئيسية | Главная | صفحه اصلی |
| `nav.products` | Ürünler | Products | المنتجات | Продукция | محصولات |
| `nav.about` | Kurumsal | About Us | من نحن | О компании | درباره ما |
| `nav.production` | Üretim Altyapısı | Manufacturing | البنية التحتية للإنتاج | Производство | زیرساخت تولید |
| `nav.catalogue` | Dijital Katalog | Digital Catalogue | الكتالوج الرقمي | Цифровой каталог | کاتالوگ دیجیتال |
| `nav.contact` | İletişim | Contact | اتصل بنا | Контакты | تماس با ما |
| `cta.rfq` | Teklif & Numune İste | Request RFQ & Sample | طلب عرض سعر وعينة | Запрос КП и образцов | استعلام قیمت و نمونه |
| `cta.download_pdf` | Kataloğu İndir (PDF) | Download Catalogue (PDF) | تحميل الكتالوج (PDF) | Скачать каталог (PDF) | دانلود کاتالوگ (PDF) |
| `cta.whatsapp` | Doğrudan WhatsApp | Direct WhatsApp | واتساب مباشر | Написать в WhatsApp | واتس‌اپ مستقیم |
| `cta.explore_line` | Üretim Hattını İncele | Explore Production Line | استكشف خط الإنتاج | Подробнее о линии | بررسی خط تولید |
| `cta.submit` | Talebi Gönder | Submit Request | إرسال الطلب | Отправить заявку | ارسال درخواست |

---

## 3. 4 Temel Ürün Kategorisi ve Açıklamaları

### 01 / Deniz Şortu (Swim Shorts)
- **TR:**
  - *Başlık:* Deniz Şortu Özel Üretim Çözümleri
  - *Spot:* Koleksiyonun öne çıkan uzmanlık alanı. Özel su itici mikro kumaşlar ve hızlı kuruyan apreler.
  - *Özellikler:* 110-140 GSM Hızlı Kuruyan Polyester, Klor & Tuz Dirençli, Özel Kuşgözü & Kordon.
- **EN:**
  - *Title:* Custom Swim Shorts Manufacturing Solutions
  - *Spot:* Our flagship manufacturing expertise. Specialized quick-dry water-repellent micro fabrics.
  - *Specs:* 110-140 GSM Quick-Dry Polyester, Chlorine & Salt Water Resistant, Custom Eyelets & Drawstrings.
- **AR:**
  - *Title:* حلول تصنيع شورتات السباحة المخصصة
  - *Spot:* مجال تخصصنا الرائد. أقمشة ميكرو خاصة طاردة للماء وسريعة الجفاف.
  - *Specs:* بوليستر سريع الجفاف 110-140 غرام، مقاوم للكلور والملح، حلقات وأربطة مخصصة.
- **RU:**
  - *Title:* Производство шорт для плавания на заказ
  - *Spot:* Главная производственная специализация. Быстросохнущие микроткани с водоотталкивающей пропиткой.
  - *Specs:* 110-140 GSM Быстросохнущий полиэстер, устойчивость к хлору и соли, брендированная фурнитура.
- **FA:**
  - *Title:* راه‌کارهای تولید سفارشی شلوارک شنا
  - *Spot:* حوزه تخصصی و پرچمدار مجموعه. پارچه‌های میکرو دافع آب با قابلیت خشک‌شدن سریع.
  - *Specs:* پلی‌استر ۱۱۰-۱۴۰ گرم با خشک‌شدن سریع، مقاوم در برابر کلر و شوری آب، بند و یراق‌آلات اختصاصی.

### 02 / Pantolon (Knit Pants)
- **TR:**
  - *Başlık:* Pantolon & Örme Giyim Üretim Çözümleri
  - *Spot:* Örme kumaş ağırlıklı kadın ve erkek modelleri. 280 - 450 GSM pamuk ve kilit dikiş kalitesi.
  - *Özellikler:* 280-450 GSM Ağır Örme Pamuk / 3 İplik Şardonlu, Çift İğne Kilit Dikiş, Ön Çekmezlik İşlemi.
- **EN:**
  - *Title:* Knit Pants & Streetwear Trousers Manufacturing
  - *Spot:* Premium knitwear pants for men and women. 280 - 450 GSM heavy cotton and flatlock seam durability.
  - *Specs:* 280-450 GSM Heavy Cotton Fleece / French Terry, Flatlock Stitching, Pre-Shrunk Finishing.
- **AR:**
  - *Title:* حلول تصنيع البناطيل وألبسة التريكو
  - *Spot:* موديلات رجالية ونسائية تركز على الأقمشة المحبوكة. قطن فاخر 280 - 450 غرام ومتانة درزات القفل.
  - *Specs:* قطن ثقيل محبوك 280-450 غرام / قطن فرنسي مشطوب، خياطة متينة ومقاومة للانكماش.
- **RU:**
  - *Title:* Производство трикотажных брюк на заказ
  - *Spot:* Мужские и женские модели из премиального трикотажа. Хлопок 280 - 450 GSM и сверхпрочные плоские швы.
  - *Specs:* 280-450 GSM Плотный футер / французский терри, усиленные швы flatlock, декатировка полотна.
- **FA:**
  - *Title:* راه‌کارهای تولید شلوار و پوشاک تریکو
  - *Spot:* مدل‌های زنانه و مردانه با تکیه بر پارچه‌های تریکو. پنبه سنگین ۲۸۰ تا ۴۵۰ گرم و دوخت قفل بادوام.
  - *Specs:* پنبه ضخیم تریکو ۲۸۰-۴۵۰ گرم / دورس سه نخ، دوخت دو سوزنه صنعتی، آبرفت‌گیری شده.

### 03 / Kadın Elbise (Women's Dresses)
- **TR:**
  - *Başlık:* Kadın Elbise & Dokuma Özel Üretim Çözümleri
  - *Spot:* Yazlık, günlük ve rahat kesim elbiseler. Viskon, keten, saf ipek karışımları ve hassas drapaj desteği.
  - *Özellikler:* Viskon, Keten, Tencel & İpek Karışımları, Dijital / Rotasyon Baskı, Hassas Drapaj & Fransız Dikişi.
- **EN:**
  - *Title:* Women's Dresses & Woven Apparel Manufacturing
  - *Spot:* Resort, casual and elegant silhouettes. Viscose, linen, pure silk blends with precision drapery.
  - *Specs:* Viscose, Linen, Tencel & Silk Blends, Digital / Rotary Screen Printing, French Seams.
- **AR:**
  - *Title:* حلول تصنيع الفساتين النسائية والأنسجة
  - *Spot:* فساتين صيفية ويومية بقصات مريحة وراقية. مزيج الفسكوز والكتان والحرير مع ثنيات متقنة.
  - *Specs:* مزيج فسكوز وكتان وتنسل وحرير، طباعة رقمية دوارة، درزات فرنسية مخفية.
- **RU:**
  - *Title:* Производство женских платьев и текстиля
  - *Spot:* Летние, повседневные и премиальные платья. Вискоза, лен, шелк и безупречная посадка по фигуре.
  - *Specs:* Смеси вискозы, льна, тенселя и шелка, цифровая и ротационная печать, французский шов.
- **FA:**
  - *Title:* راه‌کارهای تولید پیراهن زنانه و منسوجات
  - *Spot:* پیراهن‌های تابستانه، روزمره و فاخر. ترکیبات ویسکوز، کتان، ابریشم و دراپه دقیق.
  - *Specs:* ترکیبات ویسکوز، کتان، تنسل و ابریشم، چاپ دیجیتال، دوخت ظریف فرانسوی.

### 04 / Sokak Giyim (Streetwear)
- **TR:**
  - *Başlık:* Sokak Giyim & Ağır Gramaj Koleksiyonları
  - *Spot:* Modern ve konforlu günlük koleksiyonlar. Oversize kalıplar, yıkama efektleri ve özel baskı teknikleri.
  - *Özellikler:* 320-500 GSM Heavyweight Hoodie & Sweatshirt, Acid/Vintage Wash, Kabartma (Puff) & Serigrafi Baskı.
- **EN:**
  - *Title:* Streetwear & Heavyweight Apparel Manufacturing
  - *Spot:* Contemporary oversized street fashion. High-density fabrics, vintage wash effects, and specialty prints.
  - *Specs:* 320-500 GSM Heavyweight Hoodie & Tees, Acid / Vintage Pigment Wash, Puff Screen Printing & Embroidery.
- **AR:**
  - *Title:* ملابس الشارع ومجموعات الأوزان الثقيلة
  - *Spot:* مجموعات عصرية ومريحة بنمط الشارع. مقاسات واسعة (Oversize)، تأثيرات الغسيل العتيق وتقنيات طباعة خاصة.
  - *Specs:* هودي وتيشيرتات ثقيلة 320-500 غرام، غسيل أسيدي عتيق، طباعة بارزة (Puff) وتطريز عالي الكثافة.
- **RU:**
  - *Title:* Производство уличной одежды (Streetwear)
  - *Spot:* Современная одежда свободного кроя (Oversize). Тяжелый хлопок, винтажная варка и сложные виды печати.
  - *Specs:* Худи и футболки 320-500 GSM, винтажная варка (acid/stone wash), объемная шелкография (puff) и вышивка.
- **FA:**
  - *Title:* پوشاک استریت‌ویر و پارچه‌های سنگین
  - *Spot:* کلکسیون‌های مدرن شهری با تن‌خور اورسایز، تکنیک‌های شستشوی وینتیج و چاپ‌های سفارشی.
  - *Specs:* هودی و تی‌شرت‌های ۳۲۰ تا ۵۰۰ گرم، شستشوی وینتیج و اسیدواش، چاپ پفکی و گلدوزی متراکم.

---

## 4. B2B İhracat Metrikleri ve Fabrika Standartları Sözlüğü

| Anahtar (Key) | Türkçe (TR) | English (EN) | العربية (AR) | Русский (RU) | فارسی (FA) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `metric.moq` | Minimum Sipariş (MOQ): 500 Adet/Model | Minimum Order (MOQ): 500 Pcs/Style | الحد الأدنى للطلب (MOQ): 500 قطعة/موديل | Минимальный заказ (MOQ): 500 шт/модель | حداقل سفارش (MOQ): ۵۰۰ عدد/مدل |
| `metric.lead_time` | Üretim Termini: 3 - 4 Hafta | Production Lead Time: 3 - 4 Weeks | مدة الإنتاج: 3 - 4 أسابيع | Сроки производства: 3 - 4 недели | زمان تحویل تولید: ۳ تا ۴ هفته |
| `metric.sample_time` | Numune Hazırlık: 5 - 7 İş Günü | Sample Turnaround: 5 - 7 Days | تجهيز العينات: 5 - 7 أيام عمل | Изготовление образцов: 5 - 7 рабочих дней | آماده‌سازی نمونه: ۵ تا ۷ روز کاری |
| `metric.capacity` | Aylık Kapasite: 250.000+ Adet | Monthly Capacity: 250,000+ Units | الطاقة الإنتاجية الشهرية: +250,000 قطعة | Мощность в месяц: 250 000+ единиц | ظرفیت تولید ماهانه: +۲۵۰,۰۰۰ عدد |
| `metric.quality` | Kalite Standardı: AQL 1.5 Seviye II | Quality Standard: AQL 1.5 Level II | معيار الجودة: AQL 1.5 المستوى الثاني | Контроль качества: AQL 1.5 Уровень II | استاندارد کنترل کیفیت: AQL 1.5 سطح ۲ |
| `metric.certificates` | Sertifikalar: OEKO-TEX Standard 100, BSCI, ISO 9001, GOTS | Certifications: OEKO-TEX Standard 100, BSCI, ISO 9001, GOTS | الشهادات: OEKO-TEX Standard 100, BSCI, ISO 9001, GOTS | Сертификаты: OEKO-TEX Standard 100, BSCI, ISO 9001, GOTS | گواهینامه‌ها: OEKO-TEX Standard 100, BSCI, ISO 9001, GOTS |

---

## 5. İletişim Bilgileri ve Tesis Tanımları

| Anahtar (Key) | Türkçe (TR) | English (EN) | العربية (AR) | Русский (RU) | فارسی (FA) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `contact.headquarters` | İstanbul Merkez Ofis & Modelhane | Istanbul HQ & Design Atelier | المقر الرئيسي واستوديو التصميم - إسطنبول | Центральный офис и конструкторское бюро в Стамбуле | دفتر مرکزی و کارگاه الگو - استانبول |
| `contact.factory_van` | Van Tekstilkent Fabrika Tesisleri | Van Tekstilkent Manufacturing Plants | مجمعات مصانع تكستيل كينت في وان | Фабричные комплексы Текстилькент в городе Ван | مجتمع کارخانجات تکستیل‌کنت - وان |
| `contact.address_ist` | Evren Mah. Çimen Sok. No:19 Kat:4 Avrasya Plaza Güneşli, Bağcılar / İstanbul | Evren Mah. Cimen Sok. No:19 Fl:4 Avrasya Plaza Gunesli, Bagcilar / Istanbul / Turkey | حي إفرين، شارع تشيمن رقم 19، الطابق 4، أوراسيا بلازا غونشلي، باغلار / إسطنبول | Район Эврен, ул. Чимен №19, эт. 4, БЦ Avrasya Plaza, Багджилар / Стамбул | محله اورن، کوچه چیمن، پلاک ۱۹، طبقه ۴، برج اوراسیا، باغجیلار / استانبول |
| `contact.address_van1` | Süphan Mah. Van Tekstilkent 1009 Sk. No:3I Edremit / Van | Suphan Mah. Van Tekstilkent 1009 St. No:3I Edremit / Van / Turkey | حي سوبهان، تكستيل كينت زقاق 1009 رقم 3I، إدرميت / وان | Район Супхан, Текстилькент, ул. 1009 №3I, Эдремит / Ван | محله سوبهان، تکستیل‌کنت، خ ۱۰۰۹، پلاک ۳I، ادرمیت / وان |
| `contact.address_van2` | Kurubaş Mah. Van Tekstilkent 123 Sk. No:440 Edremit / Van | Kurubas Mah. Van Tekstilkent 123 St. No:440 Edremit / Van / Turkey | حي قورباش، تكستيل كينت زقاق 123 رقم 440، إدرميت / وان | Район Курубаш, Текстилькент, ул. 123 №440, Эдремит / Ван | محله قوروباش، تکستیل‌کنت، خ ۱۲۳، پلاک ۴۴۰، ادرمیت / وان |
| `contact.phone` | +90 535 233 6073 | +90 535 233 6073 | +90 535 233 6073 | +90 535 233 6073 | +90 535 233 6073 |
| `contact.email` | sedatuzumcu@bsntextile.com / info@bsntextile.com | sedatuzumcu@bsntextile.com / info@bsntextile.com | sedatuzumcu@bsntextile.com / info@bsntextile.com | sedatuzumcu@bsntextile.com / info@bsntextile.com | sedatuzumcu@bsntextile.com / info@bsntextile.com |

---

## 6. PDF Katalog Dosya İsimleri Standart Tablosu

| Kategori | Türkçe (TR) | English (EN) | العربية (AR) | Русский (RU) | فارسی (FA) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Genel Katalog** | `BSN-Genel-Uretim-Katalogu-2025.pdf` | `BSN-General-OEM-Catalogue-2025.pdf` | `BSN-General-Catalogue-2025-AR.pdf` | `BSN-General-Catalogue-2025-RU.pdf` | `BSN-General-Catalogue-2025-FA.pdf` |
| **Deniz Şortu** | `BSN-Deniz-Sortu-Koleksiyonu-2025.pdf` | `BSN-Swim-Shorts-Collection-2025.pdf` | `BSN-Swim-Shorts-Lookbook-2025.pdf` | `BSN-Swim-Shorts-Lookbook-2025.pdf` | `BSN-Swim-Shorts-Lookbook-2025.pdf` |
| **Pantolon** | `BSN-Pantolon-Koleksiyonu-2025.pdf` | `BSN-Knit-Pants-Collection-2025.pdf` | `BSN-Knit-Pants-Lookbook-2025.pdf` | `BSN-Knit-Pants-Lookbook-2025.pdf` | `BSN-Knit-Pants-Lookbook-2025.pdf` |
| **Kadın Elbise** | `BSN-Kadin-Elbise-Koleksiyonu-2025.pdf` | `BSN-Womens-Dress-Collection-2025.pdf` | `BSN-Womens-Dress-Lookbook-2025.pdf` | `BSN-Womens-Dress-Lookbook-2025.pdf` | `BSN-Womens-Dress-Lookbook-2025.pdf` |
| **Sokak Giyim** | `BSN-Sokak-Giyim-Koleksiyonu-2025.pdf` | `BSN-Streetwear-Collection-2025.pdf` | `BSN-Streetwear-Lookbook-2025.pdf` | `BSN-Streetwear-Lookbook-2025.pdf` | `BSN-Streetwear-Lookbook-2025.pdf` |

---

## 7. Frontend i18n JSON Veri Mimarisi (Örnek Yapı)

```json
{
  "locale": "en",
  "direction": "ltr",
  "brand": {
    "name": "BSN Textile",
    "tagline": "Industrial OEM & ODM Apparel Manufacturing in Turkey",
    "certifications": ["OEKO-TEX Standard 100", "BSCI", "ISO 9001", "GOTS"]
  },
  "metrics": {
    "moq": "500 pcs/colorway",
    "lead_time": "3-4 weeks delivery",
    "sampling": "5-7 business days",
    "quality_standard": "AQL 1.5 Level II"
  },
  "categories": [
    {
      "id": "swim-shorts",
      "slug": "/swim-shorts",
      "title": "Swim Shorts",
      "spot": "Flagship quick-dry and water-repellent micro fabric manufacturing.",
      "gsm": "110-140 GSM",
      "catalogue_file": "BSN-Swim-Shorts-Collection-2025.pdf"
    },
    {
      "id": "knit-pants",
      "slug": "/knit-pants",
      "title": "Pants",
      "spot": "Premium heavy cotton knitwear pants with reinforced flatlock stitching.",
      "gsm": "280-450 GSM",
      "catalogue_file": "BSN-Knit-Pants-Collection-2025.pdf"
    },
    {
      "id": "womens-dress",
      "slug": "/womens-dress",
      "title": "Women's Dresses",
      "spot": "Fluid viscose, linen, and silk resort wear with precision drapery.",
      "gsm": "90-220 GSM",
      "catalogue_file": "BSN-Womens-Dress-Collection-2025.pdf"
    },
    {
      "id": "streetwear",
      "slug": "/streetwear",
      "title": "Streetwear",
      "spot": "High-density oversize heavyweight hoodies and custom vintage washes.",
      "gsm": "320-500 GSM",
      "catalogue_file": "BSN-Streetwear-Collection-2025.pdf"
    }
  ]
}
```

---

## 8. Teknik Entegrasyon & RTL Kuralları
1. **HTML Kök Etiketi:**
   - TR / EN / RU: `<html lang="en" dir="ltr">`
   - AR / FA: `<html lang="ar" dir="rtl">`
2. **CSS / Tailwind Uyumlandırması:**
   - Sağ/sol boşluklar için mantıksal özellikler kullanılır (`ms-` / `me-` yerine `ml-` / `mr-`, `start-` / `end-` yerine `left-` / `right-`).
3. **Yazı Tipleri:**
   - Arapça için `Cairo` veya `IBM Plex Sans Arabic`, Farsça için `Vazirmatn` fontları projeye dinamik olarak eklenir.
