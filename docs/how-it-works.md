# How it works

This page explains each step so you can understand what Claude is doing, and fix it when a step breaks.

## The big picture

```
Write prompts  →  Open Gemini in Chrome  →  Wait and check  →  Download  →  Bring files in  →  Use in design
```

Everything happens in your real Chrome, in a new tab next to your own. Claude never sees your password. It uses the sign-in that Chrome already has.

## The steps

1. **Plan the batch.** Claude lists every image the task needs and writes all prompts first. This keeps the browser part short.
2. **Load the browser tools once.** Claude loads all the Chrome tools it needs in a single step, because each extra loading step costs a round trip.
3. **Open Gemini.** Claude looks at your open tabs, then opens gemini.google.com/app in a new tab.
4. **Send the prompt.** It finds the prompt box, clicks it, types the prompt, and presses Enter.
5. **Wait and check.** Gemini shows "Creating your image" while it works, usually 30 to 45 seconds. Claude checks by reading the page as text, which is cheap.
6. **Look once.** When the image is done, Claude takes one small screenshot to confirm it looks right. Screenshots are the costly part, so it avoids more than one.
7. **Download.** It hovers over the image so the controls appear, then clicks "Download full size image".
8. **Repeat.** For more images, it stays in the same chat and sends the next prompt.
9. **Close the tab.** Claude closes the tab it opened.
10. **Bring the files in.** See the next section.
11. **Use them in the design.** Claude uploads each image, adds alt text, and picks colours from the images.

## Getting the files from your Mac to Claude

Gemini saves the images to your Downloads folder, which Claude's workspace can't see on its own. There are two ways across:

- **Folder access (needs the Claude desktop app).** You allow access to Downloads once, and Claude copies the newest image files itself.
- **Drag and drop.** You drag the files into the chat.

During the first test, the folder tool that copies files wasn't available, so drag and drop was the route that worked. If you try again with the desktop app linked, folder access may work now.

## Why it costs what it costs

A real image tool is one call: send a prompt, get a file. Driving a website takes about 10 to 20 small actions per image. That adds to the conversation Claude is carrying, so long sessions use up your Claude allowance faster. The measured first run took about 15 browser steps and one small screenshot, which is lighter than expected.

## What it relies on

The skill clicks things by their labels: the prompt box, "Download full size image". If Google renames or moves those, the skill needs a small update. See [troubleshooting](troubleshooting.md).
