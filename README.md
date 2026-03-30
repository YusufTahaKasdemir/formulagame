# F1 2026: Efsane Geri Döndü

Tarayıcı üzerinde çalışan, **Three.js** tabanlı bir mini Formula 1 yarış oyunu. Proje; gerçek zamanlı 3B sahne oluşturma, dinamik pist üretimi, temel sürüş fiziği, HUD arayüzü, tur takibi ve çoklu kamera açıları gibi modern web tabanlı oyun bileşenlerini tek bir HTML dosyasında bir araya getirmektedir.

## Proje Amacı

Bu proje, kullanıcıya kurulum gerektirmeden doğrudan tarayıcı üzerinden erişilebilen hızlı, akıcı ve görsel açıdan etkileyici bir yarış deneyimi sunmayı amaçlamaktadır. Uygulama özellikle:

- Web tabanlı 3B oyun geliştirme mantığını göstermek,
- Three.js ile sahne, kamera, ışık ve geometri kullanımını örneklemek,
- Mobil ve masaüstü cihazlarda çalışabilecek bir kontrol yapısı sunmak,
- Tek dosyalı, taşınabilir ve kolay yayınlanabilir bir oyun yapısı oluşturmak

için geliştirilmiştir.

## Öne Çıkan Özellikler

- **Three.js tabanlı 3B yarış sahnesi**
- **Procedural (dinamik) pist üretimi**
- **Başlangıç ışıkları ile yarış başlangıç sekansı**
- **Gerçek zamanlı hız, vites, RPM ve tur süresi gösterimi**
- **En iyi tur zamanı takibi**
- **Klavye ve dokunmatik kontrol desteği**
- **Farklı kamera modları arasında geçiş**
- **Yeni pist oluşturma özelliği**
- **Çarpışma ve pist dışına çıkma kontrolü**
- **Mobil uyumlu tam ekran oyun yapısı**

Kod içinde `RacingGame` sınıfı, giriş yönetimi, araç modeli, pist üretimi, çarpışma kontrolü, görsel güncellemeler ve kamera mantığını tek merkezde toplamaktadır. Arayüzde yükleme ekranı, HUD, başlangıç ışıkları, kaza efekti ve mobil kontroller tanımlanmıştır. :contentReference[oaicite:1]{index=1}

## Kullanılan Teknolojiler

- **HTML5**
- **CSS3**
- **JavaScript (Vanilla JS)**
- **Three.js r128**

Projede Three.js kütüphanesi CDN üzerinden dahil edilmiştir. Bu sayede ek kurulum olmadan doğrudan tarayıcı üzerinde çalıştırılabilir. :contentReference[oaicite:2]{index=2}

## Oyun Mekanikleri

### 1. Araç Kontrolü
Oyuncu aracı hızlandırabilir, fren yapabilir ve sağa-sola yön verebilir. Kontroller hem klavye hem de dokunmatik arayüz ile desteklenmektedir.

**Klavye kontrolleri:**
- `W` / `ArrowUp` → Gaz
- `S` / `ArrowDown` → Fren / geri
- `A` / `ArrowLeft` → Sola dön
- `D` / `ArrowRight` → Sağa dön

**Ekran kontrolleri:**
- Sol ve sağ yön tuşları
- Gaz pedalı
- Fren pedalı

Kodda hem `keydown/keyup` olayları hem de mobil için `touchstart/touchend` bağlamaları tanımlanmıştır. :contentReference[oaicite:3]{index=3}

### 2. Yarış Başlangıcı
Oyun açıldığında önce bir yükleme ekranı gösterilir. Ardından F1 tarzı kırmızı başlangıç ışıkları sıralı şekilde yanar ve yarış başlar. Bu yapı kullanıcı deneyimini güçlendiren sinematik bir başlangıç etkisi sağlar. :contentReference[oaicite:4]{index=4}

### 3. Pist Sistemi
Pist yapısı sabit bir harita yerine matematiksel olarak dinamik biçimde oluşturulmaktadır. Noktalar üzerinden kapalı bir eğri oluşturularak asfalt yüzey, kerbler, çakıl alanları, lastik duvarlar ve tribünler sahneye eklenmektedir. Böylece her yeni pist üretiminde farklı bir deneyim sağlanır. :contentReference[oaicite:5]{index=5}

### 4. Çarpışma ve Yol Dışı Kontrolü
Araç pist sınırlarını aştığında sistem en yakın pist noktasını hesaplar ve aracı tekrar sınır içine çeker. Hız yeterince yüksekse “KAZA!” efekti gösterilir ve araç hızı sıfırlanır. Bu yapı temel ama etkili bir çarpışma hissi sunar. :contentReference[oaicite:6]{index=6}

### 5. Tur ve Telemetri
Arayüzde aşağıdaki bilgiler canlı olarak güncellenir:

- Hız (KM/H)
- Vites
- RPM barı
- Mevcut tur
- Anlık tur süresi
- En iyi tur süresi

Tur takibi için araç pist üzerindeki ilerleme yüzdesine göre kontrol edilir. Belirli eşik geçildiğinde yeni tur algılanır ve en iyi derece güncellenir. :contentReference[oaicite:7]{index=7}

## Kamera Modları

Projede birden fazla kamera açısı desteklenmektedir. Kullanıcı arayüzündeki **KAMERA** butonu ile farklı bakış açıları arasında geçiş yapılabilir.

Desteklenen kamera modları:
- **Chase Close** – aracın arkasından yakın takip kamerası
- **Cockpit** – sürücü perspektifi
- **Nose** – aracın ön burun kısmından görünüm
- **TV** – yukarıdan genel izleme açısı

Kodda ayrıca `halo` görünümüne dair bir kontrol yapısı da bulunmaktadır; bu, gelecekte genişletilebilir kamera modları için uygun bir altyapı sunar. :contentReference[oaicite:8]{index=8}

## Arayüz Bileşenleri

Arayüz modern yarış oyunlarından ilham alınarak tasarlanmıştır. Başlıca bileşenler:

- **Loader ekranı**
- **Başlangıç ışıkları paneli**
- **Üst HUD telemetri alanı**
- **Tur ve süre paneli**
- **Kamera ve yeni pist butonları**
- **Mobil oyun tuşları**
- **Kaza efekti bildirimi**

Bu yapı, oyunun yalnızca teknik olarak değil görsel olarak da daha etkileyici görünmesini sağlamaktadır. :contentReference[oaicite:9]{index=9}

## Dosya Yapısı

Bu proje şu anda tek bir HTML dosyasında çalışacak şekilde tasarlanmıştır:

```bash
project/
└── index.html
