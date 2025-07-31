---
**Author**: Shaktivel Shankar Pillai (shp40) 
**Role**: PhD Researcher in Solar Physics 
**Affiliation**: [Aberystwyth University, FBAPS] 
**GitHub**: https://github.com/shaktivel-pillai
**ORCID**:
**Note**: This guide is based on personal experience setting up Obsidian on Ubuntu without sudo access. 


## What is Obsidian?
**Obsidian**is a powerful note-taking and knowledge management app designed for researchers, writers, and thinkers. It uses **Markdown files** stored locally and allows you to create a network of linked ideas.
### Key Features
- Markdown-based notes (`.md`)
- Local-first (no cloud required)
- Bi-directional linking (`[[note name]]`)
- Graph view of connected notes
- Plugin support (e.g., LaTeX, Zotero)
- Vaults for organizing workspaces


**Steps to Run Obsidian on Ubuntu Without sudo**

1. Download the AppImage
Go to: https://obsidian.md/download
Choose Linux (AppImage) and download it to your Downloads or Documents folder.

2. Make the AppImage Executable
#Option A: Using File Manager
	Right-click the .AppImage file.
	Go to Properties → Permissions tab.
	Check the box: “Allow executing file as program”.
	Close the window and double-click the file to run Obsidian.

#Option B: Using Terminal
If you prefer the terminal:
	cd ~/Downloads  # or wherever you saved the file
	chmod +x Obsidian-*.AppImage
	./Obsidian-*.AppImage

3. If you get an error when you try to run the appimage stating 
	AppImage 
	dlopen(): error loading libfuse.so.2
This means AppImages require FUSE to run. 

4. If error then do below:
Steps to Extract the AppImage (if FUSE is not available)

#Open a terminal and navigate to the folder:
	cd ~/Downloads

#Extract the AppImage:
	./Obsidian-*.AppImage --appimage-extract

#This creates a folder called squashfs-root.

#Run Obsidian:
	./squashfs-root/AppRun


5. How to Create a Desktop Shortcut (No sudo)
#Open a terminal and run:
	nano ~/.local/share/applications/obsidian.desktop

#Paste the following content (update the paths as needed):
	[Desktop Entry]
	Name=Obsidian
	Exec=/home/yourusername/Downloads/squashfs-root/AppRun
	Icon=/home/yourusername/Downloads/squashfs-root/obsidian.png
	Type=Application
	Categories=Utility;
	Terminal=false

Save and exit (Ctrl + O, Enter, then Ctrl + X).

#Make it executable:
	chmod +x ~/.local/share/applications/obsidian.desktop

**You should now see Obsidian in your application launcher.**
