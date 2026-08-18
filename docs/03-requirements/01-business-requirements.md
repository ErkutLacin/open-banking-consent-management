# BR-001 | İş Gereksinimleri Dokümanı (Business Requirements Document)

## Açık Bankacılık Rıza Yönetim Sistemi

---

| Alan | Bilgi |
|------|-------|
| **Belge ID** | BR-001 |
| **Belge Adı** | Business Requirements Document (BRD) |
| **İlişkili Belgeler** | PC-001, SA-001, RM-001, RR-001, AP-001 |
| **Hazırlayan** | Erkut Laçin — Business Analyst |
| **Hazırlanma Tarihi** | 24 Temmuz 2026 |
| **Versiyon** | 1.0 |
| **Durum** | Taslak |

---

## Revizyon Geçmişi

| Versiyon | Tarih | Hazırlayan | Açıklama |
|----------|-------|-----------|----------|
| 1.0 | 24 Temmuz 2026 | Erkut Laçin | İlk yayın |

---

## 1. Amaç

Bu belge, Faz 1'de tespit edilen sorunları (AP-001) ve mevzuat gerekliliklerini (RR-001) test edilebilir fonksiyonel gereksinimlere dönüştürür. Her gereksinim, kaynağına (hangi sorun veya hangi ÖHVPS/KVKK maddesi) izlenebilir şekilde numaralandırılmıştır.

**ID Kuralı:** Fonksiyonel gereksinimler `FR-XXX` formatındadır. `BR` kısaltması Business Rules dokümanına, `NFR` kısaltması Non-Functional Requirements dokümanına ayrılmıştır — bu ayrım RTM'de karışıklığı önler.

---

## 2. Kapsam Referansı

PC-001 Bölüm 3'te tanımlanan kapsam bu belgede aynen geçerlidir. Bu BRD, **Hesap Bilgisi Rızası (HBH)** ve **Ödeme Emri Başlatma Rızası (ÖEBH)** akışlarını **eşit detay seviyesinde** kapsar.

| Kapsam Dahilinde | Bu BRD'de Karşılığı |
|-------------------|---------------------|
| Hesap Bilgisi Rızası (HBH) | Bölüm 5.1, 5.3-5.7 |
| Ödeme Emri Başlatma Rızası (ÖEBH) | Bölüm 5.2, 5.3-5.7 |
| Güçlü Kimlik Doğrulama (GKD) | Bölüm 5.3 |
| Denetim Kaydı | Bölüm 5.6 |
| KVKK Gereksinimleri | Bölüm 5.7 |

---

## 3. İş Hedefleri ile Bağlantı

| PC-001 Hedefi | Bu BRD'nin Katkısı |
|----------------|---------------------|
| H-01: BDDK uyumluluğu | Tüm FR'ler RR-001'deki ÖHVPS kurallarına dayanır |
| H-02: Rıza sürecinin dijitalleştirilmesi | FR-001 – FR-010 (rıza oluşturma/yönetme) |
| H-03: Self-servis oranının artırılması | FR-016 – FR-018 (görüntüleme/iptal) |
| H-04: KVKK uyumluluğu | FR-024 – FR-026 |
| H-05: Denetlenebilirlik | FR-019 – FR-023 (audit log) |

---

## 4. Fonksiyonel Gereksinimler

### 4.1 Rıza Oluşturma — Hesap Bilgisi Rızası (HBH)

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-001 | Sistem, YÖS'ten gelen bir HBH rıza talebini alıp `B` (Yetki Bekleniyor) durumunda bir kayıt oluşturmalıdır. | RR-001 §2.2 | Zorunlu |
| FR-002 | Sistem, rıza talebinde hangi hesap(lar)ın ve hangi veri kapsamının (bakiye, işlem geçmişi, hesap sahibi bilgisi vb.) talep edildiğini ayrı ayrı listelemelidir. | RR-001 §2.4 | Zorunlu |
| FR-003 | Sistem, aynı ÖHK için aynı YÖS'te ve aynı HHS'de yalnızca tek bir aktif (`B`/`Y`/`K`) HBH rızasına izin vermelidir; bireysel ve kurumsal kullanıcı için bu kısıt ayrı ayrı uygulanmalıdır. | RR-001 §2.4, Madde 1 | Zorunlu |
| FR-004 | Kullanıcı, rıza kapsamındaki hesaplardan hangilerini paylaşacağını seçebilmelidir (tüm hesaplar zorunlu değildir). | AP-001 §2.2 (S-02 çözümü) | Zorunlu |

