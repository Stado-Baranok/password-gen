# 🔐 Password Generator — Entropy‑Driven & Quantum‑Ready

> Командная утилита и библиотека для генерации паролей с продвинутой энтропией, проверкой на утечки и поддержкой квантовой стойкости (пост-квантовая криптография).

![Demo](https://img.shields.io/badge/demo-CLI-blueviolet?style=flat) 
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python)
![Rust](https://img.shields.io/badge/Rust-core-000000?logo=rust)

## 🧠 Features

- **Адаптивная сложность** – подбор длины и набора символов под требования сайта
- **Энтропия > 128 бит** – использует `/dev/urandom` + системный шум
- **Проверка на утечки** – интеграция с `haveibeenpwned` (API v3)
- **Пост-квантовая схема** – опциональное добавление энтропии на основе CRYSTALS-Kyber (через FFI)
- **Вывод в разных форматах** – JSON, plain, QR‑код (ASCII art)
- **Менеджер клипборда** – копирование с автозачисткой через 30 секунд

## 📦 Установка

```bash
# Python версия
pip install stado-pwgen

# Rust версия
cargo install stado_pwgen
$ pwgen --length 20 --symbols --no-ambiguous --show-entropy
Generated: 9f$#kLm2Q@xV!7zY&bC3
Entropy: 145.3 bits
Pwned: ❌ not found
[✓] copied to clipboard (clears in 30s)
from stado_pwgen import generate, check_breach

password = generate(length=24, digits=True, punctuation=True)
print(f"New pass: {password}")
print(f"Leaked? {check_breach(password)}")  # False / count
