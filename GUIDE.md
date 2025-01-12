# PhotoScapeXPro_on_Linux
This repo will cover my personal method in which i managed to get PhotoScape_X_Pro.exe to run properly with actual fonts
Tested on Debian 12.8

1. install wine from https://www.winehq.org/
2. download PhotoScapeXPro from the source you prefer (i'm not responsible for pirated copies distribtio, sorr)
3. download WinRAR (https://www.win-rar.com/download.html?&L=0)
4. install winetricks (sudo apt install winetricks)
5. install winrar by running the setup executable (wine [exectable_name.exe])
   Make sure you install WinRAR in partition Z:\ for easy access
6. install winetricks dependencies (here are the commands):
   -winetricks allfonts
   -winetricks windows_codecs
   -winetricks dotnet48
   -winetricks vcrun2015
   -winetricks d3dx10
   -winetricks wmp10
7. go through the PhotoScapeXPro setup and install it in partition Z:\
8. type in terminal: winecfg
9. go to graphics and check to emulate desktop.
10. run command: wine PhotoScapeXPro.exe (in the folder where PhotoScapeXPro files are installed)

From this point on, the application should run fine, especially the fonts (except: noto, it still crashes sometimes).
With this solution, PhotoScapeXPro should be quite stable and it will share fonts with your Linux system, therefore adding fonts would become easier.
Why emulate a desktop? PhotoScapeXPro uses PyQt5 for GUI and Windows and Linux implementations of this API are a bit different, therefore some bugs may appear
when running the application dirrectly on X11 or Wayland Desktop Environments. Not to mention that it might crash the whole application when selecting fonts.

For a more comfortable daily use follow the next steps as well:
11. install lutris (https://lutris.net/)
12. navigate to the folder of PhotoScapeXPro
13. create a script in terminal for starting the executable:
-nano start.sh
-type in there: wine PhotoScapeXPro.exe
-leave nano
-type in terminal: chmod +x start.sh
14. go back to lutris
15. add local game
16. call it "PhotoScapeXPro"
17. select it to be run through Linux
18. select it to execute the new start.sh script for PhotoScapeXPro

And now, you can run PhotoScapeXPro at the press of a button with good stability and near native performance, enjoy :D
