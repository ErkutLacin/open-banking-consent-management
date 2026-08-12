# PC-001 | Proje Tüzüğü (Project Charter)

## Açık Bankacılık Rıza Yönetim Sistemi

---

| Alan | Bilgi |
|------|-------|
| **Belge ID** | PC-001 |
| **Belge Adı** | Proje Tüzüğü (Project Charter) |
| **Proje Adı** | Açık Bankacılık Rıza Yönetim Sistemi |
| **Proje Kodu** | OBRYS-2025 |
| **Hazırlayan** | Erkut Laçin — Business Analyst |
| **Hazırlanma Tarihi** | 21 Temmuz 2026 |
| **Versiyon** | 1.0 |
| **Durum** | Onay Bekliyor |
| **Sponsor** | Dijital Bankacılık Genel Müdür Yardımcısı |
| **Gizlilik Derecesi** | Kurum İçi |

---

## Revizyon Geçmişi

| Versiyon | Tarih | Hazırlayan | Açıklama |
|----------|-------|-----------|----------|
| 0.1 | 14 Temmuz 2026 | Erkut Laçin | İlk taslak |
| 1.0 | 21 Temmuz 2026 | Erkut Laçin | Paydaş geri bildirimleri ile güncellendi, onaya sunuldu |

---

## 1. Yönetici Özeti

Bankacılık Düzenleme ve Denetleme Kurumu (BDDK), 2019 yılında yürürlüğe giren Açık Bankacılık mevzuatı kapsamında tüm yetkili kuruluşların, müşteri rızalarını kayıt altına almasını, yönetmesini ve denetlenebilir hâle getirmesini zorunlu kılmaktadır. Avrupa'daki PSD2 direktifinden ilham alan bu düzenleme, Türkiye'de ÖHVPS (Ödeme Hizmeti Veri Paylaşım Servisleri) standartları çerçevesinde uygulanmaktadır.

Bu proje; **Portföy Bankası A.Ş.**'nin müşterilerine ait açık bankacılık rızalarının uçtan uca dijital olarak yönetilmesini sağlayacak **Açık Bankacılık Rıza Yönetim Sistemi (OBRYS)**'ni kapsayan iş analizi çalışmasının tümünü belgelemek amacıyla başlatılmaktadır.

> **Not:** Portföy Bankası A.Ş., bu portföy çalışmasında kullanılan varsayımsal bir kurumdur. Gerçek bir kuruma ait içerik kullanılmamıştır.

---

## 2. İş Gerekçesi (Business Case)

### 2.1 Problem Tanımı

Portföy Bankası A.Ş., hâlihazırda müşteri rızalarını aşağıdaki yöntemlerle almaktadır:

- Şube kanalında imzalı kâğıt formlar
- İnternet bankacılığı check-box onayları (denetim izi yok)
- Çağrı merkezi ses kaydı

Bu mevcut yapının üç temel sorunu bulunmaktadır:

| # | Sorun | İş Etkisi |
|---|-------|-----------|
| 1 | Rızalar merkezi bir sistemde tutulmuyor | BDDK denetimleri için rıza kanıtı sunulamaması riski |
| 2 | Müşteri, verdiği rızayı görecek veya geri alacak bir arayüze sahip değil | KVKK Madde 11 kapsamında müşteri hakları ihlali riski |
| 3 | Üçüncü taraf servis sağlayıcılar (YÖS) rıza doğrulamasını standart API üzerinden yapamıyor | ÖHVPS uyumluluğu sağlanamıyor, gelir kaybı |

### 2.2 Fırsat

Türkiye Açık Bankacılık ekosistemi hızla büyümektedir. Standart bir rıza yönetim altyapısı kurulması:

- Yeni YÖS ortaklıklarını mümkün kılacak
- Müşteri güvenini artıracak
- BDDK denetimlerinde kuruma pozitif bir profil kazandıracak
- Gelecekteki ürün geliştirme süreçlerini hızlandıracaktır

