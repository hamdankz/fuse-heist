# Word Heist: Fuse
A standalone mobile-first multiplayer word-clue hot-potato game. Node 20+; no external dependencies. Run `npm start`, open http://localhost:3000, create a room and share the six-character code. Start with 3–6 players. Deploy as a Render Node web service using npm install / npm start; health endpoint /health.

## Rules
100 HP, 15-second server-controlled fuse, maximum five pushes. First correct answer earns one lobby point and two seconds to choose Push or Defuse (default Push). Defuse is available below full health with at least three seconds remaining; solve a longer clue before the original fuse expires for +15 HP capped at 100, otherwise lose 30. Push redirects away from the solver; bomb grows continuously. At timeout or fifth push, opposite player loses 30 HP; no push means everyone loses 15. Odd survivor counts target two opposite neighbours: two-second multiple-choice word duel, winner avoids damage, loser loses 30, timeout both lose 15. After impact surviving slices redistribute. Last survivor wins; simultaneous elimination is a draw. Host can rematch, points and wins persist until room empties. Disconnected clients have 60 seconds to reconnect; disconnected bomb owner/source or duel participant causes a fresh round. State is in memory and lost on server restart.

## Bank and validation
New AI-authored clues filtered against exact answers and exact clue text from Crossword Heist v1.1. Not independently dictionary/editor reviewed; some clues may admit synonyms. Standard answers 3–6 letters; defusal 6+ letters; duel 3–5 letters. No repeat answer until eligible pool exhausted. One exact answer (case-insensitive); no automatic synonym acceptance. Run npm test for game logic. Four-client local HTTP/SSE smoke test performed; physical mobile and real family playtests remain outstanding.

## v1.0.1
Crimson and obsidian interface, teal defuse controls, updated branding and critical fuse highlight. Game rules and question bank unchanged.
