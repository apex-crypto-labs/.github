# Apex Research Labs, LLC

Creators of **APEX-256™** (`v2.2.8.2`), a zero-allocation, constant-time 256-bit stream cipher and modular cryptographic suite engineered for SWaP-C constrained embedded systems, tactical telemetry, and bare-metal IoT hardware (`ARM Cortex-M`, `ESP32-S3`, `nRF52840`, `RISC-V`, and `FPGA RTL`).

### Core Architecture & Companion Suite (`v2.2.8.2`)
* **Self-Contained Zero-Allocation Context (`40 Bytes`):** `40-byte` self-contained `Apex256Nano` instance (`32-byte` / `256-bit` four-register core manifold and 8 bytes of companion control metadata; `0 bytes` dynamic heap allocation, `0 bytes` static `.bss`/`.tbss`/`.data`), 1:1 payload density (zero ciphertext expansion), and branchless 24-round coupled initialization.
* **Stage 1 & Stage 2 Architectural Capabilities (Waves 15 - 16):**
  * **Ephemeral Hardware Multiplier Masking:** Bit-exact side-channel operand blinding across the 64-bit modular multiplier datapath (`CPA |r| = 0.0024`, Welch `|t| = 0.74 < 4.50`, `100%` wire-compatible with standard Known Answer Tests).
  * **Extended 256-Bit Nonce (`X256`):** `init_x256`, `init_stealth_x256`, `init_wide_x256`, and `apex_aead_encrypt_x256` / `decrypt_x256` expanding random-nonce birthday safety from `2^32` to `2^128` messages with zero added RAM.
  * **Forward-Secrecy Keyframe Ratcheting:** `process_payload_ratcheted` and `ratchet_stream` executing an irreversible one-way state transition every 256 bytes (`100%` chunk-split invariant) so a physical RAM capture cannot be inverted to recover prior keystream.
  * **Full-State 256-Bit Companion Mode Architecture (`F256`):** Reclaims all 256 bits of active state across `HASH-W64`, `CFB-256`, `VFS-256` (with bijective 256-bit sector tweak isolation), and `DRBG-256` while keeping the `40-byte` context unchanged.
  * **Word-Rate Sponge (`W64`) & Feedforward Multi-Byte Stream Extraction (`process_payload_fast`):** Delivers `4x` to `8x` throughput acceleration across bulk stream encryption, hashing, MAC, KDF, VFS sector processing, and AEAD while preserving `100%` streaming chunk invariance and `1:1` byte-stream compatibility.
* **Modular Companion Primitives:** `APEX-HASH` / `HASH-W64`, `APEX-AEAD` / `AEAD-W64` / `AEAD-X256` (Encrypt-then-MAC with strict RUP immunity and dual-accumulator tag verification), `APEX-DRBG` / `DRBG-256`, `APEX-VFS` / `VFS-256` (`O(1)` sector encryption), `APEX-CFB` / `CFB-256`, `APEX-FPE`, `APEX-W32`, `APEX-STEALTH` (EM/power side-channel equalization), and `APEX-TAMPER` (active memory integrity binding).
* **Waves 1 - 16 & 38-Tool Formal Verification Battery:** Certified across 32 TB PractRand, TestU01 BigCrush, NIST SP 800-22, 16 cryptanalysis waves, a 38-tool external formal/SMT/SAT/MILP/SCA/RTL battery (Bitwuzla, cvc5, CaDiCaL, Coq, F*, HiGHS, SCALib, Lascar, VerFI, SymbiYosys), and a 7-engine reduced-round security-margin certification (`4.0x` to `24.0x` safety margin across the 24-round initialization schedule).
* **Supply-Chain Provenance:** All SDK builds distributed through the Build Forge are protected by **3-Layer Zero-Callback Fingerprinting (`3LZCF v3.1`)** and a 4-source compile-time target-architecture silicon interlock with zero runtime overhead and zero network callbacks.

### Access & Evaluation
APEX-256 and its companion primitives are commercial intellectual property protected by pending U.S. and International Patent Applications (Inventor: Diab Anthony Sheteyh). Reference source headers (`apex256_nano.h`) and raw test vectors are distributed exclusively under an executed Evaluation NDA.

To request evaluation access and provision your organization on the [APEX Developer Portal (apex256.io)](https://apex256.io), contact:
**👉 info@apex256.com**

### Public Resources
* 🌐 [Public & Defense Architecture Portal (`apex256.com`)](https://apex256.com)
* 🛡️ [Public Security & Engineering Ledger (`apex256.io/security-ledger`)](https://apex256.io/security-ledger)
* 📊 [Statistical Validation & Hardware Benchmarks (`apex256-benchmarks`)](https://github.com/apex-crypto-labs/apex256-benchmarks)
* 📚 [Public C++ API & Integration Documentation (`apex256-docs`)](https://github.com/apex-crypto-labs/apex256-docs)
