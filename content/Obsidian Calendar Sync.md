---
Tags: Note
Name: Obsidian Calendar Sync
Created: 2022-11-30
---
# Obsidian Calendar Sync - [[2022-11-30]]
## Notes
[Google Apps Script](https://script.google.com/home/projects/1QVHAis6aLzVABn5ySP-j8S9poSVheDXWZm5v9tEleUyzRc8WoNIS94Ce/edit), to pull my events from my daily work calendar and turn them into markdown files with the [[Meeting Note Template]] embedded. Includes full meeting recipient list, with meeting attendance status.

Runs daily at 5:23am (just because)

Also need to maintain a [Google Sheet](https://docs.google.com/spreadsheets/d/1lbDzKateKGQ_gSAGXfCOrftLGlKI2Ei-BLKAXm3RlOE/edit#gid=0) of names and email addresses for anyone who's Google account is not setup properly by woolies IT. Some don't have a name associated with their account, so the script will search the email address in the Sheet, and returns the name if matched. The good part about obisidian is that, at any point, I can rename **one** of the markdown files that contains only an email address ([[psnedden@bigw.com]] for example) and it will rename all of them if required.

[[2023-01-13]] update: Using [[Gareth Banks]] as my example, let's see what happens on [[2023-01-17]] as I have two meetings with him. Currently, he is showing as [[Gareth Banks]]. I will rename him then and see what happens to both references here. He is currently NOT in the Google Sheet to to transpose his email to his full name. If my thinking is correct, in that a rename of one of the email references to full name will result in all email references being renamed, then that makes the Google Sheet redundant

20[[2023-01-17]] update: [[Gareth Banks]] works fine with his name appearing from Calendar, so not sure what the issue was with the SDF last week. Anyway, I created his file using email anyway, and then renamed it....resulting in all the backlinks being renamed as well (as expecteD)