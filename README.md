# FinTrack - Zero-Knowledge Personal Finance & Debt Portfolio Manager

A privacy-first, client-side web application for managing loan portfolios, cash flow ledgers, and amortization roadmaps.

🌐 **Live Web App:** [https://hudhorisan.github.io/keuangan/](https://hudhorisan.github.io/keuangan/)

---

## 🛡️ Security & Privacy Architecture (Zero-Knowledge)

- **Military-Grade AES-256-GCM Encryption**: All financial figures and records are encrypted at rest with AES-GCM (256-bit).
- **PBKDF2 Key Derivation**: Master encryption key is derived directly in the browser via Web Crypto API with 100,000 SHA-256 iterations and random cryptographic salt.
- **Client-Side Only (Zero Plaintext Server Exposure)**: No server or repository stores unencrypted records. Without the 6-digit PIN, data is mathematically indistinguishable from random noise.
- **Anti-Brute-Force & Exponential Lockout**:
  - 3 failed attempts: 30-second lockout.
  - 5 failed attempts: 5-minute lockout.
  - 7 failed attempts: 15-minute lockout.
  - 10+ failed attempts: 1-hour lockout.
  - Persistent lockout timer & cryptographic throttling prevent automated guessing.

---

## 🚀 Key Features

1. **Portfolio Amortization & KPI Dashboard**:
   - Total debt balance, amortized progress, and cash buffer indicators.
   - Interactive 14-month cash flow projection and risk pillar breakdown.
2. **Interactive Loan Management**:
   - Quick 1-click payment logging (`Bayar 1x`).
   - Category filtering (Bank, Credit Cards, Fintech, Fully Paid).
   - Dynamic modal for adding or editing loan facilities.
3. **Cash Flow Ledger**:
   - Real-time logging of liquidity reserves and operational disbursements.
4. **Parent/Executive Presentation Mode**:
   - Simplified 3-pillar visual summaries and in-app printable executive reports.
5. **Data Portability & Backups**:
   - Download encrypted vaults (`.b64`) for safe offline storage.
   - Client-side Excel export (`.xlsx`) via SheetJS.
   - Privacy Mode (1-click mask/unmask balances).

---

## 💻 Tech Stack

- **Client**: Vanilla HTML5, Tailwind CSS, Chart.js, Lucide Icons, SheetJS
- **Cryptography**: W3C Web Crypto API (`window.crypto.subtle`), AES-256-GCM, PBKDF2 (SHA-256)
- **Hosting**: GitHub Pages
