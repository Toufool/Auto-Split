# autosplitter
This program is used together with a speedrun timer (livesplit, wsplit, etc) that compares split images to the game screen region of your monitor and automaticlly hits your split hotkey when there is a match.

# HOW IT WORKS:

Autosplitter takes a folder of images and looks at the first image in the folder (alphabetically) and begins to compare it to the live gameplay feed on your monitor. Once that image meets the "Match % Threshold" compared to your game feed, it presses your split hot key and moves on to the next image in the folder and repeats the procedure until all images have been matched and split.

# TUTORIAL:

## DOWNLOAD AND OPEN

- Windows: https://www.dropbox.com/s/kn4wdwvgvz2ax1w/auto_splitter_app.zip?dl=0 (62.8MB)
- Unzip and open "auto_splitter_app.exe'

## SPLIT IMAGE FOLDER:
- All split images currently must be .png files
- They can be any size
- Name split images alphabetically in the order you want them to split - an easy way to do this is name the file "a_splitname.png, b_splitname.png, etc

A good split image is:
- One that is still or mostly still for a few seconds during gameplay
- One that is unique and does not repeat during the run
    - If it does repeat and you have the same two split images in a row, make sure your "pause" option is long enough so that the program doesn't split twice, and make sure the image doesn't appear in your game feed again until you want the program to split
- One that is NOT completely black or completely white - these are common loading screens that could cause false positive matches/splits. However if there is no black or white screens between splits, this is okay to use

## GAME SCREEN REGION
- Click "Set Top Left", hover your mouse over the top left corner of your game screen and wait a few seconds until the coordinates change in the program
- Click "Set Bottom Right", hover your mouse over the bottom corner of your game screen and wait a few secounds until the coordinates change in the program
- These coordinates do not have to be exact, but try to get them as accurate as you can
- Once both coordinates are set, make sure to not move your game feed (OBS, Xsplit, or any other source that you are using). The coordinates do not follow your game feed - they are viewing your monitor.
Note: Making the game screen region smaller will increase performance. See "Check FPS" in Options below
- The "Take Screenshot" button is a built in screenshot function that will take a screenshot of the game region and save it to your split image folder named screenshot_0, screenshot_1, screenshot_2, etc. Don't worry - if the file already exists, it won't overwrite your file. You might want to rename them to what is recommended in the Split Image Folder section above so that the order is correct. 

## GLOBAL TIMER HOTKEYS
- Click "Set Hotkey" on each option and make sure that they match up to what your hotkeys are in your preferred speedrun timer. These are global hotkeys and act the same as they do in livesplit, wsplit, etc. It is best to set your hotkeys in your timer program before the autosplitter.
- Only the split / start hotkey is required to start the auto splitter, the others are optional. Using the Start Auto Splitter, Reset, Undo Split, and Skip Split will not hit any key and only acts on the program.
- Currently, the Split / Start hotkey cannot accept these keys: scrolllock, backspace, capslock, shiftleft, shiftright, any windows key, altleft, altright, apps, pageup, pagedown. Using numpad while numlock is active may cause issues right now, so avoid having numlock active if possible.
- If your timer stops starting/splitting from hitting your hotkey or when the program splits, try restarting your timer program.

## OPTIONS
### Pause After Split:
- After a match occurs and the program splits, this is the amount of time the program will pause and stop comparing images before it goes to the next split.  If all of your images are unique, there is no need to change this option 
- If your split image folder has 2 or more split images in a row that are the same (for example, [this image](https://i.imgur.com/MubhHc5.png) that appears in Super Mario Odyssey each time you finish a world) make sure that you pause for enough time so that the program does not split more than once

### Check FPS
- Clicking this button will tell you how many times per second your gamefeed is being compared to the split image
- The higher the number, the more accurate the split will be. It is good to keep this number above 30
- To increase your FPS, make your Game Screen Region smaller

### % Match Threshold
- Once the program matches your game screen region with a split image with a number higher than this %, the program will split.
- If the program is not splitting, trying lowering this number
- If the program is splitting too early or not when you want it to, try raising this number. 
- 90% is generally a good starting point, and is the default option.
- The "test" option will make it so that your program will never split. This is good to use for testing split images
- Check the "Show Live % Match" option to view how your game screen region is matching to your current split image

### Start Auto Splitter
- Starts the auto splitter from your first split in your split image folder. The current split image is displayed on the bottom
- You can use your Start / Split hotkey to start the auto splitter
- Use the Reset, Undo Split, and Skip Split hotkeys or buttons as needed. Using the buttons does not activate any hotkeys (it will not affect your timer).
- Note that because it is taking so many images of your monitor per second, running the autosplitter does take a bit of processing power.

### Known Issues:
- If using LiveSplit, hotkeys may start to act strange in livesplit (timer not starting or splitting, splitting when hitting reset key, etc.) if this happens, restarting LiveSplit should fix it. 
    - To avoid this issue, it is a good idea to open the Auto Splitter app first, configure settings, and make sure it runs before opening LiveSplit.
- hotkeys & other settings don't save after closing
- On rare occurrances, when the auto splitter is running, it will stop working when using the skip or undo split hotkeys. You can just hit your reset hotkey or the reset button and start the autosplitter again if this happens.
