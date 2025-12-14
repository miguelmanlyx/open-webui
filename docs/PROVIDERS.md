# OpenAI-Compatible API Providers

Open WebUI supports connecting to various OpenAI-compatible API endpoints. This allows you to use different AI providers while maintaining a consistent interface.

## How to Add a Provider

1. Navigate to **Settings** → **Connections** in your Open WebUI admin panel
2. Enable the **OpenAI API** toggle
3. Click the **Add Connection** button
4. Enter the provider's API URL and API key
5. Click **Save**

## Supported Providers

### AI Badgr (Budget/Utility, OpenAI-compatible)

AI Badgr is a budget-focused AI provider offering tier-based model access.

**Configuration:**
- **Base URL**: `https://aibadgr.com/api/v1`
- **Authentication**: Bearer token (API Key)

**Model Names:**

Tier-based models (recommended):
- `basic` - Entry-level model for simple tasks
- `normal` - Standard model for general use
- `premium` - Advanced model for complex tasks (recommended default)

Power-user models (mapped automatically):
- `phi-3-mini` → maps to basic tier
- `mistral-7b` → maps to normal tier
- `llama3-8b-instruct` → maps to premium tier

OpenAI model names are also accepted and mapped automatically.

**Example Setup:**

Via UI:
1. Go to Settings → Connections
2. Enable OpenAI API
3. Click "Add Connection"
4. Set URL to: `https://aibadgr.com/api/v1`
5. Enter your AI Badgr API key
6. Save

Via Environment Variables:
```bash
export OPENAI_API_BASE_URL=https://aibadgr.com/api/v1
export OPENAI_API_KEY=your_aibadgr_api_key
```

**Verification:**

To test your connection, use the "Verify Connection" button in the connection form. A successful connection will show a success message.

**Example Usage:**

Once connected, select `premium` (or any available model) from the model dropdown in your chat interface.

### LMStudio

Local AI model hosting solution.

**Configuration:**
- **Base URL**: `http://localhost:1234/v1` (default)
- **Authentication**: Usually not required for local instances

### GroqCloud

High-performance AI inference service.

**Configuration:**
- **Base URL**: `https://api.groq.com/openai/v1`
- **Authentication**: API Key required

### Mistral AI

Mistral AI's hosted API service.

**Configuration:**
- **Base URL**: `https://api.mistral.ai/v1`
- **Authentication**: API Key required

### OpenRouter

Multi-model AI routing service.

**Configuration:**
- **Base URL**: `https://openrouter.ai/api/v1`
- **Authentication**: API Key required

## General Configuration Notes

- All OpenAI-compatible providers follow the same connection pattern
- Remove trailing slashes from URLs
- API keys are stored securely in your Open WebUI instance
- Multiple providers can be configured simultaneously
- Models from all connected providers appear in the model selector

## Troubleshooting

If you encounter connection issues:

1. Verify the API URL is correct and accessible
2. Check that your API key is valid
3. Use the "Verify Connection" button to test the connection
4. Ensure no firewall or network rules are blocking the connection
5. Check the provider's status page for any outages

For more help, visit the [Open WebUI Documentation](https://docs.openwebui.com/) or join the [Discord community](https://discord.gg/5rJgQTnV4s).
