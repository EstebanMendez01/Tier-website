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

### D﻿escription of the tool:

The tool was implemented to make the life of professors easier. The tool is for reading the Google Sheets sheet with the grades, in other words, the grade book. The grade book will be analyzed and will sort all of the grades between tiers in the document. Then, the program is going to create issues for those who have green, yellow, and red tiers. The professor is going to edit the message that wants to be sent, and after that, the issue will be created.

1. Add the path to your private token for both the Google Sheets and Github APIs. The private keys need to be added as a secret token on Github. This private tokens need to have a name, in this case the names are ARBORIST for Github and GOOGLE_SHEET_KEY for the Google Sheets Key. Change this to the name that you want or even better if you use the names that are here to not change anything in the code. 
2. W﻿hen added make sure that the Google Sheets API is working correctly. Check Google Sheets API  website. 
3. R﻿un the file for \`ReadWriteGoogleSheet\` by running the command \`python ReadWriteGoogleSheet.py\`. To make sure that the file is sorting the data correctly. The data that needs to be displayed are the Github usernames and the grades that they had for the assignment that is being analyzed.  This is inside the Tier-comparison repository.

   ![Sorting grades](/images/screenshot-2022-12-01-122543.png "Sort")
4. A﻿fter making sure that it works correctly, you can start the Github actions in the Tier Tester main.yml. This will post the issues and show the Github usernames with their grades and tier. 

   ![Creating issues](/images/issues.png "Issues")
5. N﻿ow in the ReadWriteGoogleSheets file you should be able to change the cells that need to be analyzed, in this case we have \`C2:C5\`. Then you can change the value of the letter that is inside the f-string, depending on the cells that are being analyzed.

   ```
   grades = 'C2:C5'

   sheet.format(f"C{cell.row}",{"backgroundColor": {"red": 0.0,"green": 1.0,"blue": 0.0}})
   ```