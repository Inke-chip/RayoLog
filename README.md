
RayoLog ⚡🐰
Ultra-fast, lightweight event-streaming broker written in pure Go.
Faster than a rabbit on an energy drink. Zero JSON, zero garbage, pure speed.

Choose your language / Выбери язык / Elige tu idioma 🐰:

EnglishРусскийEspañol


🇬🇧 English
Cute Nose Bunny

🧠 Engineering Overview
RayoLog (Rayo — Spanish for Lightning) is a high-performance event-streaming log engine built from scratch in Go. It eschews heavy JSON serialization and complex queue management in favor of an Append-Only Log architecture with an In-Memory Byte Index, guaranteeing O(1) read and write time complexity.

Designed by a developer who loves rabbits and hates unnecessary memory allocations.

⚙️ Architecture & Deep Dives
Append-Only Disk Engine: Sequential bin writes minimizing disk head movement and syscall overhead. No middlemen, just raw bytes.
O(1) In-Memory Index: Sparse/dense byte offset mappings for instantaneous message lookups without disk scans. Memory footprint is strictly controlled.
Zero-JSON Binary Protocol: Custom length-prefixed framing over TCP designed for minimal memory allocations (allocs/op). We don't parse JSON; we frame bytes.
Thread-Safe Concurrency: Atomic state management and fine-grained sync.RWMutex locking. High-parallelism safety without global lock bottlenecks.
📂 Project Layout
Click to expand structure
</details>

🚀 Quick Start
bash

# Clone the repository
git clone https://github.com/your-username/RayoLog.git
cd RayoLog

# Run the broker server
go run cmd/server/main.go
<a name="russian"></a>

🇷🇺 Русский
<p align="center">
<img src="https://media.giphy.com/media/3oEjI5VtIhHvK5W2mY/giphy.gif" alt="Bouncing Bunny" width="280" />
</p>

🧠 Инженерный обзор
RayoLog (Rayo — с испанского Молния) — высокопроизводительный движок потоковой обработки событий (event-streaming), написанный с нуля на Go. Проект отказывается от тяжелой JSON-сериализации и громоздких структур в пользу Append-Only журнала с индексом байтовых смещений в оперативной памяти, обеспечивая сложность 
O(1)
 на операции чтения и записи.

Создано разработчицей, которая любит кроликов и не терпит лишних аллокаций памяти.

⚙️ Архитектура и технические детали
Append-Only диск-движок: Последовательная бинарная запись, минимизирующая перемещения головок диска и накладные расходы файловой системы.
Индекс в ОЗУ за 
O(1)
: Массив байтовых офсетов для мгновенного точечного чтения сообщений без сканирования файла. Следим за потреблением памяти.
Бинарный протокол без JSON: Кастомный кадровый протокол (length-prefixed framing) по TCP для нулевых/минимальных аллокаций (allocs/op). Мы не парсим JSON, мы оперируем байтами.
Потокобезопасность: Атомарное управление состоянием и тонкие гранулы блокировок sync.RWMutex. Высокая параллельность без узких мест на глобальных мьютексах.
📂 Структура проекта
Нажми, чтобы развернуть
🚀 Быстрый запуск
bash

# Клонирование репозитория
git clone https://github.com/your-username/RayoLog.git
cd RayoLog

# Запуск сервера брокера
go run cmd/server/main.go
<a name="spanish"></a>

🇪🇸 Español
<p align="center">
<img src="https://media.giphy.com/media/26gscDsXKM3qje840/giphy.gif" alt="Sleeping Fluffy Bunny" width="280" />
</p>

🧠 Descripción de Ingeniería
RayoLog (Rayo — Relámpago en español) es un motor de streaming de eventos de alto rendimiento construido desde cero en Go. Descarta la pesada serialización JSON y la gestión compleja de colas a favor de una arquitectura de Registro Append-Only con un Índice de Bytes en Memoria, garantizando una complejidad de tiempo 
O(1)
 para lectura y escritura.

Creado por una desarrolladora a la que le encantan los conejos y odia las asignaciones de memoria innecesarias.

⚙️ Arquitectura y Detalles Técnicos
Motor de Disco Append-Only: Escrituras binarias secuenciales que minimizan el movimiento del cabezal del disco y la sobrecarga del sistema de archivos.
Índice en Memoria 
O(1)
: Mapeo de offsets de bytes para búsquedas instantáneas de mensajes sin escanear el disco. Huella de memoria estrictamente controlada.
Protocolo Binario sin JSON: Encuadre personalizado basado en longitud (length-prefixed framing) sobre TCP, diseñado para minimizar las asignaciones de memoria (allocs/op). No parseamos JSON, enmarcamos bytes.
Concurrencia Segura para Hilos: Gestión de estado atómico y bloqueos sync.RWMutex de grano fino. Alta seguridad en paralelismo sin cuellos de botella de bloqueo global.
📂 Estructura del Proyecto
Haz clic para expandir
🚀 Inicio Rápido
