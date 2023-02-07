# Lifesheet

Lifesheet ("hoja de vida" in Spanish) is an online tool that helps you build a professional resume with the help of co:here AI

<img src="./docs/landing-page.png"/>

## Features

-   CV Editor with typo highlighting (Rich Text)
    -   Initial template based on: [Apply to tech companies with this CV template](https://delacruzdev.notion.site/Apply-to-tech-companies-with-this-CV-template-fd977e7e715d4445a6ba1878a500e327)
-   Bot Tips (Every 30s, powered by co:here AI)

<img src="./docs/edit-page.png"/>

-   Save on Edit & Ready to share
-   Preview and Print page

<img src="./docs/print-page.png"/>

## Stack

[![co:here](https://img.shields.io/badge/co:here-AI-white?style=for-the-badge)](https://dashboard.cohere.ai)
[![Vue.js](https://img.shields.io/badge/vue.js-black?style=for-the-badge&logo=vue.js)](https://vuejs.org)
[![Typescript](https://img.shields.io/badge/Typescript-white?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org//)
[![Vite](https://img.shields.io/badge/vite-yellow?style=for-the-badge&logo=vite)](https://vitejs.dev)
[![Quill](https://img.shields.io/badge/Q-Quill-white?style=for-the-badge&logo=quill)](https://quilljs.com)
[![Tailwind](https://img.shields.io/badge/tailwind%20css-0f172a?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)

## Live Sample

[![lifesheet.online](https://img.shields.io/badge/lifesheet.online-white?style=for-the-badge&logo=digitalocean)](http://143.110.153.184:5173)

## Run locally

```bash
git clone git@github.com:sguerra/lifesheet.git
cd lifesheet
pnpm install

# Rename .env.sample file to .env and replace VITE_COHERE_API_KEY with your co:here API key

pnpm run dev
```

## Recommended Setup

[![pNPm](https://img.shields.io/badge/pNPm-white?style=for-the-badge&logo=pnpm)](https://pnpm.io)
[![VS Code](https://img.shields.io/badge/VS%20CODE-blue?style=for-the-badge&logo=visualstudio)](https://code.visualstudio.com/)

## Future work

-   Responsive design for mobile
-   More AI interactions on text selection for corrections / suggestions
