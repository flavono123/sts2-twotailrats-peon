# STS2 Two-Tailed Rats — OpenPeon Sound Pack

```
    ·– ·– ·–    ᵉᵉᵏ!    ·– ·– ·–
  skitter · squeak · scream · silence
```

<p align="center">
  <i>"Two tails, one temper."</i><br/>
  An <a href="https://openpeon.com">OpenPeon</a> (CESP v1.0) sound pack of
  Two-Tailed Rat voice lines from
  <i>Slay the Spire 2</i> (2026, Mega Crit).
</p>

<p align="center">
  <a href="#installation">Install</a> ·
  <a href="#categories">Categories</a> ·
  <a href="#source">Source</a> ·
  <a href="#copyright--fair-use-notice">License</a>
</p>

---

A gritty, combat-only pack. Unlike companion voice packs with greetings and
thanks, the Two-Tailed Rats only ever hurt, die, attack, and summon — 37 clips
of pure hostile vermin energy wired into your Claude Code / Codex / IDE events.
Own the chaos.

## Installation

```sh
git clone https://github.com/flavono123/sts2-twotailrats-peon.git
peon packs install-local sts2-twotailrats-peon
peon packs use sts2_twotailrats
```

Preview any category:

```sh
peon preview session.start       # the rats appear
peon preview task.error          # ouch
peon preview resource.limit      # a rat dies, out of gas
peon preview user.spam           # pained squeals from over-prompting
```

## Categories

Mapped from the game's internal `sts2_sfx_VO_twotailrats_*` events in
`sfx.bank`. Pure monster VO — no greetings, no thanks, no laughter. Every
category is some flavor of combat or pain.

| CESP event         | Game event                        | Clips |
|--------------------|-----------------------------------|------:|
| `session.start`    | `twotailrats_summon`              |     2 |
| `task.acknowledge` | `twotailrats_attack1_a`           |     8 |
| `task.complete`    | `twotailrats_attack2`             |     4 |
| `task.error`       | `twotailrats_hurt` (1–6)          |     6 |
| `input.required`   | `twotailrats_attack1_b`           |     4 |
| `resource.limit`   | `twotailrats_die`                 |     7 |
| `user.spam`        | `twotailrats_hurt` (7–13)         |     6 |

> Mapping logic: the rats *appear* (summon) when your session starts; they
> *charge forward* (attack1_a) to take on each prompt; the *finishing
> lunge* (attack2) marks a completed response; *a hurt squeal* signals an
> error; the *quieter jab* (attack1_b) prods you when the turn is yours;
> a *death rattle* (die) means resources ran dry; and if you spam the
> prompt, well — more squeals. The hurt clips are intentionally split so
> `task.error` and `user.spam` feel distinct: error hurts are the early
> variants (lower-pitched jolts), spam is the later, more exasperated set.

**37 clips total · ~7.5 MB · 48 kHz stereo WAV**

## Source

Audio is extracted from the game's FMOD Studio sound banks. VO credit:
**Mars Orach** (voice of the Two-Tailed Rats).

1. Extract `Slay the Spire 2.pck` with
   [GDRE Tools](https://github.com/GDRETools/gdsdecomp):
   ```sh
   "Godot RE Tools.app" --headless \
       --recover="/path/to/Slay the Spire 2.pck" \
       --output-dir=extraction
   ```
2. Decode the twotailrats subsongs from `extraction/banks/desktop/sfx.bank`
   with [vgmstream](https://github.com/vgmstream/vgmstream):
   ```sh
   vgmstream-cli -s <subsong_n> -i -o "?n.wav" \
       extraction/banks/desktop/sfx.bank
   ```

All 37 twotailrats VO streams were extracted, renamed (stripping the
`sts2_sfx_VO_` prefix and `_v1_rr<N>` suffix), and mapped to CESP
categories by emotional context.

## Copyright & Fair Use Notice

The audio clips in this pack are short excerpts of voice lines from
*Slay the Spire 2*, copyright © 2026 Mega Crit, LLC. All rights reserved
by the original owners. Original VO performed by **Mars Orach**.

**This pack is:**
- **Non-commercial** — not sold, not monetized
- **Fan-made** — created out of appreciation for the game
- **Minimal in scope** — only short twotailrats VO grunts and squeals are
  included; no music, no full scenes, nothing that could substitute for the
  original game

This project makes no claim of ownership over any Slay the Spire 2
assets. If Mega Crit or any rights holder objects to this use, the repo
will be taken down promptly upon request.

The pack manifest, scripts, and documentation in this repository are
licensed under [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0/).
Audio assets themselves remain the property of their respective copyright
holders.

## Disclaimer

This is an unofficial fan project and is not affiliated with, endorsed
by, or sponsored by Mega Crit, LLC.
