SubMonkey
==============

This bundle lets you to use the multi-platform editor [Sublime Text](http://www.sublimetext.com) as an IDE for the [monkey programming language](http://www.monkey-x.com). It is based on [monkey.sublime](https://github.com/gingerbeardman/monkey.sublime), origionaly based on [monkey.tmbundle](https://github.com/gingerbeardman/monkey.tmbundle).

Origionaly created by Matt Sephton, [http://www.gingerbeardman.com/monkey/](http://www.gingerbeardman.com/monkey/)

Shamelessly Copied/Adoped, updated, and renamed by Russell King, [http://rkpweb.com](http://www.rkpweb.com/) from Aaron Nech's forked and updated repository, [http://www.aaronnech.com](http://www.aaronnech.com/)

## Features

**Easy Installation**
With Package Controll for Sublime Text, it is quick and simple to install the bundle

**Syntax Highlighting**  
Easily see keywords, constants, strings, comments, numbers and functions/classes/methods in your code

**Auto Completion of Keywords**  
Press the Tab key to expand to the first match after typing part of a keyword, Option+Escape will present a list of matches for you to choose from

**Expand Keywords into Code**  
Press the Tab key to expand one keyword into one or more lines of code, subsequent presses of tab intelligently jump you through the resulting code allowing you to fill in multiple parameters with minimal key strokes

**Build Systems**  
Seperated by operating system in the tools menu and all build targets accessable from the command palette. Quickly build for the desktop with ctrl+B

**Easy Source Navigation**  
Navigate around your source using the index of functions, classes and methods

...and more to come

## Installation

Instructions for downloading and installing Package Manager for Sublime Text can be found here: [https://sublime.wbond.net/installation](https://sublime.wbond.net/installation)

Once installed, use Preferences->Package Control in Sublime, and click on or type "Add Repository". Enter the URL of the repository [https://github.com/Russell-King/SubMonkey](https://github.com/Russell-King/SubMonkey) at the bottom of editor.

Now, once again use Preferences->Package Control and click on or type "Install Package". Type "SubMonkey" to find the package quickly and click to install. Restart Sublime Text and you are ready to get coding!

### Adding monkey to your PATH
There are two paths in Mac OS X, the $PATH used by Terminal/shells and the Environment PATH as used by Windowed apps.  
We'll add to both, just in case you need to use trans_macos from a shell as well as Sublime Text.

There is also the $PATH variable in most Linux systems that you will need to update.

This is how sublime will be able to find your Monkey executables and compile your application with the build tools. So you must add the Monkey executables to your $PATH variable. It essentially puts executables into the global scope of the terminal and allows sublime to execute them without knowing where they are stored on your computer.

#### Adding to the Terminal/shell $PATH
	
	In OSX, it is usually something along the lines of:
    echo "export PATH=\$PATH:/user/folder/monkey/bin" >> ~/.profile

    In Linux, you can edit your ~/.bashrc file and add the line:
    export PATH=/path/to/monkey/bin:${PATH}

#### Adding to the Environment PATH / Other things

You may need to do the following as well(in OSX):

Assuming you have done the step above, in Terminal:

    defaults write ${HOME}/.MacOSX/environment PATH "${PATH}"

Alternatively, you can manually edit `~/.MacOSX/environment.plist` or use the  [RCEnvironment](http://www.rubicode.com/Software/RCEnvironment/) preference pane.  
Either way, the goal is to add your monkey/bin path to the PATH variable in your environment.

You will need to restart Mac OS X for the changes to take effect. Note that this second step may not work in Yosemite. See below section for instructions on getting 

In Linux you may need need to type "source ~/.bashrc" to load in the changes; alternatively you can restart.

In Windows you can add the bin folder inside the location you installed Monkey to your PATH by going to Control Panel->System and Security->System->Advanced system settings->Environment Varibles. Under 'System varibles' find and double click on the Path varible to add the location of the bin file to the value field(e.g., C:\Monkey\bin; ). Entries should be seperated with a semicolon.

#### OSX Yosemite 

Due to a change in how GUI apps access the PATH, the second step above for OSX may not work. I have created a build file that must be installed by hand for now until a better fix is found.

In a terminal, type "echo $PATH" and copy the result. The line should include what we added in the first step above. ( ending in something like "/user/folder/monkey/bin")

Download the build file [here](https://dl.dropboxusercontent.com/u/1348869/Monkey/Monkey%20-%20OSX%20Yosemite%20.sublime-build), unzip it, and copy the build file to Sublime's user folder. This is found by going to "Sublime text" > "Preferences" > "Browse Packages..."

Open the build file in Sublime Text and follow the commented text. You may have to restart Sublime after this, but now the new build system will appear under tools.


#### Building your Monkey files

The build system for each operating system can be found under "Tools" > "Build System". 

By default Sublime will build and run the desktop(Glfw3) target with the debug option selected.

Other build targets, including release and debug options, can be accessed from the Command Palette.



## Support
You can talk about the bundle on the [official Monkey forum](http://www.monkey-x.com/Community/_index_.php/)

Feel free to contact me on git as well. Submit an issue and i'll get back to you as soon as I can.

## Requirements
- Sublime Text 3 [http://www.sublimetext.com/3](http://www.sublimetext.com/3)
- Monkey [http://www.monkey-x.com](http://www.monkey-x.com)

## License
monkey.sublime and SubMonkey is made available under a [Creative Commons Attribution-Share Alike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0).

## Changelog(SubMonkey):

**2015-08-03**
- Added build options for Glfw2 and Glfw3.
- Updated the Yosemite build file fix to also include Glfw2 and Glfw3. 
- Now builds Glfw3 by default
- Fixed long string in the Import snippet
- Cleaned up the command palette list and removed redundent labling
- Cleaned up/Added some folders to make the package look pretty.



**2015-02-13**
- Restructured build files to cut down on clutter in interface
- Default build is now desktop_game
- New build system to allow choosing between Debug, Release, and various platform target builds from the command palette. 
- Created a work around for a bug caused by changes to OSX in Yosemite
- Updated Readme to reflect new install steps and use of the build system.

**2014-06-06**
- Renamed to SubMonkey to comply with Package Control's suggested naming convention
- Updated Desktop target build files to new Monkey syntax
- Renamed 'Monkey - glfw.sublime-build' to 'Monkey - Desktop.sublime-build'
- Updated the README file to fix/change URLS and make minor edits to the install intructions.

## Old Changelog (copied from origional and Aaron Nech's repositories):
**2014-02-15**
- Changed BUILD files adding cross platform support
- Updated instructions for easier installation using Sublime Package Manager

**2012-05-04**  
- Added DrawPoint (v50)  
- Included current TextMate language grammar  

**2011-10-08**  
- Added FirstNode, LastNode, NextNode, PrevNode, Exp (v45c)  
- Added DisableKeyboard, EnableKeyboard (v45)  
- Added ACosr, ASinr, ATan2r, ATanr, Cosr, Sinr, Tanr (v44)  
- Added DrawPoly (v43)  
- Added App: UpdateRate  
- Added Audio: music commands (v35), Discard  
- Added Graphics: DeviceHeight, DeviceWidth, Frames, HandleX, HandleY, Height, Width  
- Added Lang: Print, Length, Resize, Compare, ToLower, ToUpper, Trim  
- Added List: Backwards, Clear, Count, First, IsEmpty, Last, LastNode, ObjectEnumerator, RemoveFirst, RemoveLast, Value, ToArray  
- Added Map: Set, Values, Key  
- Added Random: Seed  
- Added Set: Insert  
- Added Stack: Insert, Pop, Push, Top  

**2011-08-11**  
- Added LANG const  

**2011-08-09**  
- Removed extraneous JOY constants  
- Added missing JoyX/Y/Z keywords  
- Added TARGET const  
- Removed binary integer grammar which was resulting in incorrect display of numerical values  

**2011-08-08**  
- Updated language definition to the latest one from monkey.tmbundle, lots of changes:  
- Added else/elseif snippet  
- Reduced number of foldable elements  
- Added keyEquivalent ^⌥⇧+M to activate bundle  
- Renamed bundle from monkey to Monkey  
- Removed preprocessor grammar  
- Removed framework grammar  
- Removed module grammar  
- Added better if/then/elseif/else/endif handling  
- Added bitwise complement operator  
- Removed superstrict reference  
- Tidied block comment grammar  
- Replaced instances of (?:(?:^|;)\s*) with neater \b (regexp boundary)  
- Removed references to integer number symbol %  
- Corrected PI constants regexp  
- Removed pointerops grammar  
- Removed unused types from types grammar  
  
**2011-06-01**  
- Added one build system per target, should default to HTML5 but may need specifying manually  
  
**2011-05-31**  
- Updated language definition to the latest one from monkey.tmbundle (v40)  
  
**2011-05-19**  
- Updated language definition to the latest one from monkey.tmbundle (v39)  
  
**2011-04-20**  
- Added workaround for path issue  
- Added installation notes  
- Fixes for some broken snippets  
- Added file_regex so errors can be located  
  
**2011-04-19**  
- Added multiple command line parameters, thanks to Adam Woodall  
  
**2011-04-18**  
- Added build system (path to trans needs to be hard coded - you will have to edit the Monkey.sublime-build file)  
  
**2011-04-08**  
- Initial release  

## To do

- support for tab [completions](http://sublimetext.info/docs/extensibility/completions.html)  
- support for context sensitive help through a [command](http://sublimetext.info/docs/extensibility/plugins.html#types-of-commands)  

