---
title: Instructions
date: 2022-11-29T20:09:53.181Z
image: /images/free_sample_by_wix-removebg-preview.png
tags:
  - Automation
  - SheetShuttle
  - Sorting
  - Tiers
  - Grades
draft: false
---
## How to use it?

### I﻿nstructions:

The tool was implemented to make the life of professors easier. The tool is for reading the Google Sheets sheet with the grades, in other words, the grade book. The grade book will be analyzed and will sort all of the grades between tiers in the document. Then, the program is going to create issues for those who have green, yellow, and red tiers. The professor is going to edit the message that wants to be sent, and after that, the issue will be created.

1. Add the path to your private token for both the Google Sheets and Github APIs. The path needs to be added to the python files. After doing that, the key paths need to be added to the .gitignore, so the keys are private and not uploaded to the repo.
2. W﻿hen added make sure that the Google Sheets API is working correctly. Check Google Sheets API  website. 
3. N﻿ext edit the \`create_issues\` yml, to make sure that the issues that you are creating are the right ones. The user can edit the body and the repo that they are using for issues, also the username from the person that needs to be uploaded can be in there too.

   ```
   # Create an issue
   # labels are optional
   - type: issue
     action: create
     repo: CMPSC-203-Allegheny-College-Fall-2022/Tier-comparison
     title: Green Tier
     body: This is the green tier. You are doing great!
     labels:
       - SheetShuttle
       - Automated

   # Create an issue
   # labels are optional
   - type: issue
     action: create
     repo: CMPSC-203-Allegheny-College-Fall-2022/Tier-comparison
     title: Yellow Tier
     body: This is the yellow tier. You are doing some good things, but need to get to green tier.
     labels:
       - SheetShuttle
       - Automated
   ```
4. R﻿un the file for \`ReadWriteGoogleSheet\` by running the command \`python ReadWriteGoogleSheet.py\`. To make sure that the file is sorting the data correctly. The data that needs to be displayed are the github usernames and the grades that they had for the assignment that is being analyzed. 

   ![Sorting grades](/images/screenshot-2022-12-01-122543.png "Sort")
5. A﻿fter making sure that it works correctly, you can start to run the file to post the issues to the users that you want after running the sorting. The usernames can be copied from the terminal that was displaying the grades.

   ![Creating issues](/images/issues.png "Issues")
6. N﻿ow in the ReadWriteGoogleSheets file you should be able to change the cells that need to be analyzed, in this case we have \`C2:C5\`. Then you can change the value of the letter that is inside the f-string, depending on the cells that are being analyzed.

   ```
   grades = 'C2:C5'

   sheet.format(f"C{cell.row}",{"backgroundColor": {"red": 0.0,"green": 1.0,"blue": 0.0}})
   ```