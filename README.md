# thinLocalSnapshots
Small Applescript to automate thinning your local Time Machine snapshots. 

The script can be scheduled to run periodically as a Calendar event (follow the instructions on the link https://smallbusiness.chron.com/schedule-automator-tasks-mac-os-x-39132.html) or with a plist via launchd.

To schedule the script with a plist first edit the plist file and make sure you replace USERNAME with yours in place in the plist file. The plist is scheduled to run the script every 3 hours (10800 s) and assumes that the repository folder lies on your Desktop, therefore modify the time and repository path accordingly if needed. Lastly, open a terminal and execute the following commands in order to copy the plist file to LaunchAgents folder and then load it.

Create the LaunchAgents folder if it doesn't exist:

`mkdir -p ~/Library/LaunchAgents`

Copy the plist file to LaunchAgents folder:

`cp -p thinLocalSnapshots.plist ~/Library/LaunchAgents/`

Load the plist file:

`load -w ~/Library/LaunchAgents/thinLocalSnapshots.plist`

Happy thinning!