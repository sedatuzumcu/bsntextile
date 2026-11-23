# BSN Textile (bsntextile.com) — SEO, Site Haritası (sitemap.xml), robots.txt ve Çok Dilli (hreflang) Arama Motoru Rehberi

Bu döküman, BSN Textile'in 5 dilli (`TR`, `EN`, `AR`, `RU`, `FA`) küresel B2B hazır giyim ihracat platformunun arama motorlarında (Google, Yandex, Bing vb.) en üst sıralarda yer alması için hazırlanmış teknik SEO ve indeksleme spesifikasyonudur.

---

## 1. robots.txt Yapılandırması
Sunucunuzun kök dizinine (`https://www.bsntextile.com/robots.txt`) eklenecek içerik:

```txt
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /api/
Disallow: /temp/

# Yandex botu için özel direktifler
User-agent: Yandex
Allow: /ru/
Allow: /

# XML Site Haritası Bağlantısı
Sitemap: https://www.bsntextile.com/sitemap.xml
```

---

## 2. Uluslararası Çok Dilli hreflang Mimarisi
Google ve arama motorlarının Türkçe, İngilizce, Arapça, Rusça ve Farsça sayfaları doğru ülkelere göstermesi ve "yinelenen içerik" (duplicate content) cezası vermemesi için her sayfanın `<head>` etiketine eklenecek hreflang etiketleri:

```html
<!-- Ana Sayfa İçin hreflang Etiketleri -->
<link rel="alternate" hreflang="x-default" href="https://www.bsntextile.com/en/" />
<link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/" />
<link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/" />
<link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/" />
<link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/" />
<link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/" />
```

---

## 3. Dinamik XML Site Haritası (sitemap.xml)
Sunucu kök dizininde (`https://www.bsntextile.com/sitemap.xml`) bulunacak XML haritası. Tüm diller ve öncelikler tanımlanmıştır:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:xhtml="http://www.w3.org/1999/xhtml">

  <!-- ==================== ANA SAYFALAR ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/</loc>
    <xhtml:link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/"/>
    <xhtml:link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/"/>
    <xhtml:link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/"/>
    <xhtml:link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/"/>
    <xhtml:link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/"/>
    <xhtml:link rel="alternate" hreflang="x-default" href="https://www.bsntextile.com/en/"/>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/en/</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/ar/</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/ru/</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/fa/</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>

  <!-- ==================== ÜRÜN KATEGORİLERİ: AĞIR GRAMAJ SOKAK GİYİMİ ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/agir-gramaj-sweatshirt</loc>
    <xhtml:link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/agir-gramaj-sweatshirt"/>
    <xhtml:link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/heavyweight-streetwear"/>
    <xhtml:link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/streetwear-knitwear"/>
    <xhtml:link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/streetwear-apparel"/>
    <xhtml:link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/streetwear-apparel"/>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/en/heavyweight-streetwear</loc>
    <priority>0.9</priority>
  </url>

  <!-- ==================== ÜRÜN KATEGORİLERİ: ÖZEL DENİZ ŞORTU ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/deniz-sortu-uretimi</loc>
    <xhtml:link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/deniz-sortu-uretimi"/>
    <xhtml:link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/custom-swim-shorts"/>
    <xhtml:link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/swim-shorts"/>
    <xhtml:link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/swim-shorts"/>
    <xhtml:link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/swim-shorts"/>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/en/custom-swim-shorts</loc>
    <priority>0.9</priority>
  </url>

  <!-- ==================== ÜRÜN KATEGORİLERİ: ÖRME PANTOLON & JOGGER ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/orme-pantolon-jogger</loc>
    <xhtml:link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/orme-pantolon-jogger"/>
    <xhtml:link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/knit-pants-joggers"/>
    <xhtml:link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/knit-pants-joggers"/>
    <xhtml:link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/knit-pants-joggers"/>
    <xhtml:link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/knit-pants-joggers"/>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.9</priority>
  </url>

  <!-- ==================== ÜRÜN KATEGORİLERİ: KADIN ELBİSE & DOKUMA ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/kadin-elbise-dokuma</loc>
    <xhtml:link rel="alternate" hreflang="tr" href="https://www.bsntextile.com/tr/kadin-elbise-dokuma"/>
    <xhtml:link rel="alternate" hreflang="en" href="https://www.bsntextile.com/en/womens-dresses-woven"/>
    <xhtml:link rel="alternate" hreflang="ru" href="https://www.bsntextile.com/ru/womens-dresses-woven"/>
    <xhtml:link rel="alternate" hreflang="ar" href="https://www.bsntextile.com/ar/womens-dresses-woven"/>
    <xhtml:link rel="alternate" hreflang="fa" href="https://www.bsntextile.com/fa/womens-dresses-woven"/>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.9</priority>
  </url>

  <!-- ==================== İLETİŞİM, FABRİKA & TEKLİF (RFQ) ==================== -->
  <url>
    <loc>https://www.bsntextile.com/tr/iletisim</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/en/contact</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://www.bsntextile.com/tr/dijital-katalog-teklif</loc>
    <lastmod>2025-02-01</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.85</priority>
  </url>
</urlset>
```

---

## 4. Yapılandırılmış Veri Şeması (Schema.org / JSON-LD)
Arama motorlarının firmanızı resmi bir **Üretici / Tekstil Fabrikası (Organization & Manufacturer)** olarak tanıması için HTML sayfalarına yerleştirilecek JSON-LD kodu:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "BSN Textile",
  "legalName": "BSN Textile San. ve Tic. Ltd. Şti.",
  "url": "https://www.bsntextile.com",
  "logo": "https://www.bsntextile.com/assets/images/bsn-logo.png",
  "description": "Custom apparel manufacturing, high-density knitwear, custom swimwear, and woven dress production in Istanbul, Turkey.",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Gürsel Mah. Kağıthane",
    "addressLocality": "İstanbul",
    "addressCountry": "TR"
  },
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+90-535-233-6073",
    "contactType": "sales",
    "contactOption": "TollFree",
    "areaServed": ["TR", "EU", "US", "RU", "MENA"],
    "availableLanguage": ["Turkish", "English", "Russian", "Arabic", "Persian"]
  }
}
```
