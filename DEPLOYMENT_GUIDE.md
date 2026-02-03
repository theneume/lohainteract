# LOHA Dating Coach - Deployment Guide

## This is the WORKING TODAY version with Stripe integration added

## Environment Variables Required

Set these in your Render dashboard:

```
GEMINI_API_KEY = AIzaSyAdPloqiysvHwHk451wwtdn7ux9W3G4Pd4
STRIPE_SECRET_KEY = (your Stripe Restricted Key)
STRIPE_WEBHOOK_SECRET = (your webhook secret)
```

## Stripe Configuration

1. **Webhook Endpoint**: `https://lohadatingcoach.com/api/webhook`
2. **Event to listen for**: `checkout.session.completed`

## Features

- ✅ Working chat with AI
- ✅ Paywall after 5 messages ($2.95)
- ✅ Stripe payment processing
- ✅ Custom domain support (lohadatingcoach.com)
- ✅ Conversation history restored after payment
- ✅ Message limit (12 messages max to prevent timeouts)
- ✅ Gravitor Code integration
- ✅ Cultural avatars (every 5 messages)

## Deployment Steps

1. Create a new repository on GitHub
2. Upload the contents of this folder
3. Create a new Web Service on Render
4. Connect to the GitHub repository
5. Set the environment variables above
6. Deploy
7. Update Stripe webhook to point to your domain

## Files Included

- `app.py` - Main Flask application
- `templates/index.html` - Frontend
- `ai_system_prompt.txt` - AI system prompt
- `deepsyke_core_rag.json` - Deepsyke knowledge base
- `dating_coach_rag.json` - Dating coach knowledge base
- `gravitor_code_rag.json` - Gravitor Code knowledge base
- `natal_calculator.py` - Natal type calculator
- `requirements.txt` - Python dependencies
- `render.yaml` - Render configuration
- `static/` - Static files

## Custom Domain

The success URL is hardcoded to: `https://lohadatingcoach.com`

If you need to change this, edit line 598 in `app.py`.