# NGP-005 Security Header Auditor Bot

## Overview
An automated security-header auditing workflow built using n8n. It receives audit commands through Telegram, checks five HTTP security headers, and uses AI to explain missing headers and suggest fixes.

## Features
- Telegram-based URL audit commands
- HTTP security-header checks
- AI-assisted security recommendations
- Severity-based responses: Red, Orange, and Green
- Output validation and fallback messaging

## Security Headers Checked
1. Content-Security-Policy (CSP)
2. Strict-Transport-Security (HSTS)
3. X-Frame-Options
4. X-Content-Type-Options
5. Referrer-Policy

## Technologies Used
- n8n
- Telegram Bot API
- Groq API
- JavaScript
- HTTP

## Usage
Send `/audit <URL>` to the configured Telegram bot to request an audit of an authorized target.

## Security Note
Import the workflow into n8n and configure your own Telegram and Groq credentials. Never publish API keys, bot tokens, or passwords.

## Project ID
NGP-005
