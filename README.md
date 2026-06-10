# Opus Trade Bot

C++20 ile yazılmış profesyonel algoritmik trading botu — Binance Futures için tasarlanmıştır.

## Özellikler

- C++20 modern standartları, CMake build sistemi
- vcpkg ile bağımlılık yönetimi
- SOLID prensiplerine dayalı modüler mimari
- Binance Futures REST + WebSocket entegrasyonu

## Mimari

```
src/
├── core/       # Temel motor ve konfigürasyon
├── exchange/   # Binance API adaptörü
├── market/     # Market data işleme
├── network/    # HTTP/WebSocket katmanı
├── order/      # Emir yönetimi
└── strategy/   # Trading stratejileri
```

## Build

```bash
cmake -B build -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
cmake --build build
```

## Gereksinimler

- CMake 3.20+
- C++20 uyumlu derleyici (GCC 12+ / Clang 14+ / MSVC 2022)
- vcpkg
