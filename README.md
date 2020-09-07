# S10 Capture app

This free Windows/macOS app is designed to help make "Screen Capturing" of live videos using applications like OBS easier and more reliable. Use it for adding custom overlays to Stage TEN streams (like closed-captions) or for recording ISO (isolated) feeds of S10 participant using OBS or other video recording software.

<a href="https://github.com/steveseguin/s10capture/releases/">Downloads for Mac and Windows Here</a>

For advanced Stage TEN settings, such as increased audio fidelity and directions on how to capture directly into Windows OBS without this capture tool, <a href="https://docs.google.com/document/d/e/2PACX-1vS3ol8Tpnu4NrqRrGjzzmcOXxocsQ7pWj3Jrb1x_essbmcC5mxRp1QFCY1LUCoVglIgF0tb2UykbFTO/pub">see this guide</a>.

For free closed-captioning using ML-based speech-to-text, see <a href="https://caption.ninja">Caption.Ninja</a>. It's compatible with S10 and OBS.

![image](https://user-images.githubusercontent.com/2575698/92375560-441eff00-f0cf-11ea-8323-71186fc7c585.png)

## Why ?
OBS on macOS currently doesn't support its Browser Source plugin all that well, so this tool is a viable alternative. It lets you cleanly screen-grab just a video stream without the need of the Browser Source plugin. It also makes it easy to select the output audio playback device, such as a Virtual Audio device: ie) https://rogueamoeba.com/loopback/ (macOS & non-free, but excellent) and https://existential.audio/blackhole/ (macOS & free)

The app also remains on top of other windows, attempts to hide the mouse cursor when possible, and provides accurate window sizes for 1:1 pixel mapping.

This S10 Capture app uses the newest version of Chromium, which is more resistant to desync, video smearing, and other issues that might exist in the native OBS browser source capture method. Even Windows users might find it beneficial.


## Settings and Parameters

The default frameless resolution of the capture window is 1280x720. The app automatically accounts for high-DPI displays, so it is always 1:1 pixel-accurate with the specified resolution on even Apple Retina displays.

The optional Command Line arguments can be seen as examples below, along with their default values.

```
capture.exe --width 1280 --height 720 --url https://s10.watch/electron
```
or for example
```
./capture -w 1280 -h 720 -u https://s10.watch/electron
```
### Audio Output 

A popular way of outputting audio from this S10 Capture app into OBS is done using a virtual audio cable. Some such cables include:

Mac Audio Options: https://rogueamoeba.com/loopback/ (macOS & non-free, but excellent) and https://existential.audio/blackhole/ (macOS & free)
Windows Audio Option: https://www.vb-audio.com/Cable/

## Notes on Using and Closing the App

- The top portion of the app is draggable, so you can move it around to place it accordingly. It is also resizable.

- Right click to bring up the context menu, which allows you to close the app. Windows users, you can also press ALT-F4 in many cases to close.

#### For Mac users:

- You can hover your mouse cursor over the top-left corner of the app to show the close button.

- Multiple versions of the app can run on macOS; just make a copy of the file with a different name to open up a new window.

- If capturing the window with OBS, you can use either DISPLAY CAPTURE with a WINDOW CROP  -or-  WINDOW CAPTURE

--- *WINDOW CAPTURE* will have a video delay of up to ~800ms, but Windows can be stacked without issue

--- *DISPLAY CAPTURE* will have no delay, but the windows cannot be stacked, which could be a problem if you only have one screen

## Building the App from Source

You'll need to download and extract the source code; or git clone it.
You'll also need npm installed.

### To run the app from source, you can:
```
npm install
npm start
```

### Building the app from source:
Building does not support cross-compiling. In order to build you must be logged in to a host having the target OS for the build. Once logged in, type the following:

```
npm install
npm run build
```

* For Mac, please also see this issue for building: https://github.com/electron-userland/electron-builder/issues/3828

And for notorization on macOS,..
```
npm install
export appleId={yourApp@dev.email}
export appleIdPassword={app-specific-password-here}
sudo -E npm run build

```



![image](https://user-images.githubusercontent.com/2575698/92375617-5bf68300-f0cf-11ea-9041-3202c90144cd.png)

#### ~ Guide and app written by Steve Seguin
