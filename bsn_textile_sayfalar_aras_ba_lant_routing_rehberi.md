# BSN Textile (bsntextile.com) — Sayfalar Arası Bağlantı (Routing & Navigation) ve URL Haritası Mimarisi

Bu döküman, BSN Textile'in 5 dilli (`TR`, `EN`, `AR`, `RU`, `FA`) masaüstü ve mobil platformundaki tüm sayfalar arası bağlantı (hyperlink / href routing) standartlarını ve yazılımcı entegrasyon kurallarını tanımlar.

---

## 1. Sayfa URL Rota Eşleşmeleri (Routing Map)

### 🇹🇷 Türkçe (TR) Sayfaları:
| Sayfa Tanımı | URL Yolu (href) | Sayfa Dosyası / Bileşeni |
| :--- | :--- | :--- |
| **Ana Sayfa** | `/` veya `/tr/` | `index.html` (Desktop: SCREEN_93 / Mobile: SCREEN_17) |
| **Kurumsal & Fabrika Altyapısı** | `/tr/kurumsal` | `kurumsal.html` (SCREEN_83) |
| **Deniz Şortu Özel Üretim** | `/tr/deniz-sortu-uretimi` | `deniz-sortu.html` (SCREEN_91 / Mobile: SCREEN_11) |
| **Örme Pantolon & Jogger** | `/tr/orme-pantolon-jogger` | `orme-pantolon.html` (SCREEN_89 / Mobile: SCREEN_7) |
| **Kadın Elbise & Dokuma Koutür** | `/tr/kadin-elbise-dokuma` | `kadin-elbise.html` (SCREEN_87 / Mobile: SCREEN_5) |
| **Ağır Gramaj Sokak Giyimi & Sweat**| `/tr/agir-gramaj-sweatshirt` | `agir-gramaj-sweatshirt.html` (SCREEN_85 / Mobile: SCREEN_9) |
| **Dijital Katalog & RFQ İletişim** | `/tr/dijital-katalog-teklif` | `dijital-katalog.html` (SCREEN_81 / Mobile: SCREEN_19) |
| **İletişim & Merkez Fabrika** | `/tr/iletisim` | `iletisim.html` (SCREEN_79 / Mobile: SCREEN_13) |

---

### 🇬🇧 İngilizce (EN) Sayfaları:
| Sayfa Tanımı | URL Yolu (href) |
| :--- | :--- |
| **Global Homepage** | `/en/` |
| **Streetwear & Heavyweight Apparel** | `/en/heavyweight-streetwear` |
| **Custom Swim Shorts** | `/en/custom-swim-shorts` |
| **Knit Pants & Engineered Joggers** | `/en/knit-pants-joggers` |
| **Women's Dresses & Woven Solutions**| `/en/womens-dresses-woven` |
| **Digital Catalogue & RFQ Hub** | `/en/digital-catalogue` |
| **Contact & Facilities Hub** | `/en/contact` |

---

### 🇷🇺 Rusça (RU) Sayfaları:
| Sayfa Tanımı | URL Yolu (href) |
| :--- | :--- |
| **Главная Страница** | `/ru/` |
| **Производство Стритвира** | `/ru/streetwear-knitwear` |
| **Производство Плавательных Шорт** | `/ru/swim-shorts` |
| **Производство Брюк и Джоггеров** | `/ru/knit-pants-joggers` |
| **Производство Женских Платьев** | `/ru/womens-dresses-woven` |
| **Цифровой Каталог & RFQ** | `/ru/catalogue-rfq` |
| **Контакты и Производство** | `/ru/contact` |

---

### 🇦🇪 Arapça (AR - RTL) Sayfaları:
| Sayfa Tanımı | URL Yolu (href) |
| :--- | :--- |
| **الصفحة الرئيسية** | `/ar/` |
| **تصنيع ملابس الشارع والأقمشة الثقيلة** | `/ar/streetwear-apparel` |
| **تصنيع شورتات السباحة المخصصة** | `/ar/swim-shorts` |
| **تصنيع بناطيل التريكو والجوغر** | `/ar/knit-pants-joggers` |
| **تصنيع الفساتين النسائية والمنسوجات** | `/ar/womens-dresses-woven` |
| **اتصل بنا ومراكز التصنيع** | `/ar/contact` |

---

### 🇮🇷 Farsça (FA - RTL) Sayfaları:
| Sayfa Tanımı | URL Yolu (href) |
| :--- | :--- |
| **صفحه اصلی** | `/fa/` |
| **تولید پوشاک خیابانی و سنگین** | `/fa/streetwear-apparel` |
| **تولید شلوارک‌های شنای سفارشی** | `/fa/swim-shorts` |
| **تولید شلوارهای بافتنی و اسلش** | `/fa/knit-pants-joggers` |
| **تولید پیراهن‌های زنانه و منسوجات** | `/fa/womens-dresses-woven` |
| **کاتالوگ دیجیتال و استعلام قیمت** | `/fa/catalogue-rfq` |

---

## 2. Navigasyon, Buton ve Kart Bağlantı Kuralları

1. **Logo Bağlantısı:**
   * Masaüstü ve mobilde sol üstteki `BSN Textile` logosuna tıklandığında aktif dile göre ana sayfaya yönlenir (`/tr/`, `/en/` vb.).
2. **Üretim Hatları Kartları ve Menüleri:**
   * "Uzmanlık Alanlarımız" / "Her Koleksiyon İçin Ayrı Üretim Hücresi" kartlarındaki butonlar doğrudan ilgili ürün detay sayfasına yönlenir (`/tr/deniz-sortu-uretimi` vb.).
3. **RFQ / Fiyat Teklifi Al Butonları:**
   * Üst navigasyondaki "ÜRETİM TEKLİFİ AL (RFQ)" butonu sayfada teklif formu varsa `#rfq-section` anchor linkine, yoksa `/tr/dijital-katalog-teklif` sayfasına yönlendirilir.
4. **Hızlı WhatsApp İletişim Bağlantısı:**
   * WhatsApp butonları doğrudan `https://wa.me/905352336073?text=Merhaba%20BSN%20Textile,%20B2B%20fason%20üretim%20için%20bilgi%20almak%20istiyorum.` bağlantısına yönlenir.
5. **Dil Değiştirici (Language Switcher):**
   * Üst çubuktaki `TR | EN | AR | RU | FA` butonları ilgili dilin eşdeğer sayfasına geçiş yapar.
6. **Mobil Alt Tab Bar (Bottom Navigation):**
   * Mobil arayüzde alt tab bar 5 temel rotaya kilitlenmiştir:
     * Ana Sayfa: `/tr/`
     * Katalog: `/tr/dijital-katalog-teklif`
     * RFQ Al: `/tr/dijital-katalog-teklif#teklif`
     * Üretim: `/tr/kurumsal`
     * İletişim: `/tr/iletisim`
