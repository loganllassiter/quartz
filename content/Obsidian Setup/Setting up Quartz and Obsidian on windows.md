## Cloning repo and Initializing Quartz

Quartz requires **at least [Node](https://nodejs.org/)** **v18.14** and `npm` v9.3.1 to function correctly. Ensure you have this installed on your machine before continuing.

Download the latest recommended version of Node.js

![[Pasted image 20240224093010.png]]


Follow the Install wizard
![[Pasted image 20240224093054.png]]


Open the terminal and ensure that the version for node and npm meet the requirements above
![[Pasted image 20240224093805.png]]
Open GitHub desktop and clone the quartz repo onto your machine
![[Pasted image 20240224094145.png]]![[Pasted image 20240224094217.png]]


Open file explorer to your new quartz repo and open the terminal in that directory
![[Pasted image 20240224094326.png]]


Enter the following commands
- `npm i`
- `npx quartz create`
![[Pasted image 20240224094706.png]]

Open quartz > content directory and make a copy of the 'index.md' on your machine. We will need this file later.
![[Pasted image 20240224103827.png]]

Select "Empty Quartz"
![[Pasted image 20240224100750.png]]

Select "Treat links as shortest path"
![[Pasted image 20240224095308.png]]

Now copy and paste the original index.md file back into the content folder. This was reset with the new quartz installation.
![[Pasted image 20240224104102.png]]
## Setting up Obisidan.md

Download [Obsidian.md](https://obsidian.md/)

Run Obsidian and select "Open folder as vault" and open the 'quartz' folder.
![[Pasted image 20240224100058.png]]

You should now see the 'quartz' vault and the content folder.
![[Pasted image 20240224101035.png]]

Open the setting menu > Files and links
![[Pasted image 20240224101144.png]]

Change the "Default location for new attachments" to "In a subfolder under current folder" and name it 'attachments'
![[Pasted image 20240224101421.png]]

Change "Default location for new notes" to "Same folder as current file"
![[Pasted image 20240224101808.png]]

Close the Settings menu and open 'GE02-Technical-Documentation'
![[Pasted image 20240224101940.png]]

Type "testing quartz sync" under "Naomi Rodriguez"
![[Pasted image 20240224102132.png]]
Open GitHub desktop and commit and push your changes to the repo, write "quartz initialization \[Your Name Here]"
![[Pasted image 20240224102546.png]]

Open the [quartz repo](https://github.com/loganllassiter/quartz) and check the status of your quartz deployment
![[Pasted image 20240224102704.png]]

You should see the green check mark. Which means everything worked.
![[Pasted image 20240224102842.png]]

Open the url to the "[GE 02 Technical Documentation](https://loganllassiter.github.io/quartz/GE02/GE02-Technical-Documentation)" and verify your changes were made.
![[Pasted image 20240224103452.png]]

Now undo the changes made and recommit and push.

Congrats! You're all done!