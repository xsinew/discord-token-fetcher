# Discord Token Fetcher (With 2FA Support)

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/yourusername/discord-token-fetcher/blob/main/LICENSE)
A Python script demonstrating Discord's authentication flow, supporting both standard and 2FA-protected accounts for educational and research purposes.

## Table of Contents
1. [🌟 Features](#-features)
2. [⚠️ Critical Disclaimer](#️-critical-disclaimer)
3. [🛠️ Installation](#️-installation)
4. [🚀 Usage Guide](#-usage-guide)
5. [⚙️ Technical Overview](#️-technical-overview)
6. [🔒 Security Notes](#-security-notes)
7. [🐛 Troubleshooting](#-troubleshooting)
8. [📞 Contact](#-contact)

## 🌟 Features
- **Dual Authentication:** Supports standard email/password login and Time-based One-Time Password (TOTP) 2FA.
- **Modern API:** Utilizes Discord's current v9 API endpoints with proper `X-Super-Properties` and headers.
- **User-Friendly:** Provides clear, color-coded console prompts and output.
- **Secure Design:** Does not store or log tokens and has minimal dependencies.

## ⚠️ Critical Disclaimer
This project is intended **solely** for:
- Educational demonstrations of OAuth2 flows.
- Security research (with explicit permission).
- API interaction studies.

**Strictly prohibited:**
- Unauthorized access to Discord accounts.
- Harvesting user tokens.
- This code violates Discord's [Terms of Service](https://discord.com/terms).

By using this code, you acknowledge and accept full responsibility for your actions.

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package installer)

### Setup
```bash
# Clone the repository
git clone [https://github.com/RealRahan/discord-token-fetcher.git](https://github.com/RealRahan/discord-token-fetcher.git)
cd discord-token-fetcher

# Install the required library
pip install requests

# Run the script
python discord_token.py
```

## 🚀 Usage Guide

### Basic Steps

1.  Run the `discord_token.py` script.
2.  Enter your Discord email and password when prompted.
3.  If your account has 2FA enabled:
      - Open your authenticator app.
      - Enter the 6-digit verification code.
4.  Upon successful login, your Discord token will be displayed.

### Example Output

![demo review](https://cdn.discordapp.com/attachments/1358485369766678863/1367491701714718740/demo.jpg)

## ⚙️ Technical Overview

### Authentication Flow

1.  The script sends an initial login request to Discord's `/auth/login` endpoint.
2.  The server response indicates if 2FA is required (HTTP status code 400 with the `mfa` flag).
3.  For 2FA-enabled accounts, the script exchanges a temporary ticket for TOTP verification.
4.  Finally, upon successful authentication, the access token is retrieved.

## 🔒 Security Notes

  - **Token Display:** The fetched token is displayed only once and is not stored by the script.
  - **Clipboard Avoidance:** The script does not automatically copy the token to the clipboard to minimize potential exposure.
  - **HTTPS Only:** All network communication is conducted over secure HTTPS.
  - **No Proxies:** The script connects directly to Discord's servers without using intermediate proxies.
  - **Isolated Environment:** It is recommended to run this script in an isolated environment for testing purposes.
  - **Token Revocation:** After you have finished using the script for its intended purpose, consider revoking the generated token through your Discord settings.

## 🐛 Troubleshooting

| Error                     | Solution                                          |
|---------------------------|---------------------------------------------------|
| Captcha required          | Wait 1-2 hours before attempting to log in again. |
| Invalid email/password    | Double-check your login credentials.              |
| Invalid 2FA code          | Ensure the code from your authenticator app is current and entered correctly. |
| Rate limited              | Reduce the frequency of your requests.           |
| `requests` module not found | Run `pip install requests` in your terminal.     |

## 📞 Contact

For questions you can dm me:

[![Discord](https://img.shields.io/badge/_0vk-7289DA?style=flat&logo=discord&logoColor=white)](https://discord.com/users/1336772500490686535)
