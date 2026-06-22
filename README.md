# Phishing Email Analysis Project

A hands-on SOC-style investigation of real, archived phishing samples — covering header forensics, redirect-chain decoding, IOC extraction, and MITRE ATT&CK mapping, packaged the way a security team would document and respond to it.

## What's Inside

| File | Description |
|---|---|
| `sample-2075.eml` | Archived phishing sample — fake MetaMask "Reset Password" email, sent via abused Zendesk infrastructure |
| `Phishing_Incident_Report_PHISH-2075.pdf` | Completed incident report for `sample-2075.eml`, including header/SPF-DKIM-DMARC analysis, decoded redirect chain, IOC table, and MITRE ATT&CK mapping |
| `Phishing_Incident_Response_Playbook.pdf` | Reusable SOC playbook — severity matrix, 12-phase response process, and a tool reference for each phase |

## Key Finding

This case demonstrates that **passing SPF/DKIM/DMARC does not guarantee legitimacy** — the attacker registered a free Zendesk help-desk account, allowing the phishing email to pass all standard authentication checks while impersonating MetaMask Support. The "Reset Password" link routes through a legitimate Bing click-tracking redirector before landing on an unrelated, compromised domain assessed as a credential-harvesting page.

## Tools Used

Google Messageheader · MXToolbox · CyberChef · urlscan.io · VirusTotal · AbuseIPDB · WHOIS · Linux · Terminal · SHA256sum

## ⚠️ Disclaimer

Email samples are real archived phishing emails sourced from [phishing_pot](https://github.com/rf-peixoto/phishing_pot), included for educational analysis only. All URLs/IPs in the documentation are defanged. **Do not open `.eml` files in a default mail client or click any embedded links.**