### 4.2 Rıza Oluşturma — Ödeme Emri Başlatma Rızası (ÖEBH)

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-005 | Sistem, YÖS'ten gelen bir ÖEBH rıza talebini alıp `B` durumunda bir kayıt oluşturmalıdır. | RR-001 §2.2 | Zorunlu |
| FR-006 | Sistem, ödeme emri rızasında tutar, alıcı hesap bilgisi ve ödeme amacını zorunlu alanlar olarak talep etmelidir. | RR-001 §2.1 | Zorunlu |
| FR-007 | Sistem, aynı ÖHK'nın bir YÖS için bir HHS'de birden fazla eşzamanlı ÖEBH rızasına sahip olmasına izin vermelidir (HBH'deki tekillik kısıtı burada uygulanmaz). | RR-001 §2.4, Madde 2 | Zorunlu |
| FR-008 | Sistem, ödeme emri rızası `K` (Yetki Kullanıldı) durumundayken ödeme gerçekleştiğinde durumu otomatik olarak `E` (Yetki Ödeme Emrine Dönüştü) durumuna geçirmelidir. | RR-001 §2.2 | Zorunlu |

### 4.3 Rıza Değişikliği ve Yenileme

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-009 | Sistem, mevcut bir rızanın hesap/izin/tarih kapsamının doğrudan güncellenmesine izin vermemelidir; kullanıcı önce mevcut rızayı iptal etmeli, ardından yeni bir rıza talebi başlatmalıdır. | RR-001 §2.4, Madde 4 | Zorunlu |
| FR-010 | Sistem, kullanıcıya güncelleme talep ettiğinde "önce iptal, sonra yeniden rıza" akışını açıkça anlatan bir yönlendirme mesajı göstermelidir. | AP-001 §2.2 (S-02 çözümü) | Önerilen |

### 4.4 Güçlü Kimlik Doğrulama (GKD)

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-011 | Sistem, `B` durumundaki her rıza için GKD sürecini tetiklemelidir; GKD başarısız olursa rıza ilgili iptal detay koduyla (07-14) `I` durumuna geçmelidir. | RR-001 §2.2, §2.3 | Zorunlu |
| FR-012 | Mobil uygulaması bulunan HHS senaryosu için sistem Ayrık (decoupled) GKD akışını desteklemelidir. | RR-001 §2.4, Madde 8 | Zorunlu |
| FR-013 | Sistem, `B` durumunda 5 dakikadan uzun süre GKD tamamlanmayan rızaları otomatik olarak iptal detay kodu `04` ile `I` durumuna geçirmelidir. | RR-001 §2.3, §2.4 Madde 3 | Zorunlu |
| FR-014 | Sistem, `Y` durumunda 5 dakikadan uzun süre erişim belirteci alınmayan rızaları iptal detay kodu `05` ile `I` durumuna geçirmelidir. | RR-001 §2.3, §2.4 Madde 3 | Zorunlu |

### 4.5 Rıza Görüntüleme

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-015 | Kullanıcı, mobil/internet bankacılığı üzerinden tüm aktif rızalarını (HBH ve ÖEBH) tek bir ekranda listeleyebilmelidir. | AP-001 §2.2 (S-02 çözümü) | Zorunlu |
| FR-016 | Rıza listesinde her kayıt için YÖS adı, kapsam (hangi hesap/veri), oluşturulma tarihi ve geçerlilik tarihi gösterilmelidir. | KVKK Madde 11 | Zorunlu |
| FR-017 | Kullanıcı, geçmiş (sonlandırılmış/iptal edilmiş) rızalarını da ayrı bir sekmede görüntüleyebilmelidir. | KVKK Madde 11 | Önerilen |

### 4.6 Rıza İptali

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-018 | Kullanıcı, aktif bir rızayı tek bir işlemle (self-servis) iptal edebilmelidir; iptal detay kodu `02` veya `03` (kanala göre) otomatik atanmalıdır. | AP-001 §2.2, §3 (S-02, S-03) | Zorunlu |
| FR-019 | Sistem, rıza iptal edildiğinde ilgili YÖS'e gerçek zamanlı bildirim göndermelidir (webhook/callback). | RR-001 §2.1 | Zorunlu |
| FR-020 | Kullanıcı, hesap/kart kapatma işlemiyle rızasını otomatik iptal etmek istemiyorsa, rıza kapatma işleminden bağımsız olarak varlığını sürdürmelidir. | RR-001 §2.4, Madde 5 | Zorunlu |

### 4.7 Denetim Kaydı (Audit Log)

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-021 | Sistem, her rıza durum değişikliğini (B→Y→K→E/S/I) zaman damgası, kanal ve tetikleyen aktör bilgisiyle audit log'a kaydetmelidir. | AP-001 §3 (S-01) | Zorunlu |
| FR-022 | Zaman damgaları, 5070 sayılı Elektronik İmza Kanunu'ndaki zaman damgası tanımına uygun üretilmelidir. | RR-001 §2.4, Madde 7 | Zorunlu |
| FR-023 | Audit log kayıtları değiştirilemez (immutable) olmalı ve en az yasal saklama süresi kadar tutulmalıdır. | AP-001 §3 (S-01) | Zorunlu |
| FR-024 | Yetkili kullanıcılar (uyum/denetim ekibi), belirli bir ÖHK veya YÖS için audit log'u filtreleyip sorgulayabilmelidir. | PC-001 H-05 | Zorunlu |

### 4.8 KVKK Gereksinimleri

| ID | Gereksinim | Kaynak | Öncelik |
|----|-----------|--------|---------|
| FR-025 | Sistem, rıza akışı başlamadan önce KVKK Madde 10 kapsamında bir aydınlatma metni göstermeli ve kullanıcının bu metni gördüğünü onaylamasını istemelidir. | RR-001 §3 | Zorunlu |
| FR-026 | Aydınlatma metni, tüm kanallarda (şube, internet bankacılığı, mobil) aynı içerikte ve güncel olmalıdır. | AP-001 §3 (S-04) | Zorunlu |
| FR-027 | Kullanıcı, verisinin işlenip işlenmediğini ve hangi amaçla paylaşıldığını sorgulayabilmelidir (KVKK Madde 11). | RR-001 §3 | Zorunlu |

---

## 5. Gereksinim → Sorun İzlenebilirlik Özeti

| AP-001 Sorunu | Karşılayan Gereksinimler |
|----------------|---------------------------|
| S-01: Rıza durumları sistematik takip edilmiyor | FR-001, FR-005, FR-021 |
| S-02: GKD standardına uygun kimlik doğrulama yok | FR-011 – FR-014 |
| S-03: Rıza iptali standart değil | FR-018 – FR-020 |
| S-04: Aydınlatma metni tutarsız | FR-025, FR-026 |
| S-05: Rıza API üzerinden sunulamıyor | Tüm FR'ler (API tasarımı Faz 3'te bu gereksinimlere dayanacak) |

