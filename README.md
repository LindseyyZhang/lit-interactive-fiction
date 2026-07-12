# lit-interactive-fiction

A Claude Skill that turns literary works into playable, single-file HTML interactive fiction — with meaningful choices, hidden value axes, butterfly effects, and endings that read as personality verdicts rather than win/lose states.

No build step. No dependencies. One HTML file you can double-click, host on GitHub Pages, or upload to itch.io.
---

## What it produces

Three games built with this skill, from three very different sources:

| Game | Source | Path taken |
|------|--------|-----------|
| **不落地的人 / Never Landing** | Calvino, *The Baron in the Trees* | Kernel-originalized (source still in copyright) |
| **The Trial** | Kafka, *The Trial* | Direct adaptation (public domain) |
| **Hamlet — An Interactive Tragedy** | Shakespeare, *Hamlet* | Direct adaptation (public domain) |

A complete worked example ships in https://tidalmoss.itch.io/hamlet-an-interactive-tragedy — open it in any browser to see what the skill actually outputs.

> Replace this section's links with your live URLs once deployed.

---

## Why it exists

Most "turn a book into a game" attempts produce a quiz: the choices are flavors of the same act, they converge immediately, and the ending is a grade. This skill encodes the craft rules that avoid that:

- **Dilemmas, not preferences.** Every choice node has to pass a test — would a thoughtful reader hesitate? If one option is obviously correct, it gets redesigned.
- **Three hidden value axes** named for the source's central tensions (Freedom / Wisdom / Bond; Resolve / Reason / Bond). Choices are worldviews, not stats.
- **At least one butterfly effect.** A small, innocent-looking early choice that visibly decides someone's fate in the final act.
- **Endings as verdicts.** "One who would rather be wrong in blood than right in silence" — never "good ending / bad ending." The ending that breaks the premise entirely gets equal dignity.
- **Copyright handled up front.** A check routes public-domain sources to direct adaptation, and copyrighted ones to kernel-based original creation — sharing only the *idea* (which isn't copyrightable), never the names, scenes, or prose.

---

## Install

**Claude Code (plugin):**
```bash
/plugin marketplace add YOUR-USERNAME/lit-interactive-fiction
/plugin install lit-interactive-fiction@lit-interactive-fiction
```

**Manual:** clone this repo and drop the `lit-interactive-fiction/` folder into your skills directory (`~/.claude/skills/` or your project's `.claude/skills/`).

**Claude.ai:** upload the `lit-interactive-fiction/` folder in Settings → Capabilities → Skills.

Installation methods change — check the [official docs](https://github.com/anthropics/skills) if the above doesn't match your setup.

---

## Usage

Just name a work:

> Turn *Hamlet* into an interactive fiction.
>
> 把《变形记》做成一个文字互动游戏
>
> Add a Chinese version and unlockable epilogues to the game we built.

The skill walks the full pipeline: extract the kernel → copyright check → originalize if needed → design chapters and choice nodes → build the game on the scene engine → generate ending cards and social copy → offer deployment.

---

## Structure

```
lit-interactive-fiction/
  SKILL.md                        # the workflow Claude follows
  references/
    narrative-design.md           # choice design, butterfly effects, ending craft
    html-engine.md                # scene engine architecture, particle/mood mapping
  assets/
    game-template.html            # complete working engine — don't rebuild, just reskin
```

The template ships with six particle systems (leaves, fireflies, rain, stars, embers, snow), gradient fallbacks so it works offline, WebAudio sound, mouse/gyroscope parallax, and mobile-safe layout. The skill's job is to write the story data, not the engine.

---

## A note on rights

Games built via the public-domain path are yours. Games built via the kernel path share only an unprotectable idea with their source. Neither is a blanket guarantee — the skill delivers a rights note with each finished game explaining the residual risks (differing PD dates by jurisdiction, translations that may still be in copyright, trademark on titles). Consult an IP lawyer before commercializing anything.

---

## License

MIT — see [LICENSE](LICENSE).

Background imagery in the template is hotlinked from Unsplash under its license.
