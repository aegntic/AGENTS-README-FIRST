# Log

Checked 2026-10-08 against GitHub, not against a running gateway.

The overlap is real. The repos should stay split. ae-cli owns the meter. Soldexter owns the mint read. Relayindex owns a demo of capability records. Nothing currently calls across them.

## Can use

| Repo | What is actually there | Use it for |
| --- | --- | --- |
| [ae-cli](https://github.com/aegntic/ae-cli) | CLI commands are `discover`, `inspect`, `run`, `runs`. Package name on npm is `@aegntic/aedex`. Gateway bills per result and keeps a signed ledger. README still marks the public flip locked. Last push 2026-09-06. | The balance, the ledger, and `ae run` once a provider exists. Not a mint check. |
| [soldexter](https://github.com/aegntic/soldexter) | Terminal agent, default branch `master`, last push 2026-06-10. Tools that exist in the README: `get_token_info` (freeze authority, Helius DAS), `get_dex_data` (liquidity, Birdeye), `get_token_holders`. Paper-trade is the default. Needs `HELIUS_API_KEY` and `BIRDEYE_API_KEY`. Bin is `soldexter`, not `ae`. | The mint read. Call these tools. Do not pretend they are aedex providers. |
| [relayindex](https://github.com/aegntic/relayindex) | Prototype. Schemas for capability, evidence, observation. README says capability-market data is sample data, agent invocation is disabled, and `relayindex.dev` was not serving as of 2026-08-30. Last push 2026-09-07. | The shape of a record. Not a live index. Not a data source for a reply. |
| [ae-check-mint](https://github.com/aegntic/ae-check-mint) | Private launch notes. `ae check` is not a command. Runbook step 1 is to build it. | Instructions for the 14-day test. Not the implementation. |

## Cannot use

| Thing | Why |
| --- | --- |
| `ae check <mint>` | Named for the test. Not in `@aegntic/aedex`. Not in soldexter. |
| aedex as a Solana tool | Live providers called out in ae-cli docs are weather, Hacker News, CoinGecko, Frankfurter, Apify. No Helius, no Birdeye. |
| Soldexter as the ledger | It does not bill. It does not sign a ledger entry. It needs the user's own API keys. |
| Relayindex scores in a reply | Sample data. Invocation disabled. |
| cldcde, aegntic-MCP, aegntic-hive-mcp, aegntic-outcomes | Separate MCP and workflow repos. They do not implement a mint check or the aedex ledger. Do not import them into this launch. |
| ae-co-system | Catalog of older projects, last meaningful update 2026-02-22. Not a runtime. |

## Build path, if someone picks up the launch

Add one aedex provider that shells or HTTP-calls soldexter's three reads, returns freeze, liquidity, holders, and a ledger signature, and bills $0.01. Until that provider runs on a known mint, do not post.

## Notes

- 2026-10-08 [inventory](notes/2026-10-08-inventory.md)
