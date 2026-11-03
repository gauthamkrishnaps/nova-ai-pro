# NOVA AI PRO — final starter

## Features
- Responsive chat UI and provider selector: OpenAI, Gemini, OpenRouter
- Image generation endpoint (OpenAI Images API)
- Text/Markdown document attachment (browser reads up to 5,000 chars from a max 500 KB file and adds it to a chat prompt)
- Recent chat history saved locally in the current browser
- Provider configuration status (reports presence only, never exposes secrets)
- Server-side API keys and basic safety-focused cybersecurity policy
- No visible credit counter

## Important limitations
This is a deployable starter, not a website already published to a public domain. Deployment requires your Vercel/GitHub accounts and API keys. I cannot sign in, accept terms, create paid accounts, or deploy to your accounts from this chat.
No visible credit counter does not mean unlimited free provider usage. Providers can charge, enforce quotas, or change free tiers.
Chat history is local to one browser/device; it is not cloud-synced. Document support is text/Markdown only, not PDF/DOCX. Image generation requires an OpenAI key and may incur charges.
There is no real user-account system or admin console in this starter. Adding those safely requires a configured authentication/database service and admin identity; do not use a shared hardcoded password.

## Deploy on Vercel
1. Download and extract this ZIP.
2. Create a GitHub repository and upload the files. Do not upload `.env` or `.env.local`.
3. Sign in at https://vercel.com and import the repository.
4. In Project Settings → Environment Variables, add at least one:
   - `OPENAI_API_KEY`
   - `GEMINI_API_KEY`
   - `OPENROUTER_API_KEY`
5. Optionally set model variables from `.env.example`.
6. Deploy and open the generated Vercel URL.
7. Test chat with each provider whose key you configured. Image generation uses OpenAI `gpt-image-1` and requires `OPENAI_API_KEY`.

## Local development
Requires Node.js 18+:
```bash
npm install
cp .env.example .env.local
# Put your keys in .env.local
npx vercel dev
```

## Security notes
- Keep API keys only in Vercel environment variables or local `.env.local`.
- Add authentication, rate limiting, abuse monitoring, and spending limits before public launch.
- The safety checks in this starter are not a complete security boundary. Provider policies also apply.
- Do not use the service for credential theft, phishing operations, malware, unauthorized access, or cyberattacks.

## Project tree
```text
nova-ai-pro-final/
├── api/
│   ├── chat.js
│   ├── image.js
│   └── status.js
├── public/
│   └── index.html
├── .env.example
├── .gitignore
├── package.json
├── vercel.json
└── README.md
```
