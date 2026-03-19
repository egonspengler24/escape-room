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
'''

'''

### Task Config:
'''

'''


## Prep:

Decide your ten challenges and their codes (keep them short & memorable: e.g., BRIDGE-42).
Use Authoring Tool to generate hashes; paste them back into index.html.
Print the physical challenge sheets (each reveals a code).
Set your GitHub Pages link on the room PC (or a tablet) and put it in kiosk mode via Admin.



On the day:

Group of 10 apprentices enters.
Start the session, set team name & duration, press Start.
They solve each physical task → input the code → progress unlocks.
If you need to intervene (rare): ⚙️ admin → skip/add time.
Finish triggers confetti & shows time remaining.



Between sessions:

⚙️ admin → Full Reset.
(Optional) Change the Event Key per team if you want to resume a specific run later.
