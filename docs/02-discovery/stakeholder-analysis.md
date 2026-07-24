# SA-001 | Paydaş Analizi (Stakeholder Analysis)

## Açık Bankacılık Rıza Yönetim Sistemi

---

| Alan | Bilgi |
|------|-------|
| **Belge ID** | SA-001 |
| **Belge Adı** | Paydaş Analizi |
| **İlişkili Belge** | PC-001 — Project Charter (Bölüm 5) |
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

Bu belge, PC-001 Project Charter'da tanımlanan paydaş listesini genişleterek her paydaşın beklentisini, endişesini, iletişim tercihini ve etki/ilgi seviyesine göre konumunu tanımlar. Amaç, ilerleyen gereksinim toplama görüşmelerinde doğru kişiyle doğru soruyu doğru zamanda sormaktır.

---

## 2. Etki / İlgi Matrisi

Paydaşlar, projeye olan **etkileri** (kararları ne kadar değiştirebilecekleri) ve **ilgileri** (proje sonucundan ne kadar etkilenecekleri) baz alınarak dört gruba ayrılmıştır.

| Konum | Strateji | Paydaşlar |
|-------|---------|-----------|
| **Yüksek Etki / Yüksek İlgi** | Yakın yönetim, sık iletişim | Dijital Bankacılık GMY, Ürün Müdürü, Baş Hukuk Danışmanı, Bilgi Güvenliği Ekibi, BDDK |
| **Yüksek Etki / Düşük İlgi** | Memnun tut, özet bilgilendir | IT Mimarisi Ekibi, BKM |
| **Düşük Etki / Yüksek İlgi** | Bilgilendirilmiş tut | Müşteri Deneyimi Ekibi, YÖS'ler, Müşteriler (ÖHK) |
| **Düşük Etki / Düşük İlgi** | Asgari takip | Yazılım Geliştirme Ekibi (bu fazda) |

> **Not:** Yazılım Geliştirme Ekibi'nin düşük etki/ilgi seviyesi yalnızca **Faz 1-2 (Keşif ve Gereksinim)** için geçerlidir. Faz 3'te (Çözüm Tasarımı) bu ekip Yüksek Etki/Yüksek İlgi grubuna geçecektir.

---

## 3. Detaylı Paydaş Profilleri

### 3.1 Dijital Bankacılık GMY (Proje Sponsoru)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Yüksek / Yüksek |
| **Beklenti** | BDDK denetimlerinde kurumun uyumlu görünmesi, stratejik konumlanma |
| **Endişe** | Proje bütçesinin ve süresinin aşılması |
| **Karar Yetkisi** | Kapsam onayı, bütçe onayı, proje iptal/devam kararı |
| **İletişim Tercihi** | Aylık üst düzey sunum, kritik konularda ad-hoc toplantı |
| **BA'nın Dikkat Etmesi Gereken** | Teknik detaya girmeden iş etkisi ve uyum durumu odaklı raporlama yapılmalı |

### 3.2 Ürün Müdürü — Açık Bankacılık (Ürün Sahibi)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Yüksek / Yüksek |
| **Beklenti** | Rekabetçi bir açık bankacılık ürünü, hızlı YÖS onboarding süreci |
| **Endişe** | Kapsamın aşırı genişlemesi (scope creep), teslim tarihlerinin kayması |
| **Karar Yetkisi** | Backlog önceliklendirme, user story kabul/red |
| **İletişim Tercihi** | Haftalık sprint toplantıları, Jira üzerinden sürekli takip |
| **BA'nın Dikkat Etmesi Gereken** | Her gereksinim değişikliğinde önceliklendirme etkisini netleştirmeli |

