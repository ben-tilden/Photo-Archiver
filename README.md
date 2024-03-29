# Photo-Archiver

archivePhotos.py is a python program which automatically and consistently imports photos from Apple devices to Mac via Preview.  

The most significant methods:
* transferPhotos()
	* Transfers photos from Apple devices to Mac
* sortPhotos()
	* Sorts pictures from transferPhotos into folders based on Date Modified (date created) and file extension
	* Directory options for sorting:
		* /PATH FROM TRANSFERPHOTOS/Pictures/MONTH YEAR/Pictures (for photos)
		* /PATH FROM TRANSFERPHOTOS/Pictures/MONTH YEAR/Screenshots (for screenshots)
		* /PATH FROM TRANSFERPHOTOS/Videos/MONTH YEAR (for videos)

Quick Notes on transferPhotos():
* __Because this program uses applescript, in order to for it to work, Terminal must have assistive access.__ This can be provided by adding Terminal to System Preferences > Security & Privacy > Privacy > Accessibility
* This program was developed for and tested on version 10.1 of Preview and version 10.14.6 of Mojave. 
* Preview, unfortunately, sometimes has difficulty with importing live photos, so while the JPG's of live photos will always be imported, their MOV counterparts may not. 
* Around 90% of the time, if there is an attempt by Preview to import a time-lapse video it will fail, so it is recommendeded to import time-lapse videos separately. The program is designed to exit upon finding unresponsive time-lapse videos. 
* Applescript UI navigation is dependent on maintaining control of applications and their functioning in the GUI. User interference with this will often cause the program to fail, so it is recommended not to interfere. The program is designed to exit upon nearly all failures.
	* In some cases, if the user performs specific tasks, applescript processes can become stuck in a delaying while loop. There are currently no future plans to build out fullDelay.scpt to handle these (the timing would be too variable to predict). If this seems to be the case (although it very rarely is), quitting Preview should cause the program to resolve cleanly.

Quick Notes on sortPhotos():
* See PHOTO_EXTENSION_LIST, VIDEO_EXTENSION_LIST, and RAW_EXTENSION_LIST for photos that can be imported via Preview (and thus transferPhotos)
* "Pictures" are distinguished from "Screenshots" by having .JPG as their file extension. This may be refined in future updates.

## Requirements

There is a requirements.txt file included in the main directory  
Type 'pip install -r requirements.txt' into the command line and enter and the necessary packages will install

## Built With

* os
* re
* signal
* sys
* time
* threading
* traceback
* applescript: https://pypi.org/project/applescript/
* runcmd: https://pypi.org/project/runcmd/

## Author

Ben Tilden
