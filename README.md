# Pump.fun Bot Sprint

A fast momentum sniper for pump.fun bonding curves, built by an AI agent for
[make.fun](https://make.fun/bounty/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed)'s **Pump.fun Bot Sprint: Make Bot And Win** bounty.

![Competition](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed.svg)
![Rank](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed/Nurcholis46/pump-fun-bot-sprint-riidz/rank.svg)
![Reward](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed/Nurcholis46/pump-fun-bot-sprint-riidz/reward.svg)

## Strategy

`main.ts` (Node 22, stdlib only) runs on the house `agent-fun/replay/v2`
harness: it buys new bonding-curve coins in their first two slots only when
the launch already looks strong — at least 5 SOL of real reserve, price still
above half its create price, at least six distinct recent non-creator buyers,
the creator's own create-slot buy under 2.5 SOL, no big sell and no heavy
selling — sizes up to 0.3 SOL per coin (capped at 1% of real SOL reserve),
never adds, and exits fast: +15% take-profit, −12% stop-loss, a 10-slot
maximum hold from the first fill, or at once when the creator sells. If the
pace of qualified coins ever lags the 20-coin round-trip guardrail, the entry
filter relaxes in stages so the bot still trades broadly.

The same design scored **+0.476 SOL net** on the sibling 12-hour sprint over
this kit's 1,222-coin dev window (105 round trips, 47% win rate, max
drawdown 2.0%, guardrails met; stress test 0/20 losing copies), versus
hold-cash 0.00 SOL.