### 2.3 Beklenen Faydalar

| Fayda Türü | Beklenen Fayda |
|------------|----------------|
| **Uyum (Compliance)** | BDDK ÖHVPS gereksinimlerinin %100 karşılanması |
| **Risk Azaltma** | KVKK ihlal cezası riskinin ortadan kaldırılması |
| **Müşteri Deneyimi** | Rıza yönetimi için self-servis dijital kanal |
| **Operasyonel Verimlilik** | Manuel rıza işlem yükünün azaltılması |
| **İş Geliştirme** | YÖS entegrasyonlarının standart API ile hızlanması |

---

## 3. Proje Kapsamı

### 3.1 Kapsam Dahili (In Scope)

Aşağıdaki iş süreçleri ve sistem bileşenleri bu projenin kapsamındadır:

- **Hesap Bilgisi Rızası (HBH):** Müşterinin YÖS'e hesap bilgilerine erişim izni vermesi
- **Ödeme Emri Başlatma Rızası (OEBH):** Müşterinin YÖS'e ödeme başlatma yetkisi vermesi
- **Rıza Görüntüleme:** Müşterinin aktif rızalarını listeleyebilmesi
- **Rıza İptal:** Müşterinin rızasını her an geri alabilmesi
- **Güçlü Kimlik Doğrulama (GKD):** Rıza süreçlerinde çok faktörlü kimlik doğrulama
- **Denetim Kaydı (Audit Log):** Tüm rıza işlemlerinin izlenebilirliği
- **ÖHVPS API Uyumluluğu:** BKM API Geçidi standartlarına tam uyum
- **KVKK Gereksinimleri:** Aydınlatma metni sunumu, açık rıza kaydı, veri sahibi hakları

### 3.2 Kapsam Harici (Out of Scope)

Aşağıdakiler bu projenin kapsamı **dışındadır:**

| Kapsam Dışı | Gerekçe |
|-------------|---------|
| Kredi başvurusu süreçleri | Ayrı proje kapsamı |
| Müşteri kimlik doğrulama altyapısının yeniden yazılması | Mevcut IAM sistemi kullanılacak |
| YÖS portal geliştirmesi | YÖS tarafının sorumluluğu |
| Mobil uygulama UI geliştirmesi | Yalnızca backend API analizi bu kapsamdadır |
| FAST / anlık ödeme sistemi altyapısı | Mevcut TCMB altyapısı üzerine çalışılacak |

---

## 4. Proje Hedefleri ve Başarı Kriterleri

| # | Hedef | Başarı Kriteri | Ölçüm Yöntemi |
|---|-------|---------------|---------------|
| H-01 | BDDK uyumluluğu sağlanması | ÖHVPS v2.0 standartlarına %100 uyum | BDDK denetim raporu |
| H-02 | Rıza sürecinin dijitalleştirilmesi | Tüm rıza işlemlerinin API üzerinden yapılabilmesi | UAT test geçiş oranı ≥ %95 |
| H-03 | Müşteri self-servis oranının artırılması | Rıza iptali işlemlerinin %80'inin self-servis yapılması | Sistem metrikleri |
| H-04 | KVKK uyumluluğu | Rıza kayıtlarının yasal saklama süreleri ile uyumlu tutulması | Hukuk departmanı onayı |
| H-05 | Denetlenebilirlik | Tüm rıza işlemlerine ait audit log'un eksiksiz tutulması | Log analizi |

---

## 5. Paydaş Analizi

### 5.1 Paydaş Listesi

