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

1. Add the path to your private token for both the Google Sheets and Github APIs. The path needs to be added to the python files.
2. W﻿hen added make sure that the Google Sheets API is working correctly.
3. N﻿ext edit the \`create_issues\` yml, to make sure that the issues that you are creating are the right ones. 
4. R﻿un the file for \`ReadandWrite\` to make sure that the file is sorting the data correctly.
5. A﻿fter making sure that it works correctly, you can start to run the file to post the issues to the users that you want after running the sorting.