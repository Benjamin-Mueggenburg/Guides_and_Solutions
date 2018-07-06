## Windows
### - Microsoft Visual C++ 10.0 is required (Unable to find vcvarsall.bat).
**The Problem** <br>
While running `python setup.py develop` you get the error `Microsoft Visual C++ 10.0 is required (Unable to find vcvarsall.bat).` <br>
**Solution** <br>
Usually you would install Visual Studio 2017, but if you don't need the IDE (which I don't) follow these steps.
Go to [https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017). Scroll down the page until you find a download for "Build Tools for Visual Studio 2017". ![Build Tools for Visual Studio 2017](https://i.imgur.com/ZueTtLm.png)
Click the download the button for Build Tools for Visual Studio. The installer should download automatically. Once downloaded run the installer! Make sure that Visual Studio Build Tools 2017 is selected to be installed. Just click next and continue. It's a pretty large install - about 3GB, so give it time to download. 

Go to your Local disk (or C:/ drive) folder. Navigate to the _Program Files (x86)_. Inside _Program Files (x86)_ there should be a folder called _Microsoft Visual Studio_. Now go to the following directory: `2017/BuildTools/VC/Auxiliary/Build`. Your file explorer should look like this:
![File Explorer](https://i.imgur.com/aAEviN8.png) And there is your vcvarsall.bat file, make sure to copy the directory of the folder it's in. Now even though you have it's on your computer you still have to add the directory to the environment variable, PATH. To do this first, on your keyboard, press **Windows Key + pause** or go through Control Panel, and then System. This will take you to a page that shows basic information. Next click 'Advanced System Settings'
![system info](https://i.imgur.com/u21GlOV.png) A small window should pop up. Click the button labelled 'Environment Variables'. ![Advanced System Settings](https://i.imgur.com/ZjoWNjp.png)
Now under the 'User Variables for Admin' heading select the `path` variable, and then edit. **Be very careful as if you delete anything then it may cause you computer to malfunction** ![System Variables](https://i.imgur.com/8YTmkOs.png)
On the new window click 'New' (step 1 in the image below) and enter in the directory of vcvarsall.bat (step 2 in the image below) that you should have copied. In my case it will be `C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools\VC\Auxiliary\Build`. ![Variable](https://i.imgur.com/W2Ewdy0.png) Press enter and your variable has been added to the Path variable. Click 'Ok' (step 3 in the image above) until you get  back to the window that shows your systems basic information - you can just exit out of this. Now you can try again, and hopefully your problem will be resolved.