| Paydaş | Rol | Kategori | İlgi Alanı | Etkisi |
|--------|-----|----------|-----------|-------|
| Dijital Bankacılık GMY | Proje Sponsoru | İç | Stratejik uyum, maliyet | Yüksek |
| Ürün Müdürü – Açık Bankacılık | Ürün Sahibi | İç | Kapsam, önceliklendirme | Yüksek |
| Baş Hukuk Danışmanı | Hukuki Onaylayan | İç | KVKK, BDDK mevzuatı | Yüksek |
| IT Mimarisi Ekibi | Teknik Değerlendirici | İç | API mimarisi, entegrasyon | Yüksek |
| Yazılım Geliştirme Ekibi | Geliştirici | İç | Teknik gereksinimler | Orta |
| Müşteri Deneyimi Ekibi | Kullanıcı Temsilcisi | İç | Kullanıcı arayüzü, UX | Orta |
| Bilgi Güvenliği Ekibi | Güvenlik Onaylayan | İç | GKD, veri güvenliği | Yüksek |
| BDDK | Düzenleyici Kurum | Dış | Mevzuat uyumu | Çok Yüksek |
| BKM | API Geçit Sağlayıcısı | Dış | ÖHVPS standartları | Yüksek |
| YÖS'ler (3. Taraf Sağlayıcılar) | API Kullanıcısı | Dış | API erişimi, rıza doğrulama | Orta |
| Müşteriler (ÖHK) | Son Kullanıcı | Dış | Güven, kontrol, şeffaflık | Yüksek |

---

## 6. Proje Yaklaşımı

Bu proje, **Business Analysis odaklı** bir çalışma olarak yürütülecektir. Yazılım geliştirme bu çalışmanın kapsamına girmemektedir; hedef gerçekçi ve endüstri standardı BA çıktıları üretmektir.

### 6.1 Metodoloji

- **Gereksinim Toplama:** Paydaş görüşmeleri, doküman analizi (ÖHVPS v2.0, KVKK)
- **Modelleme:** BPMN 2.0 süreç diyagramları (Camunda Modeler)
- **Dokümantasyon:** BRD, User Story, Use Case, Test Case
- **API Analizi:** OpenAPI 3.0 spesifikasyonu, Postman koleksiyonu
- **Proje Yönetimi:** Agile/Scrum prensipleri, Jira

### 6.2 Proje Fazları

| Faz | Adı | Ana Çıktılar |
|-----|-----|-------------|
| **Faz 1** | Keşif & Kapsam | Project Charter, Stakeholder Register, As-Is Süreç |
| **Faz 2** | Gereksinim Analizi | BRD, Business Rules, Veri Sözlüğü |
| **Faz 3** | Çözüm Tasarımı | User Stories, Use Cases, To-Be Süreç, API Spec |
| **Faz 4** | Doğrulama & Test | Test Senaryoları, Test Case'ler, Postman Koleksiyonu |
| **Faz 5** | Kapanış | Retrospektif, Portföy Sunumu |

---

## 7. Varsayımlar ve Kısıtlar

### 7.1 Varsayımlar

| # | Varsayım |
|---|---------|
| V-01 | Portföy Bankası, TCMB ve BKM ile gerekli sözleşmeleri imzalamış; YÖS/HHS sertifikasyon sürecini tamamlamıştır. |
| V-02 | Mevcut IAM (Kimlik ve Erişim Yönetimi) altyapısı GKD gereksinimlerini karşılamaktadır. |
| V-03 | ÖHVPS v2.0 standartları proje süresince değişmeyecektir. |
| V-04 | Müşteriler, açık bankacılık hizmetine yalnızca dijital kanallar (mobil uygulama, internet bankacılığı) üzerinden erişebilmektedir. |
| V-05 | Hukuk departmanı KVKK aydınlatma metni taslakları için zamanında geri bildirim sağlayacaktır. |

### 7.2 Kısıtlar

| # | Kısıt |
|---|-------|
| K-01 | ÖHVPS standartları BKM tarafından belirlenmiş olup değiştirilemez. |
| K-02 | Veri saklama politikaları KVKK ve BDDK mevzuatına tabidir. |
| K-03 | Güçlü kimlik doğrulama (GKD) mekanizması değiştirilemez; mevcut altyapı kullanılacaktır. |
| K-04 | Tüm API iletişimleri TLS 1.2 ve üzeri ile şifrelenmelidir. |

