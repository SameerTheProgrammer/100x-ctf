# 🧩 Challenge: Twist & Claim (ed25519)

**Tags:** `ed25519`, `web3.js`, `API`, `bip39`

---

## 📖 Overview

This challenge is designed to test your understanding of **ed25519 key generation**, **mnemonics**, and **API integration**.
There are **two possible solutions**:

1. Using the hints provided in **Section 4 (Helpers)**.
2. Using the **standalone API**.

⚡ If you solve the second method, you’ll receive an **additional reward of 1 iceSOL**.

---

## 🔍 Attack Flow

Follow these steps to solve the challenge:

1. **Identify the issue in the given message.**
2. **Use the message text as a seed** to generate a keypair.
3. **Submit the secret key string** to the oracle API.

---

## 🛠️ Helpers

### 4.1 — Hint Question

- **Q:** What happened in the Terra Luna crash?
- **A:** Use the answer to derive the mnemonic.

---

### 4.2 — Example Code

You can use the following snippet to generate the secret key:

````js
import * as bip39 from "bip39";
import { Keypair } from "@solana/web3.js";
import bs58 from "bs58";

const orcaleCode = () => {
  const mnemonic = ans; // replace with the answer from 4.1

  const seed = bip39.mnemonicToSeedSync(mnemonic, "");
  const keypair = Keypair.fromSeed(seed.subarray(0, 32));

  console.log(bs58.encode(keypair.secretKey).toString());
  // 👉 Submit this output
};


### 4.3 — API Endpoint

Submit your generated secret key using the following API:

```bash

curl --location 'https://100x-server-production.up.railway.app/submit/orcale' \
--header 'Content-Type: application/json' \
--data '{
    "msg": "<your-secret-key>"
}'

````

## 5 License

MIT. Hack responsibly. 🛡️
