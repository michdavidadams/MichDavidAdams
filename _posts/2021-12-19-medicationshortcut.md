---
layout: post
title:  "Medication Shortcuts"
author: Michael
tag: shortcuts
---

### These are the shortcuts I use for medication tracking.

Previously I had been using Reminders to remember to take my meds, but I found that to be unreliable due to bugs and unhelpful for as-needed meds.

1. Make a Reminders list and add your meds. 
![Reminders list](/assets/shortcuts/Medications/reminderslist.jpeg)

2. Create a calendar for your meds.
![Meds calendar](/assets/shortcuts/Medications/medicationscalendar.jpeg)

3. Make a .json file and save it to the Shortcuts folder in iCloud Drive. Make it in this format:
> {"Levothyroxine":20,"Lyrica":6}

4. For meds taken once daily, add these actions:
![Find cal event](/assets/shortcuts/Medications/findcalevents.jpeg)
![Otherwise add to cal](/assets/shortcuts/Medications/otherwiseaddtocal.jpeg)
![Find all reminders](/assets/shortcuts/Medications/findallreminders.jpeg)
![Get count](/assets/shortcuts/Medications/getcount.jpeg)
![Save](/assets/shortcuts/Medications/save.jpeg)

5. Now, when you go to take the medication, run the shortcut and it will complete the reminder, add it to the calendar, and decrease the med quantity you have left.

You can also download the shortcut [here.](https://www.icloud.com/shortcuts/7c010f7437954b1dbddc8605b4fb242a)