---

## 8. Riskler

| Risk ID | Risk | Olasılık | Etki | Önem | Azaltma Stratejisi |
|---------|------|---------|------|------|--------------------|
| R-01 | BDDK mevzuat değişikliği | Orta | Yüksek | Yüksek | BDDK duyuru takibi, modüler tasarım |
| R-02 | Paydaşların gereksinim onay süreçlerinde gecikmesi | Yüksek | Orta | Yüksek | Onay takvimi önceden netleştirilmeli |
| R-03 | BKM API Geçidi teknik değişiklikleri | Düşük | Yüksek | Orta | ÖHVPS değişiklik logları takip edilmeli |
| R-04 | GKD entegrasyonunda teknik zorluklar | Orta | Orta | Orta | PoC aşamasında erken test |
| R-05 | Müşteri farkındalığının düşük olması | Yüksek | Orta | Orta | UX araştırması ve kullanıcı testleri |

---

## 9. Üst Düzey Zaman Çizelgesi

| Faz | Süre | Hedef Tarih |
|-----|------|-------------|
| Faz 1 – Keşif & Kapsam | 2 Hafta | Temmuz 2026 |
| Faz 2 – Gereksinim Analizi | 3 Hafta | Ağustos 2026 |
| Faz 3 – Çözüm Tasarımı | 3 Hafta | Eylül 2026 |
| Faz 4 – Doğrulama & Test | 2 Hafta | Ekim 2026 |
| Faz 5 – Kapanış | 1 Hafta | Ekim 2026 |

---

## 10. Bütçe (Üst Düzey)

> Bu portföy çalışması için gerçek bir bütçe tahsisi yapılmamaktadır.
> Gerçek proje senaryosunda aşağıdaki kategoriler değerlendirilirdi:

| Kategori | Varsayımsal Tutar |
|----------|-----------------|
| İnsan Kaynağı (BA, Geliştirici, QA) | ₺850.000 |
| Yazılım Lisansları ve Araçlar | ₺120.000 |
| BKM Sertifikasyon Maliyetleri | ₺95.000 |
| Eğitim | ₺35.000 |
| **Toplam Tahmini Bütçe** | **₺1.100.000** |

---

## 11. İletişim Planı

| Hedef Kitle | İletişim Türü | Sıklık | Kanal |
|------------|--------------|--------|-------|
| Sponsor | İlerleme Raporu | Aylık | Sunum |
| Tüm Paydaşlar | Faz Kapanış Raporu | Her faz sonunda | E-posta + Confluence |
| Geliştirme Ekibi | Sprint Takibi | Haftalık | Jira |
| Hukuk & Uyum | Gereksinim İncelemesi | İhtiyaç halinde | Toplantı |

---

## 12. Proje Onayı

Bu tüzüğün onaylanması, projenin başlatıldığını ve Business Analyst'e gereksinimleri toplama, paydaşlarla görüşme yapma ve proje çıktılarını üretme yetkisinin verildiğini teyit etmektedir.

| Rol | Ad Soyad | Tarih | İmza |
|-----|---------|-------|------|
| Proje Sponsoru – Dijital Bankacılık GMY | *(Ad)* | ___/___/2026 | ________ |
| Ürün Müdürü – Açık Bankacılık | *(Ad)* | ___/___/2026 | ________ |
| Baş Hukuk Danışmanı | *(Ad)* | ___/___/2026 | ________ |
| Proje Yöneticisi | *(Ad)* | ___/___/2026 | ________ |
| Business Analyst | Erkut Laçin | 21 Temmuz 2026 | ________ |

---

*Bu doküman OBRYS-2025 projesine ait resmi proje tüzüğüdür.*
*Tüm revizyonlar versiyon geçmişine işlenmelidir.*
*Bir sonraki belge: Stakeholder Analysis (SA-001).*