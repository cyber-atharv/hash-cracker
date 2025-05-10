# ⚡ High-Speed Multi-Threaded Hash Cracker

> A fast C++ password hash recovery tool supporting dictionary attacks, rule-based word mutations, brute-force keyspace partitioning, and multi-core acceleration.

[![Author](https://img.shields.io/badge/Made%20by-cyber--atharv-00ffcc?style=flat-square&logo=github)](https://github.com/cyber-atharv)
[![C++](https://img.shields.io/badge/C%2B%2B-23-00599C?style=flat-square&logo=cplusplus&logoColor=white)](https://isocpp.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

---

## 📌 What is Hash Cracking?

Cryptographic hash functions (like MD5, SHA-1, SHA-256) are **one-way mathematical algorithms**. Once a password is turned into a hash, you cannot mathematically reverse it. 

To recover an original password from a leaked hash, security analysts use **Dictionary Attacks** (testing millions of known passwords hashed against the target) and **Brute-Force Attacks** (generating every possible character combination).

This high-performance cracker was created by **cyber-atharv** using modern C++ with native multi-threading and zero-copy memory mapping (`mmap`) for maximum throughput.

---

## ✨ Key Features

- **Multi-Algorithm Support:** Automatically detects hash type by byte length:
  - `MD5` (32 hex characters)
  - `SHA-1` (40 hex characters)
  - `SHA-256` (64 hex characters)
  - `SHA-512` (128 hex characters)
- **Multi-Threaded Performance:** Automatically distributes candidate words across all available CPU threads with zero-lock contention.
- **Rule-Based Mutations (`--rules`):** Tests realistic password variations like Leet Speak (`p@ssw0rd`), Capitalization (`Password`), Digit Appending (`password2026`), and Reversals.
- **Pure Brute-Force Engine:** Keyspace search with custom character sets (lowercase, alphanumeric, symbols).
- **Salt Support:** Handles prepended and appended password salts (`hash(salt + password)`).
- **Live Terminal Telemetry:** Real-time speed monitor (hashes/sec), progress bar, and estimated time remaining (ETA).

---

## 🚀 Quick Start & Usage

### 1. Build using CMake
```bash
cd hash-cracker
cmake -B build
cmake --build build --config Release
```

### 2. Examples

#### 🔹 Crack a SHA-256 hash using a wordlist
```bash
./build/hashcracker --hash 5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8 --wordlist wordlists/10k-most-common.txt
# Output: ✔ CRACKED: password
```

#### 🔹 Crack with Rule Mutations (e.g. Leet Speak & Appended numbers)
```bash
./build/hashcracker --hash ed9d3d832af899035363a69fd53cd3be8f71501c --wordlist wordlists/10k-most-common.txt --rules
```

#### 🔹 Brute-Force unknown short passwords
```bash
./build/hashcracker --hash 8621ffdbc5698829397d97767ac13db3 --bruteforce --charset lower --max-length 6
```

---

## 🧠 Why I Built This

I wanted to understand low-level cryptographic implementations and concurrency in C++. Building this tool demonstrated the immense compute cost differences between fast, insecure hashes (MD5/SHA1) versus modern salted key-derivation functions (bcrypt/Argon2id), showing why password hashing algorithms must be computationally expensive.

---

## ⚠️ Responsible Use

> **Authorized Use Only:** Never test hashes from systems you do not own or without explicit authorization.

---

## 📜 Author & License

- **Author:** [cyber-atharv](https://github.com/cyber-atharv)
- **License:** Open source under the MIT / AGPL License.
