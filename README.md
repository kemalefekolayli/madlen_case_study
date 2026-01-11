# 🧙‍♂️ Madlen Chat - AI Assistant

Madlen Chat, kullanıcıların farklı Yapay Zeka modelleriyle (OpenRouter aracılığıyla) etkileşim kurmasını sağlayan, modern ve yerel olarak çalıştırılabilir bir web tabanlı sohbet uygulamasıdır.

Bu proje, **Geliştirici Deneyimi (DevEx)**, **Sağlamlık (Robustness)** ve **Kullanıcı Deneyimi (UX)** odaklı olarak, Docker üzerinde tek bir komutla çalışacak şekilde tasarlanmıştır.

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Docker](https://img.shields.io/badge/Docker-Ready-blue)
![Tech Stack](https://img.shields.io/badge/Stack-Spring_Boot_%7C_React_%7C_MongoDB-green)

## ✨ Öne Çıkan Özellikler & Bonuslar

Proje isterlerini tam karşılamanın ötesinde, kullanıcı deneyimini artıran ek özellikler geliştirilmiştir:

* **🎨 Gelişmiş UI/UX:**
    * **Dark/Light Mod:** Kullanıcı tercihine göre tema desteği.
    * **Responsive Tasarım:** Mobil ve masaüstü uyumlu modern arayüz.
    * **Anlık Geri Bildirimler:** Yükleniyor durumları, hata mesajları ve kullanıcı dostu uyarılar.
* **👁️ Vision (Görsel) Desteği:**
    * Uygulama, metin tabanlı modellerin yanı sıra **Görsel Analiz (Vision)** yeteneği olan modelleri de destekler (Örn: Gemini Vision, Llama Vision).
    * *Not: Arayüzde sadece desteklenen modeller seçildiğinde resim yükleme butonu aktif olur.*
* **🛡️ Sağlamlık (Robustness):**
    * Backend hataları (Session limitleri, API hataları) kullanıcıya teknik kodlarla değil, anlaşılır Türkçe mesajlarla iletilir.
    * Docker Healthcheck'leri ile servislerin sağlığı sürekli kontrol edilir.
* **📊 Gözlemlenebilirlik (Observability):**
    * **OpenTelemetry & Jaeger Entegrasyonu:** Tüm sistemin trace'leri (izleri) Jaeger üzerinden takip edilebilir.

## 🛠️ Teknoloji Yığını

* **Backend:** Java 21, Spring Boot 3.4, MongoDB, OpenTelemetry
* **Frontend:** React, TypeScript, Vite, Tailwind CSS
* **Altyapı:** Docker & Docker Compose

🚀 Kurulum ve Çalıştırma

Projeyi yerel makinenizde çalıştırmak için sadece **Docker**'ın yüklü olması yeterlidir.

1. Repoyu Klonlayın

git clone [https://github.com/KULLANICI_ADIN/REPO_ADIN.git](https://github.com/KULLANICI_ADIN/REPO_ADIN.git)
cd madlen-chat-app
2. API Anahtarını Ayarlayın
Ana dizinde .env isminde bir dosya oluşturun ve OpenRouter API anahtarınızı içine yapıştırın:

Kod snippet'i

OPENROUTER_API_KEY=sk-or-v1-sizin-anahtariniz-buraya
3. Başlatın
Tek bir komutla tüm sistemi (Frontend, Backend, Veritabanı, Jaeger) ayağa kaldırın:

Bash

docker-compose up --build
İlk açılışta bağımlılıkların indirilmesi internet hızınıza bağlı olarak birkaç dakika sürebilir.

🖥️ Uygulamaya Erişim
Sistem ayağa kalktıktan sonra tarayıcınızdan erişebilirsiniz:

Sohbet Uygulaması: http://localhost:5173

Jaeger (Trace İzleme): http://localhost:16686

Backend API Health: http://localhost:8080/api/health

📂 Proje Yapısı
madlen-chat-app/
├── docker-compose.yml   # Tüm servis orkestrasyonu
├── .env                 # Konfigürasyon (Git'e atılmaz)
├── madlen_demo/         # Backend Kaynak Kodları (Spring Boot)
│   ├── src/
│   └── Dockerfile       # Multi-stage build optimizasyonu
└── madlen_ui/           # Frontend Kaynak Kodları (React)
    ├── src/
    └── Dockerfile       # Node.js alpine imajı
📝 Notlar
API Anahtarı: Güvenlik gereği .env dosyası repoya dahil edilmemiştir. Kendi anahtarınızı oluşturmanız gerekmektedir.

Model Seçimi: Listelenen modellerden bazıları (Vision destekli olanlar) görsel yüklemeye izin verirken, diğerleri sadece metin tabanlıdır. Arayüz bunu otomatik algılar.

Geliştirici: Kemal Efe Kolaylı


