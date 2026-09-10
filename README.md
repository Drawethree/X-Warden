# X-Warden
![X-Warden Header](https://imgur.com/k7W57di.png)

![Discord](https://img.shields.io/discord/1387881708581290257?label=Discord&logo=Discord)

X-Warden is anti-abuse for prison servers. It detects and proves the three things that actually kill
a prison economy — **automated mining**, **economy exploits** and **duping** — and gives your staff
enough evidence to judge each one in under thirty seconds.

It runs on any Paper server with **no required dependencies**. Install X-Prison alongside it and it
hooks straight into the core, gaining economy auditing that nothing else on the platform can offer.

## 💎 Get X-Warden

**X-Warden is a premium paid resource.** You can purchase it here:

### 👉 [**Buy X-Warden on BuiltByBit**](https://builtbybit.com/store/prison-store.392/) 👈

We also offer **a lot more for prison servers** — the [X-Prison core](https://builtbybit.com/resources/x-prison-core.18271/),
addons, setups and premium extras — at our [**Prison Store**](https://builtbybit.com/store/prison-store.392/),
with **amazing bundle discounts**!

---

## Why a prison-specific anticheat

A generic anticheat watches movement and combat. It has never heard of a sell multiplier.

**Speed is not the signal. Consistency is.** X-Warden measures timing variation, timing spread,
repeating loops, camera drift, session continuity and movement repetition, and scores each one
**next to what an ordinary player on your server looks like on the same measurement**. "0.4%
variation" means nothing on its own. "0.4%, and people are usually above 15%" is something a
moderator can act on.

It also knows what your server is: a player whose pickaxe breaks a block every tick is not a macro,
they own a good pickaxe, and X-Warden says nothing about their timing at all.

## Getting Started

| Step | Page |
|------|------|
| 1. Install it | [Installation](https://github.com/Drawethree/X-Warden/wiki/Installation) |
| 2. Learn the commands | [Commands & Permissions](https://github.com/Drawethree/X-Warden/wiki/Commands-&-Permissions) |
| 3. Calibrate to your own players | [Calibration](https://github.com/Drawethree/X-Warden/wiki/Calibration) |
| 4. Read what it can and cannot see | [What It Detects](https://github.com/Drawethree/X-Warden/wiki/What-It-Detects) |

---

# Pages

### General
* [Home](https://github.com/Drawethree/X-Warden/wiki)
* [Installation](https://github.com/Drawethree/X-Warden/wiki/Installation)
* [Commands & Permissions](https://github.com/Drawethree/X-Warden/wiki/Commands-&-Permissions)
* [Configuration](https://github.com/Drawethree/X-Warden/wiki/Configuration)
* [Placeholders](https://github.com/Drawethree/X-Warden/wiki/Placeholders)
* [Changelog](https://github.com/Drawethree/X-Warden/wiki/Changelog)

### How it works
* [What It Detects](https://github.com/Drawethree/X-Warden/wiki/What-It-Detects) — the honest list, including what it cannot see
* [Automation](https://github.com/Drawethree/X-Warden/wiki/Automation) — macros, autoclickers, AFK mining
* [Economy](https://github.com/Drawethree/X-Warden/wiki/Economy) — the invariant guard, multiplier auditing, the ledger and rollback
* [Integrity](https://github.com/Drawethree/X-Warden/wiki/Integrity) — duplicate items, proven rather than suspected
* [Linked Accounts](https://github.com/Drawethree/X-Warden/wiki/Linked-Accounts) — alt correlation, which can never punish anybody
* [Calibration](https://github.com/Drawethree/X-Warden/wiki/Calibration) — measuring the thresholds from your own players

### Default Files
* [_warden.yml_](https://github.com/Drawethree/X-Warden/wiki/warden.yml)
* [_warden-gui.yml_](https://github.com/Drawethree/X-Warden/wiki/warden-gui.yml)
* [_warden-messages.yml_](https://github.com/Drawethree/X-Warden/wiki/warden-messages.yml)

### Presets
* [_lenient.yml_](https://github.com/Drawethree/X-Warden/wiki/lenient.yml)
* [_balanced.yml_](https://github.com/Drawethree/X-Warden/wiki/balanced.yml)
* [_strict.yml_](https://github.com/Drawethree/X-Warden/wiki/strict.yml)

### Support
* [FAQ & Troubleshooting](https://github.com/Drawethree/X-Warden/wiki/Frequently-Asked-Questions---Troubleshooting)

### For Developers
* [Developer API](https://github.com/Drawethree/X-Warden/wiki/Developer-API)

---

## Built so it cannot ban your paying customers

- **Every statistical check ships on ALERT.** Nothing punishes anybody until you decide it should.
- **Every threshold carries a written note** saying what a false positive on that check looks like.
- **Only unstackable items are fingerprinted**, because an identity lives in an item's metadata and
  splitting a stamped stack would report a duplicate nobody created.
- **Checks stay silent until they have enough data.** A threshold guessed against an empty server is
  how good plugins get uninstalled on day one.
- **`/xwarden calibrate` measures your own players** and suggests the numbers, so you are not running
  thresholds guessed for somebody else's server. It never applies anything on its own.
- **X-Warden never recommends a punishment.** The evidence screen has a "What to do next" panel
  written for a new moderator and investigation buttons. There is no ban button, deliberately.
- **Alt-account detection cannot punish anybody.** There is no setting for it, because there is no
  responsible way to ban somebody for who else uses their connection.

## Built so it cannot cost you TPS

- Detection is O(1) per event, into fixed-size buffers that never grow.
- **Nothing allocates on the block-break path.**
- Every analysis runs off the main thread; every menu and every write is asynchronous.
- Mining income never becomes a database row per payout — three tiers, only two of which touch disk.
- A module you switch off registers no listeners and runs no tasks.

## Privacy

X-Warden **contacts nothing**. The only outbound connection it ever makes is the Discord webhook you
configure yourself: no telemetry, no update check, no metrics. Connection addresses are never stored
— what is stored is a hash under a salt generated on your server, which never leaves it.
