# Daydreams x402 Auth Plugin for OpenClaw

An OpenClaw plugin that adds Daydreams Router (x402) as an authentication provider, enabling wallet-signed ERC-2612 permits for AI payments in USDC.

## What is x402?

x402 is a payment protocol (referencing HTTP 402 "Payment Required") that lets you pay for AI API calls using crypto instead of traditional API keys. It uses ERC-2612 permits signed by your wallet.

## Installation

```bash
# Install from local directory
openclaw plugins install -l /path/to/this/plugin

# Or via npm (once published)
openclaw plugins install @daydreams/openclaw-x402
```

## Configuration

During onboarding, you'll be prompted for:

- **Wallet private key** - A dedicated wallet for AI spend (0x + 64 hex chars)
- **Router URL** - Daydreams Router endpoint (default: https://ai.xgate.run/v1)
- **Permit cap** - Max USDC spend per permit (default: $10)
- **Network** - CAIP-2 chain ID (default: eip155:8453 for Base)

## Usage

After setup, use the x402 provider:

```bash
openclaw chat --model x402/anthropic/opus-4.5
```

## Security

- Use a **dedicated wallet** for AI spend, not your main wallet
- Private keys are stored locally in your OpenClaw config
- Permit caps limit exposure per session

## License

MIT
