# VulnAlert Bot — Setup Guide

## What It Does
Monitors GitHub repositories for security keywords and sends Slack alerts.

## Keywords Detected
vulnerability | exploit | CVE | XSS | SQL injection | CSRF | 0-day | breach | hack | injection | attack | bug | RCE | backdoor

## Setup Instructions

### 1. Create n8n Account
- Go to [n8n.cloud](https://n8n.cloud) and sign up
- Create a new workflow
- Import `vulnalert-workflow.json`

### 2. Create Slack App
- Go to [api.slack.com/apps](https://api.slack.com/apps)
- Create app → From scratch → Name: VulnAlert
- Add permissions: `chat:write`
- Install to workspace
- Copy Bot Token

### 3. Connect n8n to Slack
- In n8n, click Slack node
- Add credential with your Bot Token

### 4. Configure GitHub Webhook
- Go to repo Settings → Webhooks
- Add webhook with n8n URL
- Select Issues events

### 5. Activate
- Turn on the n8n workflow
- Create a test issue with "vulnerability" in the title
- Check Slack for alert
