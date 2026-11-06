# Other ways to get Gemini images into Claude

This repo uses the "drive the website" route. It is the easiest to start, but not the only one. Details below were checked in November 2026 and may change.

## Comparison

| Route | Uses your Gemini subscription quota | Setup effort | Cost to Claude usage per image | Reliability |
|---|---|---|---|---|
| **Drive Gemini in Chrome** (this repo) | Yes | Low, nothing to install beyond the Chrome extension | Highest, about 15 browser steps | Medium, breaks if Google changes the page |
| **Figma's image generator** | No, uses Figma AI credits | None if Figma is already connected | Low | High |
| **Own small tool using the Gemini API** | No, billed separately | Medium, about 100 lines of code and a key | Lowest | High |

## Gemini API with your Google AI plan

Your Google AI Pro or Ultra subscription does not give a Gemini API key, and its quota for the Gemini app does not carry over to the API. Per Google's documentation, the plan benefits in AI Studio apply to its web interface only. Direct API use through a key is billed separately.

What the plan does include is monthly Google Cloud credits:
- AI Pro: $10 per month. Ultra plans get more.
- You must activate them once in the Google Developer Program and attach them to a Cloud billing account (a card on file is needed).
- They can be spent on the Gemini API, among other things, and expire a year after they are granted.
- They go to the subscriber and cannot be shared.

So an API-based tool could be paid largely from those credits, but it would need a billing account set up first.

## Building your own tool

The idea is a small local server that wraps the Gemini API and gives Claude a `generate_image(prompt, aspect_ratio)` tool. It would save each image to a folder you connect to Claude, so no manual dragging is needed. It keeps full-size files and costs far fewer Claude steps. Add an `edit_image` tool if you want variations of an existing picture.

If you build it, keep the API key in the tool's own settings on your machine. Don't paste it into a chat.

## Figma

If Figma is connected to Claude, it can generate images with Google's Gemini image models and place them in a Figma file. It charges Figma AI credits, not your Gemini account. This is a good default for design work, because the images end up somewhere you can edit.

## What not to do

Don't use tools that grab your Gemini browser cookies and turn them into a "free API". They go against Google's terms and put your account at risk.

## Sources

- [Google AI plans, Gemini API docs](https://ai.google.dev/gemini-api/docs/google-ai-plans)
- [Google blog: new developer tools for Google AI Pro and Ultra subscribers](https://blog.google/innovation-and-ai/technology/developers-tools/gdp-premium-ai-pro-ultra/)
