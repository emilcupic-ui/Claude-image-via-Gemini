# Claude image via Gemini

A Claude skill that lets Claude make images with **your own Gemini account** and use them in a design, with no API key and no extra billing.

Claude opens gemini.google.com in your signed-in Chrome, types the prompt, waits for the picture, and downloads it. The image then goes into whatever Claude is building, usually a landing page on a design canvas.

```
Claude writes prompt  →  Gemini in your Chrome  →  Downloads folder  →  Claude design
```

## What you need

- A Claude plan with skills and the Claude in Chrome extension
- Chrome open and signed in to a Google account that has Gemini
- Optional: the Claude desktop app, so Claude can reach your Downloads folder

## Quick start

1. Add the skill to Claude (see [docs/setup.md](docs/setup.md)).
2. Ask for images in plain words:
   *"Use Gemini to make 4 images for this landing page. Soft pastel, isometric, 16:9."*
3. Claude batches the prompts, runs Gemini in Chrome, and downloads the files.
4. If Claude can't copy the files itself, drag them into the chat. It does the rest.

## How well it works

- One image takes about 40 seconds and roughly 15 browser steps.
- Several images in one Gemini chat cost less per image than single runs.
- Files in the chat arrive compressed (about 270 KB from a 2 MB original). That is fine for mockups. Use the originals from Downloads for final work.

## Documentation

| Page | What it covers |
|---|---|
| [docs/setup.md](docs/setup.md) | Adding the skill, and what must be connected |
| [docs/usage.md](docs/usage.md) | How to ask, writing good prompts, a worked example |
| [docs/how-it-works.md](docs/how-it-works.md) | Each step Claude takes, and why |
| [docs/troubleshooting.md](docs/troubleshooting.md) | What to do when something fails |
| [docs/alternatives.md](docs/alternatives.md) | Other ways to get Gemini images into Claude, and when to switch |
| [CHANGELOG.md](CHANGELOG.md) | What changed in each version |

The skill itself is in [skills/gemini-image-gen/SKILL.md](skills/gemini-image-gen/SKILL.md).

## Good to know

- This drives the normal Gemini website the way you would by hand. It is not an official integration, so a change to Google's page layout can break it. See the troubleshooting page.
- It uses your Gemini image allowance, not Claude's. Claude usage still goes up, because every browser step costs some.
- Check Google's current terms for automated use of your account before relying on this heavily.
