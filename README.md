# AI Content Repurposer: Blog Post to Social Media Posts

Automatically transform any blog post into platform-optimized social media content using **n8n** and **AI (GPT-4o-mini)**.

![n8n](https://img.shields.io/badge/n8n-workflow-orange?logo=n8n)
![AI Powered](https://img.shields.io/badge/AI-Powered-blue?logo=openai)
![License](https://img.shields.io/badge/license-MIT-green)

## What It Does

This n8n workflow takes a blog post URL and automatically generates:

- **Twitter/X post** — Concise tweet with hashtags (280 char limit)
- **Twitter/X thread** — 3-5 tweet thread breaking down key points
- **LinkedIn post** — Professional format with hook, value points, and CTA
- **Instagram caption** — Engaging copy with emojis and relevant hashtags
- **Summary** — One-paragraph blog summary

## How It Works

1. **Webhook Trigger** — Receives a POST request with the blog URL
2. **Fetch Blog Post** — Downloads the HTML content from the URL
3. **Extract Text** — Strips HTML tags and extracts clean text
4. **AI Generate Posts** — Sends content to GPT-4o-mini with platform-specific prompts
5. **Format Output** — Structures the AI response into a clean JSON object
6. **Respond** — Returns all generated posts via webhook response

## Quick Start

### Prerequisites

- n8n installed (self-hosted or cloud)
- OpenAI API key

### Setup

1. Import the workflow - Open n8n, go to Workflows > Import from File, select workflow.json
2. Configure OpenAI credentials - Go to Credentials > Add Credential > OpenAI API
3. Activate the workflow - Toggle to Active

### Usage

Send a POST request:
curl -X POST https://your-n8n-instance.com/webhook/repurpose-content -H "Content-Type: application/json" -d '{"blog_url": "https://example.com/your-blog-post"}'

## Customization

- Change AI Model - Edit the AI node to use gpt-4o, gpt-3.5-turbo, etc.
- Add More Platforms - Modify the prompt for Facebook, TikTok, email newsletters
- Adjust Tone - Update the system prompt to match your brand voice

## License

MIT — free to use, modify, and share.

## Author

**Ivan Siyanko** — AI Automator
Website: siyanko.com | GitHub: @ivansiyanko

Built with n8n — the workflow automation platform
