# Troubleshooting

Find your symptom in the left column.

| What you see | Likely cause | What to do |
|---|---|---|
| Claude says Chrome isn't connected | Chrome is closed, or the extension is off or not signed in | Open Chrome, check the Claude extension is on, then ask again |
| Claude asks you to approve the site | The extension asks permission per website | Allow gemini.google.com in the extension |
| Gemini asks you to sign in | The Chrome profile isn't signed in to Google | Sign in yourself, then ask again. Claude won't type your password |
| Image never appears | Gemini is slow, busy, or refused the prompt | Wait a minute and ask Claude to check. If Gemini shows a refusal, rephrase the prompt |
| Gemini answers in text, not an image | The prompt didn't clearly ask for an image | Start the prompt with "Generate an image:" (the skill already does this) |
| Download button not found | Google changed the page, or the controls were hidden | Ask Claude to hover over the image and try again. If it still fails, see "After Google changes the page" below |
| Claude can't find the file in Downloads | Folder access isn't granted, or the download didn't finish | Check Downloads yourself for a `Gemini_Generated_Image_*.jpeg` file, then grant access or drag it in |
| Image looks soft or grainy in the design | The chat compressed it (about 270 KB from 2 MB) | Use the original file from Downloads for final work |
| Claude usage goes up fast | Every browser step costs usage, and screenshots cost most | Ask for images in batches, and avoid asking Claude to watch every step |
| Claude stops and reports a problem | The skill stops after two failed tries on a step, by design | Read what it says, fix the cause, and ask again |

## After Google changes the page

The skill finds things by name, like the prompt box and the "Download full size image" button. If Google changes those names, or the layout, the skill can fail even though nothing is wrong on your side.

To repair it:
1. Ask Claude to open Gemini and describe what controls it sees around a generated image.
2. Update the matching lines in `skills/gemini-image-gen/SKILL.md` (the "Running it in Chrome" steps).
3. Add a line to the [changelog](../CHANGELOG.md).

## When to give up on this route

If it breaks often, or you need many images, a direct tool is more dependable. See [alternatives](alternatives.md).