### 3.3 Baş Hukuk Danışmanı (Hukuki Onaylayan)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Yüksek / Yüksek |
| **Beklenti** | KVKK Madde 11 ve BDDK yönetmeliklerine tam uyum, hukuki risklerin sıfırlanması |
| **Endişe** | Rıza metinlerinin yasal olarak yetersiz kalması, veri saklama sürelerinin ihlali |
| **Karar Yetkisi** | Aydınlatma metni onayı, veri saklama politikası onayı |
| **İletişim Tercihi** | Resmi doküman incelemesi, yazılı geri bildirim |
| **BA'nın Dikkat Etmesi Gereken** | Mevzuata dayalı her ifade için güncel kaynak referansı sunulmalı (bkz. Bölüm 5) |

### 3.4 IT Mimarisi Ekibi (Teknik Değerlendirici)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Yüksek / Düşük |
| **Beklenti** | Mevcut sistem mimarisiyle uyumlu, ölçeklenebilir bir çözüm |
| **Endişe** | Yeni sistemin mevcut altyapıya (IAM, çekirdek bankacılık) ek yük getirmesi |
| **Karar Yetkisi** | Teknik mimari onayı, entegrasyon yöntemi seçimi |
| **İletişim Tercihi** | Teknik doküman inceleme, gerektiğinde mimari toplantı |
| **BA'nın Dikkat Etmesi Gereken** | API tasarım fazında erken görüş alınmalı, sürprizden kaçınılmalı |

### 3.5 Yazılım Geliştirme Ekibi (Geliştirici)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Faz 1-2: Düşük/Düşük → Faz 3+: Yüksek/Yüksek |
| **Beklenti** | Net, test edilebilir ve çelişkisiz gereksinimler |
| **Endişe** | Belirsiz kabul kriterleri nedeniyle yeniden işlem (rework) |
| **Karar Yetkisi** | Teknik uygulanabilirlik geri bildirimi |
| **İletişim Tercihi** | Jira, sprint planlama, backlog refinement toplantıları |
| **BA'nın Dikkat Etmesi Gereken** | User Story'ler INVEST kriterlerine uygun yazılmalı |

### 3.6 Müşteri Deneyimi Ekibi (Kullanıcı Temsilcisi)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Düşük / Yüksek |
| **Beklenti** | Rıza sürecinin müşteri için anlaşılır ve az adımlı olması |
| **Endişe** | Hukuki/teknik zorunlulukların kullanıcı deneyimini karmaşıklaştırması |
| **Karar Yetkisi** | UX önerisi sunma (bağlayıcı değil) |
| **İletişim Tercihi** | Workshop, kullanıcı senaryosu değerlendirme oturumları |
| **BA'nın Dikkat Etmesi Gereken** | Zorunlu hukuki metinler ile UX basitliği arasında denge kurulmalı |

### 3.7 Bilgi Güvenliği Ekibi (Güvenlik Onaylayan)

| Alan | Detay |
|------|-------|
| **Kategori** | İç Paydaş |
| **Etki/İlgi** | Yüksek / Yüksek |
| **Beklenti** | GKD (Güçlü Kimlik Doğrulama) ve veri şifreleme standartlarının tam uygulanması |
| **Endişe** | Rıza verilerinin yetkisiz erişime açık olması |
| **Karar Yetkisi** | Güvenlik mimarisi onayı, penetrasyon testi gereksinimleri |
| **İletişim Tercihi** | Güvenlik değerlendirme toplantıları, resmi doküman incelemesi |
| **BA'nın Dikkat Etmesi Gereken** | TLS 1.2+, sertifika yönetimi gibi teknik gereksinimler BRD'de netleştirilmeli |

### 3.8 BDDK (Düzenleyici Kurum)

| Alan | Detay |
|------|-------|
| **Kategori** | Dış Paydaş |
| **Etki/İlgi** | Çok Yüksek / Düşük (doğrudan proje sürecine dahil değil, ama tüm kararları şekillendirir) |
| **Beklenti** | ÖHVPS standartlarına tam uyum |
| **Endişe** | — (doğrudan endişesi yok, denetim odaklı) |
| **Karar Yetkisi** | Denetim, yaptırım, ruhsat iptali riski |
| **İletişim Tercihi** | Doğrudan iletişim yok; mevzuat ve tebliğ üzerinden dolaylı etkileşim |
| **BA'nın Dikkat Etmesi Gereken** | Tüm gereksinimler ÖHVPS v2.0 dokümanına satır satır izlenebilir olmalı |

