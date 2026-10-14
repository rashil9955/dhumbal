# Setting up online play

Online play uses a free Firebase project to pass moves between players. It takes about five minutes, and you only do it once.

## 1. Create the project

1. Go to <https://console.firebase.google.com> and sign in with a Google account.
2. Click **Create a project**, name it (for example `dhumbal`), and finish the steps. You can turn off Google Analytics.

## 2. Turn on anonymous sign-in

Players don't make accounts. Each browser gets an anonymous ID so the database can tell whose cards are whose.

1. Open **Build → Authentication → Get started**.
2. On the **Sign-in method** tab, choose **Anonymous**, switch it on, and click **Save**.
3. On the **Settings** tab, open **Authorized domains** and add `rashil9955.github.io`.

## 3. Create the database

1. Open **Build → Realtime Database → Create Database**.
2. Pick a location near you and start in **locked mode**.
3. On the **Rules** tab, replace everything with the contents of [`database.rules.json`](database.rules.json) and click **Publish**.

## 4. Connect the game

1. Open **Project settings** (the gear icon) → **General** → **Your apps**, and click the web icon `</>`.
2. Name the app and register it. You don't need Firebase Hosting.
3. Copy the `firebaseConfig` object it shows and paste it into [`firebase-config.js`](firebase-config.js):

```js
window.DHUMBAL_FIREBASE = {
  apiKey: "...",
  authDomain: "....firebaseapp.com",
  databaseURL: "https://...firebasedatabase.app",
  projectId: "...",
  appId: "..."
};
```

Make sure `databaseURL` is included. If it's missing, copy it from the top of the Realtime Database page.

## Is it safe to publish these values?

Yes. The Firebase web config identifies your project, but it isn't a password, and every Firebase web app ships it to the browser. What protects the data is the rules in `database.rules.json`:

- Your cards are readable only by you. Nobody else at the table can see them, the other players included.
- The deck and the bots' cards are readable only by the host's browser.
- Players can only send moves as themselves, and the host's browser checks every move against the rules of the game.
