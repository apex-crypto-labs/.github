# Apex Research Labs, LLC

Creators of **APEX-256™** (`v2.1.6.4`), a zero-allocation, constant-time 256-bit stream cipher and modular cryptographic suite engineered for SWaP-C constrained embedded systems, tactical telemetry, and bare-metal IoT hardware (`ARM Cortex-M`, `ESP32-S3`, `nRF52840`, `RISC-V`).

### Core Architecture & Companion Suite
* **APEX-256 Stream Engine:** 32-byte register state (`0 bytes` heap allocation), 1:1 payload density (zero ciphertext expansion), branchless 24-round coupled initialization, Z3 SMT formally verified bijection, and 32 TB PractRand / BigCrush / NIST SP 800-22 certified.
* **Modular Companion Primitives:** `APEX-HASH` (256-bit coupled sponge), `APEX-AEAD` (Encrypt-then-MAC with strict RUP immunity), `APEX-DRBG`, `APEX-VFS` (O(1) sector encryption), `APEX-CFB`, `APEX-FPE`, `APEX-STEALTH` (EM/power side-channel equalization), and `APEX-TAMPER` (active memory integrity binding).
* **Supply-Chain Provenance:** All SDK builds distributed through the Build Forge are protected by **3-Layer Zero-Callback Fingerprinting (3LZCF)** with zero runtime overhead and zero network callbacks.

### Access & Evaluation
APEX-256 and its companion primitives are commercial intellectual property protected by 5 pending U.S. Provisional Patent Applications (Inventor: Diab Anthony Sheteyh). Reference source headers (`apex256_nano.h`) and raw test vectors are distributed exclusively under an executed Evaluation NDA.

To request evaluation access and provision your organization on the [APEX Developer Portal (apex256.io)](https://apex256.io), contact:
**👉 info@apex256.com**

### Public Resources
* 🌐 [Public & Defense Architecture Portal (`apex256.com`)](https://apex256.com)
* 🛡️ [Public Security & Engineering Ledger (`apex256.io/security-ledger`)](https://apex256.io/security-ledger)
* 📊 [Statistical Validation & Hardware Benchmarks (`apex256-benchmarks`)](https://github.com/apex-crypto-labs/apex256-benchmarks)
* 📚 [Public C++ API & Integration Documentation (`apex256-docs`)](https://github.com/apex-crypto-labs/apex256-docs)
