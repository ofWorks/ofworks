# ░░░  ▒▒▒▒  ▓▓▓  ████ █   █    Project Generator  
░   ░ ▒    ▓     █    ██  █    for **ofWorks**  
░   ░ ▒▒▒  ▓  ▓▓ ███  █ █ █    (OpenFrameworks fork)  
░   ░ ▒    ▓   ▓ █    █  ██  
 ░░░  ▒     ▓▓▓  ████ █   █

---

**ofGen** is a command-line tool to generate ofWorks projects.

- The complete installation script already builds it and adds it to your system path.
- If you have it installed, you can simply call `ofgen` from any folder.
- If not installed, you can compile and install using:

```bash
cd ofworks/ofgen
./compile.sh # Windows requires Git Bash or ./compile.ps1 for Powershell
```

---

## 🚀 Basic Usage

Navigate to your project folder and invoke:

```bash
cd ofworks/apps/Work2026/transmutation
ofgen
```
*Without parameters, it detects your platform and installs the recommended templates.*

A favorite workflow is to run this in any openFrameworks project:

```bash
ofgen import
```

This imports project data (addons list) and creates a file called `of.yml` in your project folder.  
This file is a "recipe" with all settings required to build the project.

You can also invoke parameters directly:

```bash
cd ofworks/apps/workApps/awesomeApp
ofgen templates=zed,chalet,macos addons=ofxMidi,ofxOpencv ofpath=../../.. path=/Volumes/tool/Transcend
```

Or quickly test templates:

```bash
ofgen templates=chalet,zed
```

---

## 🗂️ Templates

Templates can mean any mix of:

- Code Editors: `zed`, `VSCode`
- Build Systems: `chalet`
- Both: `XCode`

- `ofgen open` will open the first template in your list that is a code editor.
- `ofgen buildrun` will use the first build system listed.

Example using `of.yml`:

```yaml
templates: [macos, zed, chalet]
```
- `ofgen open` ➜ Xcode
- `ofgen buildrun` ➜ xcodebuild

Another example:

```yaml
templates: [zed, chalet, macos]
```
- `ofgen open` ➜ zed
- `ofgen buildrun` ➜ chalet buildrun

---

## 📝 of.yml Recipe Example

```yaml
# name: XPFlagship2024

ofpath: ../../..

addons:
  - ofxAssimpModelLoader
  - ofxMicroUI
  # - ofxMicroUIMidiController
  - ofxTools
  - ofxScenes
  - ofxNetwork
  - ofxOsc
  # - ofxSyphon
  - ofxTweeny
  - ofxVideoRecorder
# - ofxMidi

templates: [macos, zed, chalet]

# Advanced settings
sources:
  # - ../XP/src
  # - ../DEDGE-RIO/src
  - ../XP/src/additional
  - ../Aura/src2 # only testing

defines:
  - NANOVG_GL2_IMPLEMENTATION
  - FORCE_RGFW

frameworks: [Security, IOKit]
```

---

## 🧩 Roadmap / Coming Soon

- [ ] Addons with a git address: clone automatically on missing addons when moving projects between machines, with support for specific tags or branches.

---