> Bu tablo, Faz 4'te hazırlanacak **Requirements Traceability Matrix (RTM)**'in ilk taslağı niteliğindedir.

[GÖRSEL ÖNERİSİ: Gereksinim Kategorileri Pasta/Bar Grafik — 27 FR'nin kategori bazlı dağılımını (Rıza Oluşturma: 8, GKD: 4, Görüntüleme: 3, İptal: 3, Audit: 4, KVKK: 3, Değişiklik: 2) görselleştiren basit bir bar chart, LinkedIn'de "kapsamın büyüklüğünü" hızlıca anlatır. Excel/Google Sheets ile kolayca üretilebilir.]

---

## 6. Varsayımlar ve Kısıtlar

PC-001 Bölüm 7'deki varsayım ve kısıtlar bu belge için de geçerlidir. Ek olarak:

| # | Varsayım/Kısıt |
|---|-----------------|
| V-06 | Webhook/callback altyapısının YÖS tarafında da desteklendiği varsayılmaktadır (FR-019). |
| K-05 | Audit log saklama süresi, hukuk departmanının belirleyeceği yasal asgari süreye tabidir (FR-023) — kesin süre bu BRD'de belirtilmemiştir. |

---

## 7. Onay Bekleyen Açık Noktalar

- **FR-017 (geçmiş rıza görüntüleme)** "Önerilen" önceliğinde bırakıldı — Ürün Müdürü'nün MVP kapsamına alıp almayacağına karar vermesi gerekiyor.
- **FR-023'teki saklama süresi** hukuk onayı bekliyor; placeholder olarak "yasal asgari süre" ifadesi kullanıldı.

