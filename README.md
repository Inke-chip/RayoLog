<div align="center">

# RayoLog ⚡🐇

**Ultra-fast, lightweight event-streaming broker written in Go.**
*Faster than a rabbit on an energy drink.*

<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3Z3VmbHRiMDlrdGVxMHNjdDRzbXNneXdtYnFleGxveDVhdXF6c2ZqYSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/Xb6J4XCrn1G08vnyvh/giphy.gif" width="200"/><img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3Z3VmbHRiMDlrdGVxMHNjdDRzbXNneXdtYnFleGxveDVhdXF6c2ZqYSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/Xb6J4XCrn1G08vnyvh/giphy.gif" width="200"/><img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3Z3VmbHRiMDlrdGVxMHNjdDRzbXNneXdtYnFleGxveDVhdXF6c2ZqYSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/Xb6J4XCrn1G08vnyvh/giphy.gif" width="200"/>

<br/><br/>

[![Go Version](https://img.shields.io/badge/Go-1.21%2B-0080FF?style=for-the-badge&logo=go&logoColor=white)](https://go.dev)
[![License: MIT](https://img.shields.io/badge/license-MIT-0080FF?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/status-active-0080FF?style=for-the-badge)](#)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-0080FF?style=for-the-badge)](#-contributing--вклад--contribuciones)

<br/>

### 🌍 Choose your language / Выберите язык / Elige tu idioma

<a href="#-english"><img src="https://img.shields.io/badge/🇬🇧-English-0080FF?style=for-the-badge"/></a>
<a href="#-русский"><img src="https://img.shields.io/badge/🇷🇺-Русский-0080FF?style=for-the-badge"/></a>
<a href="#-español"><img src="https://img.shields.io/badge/🇪🇸-Español-0080FF?style=for-the-badge"/></a>

</div>

---

<a id="-english"></a>
## 🇬🇧 English

<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmttanByMmpzd2M3dnR3dnFseWF2cGxsNXEzazlicmFiZ3BpZTBwdCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/YqPBdDdjEOlUBURAJS/giphy.gif" alt="Adorable Bunny" width="500"/>
</div>

### 📖 Overview

**RayoLog** (*Rayo* — Spanish for *Lightning*) is a high-performance event-streaming log engine built from scratch in Go. It skips heavy JSON serialization and complex queue management in favor of an **append-only log** architecture backed by an **in-memory byte-offset index**, targeting **O(1)** read and write complexity.

### 🏗 Architecture & Engineering Highlights

| Feature | Why it matters |
|---|---|
| 🐇 **Append-only disk engine** | Sequential binary writes — minimal disk-head movement, minimal fsync overhead |
| 🐇 **O(1) in-memory index** | Byte-offset lookup table for instant reads, no full-file scans |
| 🐇 **Zero-JSON binary protocol** | Custom length-prefixed TCP framing — near-zero allocations per message |
| 🐇 **Thread-safe by design** | Fine-grained `sync.RWMutex` + atomics for safe high-concurrency access |

### 📁 Project Layout

```
.
├── cmd/
│   └── server/          # Application entrypoint
├── pkg/
│   ├── partition/       # Low-level disk log & byte-index engine
│   └── server/          # High-performance TCP binary server
├── .gitignore
├── go.mod
└── README.md
```

### 🚀 Quick Start

```bash
git clone https://github.com/Inke-chip/RayoLog.git
cd RayoLog
go run cmd/server/main.go
```

### 📊 Benchmarks


| Operation | Throughput | Latency (p99) |
|---|---|---|
| Write | `TODO` msg/s | `TODO` |
| Read | `TODO` msg/s | `TODO` |

### 🤝 Contributing

Issues and PRs are welcome. If you make RayoLog faster, a rabbit somewhere will run even faster. 🐇💨

### 📄 License

Distributed under the MIT License. See `LICENSE` for details.

<div align="right"><a href="#rayolog-">↑ back to top</a></div>

---

<a id="-русский"></a>
## 🇷🇺 Русский

<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExdGk3Z29uMGJpM3Z1c2tscmNjenBqOTloczNvZW9iMXBqeW9xbnp1YSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/KHh7jLrG6gIXBTnxsp/giphy.gif" alt="Кролики" width="500"/>
</div>

### 📖 Обзор

**RayoLog** (*Rayo* — с испанского «Молния») — высокопроизводительный движок потоковой обработки событий, написанный с нуля на Go. Проект отказывается от тяжёлой JSON-сериализации и громоздких структур очередей в пользу архитектуры **append-only лога** с индексом байтовых смещений в оперативной памяти, обеспечивая сложность **O(1)** на операциях чтения и записи.

### 🏗 Архитектура и инженерные особенности

| Фича | Почему это важно |
|---|---|
| 🐇 **Append-only дисковый движок** | Последовательная бинарная запись — минимум движений головки диска и накладных расходов fsync |
| 🐇 **O(1) индекс в памяти** | Таблица байтовых офсетов для мгновенного чтения без сканирования файла |
| 🐇 **Бинарный протокол без JSON** | Кастомный length-prefixed TCP-фрейминг — почти нулевые аллокации на сообщение |
| 🐇 **Потокобезопасность по умолчанию** | Тонкая гранулярность `sync.RWMutex` + атомики для безопасного параллелизма |

### 📁 Структура проекта

```
.
├── cmd/
│   └── server/          # Точка входа в приложение
├── pkg/
│   ├── partition/       # Низкоуровневый движок лога и индекса
│   └── server/          # Высокопроизводительный TCP-сервер
├── .gitignore
├── go.mod
└── README.md
```

### 🚀 Быстрый запуск

```bash
git clone https://github.com/Inke-chip/RayoLog.git
cd RayoLog
go run cmd/server/main.go
```

### 📊 Бенчмарки

| Операция | Пропускная способность | Задержка (p99) |
|---|---|---|
| Запись | `TODO` msg/s | `TODO` |
| Чтение | `TODO` msg/s | `TODO` |

### 🤝 Вклад в проект

Issues и Pull Request'ы приветствуются. Если ты ускоришь RayoLog — где-то кролик побежит ещё быстрее. 🐇💨

### 📄 Лицензия

Проект распространяется под лицензией MIT. Подробности в файле `LICENSE`.

<div align="right"><a href="#rayolog-">↑ наверх</a></div>

---

<a id="-español"></a>
## 🇪🇸 Español

<div align="center">
<img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExNG80MW12cGkwYjQzZTBzdjB6cDc3dXZneHRwcTF4NHJwNnAwdDF4ciZlcD12MV9naWZzX3NlYXJjaCZjdD1n/XmyF99pGjTQKk/giphy.gif" alt="Conejo sentado" width="500"/>
</div>

### 📖 Descripción general

**RayoLog** (*Rayo* — porque va como uno) es un motor de streaming de eventos de alto rendimiento, construido desde cero en Go. Evita la serialización pesada en JSON y la gestión compleja de colas a favor de una arquitectura de **log append-only** respaldada por un **índice de offsets en memoria**, apuntando a una complejidad **O(1)** en lectura y escritura.

### 🏗 Arquitectura y aspectos técnicos destacados

| Característica | Por qué importa |
|---|---|
| 🐇 **Motor de disco append-only** | Escrituras binarias secuenciales — mínimo movimiento del cabezal y overhead de fsync |
| 🐇 **Índice en memoria O(1)** | Tabla de offsets para lecturas instantáneas sin escanear el archivo |
| 🐇 **Protocolo binario sin JSON** | Framing TCP personalizado con prefijo de longitud — asignaciones casi nulas por mensaje |
| 🐇 **Seguro para concurrencia** | `sync.RWMutex` de grano fino + atómicos para acceso concurrente seguro |

### 📁 Estructura del proyecto

```
.
├── cmd/
│   └── server/          # Punto de entrada de la aplicación
├── pkg/
│   ├── partition/       # Motor de log e índice de bajo nivel
│   └── server/          # Servidor TCP binario de alto rendimiento
├── .gitignore
├── go.mod
└── README.md
```

### 🚀 Inicio rápido

```bash
git clone https://github.com/Inke-chip/RayoLog.git
cd RayoLog
go run cmd/server/main.go
```

### 📊 Benchmarks


| Operación | Throughput | Latencia (p99) |
|---|---|---|
| Escritura | `TODO` msg/s | `TODO` |
| Lectura | `TODO` msg/s | `TODO` |

### 🤝 Contribuciones

Los issues y pull requests son bienvenidos. Si haces que RayoLog vaya más rápido, en algún lugar un conejo correrá aún más rápido. 🐇💨

### 📄 Licencia

Distribuido bajo la licencia MIT. Ver `LICENSE` para más detalles.

<div align="right"><a href="#rayolog-">↑ arriba</a></div>

---

<div align="center">

🐇 Made with love, coffee and a lot of bunnies 🐇

</div>
