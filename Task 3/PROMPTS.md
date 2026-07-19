# Prompts

## Prompt Used
```
first fetch any last 2 aws related emails
1 I connect gmail with claude and
verified it by if there is actual last aws emails and put these emails in my readme file
2 prompt is "first fetch any last 2 aws related emails
1 I connect gmail with claude and
verified it by if there is actual last aws emails and put these emails in my readme file "
3 screenshot is
```
**Context:** Requested Claude fetch the 2 most recent AWS-related emails from the connected Gmail account, use them as verification that the Gmail connection was real, and place the actual email details in the README.
**Result:** Claude searched the connected inbox, identified the 2 most recent genuinely AWS-related emails (both AWS certification notices from certmetrics.com, dated July 19 and July 12, 2026), and recorded their subject, sender, date, and content preview in `README.md` as verification evidence.

## Key Takeaways
- Using real, dated, sender-specific email content as verification is a stronger signal than a generic "connection successful" message — it proves the connector is pulling live account data.
- Broader search terms (e.g. "AWS") can surface unrelated matches (LinkedIn posts, job alerts); narrowing to `subject:AWS` helped isolate the genuinely relevant emails.
