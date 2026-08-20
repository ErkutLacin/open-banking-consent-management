# Açık Bankacılık Rıza Yönetim Sistemi (OBRYS-2025)

BDDK'nın ÖHVPS v2.0 standardına uygun, uçtan uca bir **Business Analysis portföy projesi**. Gerçek bir yazılım geliştirme çalışması değildir — kurgusal bir kurum olan **Portföy Bankası A.Ş.** üzerinden, bir Junior Business Analyst pozisyonu için hazırlanan bir vitrin çalışmasıdır.

> Bu projede kullanılan kurum, kişi ve iç veriler tamamen kurgusaldır. Gerçek bir kuruma ait bilgi içermez.

---

## 📍 Proje Durumu

**Şu an: Faz 2 — Süreç Analizi tamamlandı.** Faz 3 — Gereksinim Analizi'ne geçiliyor.

| Faz | Durum |
|-----|-------|
| Faz 1 — Keşif & Kapsam | ✅ Tamamlandı |
| Faz 2 — Süreç Analizi | ✅ Tamamlandı |
| Faz 3 — Gereksinim Analizi | 🔄 Devam Ediyor |
| Faz 4 — Ürün & Kullanıcı Gereksinimleri | ⏳ Bekliyor |
| Faz 5 — Teknik Analiz | ⏳ Bekliyor |
| Faz 6 — Test & Doğrulama | ⏳ Bekliyor |
| Faz 7 — Paketleme & Sunum | ⏳ Bekliyor |

---

## 📂 Repository Navigasyonu

### Faz 1 — Keşif & Kapsam
| Belge | Açıklama |
|-------|----------|
| [Project Charter](docs/01-charter/01-project-charter.md) | Projenin kapsamı, hedefleri, riskleri |
| [Stakeholder Analysis](docs/02-discovery/01-stakeholder-analysis.md) | Paydaş profilleri, etki/ilgi matrisi |
| [RACI Matrix](docs/02-discovery/02-raci-matrix.md) | Sorumluluk atama matrisi |
| [Regulatory Research](docs/02-discovery/03-regulatory-research.md) | BDDK ÖHVPS v2.0 ve KVKK araştırması |
| [Glossary](docs/02-discovery/04-glossary.md) | Terimler sözlüğü |

### Faz 2 — Süreç Analizi
| Belge | Açıklama |
|-------|----------|
| [As-Is Process Analysis](docs/04-design/01-as-is-process-analysis.md) | Mevcut (kurgusal) rıza sürecinin analizi |
| [Consent Lifecycle](docs/04-design/02-consent-lifecycle.md) | Rıza durum makinesi (HBH ve ÖEBH) |
| [To-Be Process](docs/04-design/03-to-be-process.md) | Hedef dijital rıza süreci |
| [Data Flow Diagram](docs/04-design/04-data-flow-diagram.md) | Veri akış diyagramı |

### Faz 3 — Gereksinim Analizi (devam ediyor)
| Belge | Açıklama |
|-------|----------|
| [Business Requirements Document](docs/03-requirements/01-business-requirements.md) | İş gereksinimleri (Faz 2 çıktılarına göre gözden geçirilecek) |

---

## 🛠️ Kullanılan Teknolojiler ve Araçlar

- **Diyagramlama:** Camunda Modeler (BPMN), Draw.io
- **API Tasarımı:** OpenAPI 3.0 / Swagger, Postman
- **Mock API:** Node.js + Express (Faz 5'te eklenecek)
- **Veritabanı:** PostgreSQL

---

## 📄 Lisans ve Uyarı

Bu proje eğitim/portföy amaçlıdır. İçerik, gerçek bir bankacılık kurumunu temsil etmez.