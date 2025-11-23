# Email AI Agent Workflow Setup

This N8N workflow automatically processes incoming emails using an AI agent and sends intelligent responses.

## Workflow Overview

The workflow consists of three main nodes:

1. **Email Trigger (IMAP)** - Monitors an email inbox for new messages
2. **AI Agent** - Processes the email content and generates a professional response
3. **Send Email Response** - Sends the AI-generated reply back to the sender

## Prerequisites

Before importing this workflow, ensure you have:

- N8N instance running (self-hosted or cloud)
- Email account with IMAP access enabled
- SMTP credentials for sending emails
- OpenAI API key (or compatible AI service)

## Setup Instructions

### 1. Import the Workflow

1. Open your N8N instance
2. Click on "Workflows" in the sidebar
3. Click "Import from File"
4. Select `email-ai-agent-workflow.json`

### 2. Configure Email Credentials

#### IMAP (for receiving emails):
1. Click on the "Email Trigger (IMAP)" node
2. Click "Create New Credential"
3. Enter your email settings:
   - **User**: your-email@example.com
   - **Password**: your-email-password or app-specific password
   - **Host**: imap.gmail.com (for Gmail) or your provider's IMAP server
   - **Port**: 993 (default for SSL)
   - **SSL/TLS**: Enable

#### SMTP (for sending emails):
1. Click on the "Send Email Response" node
2. Click "Create New Credential"
3. Enter your SMTP settings:
   - **User**: your-email@example.com
   - **Password**: your-email-password or app-specific password
   - **Host**: smtp.gmail.com (for Gmail) or your provider's SMTP server
   - **Port**: 465 or 587
   - **SSL/TLS**: Enable

### 3. Configure AI Credentials

1. Click on the "AI Agent" node
2. Click "Create New Credential"
3. Select "OpenAI" (or your preferred AI service)
4. Enter your API key

### 4. Customize the AI Prompt (Optional)

You can modify the AI agent's behavior by editing the prompt in the "AI Agent" node:

- Adjust the tone (formal, casual, technical)
- Add specific instructions for handling certain types of emails
- Include company-specific information or policies

### 5. Activate the Workflow

1. Click the toggle switch in the top-right corner to activate the workflow
2. The workflow will now monitor your inbox every minute

## How It Works

1. The workflow checks your inbox for new emails every minute
2. When a new email arrives, it's sent to the AI Agent
3. The AI Agent analyzes the email content and generates a professional response
4. The response is automatically sent back to the original sender

## Security Considerations

- Use app-specific passwords instead of your main email password
- Consider adding filters to only process emails from specific domains
- Review AI responses before enabling auto-send in production
- Keep your API keys secure and never commit them to version control

## Customization Ideas

- Add a filter node to only process emails with specific subjects
- Include a human-in-the-loop approval step before sending
- Log all interactions to a database or spreadsheet
- Add sentiment analysis to prioritize urgent emails
- Integrate with a CRM system

## Troubleshooting

- **Emails not being received**: Check IMAP credentials and ensure IMAP is enabled on your email account
- **Emails not being sent**: Verify SMTP credentials and check if less secure app access is enabled
- **AI not responding**: Confirm OpenAI API key is valid and has sufficient credits
- **Workflow not triggering**: Ensure the workflow is activated (toggle is ON)

## Support

For N8N documentation and community support:
- Official Docs: https://docs.n8n.io/
- Community Forum: https://community.n8n.io/
- GitHub: https://github.com/n8n-io/n8n
