# Dhumbal (धुम्बल)

A browser version of Dhumbal, the Nepali card game. You play against 1–5 bots. Each player gets five cards, and the lowest hand total wins the round.

## Play

Open `index.html` in a browser. There's no build step and nothing to install.

## Rules

- **Card values:** A = 1, 2–10 = face value, J = 11, Q = 12, K = 13.
- **On your turn:** throw one card, a set of the same rank, or a run of 3+ in one suit. Then take the top card of the deck or a card from the previous player's throw. From a run you can only take an end card.
- **Show:** at the start of your turn you can call Show if your total is at or below the limit. If you have the lowest hand, you score 0 and everyone else scores their hand. If someone ties or beats you, you score your hand + 25 and the player with the lowest hand scores 0.
- When a player reaches the target score (50 / 100 / 200), they're out.
