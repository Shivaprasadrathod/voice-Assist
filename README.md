AI Voice Assistant — Local Server

This folder contains a simple Express server (server.js) that serves the frontend and proxies requests to the OpenAI Chat Completions API.

Quick start (PowerShell):

1. Copy `.env.example` to `.env` and add your OpenAI API key.

Copy-Item .env.example .env
# then edit .env and set OPENAI_API_KEY

2. Install dependencies:

npm install

3. Start the server:

npm start

4. Open the demo in your browser (server serves `public/`):

http://localhost:3000/ai-voice-assistant.html

Notes
- The server expects the model to return JSON only; the system prompt requests that. If the model outputs surrounding text, the server attempts to extract the JSON object from the model output.
- If you're running Node 18+, global `fetch` is used. Otherwise `node-fetch@2` is included so `require('node-fetch')` works.
- Move or place any frontend assets inside `public/` so they are served.

If you want, I can:
- Move your existing HTML into `public/` for you (done by default), or change the server to serve the project root instead.
- Add a tiny canned response endpoint for testing without OpenAI.
