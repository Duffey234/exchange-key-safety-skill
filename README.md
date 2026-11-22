# exchange-key-safety: an agent skill for crypto exchange API keys

An [Agent Skill](https://agentskills.io/) (`SKILL.md`) that AI coding agents (Claude Code, Cursor, Codex, Copilot, Gemini CLI and others that read `SKILL.md`) load whenever a task touches a crypto exchange API key: Binance, Bybit, OKX, Bitget, ccxt, freqtrade, hummingbot, trading bots, or trading MCP servers.

We built it (Duffey234 / YourAITools). It's education, not financial or security advice.

## What it makes the agent do

- **Never** ask you to paste a key or secret into chat, and never put one in a command, URL, commit or log. It uses environment variables by name instead.
- **Never** turn on withdrawal or transfer permissions for a bot. Read + trade only, with an IP whitelist and testnet first.
- Treat any secret that appears in the conversation as leaked, and tell you to delete it on the exchange.
- Refuse to handle wallet seed phrases or private keys.
- Flag risky trading skills and MCP servers (ones that ask for withdrawal permission, hide steps, or run packed installers) before installing them.
- Fix common auth errors (Binance -2015, Bybit 10003/33004, OKX 50119, Bitget passphrase) instead of retrying in a loop or adding permissions.

## Install

```bash
npx skills add Duffey234/exchange-key-safety-skill
# or from the self-hosted discovery index (same file, sha256-pinned)
npx skills add https://quantaira.app
```

Or copy `skills/exchange-key-safety/SKILL.md` into your agent's skills folder (for example `.claude/skills/exchange-key-safety/SKILL.md`).

## Companion CLI

[exchange-key-doctor](https://github.com/Duffey234/exchange-key-doctor) is the CLI the skill refers to. It scans a repo for leaked Binance/Bybit/OKX/Bitget keys, includes gitleaks rules, and has an opt-in, local, read-only "can this key withdraw?" check.

## License

MIT
