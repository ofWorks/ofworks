## Chalet

Chalet is a modern build system that works with organized recipes.<br>
it works with .json and .yaml format. <br>
ofWorks favors .yaml syntax, it is much cleaner to read and accepts comments (comment out parts of the structure)
<br>
<br>
Chalet can be used in multiple ways and it is used extensively to build [ofLibs, ofWorks libraries](https://github.com/dimitre/ofLibs/).<br>
Libraries are all compiled as static libs for all platforms.<br>
<br><br>
In ofWorks projects it replaces openFrameworks make, being the default build system for all platforms.
Useful commands in this context are:
<br><br>
| Command | Description |
| :--- | :---: |
| ```chalet buildrun``` | Builds project and run |
| ```chalet clean --all``` | Clean project and intermediate files |
| ```chalet bundle``` | Bundles for distribution and export output to a folder called ```dist``` |
| ```chalet export vssolution``` | Export Visual Studio Project |
