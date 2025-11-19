# PhishingEmailAnalysis
This project demonstrates my ability to create, analyze, and detect phishing emails. I used GoPhish to simulate a phishing campaign, then analyzed the emails to identify malicious indicators and develop detection methods.

## Tools Used
- GoPhish (phishing simulation platform)
- Email header analysis tools
- Text editor for examining raw email source

## What I Did
1. Created Phishing Campaign
Used GoPhish to create realistic phishing emails that simulated common attack scenarios:
- Fake password reset requests
- Urgent account verification emails
- Fraudulent invoice/payment notifications

2. Email Header Analysis
- Examined email headers to identify suspicious indicators:
Red Flags Found:
- Sender domain doesn't match claimed organization
- Reply to address differs from sender address
- Missing or suspicious SPF/DKIM/DMARC authentication
- Unusual mail server origins
- Mismatched display name and email address

3. URL Analysis
- Inspected links within phishing emails:
Malicious Indicators:
- URLs that look similar to legitimate sites (typosquatting)
- Shortened URLs hiding true destination
- Links with suspicious subdomains
- HTTPS used to appear legitimate but domain is fake

4. Attachment Analysis
- Analyzed suspicious email attachments:
Warning Signs:
- Unexpected file types (.zip, .exe, .html disguised as documents)
- Files with double extensions (invoice.pdf.exe)
- Macro enabled documents from unknown senders
- Password protected archives to evade scanning

## Detection Methods
Email Filter Rules
Created rules to catch phishing attempts:
- Block emails with mismatched sender/reply to addresses
- Flag emails failing SPF/DKIM/DMARC checks
- Block common phishing keywords ("urgent," "verify account," "suspended")
- Quarantine emails with suspicious attachment types

SIEM Correlation Rules
Developed detection logic for security monitoring:
- Alert on multiple users clicking same suspicious link
- Flag emails from newly registered domains
- Detect credential submissions to noncorporate sites
- Monitor for spikes in similar emails across organization

## User Training Indicators
Documented red flags users should recognize:
- Urgent or threatening language
- Generic greetings ("Dear Customer")
- Requests for credentials or sensitive information
- Poor grammar or spelling errors
- Unexpected emails requesting action

## IOCs Extracted
Email Indicators:
- Malicious sender domains
- Suspicious IP addresses from mail headers
- Known phishing email subjects
- Malicious URLs and redirect chains
Behavioral Indicators:
- Social engineering tactics used
- Sense of urgency language patterns
- Impersonation techniques

## Skills Demonstrated
- Phishing email analysis
- Email header examination
- URL and attachment inspection
- IOC extraction and documentation
- Detection rule development
- Security awareness training concepts

Key Findings
1. Most phishing emails have multiple red flags when examined closely
2. Header analysis reveals true sender even when display name is spoofed
3. Combining technical controls with user awareness creates best defense
4. Automated detection rules significantly reduce phishing success rates

Defensive Recommendations
- Implement SPF, DKIM, and DMARC for your domain
- Use email security gateways with URL rewriting and sandboxing
- Deploy SIEM rules to detect phishing campaigns across organization
- Conduct regular phishing simulations and training
- Enable multifactor authentication to reduce credential theft impact
