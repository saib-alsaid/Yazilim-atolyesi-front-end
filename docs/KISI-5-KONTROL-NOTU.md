﻿﻿# KİŞİ 5 - KONTROL NOTU

## 1. Eşleştirme Tablosu (Arayüz alanı | KİŞİak anahtar | Dinamik mi statik mi)

| Arayüz alanı | KİŞİak anahtar | Dinamik mi / Statik mi | Açıklama |
|---|---|---|---|
| Hero başlığı (HERO.title) | contentKİŞİ home-hero (HOME/HERO) | Dinamik | Backend page_contents (HOME, HERO, home-hero).title |
| Hero alt başlık (HERO.subtitle) | contentKİŞİ home-hero (HOME/HERO) | Dinamik | Backend page_contents (HOME, HERO, home-hero).subtitle |
| Hero gövdesi (HERO.body) | contentKİŞİ home-hero (HOME/HERO) | Dinamik | Backend page_contents (HOME, HERO, home-hero).body |
| KİŞİp adı | club.name (lib/content.ts) | Statik | Sabit metin (fallback) |
| Üniversite | club.university (lib/content.ts) | Statik | Sabit metin (fallback) |
| Hakkımızda (ABOUT) | contentKİŞİ about-main (ABOUT/TEXT) | Dinamik | Backend page_contents (ABOUT, TEXT, about-main) |
| İletişim açıklaması | contentKİŞİ contact-main (CONTACT/CONTACT_INFO) | Dinamik | Backend page_contents (CONTACT, CONTACT_INFO, contact-main) |
| E-posta (footer) | site_settings.contact.email | Dinamik | Backend site_settings (public) |
| Takım bölümü (takımlar) | lib/content.ts teams | Statik | Plan kapsamında statik bırakıldı |
| Çalışma akışı (steps) | lib/content.ts steps | Statik | Plan kapsamında statik bırakıldı |
| KİŞİllar (rules) | lib/content.ts rules | Statik | Plan kapsamında statik bırakıldı |
| Güncellemeler (updates) | lib/content.ts updates | Statik | Plan kapsamında statik bırakıldı |
| Dikeyler (pillars) | lib/content.ts pillars | Statik | Plan kapsamında statik bırakıldı |

> Not: Var olmayan anahtar uydurulmadı. Eksik içerik durumunda fallback (statik) içerik kullanıldı.

## 2. Uygulanan Değişiklikler (KİŞİca)
- components/contact-form.tsx: alanlar 
ame/email/subject/message ile eşleştirildi; çift gönderim engellendi; başarı mesajı "Mesaj alındı"; 400'de FieldErrors kullanıldı; 429 ve ağ hatası için uygun mesajlar; form verisi hata sonrası korunuyor.
- eatures/site-content/*: tipler, fixture'lar, adaptörler, eşleştirme tablosu eklendi.
- pp/page.tsx: Promise.allSettled ile paralel okuma, güvenli render (düz metin), HomeAnnouncements entegre edildi.
- components/hero.tsx, components/public-blocks.tsx: gelen metinler düz metin olarak render ediliyor; satır sonlarını desteklemek için CSS'te white-space: pre-line önerisi (mevcut CSS korundu, değişiklik minimal).

## 3. Test Sonuçları
- 
pm run typecheck: exit 0
- 
pm run build: exit 0
