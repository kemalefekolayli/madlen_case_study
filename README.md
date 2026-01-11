# 🧙‍♂️ Madlen Chat – AI Assistant

Madlen Chat, kullanıcıların **OpenRouter** aracılığıyla farklı Yapay Zeka (LLM & Vision) modelleriyle etkileşim kurmasını sağlayan, **modern**, **gözlemlenebilir** ve **yerel olarak çalıştırılabilir** bir web tabanlı sohbet uygulamasıdır.

Bu proje; **Geliştirici Deneyimi (DevEx)**, **Sağlamlık (Robustness)** ve **Kullanıcı Deneyimi (UX)** odağında tasarlanmış olup, **Docker üzerinde tek bir komutla** tüm sistemin ayağa kalkmasını hedefler.

---

## ✨ Öne Çıkan Özellikler

### 🎨 Gelişmiş UI / UX

* **Dark / Light Mode** – Kullanıcı tercihine göre tema desteği
* **Responsive Tasarım** – Mobil ve masaüstü uyumlu modern arayüz
* **Anlık Geri Bildirimler** – Loading durumları, hata mesajları ve kullanıcı dostu uyarılar

### 👁️ Vision (Görsel) Desteği *(Bonus)*

* Vision yeteneği olan modellerle **resim yükleyerek soru sorma**
* (Örn: Gemini Vision, Llama Vision)
* Sadece **Vision destekleyen modeller** seçildiğinde resim yükleme butonu aktif olur

### 🛡️ Sağlamlık (Robustness)

* Backend kaynaklı hatalar (API limitleri, ağ problemleri vb.) kullanıcıya **teknik detaylara boğulmadan**, **anlaşılır Türkçe mesajlarla** gösterilir
* **Docker healthcheck**’leri ile servislerin durumu sürekli izlenir

### 📊 Gözlemlenebilirlik (Observability)

* **OpenTelemetry entegrasyonu**
* Backend API çağrıları ve kritik akışlar **Jaeger** üzerinden trace & span olarak izlenebilir

---

## 🛠️ Teknoloji Yığını

### Backend

* Java 21
* Spring Boot 3.4
* MongoDB
* OpenTelemetry

### Frontend

* React
* TypeScript
* Vite
* Tailwind CSS

### Altyapı

* Docker
* Docker Compose

---

## 🚀 Kurulum ve Çalıştırma

Bu projeyi çalıştırmak için **yalnızca Docker** kurulu olması yeterlidir.

### 1️⃣ Repoyu Klonlayın

```bash
git clone https://github.com/KULLANICI_ADIN/REPO_ADIN.git
cd madlen-chat-app
```

### 2️⃣ OpenRouter API Anahtarını Ayarlayın

Proje kök dizininde `.env` adında bir dosya oluşturun:

```env
OPENROUTER_API_KEY=sk-or-v1-sizin-api-anahtariniz
```

> ⚠️ `.env` dosyası **güvenlik sebebiyle** GitHub reposuna dahil edilmez.

### 3️⃣ Uygulamayı Başlatın

Tek bir komutla tüm sistemi (Frontend, Backend, MongoDB, Jaeger) ayağa kaldırın:

```bash
docker-compose up --build
```

> ⏳ İlk çalıştırmada imajların indirilmesi birkaç dakika sürebilir.

---

## 🖥️ Erişim Adresleri

Sistem başarıyla ayağa kalktıktan sonra:

* 💬 **Sohbet Uygulaması**: [http://localhost:5173](http://localhost:5173)
* 📊 **Jaeger (Trace İzleme)**: [http://localhost:16686](http://localhost:16686)
* ❤️ **Backend Health Check**: [http://localhost:8080/api/health](http://localhost:8080/api/health)

---

## 📂 Proje Yapısı

```text
madlen-chat-app/
├── docker-compose.yml      # Tüm servislerin orkestrasyonu
├── .env                    # Ortam değişkenleri (repo dışı)
├── madlen_demo/            # Backend (Spring Boot)
│   ├── src/
│   └── Dockerfile          # Multi-stage build
├── madlen_ui/              # Frontend (React + Vite)
│   ├── src/
│   └── Dockerfile          # Node.js Alpine
└── README.md
```

---

## 🔍 Teknik Kararlar & Gerekçeler

* **Monorepo yapı**: Frontend ve Backend’in birlikte versiyonlanması ve tek komutla çalıştırılabilmesi
* **Docker Compose**: Reviewer ve geliştiriciler için sıfır kurulum maliyeti
* **OpenTelemetry**: Production-ready gözlemlenebilirlik yaklaşımı
* **Vite + React**: Hızlı geliştirme ve modern frontend deneyimi

---

## 🧪 Model Seçimi Hakkında

* Listelenen modeller **OpenRouter’ın ücretsiz modelleri** arasından seçilmiştir
* Vision destekli modeller otomatik olarak algılanır
* Metin tabanlı modellerde resim yükleme pasif hale gelir

---

## 👨‍💻 Geliştirici

**Kemal Efe Kolaylı**

> Bu proje, Madlen Case Study kapsamında geliştirilmiştir ve production-ready mimari, temiz kod ve kullanıcı deneyimi ön planda tutularak tasarlanmıştır.
