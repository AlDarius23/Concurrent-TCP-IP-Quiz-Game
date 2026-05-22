# Concurrent TCP/IP Quiz Game

A terminal-based, multiplayer trivia game built in C. It relies on a concurrent client-server architecture and an SQLite database to provide a synchronized, real-time competitive experience across multiple connected users.

## Features

- **Concurrent Server:** Utilizes `fork()` to spawn independent processes for each connected client, allowing simultaneous gameplay.
- **Database Integration:** Uses `sqlite3` to dynamically load random questions, track player scores, and manage the central game state (`quiz_game.db`).
- **Asynchronous Timeouts:** The client implements the `select()` system call to enforce a strict 15-second timeout for answering questions, ensuring the game flows without blocking.
- **Turn-Based Logic:** Players wait in a lobby until the game starts, and then take turns answering questions, with the server automatically syncing the turn order.

## Tech Stack

- **Language:** C
- **Networking:** POSIX Sockets (TCP/IP)
- **Database:** SQLite3
- **System Calls:** `fork`, `waitpid`, `select`

## Setup & Compilation

**Prerequisites:** You need GCC and the SQLite3 development library installed on your Linux environment.
```bash
sudo apt-get install libsqlite3-dev
