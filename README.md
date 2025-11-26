# ofWorks Installation & Quick Start

You can use the following script to install the **ofWorks** fork.  
Run this script from the folder you want **ofWorks** to be installed:

```bash
curl -fsSL https://ofworks.cc/of.sh | bash
```

```
 o-o  o--o o       o  o-o  o--o  o  o  o-o
o   o |    |       | o   o |   | | /  |
|   | O-o  o   o   o |   | O-Oo  OO    o-o
o   o |     \ / \ /  o   o |  \  | \      |
 o-o  o      o   o    o-o  o   o o  o o--o
```

This script installs everything needed (libraries, `ofGen`) to run your projects.  
`ofGen` is a command line project generator and it will be available in your global path.

> [!NOTE]  
> **Tested working on:**  
> macOS (Apple Silicon), Windows, Linux (Ubuntu x86_64/Pop!_OS), Raspberry PI (and Ubuntu arm in GitHub Actions)

---

### Upgrading

After installed, you can upgrade to latest **ofWorks / ofLibs / ofGen** by calling:

```sh
cd ofworks
./ofStart.sh # Windows requires Git Bash
# or ofStart.ps1 from Windows Powershell
```

---

### Windows

**Pre-requisites:**  
[Git for Windows](https://git-scm.com/install/windows) and [Chalet Build System](https://chalet-work.space/download/).

You run the install script from `Git Bash`.  
After installation is complete you can use it from `Powershell` or `Git Bash` to build and run your projects.

---

## ofGen

`ofgen` tool will be installed and available in path, so you can navigate to your project folder and call it, like:

```sh
cd ofworks/apps/workApps/awesomeApp
ofgen
```
or
```sh
ofgen buildrun
```

[More ofGen info here](ofGen.md)

Without parameters it will detect your platform and create the recommended templates for your platform. Today the default ones are:

## Templates

| Platform                | Templates              |
| :---------------------- | :--------------------: |
| macOS                   | XCode, Chalet, ZED     |
| Windows                 | Chalet, ZED            |
| Linux                   | Chalet, ZED            |
| Raspberry PI / Linux Arm| Chalet, ZED            |

VSCode to be re-added soon.  
From chalet project it is possible to export to Visual Studio, CLion, Fleet, XCode, Code::Blocks.

[More Chalet info here](chalet.md)

---

## Chalet / ZED combo

For a unified experience in all platforms you can install [ZED editor](https://zed.dev).  
After running `ofGen` you can open your project: 
```sh
zed .
```
and build by pressing <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> (macOS), or <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> (Windows / Linux).

---

## openFrameworks / ofWorks Differences

**In ofWorks:**

- Core doesn't have Cairo functionality.  
  Moved aside to an addon: `ofxCairo` (libraries are not ready yet).
- Core doesn't have `ofLoadURL` capabilities,  
  moved aside to an addon: `ofxURL` (libs not ready yet).
- This reduces 4 megabytes of final binary size.
- Legacy openFrameworks math is moved aside to an addon called `ofxMath`.
  It can be added if needed to access any of these objects:
  ```
  ofPoint, ofMatrix3x3, ofMatrix4x4, ofQuaternion, 
  ofVec2f, ofVec3f, ofVec4f, ofVectorMath
  ```
- Core only uses `glm` operations.  
- FreeImage was removed and now `ofImage` has a mango library backend (faster and more modern).
- For now loading and saving of TIF, PNG and JPG is OK.  
  Some other operations to be implemented.

---

## Collaboration

Feedback and collaboration is encouraged. Pull requests are very welcome.

It is preferred to discuss first any feature change using issues and discussions before submitting PRs.