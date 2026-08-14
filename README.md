<div align="center"> <img src="https://media.giphy.com/media/xTiTnHXbRoaZ1B1Mo8/giphy.gif" alt="Speedy Rabbit" width="260"/>
RayoLog ⚡🐇

Ultra-fast, lightweight event-streaming broker written in Go. Faster than a rabbit on an energy drink.

Show Image Show Image Show Image Show Image

<br/>
🌍 Choose your language / Выберите язык / Elige tu idioma

<a href="#-english"><img src="https://img.shields.io/badge/🇬🇧-English-2ea44f?style=for-the-badge"/></a> <a href="#-русский"><img src="https://img.shields.io/badge/🇷🇺-Русский-2ea44f?style=for-the-badge"/></a> <a href="#-español"><img src="https://img.shields.io/badge/🇪🇸-Español-2ea44f?style=for-the-badge"/></a>

(GitHub README не умеет выполнять JS, поэтому кнопки — это якоря, ведущие к нужному блоку ниже. Работает в один клик, как настоящий переключатель.)

</div>

<a id="-english"></a>

🇬🇧 English
<p align="center"> <img src="https://media.giphy.com/media/3o7TKz2eMXx7dn95FS/giphy.gif" alt="Hyperactive Bunny" width="220"/> </p>
Overview

RayoLog (Rayo — Spanish for Lightning) is a high-performance event-streaming log engine built from scratch in Go. It skips heavy JSON serialization and complex queue management in favor of an append-only log architecture backed by an in-memory byte-offset index, targeting O(1) read and write complexity.

Built for engineers who like their brokers the way rabbits like carrots: lean, fast, no bloat.

🏗 Architecture & Engineering Highlights
Feature	Why it matters
🐇 Append-only disk engine	Sequential binary writes — minimal disk-head movement, minimal fsync overhead
🐇 O(1) in-memory index	Byte-offset lookup table for instant reads, no full-file scans
🐇 Zero-JSON binary protocol	Custom length-prefixed TCP framing — near-zero allocations per message
🐇 Thread-safe by design	Fine-grained sync.RWMutex + atomics for safe high-concurrency access
📁 Project Layout
.
├── cmd/
│   └── server/          # Application entrypoint
├── pkg/
│   ├── partition/       # Low-level disk log & byte-index engine
│   └── server/          # High-performance TCP binary server
├── .gitignore
├── go.mod
└── README.md
🚀 Quick Start
bash
# Clone the repository
git clone https://github.com/your-username/RayoLog.git
cd RayoLog

# Run the broker server
go run cmd/server/main.go

📊 Benchmarks

Operation	Throughput	Latency (p99)
Write	TODO msg/s	TODO
Read	TODO msg/s	TODO
🤝 Contributing

Issues and PRs are welcome. If you improve RayoLog's speed, a rabbit somewhere will run even faster. 🐇💨

📄 License

Distributed under the MIT License. See LICENSE for details.

<div align="right"><a href="#rayolog-">↑ back to top</a></div>

<a id="-русский"></a>

🇷🇺 Русский
<p align="center"> <img src="https://media.giphy.com/media/3o7TKz2eMXx7dn95FS/giphy.gif" alt="Гиперактивный кролик" width="220"/> </p>
Обзор

RayoLog (Rayo — с испанского «Молния») — высокопроизводительный движок потоковой обработки событий, написанный с нуля на Go. Проект отказывается от тяжёлой JSON-сериализации и громоздких структур очередей в пользу архитектуры append-only лога с индексом байтовых смещений в оперативной памяти, обеспечивая сложность O(1) на операциях чтения и записи.

Сделано для тех, кто любит брокеры так же, как кролики любят морковку: без лишнего жира, только скорость.

🏗 Архитектура и инженерные особенности
Фича	Почему это важно
🐇 Append-only дисковый движок	Последовательная бинарная запись — минимум движений головки диска и накладных расходов fsync
🐇 O(1) индекс в памяти	Таблица байтовых офсетов для мгновенного чтения без сканирования файла
🐇 Бинарный протокол без JSON	Кастомный length-prefixed TCP-фрейминг — почти нулевые аллокации на сообщение
🐇 Потокобезопасность по умолчанию	Тонкая гранулярность sync.RWMutex + атомики для безопасного параллелизма
📁 Структура проекта
.
├── cmd/
│   └── server/          # Точка входа в приложение
├── pkg/
│   ├── partition/       # Низкоуровневый движок лога и индекса
│   └── server/          # Высокопроизводительный TCP-сервер
├── .gitignore
├── go.mod
└── README.md
🚀 Быстрый запуск
bash
# Клонирование репозитория
git clone https://github.com/your-username/RayoLog.git
cd RayoLog

# Запуск сервера брокера
go run cmd/server/main.go
📊 Бенчмарки

Операция	Пропускная способность	Задержка (p99)
Запись	TODO msg/s	TODO
Чтение	TODO msg/s	TODO
🤝 Вклад в проект

Issues и Pull Request'ы приветствуются. Если ты ускоришь RayoLog — где-то кролик побежит ещё быстрее. 🐇💨

📄 Лицензия

Проект распространяется под лицензией MIT. Подробности в файле LICENSE.

<div align="right"><a href="#rayolog-">↑ наверх</a></div>

<a id="-español"></a>

🇪🇸 Español
<p align="center"> <img src="https://media.giphy.com/media/3o7TKz2eMXx7dn95FS/giphy.gif" alt="Conejo hiperactivo" width="220"/> </p>
Descripción general

RayoLog (Rayo — porque va como uno) es un motor de streaming de eventos de alto rendimiento, construido desde cero en Go. Evita la serialización pesada en JSON y la gestión compleja de colas a favor de una arquitectura de log append-only respaldada por un índice de offsets en memoria, apuntando a una complejidad O(1) en lectura y escritura.

Hecho para quienes quieren su broker tan ligero y rápido como un conejo asustado.

🏗 Arquitectura y aspectos técnicos destacados
Característica	Por qué importa
🐇 Motor de disco append-only	Escrituras binarias secuenciales — mínimo movimiento del cabezal y overhead de fsync
🐇 Índice en memoria O(1)	Tabla de offsets para lecturas instantáneas sin escanear el archivo
🐇 Protocolo binario sin JSON	Framing TCP personalizado con prefijo de longitud — asignaciones casi nulas por mensaje
🐇 Seguro para concurrencia	sync.RWMutex de grano fino + atómicos para acceso concurrente seguro
📁 Estructura del proyecto
.
├── cmd/
│   └── server/          # Punto de entrada de la aplicación
├── pkg/
│   ├── partition/       # Motor de log e índice de bajo nivel
│   └── server/          # Servidor TCP binario de alto rendimiento
├── .gitignore
├── go.mod
└── README.md
🚀 Inicio rápido
bash
# Clona el repositorio
git clone https://github.com/your-username/RayoLog.git
cd RayoLog

# Ejecuta el servidor broker
go run cmd/server/main.go
📊 Benchmarks

Operación	Throughput	Latencia (p99)
Escritura	TODO msg/s	TODO
Lectura	TODO msg/s	TODO
🤝 Contribuciones

Los issues y pull requests son bienvenidos. Si haces que RayoLog vaya más rápido, en algún lugar un conejo correrá aún más rápido. 🐇💨

📄 Licencia

Distribuido bajo la licencia MIT. Ver LICENSE para más detalles.

<div align="right"><a href="#rayolog-">↑ arriba</a></div>
<div align="center">

🐇 Made with love, coffee and a lot of bunnies 🐇

</div>
