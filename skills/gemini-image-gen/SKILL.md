---
name: "gemini-image-gen"
description: "Generate images with the user's own Gemini account by driving gemini.google.com in Chrome, then use them in Claude designs. Use when Emil asks to make images with Gemini."
---

# Gemini image generation via Chrome

Uses Emil's signed-in Gemini subscription (no API key, no API billing) by operating gemini.google.com in his Chrome through Claude in Chrome. Images come back through his Downloads folder and go into whatever Claude is building, usually a Design canvas.

## Before starting

1. Collect every image the task needs and write all the prompts up front. One batch per request keeps the browser overhead low.
2. Load the chrome-browser skill, then load the Chrome tools in ONE ToolSearch call: tabs_context_mcp, tabs_create_mcp, navigate, find, computer, tabs_close_mcp (add browser_batch if available).
3. If Emil asked for the images, that request already covers the downloads. Don't stop to ask again for each one.

## Writing prompts

- Start each with "Generate an image:" so Gemini creates an image and doesn't answer in text.
- Specify the subject, style (e.g. clean vector, isometric, photo), palette, lighting and aspect ratio ("wide 16:9 format", "square 1:1").
- For a set that must match, repeat the same style sentence in every prompt.
- If the design already has colours, name them in the prompt so the image fits the page.

## Running it in Chrome

1. tabs_context_mcp, then open gemini.google.com/app in a new tab, or the empty tab Chrome hands back.
2. find "prompt input box", click it, type the prompt, press Enter.
3. Wait about 20 s, then check with find (cheap text read). Gemini shows "Creating your image" while it works. An image usually takes 30 to 45 s in total.
4. Once it's done, take ONE half-scale screenshot (scale 0.5) to check the result looks right. Avoid other screenshots: text reads cost much less.
5. Hover over the image so its controls appear, then find "Download full size image" and click it.
6. For the next image in the batch, stay in the same Gemini chat: type the next prompt and repeat steps 3 to 5.
7. Close the tab when done.

If a step fails twice (button missing, page not loading, a sign-in prompt), stop and tell Emil what happened. Don't keep retrying.

## Getting the files into the workspace

- Files land in ~/Downloads as Gemini_Generated_Image_*.jpeg, each roughly 2 MB at full size.
- If the device file tools can copy files from the Mac into the workspace, use them on the newest files in Downloads (ask for Downloads folder access if it isn't connected).
- Otherwise, ask Emil to drag the files into the chat. This has been the reliable route so far. Note that chat may compress them to a few hundred KB, which is fine for mockups. For final assets, say that the full-size originals are in Downloads.
- Attached files show up under /mnt/user-data/uploads/. Copy them into the scratchpad before uploading anywhere.

## Using them in a design

- On a Design canvas, upload each image as an asset (Artifact publish with asset: true) and use the returned /_blob/ url as the image source.
- Write real alt text that describes the image.
- Pick the page's colours from the image so the two feel like one piece.

## Wrapping up

Briefly report how many images were made, which files arrived, and anything that failed. Don't recap each browser step.
