# Using it

## How to ask

Describe what the images are for and say you want Gemini to make them. A few examples:

- *"Use Gemini to make 4 images for this landing page, same style."*
- *"Make a hero image for the coffee shop site with Gemini. Warm light, photo style, wide."*
- *"Generate three square illustrations with Gemini for the feature cards."*

Saying you want the images made also counts as permission to download them, so Claude doesn't stop to ask for each file.

## Ask for several at once

Claude opens Gemini once and keeps going in the same chat. Doing three images together costs less than three separate requests, because the opening and checking steps are shared.

## What makes a good prompt

Claude writes the prompts for you, but you can steer them. Each prompt should say:

| Part | Example |
|---|---|
| Subject | a small glass design studio with a desk, monitor and plants |
| Style | clean modern vector, isometric |
| Colours | soft pastels, sky blue and terracotta |
| Light | warm afternoon light |
| Shape | wide 16:9, or square 1:1 |

If the images must match each other, Claude repeats the same style sentence in every prompt. If the page already has colours, tell Claude and it will name them in the prompt so the picture fits.

## Worked example

This is the run the skill was built from.

**Prompt sent to Gemini:**
> Generate an image: a cozy isometric illustration of a tiny design studio on a floating island in the sky, a desk with a glowing monitor, plants and a small coffee mug, soft pastel colors, warm afternoon light, clean modern vector style, wide 16:9 format.

**What happened:**
1. Claude opened Gemini in Chrome and confirmed it was signed in.
2. It typed the prompt and waited about 40 seconds.
3. It took one small screenshot to check the result, then clicked "Download full size image".
4. The file landed in Downloads as `Gemini_Generated_Image_*.jpeg` (about 2 MB).
5. The image was dragged into the chat, uploaded to a design canvas, and used as the hero picture of a landing page. The page colours were chosen from the image.

## After the images arrive

- Claude uploads each one to the design and gives it alt text that describes it.
- It picks the page colours from the images so everything matches.
- It reports how many images were made and anything that failed. It does not list every click.

## Final-quality files

Images that pass through the chat get compressed. For anything you will publish, use the original files in your Downloads folder.
