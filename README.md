# Analysing-Phishing-Email
Identify phishing characteristics in a suspicious email sample.


##Phishing Email Analyzer (using coding)##

A powerful open source toolkit for analyzing phishing emails, extracting red flags, and generating reports with contextual insights. Built for cybersecurity students, analysts, and researchers.

Features:-

  Extract and inspect sender details
  Analyze and decode email headers
  Detect suspicious links and mismatched URLs
  Identify urgent language or social engineering tricks
  Grammar/spelling analysis using NLP
  Attachment scanning hooks ready for integration (e.g., YARA, oletools)

Tools Used:-

  `flanker`   Header parsing
  `bs4`   HTML content handling
  `language tool python`   Grammar checks
  `yara`, `oletools`   Attachment analysis (optional)

 using email parser-- (using python)

from email import policy
from email.parser import BytesParser

def get_sender_info(filepath):
    with open(filepath, 'rb') as f:
        msg = BytesParser(policy=policy.default).parse(f)
    return msg['From'], msg['Reply-To'], msg['Return-Path']


##Phishing Email Analyzer (manual way)##


Use Gmail: Open email → click “⋮” → “Show Original”.
Look at From, Reply-To, Return-Path, and Received headers.

Use Online Tools:
1.Paste full email header into:

2.Google Header Analyzer

3.MXToolbox Header Analyzer
(Screenshots of performing scanning is provided)

Also What to Look For:
Mismatched domains (e.g., support@paypal.com.xyz)

Unusual domains (e.g., .ru, .tk, .ml)

Check if From, Reply-To, and Return-Path addresses don’t match (use header analyzer tools).

4. i found some suspicious links attachment inside email 
   which can be scanned through virustotal website
https://www.virustotal.com/
(scan history has been provided)


5.Check for Grammar and Spelling Errors
Many phishing emails contain:

Poor punctuation
Misused capital letters
Spelling mistakes

Professional companies proofread their emails — scammers don’t.

6.Overall Phishing Traits Summary Checklist

Trait	                           Status
Sender email mismatched	           ✅/❌
Reply-To/Return-Path suspicious	   ✅/❌
Link destinations suspicious	   ✅/❌
Urgent language used	           ✅/❌
Grammar/spelling issues	           ✅/❌
Suspicious attachments	           ✅/❌
DKIM/SPF/DMARC failed (from headers)✅/❌

If multiple red flags are present, it is very likely a phishing attempt.
