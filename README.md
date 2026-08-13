# RayoLog ⚡

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExdW5pY29yb3Bzc2VkMXR1N2t3YnYxbzRzaWRvcm9iYms3cnBneCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Lq0h93752f6J9tijrh/giphy.gif" alt="Fast Bunny" width="300" />
</p>

<p align="center">
  <b>Ultra-fast, lightweight event-streaming broker written in Go.</b><br>
  <i>Faster than a rabbit on an energy drink. 🐇⚡</i>
</p>

<p align="center">
  <a href="#english">English</a> •
  <a href="#russian">Русский</a>
</p>

---

<a name="english"></a>
## 🇬🇧 English

### Overview

**RayoLog** (*Rayo* — Spanish for *Lightning*) is a high-performance event-streaming log engine built from scratch in Go. It eschews heavy JSON serialization and complex queue management in favor of an **Append-Only Log** architecture with an **In-Memory Byte Index**, guaranteeing $O(1)$ read and write time complexity.

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1aGNnYXZvOWs0bnM1dXlydWZ3dnpvbDJvNXhhcTZ6NWgxeW52dyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Julianu5L62Iis323M/giphy.gif" alt="Hyperactive Bunny" width="280" />
</p>

### Architecture & Engineering Highlights

- **Append-Only Disk Engine:** Sequential bin writes minimizing disk head movement and filesystem overhead.
- **$O(1)$ In-Memory Index:** Sparse/dense byte offset mappings for instantaneous message lookups without disk scans.
- **Zero-JSON Binary Protocol:** Custom length-prefixed framing over TCP designed for minimal memory allocations (`allocs/op`).
- **Thread-Safe Concurrency:** Atomic state management and fine-grained `sync.RWMutex` locking for high-parallelism safety.

### Project Layout
├── cmd/
│   └── server/          # Application entrypoint
├── pkg/
│   ├── partition/       # Low-level disk log & byte index engine
│   └── server/          # High-performance TCP binary server
├── .gitignore
├── go.mod
└── README.md
### Quick Start

```bash
# Clone the repository
git clone [https://github.com/your-username/RayoLog.git](https://github.com/your-username/RayoLog.git)
cd RayoLog

# Run the broker server
go run cmd/server/main.go
🇷🇺 Русский
Обзор проекта
RayoLog (Rayo — с испанского Молния) — высокопроизводительный движок потоковой обработки событий (event-streaming), написанный с нуля на Go. Проект отказывается от тяжелой JSON-сериализации и громоздких структур в пользу Append-Only журнала с индексом байтовых смещений в оперативной памяти, обеспечивая сложность $O(1)$ на операции чтения и записи.Архитектура и инженерные особенностиAppend-Only диск-движок: Последовательная бинарная запись, минимизирующая головные расходы файловой системы.Индекс в OPM за $O(1)$: Массив байтовых офсетов для мгновенного точечного чтения сообщений без сканирования файла.Бинарный протокол без JSON: Кастомный кадровый протокол (length-prefixed framing) по TCP для нулевых/минимальных аллокаций памяти (allocs/op).Потокобезопасность: Использование тонких гранул блокировок sync.RWMutex для поддержки параллельных конкурентных запросов.Структура проекта.
├── cmd/
│   └── server/          # Точка входа в приложение
├── pkg/
│   ├── partition/       # Низкоуровневый движок лога и индекса
│   └── server/          # Высокопроизводительный TCP-сервер
├── .gitignore
├── go.mod
└── README.md

Быстрый запуск
Bash# Клонирование репозитория
git clone [https://github.com/your-username/RayoLog.git](https://github.com/your-username/RayoLog.git)
cd RayoLog

# Запуск сервера брокера
go run cmd/server/main.go
