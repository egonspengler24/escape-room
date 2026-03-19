# escape-room
## ENWL Apprentice Selection Escape Room Challenge

## Description:
This project runs an "Escape Room" challenge which gives a physical team of potential apprentices the ability to complete a number of tasks, each of which generates
a code which if input correctly allows them to move onto the next step.
A countdown timer is on-screen which shows the time remaining
A visual set of steps along with descriptions and images is provided.

## Technical Notes:
* A single HTML file (index.html) contains the javascript code as well as the configuration
* Another file (authoring.html) allows the generation of hashed codes which prevent a clever user looking in the index.html source code to discover the codes.

The congiguration steps within the index.html file allow the various steps to be configured.
The system supports a user configurable time as well as multiple steps.

### Main Config:
The main config is shown in the snippet below, and behaves as follows  
Title - Detault title 
adminPin - Pin number to be input when selecting the "Admin" function (which opens up Admin configuration options)  
defaultMinutes - The default number of minutes the team will have to escape  
eventKeyDefault - The default key used to record progress in case the page is refreshed and needs to be resumed  
showStepTitlesWhenDone - true / false - Not currently used by controls if the previous steps can be used in dialogs once the finish is reached  
rateLimit - Controls the number of wrong answers allowed before a "cooldown" period is needed. In the case of the example 3 wrong answers then waits for 3 seconds before allowing a retry  
```
{
    "title": "Apprentice Escape Room",
    "adminPin": "admin",
    "defaultMinutes": 40,
    "eventKeyDefault": "escape-room-demo",
    "showStepTitlesWhenDone": true,
    "rateLimit": { "limit": 3, "cooldownSec": 3 },
    "steps": [
```

### Task Config:
The task config is shown in the snippet below, and behaves as follows  
Title - Displayed title for the step  
image - the image file and path (relative) for the step image  
imageAlt - the alt text for the image  
descriptionMd - description (allows markdown as per the example)  
description - Plan text description  
descriptionHTML - description also allwing HTML links  
codeHashes - A hashed value representing the code (which you can generate using authoring.html)  

```
"title": "Cyber Caterpillar 1",
      "image": "images/stage1.png",
      "imageAlt": "A caterpillar preventing a cyber attach",
      "descriptionMd": "**Welcome!** Complete the Cyber task to find the codes.\n\n- Note the *order*\n- Combine to reveal the code\n\nTip: Look for the best people in your team to help 👀",
      "codeHashes": ["3a7bd3e2360a3d29eea436fcfb7e44c735d117c42d1c1835420b6b9942dd4f1b"]  
},
```
### Admin Panel 
A user can select the Cog symbol at the top RHS and input the admin code (specified in the config) to gain access to the admin panel. 
Here they have the following options  
Adjust time (seconds) - This adds or removes (specify a -nus character) the specified number of seconds  
Skip to step (1..x) - This allows the admin to put in the number of a step. Press the Skip button to jump to that step  
+Time / -Time - Clicking these buttons add or remove time in 30 second increments  
End Now - Immediatley move to the end screen  
Toggle Kiosk UI - Remove the Admin panel link and the top menu text for a cleaner look  
Full Reset - Reset everything, including any existing sessions which would be able to be resumed

## Prep:

Decide your ten challenges and their codes (keep them short & memorable: e.g., BRIDGE-42).  
Use Authoring Tool to generate hashes; paste them back into index.html.  
Print the physical challenge sheets (each reveals a code).  
Set your GitHub Pages link on the room PC (or a tablet) and put it in kiosk mode via Admin.  

## On the day:
Group of 10 apprentices enters.  
Start the session, set team name & duration, press Start.  
They solve each physical task → input the code → progress unlocks.  
If you need to intervene (rare): ⚙️ admin → skip/add time or take necessary actions  
Finish triggers confetti & shows time remaining.  

### Between sessions:  
⚙️ admin → Full Reset.  
(Optional) Change the Event Key per team if you want to resume a specific run later.  
