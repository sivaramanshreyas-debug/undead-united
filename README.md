# Undead United

A Game Boy–style soccer survival game that runs in the browser. You're the striker with two teammates. The only weapon is the ball: power-shoot it through the zombies, keep your teammates from being bitten, and score to clear the pitch.

Play it: open `index.html` in a browser (no build step, no dependencies).

## How it plays

- **Score a goal** to clear every zombie and revive one bitten teammate (or regain a heart).
- **Each goal drops a coin.** Collect 2 coins to summon a dragon that burns every zombie in its path.
- **Each goal also raises the difficulty:** zombies get faster and more numerous, and the undead keeper gets quicker, reaches further and starts reading your shots.
- You have 3 hearts. A zombie touching a teammate turns them into another zombie.

## Controls

| Action | Keyboard | On-screen |
| --- | --- | --- |
| Run | Arrows / WASD | D-pad |
| Kick (hold to power up) | Z, J or Space | A |
| Pass (control follows the ball), or switch to the teammate nearest the ball | X or K | B |
| Start / pause | Enter, or click the screen | START |
| Sound on/off | Shift | SELECT |

## Tuning

Everything lives in `index.html`. The difficulty curve is a set of small functions near the top of the script, all driven by goals scored:

- `zombieSpeed`, `spawnGap`, `maxZombies`: zombie pressure
- `keeperSpeed`, `keeperReach`, `keeperRead`, `keeperRecover`: the keeper
- `COINS_PER_DRAGON`: coins needed to summon a dragon

The screen is a 160×144 canvas drawn in the original four-shade green palette. Sprites and the 3×5 pixel font are defined as strings in the script.

## Note on the file format

`index.html` is written as a page fragment (no `<!doctype>`/`<html>`/`<head>`/`<body>`), because it's also published as a Claude artifact, which adds that wrapper itself. It opens fine in a browser as-is.
