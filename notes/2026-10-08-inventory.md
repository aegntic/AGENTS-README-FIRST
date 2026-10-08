# 2026-10-08 inventory

Author: session looking at GitHub only. Did not run the CLIs. Did not call the gateway.

## ae-cli

https://github.com/aegntic/ae-cli

`packages/cli/src/index.ts` registers `discover`, `inspect`, `run`, `runs`. README install line is `bun add -g @aegntic/aedex`. `apps/web/public/llms.txt` shows `ae run openmeteo/weather/current`. PRD names the gateway, Stripe, and a locked public flip. 1 star, 7 open issues, pushed 2026-09-06.

Usable: ledger and CLI shape.
Not usable: a mint command.

## soldexter

https://github.com/aegntic/soldexter

README tools match the mint test: freeze via Helius, liquidity via Birdeye, holders via Helius. `package.json` bin is `soldexter`. Version `2026.5.30`. Default branch `master`. Pushed 2026-06-10. Forked from virattt/dexter. 3 stars.

Usable: the read, if keys are present.
Not usable: as an `ae` subcommand.

## relayindex

https://github.com/aegntic/relayindex

README says the graph is sample data and agent invocation is disabled. Domain `relayindex.dev` was parked as of the note dated 2026-08-30 inside that README. Pushed 2026-09-07. 0 stars.

Usable: schema names if a later record needs them.
Not usable: as a source in a public reply.

## Left alone

cldcde (12 stars, MCP hub), aegntic-MCP, aegntic-hive-mcp, aegntic-outcomes, tab-harvest, auto-sov-ops, ae-co-system. Related names. Not on the mint path.

## App idea

A GitHub App that opens this kind of log on install, and appends a note when a contributor's agent finishes a pass, would be a separate product. This repo is the file it would write. Not built here.
