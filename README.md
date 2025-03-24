# PumpSwap SDK

PumpSwap SDK is a lightweight library for interacting with PumpSwap, enabling easy token swaps on the Pump.fun ecosystem.

## Getting Started

1. Install dependencies:
   ```sh
   npm i
   ```

2. Configure environment variables:
   - Copy `.env.copy` to `.env`
   - Add your **private key** and **Helius RPC key** to the `.env` file.

## Usage

### Buy/Sell on PumpSwap

```typescript
import { wallet_1 } from "./constants";
import { PumpSwapSDK } from "./pumpswap";

async function main() {
    const mint = "your-pumpfun-token-address";
    const sol_amt = 0.99; // Buy 0.99 SOL worth of tokens using WSOL
    const sell_percentage = 0.5; // Sell 50% of the tokens
    const pumpswap_sdk = new PumpSwapSDK();

    await pumpswap_sdk.buy(new PublicKey(mint), wallet_1.publicKey, sol_amt);
    await pumpswap_sdk.sell_percentage(new PublicKey(mint), wallet_1.publicKey, sell_percentage);
    await pumpswap_sdk.sell_exactAmount(new PublicKey(mint), wallet_1.publicKey, 1000); // Sell 1000 tokens
}
```

### Fetch Token Price

```typescript
import { getPrice } from "./pool";

async function main() {
    const mint = new PublicKey("your-pumpfun-token-address");   
    console.log(await getPrice(mint));
}
```

### Fetch PumpSwap Pool Info

```typescript
import { getPumpSwapPool } from "./pool";

async function main() {
    const mint = new PublicKey("your-pumpfun-token-address");   
    console.log(await getPumpSwapPool(mint));
}
```

---

For any inquiries or collaborations, contact me on Telegram: **[@g0drlc](https://t.me/g0drlc)**

