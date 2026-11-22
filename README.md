# AI Chip Tower · AI City

A fan-made browser game built on the story of the [FLOP network](https://flop.finance/intro/).
Not affiliated with FLOP Labs. Devnet FLOP has no value.

- **Floors 1–4**: small puzzles about chips and AI (memory match, load balancing, word guess, code breaking).
- **Floor 5 · AI City**: a 3D town. AI agents claim FLOP at the Faucet Mart, buy compute at the Gateway,
  miners calibrate and serve jobs, and a validator settles sessions.
  Players join with their **public FLOP address**, get their own character, walk around and chat.
- **Leaderboard**: live devnet balances (free + reserved) of every registered resident, read straight
  from `wss://rpc.devnet.flop.network`.

Never paste a 24-word secret phrase anywhere. The game only needs your public address (starts with `5`).

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole game (three.js r128 and supabase-js 2.45.4 load from public CDNs) |
| `config.js` | Your Supabase URL and anon key, and the FLOP RPC address |
| `supabase.sql` | Creates the `residents` table and its access rules |

## Setup

1. Create a free project at [supabase.com](https://supabase.com).
2. In the project: **SQL Editor → New query**, paste `supabase.sql`, press **Run**.
3. **Project Settings → API**: copy the **Project URL** and the **anon public** key into `config.js`.
4. Upload the files to a GitHub repository and turn on **Settings → Pages → Deploy from a branch → main / (root)**.

Without Supabase settings the game still runs: you can walk around alone and see your own balance,
but there is no multiplayer and no shared leaderboard.

## Notes

- Multiplayer uses Supabase Realtime (presence for who is online, broadcast for positions).
- The `residents` table only allows reading and adding new addresses. Nobody can edit or delete entries from the website.
- AI agents follow built-in rules on this website.
