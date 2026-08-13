# RayoLog ⚡

RayoLog (*Rayo* - Lightning) is an ultra-fast, lightweight event-streaming broker written in Go. It utilizes an append-only log architecture with an in-memory byte offset index to achieve $O(1)$ read/write complexity.

## Key Architecture & Features

- **Append-Only Storage:** High-throughput sequentially written binary segments.
- **In-Memory Indexing:** $O(1)$ offset-to-byte positioning for zero-cost message lookup.
- **Binary Protocol:** Low-overhead length-prefixed framing over TCP without JSON parsing penalties.
- **Thread-Safe Operations:** Concurrent read/write guarantees via `sync.RWMutex`.

## Project Structure
├── cmd/
│   └── server/          # Application entrypoint
├── pkg/
│   ├── partition/       # Low-level disk & index storage engine
│   └── server/          # High-performance TCP binary server

