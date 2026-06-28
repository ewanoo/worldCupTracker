## World Cup Tracker 

A single self-contained web app — one file with all HTML, CSS, and JavaScript, no build step, no server, no dependencies.
It's a "World Cup SweetStake" tracker: a family/office sweepstake tool for the 2026 World Cup knockout stage.

The premise: the 32 teams that reached the Round of 32 get shared out between 2–8 players (one per person in your group), then you follow the tournament and watch whose teams survive. It's pure client-side — everything saves to localStorage under the key wc-sweetstake-v2 (footer: "Saved in this browser only"), so it lives entirely in whoever's browser opened it.

The 32 teams, their FIFA rankings (June 2026), flag emoji, and the 16 Round-of-32 fixtures are all hard-coded in the script (TEAMS, R32), wired in proper bracket order so winners propagate correctly through R16 → QF → SF → Final.
---

#1. Setup (first run)
- Pick how many players (2–8) and type their names. Each person gets a fixed colour that follows them everywhere. A live hint tells you how the 32 teams divide (e.g. "8 each", or "X each with Y getting one extra, shared fairly at random").
- Make the draw — an animated lottery-ball draw. Choose a method first:
---

#2. The Draw tab — three ways to assign teams:
  - Pure random — straight shuffle.
  - Seeded – pots — split by FIFA rank into bands so everyone gets a mix of strong/weak.
  - Seeded – top teams first — top seeds dealt one-each, keeping the giants spread out.
  - You can "Skip to result" or "Draw again".
- Enter our draw by hand — if you already did the draw on paper/in the group chat. Either drag-and-tap teams onto each player's area (tap a team, then tap a player on mobile), or use a dropdown-per-team list. Save when all 32 are assigned.
- Record this draw — after drawing it shows the squads in plain words (copyable) plus a restore code (JSON). This is the key "share/portability" feature: copy the code, paste it into the app on another device or later, and the exact same squads rebuild (the tracker resets to the start of R32).
---

#3. The Tracker tab
- A scoreboard shows each player's count of "teams still in" and lists their teams (eliminated ones struck through).
- For each fixture, tap the team that won — it advances, the loser is struck out, and the winner feeds into the next round automatically. Tap the winner again to undo. Rounds appear as they fill up, ending in a highlighted Champions banner crediting the owning player.
- "Clear results" wipes bracket progress but keeps the draw; "Change number of players / start again" resets everything.
---
