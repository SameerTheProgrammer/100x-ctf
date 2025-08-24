# 🧩 Challenge: Twist & Claim (ed25519)

**Tags:** ed25519, web3.js, general API knowledge

## 2. Background

This problem has 2 solutions, 1 using the hints from section 4 and another using the standlone API
if you figout 2nd problem additional 1 iceSOL will be given to you as a reward

## 3. Attack Flow

1. Identify the issue in the message
2. use the message as text as seed to generate key
3. Submit the secret key string.

## 4. Helpers

### 4.1

- What happend in terra luna crash ? gives you the answer

### 4.2

```js
const orcaleCode = () => {
	const mnemonic = ans;

	const seed = bip39.mnemonicToSeedSync(mnemonic, "");
	const keypair = Keypair.fromSeed(seed.subarray(0, 32));

	console.log(bs58.encode(keypair.secretKey).toString()); // submit this output
};
```

### 4.3 API URL

```bash

curl --location 'https://100x-server-production.up.railway.app/submit/orcale' \
--header 'Content-Type: application/json' \
--data '{
    "msg": "<todo>"
}'

```

## 5 License

MIT. Hack responsibly. 🛡️
