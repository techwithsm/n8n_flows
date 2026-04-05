### Social Media Post Automation

**File:** `socia_media_post_automation/SociaMediaWorkflow.json`

An end-to-end AI-powered social media content pipeline that researches trending topics and generates platform-specific posts.

#### Overview

Triggered by a chat message, the workflow:

1. **Researches topics** — scrapes YouTube and X (Twitter) for relevant content and context
2. **Generates content ideas** — an AI agent produces post concepts using OpenRouter (Mistral 7B)
3. **Writes platform posts** — separate agents create tailored content for:
   - LinkedIn (400-word long-form post)
   - Twitter/X
   - Facebook
   - Instagram
4. **Finds images** — queries the Pexels API for relevant visuals
5. **Saves to Google Docs** — stores the final formatted content
6. **Sends email notification** — emails a review notification via Gmail

#### Integrations

| Service | Purpose |
|---|---|
| OpenRouter (Mistral 7B) | AI content generation for all platforms |
| YouTube & X/Twitter | Topic research and trend analysis |
| Pexels | Stock image search |
| Google Docs | Content storage and formatting |
| Gmail | Review notification emails |

#### Setup

1. Import `SociaMediaWorkflow.json` into your n8n instance
2. Configure the following credentials in n8n:
   - **OpenRouter API** — for AI generation
   - **Google Docs OAuth2** — for saving content
   - **Gmail OAuth2** — for email notifications
   - **Pexels API** — for image search
3. Activate the workflow and trigger it via the chat interface

#### Brand Voice

The LinkedIn agent is pre-configured with a brand voice focused on:
- Authentic, practitioner-style writing
- Actionable insights for marketers scaling with AI
- n8n-specific use cases (ad campaigns, outbound, content creation)
- No hashtags in body copy; exactly 3 hashtags at the end

## Repository Structure

```
n8n_flows/
└── socia_media_post_automation/
    └── SociaMediaWorkflow.json
```

## Requirements

- n8n instance (self-hosted or cloud)
- API keys for the services listed above
