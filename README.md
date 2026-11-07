# The A+ Challenge — Multiplayer prototype

## What works
- Host creates a unique 6-character room and shares an invite URL.
- Up to **20 real players** join simultaneously from their own browsers, enter a name, and choose one of 12 cartoon avatars.
- Automatic cartoon-themed host and Byte the Raven co-host (emoji placeholders for now).
- Four rounds: 15-second audience qualifying question; fastest correct answer goes on stage; three timed onstage questions; scores update live.
- 15% random Core 2 bonus chance on qualifying questions after the first, with no back-to-back bonus.
- 13 **original prototype questions**, automatic question explanations, leaderboard, reset.
- Basic low-volume synthesized ambient sound toggle (not yet the full 90s hip-hop soundtrack).

## Run locally
Install Node.js 18 or later. In this directory:

```bash
npm install
npm start
```

Open `http://localhost:3000` to host. To test players on the same computer, open the invite link in separate browser windows. To join from different devices on your home Wi-Fi, use the host computer's LAN IP address instead of `localhost` (e.g. `http://192.168.1.10:3000/?room=ABC123`) and allow the server through the firewall.

## Deploy for classmates
Deploy the **entire Node.js app** to a host that supports long-lived Node servers and WebSockets (for example, Render or Railway). Build command: `npm install`. Start command: `npm start`. Share the public HTTPS link with your Slack group. Free hosts may sleep and interrupt games; use a reliable instance for live sessions. This prototype stores rooms and scores only in server memory; a restart loses the session. Keep one server instance for now.

## Current limitations
- Cartoon characters are emoji placeholders; no walking animation yet.
- Stage round is a three-question challenge; mini-games, wheel, championship, and study exports are not implemented.
- No persistent database, login, moderation, recovery from disconnect, or anti-cheat protections. The fastest-answer winner is measured by server receipt time, so network latency can affect ties.
- The game bank currently contains 10 Core 1 and 3 Core 2 questions; target is 75 Core 1 and 25 Core 2.
- Not affiliated with the NFL, Baltimore Ravens, or CompTIA. For a public release, use original branding and character art rather than official logos/mascots without permission.
