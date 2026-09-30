# Interview Quick Answer Assistant

A browser interview assistant. Press one key, say the topic, and get a short answer you can read or speak.

This repository is the public site. The application source stays in a separate private repository, so opening this GitHub Pages site does not open the source.

## Use the live app

1. Press **S** to turn voice on.
2. Hold one answer key and speak the topic. You can let go while you talk.
3. Press **Esc** to turn voice off and clear the screen.
4. Press **Y** to copy the answer.
5. Press **/** to type a topic instead.

| Key | Answer |
| --- | --- |
| **D** | Definition |
| **C** | Code example |
| **I** | Comparison |
| **E** | Practical example |
| **Q** | Interview answer |
| **K** | Key points |

Answers are looked up on this device first. A connected model is used only when that topic is not already saved and an API key has been added in Settings.

## What is public

This repository may contain:

- this overview
- the built website files that GitHub Pages serves (`index.html` and the bundled assets)

It must not contain the private source, `node_modules`, API keys, or `.env` files.

Visitors can use the live site. They cannot open the private source repository from here. The browser can still download the built page, the same way it downloads any website.

## Publish a new version

From the private app repository:

```bash
npm run build
```

Copy only the contents of `dist/` into this repository, then push this repository. GitHub Pages should serve the branch that contains those built files.

If the public repository is named `overview`, the site address is `https://<github-user>.github.io/overview/`. Build the app with that path as the Vite base, or the page assets will not load.
