# Dhumbal (धुम्बल)

A browser version of Dhumbal, the Nepali card game. Play against 1–5 bots, or online with friends on different devices. Each player gets five cards, and the lowest hand total wins the round.

**Play:** <https://rashil9955.github.io/dhumbal/>

## Playing online with friends

1. Choose **Play online with friends**, type your name, and click **Create table**.
2. Send your friends the 4-letter code or the invite link.
3. When everyone is in the lobby, pick how many bots fill the empty seats and deal.

Up to 6 players, people and bots combined. The host's browser runs the game, so the host should keep their tab open. If the host reloads, the game picks up where it left off. If a friend's connection drops on their turn, a bot plays for them until they're back.

Online play needs a Firebase project. See [FIREBASE_SETUP.md](FIREBASE_SETUP.md).

## Rules

- **Card values:** A = 1, 2–10 = face value, J = 11, Q = 12, K = 13.
- **On your turn:** throw one card, a set of the same rank, or a run of 3+ in one suit. Then take the top card of the deck or a card from the previous player's throw. From a run you can only take an end card.
- **Show:** at the start of your turn you can call Show if your total is at or below the limit. If you have the lowest hand, you score 0 and everyone else scores their hand. If someone ties or beats you, you score your hand + 25 and the player with the lowest hand scores 0.
- When a player reaches the target score (50 / 100 / 200), they're out.

## Files

- `index.html`: the whole game
- `firebase-config.js`: Firebase project settings for online play
- `database.rules.json`: database security rules, which keep each player's cards private
