# GL-001 | Terimler Sözlüğü (Glossary)

## Açık Bankacılık Rıza Yönetim Sistemi

---

| Alan | Bilgi |
|------|-------|
| **Belge ID** | GL-001 |
| **Belge Adı** | Terimler Sözlüğü |
| **İlişkili Belgeler** | PC-001, RR-001 |
| **Hazırlayan** | Erkut Laçin — Business Analyst |
| **Hazırlanma Tarihi** | 24 Temmuz 2026 |
| **Versiyon** | 1.0 |
| **Durum** | Yaşayan Belge (Faz boyunca güncellenir) |

---

## Revizyon Geçmişi

| Versiyon | Tarih | Hazırlayan | Açıklama |
|----------|-------|-----------|----------|
| 1.0 | - | Erkut Laçin | İlk yayın — Faz 1 terimleri konsolide edildi |

---

## 1. Amaç

Bu belge, projede kullanılan tüm kısaltmaları, rol tanımlarını ve durum kodlarını tek bir referans noktasında toplar. **Yaşayan bir belgedir** — her yeni fazda ortaya çıkan yeni terimler buraya eklenecektir (örn. Faz 3'te API/teknik terimler, Faz 4'te test terminolojisi).

---

## 2. Roller ve Aktörler

| Terim | Açık Adı | Tanım |
|-------|----------|-------|
| **ÖHK** | Ödeme Hizmeti Kullanıcısı | Bankacılık hizmetini kullanan son kullanıcı / müşteri |
| **HHS** | Hesap Hizmeti Sağlayıcısı | Müşterinin hesabını tutan kurum (bu projede: Portföy Bankası) |
| **YÖS** | Yetkilendirilmiş Ödeme Servis Sağlayıcısı | Rıza ile hesap/ödeme verisine erişen üçüncü taraf kurum (genel terim) |
| **HBHS** | Hesap Bilgisi Hizmeti Sağlayıcısı | Yalnızca hesap bilgisine erişen YÖS alt tipi |
| **ÖBHS** | Ödeme Başlatma Hizmeti Sağlayıcısı | Ödeme emri başlatan YÖS alt tipi |

## 3. Rıza Türleri

| Terim | Açık Adı | Tanım |
|-------|----------|-------|
| **HBH** | Hesap Bilgisi Rızası | Müşterinin YÖS'e hesap bilgilerine erişim izni vermesi |
| **ÖEBH** | Ödeme Emri Başlatma Rızası | Müşterinin YÖS'e ödeme başlatma yetkisi vermesi |
| **GKD** | Güçlü Kimlik Doğrulama | Rıza süreçlerinde uygulanan çok faktörlü kimlik doğrulama |

## 4. Rıza Durum Kodları

| Kod | Durum | Kısa Tanım |
|-----|-------|-----------|
| **B** | Yetki Bekleniyor | İlk rıza talebi oluşturuldu, GKD bekleniyor |
| **Y** | Yetkilendirildi | GKD başarıyla tamamlandı |
| **K** | Yetki Kullanıldı | Erişim belirteci (access token) alındı |
| **E** | Yetki Ödeme Emrine Dönüştü | Yalnızca ÖBHS akışında, ödeme emri gerçekleşti |
| **S** | Yetki Sonlandırıldı | Geçerlilik süresi doldu |
| **I** | Yetki İptal | Kullanıcı/sistem/zaman aşımı kaynaklı iptal |

> Detaylı geçiş kuralları ve iptal detay kodları (01-14, 99) için bkz. RR-001, Bölüm 2.2-2.3.

## 5. Mevzuat ve Kurumlar

| Terim | Açık Adı | Tanım |
|-------|----------|-------|
| **BDDK** | Bankacılık Düzenleme ve Denetleme Kurumu | Türkiye'de bankacılık sektörünü düzenleyen otorite |
| **ÖHVPS** | Ödeme Hizmeti Veri Paylaşım Servisleri | BDDK'nın açık bankacılık API standardı |
| **BKM** | Bankalararası Kart Merkezi | ÖHVPS API Geçidi'ni işleten kurum |
| **KVKK** | Kişisel Verilerin Korunması Kanunu | 6698 sayılı, kişisel veri işleme süreçlerini düzenleyen kanun |

## 6. Teknik ve Süreç Terimleri

| Terim | Tanım |
|-------|-------|
| **Access Token (Erişim Belirteci)** | Rıza yetkilendirildikten sonra API isteklerinde kullanılan geçici erişim anahtarı |
| **Refresh Token (Yenileme Belirteci)** | Erişim belirtecinin süresi dolduğunda yeni belirteç almak için kullanılan anahtar (ÖBHS akışında) |
| **Decoupled Authentication (Ayrık GKD)** | Kullanıcının kimlik doğrulamayı ayrı bir cihaz/uygulama üzerinden tamamladığı GKD yöntemi |
| **Audit Log (Denetim Kaydı)** | Tüm rıza durum değişikliklerinin değiştirilemez şekilde kaydedildiği log yapısı |
| **BRD** | Business Requirements Document — iş gereksinimleri dokümanı |
| **RACI** | Responsible, Accountable, Consulted, Informed — sorumluluk atama matrisi |
| **RTM** | Requirements Traceability Matrix — gereksinim izlenebilirlik matrisi |

---

## 7. Güncelleme Notu

Bu sözlük her fazın sonunda gözden geçirilecek ve o fazda ortaya çıkan yeni terimlerle güncellenecektir. Faz 2'de eklenmesi planlanan terimler: BPMN notasyon terimleri (gateway, swimlane, event), DFD terimleri (data store, process, external entity).

---

*Bu doküman OBRYS-2025 projesine ait terimler sözlüğüdür*
*Bu belgenin tamamlanmasıyla Faz 1 — Keşif & Kapsam eksiksiz tamamlanmıştır.*
*Bir sonraki belge: As-Is Process Analysis (AP-001) — Faz 2, Süreç Analizi'nin ilk belgesi.*