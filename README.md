<div align="center">

# Opus Trade Bot

**C++20 ile yazılmış profesyonel algoritmik trading botu**

[![C++](https://img.shields.io/badge/C++-20-00599C?style=flat-square&logo=cplusplus&logoColor=white)](https://isocpp.org)
[![CMake](https://img.shields.io/badge/CMake-3.20+-064F8C?style=flat-square&logo=cmake&logoColor=white)](https://cmake.org)
[![vcpkg](https://img.shields.io/badge/vcpkg-dependencies-5C2D91?style=flat-square)](https://vcpkg.io)
[![Binance](https://img.shields.io/badge/Exchange-Binance%20Futures-F0B90B?style=flat-square&logo=binance&logoColor=black)](https://binance.com)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square)](LICENSE)

</div>

---

## Genel Bakış

Binance Futures için Wall Street standartlarında tasarlanmış C++20 algoritmik trading botu. SOLID prensiplerine dayalı modüler mimari ile geliştirilmiştir.

---

## Mimari

```
src/
├── core/           # Motor: konfigürasyon, event loop, risk yönetimi
├── exchange/       # Binance REST + WebSocket API adaptörü
├── market/         # Market data akışı ve işleme
├── network/        # Asenkron HTTP/WebSocket katmanı
├── order/          # Emir oluşturma ve yaşam döngüsü yönetimi
└── strategy/       # Trading strateji arayüzü ve implementasyonları
```

---

## Özellikler

- **C++20:** `std::concepts`, `std::ranges`, coroutine desteği
- **Asenkron ağ:** WebSocket üzerinden gerçek zamanlı market data
- **Modüler strateji:** Yeni strateji eklemek için `IStrategy` arayüzü
- **Risk yönetimi:** Pozisyon limiti ve stop-loss motoru
- **Yüksek performans:** Sıfır-kopya mesajlaşma, düşük gecikme tasarımı
- **vcpkg:** Tüm bağımlılıklar vcpkg manifest ile yönetilir

---

## Build

### Gereksinimler

- CMake 3.20+
- C++20 destekli derleyici: GCC 12+, Clang 14+ veya MSVC 2022
- [vcpkg](https://github.com/microsoft/vcpkg)

### Derleme

```bash
# Repo'yu klonla (vcpkg submodule dahil)
git clone --recurse-submodules https://github.com/furkntrg41/opus-trade-bot.git
cd opus-trade-bot

# Konfigüre et
cmake -B build \
  -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake \
  -DCMAKE_BUILD_TYPE=Release

# Derle
cmake --build build --parallel
```

### Çalıştırma

```bash
./build/opus_trade_bot --config config/config.json
```

---

## Proje Yapısı

```
.
├── src/                  # Kaynak kodlar
├── include/              # Header dosyaları
├── tests/                # Unit testler
├── config/               # Konfigürasyon dosyaları
├── vcpkg/                # vcpkg submodule
├── vcpkg.json            # Bağımlılık manifest
└── CMakeLists.txt        # Build tanımı
```

---

## Bağımlılıklar

vcpkg ile otomatik yönetilir:

| Kütüphane | Kullanım |
|-----------|---------|
| boost | Asio asenkron I/O |
| nlohmann-json | JSON parse |
| openssl | TLS/SSL |
| spdlog | Logging |

---

## Lisans

[MIT](LICENSE) © 2026 furkntrg41
