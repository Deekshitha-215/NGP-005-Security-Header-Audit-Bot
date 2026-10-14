# 🛡️ NGP-005 | Security Header Auditor Bot

An n8n-based security automation that checks HTTP security headers, uses AI to explain missing protections, and sends a structured audit report through Telegram.

**n8n · JavaScript · Groq AI · Telegram Bot API**

## 📌 Overview

NGP-005 automates basic security-header checks for a given URL. It evaluates five HTTP security headers, calculates a score, and uses an AI agent to provide simple explanations and remediation suggestions.

## ✨ Key Features

- Telegram-based URL audit requests
- Automated inspection of five security headers
- AI-generated explanations and recommended fixes
- RED, ORANGE, and GREEN severity classification
- Output validation before sending reports
- Fallback messaging when report validation fails

## 🔍 Security Headers Checked

| Header | Purpose |
|---|---|
| Content-Security-Policy (CSP) | Restricts permitted content sources |
| Strict-Transport-Security (HSTS) | Encourages HTTPS connections |
| X-Frame-Options | Helps prevent clickjacking |
| X-Content-Type-Options | Helps prevent MIME-type sniffing |
| Referrer-Policy | Controls referrer information sharing |

## 🎯 Severity Levels

| Severity | Score | Meaning |
|---|---|---|
| 🔴 RED | 0–1 / 5 | Several security headers are missing |
| 🟠 ORANGE | 2–3 / 5 | Some headers are present, but gaps remain |
| 🟢 GREEN | 4–5 / 5 | Most or all checked headers are present |

*These are project-defined severity levels based on header presence, not an overall security rating.*

## ⚙️ Workflow

1. **Telegram Trigger** receives the audit request.
2. **URL Validation** extracts and checks the requested target.
3. **HTTP Request** retrieves response information.
4. **Header Audit** checks the five configured headers and calculates the score.
5. **AI Agent** explains missing headers and suggests fixes.
6. **Output Validation** checks the generated report.
7. **Severity Routing** sends the appropriate report through Telegram.

## 🚀 Setup and Usage

**Requirements**
- n8n instance
- Telegram bot and Telegram API credentials
- Groq API key

**Setup**
1. Import the workflow JSON into n8n.
2. Configure your Telegram credentials in the relevant nodes.
3. Configure the Groq API credentials.
4. Review the URL validation rules and test with an authorised target.
5. Execute the workflow and verify the Telegram report.

Send a command in this format:

`/audit https://your-authorized-test-target.example`

## 🧰 Technologies Used

- n8n workflow automation
- JavaScript
- Telegram Bot API
- Groq AI
- HTTP response-header inspection

## 🔐 Security and Limitations

- Never publish API keys, bot tokens, or passwords.
- Test only websites you own or are authorised to assess.
- Header presence does not guarantee that a configuration is secure.
- This project checks five headers and is not a comprehensive vulnerability scanner.
- AI-generated recommendations should be reviewed before implementation.

## 📁 Repository Structure

```text
NGP-005-Security-Header-Auditor/
├── README.md
├── Security_Header_Audit_Bot_NGP-005.json
└── screenshots/
    └── workflow-overview.png
```
