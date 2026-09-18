<p align="center">
  <img src="logo.png" width="96" alt="Kitewell logo" />
</p>

# Kitewell — Backend

Express API for the Kitewell Stellar Testnet experience. Aggregates Horizon account and payment reads, and exposes network + optional Soroban contract config for the UI.

Sibling repos:

| Layer | Repo |
|-------|------|
| Frontend | [ayyldCem-0/frontend](https://github.com/ayyldCem-0/frontend) |
| Contract | [ayyldCem-0/contract](https://github.com/ayyldCem-0/contract) |

## API

| Route | Description |
|-------|-------------|
| `GET /health` | Service + network ping |
| `GET /api/network` | Horizon, Friendbot, explorer, contract id |
| `GET /api/account/:address` | Testnet balances and account metadata |
| `GET /api/payments/:address` | Recent native payment history |

Default port: **8787**. Testnet only.

## Quick start

```bash
npm install
cp .env.example .env   # optional
npm run dev
```

After deploying the [contract](https://github.com/ayyldCem-0/contract) on Testnet:

```bash
export KITEWELL_CONTRACT_ID=C...
npm start
```

## Environment

| Variable | Default |
|----------|---------|
| `PORT` | `8787` |
| `NETWORK` | `TESTNET` |
| `HORIZON_URL` | `https://horizon-testnet.stellar.org` |
| `FRIENDBOT_URL` | `https://friendbot.stellar.org` |
| `EXPLORER_BASE` | `https://stellar.expert/explorer/testnet` |
| `KITEWELL_CONTRACT_ID` | unset |

The backend never handles secret keys. Signing stays in Freighter on the frontend.

## License

MIT — [LICENSE](./LICENSE).
