# crab_games_one_pager

Why this exists
Most tokens reward insiders or farms. Crab Game rewards survival. It's fair because the rules live in code, not in Discord. If you want the cream, play the game.

Wanna play the fair game?



Crab Game — one-pager 
TL;DR: Buy CRBH, hit the min holding amount, and you're in the season. Each round you press Play (small fee). Miss too many → you're eliminated. Eliminated balances are confiscated, swapped to USDC, and added to the prize pool. The season ends when the majority votes to quit or one wallet remains. Survivors split the pot pro-rata. All rules are enforced on-chain.

Live on Base (mainnet)
- Token (CRBH): 0x4582093Cd0b721ADf2372AC6208F90d1dC5B9CfB
- Controller: 0xE6a6FF016411A73AE224FCB5dcddD79a6D1B6d0b
- Treasury: 0x7aC01a214Df8A60DA000009b4dFB0683C019d93C

What it is
A round-based survival game tied to a token. No private admin magic, no insider exit ramps. If you're in, you play by the same code as everyone else.

How to join
Buy CRBH and reach the minimum holding amount (configurable, shown in the UI).

If a season is live, you're auto-registered (within the early "join window").

Your wallet becomes locked for regular transfers while the game is active—so you can't dodge eliminations by moving coins. This applies while you're registered/active in a live season. After the late-join cutoff, wallets above the minimum also can't transfer out—closing the brief escape window.

If you're below the min holding amount, you're safe (not in the game). Cross the line during the join window → you enter.

No one is safe.
Even if you hold below the minimum and think you are safe, other players can send tokens to
your wallet. If that pushes you over the minimum and the late-join window is still open for the
current round, you will be auto-registered. This is a survival game, not a safe harbor.


Rounds & phases (simple)
Play → press Play during the timer (small fee).

Discuss → chill, read the room.

Vote → press Vote to Quit if you want the season to end now (small fee).

Resolve → either the next round begins, or the season ends and prizes are claimable.

Strikes: If you skip Play, you get a strike. 3 strikes = eliminated.
Note: strikes persist across seasons, but they can be cleared occasionally (amnesty) or via a hard reset—so don't build a lazy habit.

Eliminations & prize pool
When someone is eliminated, the controller confiscates their CRBH, sells it on DEX (with slippage/tax protections), and adds the USDC to the prize pool.

At season end, survivors share the pool pro-rata to their snapshot balance.

You claim within a short window (shown in UI; configurable, typically ~1 day). Unclaimed leftovers go to the treasury to keep the ecosystem running.

How a season ends
Majority vote to quit (more than 50% of survivors vote), or

Last wallet standing (everyone else eliminated).

Why it's hard to game
Transfer locks: If you're active, you can't transfer out to dodge risk. After the late-join cutoff, wallets above the minimum can't transfer out either, gently closing the escape window.

Auto-register: If you hit the min holding amount during a live join window, the token tries to register you immediately—no "I bought but I'm not playing" games.

Fee levers (capped): Play/Vote fees can be tuned up (within hard on-chain limits) to price out spam bots or multi-wallet farms.

System-only exemptions: Only the controller/treasury bypass transfer locks—no secret admin wallets.

Commit-reveal randomness and weighted selection make eliminations scalable and auditable.

No one is fully safe: Bigger balances lower your odds, but never to zero. Everyone plays under the same rules.

Everything emits events. The UI just mirrors on-chain truth.

Money flow (plain English)
Buy/Sell taxes (capped): Part can burn (reducing supply), part can go to treasury (ops, LP, keepers).

Eliminations → prize: Confiscated CRBH is swapped to USDC and tracked on-chain.

Claims: Survivors claim directly from the controller. If you miss the window, funds are swept to treasury (transparent).

Play/Vote fees: Forwarded to the treasury; they don't fund the prize pool.

Relevant tokenomics
- Supply: 1,000,000,000,000 CRBH (fixed)
- Buy tax: 5% max (current: 5%)
- Sell tax: 20% max (current: 20%)
- Auto-register minimum stake (controller): default 1,000,000 CRBH
 - Weighting: Inverse (sqrt). Smaller = higher elim weight; whales never 0. Cap > 5,000,000 CRBH.

Burn mechanics 
- Buys: 5% of the trade is burned.
- Sells: 20% total tax → 10% burned + 10% sent to treasury (in CRBH).
- Treasury CRBH is held (not auto-LP); ops can add LP later when desired.

Treasury options (ops-managed): ETH from fees and CRBH from taxes can be paired to top up liquidity, or ETH can be used to buy CRBH and burn. We have flexible tools, so we don't need constant sells to fund operations. Transfer locks on active players also help ease sell pressure during a season.

Community distributions: CRBH can be airdropped to engage more users so they play the game and continue sending ETH fees. During live seasons, transfer locks on active players help reduce immediate sell pressure. ETH continues building treasury or LP alongside if airdropped wallets choose to play the game.

What you actually do in the dApp
Connect Wallet

See: timers, current round, live eliminations, prize pool, your strikes, your eligibility.

Buttons:

Play (during Play phase)

Vote to Quit (during Voting)

Claim (if you survived when the season ends)

That's it. No spreadsheets, no degen rituals.

Player checklist
Hit the min holding amount before the join window closes.

Press Play every round. Don't get strikes.

Watch Voting—if most want out, the season ends and you claim.

If you survive the end: Claim within the window.

Risk notes (no BS)
Prices move. Taxes apply on buys/sells per config.

If you go AFK and rack up strikes, you will be eliminated and your CRBH will be sold into the pot.

If you don't claim in time, your share goes to treasury.

Smart contracts are open-source and tested, but still: crypto is crypto. Only play what you can afford to risk.

For the curious (light technicals)
The controller runs phases, eliminations, prize calc, claims, and DEX sells with a minOut guard.

The token enforces auto-register + transfer lock while the season is live; only system addresses are exempt.

Randomness: commit in one phase, reveal in the next; fallback seed if no reveal.

Weighted elim: Fenwick tree for gas-efficient draws; inactivity removals update weights.

Admin caps: Fee/tax maxes are hardcoded; configs are lockable; deployer can renounce.

Activation (optional): Some features engage once a minimum number of eligible holders exists; once on, they stay on.



Disclaimer
Crab Game is experimental software and a high-risk game token. It is not an investment, security, or advice. Smart
contracts can fail and markets can be volatile. Taxes, fees, and parameters are bounded by code and may be
updated by authorized roles. Participation may have legal or tax implications depending on your jurisdiction. Always
do your own research and only use funds you can afford to lose. By using the protocol you acknowledge these risks
and agree that you are responsible for your actions.
