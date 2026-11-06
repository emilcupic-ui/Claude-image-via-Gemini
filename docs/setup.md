# Setup

This page covers adding the skill to Claude and checking that everything it needs is connected.

## 1. What has to be in place

| Piece | Why it is needed | How to check |
|---|---|---|
| Claude in Chrome extension | Lets Claude open and click through Gemini in your real Chrome | Chrome is open and the extension shows as connected |
| Signed-in Google account with Gemini | The images come from your own Gemini allowance | Open gemini.google.com yourself and confirm it shows your account |
| Claude desktop app (optional) | Lets Claude read your Downloads folder instead of asking you to drag files over | Claude's message box has an "Add folder" option in the "+" menu |

Without the desktop app, the skill still works. You just drag each downloaded image into the chat.

## 2. Add the skill

The skill is one file: `skills/gemini-image-gen/SKILL.md`. Pick the route that matches where you use Claude.

**In Claude (web or desktop app):**
1. Zip the skill folder so the zip contains a `gemini-image-gen` folder with `SKILL.md` inside:
   ```bash
   cd skills
   zip -r gemini-image-gen.zip gemini-image-gen
   ```
2. Upload the zip in Claude's skill settings.

**In Claude Code:** copy the folder into your skills folder.
```bash
cp -r skills/gemini-image-gen ~/.claude/skills/
```
Restart Claude Code afterwards.

If the upload screen asks for something different from the steps above, follow the screen. Claude's settings change over time.

## 3. Give Claude your Downloads folder (optional)

The first time you use the skill, Claude may ask to see your Downloads folder. Say yes only if you want it to pick up images itself. It reads the newest `Gemini_Generated_Image_*.jpeg` files and nothing else is needed.

## 4. Test it

Ask: *"Use Gemini to make one test image: a cozy isometric design studio on a floating island, pastel colours, 16:9."*

You should see Chrome open Gemini, an image appear after about 40 seconds, and a download land in your Downloads folder.

## Changing the skill

The skill text mentions "Emil" because it was written for one person. If you share this repo or reuse it, replace the name and the sentence about his Downloads folder in `SKILL.md` with your own.
