You can use the following script to install ofWorks fork<br>
Run this script from the folder you want ofWorks to be installed<br>
```bash
curl -fsSL https://dmtr.org/of.sh | bash
```
```
 o-o  o--o o       o  o-o  o--o  o  o  o-o
o   o |    |       | o   o |   | | /  |
|   | O-o  o   o   o |   | O-Oo  OO    o-o
o   o |     \ / \ /  o   o |  \  | \      |
 o-o  o      o   o    o-o  o   o o  o o--o
```
This script install everything needed (libraries, ofGen) to run your projects<br>
ofGen is a command line project generator and it will be available in your path.<br>
Tested on macOS, Windows, Linux (Ubuntu x86_64), Raspberry PI (and Ubuntu arm in github actions)<br>
<br>
After installed you can upgrade to latest ofWorks / ofLibs / ofGen by calling
```
cd $ofWorks
./ofStart.sh # or ofStart.ps1 from Windows Powershell
```

Windows: Pre-requisites are <a href="https://git-scm.com/install/windows" target="_blank">Git for Windows</a> and <a href="https://chalet-work.space/download/" target="_blank">Chalet Build System</a>.
You run the install script from git bash. after installation is complete you can use it from Powershell or Git Bash to build and run your projects.

## ofGen
ofgen tool will be installed and available in path, so you can navigate to your project folder and call it, like
```sh
cd $ofw/apps/workApp/awesome
ofgen
```
or
```sh
ofgen buildrun
```
[More ofGen info here](ofGen.md)

without parameters it will detect your platform and create the recommended templates for your platform.
Today the default ones are:

| Platform | Templates |
| :--- | :---: |
| macOS | XCode, Chalet, ZED |
| Windows | Chalet, ZED |
| Linux | Chalet, ZED |

VSCode to be re-added soon.<br>

## Chalet / ZED combo
For a unified experience in all platforms you can install <a href="https://zed.dev" target="_blank">ZED editor</a><br>
after running ofGen you can open your project: ```zed . ``` and build by pressing Command + Shift + R in macOS, or Alt + Shift + R in Windows / Linux<br>

## openFrameworks / ofWorks Differences
in ofWorks:<br>
Core doesn't have Cairo functionality. Moved aside to an addon ```ofxCairo``` (libraries are not ready yet).<br>
Core doesn't have ofLoadURL capabilities, moved aside to an addon ```ofxURL``` (libs not ready yet)<br>
This reduces 4 megabytes of final binary size.<br>
Legacy openFrameworks math is moved aside to an addon called ofxMath. <br>
Core only uses glm operations. it can be added if needed to access any of this objects: <br>
```ofPoint, ofMatrix3x3, ofMatrix4x4, ofQuaternion, ofVec2f, ofVec3f, ofVec4f, ofVectorMath```<br>
FreeImage was removed and now ofImage has a mango library backend (faster and more modern).<br>
For now loading and saving of TIF, PNG and JPG is OK. Some other operations to be implemented.<br>

## Collaboration
Feedback and collaboration is encouraged. Pull requests are very welcome.<br>
It is preferred to discuss first any feature change using issues and discussions before submitting PRs, <br>
~~~ no code lost ~~~
