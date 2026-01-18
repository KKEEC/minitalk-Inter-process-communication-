# Minitalk — Minimal Inter-Process Communication (MVP)

**Minitalk** is a minimal Unix-like client-server communication system written in C, designed to demonstrate **inter-process communication (IPC)** using **Unix signals**.  
This MVP implementation enables sending messages from a client process to a server process at the bit level, providing hands-on experience with signals, process IDs, and low-level communication.

---

## 📌 Project Overview

Minitalk implements a simple message exchange system between two programs:

- **Server:** Waits for messages and prints them
- **Client:** Sends messages to the server using its PID

Messages are transmitted one bit at a time using **`SIGUSR1` for 0** and **`SIGUSR2` for 1**. This teaches signal handling, bit encoding/decoding, and process synchronization in C.

---

## 📂 Project Structure

minitalk-Inter-process-communication-/
├── client.c # Sends encoded messages to the server
├── server.c # Receives and prints messages
├── utils.c # Utility functions
├── utils.h # Function prototypes and constants
├── Makefile # Build automation
└── README.md # Project documentation


---

## ▶️ Usage

To use Minitalk, compile the programs, start the server, and send messages with the client. The server prints incoming messages in real-time.

This library-like MVP demonstrates reusable concepts for low-level IPC and can be integrated into larger projects requiring **process-to-process communication**.

---

## 🚀 Build & Run

1. **Clone the repository:**
```bash
git clone https://github.com/KKEEC/minitalk-Inter-process-communication-.git
cd minitalk-Inter-process-communication-
make
./server
> Server PID: 12345
./client 12345 "Hello from client"

$ ./server
Server PID: 12345
$ ./client 12345 "Hello World"
Hello World
$ ./client 12345 "Minitalk Test"
Minitalk Test
