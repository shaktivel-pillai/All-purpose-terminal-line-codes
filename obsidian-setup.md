# What is Obsidian?

**Obsidian** is a powerful, Markdown-based note-taking and knowledge management app tailored for researchers, writers, and thinkers. It allows you to build a network of linked ideas using plain-text files stored locally.

## Key Features

- Uses `.md` (Markdown) files  
- Local-first (no cloud required)  
- Bi-directional linking (`[[note name]]`)  
- Graph view of connected notes  
- Plugin support (e.g., LaTeX, Zotero)  
- Vaults for organizing workspaces  

---

# How to Run Obsidian on Ubuntu Without `sudo`

## Step 1: Download the AppImage

- Visit: [https://obsidian.md/download](https://obsidian.mdppImage)** and download it to your `Downloads` or `Documents` folder.

## Step 2: Make the AppImage Executable

#### Option A: Using File Manager

1. Right-click the `.AppImage` file.  
2. Go to **Properties → Permissions**.  
3. Check **“Allow executing file as program”**.  
4. Close the window and double-click the file to launch Obsidian.

#### Option B: Using Terminal

```bash
cd ~/Downloads  # or the folder where you saved the file
chmod +x Obsidian-*.AppImage
./Obsidian-*.AppImage
```

## **Step 3: If You Encounter a FUSE Error**

If you see:
```bash
AppImage
dlopen(): error loading libfuse.so.2
```
*This means your system lacks FUSE, which AppImages require.*

## Step 4: Extract the AppImage (No FUSE Required)
```bash
cd ~/Downloads
./Obsidian-*.AppImage --appimage-extract
```
- This creates a folder named squashfs-root.  
Run Obsidian with:
```bash
./squashfs-root/AppRun
```
## Step 5: Create a Desktop Shortcut (No sudo)
```bash
nano ~/.local/share/applications/obsidian.desktop
```
- Paste the following content (update paths as needed):
```bash
  [Desktop Entry]
Name=Obsidian
Exec=/home/yourusername/Downloads/squashfs-root/AppRun
Icon=/home/yourusername/Downloads/squashfs-root/obsidian.png
Type=Application
Categories=Utility;
Terminal=false
```
Save and exit:  
 - Press Ctrl + O, then Enter to save.
 - Press Ctrl + X to exit.

## Step 6: Make it executable: 
```bash
chmod +x ~/.local/share/applications/obsidian.desktop
```
## *You should now see Obsidian in your application launcher.*




