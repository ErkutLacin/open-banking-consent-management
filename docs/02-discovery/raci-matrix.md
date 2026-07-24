# RM-001 | RACI Matrisi (RACI Matrix)

## Açık Bankacılık Rıza Yönetim Sistemi

---

| Alan | Bilgi |
|------|-------|
| **Belge ID** | RM-001 |
| **Belge Adı** | RACI Matrisi |
| **İlişkili Belgeler** | PC-001 — Project Charter, SA-001 — Paydaş Analizi |
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

Bu belge, SA-001'de tanımlanan paydaşların proje boyunca üretilecek her aktivite/teslimat için hangi sorumluluk seviyesinde yer alacağını netleştirir. Amaç, "bu karar için kime gidilir?" sorusuna proje başlamadan önce tek bir referans noktası sağlamaktır.

---

## 2. RACI Tanımları

| Kod | Anlam | Açıklama |
|-----|-------|----------|
| **R** | Responsible (Sorumlu) | İşi fiilen yapan/üreten kişi |
| **A** | Accountable (Hesap Verebilir) | Nihai onayı veren, işin sonucundan hesap veren kişi (her satırda yalnızca 1 kişi) |
| **C** | Consulted (Danışılan) | Karar öncesi görüşü alınan, çift yönlü iletişim kurulan kişi |
| **I** | Informed (Bilgilendirilen) | Karar sonrası bilgilendirilen, tek yönlü iletişim kurulan kişi |

---

## 3. Paydaş Kısaltmaları

| Kısaltma | Paydaş |
|----------|--------|
| **SPN** | Dijital Bankacılık GMY (Sponsor) |
| **PM** | Ürün Müdürü |
| **BA** | Business Analyst (Erkut Laçin) |
| **LGL** | Baş Hukuk Danışmanı |
| **ARC** | IT Mimarisi Ekibi |
| **DEV** | Yazılım Geliştirme Ekibi |
| **CX** | Müşteri Deneyimi Ekibi |
| **SEC** | Bilgi Güvenliği Ekibi |
| **BKM** | BKM (API Geçit Sağlayıcısı) |

> **Not:** BDDK bu matrise dahil edilmemiştir. BDDK, projeye doğrudan karar süreciyle dahil olan bir paydaş değil, dış denetim otoritesidir — tüm kararları mevzuat yoluyla dolaylı şekilde şekillendirir. Bu nedenle RACI'de bir "R/A/C/I" rolü atamak yanıltıcı olur; BDDK'ya ilişkin uyum gereksinimleri BRD ve Business Rules dokümanlarında doğrudan referans olarak işlenecektir.

---

## 4. RACI Matrisi

![RACI Matrisi](/assets/screenshots/raci-heatmap.png)
---

## 5. Dikkat Çeken Noktalar

### 5.1 DEV (Yazılım Geliştirme Ekibi) Rolünün Fazlara Göre Değişimi

Tabloyu satır satır takip edersen DEV sütununun şu şekilde ilerlediğini görürsün:

- **Faz 1 (satır 1-4):** Sadece **I** — henüz teknik uygulama başlamadığı için yalnızca bilgilendirilir.
- **Faz 2 (satır 5-8):** **C** — gereksinimler netleşirken teknik uygulanabilirlik görüşü alınır.
- **Faz 3 (satır 9-13):** **C/R karışık** — User Story ve To-Be süreçte danışılan taraf, ama teknik tasarım detaylarında (API, DB şeması) doğrudan katkı sağlar.
- **Faz 4 (satır 14-15):** **C** — test stratejisine görüş verir, UAT'a katılır.

Bu kademeli geçiş, SA-001'de belirttiğimiz "Faz 1-2: Düşük Etki → Faz 3+: Yüksek Etki" gözlemini RACI'de somut olarak doğrular — ayrı bir tablo açmadan.

### 5.2 "A" Sütununda Birden Fazla Kişi Olan Tek Satır (#17)

Kapanış aktivitesinde hem SPN hem PM'e "A" verdim çünkü Executive Summary hem stratejik (Sponsor) hem operasyonel (Ürün Müdürü) onay gerektiren nadir bir teslimat. **Bu, RACI'nin "her satırda tek A olmalı" kuralına bilinçli bir istisnadır** — gerçek projelerde de üst düzey kapanış raporlarında bu tür çift onay senaryosu görülür. Eğer tek A tercih edilirse, SPN'nin A, PM'in C olması daha "kural uyumlu" olurdu; bunu tartışmaya açık bırakıyorum.

---

## 6. Açık Noktalar

- **BKM'nin C rolü yalnızca API Tasarımı satırında var (#11)** — çünkü BKM, banka içi karar süreçlerine katılmaz, yalnızca teknik sertifikasyon standardı belirleyen dış otorite olarak API tasarımı aşamasında görüşü/standardı referans alınır.
- **CX (Müşteri Deneyimi) ağırlıklı olarak C** — SA-001'de belirtildiği gibi bu ekibin karar yetkisi bağlayıcı değil, öneri niteliğinde.