### 3.9 BKM (API Geçit Sağlayıcısı)

| Alan | Detay |
|------|-------|
| **Kategori** | Dış Paydaş |
| **Etki/İlgi** | Yüksek / Düşük |
| **Beklenti** | Bankanın API Geçidi standartlarına teknik uyumu |
| **Endişe** | Standart dışı entegrasyonların ekosistemde sorun yaratması |
| **Karar Yetkisi** | Sertifikasyon onayı/reddi |
| **İletişim Tercihi** | Teknik dokümantasyon, sertifikasyon süreci üzerinden |
| **BA'nın Dikkat Etmesi Gereken** | API tasarımı ÖHVPS'teki hata kodları ve alan isimlendirmeleriyle birebir uyumlu olmalı |

### 3.10 YÖS'ler — Yetkilendirilmiş Ödeme Servis Sağlayıcıları (API Kullanıcısı)

| Alan | Detay |
|------|-------|
| **Kategori** | Dış Paydaş |
| **Etki/İlgi** | Düşük / Yüksek |
| **Beklenti** | Stabil, dokümante edilmiş ve öngörülebilir API davranışı |
| **Endişe** | Rıza doğrulama sürecinde gecikme veya belirsizlik |
| **Karar Yetkisi** | Yok (banka API'sini kullanan taraf) |
| **İletişim Tercihi** | Teknik dokümantasyon (Swagger/OpenAPI) üzerinden |
| **BA'nın Dikkat Etmesi Gereken** | Hata senaryoları ve response formatları net dokümante edilmeli |

### 3.11 Müşteriler — ÖHK, Ödeme Hizmeti Kullanıcısı (Son Kullanıcı)

| Alan | Detay |
|------|-------|
| **Kategori** | Dış Paydaş |
| **Etki/İlgi** | Düşük / Yüksek |
| **Beklenti** | Rızasını kolayca anlaması, kontrol edebilmesi, istediğinde iptal edebilmesi |
| **Endişe** | Verilerinin izinsiz kullanılması, karmaşık/anlaşılmaz onay ekranları |
| **Karar Yetkisi** | Rıza verme/verilmeme (nihai karar müşteride) |
| **İletişim Tercihi** | Doğrudan iletişim yok; UX araştırması ve kullanıcı testleri üzerinden temsil edilir |
| **BA'nın Dikkat Etmesi Gereken** | KVKK Madde 10 kapsamında aydınlatma metni açık ve anlaşılır olmalı |

---

## 4. Paydaş Etkileşim Haritası (Özet)

| Paydaş Grubu | Birincil Etkileşim Kanalı | Sıklık |
|--------------|---------------------------|--------|
| Üst Yönetim (Sponsor, Ürün Müdürü) | Sunum + Jira | Aylık / Haftalık |
| Hukuk & Uyum | Doküman inceleme | Faz bazlı |
| Teknik Ekipler (IT, Güvenlik, Geliştirme) | Toplantı + Confluence/Jira | Sprint bazlı |
| Dış Paydaşlar (BDDK, BKM) | Mevzuat/standart takibi | Sürekli (dolaylı) |
| YÖS & Müşteriler | Dokümantasyon / UX araştırması | Faz 3-4 |

---

## 5. Açık Noktalar ve Notlar

> **Not:** Bu belgedeki "Baş Hukuk Danışmanı" ve "BDDK" paydaşlarına atfedilen beklenti ve endişeler, ÖHVPS v2.0 dokümanındaki genel ilkelerden ve KVKK'nın kamuya açık genel çerçevesinden türetilmiştir. Gerçek bir proje senaryosunda bu tür hukuki yorumlar mutlaka güncel resmi kaynak veya kurum hukuk departmanı onayı gerektirir. Bu belge bir portföy çalışması olup gerçek bir hukuki görüş içermez.
